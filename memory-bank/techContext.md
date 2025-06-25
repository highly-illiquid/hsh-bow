# Tech Context

## Technologies Used
- **Frontend**: HTML5, CSS3 (SCSS), JavaScript (ES6+)
- **Frameworks/Libraries**: Bootstrap 4, jQuery, Owl Carousel, AOS, Slick Carousel, etc. (as per `package.json` dependencies)
- **Build Tool**: Webpack (configured in `HTML-MASTER/webpack.config.js`)
- **CMS**: Netlify CMS (JavaScript library loaded in `admin/index.html`)
- **Hosting**: Netlify
- **Version Control**: Git

## Development Setup
- **Node.js & npm**: Required for running build scripts and managing dependencies.
- **Webpack**: Used to compile SCSS, bundle JavaScript, and process HTML partials.
- **Local Server**: A simple HTTP server (like Python's `http.server` or `live-server`) is needed for local preview, though Netlify CLI is recommended for full local testing of Netlify features.

## Technical Constraints
- **Static Site Limitations**: No server-side logic or databases are directly supported on the Netlify CDN. All dynamic content must be managed via the CMS and built into static files.
- **Netlify CMS Compatibility**: The CMS relies on Git for content storage, requiring a Git repository connected to Netlify.
- **Build Process**: Changes to source files in `HTML-MASTER` require running `npm run build` to update the `PROPERTY` directory.

## Dependencies
- Node.js (version specified in `package.json` or compatible)
- npm (Node Package Manager)
- Git

## Tool Usage Patterns
- `npm install`: To install project dependencies in `HTML-MASTER`.
- `npm run build`: To compile the source code from `HTML-MASTER` into the `PROPERTY` directory.
- `netlify.toml`: Configuration file for Netlify deployment settings (build command, publish directory, redirects).
- `admin/index.html`: Entry point for the Netlify CMS admin interface.
- `admin/config.yml`: Configuration for Netlify CMS, defining content collections and editorial workflow.
