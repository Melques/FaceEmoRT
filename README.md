# FaceEmoRT
Multi-model emotion recognition system with live webcam/stream support, FastAPI backend, React frontend, and MLflow experiment tracking.

## Architecture

```
Input (webcam / RTSP / MJPEG URL / video file)
  └─ YOLOv8-face detection
       └─ Face crop + align
            └─ Emotion classifier (swappable at runtime)
                 ├─ Custom CNN       — baseline, CPU ~2ms
                 ├─ MobileNetV2     — fine-tuned, CPU ~8ms
                 ├─ EfficientNet-B0 — best accuracy, CPU ~12ms
                 └─ ViT-tiny        — transformer, CPU ~20ms
  └─ WebSocket → React frontend
       ├─ Live annotated stream
       ├─ Emotion confidence bars
       └─ Emotion timeline chart
```

## Roadmap

- [x] Phase 0 — project skeleton
- [ ] Phase 1 — FER-2013 data prep + CNN training
- [ ] Phase 2 — YOLOv8-face + inference pipeline
- [ ] Phase 3 — FastAPI WebSocket streaming
- [ ] Phase 4 — React frontend
- [ ] Phase 5 — Video Swin-T (temporal model)
- [ ] Phase 6 — Evaluation + benchmark table
