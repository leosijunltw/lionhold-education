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

## Home hero video shortlist

Picked from titles only, so preview each one before choosing, and check that the people and setting suit a Cambodian audience. All are free stock; confirm the licence on each page before using it.

**Classrooms and school life (Pexels)**
- [Children sitting in the classroom](https://www.pexels.com/video/children-sitting-in-the-classroom-3968532/)
- [Children walking together while going to school](https://www.pexels.com/video/children-walking-together-while-going-to-school-6740266/)
- [Teacher and a group of schoolchildren on a field trip](https://www.pexels.com/video/teacher-and-a-group-of-schoolchildren-on-a-field-trip-12724048/)
- [People at a graduation ceremony](https://www.pexels.com/video/people-at-a-graduation-ceremony-3969241/)

**Studying and campus (Mixkit)**
- [Students studying on a bench](https://mixkit.co/free-stock-video/students-studying-on-a-bench-4566/)
- [Young students copying the blackboard in a classroom](https://mixkit.co/free-stock-video/young-students-copying-the-blackboard-in-a-classroom-28315/)
- [A student making notes and mathematical charts on the notebook](https://mixkit.co/free-stock-video/a-student-making-notes-and-mathematical-charts-on-the-notebook-50109/)
- [Teacher points to a mathematical chart over the student notebook](https://mixkit.co/free-stock-video/teacher-points-with-his-finger-to-a-mathematical-chart-over-50114/)
- [Kid focused on homework at laptop](https://mixkit.co/free-stock-video/kid-focused-on-homework-at-laptop-101330/)
- More: [students](https://mixkit.co/free-stock-video/students/) (for example "Students walking in a university") and [studying](https://mixkit.co/free-stock-video/studying/)

**Cambodia and Phnom Penh (Pexels)**
- [Aerial view of Phnom Penh at twilight](https://www.pexels.com/video/aerial-view-of-phnom-penh-at-twilight-32934306/)
- [Aerial view of Phnom Penh's Royal Palace](https://www.pexels.com/video/aerial-view-of-phnom-penh-s-royal-palace-32926998/)
- [Aerial view of bustling Phnom Penh skyline at sunset](https://www.pexels.com/video/aerial-view-of-bustling-phnom-penh-skyline-at-sunset-32927069/)

The Capital site already opens on Phnom Penh footage, so a classroom or campus clip will make Education feel distinct.

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
