# React Task Manager

A responsive multi-page React.js application with full CRUD (Create, Read, Update, Delete) functionality for managing tasks. Built with Vite, React Router DOM, Tailwind CSS, and localStorage for data persistence.

## Features

- ✅ **Full Task Manager**
  - Create new tasks
  - Read/view all tasks
  - Update existing tasks
  - Delete tasks

- ✅ **Responsive Design**
  - Mobile-first approach
  - Works seamlessly on all device sizes
  - Touch-friendly buttons and forms

- ✅ **Data Persistence**
  - Uses localStorage to save tasks
  - No backend required
  - Data persists across browser sessions

- ✅ **Clean UI**
  - Professional design
  - Intuitive navigation
  - Status badges and visual feedback

## Tech Stack

- **React.js** - UI library
- **Vite** - Build tool and dev server
- **React Router DOM** - Client-side routing
- **Tailwind CSS** - Utility-first CSS framework
- **localStorage** - Browser storage for data persistence

## Project Structure

```
react-crud-app/
├── public/
│   └── vite.svg
├── src/
│   ├── components/
│   │   ├── Navbar.jsx          # Navigation component
│   │   └── TaskCard.jsx        # Task card display component
│   ├── pages/
│   │   ├── Home.jsx            # Home page
│   │   ├── TaskList.jsx        # Task list page (READ + DELETE)
│   │   ├── AddTask.jsx         # Add task page (CREATE)
│   │   └── EditTask.jsx        # Edit task page (UPDATE)
│   ├── utils/
│   │   └── localStorage.js     # CRUD utility functions
│   ├── App.jsx                 # Main app with routing
│   ├── main.jsx                # Entry point
│   └── index.css               # Global styles with Tailwind
├── index.html
├── package.json
├── vite.config.js
├── tailwind.config.js
├── postcss.config.js
└── README.md
```

## Installation

### Prerequisites

- Node.js (v16 or higher)
- npm or yarn

### Step-by-Step Setup

1. **Navigate to the project directory:**
   ```bash
   cd react-crud-app
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

4. **Open your browser:**
   - The app will be available at `http://localhost:5173` (or the port shown in terminal)
   - The page will automatically reload when you make changes

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run preview` - Preview production build locally
- `npm run lint` - Run ESLint

## Pages

### 1. Home Page (`/`)
- Welcome section with introduction
- CTA button to "Manage Items"
- Feature highlights

### 2. Tasks List Page (`/tasks`)
- Displays all tasks in a responsive grid
- Each task shows title, description, status, and dates
- Delete button for each task
- Empty state when no tasks exist
- "Add New Task" button

### 3. Add Task Page (`/tasks/add`)
- Form to create new tasks
- Fields: Title (required), Description (optional), Status
- Form validation with error messages
- Saves to localStorage and redirects to task list

### 4. Edit Task Page (`/tasks/edit/:id`)
- Pre-filled form with existing task data
- Same validation as Add Task
- Updates task in localStorage
- Handles invalid/missing task IDs (404 state)

## Task Entity Structure

Each task has the following structure:

```javascript
{
  id: string,              // Timestamp-based unique ID
  title: string,           // Required, min 3 characters
  description: string,      // Optional
  status: 'pending' | 'completed',
  createdAt: string,       // ISO date string
  updatedAt: string        // ISO date string
}
```

## Deployment Guide for Netlify

### Option 1: Deploy via Netlify CLI

1. **Install Netlify CLI globally:**
   ```bash
   npm install -g netlify-cli
   ```

2. **Build the project:**
   ```bash
   npm run build
   ```

3. **Deploy to Netlify:**
   ```bash
   netlify deploy --prod --dir=dist
   ```

4. **Follow the prompts:**
   - If first time, login to Netlify
   - Create a new site or link to existing site
   - Confirm deployment

### Option 2: Deploy via Netlify Dashboard (Drag & Drop)

1. **Build the project:**
   ```bash
   npm run build
   ```

2. **Go to Netlify Dashboard:**
   - Visit [app.netlify.com](https://app.netlify.com)
   - Login or sign up

3. **Deploy:**
   - Drag and drop the `dist` folder to the Netlify dashboard
   - Wait for deployment to complete
   - Your site will be live with a random URL

### Option 3: Deploy via Git (Recommended)

1. **Push your code to GitHub/GitLab/Bitbucket:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   git remote add origin <your-repo-url>
   git push -u origin main
   ```

2. **Connect to Netlify:**
   - Go to [app.netlify.com](https://app.netlify.com)
   - Click "Add new site" → "Import an existing project"
   - Connect your Git provider
   - Select your repository

3. **Configure build settings:**
   - **Build command:** `npm run build`
   - **Publish directory:** `dist`
   - Click "Deploy site"

4. **Customize domain (optional):**
   - Go to Site settings → Domain management
   - Add your custom domain

### Important Notes for Netlify Deployment

- **SPA Routing:** Since this is a Single Page Application (SPA) with React Router, you need to handle client-side routing:

  Create a `public/_redirects` file:
  ```
  /*    /index.html   200
  ```

  Or add this to `netlify.toml` in the project root:
  ```toml
  [[redirects]]
    from = "/*"
    to = "/index.html"
    status = 200
  ```

- **Environment Variables:** If you add any environment variables later, configure them in Netlify Dashboard → Site settings → Environment variables

- **Build Settings:** Netlify will auto-detect Vite projects, but you can manually set:
  - Build command: `npm run build`
  - Publish directory: `dist`

## Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Development Notes

- All CRUD operations are handled in `src/utils/localStorage.js`
- Components are functional components using React Hooks
- Form validation is done client-side
- Error handling is implemented for localStorage operations
- Code includes clear comments explaining CRUD logic

## License

This project is open source and available for educational purposes.
