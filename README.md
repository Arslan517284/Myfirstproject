# Unsplash Image Gallery Website

A modern, responsive web application that displays beautiful images from Unsplash.com.

## Features

- 🔍 **Search Functionality** - Search for any topic (nature, cities, animals, etc.)
- 🎲 **Random Images** - Load random images with one click
- 📱 **Responsive Design** - Works on desktop, tablet, and mobile devices
- 🖼️ **Image Gallery** - Beautiful grid layout with smooth animations
- 💾 **Lazy Loading** - Images load as needed for better performance
- 📍 **Photo Details** - View photographer name and location info
- ⚡ **Fast Loading** - Optimized with minimal dependencies

## Setup Instructions

### Option 1: Without Authentication (Limited)

The website works out of the box using Unsplash's public API:
- **Limit**: 50 requests per hour
- **Best for**: Personal projects, testing, low-traffic sites

Simply open `index.html` in your browser and start searching!

### Option 2: With Authentication (Recommended for Production)

For higher rate limits (5,000 requests per hour):

1. **Register an Unsplash App**
   - Go to [https://unsplash.com/oauth/applications](https://unsplash.com/oauth/applications)
   - Sign up or log in with your Unsplash account
   - Click "New Application"
   - Accept the terms and create your app
   - Copy your **Access Key**

2. **Add Your Access Key**
   - Open `index.html` in a text editor
   - Find the line: `const ACCESS_KEY = 'YOUR_UNSPLASH_ACCESS_KEY';`
   - Replace `YOUR_UNSPLASH_ACCESS_KEY` with your actual access key

3. **Enable Authentication in the Code**
   - In the `fetchImages()` function, modify the fetch URL to include your key:
   ```javascript
   const url = query.startsWith('random')
       ? `${API_BASE}/photos/random?count=12&orientation=squarish&client_id=${ACCESS_KEY}`
       : `${API_BASE}/search/photos?query=${encodeURIComponent(query)}&page=${page}&per_page=12&orientation=squarish&client_id=${ACCESS_KEY}`;
   ```

## How to Use

1. **Open the Website**
   - Double-click `index.html` or open it in your browser

2. **Search for Images**
   - Type a search term (e.g., "mountains", "coffee", "sunset")
   - Click "Search" or press Enter

3. **View Random Images**
   - Click the "Random" button to load random images

4. **Load More**
   - Scroll to the bottom and click "Load More" to get additional images

5. **View Photo Details**
   - Hover over any image to see the photographer's name and location
   - Click an image to open it on Unsplash in a new tab

## File Structure

```
Archives/
├── index.html          # Main website (all-in-one file)
├── README.md          # This file
└── advanced.html      # (Optional) Advanced version with more features
```

## Advanced Features (Optional)

For an enhanced version with additional features, use `advanced.html`:
- Collections support
- Custom grid layout options
- Download image functionality
- Favorite images (stored locally)
- Dark mode toggle

## API Information

- **API Base URL**: https://api.unsplash.com
- **Documentation**: [Unsplash API Docs](https://unsplash.com/documentation)
- **Rate Limits**:
  - Public API: 50 requests/hour
  - Authenticated: 5,000 requests/hour

## Browser Compatibility

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Troubleshooting

### "Rate limit reached" error
- Wait 1 hour before making more requests, or
- Register for an Access Key and add authentication

### Images not loading
- Check your internet connection
- Try a different search term
- Clear browser cache and reload

### Search not working
- Make sure you've entered a search term
- Check browser console (F12) for error messages

## Resources

- [Unsplash API Documentation](https://unsplash.com/documentation)
- [Unsplash Developer Portal](https://unsplash.com/oauth/applications)
- [Unsplash Collections](https://unsplash.com/collections)

## License

This project uses the Unsplash API. All images are provided by Unsplash under the Unsplash License.
See [Unsplash License](https://unsplash.com/license) for details.

## Credits

- Images powered by [Unsplash](https://unsplash.com)
- Built with HTML, CSS, and JavaScript
