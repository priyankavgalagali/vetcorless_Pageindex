  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
INFO:     127.0.0.1:60985 - "GET /v1/status/poll/3360c52f-d642-4c8b-a7dd-0e85928cf032 HTTP/1.1" 200 OK
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 4: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
INFO:     127.0.0.1:60984 - "GET /v1/status/poll/8f53bfcd-cb01-4636-a639-e8f60a73ebb2 HTTP/1.1" 200 OK
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
ERROR:docling.pipeline.standard_pdf_pipeline:Stage layout failed for run 5: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)
Traceback (most recent call last):
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/pipeline/standard_pdf_pipeline.py", line 296, in _process_batch
    processed_pages = list(self.model(good[0].conv_res, pages))  # type: ignore[arg-type]
                      ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/base_layout_model.py", line 35, in __call__
    predictions = self.predict_layout(conv_res, pages)
                  ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling/models/stages/layout/layout_model.py", line 182, in predict_layout
    batch_predictions = self.layout_predictor.predict_batch(  # type: ignore[attr-defined]
                        ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/utils/_contextlib.py", line 116, in decorate_context
    return func(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/docling_ibm_models/layoutmodel/layout_predictor.py", line 218, in predict_batch
    outputs = self._model(**inputs)
              ^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1920, in forward
    outputs = self.model(
              ^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 1539, in forward
    features = self.backbone(pixel_values, pixel_mask)
               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr_v2/modeling_rt_detr_v2.py", line 865, in forward
    features = self.model(pixel_values).feature_maps
               ^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1553, in _wrapped_call_impl
    return self._call_impl(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/torch/nn/modules/module.py", line 1562, in _call_impl
    return forward_call(*args, **kwargs)
           ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/models/rt_detr/modeling_rt_detr_resnet.py", line 389, in forward
    return BackboneOutput(
           ^^^^^^^^^^^^^^^
  File "<string>", line 6, in __init__
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 369, in __post_init__
    if other_fields_are_none and not is_tensor(first_field):
                                     ^^^^^^^^^^^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 118, in is_tensor
    if test_func(x):
       ^^^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 242, in is_mlx_array
    return False if not is_mlx_available() else _is_mlx(x)
                                                ^^^^^^^^^^
  File "/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/transformers/utils/generic.py", line 233, in _is_mlx
    import mlx.core as mx
ImportError: dlopen(/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so, 0x0002): Library not loaded: @rpath/libmlx.dylib
  Referenced from: <43A15A5F-68A9-3136-9CC9-235DDEEBE574> /Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/core.cpython-312-darwin.so
  Reason: tried: '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/Library/Frameworks/Python.framework/Versions/3.12/lib/python3.12/site-packages/mlx/lib/libmlx.dylib' (no such file), '/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file), '/System/Volumes/Preboot/Cryptexes/OS/Users/distiller/project/build/temp.macosx-11.0-arm64-cpython-312/mlx.core/libmlx.dylib' (no such file)