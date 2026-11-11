# BrainBox WinForms web port (work in progress)

This is an initial playable browser port, **not yet an exact finished conversion**. Screen elements are positioned using coordinates, colours and text extracted from the original WinForms Designer files. All original question bank text files and image assets are included.

## Local run

Install Node.js 22+, then run `npm install` and `npm run dev`.

## GitHub Pages

Create a repository, push these files to its `main` branch, then enable **Settings → Pages → Build and deployment → GitHub Actions**. The included workflow builds and deploys the site. Vite sets the base path using `GITHUB_REPOSITORY`.

## Limitations / remaining work

- The login and leaderboard currently use **browser localStorage**. They are **not shared across devices** and passwords are stored insecurely; **do not use real passwords**. Supabase authentication and database policies must be implemented before public accounts are enabled.
- Exact designer fidelity is not complete: nested panel coordinate systems, anchoring, fonts, background images, and button styling need visual comparison against the original app.
- Quiz interactions, particularly drag/drop image matching, still need full fidelity and testing.
- Settings, first-time setup, theme selection, password management and leaderboard filtering need further work.
- No `players.dat` binary data was imported because it may contain credentials; don't publish that file.


## Fidelity notes
This revision restores WinForms Designer label alignment (including the centered login heading), improves checkbox layout, and uses browser font fallbacks. Showcard Gothic and Bauhaus 93 are Windows fonts and are not embedded in the website, so exact font matching depends on browser/OS availability. The quiz logic and all screens still require side-by-side functional testing against the original Windows application. Online authentication is NOT implemented; local browser accounts are for development only.


Image loading fix: asset_manifest.json explicitly maps original WinForms resource names to public/assets files. This avoids attempting to glob Vite's public directory.
