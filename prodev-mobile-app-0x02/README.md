# React Native Components and Styling

## Project Information
- **Repository**: `prodev-mobile-setup`
- **Directory**: `prodev-mobile-app-0x01`
- **Framework**: Expo with React Native
- **Focus**: Understanding React Native Components and Styling System

---

## Objectives

Learn how React Native components work as building blocks for native mobile applications and understand the styling system that makes them look great on both iOS and Android platforms.

### Key Concepts:

#### React Native Components vs Web HTML
React Native uses predefined components that translate to native components:

| Web (HTML) | React Native | Purpose |
|------------|--------------|---------|
| `<div>` | `<View>` | Container element |
| `<p>` | `<Text>` | Text content |
| `<button>` | `<Button>` or `<Pressable>` | Interactive elements |
| `<input>` | `<TextInput>` | User input |
| `<img>` | `<Image>` | Images |

#### Styling in React Native
- Uses JavaScript objects instead of CSS files
- Similar to inline styles in React web applications
- Provides `StyleSheet.create()` for optimized styling
- Maintains native look and feel on both iOS and Android

---

## Setup Instructions

### Step 1: Create New Expo Project

Navigate to your parent directory and create the new project:

```bash
cd prodev-mobile-setup
npx create-expo-app@latest prodev-mobile-app-0x01
```

**What happens:**
- Creates a new directory called `prodev-mobile-app-0x01`
- Installs Expo Router template with all dependencies
- Sets up the project structure

### Step 2: Navigate to Project Directory

```bash
cd prodev-mobile-app-0x01
```

### Step 3: Reset the Application

Remove the default template to start with a clean slate:

```bash
npm run reset-project
```

**Expected Output:**
```
Project reset complete. Next steps:
1. Run `npx expo start` to start a development server.
2. Edit app/index.tsx to edit the main screen.
3. Delete the /app-example directory when you're done referencing it.
```

**What this does:**
- Removes example/demo code
- Creates a minimal `app/index.tsx` file
- Moves original examples to `app-example/` for reference
- Provides a clean starting point

---

## Implementation Steps

### Step 4: Update `app/index.tsx`

Open `app/index.tsx` in VS Code and implement the following:

#### 4.1: Import Required Components

At the top of the file, import the necessary React Native components:

```typescript
import { View, Text, StyleSheet } from 'react-native';
```

**Explanation:**
- `View`: Container component (like `<div>`)
- `Text`: Text display component (like `<p>`)
- `StyleSheet`: API for creating optimized styles

#### 4.2: Create the Component Structure

```typescript
export default function Index() {
  return (
    <View style={styles.container}>
      <Text>Entry Screen - Awesome</Text>
      <View>
        <Text style={styles.largeText}>Typescript is great if you practice more</Text>
        <Text style={styles.mediumText}>React Native provides you a single codebase for cross platforms</Text>
        <Text style={styles.smallText}>ALX is awesome</Text>
      </View>
    </View>
  );
}
```

**Structure Breakdown:**
1. **Outer `<View>`**: Main container with `styles.container`
2. **First `<Text>`**: Entry screen title (no custom styling)
3. **Inner `<View>`**: Container for the three styled text components
4. **Three `<Text>` components**: Each with different styles

#### 4.3: Define Styles with StyleSheet

Add the styles object at the bottom of the file:

```typescript
const styles = StyleSheet.create({
  container: {
    backgroundColor: "#90caf9",
  },
  largeText: {
    fontSize: 30,
    color: "#f44336",
    marginBottom: 5,
    fontWeight: "700",
    fontVariant: ["small-caps"],
  },
  mediumText: {
    fontSize: 20,
    color: "#9c27b0",
    marginBottom: 10,
    fontWeight: "500",
    textAlign: "right",
  },
  smallText: {
    fontSize: 15,
    color: "#2196f3",
    fontWeight: "400",
    textAlign: "center",
  },
});
```

---

## Style Properties Explained

### Container Style
```typescript
container: {
  backgroundColor: "#90caf9",  // Light blue background
}
```
- Sets the background color of the main View
- Uses hex color code for precise color control

### Large Text Style
```typescript
largeText: {
  fontSize: 30,                    // Large text size
  color: "#f44336",                // Red color
  marginBottom: 5,                 // Small spacing below
  fontWeight: "700",               // Bold text
  fontVariant: ["small-caps"],     // Small capital letters
}
```

**Properties:**
- `fontSize`: Controls text size (in pixels on React Native)
- `color`: Text color using hex code
- `marginBottom`: Spacing below the element
- `fontWeight`: Text thickness (400=normal, 700=bold)
- `fontVariant`: Text transformation (small-caps makes lowercase letters appear as smaller capitals)

### Medium Text Style
```typescript
mediumText: {
  fontSize: 20,                    // Medium text size
  color: "#9c27b0",                // Purple color
  marginBottom: 10,                // Moderate spacing below
  fontWeight: "500",               // Medium weight
  textAlign: "right",              // Right-aligned text
}
```

**Properties:**
- `textAlign`: Controls horizontal text alignment (left, right, center, justify)
- Medium font weight (500) for semi-bold appearance

### Small Text Style
```typescript
smallText: {
  fontSize: 15,                    // Smaller text size
  color: "#2196f3",                // Blue color
  fontWeight: "400",               // Normal weight
  textAlign: "center",             // Center-aligned text
}
```

**Properties:**
- Regular font weight (400) for normal text appearance
- Center alignment for visual balance

---

## Running Your Application

### Start the Development Server

```bash
npx expo start
```

### Test on Your Device

#### For Android (Expo Go):
1. Open Expo Go app
2. Tap "Scan QR code"
3. Scan the QR code from your terminal
4. App loads with your styled components

#### For iOS (Camera App):
1. Open Camera app
2. Point at QR code
3. Tap the notification
4. App opens in Expo Go

---

## Expected Visual Result

When you run the app, you should see:

```
┌─────────────────────────────────────┐
│  Light Blue Background (#90caf9)    │
│                                     │
│  Entry Screen - Awesome             │
│                                     │
│  TYPESCRIPT IS GREAT IF YOU         │
│  PRACTICE MORE                      │
│  (Red, 30px, bold, small-caps)      │
│                                     │
│           React Native provides you │
│    a single codebase for cross      │
│                         platforms   │
│  (Purple, 20px, right-aligned)      │
│                                     │
│         ALX is awesome               │
│  (Blue, 15px, centered)             │
│                                     │
└─────────────────────────────────────┘
```

---

## Key Learnings

### 1. React Native Components
- Components are the building blocks of React Native apps
- Each component maps to native UI elements
- `<View>` is the fundamental container component
- `<Text>` is required for any text display

### 2. Styling System
- Styles are JavaScript objects, not CSS files
- `StyleSheet.create()` optimizes styles for better performance
- Style properties use camelCase (e.g., `backgroundColor`, not `background-color`)
- Numeric values don't need units (fontSize: 30, not "30px")

### 3. Style Application
- Apply styles using the `style` prop: `style={styles.styleName}`
- Can apply multiple styles: `style={[styles.style1, styles.style2]}`
- Inline styles possible but not recommended for performance

### 4. Differences from Web CSS
- No CSS selectors (no classes, IDs, or element selectors)
- Limited CSS properties (only those supported by React Native)
- No cascading styles (styles don't inherit except for `<Text>`)
- Flexbox is the default layout system

---

## Common Styling Properties

### Layout Properties
```typescript
{
  flex: 1,                    // Flex grow factor
  flexDirection: 'row',       // row | column | row-reverse | column-reverse
  justifyContent: 'center',   // flex-start | flex-end | center | space-between | space-around
  alignItems: 'center',       // flex-start | flex-end | center | stretch | baseline
  padding: 10,                // All sides
  paddingHorizontal: 15,      // Left and right
  paddingVertical: 10,        // Top and bottom
  margin: 10,                 // All sides
}
```

### Text Properties
```typescript
{
  fontSize: 16,
  fontWeight: '400',          // 100-900 or 'normal' | 'bold'
  fontStyle: 'italic',        // normal | italic
  textAlign: 'center',        // left | right | center | justify
  color: '#000000',
  textDecorationLine: 'underline',  // none | underline | line-through
}
```

### Visual Properties
```typescript
{
  backgroundColor: '#ffffff',
  borderWidth: 1,
  borderColor: '#000000',
  borderRadius: 5,
  opacity: 0.5,               // 0 to 1
  shadowColor: '#000',        // iOS
  shadowOffset: { width: 0, height: 2 },  // iOS
  shadowOpacity: 0.25,        // iOS
  shadowRadius: 3.84,         // iOS
  elevation: 5,               // Android
}
```

---

## Troubleshooting

### Issue: Styles Not Applying
**Solution:** 
- Check that you've imported `StyleSheet`
- Verify the style name matches in `StyleSheet.create()` and the component
- Ensure the `style` prop is correctly applied: `style={styles.name}`

### Issue: Text Not Visible
**Solution:**
- All text must be inside a `<Text>` component
- Check text color doesn't match background color
- Verify `fontSize` is large enough

### Issue: App Won't Load
**Solution:**
```bash
# Clear cache and restart
npx expo start -c
```

---

## File Structure

```
prodev-mobile-app-0x01/
├── app/
│   └── index.tsx          ← Your main file (modified)
├── app-example/           ← Reference files (can delete later)
├── assets/                ← Images and fonts
├── node_modules/          ← Dependencies
├── package.json           ← Project configuration
└── README.md             ← This file
```

---

## Next Steps

1. ✅ Project created and reset
2. ✅ `app/index.tsx` updated with styled components
3. ✅ Tested on physical device
4. ⬜ Experiment with different colors
5. ⬜ Try additional style properties
6. ⬜ Add more components and layouts

---

## Resources

- **React Native Components**: https://reactnative.dev/docs/components-and-apis
- **StyleSheet API**: https://reactnative.dev/docs/stylesheet
- **Flexbox Layout**: https://reactnative.dev/docs/flexbox
- **Color Reference**: https://reactnative.dev/docs/colors
- **Expo Documentation**: https://docs.expo.dev/

---

## Color Palette Used

| Element | Color Code | Color Name | Visual |
|---------|------------|------------|--------|
| Container Background | `#90caf9` | Light Blue | 🟦 |
| Large Text | `#f44336` | Red | 🟥 |
| Medium Text | `#9c27b0` | Purple | 🟪 |
| Small Text | `#2196f3` | Blue | 🔵 |

---

**Project Date**: January 9, 2026  
**Status**: ✅ Complete  
**Framework**: Expo with React Native  
**Device Tested**: Android via Expo Go