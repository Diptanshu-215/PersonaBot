# PersonaBot: Your AI-Powered Companion for Self-Reflection

![PersonaBot Banner](https://via.placeholder.com/1200x400/171717/F5F5F5?text=PersonaBot+--+AI+Counseling+and+Insights)

**PersonaBot** is an innovative AI-powered web application designed to provide a safe, private space for users to express themselves and gain deeper insights into their thoughts and feelings. Acting as a conversational AI companion, PersonaBot listens, engages in meaningful dialogue, and intelligently extracts key information and generates insightful analyses from your conversations, offering a unique blend of support and self-discovery.

Whether you're looking for a listening ear, a tool to track your emotional patterns, or to understand specific aspects of your mental well-being, PersonaBot is here to assist you on your journey.

## ✨ Features

-   **Interactive AI Chat:** Engage in natural, empathetic conversations with a sophisticated AI.
-   **Real-time Data Extraction:** PersonaBot intelligently identifies and extracts relevant information from your dialogue as you speak.
-   **AI-Powered Session Analysis:** Gain valuable insights into your mental health profile, key personality traits, potential support strategies, and information gaps.
-   **Dedicated Insights Dashboard:** A clear, organized view of all extracted data and AI analyses from your current session.
-   **Responsive & Intuitive UI:** A modern, user-friendly interface built with Next.js and Tailwind CSS for seamless interaction on any device.
-   **Dark Mode:** A comfortable dark theme for reduced eye strain and an aesthetic experience.
-   **Session State Management:** Your conversation and insights are stored locally for the duration of your session using Zustand.

## 🚀 Live Demo (Coming Soon!)

A live demo will be available shortly for you to experience PersonaBot in action.

## 🛠️ Tech Stack

PersonaBot is built with a robust and modern technology stack, ensuring a performant, scalable, and delightful user experience.

### Frontend
-   **Framework:** [Next.js](https://nextjs.org/) (React 19)
-   **Language:** [TypeScript](https://www.typescriptlang.org/)
-   **Styling:** [Tailwind CSS 4](https://tailwindcss.com/)
-   **UI Components:** [Radix UI](https://www.radix-ui.com/) & [Shadcn UI](https://ui.shadcn.com/)
-   **State Management:** [Zustand](https://zustand-ajv.barejs.com/)
-   **Icons:** [Lucide React](https://lucide.dev/)
-   **Theming:** [Next-Themes](https://github.com/pacocoursey/next-themes)
-   **Toasts:** [Sonner](https://sonner.emilkowalski.no/)

### Backend
-   **Framework:** [FastAPI](https://fastapi.tiangolo.com/)
-   **Asynchronous Server:** [Uvicorn](https://www.uvicorn.org/)
-   **AI Integration:**
    -   [Krutrim Cloud](https://www.krutrim.com/)
    -   [Groq](https://groq.com/)
-   **Environment Variables:** [python-dotenv](https://pypi.org/project/python-dotenv/)
-   **CORS Management:** [FastAPI Middleware](https://fastapi.tiangolo.com/tutorial/cors/)

## 🚦 Getting Started

Follow these instructions to set up and run PersonaBot locally on your machine.

### Prerequisites

Before you begin, ensure you have the following installed:

-   Node.js (v18.x or later) & npm / yarn
-   Python (v3.9 or later) & pip
-   Git

### 1. Clone the Repository

```bash
git clone https://github.com/Diptanshu-215/PersonaBot.git
cd PersonaBot
```

### 2. Set up the Backend

Navigate to the backend directory, install dependencies, and configure your environment.

```bash
cd persona-bot-backend
```

#### Install Dependencies

```bash
pip install -r requirements.txt
```

#### Environment Variables

Create a `.env` file in the `persona-bot-backend` directory and add your AI API keys. These keys are crucial for the AI services to function correctly.

```ini
# .env example for persona-bot-backend
KRUTRIM_API_KEY="your_krutrim_api_key_here"
GROQ_API_KEY="your_groq_api_key_here"
# Add any other API keys your AI services might require
```

#### Run the Backend Server

Start the FastAPI server. It will run on `http://127.0.0.1:8000`.

```bash
uvicorn app.main:app --reload --host 0.0.0.0 --port 8000
```
*(The `--host 0.0.0.0` is added for broader accessibility, as the frontend defaults to `127.0.0.1` and `allow_origins=["*"]` is set in main.py, making it compatible.)*

### 3. Set up the Frontend

Open a new terminal, navigate to the frontend directory, install dependencies, and start the Next.js development server.

```bash
cd ../persona-bot-frontend
```

#### Install Dependencies

```bash
npm install # or yarn install
```

#### Run the Frontend Development Server

```bash
npm run dev # or yarn dev
```

The frontend application will typically start on `http://localhost:3000`.

### 4. Access PersonaBot

Open your web browser and navigate to `http://localhost:3000`. You should now be able to interact with PersonaBot!

## 📂 Project Structure

The repository is organized into two main parts: the `persona-bot-backend` (FastAPI) and `persona-bot-frontend` (Next.js).

```
PersonaBot/
├── persona-bot-backend/
│   ├── app/
│   │   ├── __init__.py
│   │   ├── config.py             # Backend configuration (e.g., API keys)
│   │   ├── dependencies.py       # FastAPI dependency injection
│   │   ├── main.py               # Main FastAPI application, CORS, and root routes
│   │   ├── routes/
│   │   │   ├── __init__.py
│   │   │   └── chat.py           # Chat API endpoint logic
│   │   └── services/
│   │       ├── ai_service.py     # Handles AI model interactions (Krutrim, Groq)
│   │       └── chat_service.py   # Business logic for chat processing
│   ├── requirements.txt          # Python dependencies
│   └── .env.example              # Example for backend environment variables
├── persona-bot-frontend/
│   ├── public/                   # Static assets
│   ├── src/
│   │   ├── app/
│   │   │   ├── globals.css       # Global styles (Tailwind, custom themes)
│   │   │   ├── layout.tsx        # Root layout for Next.js application
│   │   │   ├── page.tsx          # Main chat interface page
│   │   │   └── insights/
│   │   │       └── page.tsx      # Session insights dashboard page
│   │   ├── components/
│   │   │   └── ui/               # Reusable Shadcn UI components
│   │   │       ├── badge.tsx
│   │   │       ├── button.tsx
│   │   │       ├── card.tsx
│   │   │       ├── input.tsx
│   │   │       ├── scroll-area.tsx
│   │   │       ├── separator.tsx
│   │   │       ├── sonner.tsx    # Toast notification component
│   │   │       └── tabs.tsx
│   │   ├── lib/
│   │   │   ├── store.ts          # Zustand store for session data and analysis
│   │   │   └── utils.ts          # Utility functions (e.g., `cn` for Tailwind)
│   │   └── types.ts              # TypeScript type definitions
│   ├── .gitignore
│   ├── package.json              # Frontend dependencies and scripts
│   ├── tsconfig.json             # TypeScript configuration
│   └── next.config.ts            # Next.js configuration
├── README.md                     # This file
└── readme.md                     # (Potentially deprecated, main is README.md)
```

## 🤝 Contributing

We welcome contributions to PersonaBot! If you have suggestions, bug reports, or want to add new features, please feel free to:

1.  **Fork** the repository.
2.  **Create a new branch** (`git checkout -b feature/your-feature-name` or `bugfix/your-bug-name`).
3.  **Make your changes**.
4.  **Commit your changes** (`git commit -m 'feat: Add new awesome feature'`).
5.  **Push to the branch** (`git push origin feature/your-feature-name`).
6.  **Open a Pull Request** describing your changes.

Please ensure your code adheres to the project's coding style and includes appropriate tests where applicable.

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Made with ❤️ by Diptanshu-215