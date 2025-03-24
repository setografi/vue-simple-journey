# Simple Journey - Vue 3 Conversion Project

This project is a responsive conversion of the "Simple Journey" static website into a dynamic Vue 3 application. The conversion maintains the original design while enhancing it with modern web technologies and responsive layouts for optimal viewing across all device sizes.

## Features

- **Responsive Design**: Fully optimized for mobile, tablet, and desktop viewports
- **Vue 3 Framework**: Leveraging the latest Vue 3 features and Composition API
- **GSAP Animations**: Smooth scroll-triggered card animations (desktop/tablet only)
- **TailwindCSS**: Utility-first CSS framework for rapid UI development
- **Pixel-perfect Conversion**: Faithful recreation of the original website design

## Tech Stack

- **Vue 3**: Progressive JavaScript framework
- **Vite**: Next-generation frontend tooling
- **TailwindCSS**: Utility-first CSS framework
- **GSAP (GreenSock Animation Platform)**: Professional-grade animation library
- **ScrollTrigger**: GSAP plugin for scroll-based animations

## Getting Started

Follow these instructions to get the project up and running on your local machine.

### Prerequisites

Make sure you have the following installed:

- Node.js (v14.0.0 or higher)
- npm (v6.0.0 or higher) or yarn (v1.22.0 or higher)

### Installation

1. Clone the repository

   ```bash
   git clone https://github.com/yourusername/simple-journey-vue.git
   cd simple-journey-vue
   ```

2. Install dependencies

   ```bash
   npm install
   # or
   yarn install
   ```

3. Start the development server

   ```bash
   npm run dev
   # or
   yarn dev
   ```

4. Open your browser and navigate to `http://localhost:5173` (or the port shown in your terminal)

## Build for Production

To build the project for production:

```bash
npm run build
# or
yarn build
```

The built files will be in the `dist` directory.

## Project Structure

```
simple-journey-vue/
├── public/          # Static assets
├── src/
│   ├── assets/      # Images and other assets
│   ├── components/  # Vue components
│   │   ├── common/  # Reusable components
│   │   ├── layout/  # Layout components
│   │   └── sections/ # Page section components (home)
│   ├── pages/       # Page views
│   ├── App.vue      # Root component
│   └── main.js      # Application entry point
├── index.html       # HTML template
├── package.json     # Project dependencies
├── tailwind.config.js # TailwindCSS configuration
└── vite.config.js   # Vite configuration
```

## Responsive Breakpoints

This project uses the following TailwindCSS breakpoints:

- **sm**: 640px and above
- **md**: 768px and above
- **lg**: 1024px and above
- **xl**: 1280px and above
- **2xl**: 1536px and above

## Animation Notes

The Services section features GSAP ScrollTrigger animations for card elements. These animations are:

- Enabled on tablet and desktop viewports (768px and above)
- Automatically disabled on mobile for better performance and usability
- Configured to properly refresh when the viewport is resized

## Credits

- Original design: Simple Journey Static Website
