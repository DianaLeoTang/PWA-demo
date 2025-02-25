# React PWA App

This project is a Progressive Web Application (PWA) built with React and TypeScript. It offers offline capabilities, installability, and an app-like experience while being accessible through a web browser.

## Features

- 📱 **Installable**: Add to home screen on mobile or desktop devices
- 🔌 **Offline Support**: Works without an internet connection
- 🚀 **Fast Loading**: Optimized for performance with caching strategies
- 📲 **Push Notifications**: Engage users with notifications (when enabled)
- 🔄 **Background Sync**: Sync data in the background when connection is restored
- 🔒 **HTTPS**: Secure by default

## Getting Started

### Prerequisites

- Node.js 14.0 or later
- npm 7.0 or later

### Installation

1. Clone this repository:
```bash
git clone https://github.com/yourusername/my-pwa-app.git
cd my-pwa-app
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm start
```

The application will open in your browser at [http://localhost:3000](http://localhost:3000).

### Compatibility Note

This project uses React 18 to ensure compatibility with all dependencies. If you encounter dependency conflicts related to React 19, you can downgrade React:

```bash
npm uninstall react react-dom
npm install react@18 react-dom@18
```

## Building for Production

Build the app for production:

```bash
npm run build
```

The build is minified and optimized for best performance. Your PWA is ready to be deployed!

## PWA Configuration

### Web App Manifest

The Web App Manifest (`public/manifest.json`) defines how your app appears when installed:

```json
{
  "short_name": "React App",
  "name": "Create React App Sample",
  "icons": [
    {
      "src": "favicon.ico",
      "sizes": "64x64 32x32 24x24 16x16",
      "type": "image/x-icon"
    },
    {
      "src": "logo192.png",
      "type": "image/png",
      "sizes": "192x192"
    },
    {
      "src": "logo512.png",
      "type": "image/png",
      "sizes": "512x512"
    }
  ],
  "start_url": ".",
  "display": "standalone",
  "theme_color": "#000000",
  "background_color": "#ffffff"
}
```

Customize this file to match your app's branding.

### Service Worker

The Service Worker provides offline capabilities and caching strategies. It's registered in `src/index.tsx`:

```typescript
import * as serviceWorkerRegistration from './serviceWorkerRegistration';

// If you want your app to work offline and load faster, you can change
// unregister() to register() below. Note this comes with some pitfalls.
// Learn more about service workers: https://cra.link/PWA
serviceWorkerRegistration.register();
```

## Testing

Run tests with:

```bash
npm test
```

This project uses Jest and React Testing Library for testing.

## Customizing Your PWA

### Updating App Icons

Replace the icons in the `public` folder with your own:

- `favicon.ico` - 64x64, 32x32, 24x24, 16x16
- `logo192.png` - 192x192
- `logo512.png` - 512x512

Update the `manifest.json` if you use different filenames or additional sizes.

### Changing Colors

Update the theme color and background color in:
- `public/manifest.json`
- `public/index.html` (meta theme-color tag)

### Offline Experience

Customize the offline experience by modifying the Service Worker configuration in `src/serviceWorkerRegistration.ts`.

## Deployment

For the PWA to function properly, it must be served over HTTPS (except on localhost).

Good hosting options include:
- [Vercel](https://vercel.com)
- [Netlify](https://netlify.com)
- [GitHub Pages](https://pages.github.com)
- [Firebase Hosting](https://firebase.google.com/docs/hosting)

## Best Practices

1. **Assets**: Keep critical assets cached for offline use
2. **User Experience**: Provide clear feedback when the user is offline
3. **Updates**: Notify users when a new version is available
4. **Testing**: Test your PWA on various devices and network conditions

## Learn More

- [Create React App PWA documentation](https://create-react-app.dev/docs/making-a-progressive-web-app/)
- [Workbox documentation](https://developers.google.com/web/tools/workbox)
- [Web App Manifest specification](https://developer.mozilla.org/en-US/docs/Web/Manifest)
- [Service Worker API](https://developer.mozilla.org/en-US/docs/Web/API/Service_Worker_API)

## License

This project is licensed under the MIT License - see the LICENSE file for details.