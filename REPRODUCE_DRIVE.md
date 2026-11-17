# Zalo AI Challenge 2026 — DataMate (Final Submission Artifacts)

## 1. Prebuilt Docker Image (Google Drive)
- **Image archive (`zaic2026_datamate_fall_to_fly.tar.gz`, 30.41 GiB)**: https://drive.google.com/open?id=1r8kxebI_I8-34cBebdgsWVUUCkmmBrAZ
- **MD5 file (`zaic2026_datamate_fall_to_fly.tar.gz.md5`)**: https://drive.google.com/open?id=1Oe9JetCoUikP_iRJyq_OdSJ6ZYm_8xjX
- **MD5 (`.tar.gz`)**: `c4e93479d73f43731daa9dea8080b280`
- **MD5 (uncompressed `.tar`)**: `25cd37afe549a75fd3ab35455184248e`
- **Uncompressed `.tar` size (bytes)**: `51192944640`
- **Docker tag**: `zaic2026_datamate_fall_to_fly:final`

## 2. Verify, Load & Run Inference
```bash
md5sum -c zaic2026_datamate_fall_to_fly.tar.gz.md5
gunzip -c zaic2026_datamate_fall_to_fly.tar.gz | docker load

docker run --rm --gpus all --shm-size=16g --network none \
  -v /path/to/test_data:/data:ro \
  -v /path/to/output:/result \
  zaic2026_datamate_fall_to_fly:final
```

## 3. Notes on Large Weights Excluded from Git
GitHub rejects single files > 100 MB, so `huan_luyen/qwen9b/adapter_mix/adapter_model.safetensors` (166 MB) and merged `/models/{qwen,qwen_norm4b}` are excluded from Git and already packaged inside the Docker archive above.
