# Tiktok Clone
- Node.js must be installed to run npm/npx commands
- Run ```npx create-next-app@latest tiktok-clone```
  - Would you like to use TypeScript? **Yes**
  - Would you like to use ESLint? **Yes**
  - Would you like to use Tailwind CSS? **Yes**
  - Would you like to use `src/` directory? **No**
  - Would you like to use App Router? (recommended) **Yes**
  - Would you like to customize the default import alias (@/*)? **No**

- Open folder `cd tiktok-clone`
- Preview `npm run dev` in `http://localhost:3000`

#### Install Packages
```
npm i appwrite debounce @types/debounce image-js moment react-advanced-cropper react-icons 
zustand canvas raw-loader
```

- Modify `nextConfig` in `next.config.js` to add a rule to handle the canvas.node binary module:
```
const nextConfig = {
    webpack: (config, {isServer}) => {
        // Add a rule to handle the canvas.node binary module
        config.module.rules.push({test: /\.node$/, use: 'raw-loader'})

        // Exclude canvas from being process by Next.js in the browser
        if(!isServer) config.externals.push('canvas');
        return config;
    }
}
```
