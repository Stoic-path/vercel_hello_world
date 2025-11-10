# vercel.json - Explanation

This file configures how Vercel deploys and serves the application.

## Structure Breakdown:

### `"version": 2`
- Specifies Vercel configuration format version
- Version 2 is the current stable format

### `"builds": []`
Defines how Vercel should build/process files:

#### Build Configuration Object:
- **`"src": "index.html"`**
  - Source file to build
  - Points to main HTML file

- **`"use": "@vercel/static"`**
  - Builder plugin to use
  - `@vercel/static` serves files without processing
  - Perfect for static HTML/CSS/JS files

### `"routes": []`
Defines URL routing rules:

#### Route Configuration Object:
- **`"src": "/(.*)"`**
  - Regular expression matching all URL paths
  - `(.*)` captures any characters after domain

- **`"dest": "/$1"`**
  - Destination for matched requests
  - `$1` = captured group from src pattern
  - Passes requests through to original paths

## Summary:
This configuration tells Vercel to serve the HTML file statically and route all requests through without modification.
