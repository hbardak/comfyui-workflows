# ComfyUI workflows

My ComfyUI workflows (UI format). To use one, drag the `.json` onto the ComfyUI canvas or copy it into `ComfyUI/user/default/workflows/`.

| Workflow | Description |
|---|---|
| `LTX-2.5_FLF_V2V_ICLoRA_Native_4K_8K.json` | LTX-2.5 video-to-video with first/last-frame guides, IC-LoRA and Tiled Fusion, built on the Native 4K/8K structure (target: RTX 3090, 24 GB) |
| `LTX-2.5_FLF_V2V_ICLoRA_SDR_to_HDR_Native_4K_8K.json` | Same FLF + IC-LoRA stage 1, then Lightricks' SDR-to-HDR Tiled Fusion pipeline: HDR-A (SDR-to-HDR IC-LoRA, FullHD) and HDR-B (refine-details IC-LoRA, 4K/8K, guided by the HDR-A result, as in Lightricks' HDR-to-HDR graph). Source through **yRead**; 10-bit HLG video + linear ACEScg into **yWrite** (EXR) and **yViewer** (read the EXRs as ACEScg in Nuke, not ACEScct) |
| `LTX-2.5_FLF_V2V_ICLoRA_SDR_to_HDR_Native_4K_8K_Subgraphs.json` | Same as the SDR-to-HDR workflow, tidied into subgraphs: Load Models, Prompt, Source Video + Sizes, Stage 1, SDR to HDR, Upscale, HDR Refine, Decode HDR |
| `LTX-2.5_FLF_V2V_ICLoRA_TiledFusion.json` | Earlier single-pass Tiled Fusion version of the above |
| `*_GGUF_Q6K.json` (one per LTX workflow above) | Same workflows with the diffusion model loaded as GGUF Q6_K through Unet Loader (GGUF) ([ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF)); the text encoder stays the Gemma comfy int8. Download links are in the "Downloads (GGUF Q6_K)" note in each workflow. |
| `image_flux3_klein_distilled_image_edit.json` | FLUX Klein distilled image edit |
| `Viewer_test.json` | Viewer test |

The SDR-to-HDR workflows use the studio nodes **yRead / yWrite** ([vfx_io](https://github.com/hbardak/vfx_io)) and **yViewer** ([vfx_viewer](https://github.com/hbardak/vfx_viewer)). Their 4K/8K pass also needs `ltx-2.5-22b-ic-lora-refine-details-1.0.safetensors` in `models/loras/` ([Lightricks/LTX-2.5-22b-IC-LoRA-Refine-Details](https://huggingface.co/Lightricks/LTX-2.5-22b-IC-LoRA-Refine-Details)).
