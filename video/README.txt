All four clips are in place. Each was re-encoded from the .mov you dropped
here; the originals are in the Trash (recoverable until you empty it).

  model-anim1.mp4   Figma 2831:8129   35.9 MB -> 2.60 MB   silent
  model-anim2.mp4   Figma 2831:8135   18.4 MB -> 0.94 MB   silent
  demo-1.mp4        Figma 2832:359    95.3 MB -> 11.9 MB   with sound
  demo-2.mp4        Figma 2832:361    82.8 MB -> 12.2 MB   with sound

Why they had to be re-encoded, not just renamed:

  model-anim1/2 were already H.264, so the container swap was lossless. They
  were rescaled 1626x928 -> 1486x848 (2x their 743x424.62 box) and had the
  audio stream removed, since they play silent.

  demo-1/2 were HEVC (H.265). Safari plays HEVC; Chrome and Firefox largely do
  not, so these genuinely could not ship as-is. Re-encoded to H.264 at their
  native 1920x1240, CRF 28, AAC 128k stereo kept.

All four: yuv420p, high profile, +faststart (index at the front, so playback
starts before the file finishes downloading).

Loading: every clip is preload="none" and starts via IntersectionObserver when
it comes near the viewport, so none of the 27 MB touches the initial page load.
They pause again when scrolled away. The two demo clips autoplay muted like the
rest; the "Play With Sound" button unmutes one at a time.
