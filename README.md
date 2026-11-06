# ComfyUI workflows

My ComfyUI workflows (UI format). To use one, drag the `.json` onto the ComfyUI canvas or copy it into `ComfyUI/user/default/workflows/`.

| Workflow | Description |
|---|---|
| `LTX-2.5_FLF_V2V_ICLoRA_Native_4K_8K.json` | LTX-2.5 video-to-video with first/last-frame guides, IC-LoRA and Tiled Fusion, built on the Native 4K/8K structure (target: RTX 3090, 24 GB) |
| `LTX-2.5_FLF_V2V_ICLoRA_SDR_to_HDR_Native_4K_8K.json` | Same FLF + IC-LoRA stage 1, then Lightricks' SDR-to-HDR Tiled Fusion pipeline (HDR-A FullHD + HDR-B 4K/8K); outputs 10-bit HLG video + ACEScg EXR, plus a linear ACEScg image output for your own EXR write (read the EXRs as ACEScg in Nuke, not ACEScct) |
| `LTX-2.5_FLF_V2V_ICLoRA_SDR_to_HDR_Native_4K_8K_Subgraphs.json` | Same as the SDR-to-HDR workflow, tidied into subgraphs: Load Models, Prompt, Source Video + Sizes, Stage 1, SDR to HDR, Upscale, HDR Refine, Decode HDR |
| `LTX-2.5_FLF_V2V_ICLoRA_TiledFusion.json` | Earlier single-pass Tiled Fusion version of the above |
| `*_GGUF_Q6K.json` (one per LTX workflow above) | Same workflows with the diffusion model loaded as GGUF Q6_K through Unet Loader (GGUF) ([ComfyUI-GGUF](https://github.com/city96/ComfyUI-GGUF)); the text encoder stays the Gemma comfy int8. Download links are in the "Downloads (GGUF Q6_K)" note in each workflow. |
| `image_flux3_klein_distilled_image_edit.json` | FLUX Klein distilled image edit |
| `Viewer_test.json` | Viewer test |
