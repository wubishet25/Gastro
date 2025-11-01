# Restaurant Order System - React Native Setup Guide

## Prerequisites

Before you start, you need to install:

1. **Node.js** (v16 or higher)
   - Download from: https://nodejs.org/
   - This includes npm (Node Package Manager)

2. **Expo CLI** (Easiest way to build React Native apps)
   ```bash
   npm install -g expo-cli
   ```

3. **Expo Go App** on your phone
   - iOS: Download from App Store
   - Android: Download from Google Play Store

## Step 1: Create Your Project

Open your terminal/command prompt and run:

```bash
# Create a new Expo project
npx create-expo-app RestaurantOrderSystem

# Navigate into the project
cd RestaurantOrderSystem
```

## Step 2: Install Required Dependencies

```bash
# Install AsyncStorage for data persistence
npx expo install @react-native-async-storage/async-storage
```

## Step 3: Replace the App.js File

1. Open the project folder in a text editor (VS Code recommended)
2. Find the `App.js` file in the root directory
3. Delete everything in `App.js`
4. Copy and paste the complete React Native code I provided above
5. Save the file

## Step 4: Run Your App

### Option A: Run on Your Phone (Recommended)

```bash
# Start the development server
npx expo start
```

This will show a QR code in your terminal. Then:
- **iPhone**: Open Camera app, scan the QR code
- **Android**: Open Expo Go app, scan the QR code

Your app will load on your phone!

### Option B: Run on Emulator

**For Android:**
1. Install Android Studio
2. Set up Android emulator
3. Run: `npx expo start --android`

**For iOS (Mac only):**
1. Install Xcode
2. Run: `npx expo start --ios`

## Step 5: Test the App

1. **Test Waiter Station**: Add items, submit orders
2. **Test Kitchen Station**: Switch to kitchen view, see orders appear
3. **Test Bar Station**: Switch to bar view, track drink orders

## Making Changes

- Edit `App.js` to customize menu items, prices, or add features
- Changes will automatically reload on your phone
- Press `r` in terminal to manually reload

## Building for Production (Optional)

### Build APK for Android:
```bash
# Build APK
eas build --platform android --profile preview
```

### Build for iOS:
```bash
# Build for iOS (requires Apple Developer account)
eas build --platform ios
```

You'll need to create an Expo account (free) for building.

## Customization Guide

### Change Menu Items

In `App.js`, find the `menuItems` object (around line 22):

```javascript
const menuItems = {
  bar: [
    { id: 'b1', name: 'Your Drink', price: 5.0, category: 'bar' },
    // Add more items here
  ],
  kitchen: [
    { id: 'k1', name: 'Your Dish', price: 12.0, category: 'kitchen' },
    // Add more items here
  ],
};
```

### Change Colors

Find the `styles` object and modify colors:
- Primary color: `#2196F3` (blue buttons)
- Success color: `#4CAF50` (complete button)
- Warning color: `#FFC107` (start button)

## Troubleshooting

### "Command not found: expo"
- Run: `npm install -g expo-cli`

### QR Code not working
- Make sure phone and computer are on same WiFi network
- Try running: `npx expo start --tunnel`

### App crashes on startup
- Check that you installed AsyncStorage: `npx expo install @react-native-async-storage/async-storage`

### Orders not syncing between devices
- AsyncStorage stores data locally on each device
- For real multi-device syncing, you'll need a backend server (Firebase, Supabase, etc.)

## Next Steps for Production

For a real restaurant deployment:

1. **Add Backend Server**: Use Firebase or Supabase for real-time syncing
2. **Add Authentication**: Different logins for waiters, kitchen, bar staff
3. **Add Printer Integration**: Use thermal printer packages
4. **Add Table Management**: Track occupied/available tables
5. **Add Payment Processing**: Integrate Stripe or Square

## Support Resources

- Expo Documentation: https://docs.expo.dev/
- React Native Documentation: https://reactnative.dev/
- Stack Overflow: Search for "React Native" questions

## Cost Breakdown

- **Development**: FREE (using Expo)
- **Testing on your phone**: FREE (using Expo Go)
- **Publishing to Google Play Store**: $25 one-time fee
- **Publishing to Apple App Store**: $99/year

---

Need help? Common issues:
- Make sure Node.js is installed: `node --version`
- Make sure Expo CLI is installed: `expo --version`
- Restart terminal after installations
