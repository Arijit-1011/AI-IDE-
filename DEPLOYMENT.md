# Deployment Guide

This project is a static React application built with Vite. You can deploy it to any static hosting service.

## Prerequisites

1.  **Build the Project**:
    Before deploying, you must build the project to generate the static files.
    ```bash
    npm run build
    ```
    This will create a `dist` folder containing your compiled application.

2.  **Test the Build Locally**:
    You can preview the production build locally to ensure everything works:
    ```bash
    npm run preview
    ```

---

## Option 1: Deploy to Netlify (Easiest - Drag & Drop)

1.  Run `npm run build` in your terminal.
2.  Go to [Netlify Drop](https://app.netlify.com/drop).
3.  Drag and drop the `dist` folder from your project directory into the Netlify page.
4.  Netlify will automatically deploy your site and give you a live URL.

## Option 2: Deploy to Vercel (Recommended for Git users)

1.  Push your code to a GitHub repository.
2.  Go to [Vercel](https://vercel.com) and sign up/log in.
3.  Click **"Add New..."** -> **"Project"**.
4.  Import your GitHub repository.
5.  Vercel will detect it's a Vite project. The default settings should be correct:
    *   **Framework Preset**: Vite
    *   **Build Command**: `vite build` (or `npm run build`)
    *   **Output Directory**: `dist`
6.  Click **Deploy**.

## Option 3: GitHub Pages

1.  Update `vite.config.js` to set the base URL:
    ```javascript
    export default defineConfig({
      base: '/your-repo-name/', // Replace with your repository name
      plugins: [react()],
    })
    ```
2.  Build the project: `npm run build`.
3.  Push the contents of the `dist` folder to a `gh-pages` branch (or use a GitHub Action).

## Running Locally

To use the app on your own machine without deploying:

1.  Start the development server:
    ```bash
    npm run dev
    ```
2.  Open your browser to the URL shown (usually `http://localhost:5173`).
