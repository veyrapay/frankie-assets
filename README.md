# frankie-assets

Skinwire image generation pipeline. RealVis XL + IPAdapter FaceID Plus v2. Frankie + Honey personas.

**Owner:** Studio 🎬 (as of 2026-05-18)  
**Production endpoint:** RunPod pod `near_tan_wallaby` — ComfyUI on H100 PCIe (port 8188, proxied)  
**Fallback:** PiAPI Flux Kontext (soft-NSFW, tight identity)

---

## Notebooks

| File | Purpose | Status |
|---|---|---|
| `frankie-nsfw-colab.ipynb` | Frankie explicit batch — 16 scenes, RealVis XL + IPAdapter | Active |
| `honey-nsfw-colab.ipynb` | Honey explicit batch — 10 scenes, RealVis XL + IPAdapter | Active |
| `frankie-spread-colab.ipynb` | Frankie spread/explicit batch, hair variations | Active |
| `duo-nsfw-colab.ipynb` | Tess × Sage duo — stacked IPAdapter, 10 scenes | Active |
| `frankie-comfy-server.ipynb` | Boot ComfyUI on Colab T4, expose via cloudflared | **Superseded** — RunPod is live production server |

## Reference assets

| File | Persona |
|---|---|
| `frankie-ref.png` | Frankie — dark hair, freckles, sleeve tattoos |
| `honey-ref.png` | Honey — warm blonde, soft features |
| `sage-ref.png` | Sage |
| `tess-ref.png` | Tess |

## Production wiring

The `/selfie` and `/honey` Telegram commands + the drop algo both point at:

```
COMFY_URL=https://hyvta50x0bowck-8188.proxy.runpod.net
```

Set in the `ai.openclaw.frankie-drop` and `com.skinwire.frankie-selfie` launchd plists on MM2.

Colab notebooks remain available for batch generation but are no longer the live server path.

## Model

- **Checkpoint:** `RealVisXL_V5.0_fp16.safetensors`
- **FaceID:** IPAdapter FaceID Plus V2, weight 0.8 / faceidv2 0.9
- **Sampler:** DPM++ 2M Karras, 30 steps, CFG 6.5
- **Resolution:** 832×1216

## Security

Bot token (`FRANKIE_BOT_TOKEN`) is not in this repo. Set via environment only. If you see a hardcoded token in history, it has been revoked — rotate immediately via BotFather.
