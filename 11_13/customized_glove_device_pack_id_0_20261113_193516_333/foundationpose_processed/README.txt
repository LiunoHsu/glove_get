333 cup: calibrated hand/object processing results

hand_object_overlay.mp4: full sequence, 1166 frames, 30fps, 38.87 seconds, 960x540.
Cyan = WiLoR hand mesh; yellow = joints; purple = cup model; green = observed visible-blue boundary.
UNCERTAIN marks a failed heuristic screening check. SCREEN PASS is not verified 3D/contact accuracy.

Method: matching-camera calibration and undistortion, previously calibrated WiLoR hand trajectory, FoundationPose-- RGB-only A1 initialization and RGBTrack masked recovery/refinement. No observed depth, contact snapping, temporal interpolation or smoothing. Original raw recording files are unchanged.

processed_trajectory.npz: frame_index (zero-based), software timestamp, original video PTS, hand joints/vertices/MANO parameters, object transforms, camera intrinsics, diagnostic flags.
Coordinates: OpenCV undistorted camera; translations and meshes in meters.
K is for 960x540 output; K_video_full is for 1920x1080 undistorted source video; D=0.
T_camera_from_object_centered applies to model/visual_centered_m.obj.
T_camera_from_source_model applies to model/source_m.obj. Do not mix these model origins.

frame_quality.csv: visible-blue coverage, full-silhouette IoU, per-frame pose steps, screening flags, original hand quality flags.
Screen rule: coverage>=0.6, full-silhouette IoU>=0.25, step<=3cm and <=20 degrees. This is a heuristic, not a confidence probability or true pose error.
Metadata and source revisions are in metadata.json; camera and model transforms are included.

Limitations: monocular depth/rotation ambiguity, occlusion errors and hand reconstruction errors remain. Hand-object contact, penetration, model physical dimensions and hardware-level tactile/video timing have not been independently verified. Existing tactile software-time alignment is retained outside this result bundle. This is a processed estimate for inspection, not validated contact ground truth.
