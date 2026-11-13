# Where in the World? — iPad-first website prototype

## What works
- Interactive country map with **multiple songs per country** and counts.
- Culture/community browse mode, independent of political borders. Each song can list `communities` and multiple `countries` codes.
- Optional mystery challenge and searchable library.
- All 12 imported songs are initially visible.
- Teacher visibility manager: open `teacher.html`, toggle songs, then **Download updated songs.json**.

## Important publishing steps
1. Upload `index.html`, `app.js`, `style.css`, `songs.json`, and optionally `teacher.html` to a static web host such as GitHub Pages. Keep them in the same directory.
2. To change visibility, open `teacher.html` on the published website, toggle the songs, and download the revised `songs.json`. **Replace the published `songs.json` with that file.** The toggles alone do NOT change what students see.
3. For student use, do not link the teacher page. Note that a public static site cannot truly protect the teacher page or unpublished content. **To keep songs genuinely secret, remove them from the published JSON**, not merely set `visible:false`. A private authenticated editing/publishing service would be needed for secure one-click controls.
4. For a local preview, run `python -m http.server 8000` in this folder and visit `http://localhost:8000`. Opening the HTML directly from Files will not load JSON.

## Content and video caveats
- This build includes **12 presentations**, not the complete collection in both Drive folders. Information was checked against slide outlines for these entries.
- Links currently open Google Slides, not original mystery videos; slide links may reveal answers. Add original video URLs to each song's `videoUrl` field before using the mystery challenge with students.
- `countries` is a list of ISO alpha-2 codes; `communities` is a list of cultural/community labels. **Only add geographic connections that are accurate for that specific performance**, not all places where a broader culture exists.
- The map uses Leaflet/OpenStreetMap and requires internet access.
- The culture view currently uses tappable labels rather than approximate invented cultural borders.

## YouTube video test (four songs)

The following performances have YouTube links in `songs.json`: Montuno, DRUM TAO, Liquindi, and Koi Ladki Hai. On song detail pages and in Mystery Challenge, the site attempts to play YouTube in an embedded frame. A YouTube fallback link is always shown. Some videos may prohibit embedding or be restricted on school iPads.

**Publish update:** Upload `index.html`, `app.js`, `style.css`, and `songs.json` to the **root** of the existing GitHub repository, replacing the same-named files. No new repository is needed. If your repository includes a `where-in-the-world` subfolder instead of these files at root, fix the placement first.

**Mystery privacy:** YouTube player controls or opening the video on YouTube may expose titles and channel information. The website hides its own answer text until Reveal, but cannot conceal YouTube's metadata.
