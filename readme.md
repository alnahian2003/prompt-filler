# Prompt Filler

![Preview](screenshot.png)

Prompt Filler is a modern tool to manage and fill dynamic AI prompts with placeholders. Built with **Tailwind CSS v4** and **Alpine.js**, it detects placeholders like `[your name]`, `[email]`, `[company]` in your prompt, generates input fields automatically, and shows a live preview with smart highlighting.

## Features

- **Dynamic Placeholder Detection** – Auto-detects all placeholders in your prompts.
- **Interactive Input Fields** – Quickly fill values for each placeholder.
- **Live Preview** – Highlights filled tokens in green and unfilled tokens in red with dashed borders.
- **Demo Prompts** – Try example prompts via clickable pills.
- **Dark Mode** – Toggle between light and dark themes.
- **Copy & Export** – Copy raw or filled prompts, or download as JSON.
- **Local Storage Persistence** – Your prompts and values are saved in your browser.

## How it works

- Paste or type a prompt with placeholders in square brackets like `[your name]` or `[email]`.
- The app detects unique placeholders and builds input fields for each one.
- Type your values. The preview updates in real time.
- Copy the final text or export your values as JSON.
