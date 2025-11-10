# package.json - Explanation

This file defines the Node.js project configuration and metadata.

## Structure Breakdown:

### `"name": "vercel-hello-world"`
- Project identifier (must be lowercase, no spaces)
- Used if published to npm registry

### `"version": "1.0.0"`
- Semantic versioning: major.minor.patch
- 1.0.0 = first stable release

### `"description": "Hello World application for Vercel deployment"`
- Brief summary of project purpose
- Displayed on npm and in search results

### `"main": "index.html"`
- Entry point file
- First file loaded when application starts

### `"scripts"`
Commands that can be run with `npm run <script-name>`:
- **`"dev"`**: Runs local development server using `npx serve`
- **`"start"`**: Same as dev, used for production environment

### `"keywords": ["vercel", "hello-world", "static-site"]`
- Search terms for npm package discovery
- Helps categorize the project

### `"author": ""`
- Creator/maintainer information
- Can include name, email, URL

### `"license": "MIT"`
- Open source license type
- MIT allows free use, modification, and distribution
