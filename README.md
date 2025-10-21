# The Ultimate Site Hub

A beautifully designed, glassmorphic web directory that helps users discover and access useful websites across various categories. Built with modern web technologies and featuring a stunning UI with dark mode support.

## ✨ Features

- **Glassmorphic Design**: Modern, translucent card-based layout with backdrop blur effects
- **Dark Mode**: Toggle between light and dark themes with persistent preference storage
- **Real-time Search**: Instantly filter resources by name as you type
- **Category Filtering**: Browse sites by category (Learning, Productivity, Transport, Shopping, Food, Entertainment, Research, Writing, Design)
- **Responsive Layout**: Fully responsive grid that adapts from mobile to desktop
- **Smooth Animations**: Intersection Observer API powers scroll-triggered card animations
- **Resource Suggestions**: Users can suggest new sites via an integrated form (powered by Web3Forms)
- **Skeleton Loading**: Professional loading states before content appears
- **Back to Top**: Convenient button for quick navigation to the top of the page

## 🚀 Technologies Used

- **HTML5**: Semantic markup
- **Tailwind CSS**: Utility-first CSS framework via CDN
- **Vanilla JavaScript**: No framework dependencies
- **Font Awesome**: Icon library for visual enhancement
- **Google Fonts**: Poppins font family
- **Web3Forms API**: For handling suggestion submissions

## 📦 Included Resources

The site comes pre-loaded with popular services across multiple categories:

- **Transport**: Uber, Ola Cabs, Cabmate
- **Shopping**: Amazon, Flipkart, OLX
- **Food**: Zomato
- **Entertainment**: YouTube
- **Learning**: Khan Academy
- **Productivity**: Notion
- **Writing**: Grammarly
- **Research**: Google Scholar
- **Design**: Canva

## 🛠️ Setup

1. Clone or download the repository
2. Open `index.html` in your web browser
3. No build process or dependencies required!

## 🔧 Customization

### Adding New Resources

Edit the `resources` array in the JavaScript section:

```javascript
resources.push({
    id: 14,
    name: 'Your Site Name',
    url: 'https://yoursite.com',
    desc: 'Brief description of the site.',
    category: 'learning', // Choose from existing categories
    color: categoryColors.learning,
    icon: 'fa-solid fa-icon-name' // Font Awesome icon class
});
```

### Adding New Categories

1. Add the category color to `categoryColors` object
2. Add the category option to the filter `<select>` dropdown
3. Create resources with the new category value

### Customizing the Background

Replace the Unsplash URL in the CSS `body` selector:

```css
background-image: url('YOUR_IMAGE_URL');
```

### Suggestion Form Setup

The form uses Web3Forms. To use your own form:

1. Sign up at [Web3Forms](https://web3forms.com/)
2. Replace the `apikey` value in the hidden input field with your own API key

## 🎨 Color Scheme

The design uses a vibrant color palette:
- Transport: Green (`bg-green-500`)
- Shopping: Blue (`bg-blue-600`)
- Food: Red (`bg-red-500`)
- Entertainment: Purple (`bg-purple-600`)
- Learning: Indigo (`bg-indigo-500`)
- Productivity: Gray (`bg-gray-700`)
- Writing: Emerald (`bg-emerald-500`)
- Research: Amber (`bg-amber-500`)
- Design: Pink (`bg-pink-500`)

## 📱 Browser Support

Works on all modern browsers that support:
- CSS Backdrop Filter
- Intersection Observer API
- ES6 JavaScript
- CSS Grid and Flexbox

## 🔒 Privacy & Storage

- Theme preference is stored in `localStorage`
- No user tracking or analytics
- No cookies used
- Form submissions handled securely via Web3Forms

## 📄 License

This project is open source and available for personal and commercial use.

## 🤝 Contributing

To suggest improvements or report issues:
1. Use the "Suggest" button in the interface
2. Provide the site name, URL, and reason for addition

## 💡 Future Enhancements

Potential features for future versions:
- User accounts and favorites
- Sorting options (alphabetical, popularity)
- More categories
- Integration with external APIs
- Export/import resource lists
- Keyboard shortcuts

---

Made with ❤️ for the web community
