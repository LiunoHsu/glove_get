WiLoR single-right-hand reconstruction

Files:
- overlay.mp4: source video with mesh and 21-joint skeleton overlay.
- reconstruction.npz: per-frame hand geometry, camera translation and mesh faces.
- metadata.json: processing settings and frame counts.

Detection confidence threshold: 0.15. A foreground/temporal gate selects at most one hand per frame. Handedness is fixed to right. Forward-backward checked optical flow bridges at most eight consecutive missed detections. A light causal EMA smooths geometry and translation.

Frame indices in reconstruction.npz are zero-based and match source video.mp4. Detection score 0 indicates an optical-flow-only box, not a detector observation. Coordinates are hand-centered in meters; add camera_translation for camera coordinates. Camera scale and anatomical accuracy remain estimates. Coverage does not establish reconstruction accuracy.
