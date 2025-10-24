# VSH - VIT Site Hub

A beautiful, glassmorphic web directory for organizing and sharing your favorite websites and resources. Features user voting, category filtering, and an admin panel for resource management.

## 🌟 Features

### User Features
- **Beautiful Glassmorphic Design** - Modern UI with backdrop blur effects
- **Dark/Light Mode** - Toggle between themes with persistent preferences
- **Advanced Search** - Search by name, category, or subcategory with smart scoring
- **Category Filtering** - Filter resources across 8 main categories
- **Subcategory Filters** - Additional filtering for entertainment content
- **Upvote System** - Vote for your favorite resources (one vote per user)
- **Suggest Resources** - Submit suggestions via integrated Web3Forms
- **Responsive Design** - Works seamlessly on mobile, tablet, and desktop
- **Smooth Animations** - Intersection observer for scroll animations
- **Back to Top Button** - Quick navigation for long pages

### Admin Features
- **Secure Admin Panel** - Firebase Authentication with UID-based access control
- **Add Resources** - Create new entries with multiple categories
- **Edit Resources** - Modify existing entries and vote counts
- **Delete Resources** - Remove outdated or inappropriate content
- **Search Management** - Find resources quickly in the admin panel
- **Real-time Updates** - Changes reflect immediately across the site

## 📂 Project Structure

```
vsh/
├── index.html          # Main user-facing site
├── admin.html          # Admin management panel
└── README.md          # This file
```

## 🚀 Setup Instructions

### Prerequisites
- Firebase account
- Web3Forms account (for suggestions)
- Web hosting service (GitHub Pages, Netlify, Vercel, etc.)

### 1. Firebase Setup

1. Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)

2. Enable **Firestore Database**:
   - Go to Firestore Database
   - Create database in production mode
   - Set up security rules:

```javascript
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /resources/{resourceId} {
      // Anyone can read resources
      allow read: if true;
      
      // Only authenticated users can vote (update)
      allow update: if request.auth != null 
        && request.resource.data.votes == resource.data.votes + 1
        && request.auth.uid in request.resource.data.votedBy
        && !(request.auth.uid in resource.data.votedBy);
      
      // Only admin can create/delete
      allow create, delete: if request.auth != null 
        && request.auth.uid == "YOUR_ADMIN_UID_HERE";
    }
  }
}
```

3. Enable **Authentication**:
   - Go to Authentication > Sign-in method
   - Enable **Email/Password**
   - Enable **Anonymous** authentication
   - Create an admin user account

4. Get your **Firebase config**:
   - Go to Project Settings > General
   - Scroll to "Your apps" > Web apps
   - Copy the config object

5. Update both `index.html` and `admin.html`:
   - Replace the `firebaseConfig` object with your credentials
   - Update `ADMIN_UID` in `admin.html` with your admin user's UID (found in Authentication tab)

### 2. Web3Forms Setup

1. Sign up at [Web3Forms](https://web3forms.com/)
2. Create a new form and get your access key
3. In `index.html`, replace the access key:
```html
<input type="hidden" name="access_key" value="YOUR_ACCESS_KEY_HERE">
```

### 3. Deployment

#### Option A: GitHub Pages
```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin YOUR_REPO_URL
git push -u origin main
```
Then enable GitHub Pages in repository settings.

#### Option B: Netlify/Vercel
- Connect your repository
- Deploy with default settings
- No build process needed

## 🎨 Customization

### Categories
Modify categories in both files:
- `index.html`: Lines with category checkboxes and filter options
- `admin.html`: Lines with category checkboxes

Current categories:
- Entertainment
- Academics
- Notes & PYQs
- Productivity
- Coding & Dev
- Design
- Utilities
- Student Projects

### Styling
- **Colors**: Modify Tailwind config in `<script>` section
- **Background**: Change `background-image` URL in `<style>` section
- **Glass Effect**: Adjust `.glass-card` properties

### Adding Subcategories
Update the subcategory filter buttons in `index.html`:
```html
<button class="sub-filter-btn" data-value="your-subcat">Your Subcategory</button>
```

## 📊 Database Schema

### Resources Collection
```javascript
{
  name: string,              // Resource name
  url: string,               // Resource URL
  categories: array,         // Main categories
  subcategories: array,      // Optional subcategories
  votes: number,             // Vote count
  votedBy: array            // Array of user UIDs who voted
}
```

## 🔒 Security Features

- Anonymous authentication for voting (prevents multiple votes per user)
- Admin UID verification for protected operations
- Firestore security rules enforce server-side validation
- XSS protection through safe DOM manipulation
- Input sanitization on forms

## 🐛 Troubleshooting

### Resources not loading
- Check Firebase configuration
- Verify Firestore security rules
- Check browser console for errors

### Admin panel not accessible
- Verify `ADMIN_UID` matches your Firebase user
- Check Authentication is enabled
- Ensure user exists in Firebase Authentication

### Votes not working
- Anonymous authentication must be enabled
- Check Firestore security rules
- Verify user is authenticated (check console)

### Suggestions not submitting
- Verify Web3Forms access key
- Check network tab for API errors
- Ensure form fields have correct `name` attributes

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!

## 👨‍💻 Author

Created with ❤️ for organizing and sharing useful resources.

## 🙏 Acknowledgments

- [Tailwind CSS](https://tailwindcss.com/) for styling
- [Firebase](https://firebase.google.com/) for backend
- [Font Awesome](https://fontawesome.com/) for icons
- [Unsplash](https://unsplash.com/) for background images
- [Web3Forms](https://web3forms.com/) for form submissions
