# Security Policy

## Supported versions

Security fixes are provided only for the latest version on the default branch.

If you report an issue against an older copy, fork, or self-hosted deployment, reproduce it against the latest version first.

## Reporting a vulnerability

Please do **not** open a public issue for suspected security problems.

Instead:

1. Use GitHub's private vulnerability reporting for this repository, if it is enabled.
2. If private reporting is not available, contact the maintainer privately through GitHub.
3. Include clear reproduction steps, affected browser and OS, impact, and a minimal proof of concept if possible.

Useful details to include:

- browser and version
- operating system
- whether the issue happens in normal mode, PWA mode, or both
- whether the issue depends on a specific file type such as PNG, WEBP, AVIF, or SVG
- whether the issue requires a crafted file, crafted filename, share link, or batch input

You can expect:

- acknowledgement after review
- a decision on whether the report is a real security issue
- a fix or mitigation when the report is valid and reproducible

## Scope

MyPixel is a browser-based pixel art enhancement tool that runs client-side, supports batch processing, exports to multiple formats, generates shareable links, and can be installed as a PWA.

Because of that, the most relevant security areas are:

- client-side code execution or DOM injection
- unsafe handling of SVG, Base64, filenames, or share-link parameters
- data exposure through generated URLs, browser history, clipboard, cache, or PWA storage
- denial of service caused by extremely large or malformed inputs
- service worker or cache behavior that exposes stale, unexpected, or unsafe content

## What is considered a security issue

Examples of valid security reports include:

- cross-site scripting (XSS) or DOM-based injection
- arbitrary script execution through imported files, generated exports, or share-link handling
- unsafe SVG generation or rendering that can execute active content
- clipboard abuse beyond the expected export or copy actions
- private image data leaking through URLs, browser history, cache, or unexpected persistence
- service worker or offline cache behavior that exposes content in a way users would not reasonably expect
- denial of service through crafted files that freeze or crash the app far beyond normal usage limits
- dependency or supply-chain issues that materially affect users of this repository

## What is not considered a security issue

The following usually do **not** count as security vulnerabilities by themselves:

- normal force-close, slowdown, or memory use when processing very large files
- expected visibility of data that the user explicitly puts into a shareable link
- breakage in unsupported browsers or modified self-hosted deployments
- cosmetic UI bugs without security impact
- feature requests related to permissions, UX, or workflow
- reports without a realistic impact explanation

## Security expectations for this project

This project aims to keep processing on the client side. That means:

- uploaded images should stay on the user's device unless the user explicitly exports, copies, or shares data
- generated share links should be treated as sensitive if they contain encoded image data
- active content should never be introduced into exports unintentionally
- user-controlled values should be treated as untrusted input everywhere

## Safe handling guidance for users

If you use or self-host MyPixel:

- avoid sharing links that contain sensitive artwork or private images
- treat generated Base64 share links as data disclosure if posted publicly
- keep your browser updated
- review any custom modifications before self-hosting publicly
- test exported SVG output in your environment if you embed it into other sites or tools

## Disclosure policy

Please allow time for investigation and remediation before public disclosure.

Once a valid issue is understood and a fix is available, coordinated disclosure is preferred.
