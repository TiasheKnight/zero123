---
license: openrail
datasets:
- allenai/objaverse
library_name: diffusers
pipeline_tag: image-to-image
tags:
- art
---

How to use:

1. Copy or download `inference.py` from files.
2. Build a `Zero123PlusPipeline` with the checkpoint.

Example usage:

```python
pipeline = Zero123PlusPipeline.from_pretrained('sudo-ai/zero123plus-v1.1', torch_dtype=torch.float16)
pipeline.to('cuda:0')
pipeline(
  to_rgb_image(Image.open(r"condition.png"))
).images[0].show()
```

Condition needs to be in gray (127, 127, 127) or transparent (recommended) background.
