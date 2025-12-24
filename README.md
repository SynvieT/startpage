# Startpage

A lightweight, responsive, and highly customizable browser startpage built with **Material Design 3 (Expressive)** guidelines. It features dynamic theming, grid/list toggles, and data separation for easy maintenance.

## Features

* **Material Design 3:** Follows modern MD3 Expressive guidelines with dynamic color tokens.
* **10 Color Themes:** Built-in support for 10 distinct color palettes (Lavender, Cobalt, Emerald, Coffee, etc.) with automatic **Dark Mode** support.
* **Fully Responsive:** Adaptive layout that looks great on Desktops, Tablets, and Mobile devices (installable as a PWA/Home Screen app).
* **View Modes:** Toggle between **Grid View** (Icon focus) and **List View** (Text focus) instantly.
* **Search & Filtering:** Filter bookmarks by category using chips or type to search instantly.
* **Dynamic Data Loading:** Load different profiles (e.g., Gaming, Work) via URL parameters without changing code.

---

## Project Structure

Your project relies on a strict folder structure to function correctly:

```text
/ (root)
├── index.html          # The core logic and layout
├── wallpaper.png       # Background image
├── README.md           # Documentation
└── data/               # Configuration Folder
    ├── default.js      # YOUR DATA: Bookmarks, settings, & theme config
    └── default.css     # SYSTEM: Color definitions and theme styles

```

---

## How to Install / Host

### Option 1: GitHub Pages (Recommended)

This is the easiest way to host it for free and access it on your phone.

1. Create a **Public** repository on GitHub.
2. Upload your files (`index.html`, `wallpaper.png`, and the `data` folder).
3. Go to **Settings** > **Pages**.
4. Under **Build and deployment**, select **Source: Deploy from a branch** (choose `main` or `master`).
5. Visit `https://yourusername.github.io/your-repo-name/`.

### Option 2: Local Use

simply download the files and double-click `index.html`. It runs directly in the browser without a server.

---

## Configuration

All user settings are located in **`data/default.js`**. You do not need to touch HTML or CSS.

### 1. Basic Settings

Open `data/default.js` to change the title, wallpaper, or default startup mode:

```javascript
const pageTitle = "My Startpage";
const wallpaperUrl = "wallpaper.png"; 
const defaultTheme = "lavender"; // Options: lavender, cobalt, mint, coffee, etc.
const defaultView = "grid";      // Options: "grid" or "list"

```

### 2. Adding Bookmarks

Scroll down to the `bookmarksData` array in `data/default.js`:

```javascript
const bookmarksData = [
    {
        title: "YouTube",
        url: "https://youtube.com",
        category: "Entertainment",
        // icon: "https://.../icon.png" // Optional: custom icon URL
    },
    {
        title: "GitHub",
        url: "https://github.com",
        category: "Development",
        subtitle: "Code Repositories"   // Optional: displayed in List View
    }
];

```

*Note: If no icon is provided, the app automatically fetches the favicon using DuckDuckGo's API.*

---

## 🔗 Advanced: Multiple Profiles

You can load different configurations without changing the code by using the `?source=` URL parameter.

### Local Profiles

Create a new file `data/work.js`. You can now access it via:
`https://your-site.github.io/?source=work`

### External Profiles (Remote)

You can load a configuration file from any HTTPS URL (e.g., a GitHub Gist raw file):
`https://your-site.github.io/?source=https://example.com/my-config.js`

** Security Note:**
Browser security (CORS) prevents online websites (`https://`) from reading local files (`file:///`).

* If you open `index.html` locally (double-click), you **can** load local files.
* If you host on GitHub Pages, you **cannot** load `file:///C:/Users/...` data.

---

## Themes

The system comes with 10 pre-built themes defined in `data/default.css`.
To change the active theme, click the **Palette Icon** inside the search bar menu.

| Theme | Color Tone |
| --- | --- |
| **Lavender** | Purple (Default) |
| **Glacier** | Sky Blue / Cyan |
| **Mint** | Light Green |
| **Emerald** | Deep Green |
| **Cobalt** | Deep Blue |
| **Sakura** | Pink |
| **Crimson** | Red |
| **Sunset** | Orange |
| **Coffee** | Brown/Beige |
| **Midnight** | Slate Grey |

---

## 📄 License

This project is free to use and modify. No attribution required, but appreciated!
