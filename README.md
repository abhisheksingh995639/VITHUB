# The Ultimate Site Hub

Welcome to "The Ultimate Site Hub," a one-stop, responsive directory for useful websites. This single-page application is built with a clean, glassmorphism design and provides a curated list of sites for learning, productivity, transport, and more.

## ✨ Features

* **Glassmorphism UI:** Modern "glass card" design that adapts to the blurred background.
* **Dark/Light Mode:** A theme toggle that saves the user's preference in `localStorage`.
* **Dynamic Filtering:** Filter the list of sites by category (e.g., "Learning," "Productivity," "Shopping").
* **Live Search:** Instantly search and filter resources by name.
* **"Suggest a Site" Modal:** A built-in modal form that allows users to suggest new websites.
* **Form Integration:** The suggestion form is connected to **Web3Forms** for backend-less email submission.
* **Skeleton Loader:** Displays an animated skeleton card layout while the resources are (simulated) loading.
* **Scroll Animations:** Cards fade and slide into view as you scroll, powered by the `IntersectionObserver` API.
* **Responsive Design:** Fully responsive layout for all screen sizes, from mobile to desktop.
* **Utility Buttons:** Includes a "Back to Top" button for easy navigation.

## 🛠️ Tech Stack

* **HTML5**
* **Tailwind CSS (CDN)**
* **Vanilla JavaScript (ES6+)**
* **Font Awesome (CDN)** (for icons)
* **Google Fonts (Poppins)**
* **Web3Forms** (for the suggestion form)

## 🚀 Getting Started

This is a static website that runs entirely in the browser. No build process is needed.

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
    ```
2.  **Navigate to the project directory:**
    ```sh
    cd your-repo-name
    ```
3.  **Open the file:**
    Simply open the `index.html` file in your favorite web browser.

## 🔧 Configuration

All the site's data and configuration are located in the `<script>` tag at the bottom of `index.html`.

### How to Add Resources

To add new websites to the directory, edit the `resources` array. Follow the existing object structure:

```javascript
let resources = [
    // ... other resources
    { 
        id: 14, 
        name: 'New Site', 
        url: '[https://www.newsite.com/](https://www.newsite.com/)', 
        desc: 'A description for the new site.', 
        category: 'learning', // Must match a category in filterSelect
        color: categoryColors.learning, // Must match a key in categoryColors
        icon: 'fa-solid fa-star' // A Font Awesome icon class
    },
];
