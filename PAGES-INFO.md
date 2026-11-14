# GitHub Pages

This repository publishes the single-page browser tool from the repository root using the official GitHub Pages Actions workflow at `.github/workflows/pages.yml`.

Expected site URL: https://wulinlee.github.io/CamScanner-Watermark-Remover/

The PDF processing happens locally in the visitor's browser. The page loads pdf-lib 1.17.1 from jsDelivr; the selected PDF itself is not uploaded.

The latest browser build also attempts direct text-operator removal for selectable CamScanner footer text in page content streams and Form XObjects when a usable ToUnicode font map is present; it does not paint over the page.
