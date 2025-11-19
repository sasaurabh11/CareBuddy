# 🩺 CareBuddy - AI-Powered Healthcare Assistant

<div align="center">

![CareBuddy](https://img.shields.io/badge/CareBuddy-AI%20Healthcare-blue?style=for-the-badge)
![Next.js](https://img.shields.io/badge/Next.js-15.3-black?style=for-the-badge&logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue?style=for-the-badge&logo=typescript)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Neon-blue?style=for-the-badge&logo=postgresql)

**Transform Healthcare Through Intelligent Voice Technology**

A full-stack AI SaaS application that enables users to interact with virtual medical specialists using real-time voice input. The platform provides personalized medical consultations, intelligent symptom analysis, and comprehensive medical reports powered by advanced AI models.

[Features](#-features) • [Architecture](#-architecture) • [Installation](#-installation) • [Usage](#-usage) • [API Reference](#-api-reference)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Features](#-features)
- [Architecture](#-architecture)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Database Setup](#-database-setup)
- [Running the Application](#-running-the-application)
- [API Reference](#-api-reference)
- [Key Components](#-key-components)
- [Development](#-development)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

CareBuddy is an innovative healthcare platform that bridges the gap between patients and healthcare providers through AI-powered voice interactions. The application allows users to:

- **Voice-Based Consultations**: Interact with AI medical specialists using natural voice conversations
- **Intelligent Diagnosis**: Receive AI-powered symptom analysis and medical guidance
- **Specialist Matching**: Get matched with appropriate medical specialists based on symptoms
- **Medical Reports**: Generate comprehensive medical session reports automatically
- **Session History**: Track and review all past consultations

The platform uses cutting-edge AI models (Google Gemini) to understand patient symptoms, provide medical insights, and generate detailed reports that can assist healthcare professionals in making informed decisions.

---

## ✨ Features

### 🎙️ Real-Time Voice Interaction
- **Voice-to-Text Conversion**: Seamless speech recognition using Vapi AI
- **Natural Language Processing**: Understands conversational medical queries
- **Real-Time Responses**: Instant AI-powered medical guidance

### 🧠 AI-Powered Medical Intelligence
- **Symptom Analysis**: Advanced AI models analyze patient symptoms
- **Specialist Recommendations**: Intelligent matching with 11+ medical specialists
- **Medical Report Generation**: Automated generation of comprehensive session reports
- **Contextual Understanding**: Maintains conversation context throughout sessions

### 👨‍⚕️ Multiple Medical Specialists
The platform includes AI agents for:
- General Physician
- Pediatrician
- Dermatologist
- Orthopedic Surgeon
- Psychiatrist
- ENT Specialist
- Oncologist
- Ophthalmologist
- Urologist
- Gastroenterologist
- Endocrinologist

### 🔐 Security & Authentication
- **Clerk Authentication**: Secure user authentication and session management
- **Protected Routes**: Middleware-based route protection
- **User Context**: Secure user data handling

### 📊 Session Management
- **Session History**: Complete history of all consultations
- **Report Viewing**: Detailed view of generated medical reports
- **Session Tracking**: Track notes, selected doctors, and conversations

### 🎨 Modern UI/UX
- **Responsive Design**: Mobile and desktop compatible
- **Dark Theme**: Modern dark mode interface
- **Animations**: Smooth transitions using Framer Motion
- **Accessible**: Built with accessibility in mind

---

## 🏗️ Architecture

### System Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                        Client Layer                          │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │   Landing    │  │  Dashboard   │  │  Medical     │      │
│  │    Page      │  │              │  │  Agent Chat  │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└─────────────────────────────────────────────────────────────┘
                            │
                            ▼
┌─────────────────────────────────────────────────────────────┐
│                    Next.js App Router                        │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────┐      │
│  │  Middleware  │  │  API Routes  │  │  Components  │      │
│  │  (Clerk)     │  │              │  │              │      │
│  └──────────────┘  └──────────────┘  └──────────────┘      │
└─────────────────────────────────────────────────────────────┘
                            │
        ┌───────────────────┼───────────────────┐
        ▼                   ▼                   ▼
┌──────────────┐  ┌──────────────┐  ┌──────────────┐
│   Clerk      │  │  Google      │  │   Neon DB     │
│  Auth API    │  │  Gemini AI   │  │ (PostgreSQL) │
└──────────────┘  └──────────────┘  └──────────────┘
```

### Data Flow

1. **User Authentication**: Clerk handles user sign-in/sign-up
2. **Session Creation**: User creates a new medical session with notes
3. **Doctor Matching**: AI suggests appropriate specialists based on symptoms
4. **Voice Interaction**: Vapi AI handles voice-to-text conversion
5. **AI Processing**: Google Gemini processes conversation and generates responses
6. **Report Generation**: AI generates comprehensive medical report
7. **Data Storage**: All data stored in Neon PostgreSQL database

### Component Architecture

- **App Router**: Next.js 15 App Router with route groups
- **Server Components**: Default server-side rendering
- **Client Components**: Interactive UI with React hooks
- **API Routes**: Serverless API endpoints
- **Middleware**: Route protection and authentication

---

## 🧰 Tech Stack

### Frontend
| Technology | Version | Purpose |
|------------|---------|---------|
| **Next.js** | 15.3.4 | React framework with App Router |
| **React** | 19.0.0 | UI library |
| **TypeScript** | 5.x | Type-safe JavaScript |
| **Tailwind CSS** | 4.x | Utility-first CSS framework |
| **Framer Motion** | 12.23.24 | Animation library |
| **Radix UI** | Latest | Accessible component primitives |
| **Lucide React** | 0.523.0 | Icon library |
| **Sonner** | 2.0.5 | Toast notifications |

### Backend & Services
| Technology | Version | Purpose |
|------------|---------|---------|
| **Next.js API Routes** | 15.3.4 | Serverless API endpoints |
| **Clerk** | 6.35.2 | Authentication & user management |
| **Google Gemini AI** | 2.0 Flash | AI model for medical analysis |
| **OpenAI (OpenRouter)** | 5.8.0 | Alternative AI provider |
| **Vapi AI** | 2.5.1 | Voice interface SDK |
| **Groq SDK** | 0.36.0 | Fast AI inference |

### Database & ORM
| Technology | Version | Purpose |
|------------|---------|---------|
| **Neon PostgreSQL** | Latest | Serverless PostgreSQL database |
| **Drizzle ORM** | 0.44.7 | Type-safe SQL ORM |
| **Drizzle Kit** | 0.31.7 | Database migrations & introspection |

### Development Tools
| Technology | Version | Purpose |
|------------|---------|---------|
| **TypeScript** | 5.x | Type checking |
| **ESLint** | Latest | Code linting |
| **PostCSS** | Latest | CSS processing |

---

## 📁 Project Structure

```
carebuddy/
├── app/                          # Next.js App Router
│   ├── (auth)/                  # Authentication routes (route group)
│   │   ├── sign-in/            # Sign-in page
│   │   └── sign-up/            # Sign-up page
│   ├── (routes)/               # Protected routes (route group)
│   │   └── dashboard/          # Dashboard routes
│   │       ├── _components/    # Dashboard components
│   │       ├── history/        # Session history page
│   │       └── medical-agent/  # Medical agent chat interface
│   ├── api/                    # API routes
│   │   ├── medical-report/     # Medical report generation
│   │   ├── session-chat/       # Session management
│   │   ├── suggest-doctors/    # Doctor recommendation
│   │   └── users/              # User management
│   ├── _components/            # Shared app components
│   ├── layout.tsx              # Root layout
│   ├── page.tsx                # Landing page
│   └── provider.tsx            # Context providers
│
├── components/                  # Reusable UI components
│   └── ui/                     # shadcn/ui components
│       ├── button.tsx
│       ├── dialog.tsx
│       ├── table.tsx
│       └── ...
│
├── config/                      # Configuration files
│   ├── db.tsx                  # Database connection
│   ├── schema.tsx              # Database schema
│   ├── gemmaModel.tsx          # Google Gemini config
│   └── OpenAiModel.tsx         # OpenAI config
│
├── context/                     # React contexts
│   └── UserDetailContext.tsx   # User context provider
│
├── lib/                         # Utility functions
│   └── utils.ts                # Helper utilities
│
├── shared/                      # Shared data/constants
│   └── list.tsx                # AI doctor agents list
│
├── public/                      # Static assets
│   ├── logo.webp
│   ├── favicon.png
│   └── doctor*.jpg             # Doctor profile images
│
├── middleware.ts                # Next.js middleware (auth)
├── drizzle.config.ts           # Drizzle ORM config
├── next.config.ts              # Next.js config
├── tsconfig.json               # TypeScript config
├── package.json                # Dependencies
└── README.md                   # This file
```

---

## 📋 Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** 18.x or higher
- **npm** or **yarn** or **pnpm**
- **PostgreSQL** database (or Neon account)
- Accounts for:
  - [Clerk](https://clerk.com) (Authentication)
  - [Google AI Studio](https://makersuite.google.com/app/apikey) (Gemini API)
  - [Neon](https://neon.tech) (Database) or any PostgreSQL provider
  - [Vapi AI](https://vapi.ai) (Voice interface)
  - [OpenRouter](https://openrouter.ai) (Optional, for OpenAI models)

---

## 🚀 Installation

### 1. Clone the Repository

```bash
git clone <your-repo-url>
cd carebuddy
```

### 2. Install Dependencies

```bash
npm install
# or
yarn install
# or
pnpm install
```

### 3. Environment Variables

Create a `.env.local` file in the root directory:

```env
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key

# Database
DATABASE_URL=your_neon_postgresql_connection_string

# AI Models
GOOGLE_API_KEY=your_google_gemini_api_key
OPEN_ROUTER_API_KEY=your_openrouter_api_key

# Vapi AI (if using voice features)
VAPI_API_KEY=your_vapi_api_key
```

### 4. Database Setup

#### Using Drizzle Kit

```bash
# Generate migrations
npx drizzle-kit generate

# Apply migrations
npx drizzle-kit push

# Or use migrate command
npx drizzle-kit migrate
```

#### Manual Setup

The database schema includes two main tables:

1. **users**: User information and credits
2. **sessionChatTable**: Medical session data, conversations, and reports

---

## ⚙️ Configuration

### Clerk Authentication Setup

1. Create an account at [Clerk](https://clerk.com)
2. Create a new application
3. Copy your publishable key and secret key
4. Add them to `.env.local`

### Google Gemini API Setup

1. Visit [Google AI Studio](https://makersuite.google.com/app/apikey)
2. Create a new API key
3. Add it to `.env.local` as `GOOGLE_API_KEY`

### Database Setup (Neon)

1. Create an account at [Neon](https://neon.tech)
2. Create a new project
3. Copy the connection string
4. Add it to `.env.local` as `DATABASE_URL`

### Vapi AI Setup (Optional)

1. Sign up at [Vapi AI](https://vapi.ai)
2. Get your API key
3. Add it to `.env.local` as `VAPI_API_KEY`

---

## 🗄️ Database Setup

### Schema Overview

#### Users Table
```sql
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  name VARCHAR(255) NOT NULL,
  email VARCHAR(255) NOT NULL UNIQUE,
  credits INTEGER
);
```

#### Session Chat Table
```sql
CREATE TABLE "sessionChatTable" (
  id SERIAL PRIMARY KEY,
  "sessionId" VARCHAR(255) NOT NULL,
  notes TEXT,
  "selectedDoctor" JSONB,
  conversation JSONB,
  report JSONB,
  "createdBy" VARCHAR(255) REFERENCES users(email),
  "createdOn" VARCHAR(255)
);
```

### Running Migrations

```bash
# Generate migration files
npx drizzle-kit generate

# Apply migrations to database
npx drizzle-kit push

# Or use migrate
npx drizzle-kit migrate
```

---

## 🏃 Running the Application

### Development Mode

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

The application will be available at `http://localhost:3000`

### Production Build

```bash
# Build the application
npm run build

# Start production server
npm start
```

### Linting

```bash
npm run lint
```

---

## 📡 API Reference

### Session Management

#### Create Session
```http
POST /api/session-chat
Content-Type: application/json

{
  "notes": "Patient symptoms description",
  "selectedDoctor": {
    "id": 1,
    "specialist": "General Physician",
    ...
  }
}
```

**Response:**
```json
{
  "SessionChatTable": {
    "id": 1,
    "sessionId": "uuid",
    "notes": "...",
    "createdOn": "...",
    ...
  }
}
```

#### Get Session(s)
```http
GET /api/session-chat?sessionId=all
GET /api/session-chat?sessionId={sessionId}
```

### Doctor Recommendations

#### Suggest Doctors
```http
POST /api/suggest-doctors
Content-Type: application/json

{
  "notes": "Patient symptoms"
}
```

**Response:**
```json
{
  "suggested_doctors": [
    {
      "id": 1,
      "specialist": "General Physician",
      "description": "...",
      ...
    }
  ]
}
```

### Medical Reports

#### Generate Report
```http
POST /api/medical-report
Content-Type: application/json

{
  "sessionId": "uuid",
  "sessionDetail": {
    "specialist": "...",
    ...
  },
  "messages": [...]
}
```

**Response:**
```json
{
  "sessionId": "uuid",
  "agent": "...",
  "user": "...",
  "timestamp": "ISO Date",
  "chiefComplaint": "...",
  "summary": "...",
  "symptoms": [...],
  "duration": "...",
  "severity": "...",
  "medicationsMentioned": [...],
  "recommendations": [...]
}
```

### User Management

#### Get/Create Users
```http
GET /api/users
POST /api/users
```

---

## 🧩 Key Components

### Dashboard Components

- **`AppHeader`**: Main dashboard header with navigation
- **`AddNewSessionDialog`**: Dialog for creating new medical sessions
- **`DoctorsAgentList`**: List of available AI doctor agents
- **`DoctorAgentCard`**: Individual doctor agent card
- **`HistoryList`**: List of past sessions
- **`HistoryTable`**: Table view of session history
- **`ViewReportDialog`**: Dialog for viewing medical reports
- **`SuggestedDoctorCard`**: Card for AI-suggested doctors

### Medical Agent Interface

- **`MedicalVoiceAgent`**: Main voice interaction component
- Handles real-time voice conversations
- Integrates with Vapi AI for voice processing
- Manages conversation state and AI responses

### Shared Components

- **`FeatureBentoGrid`**: Feature showcase grid on landing page
- **UI Components**: Reusable shadcn/ui components (Button, Dialog, Table, etc.)

---

## 💻 Development

### Code Structure

- **TypeScript**: Full type safety throughout the application
- **Server Components**: Default for better performance
- **Client Components**: Used only when interactivity is needed
- **API Routes**: Serverless functions for backend logic

### Best Practices

1. **Component Organization**: Group related components in `_components` folders
2. **Route Groups**: Use parentheses for route organization without affecting URLs
3. **Type Safety**: Leverage TypeScript for all components and API routes
4. **Error Handling**: Implement proper error boundaries and API error handling
5. **Loading States**: Use Suspense and loading states for better UX

### Adding New Features

1. Create components in appropriate directories
2. Add API routes in `app/api/`
3. Update database schema if needed
4. Run migrations
5. Update types and interfaces

---

## 🚢 Deployment

### Vercel Deployment (Recommended)

1. Push your code to GitHub/GitLab/Bitbucket
2. Import project in [Vercel](https://vercel.com)
3. Add environment variables in Vercel dashboard
4. Deploy

### Environment Variables in Production

Ensure all environment variables are set in your deployment platform:

- `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`
- `CLERK_SECRET_KEY`
- `DATABASE_URL`
- `GOOGLE_API_KEY`
- `OPEN_ROUTER_API_KEY`
- `VAPI_API_KEY`

### Database Migrations in Production

Run migrations before or during deployment:

```bash
npx drizzle-kit push
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Contribution Guidelines

- Follow TypeScript best practices
- Maintain code style consistency
- Add tests for new features
- Update documentation
- Follow commit message conventions

---

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

---

## 🙏 Acknowledgments

- [Next.js](https://nextjs.org) - React framework
- [Clerk](https://clerk.com) - Authentication
- [Google Gemini](https://deepmind.google/technologies/gemini/) - AI models
- [Vapi AI](https://vapi.ai) - Voice interface
- [Neon](https://neon.tech) - Serverless PostgreSQL
- [Drizzle ORM](https://orm.drizzle.team) - Type-safe ORM
- [shadcn/ui](https://ui.shadcn.com) - UI components

---

## 📞 Support

For support, email support@carebuddy.com or open an issue in the repository.

---

<div align="center">

**Made with ❤️ for better healthcare**

[⬆ Back to Top](#-carebuddy---ai-powered-healthcare-assistant)

</div>
