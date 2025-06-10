# Code Craft - Execute & Share Code Snippets

[![Next.js](https://img.shields.io/badge/Next.js-15.3.1-black?style=for-the-badge&logo=next.js&logoColor=white)](https://nextjs.org)
[![Convex](https://img.shields.io/badge/Convex-1.23.0-blueviolet?style=for-the-badge&logo=convex&logoColor=white)](https://convex.dev/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

Code Craft is a modern web application designed for developers to effortlessly write, execute, and manage code snippets across various programming languages. It provides a seamless experience with user authentication, a feature-rich code editor, and persistent storage for code executions and favorite snippets, all powered by Next.js and Convex.

## ✨ Features

- **Multi-Language Code Execution**: Run code in popular languages (Python, JavaScript, Java, C++, etc.).
- **Interactive Code Editor**: Powered by Monaco Editor, offering syntax highlighting, autocompletion, and a great editing experience.
- **User Authentication**: Secure sign-up and login functionality using Clerk.
- **Persistent Storage**: Save your code executions and star your favorite snippets for later access, managed by Convex.
- **Profile Page**: View your coding statistics, recent executions, and starred snippets.
- **Pricing/Pro Plan**: Offers a Pro plan with enhanced features (details in `src/app/pricing/page.tsx`).
- **Responsive Design**: Optimized for various screen sizes.
- **Modern Tech Stack**: Built with Next.js, Convex, TypeScript, and Tailwind CSS for a fast, reliable, and maintainable application.

## 🚀 Getting Started

Follow these steps to get Code Craft running locally on your machine.

### Prerequisites

- [Node.js](https://nodejs.org/) (LTS version recommended)
- [npm](https://www.npmjs.com/), [yarn](https://yarnpkg.com/), [pnpm](https://pnpm.io/), or [bun](https://bun.sh/)
- A [Clerk](https://clerk.com/) account for authentication.
- A [Convex](https://convex.dev/) account for the backend and database.

### Installation & Setup

1. **Clone the repository:**

   ```bash
   git clone https://github.com/krishbansal-2205/code-craft.git
   cd code-craft
   ```

2. **Install dependencies:**

   ```bash
   npm install
   # or
   yarn install
   # or
   pnpm install
   # or
   bun install
   ```

3. **Set up Environment Variables:**
   Create a `.env.local` file in the root of your project and add your Clerk and Convex credentials. You'll typically need:

   ```env
   NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=
   CLERK_SECRET_KEY=
   CONVEX_DEPLOYMENT=
   NEXT_PUBLIC_CONVEX_URL=
   ```

   - Obtain your Clerk keys from the [Clerk Dashboard](https://dashboard.clerk.com/).
   - Obtain your Convex URL after deploying your Convex backend (`npx convex deploy`).
   - The `CLERK_WEBHOOK_SECRET` is used for syncing user data with Convex via webhooks (see `convex/http.ts`).

4. **Deploy Convex Backend:**
   Navigate to your project root and deploy your Convex schema and functions:

   ```bash
   npx convex dev # For development with a local backend and dashboard
   # or for a hosted development/production deployment:
   npx convex deploy
   ```

   This will also generate necessary files in the `convex/_generated` directory.

5. **Run the development server:**

   ```bash
   npm run dev
   ```

   Open [http://localhost:3000](http://localhost:3000) in your browser to see the application.

## 🛠️ Tech Stack

- **Frontend Framework**: [Next.js](https://nextjs.org/) 15.3.1 (App Router)
- **Backend-as-a-Service**: [Convex](https://convex.dev/) 1.23.0 (Realtime Database, Serverless Functions)
- **Authentication**: [Clerk](https://clerk.com/)
- **Programming Language**: [TypeScript](https://www.typescriptlang.org/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/) 4
- **Code Editor**: [@monaco-editor/react](https://www.npmjs.com/package/@monaco-editor/react)
- **UI/UX**: [Lucide React](https://lucide.dev/) (Icons), [Framer Motion](https://www.framer.com/motion/) (Animations)
- **Notifications**: [React Hot Toast](https://react-hot-toast.com/)
- **State Management (Client)**: [Zustand](https://zustand-demo.pmnd.rs/) (see `src/store/useCodeEditorStore.ts`)
- **Linting/Formatting**: [ESLint](https://eslint.org/) (with Next.js core web vitals and TypeScript configurations)
