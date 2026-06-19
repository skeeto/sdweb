# Minimal, mobile-oriented stable-diffusion.cpp web UI

User controls negative/positive prompts, no other parameters. Supports
regeneration and prompt editing. Images can be saved, but are otherwise
ephemeral. Relies on sd's CORS headers. First, start your sd server:

    $ sd-server -v --listen-ip 0.0.0.0 \
          --diffusion-model flux1-schnell-q8_0.gguf \
          --vae             ae.safetensors \
          --clip_l          clip_l.safetensors \
          --t5xxl           t5xxl_fp16.safetensors \
          --seed -1 --cfg-scale 1.0 --sampling-method euler --steps 4

Then visit `index.html` or <https://nullprogram.com/sdweb/>. The default
`host:port` is taken from the URL fragment, allowing for a bookmarkable
link to a particular server.
