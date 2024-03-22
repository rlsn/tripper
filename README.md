# Tripper
A pipeline that generate consecutive sequence of images with SD1.5. It's quite a trip to watch images evolving. Future work may enable SDXL. Inspired by [deforum](https://deforum.art/), check it out.

<img src = "preview/sample1.gif" width ="200" /> <img src = "preview/sample2.gif" width ="200" /> <img src = "preview/sample3.gif" width ="200" />

# Features
- support loading lora models (safetensors)
- support prompt token size exceeding 75, plus negative prompt
- frame zoom in/out 
# Usage
Edit the `config.json` to configure the settings:
- `model_path`: path to your SD model safetensors
- `generate_video`: set false to generate a batch of images to choose from as an initial image, then set true to switch to video mode.
- `nframes`: total number of frames to generate
- `scheduler`: choose one from "euler", "euler a", "DDIM", "DDPM", "DPM++ 2M SDE Karras", "DPM++ 2M Karras"
- `num_inference_steps`: per image
- `lora_dict`: dictionary containing: {"[path_to_lora_safetensor]":[weight]}
- `zoom`: zoom in(<1) or out(>1)
- `strength`: roughly the similarity between two consecutive images (0~1)
- `diffusion_cadence`: how often the images get direct diffused, controls smoothness of the animation

then run with
```
python run.py
```

Have fun
