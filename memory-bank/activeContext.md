# Active Context

## Current Work Focus
The current focus is on integrating Netlify CMS into the existing "Rethouse Real Estate" theme to enable non-technical content management, specifically for properties and general site text. This involves resolving build errors encountered during Netlify deployment.

## Recent Changes
- Created `admin/index.html` and `admin/config.yml` within the `PROPERTY` directory to set up Netlify CMS.
- Modified `HTML-MASTER/assets/html/partials/navbar.html` to include a link to the CMS admin interface (`/admin/`).
- Created placeholder directories for CMS content: `src/properties` and `src/data` within `HTML-MASTER`.
- Added `netlify.toml` to the project root for Netlify build configuration (`base` directory, `command`, `publish`).
- Updated `HTML-MASTER/package.json` to replace `node-sass` with `sass` and updated `sass-loader` version.
- Modified `HTML-MASTER/assets/scss/vendors/_nice-select.scss` to fix `calc()` operation error by using Sass interpolation.
- Reverted `HTML-MASTER/webpack.config.js` to re-include `exclude: /node_modules/` for image `file-loader`.
- Created `HTML-MASTER/assets/scss/vendors/_video-override.scss` to fix `owl.carousel` image path error, and updated `HTML-MASTER/assets/scss/vendors/_owl.carousel.scss` to import this override.
- Copied `owl.video.play.png` to `elements-rethouse-real-estate/HTML-MASTER/assets/images/`.

## Active Decisions and Considerations
- **CMS Choice**: Netlify CMS was chosen for its ease of use for non-technical users and seamless integration with Netlify.
- **Content Prioritization**: Initial focus is on making "Properties" and "General Text" editable, as per user's request.
- **Design Maintenance**: The existing visual design is to be maintained, with functionality being the primary goal.
- **Property Submissions**: The current "add listing" button remains a static link; no CMS integration for submissions is required at this stage.
- **Local Testing Limitations**: The Python `http.server` has limitations with MIME types for `.yml` files, which prevents full local testing of Netlify CMS. Deployment to Netlify is necessary for complete verification.
- **Build Error Resolution**: Iterative debugging of Netlify build logs to address pathing, dependency, and Sass compilation issues.

## Learnings and Project Insights
- The theme uses a Webpack build process, with `HTML-MASTER` as source and `PROPERTY` as output. Changes must be made in `HTML-MASTER` and then rebuilt.
- Netlify CMS requires a specific `div` (`#nc-root`) in its `index.html` for mounting the UI.
- Correct MIME types are crucial for `config.yml` to be parsed by Netlify CMS.
- `netlify.toml` must be at the repository root for Netlify to detect it.
- `node-sass` is deprecated and causes issues with newer Python versions; `sass` is the correct replacement.
- Sass's `calc()` function can cause errors if not used with interpolation when dealing with variables that contain `calc()` expressions.
- Webpack's `file-loader` `exclude: /node_modules/` can prevent proper image resolution from within node modules. Overriding problematic SCSS in local files is a viable solution.
