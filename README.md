# CodeShare

A beautiful code snippet sharing platform built with Next.js 14, featuring customizable themes, syntax highlighting, and seamless GitHub authentication.

## Features

- **Beautiful Code Editor**: Powered by CodeMirror with syntax highlighting for 15+ languages
- **Customizable Themes**: Choose from 7 pre-built gradient themes or create your own custom color combinations
- **Rich Customization Options**:
  - Multiple font families (Fira Code, JetBrains Mono, Inconsolata, Source Code Pro)
  - Adjustable font sizes and padding
  - Toggle line numbers
  - Custom gradient angles and grain effects
- **User Authentication**: Secure GitHub OAuth integration via NextAuth.js
- **Snippet Management**: Create, save, rename, and delete your code snippets
- **View Tracking**: Monitor how many times your snippets have been viewed
- **Export Options**: Download your code snippets as images
- **Responsive Design**: Beautiful UI built with Tailwind CSS and Radix UI components

## Tech Stack

- **Framework**: Next.js 14 (App Router)
- **Language**: TypeScript
- **Database**: PostgreSQL with Prisma ORM
- **Authentication**: NextAuth.js with GitHub provider
- **Editor**: CodeMirror 6
- **Styling**: Tailwind CSS
- **UI Components**: Radix UI, Headless UI
- **State Management**: Zustand
- **Animations**: Framer Motion
- **Data Fetching**: SWR

## Supported Languages

- TypeScript/JavaScript
- Python
- Java
- C++
- Rust
- PHP
- SQL
- HTML/CSS
- XML
- JSON
- Markdown
- And more...

## Getting Started

### Prerequisites

- Node.js 18+ 
- PostgreSQL database
- GitHub OAuth App credentials

### Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/codeshare.git
cd codeshare
```

2. Install dependencies:
```bash
npm install
```

3. Set up environment variables:

Create a `.env` file in the root directory:

```env
# Database
DATABASE_URL="postgresql://user:password@localhost:5432/codeshare?schema=public"

# GitHub OAuth
GITHUB_ID=your_github_client_id
GITHUB_SECRET=your_github_client_secret

# For local development
GITHUB_LOCAL_ID=your_github_client_id
GITHUB_LOCAL_SECRET=your_github_client_secret

# NextAuth
NEXTAUTH_URL=http://localhost:3000
NEXTAUTH_SECRET=your_nextauth_secret
```

4. Set up the database:
```bash
npx prisma migrate dev
npx prisma generate
```

5. Run the development server:
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## GitHub OAuth Setup

1. Go to GitHub Settings → Developer settings → OAuth Apps
2. Create a new OAuth App
3. Set the Authorization callback URL to: `http://localhost:3000/api/auth/callback/github`
4. Copy the Client ID and Client Secret to your `.env` file

## Database Schema

The application uses Prisma with PostgreSQL and includes:

- **Users**: User accounts with GitHub authentication
- **Snippets**: Code snippets with customization settings
- **Views**: View count tracking for snippets
- **Sessions & Accounts**: NextAuth.js authentication tables

## Project Structure

```
├── app/                    # Next.js app router pages
│   ├── api/               # API routes
│   ├── dashboard/         # User dashboard
│   └── [id]/             # Individual snippet pages
├── components/            # React components
│   ├── Dashboard/        # Dashboard components
│   ├── Editor/           # Code editor components
│   ├── Header/           # Header components
│   ├── Settings/         # Settings panel components
│   └── ui/               # Reusable UI components
├── contexts/             # React contexts
├── lib/                  # Utility functions and configurations
├── prisma/               # Database schema and migrations
└── types/                # TypeScript type definitions
```

## Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm start` - Start production server
- `npm run lint` - Run ESLint

## Deployment

This project is configured for deployment on Netlify with the Next.js plugin. You can also deploy to:

- Vercel
- Railway
- Any platform supporting Next.js 14

Make sure to set up environment variables in your deployment platform.

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is open source and available under the MIT License.

## Acknowledgments

- Built with [Next.js](https://nextjs.org/)
- Code editor powered by [CodeMirror](https://codemirror.net/)
- UI components from [Radix UI](https://www.radix-ui.com/)
- Authentication via [NextAuth.js](https://next-auth.js.org/)
