# First Mobile Application Setup with Expo Router

## Project Information
- **Repository**: `prodev-mobile-setup`
- **Directory**: `prodev-mobile-app-0x00`
- **Framework**: Expo with React Native
- **Template**: Expo Router (latest)

## Objective
Set up the first mobile application using the Expo Router template, understand the scaffolding process, and explore the file structure of a React Native application.

---

## Setup Process

### Step 1: Navigate to Project Directory
```bash
cd prodev-mobile-setup
```

**Purpose**: Ensure we're in the correct parent directory before initializing the Expo project.

### Step 2: Initialize Expo Project
```bash
npx create-expo-app@latest .
```

**What this command does**:
- `npx` - Executes the npm package without global installation
- `create-expo-app@latest` - Uses the latest version of Expo's project creation tool
- `.` - Creates the project in the current directory

**Expected Output**:
- Project scaffolding with Expo Router template
- Installation of necessary dependencies
- Creation of default file structure

### Step 3: Modify the Home Screen

**File Modified**: `app/(tabs)/index.tsx`

**Change Made**:
```tsx
// Before
<Text>Welcome!</Text>

// After
<Text>First App Created</Text>
```

**Location in File**:
- Navigate to `app/(tabs)/index.tsx`
- Locate the `<Text>` component containing "Welcome!"
- Replace the text content with "First App Created"

### Step 4: Run the Development Server

```bash
npx expo start
```

**What happens**:
1. Expo development server starts
2. QR code appears in the terminal
3. Metro bundler begins running
4. Options appear for different platforms (Android, iOS, Web)

**Testing on Device**:

#### For iOS Devices:
1. Open the native **Camera app**
2. Point camera at the QR code in terminal
3. Tap the notification that appears
4. App loads in Expo Go

#### For Android Devices:
1. Open the **Expo Go app**
2. Tap "Scan QR code"
3. Point camera at the QR code in terminal
4. App loads automatically

**Result**: The home screen displays "First App Created" instead of "Welcome!"

---

## Reset Project Command

### Command Executed:
```bash
npm run reset-project
```

### Observations and Effects:

#### What Happened:
1. **Script Execution**: The reset script ran from `package.json`
2. **App Directory Reset**: The `/app` directory was cleaned or restored to a minimal state
3. **Template Files Moved**: Example/template files were moved to `/app-example` directory
4. **Fresh Start Created**: Project was prepared for building from scratch

#### Files/Directories Affected:
- `/app` - Reset to minimal boilerplate
- `/app-example` - Created with original template files as reference
- Configuration files - Preserved
- `node_modules` - Unchanged
- `package.json` - Unchanged

#### Purpose of Reset:
The `reset-project` command is designed to:
- Remove the demo/example code from the `/app` directory
- Provide a clean slate for building your own application
- Preserve example files in `/app-example` for reference
- Maintain all dependencies and configuration

#### After Reset:
- The app structure is simplified
- Original example code is safely stored in `/app-example`
- Developers can reference examples while building from scratch
- No need to manually delete demo files

---

## Project File Structure

### Root Directory Structure:
```
prodev-mobile-app-0x00/
├── app/                    # Main application code (file-based routing)
│   ├── (tabs)/            # Tab-based navigation group
│   │   ├── index.tsx      # Home screen (modified)
│   │   └── explore.tsx    # Explore screen
│   ├── _layout.tsx        # Root layout
│   └── +not-found.tsx     # 404 screen
├── app-example/           # Example files (after reset)
│   ├── app/
│   │   └── (tabs)/
│   │       └── index.tsx  # Original example home screen
│   └── constants/
│       └── Colors.tsx     # Example color constants
├── assets/                # Images, fonts, and other static files
├── components/            # Reusable React components
├── constants/             # App-wide constants
├── hooks/                 # Custom React hooks
├── scripts/              # Utility scripts
├── node_modules/         # Dependencies
├── .gitignore           # Git ignore rules
├── app.json             # Expo configuration
├── package.json         # Project dependencies and scripts
├── tsconfig.json        # TypeScript configuration
└── README.md           # This file
```

### Key Directories Explained:

#### `/app` Directory (File-Based Routing):
- Expo Router uses file-based routing similar to Next.js
- Each file represents a route/screen
- `(tabs)` creates a tab navigation group
- `_layout.tsx` defines layout structure
- `index.tsx` is the default/home route

#### `/components` Directory:
- Houses reusable React components
- Components can be shared across screens
- Promotes code reusability

#### `/constants` Directory:
- Stores app-wide constants (colors, sizes, API endpoints)
- Centralizes configuration values

#### `/assets` Directory:
- Contains images, fonts, and static resources
- Organized by resource type

---

## Modified Files

### 1. `app/(tabs)/index.tsx`

**Original Content** (key section):
```tsx
<Text>Welcome!</Text>
```

**Modified Content**:
```tsx
<Text>First App Created</Text>
```

**Full Context**: This file represents the home/index screen of the tab navigation. It's the first screen users see when opening the app.

---

## Example Files Reference

### `app-example/app/(tabs)/index.tsx`
Contains the original template home screen with:
- Default welcome message
- Example styling
- Sample components
- Helpful comments for beginners

### `app-example/constants/Colors.tsx`
Demonstrates how to:
- Define color schemes
- Handle light/dark mode themes
- Export reusable color constants
- Organize styling values

---

## Development Workflow

### Starting Development:
```bash
npx expo start
```

### Common Development Commands:
```bash
# Start with cleared cache
npx expo start -c

# Start on specific platform
npx expo start --android
npx expo start --ios
npx expo start --web

# Install dependencies
npm install

# Reset project to clean state
npm run reset-project
```

### Hot Reload:
- Save any file in your editor
- Changes automatically reflect on your device
- No need to restart the development server

---

## Key Learnings

### 1. Expo Router Benefits:
- File-based routing (intuitive navigation)
- TypeScript support out of the box
- Built-in tab navigation
- Easy to understand folder structure

### 2. Development Experience:
- Instant feedback with hot reload
- QR code scanning for easy device connection
- No need for complex emulator setup
- Real device testing from the start

### 3. Project Organization:
- Clear separation of concerns (screens, components, constants)
- Example files preserved for reference
- Scalable structure for growing applications

---

## Troubleshooting

### QR Code Won't Scan:
- Ensure device and laptop are on the same WiFi network
- Try the tunnel option: `npx expo start --tunnel`
- Manually type the connection URL shown in terminal

### App Won't Load:
- Check if Expo Go is updated to latest version
- Clear Expo Go cache
- Restart development server with: `npx expo start -c`

### Changes Not Reflecting:
- Save the file properly in VS Code
- Check terminal for errors
- Try shaking device and selecting "Reload"

---

## Next Steps

1. ✅ Project scaffolded successfully
2. ✅ Home screen modified
3. ✅ App tested on physical device
4. ✅ Reset command executed and documented
5. ⬜ Build additional screens
6. ⬜ Add custom components
7. ⬜ Implement navigation between screens
8. ⬜ Style the application

---

## Resources

- **Expo Documentation**: https://docs.expo.dev/
- **Expo Router Docs**: https://docs.expo.dev/router/introduction/
- **React Native Docs**: https://reactnative.dev/
- **TypeScript Guide**: https://www.typescriptlang.org/docs/

---

**Setup Date**: January 9, 2026  
**Status**: ✅ Complete  
**Device Tested**: Android (Expo Go)