# Media guide

The site ships with **placeholder** images and videos (plain navy/teal gradients) so it runs end to end. To change any picture or video, replace the file with the same name in `assets/` and push. No code changes are needed.

## Slots to fill

| File | Used on | Size | Notes |
|---|---|---|---|
| `assets/hero-video.mp4` | Home hero (desktop) | 1920×1080, 8–15 s seamless loop, no audio, under ~8 MB | Plays muted on loop behind the headline |
| `assets/hero-video-sm.mp4` | Home hero (phones) | about 720×1280 or 1280×720, under ~3 MB | Smaller copy so mobile loads fast |
| `assets/hero-poster.jpg` | Home hero poster and the soft background wash behind the home page | 1920×1080 | Shown while the video loads, and to anyone with reduced motion on |
| `assets/band-2.jpg` | Home page contact band | 1600×630 | Sits under a dark overlay, so mood matters more than detail |
| `assets/bg-platform.jpg` | AI platform page header and wash | 1800×900 | |
| `assets/bg-services.jpg` | Services page header and wash | 1800×900 | |
| `assets/bg-about-flag.jpg`, `assets/about-flag-inset.webp`, `assets/angkor-flag-mark.webp` | About page | | Currently the same as Lionhold Capital |
| `assets/bg-team-aerial.jpg` | Team page header | 1800×900 | Currently the same as Lionhold Capital |

Text sits on the **left** of every header, so keep the left half of each picture calm and dark, and put the interesting subject on the right. A dark overlay is applied automatically.

## What to look for

- **Home video:** Cambodian students studying or walking on a campus, hands writing, a student on a laptop in a bright classroom, a teacher and student at a desk. Slow camera movement, cool teal/navy colour grade to match the site.
- **AI platform:** a student at a laptop or tablet with a shallow depth of field, or a softly lit screen close-up. Avoid cartoon robots and glowing-brain clichés.
- **Services:** a mentor and student reviewing documents, a graduation scene, a school leadership meeting, or Phnom Penh campuses.
- **Contact band:** Phnom Penh skyline at dusk (Lionhold Capital's `hero-still-2.jpg` would fit well).

## Where to find them

Free-to-use libraries (always check the licence on each individual item before using it commercially, and keep a note of the source):

- [Pexels](https://www.pexels.com) and [Unsplash](https://unsplash.com) for photos, and Pexels for videos. Search terms: "students studying", "classroom laptop", "graduation", "university campus", "Phnom Penh", "Cambodia school".
- [Mixkit](https://mixkit.co/free-stock-video/students/) for free stock videos of students, and [Mixkit studying videos](https://mixkit.co/free-stock-video/studying/).
- Best of all: commission or shoot your own pictures of real Cambodian students, schools and classrooms. It will look more authentic than stock footage and be uniquely yours.

If you photograph real children, get written consent from parents or the school first.

## Getting the files to the right size

Install [ffmpeg](https://ffmpeg.org), then:

```bash
# desktop loop (no audio, web-optimised)
ffmpeg -i input.mp4 -vf "scale=1920:-2" -c:v libx264 -crf 26 -preset slow -pix_fmt yuv420p -movflags +faststart -an assets/hero-video.mp4

# phone version
ffmpeg -i input.mp4 -vf "scale=720:-2" -c:v libx264 -crf 30 -preset slow -pix_fmt yuv420p -movflags +faststart -an assets/hero-video-sm.mp4
```

For photos, export as JPEG at around 80% quality and keep each under ~300 KB.
