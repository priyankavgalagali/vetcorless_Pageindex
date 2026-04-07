# Google Analytics Visitor Counter Setup

This guide shows you how to display unique visitor counts from your existing Google Analytics on your GitHub Pages site.

## Current Status

✅ **Google Analytics tracking is already installed** (ID: G-KJZVJX9NEY)
✅ **Visitor counter UI is ready** (displays in bottom-right corner)
⏳ **Backend API needed** to fetch GA data securely

## Why Do We Need a Backend?

Google Analytics data cannot be fetched directly from the browser for security reasons (API keys would be exposed). You need a simple backend API to:
1. Securely store your GA credentials
2. Fetch data from Google Analytics API
3. Return the data to your website

## Solution Options

### Option 1: Vercel Serverless Function (Recommended - FREE)

**Pros:** Free, easy to set up, automatic HTTPS, no server management

#### Step-by-Step Setup:

1. **Create a Vercel account** at https://vercel.com (free)

2. **Create a new folder structure:**
```
your-repo/
├── api/
│   └── ga-stats.js
├── _layouts/
├── index.md
└── package.json (create this)
```

3. **Create `package.json`:**
```json
{
  "name": "ga-stats-api",
  "version": "1.0.0",
  "dependencies": {
    "@google-analytics/data": "^4.0.0"
  }
}
```

4. **Create `api/ga-stats.js`:**
```javascript
const { BetaAnalyticsDataClient } = require('@google-analytics/data');

module.exports = async (req, res) => {
  // Enable CORS
  res.setHeader('Access-Control-Allow-Origin', '*');
  res.setHeader('Access-Control-Allow-Methods', 'GET');
  
  try {
    const analyticsDataClient = new BetaAnalyticsDataClient({
      credentials: {
        client_email: process.env.GA_CLIENT_EMAIL,
        private_key: process.env.GA_PRIVATE_KEY.replace(/\\n/g, '\n'),
      },
    });

    const [response] = await analyticsDataClient.runReport({
      property: `properties/${process.env.GA_PROPERTY_ID}`,
      dateRanges: [{ startDate: '2020-01-01', endDate: 'today' }],
      metrics: [
        { name: 'totalUsers' },
        { name: 'screenPageViews' }
      ],
    });

    const totalUsers = response.rows?.[0]?.metricValues?.[0]?.value || '0';
    const pageViews = response.rows?.[0]?.metricValues?.[1]?.value || '0';

    res.status(200).json({
      totalUsers: parseInt(totalUsers),
      pageViews: parseInt(pageViews)
    });
  } catch (error) {
    console.error('Error fetching GA data:', error);
    res.status(500).json({ error: 'Failed to fetch analytics data' });
  }
};
```

5. **Set up Google Analytics API:**
   - Go to https://console.cloud.google.com/
   - Create a new project or select existing
   - Enable "Google Analytics Data API"
   - Create a Service Account:
     - Go to "IAM & Admin" > "Service Accounts"
     - Click "Create Service Account"
     - Name it "ga-stats-reader"
     - Click "Create and Continue"
     - Skip role assignment for now
     - Click "Done"
   - Create a key:
     - Click on the service account
     - Go to "Keys" tab
     - Click "Add Key" > "Create new key"
     - Choose JSON format
     - Download the key file (keep it secure!)

6. **Add Service Account to Google Analytics:**
   - Go to Google Analytics (https://analytics.google.com/)
   - Click Admin (gear icon)
   - Under "Property", click "Property Access Management"
   - Click "+" and "Add users"
   - Enter the service account email (from the JSON file)
   - Select "Viewer" role
   - Click "Add"

7. **Get your GA4 Property ID:**
   - In Google Analytics, go to Admin
   - Under "Property", click "Property Settings"
   - Copy the "Property ID" (format: 123456789)

8. **Deploy to Vercel:**
   ```bash
   # Install Vercel CLI
   npm install -g vercel
   
   # Login to Vercel
   vercel login
   
   # Deploy
   vercel
   ```

9. **Add Environment Variables in Vercel:**
   - Go to your project on Vercel dashboard
   - Click "Settings" > "Environment Variables"
   - Add these variables:
     - `GA_CLIENT_EMAIL`: (from JSON key file: client_email)
     - `GA_PRIVATE_KEY`: (from JSON key file: private_key)
     - `GA_PROPERTY_ID`: (your GA4 property ID)

10. **Update your site:**
    - In `_layouts/default.html`, replace:
      ```javascript
      const response = await fetch('https://YOUR-BACKEND-URL/api/ga-stats');
      ```
    - With your Vercel URL:
      ```javascript
      const response = await fetch('https://your-project.vercel.app/api/ga-stats');
      ```

### Option 2: Netlify Functions (Also FREE)

Similar to Vercel but uses Netlify's platform. Steps are nearly identical.

### Option 3: Simple Badge (No Backend Required)

If you want a quick solution without backend setup, use a visitor badge service:

**Add to your `index.md`:**
```markdown
![Visitors](https://api.visitorbadge.io/api/visitors?path=https%3A%2F%2Fyour-username.github.io%2Fyour-repo&label=Visitors&countColor=%23263759)
```

Replace `your-username` and `your-repo` with your actual GitHub username and repository name.

### Option 4: Google Analytics Embed (Manual Update)

Display a screenshot or manually update the count:

1. Go to your Google Analytics dashboard
2. Take a screenshot of the user count
3. Add it to your site as an image
4. Update periodically

## Testing Your Setup

1. Deploy your changes to GitHub Pages
2. Visit your site
3. Check the bottom-right corner for the visitor counter
4. Verify the numbers match your GA dashboard

## Troubleshooting

**Counter shows "---":**
- Check that your backend API is deployed and accessible
- Verify environment variables are set correctly in Vercel/Netlify
- Check browser console for error messages
- Ensure CORS is enabled on your API

**Numbers don't match GA dashboard:**
- There may be a delay (up to 24-48 hours) in GA data
- Check that you're using the correct Property ID
- Verify the service account has "Viewer" access

**API errors:**
- Verify the service account JSON key is correct
- Check that the Google Analytics Data API is enabled
- Ensure the private key format is correct (newlines preserved)

## Alternative: Use Amplitude

If you prefer Amplitude over Google Analytics:

1. Sign up at https://amplitude.com (free tier available)
2. Install Amplitude SDK:
```html
<script type="text/javascript">
  !function(){"use strict";!function(e,t){var r=e.amplitude||{_q:[],_iq:{}};if(r.invoked)e.console&&console.error&&console.error("Amplitude snippet has been loaded.");else{r.invoked=!0;var n=t.createElement("script");n.type="text/javascript",n.integrity="sha384-YOUR-INTEGRITY-HASH",n.crossOrigin="anonymous",n.async=!0,n.src="https://cdn.amplitude.com/libs/analytics-browser-2.0.0-min.js.gz",n.onload=function(){e.amplitude.runQueuedFunctions||console.log("[Amplitude] Error: could not load SDK")};var s=t.getElementsByTagName("script")[0];s.parentNode.insertBefore(n,s);var o=function(e){return function(){r._q.push({name:e,args:Array.prototype.slice.call(arguments,0)})}},i=["add","append","clearAll","prepend","set","setOnce","unset","preInsert","postInsert","remove","getUserProperties"];for(var a=0;a<i.length;a++)r.identify[i[a]]=o("identify."+i[a]);var u=["setProductId","setQuantity","setPrice","setRevenue","setRevenueType","setEventProperties"];for(var c=0;c<u.length;c++)r.revenue[u[c]]=o("revenue."+u[c]);var l=["getDeviceId","setDeviceId","getSessionId","setSessionId","getUserId","setUserId","setOptOut","setTransport","reset"];for(var p=0;p<l.length;p++)r[l[p]]=o(l[p]);e.amplitude=r}}(window,document)}();

  amplitude.init('YOUR-API-KEY');
</script>
```

3. Amplitude provides built-in dashboards and can be queried via their API

## Recommended Approach

For GitHub Pages, I recommend:
1. **Quick Start**: Use the visitor badge (Option 3) - works immediately
2. **Best Solution**: Set up Vercel serverless function (Option 1) - free, scalable, secure

## Need Help?

- Vercel Documentation: https://vercel.com/docs/functions/serverless-functions
- Google Analytics Data API: https://developers.google.com/analytics/devguides/reporting/data/v1
- Amplitude Documentation: https://www.docs.developers.amplitude.com/