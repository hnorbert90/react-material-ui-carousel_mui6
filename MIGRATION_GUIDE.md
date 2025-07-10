# Migration Guide to React 19 Compatible Version

## Overview

This guide helps you migrate from react-material-ui-carousel v3.4.2 to v3.5.0, which adds React 19 support.

## What's Changed

### React Support
- Added React 19 support alongside existing React 17 and 18 support
- Updated peer dependencies to support React 19
- Updated TypeScript configuration for better React 19 compatibility

### Dependencies Updated
- Updated Material-UI to v6 (supports both MUI v5 and v6 via peer dependencies)
- Updated framer-motion to v11 for better React 19 compatibility
- Updated TypeScript to v5.6.3
- Updated other dev dependencies

### Breaking Changes
**None** - This is a backward-compatible update that maintains full compatibility with React 17, 18, and adds React 19 support.

## Migration Steps

### If Using React 17 or 18
No changes needed - the library continues to work exactly as before.

### If Upgrading to React 19
1. Update your React version:
   ```bash
   npm install react@^19.0.0 react-dom@^19.0.0
   ```

2. Update react-material-ui-carousel:
   ```bash
   npm install react-material-ui-carousel@^3.5.0
   ```

3. If using TypeScript, ensure your tsconfig.json includes:
   ```json
   {
     "compilerOptions": {
       "jsx": "react-jsx",
       "target": "es2018"
     }
   }
   ```

4. If you're using ReactDOM.render, consider updating to createRoot:
   ```javascript
   // Old way (still works)
   import ReactDOM from 'react-dom';
   ReactDOM.render(<App />, document.getElementById('root'));

   // New way (recommended for React 18+)
   import { createRoot } from 'react-dom/client';
   const root = createRoot(document.getElementById('root'));
   root.render(<App />);
   ```

## Supported React Versions

- React 17.x ✅
- React 18.x ✅
- React 19.x ✅

## Supported Material-UI Versions

- MUI v5.x ✅
- MUI v6.x ✅

## If You Encounter Issues

1. Ensure your React version is compatible (17, 18, or 19)
2. Check that Material-UI version is 5.x or 6.x
3. Verify TypeScript configuration if using TypeScript
4. Clear node_modules and reinstall if needed:
   ```bash
   rm -rf node_modules package-lock.json
   npm install
   ```

## Need Help?

If you encounter any issues during migration, please create an issue on our GitHub repository with:
- Your React version
- Your Material-UI version
- The specific error message
- A minimal reproduction example
