# System Patterns

## System Architecture
The system follows a JAMstack (JavaScript, APIs, Markup) architecture.
- **Frontend**: Static HTML, CSS, and JavaScript files generated from the theme.
- **CMS**: Netlify CMS, a Git-based headless CMS.
- **Hosting**: Netlify, serving the static files and handling continuous deployment.
- **Content Storage**: Markdown and YAML files within the Git repository.

## Key Technical Decisions
- **Static Site Generation**: Leveraging the existing theme's build process to generate static HTML files for performance and security.
- **Git-based CMS**: Choosing Netlify CMS for its ease of use for non-technical users and seamless integration with Netlify's Git-based deployment workflow.
- **Content Separation**: Separating content from presentation by storing it in Markdown/YAML files, allowing for easy updates via the CMS.

## Design Patterns in Use
- **Component-based structure**: The original theme uses partials (e.g., `navbar.html`, `footer.html`), which aligns with a component-based approach.
- **Headless CMS pattern**: Content is decoupled from the frontend, managed via the CMS, and then rendered by the static site.

## Component Relationships
- **HTML-MASTER**: Source code, including HTML partials, SCSS, and JavaScript, processed by Webpack.
- **PROPERTY**: The build output, containing the fully compiled and optimized static website files. This is the directory deployed to Netlify.
- **Netlify CMS Admin**: Located at `/admin/`, it interacts with the Git repository via Git Gateway to read and write content files.
- **Content Files**: Markdown (`.md`) for properties and YAML (`.yml`) for general site data, stored in `_data/properties` and `_data/general.yml` respectively (within the `PROPERTY` directory after build).

## Critical Implementation Paths
- **Build Process**: The `npm run build` command in `HTML-MASTER` is critical for compiling source files into the `PROPERTY` directory.
- **Netlify Deployment**: Netlify's continuous deployment pipeline, triggered by Git commits, ensures that content changes from the CMS are reflected live.
- **Netlify Identity**: Essential for user authentication and authorization for the Netlify CMS.
