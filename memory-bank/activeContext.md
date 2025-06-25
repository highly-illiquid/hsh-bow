# Active Context

## Current Work Focus
The current focus is on integrating Netlify CMS into the existing "Rethouse Real Estate" theme to enable non-technical content management, specifically for properties and general site text.

## Recent Changes
- Created `admin/index.html` and `admin/config.yml` within the `PROPERTY` directory to set up Netlify CMS.
- Modified `HTML-MASTER/assets/html/partials/navbar.html` to include a link to the CMS admin interface (`/admin/`).
- Created placeholder directories for CMS content: `src/properties` and `src/data` within `HTML-MASTER`.
- Added `netlify.toml` to the project root for Netlify build configuration.
- Executed `npm install` and `npm run build` in `HTML-MASTER` to reflect changes in `PROPERTY`.

## Active Decisions and Considerations
- **CMS Choice**: Netlify CMS was chosen for its ease of use for non-technical users and seamless integration with Netlify.
- **Content Prioritization**: Initial focus is on making "Properties" and "General Text" editable, as per user's request.
- **Design Maintenance**: The existing visual design is to be maintained, with functionality being the primary goal.
- **Property Submissions**: The current "add listing" button remains a static link; no CMS integration for submissions is required at this stage.
- **Local Testing Limitations**: The Python `http.server` has limitations with MIME types for `.yml` files, which prevents full local testing of Netlify CMS. Deployment to Netlify is necessary for complete verification.

## Learnings and Project Insights
- The theme uses a Webpack build process, with `HTML-MASTER` as source and `PROPERTY` as output. This means changes must be made in `HTML-MASTER` and then rebuilt.
- Netlify CMS requires a specific `div` (`#nc-root`) in its `index.html` for mounting the UI.
- Correct MIME types are crucial for `config.yml` to be parsed by Netlify CMS, which Netlify's hosting environment will handle automatically.
