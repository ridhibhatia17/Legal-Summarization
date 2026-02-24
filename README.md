# LegalLM: Your AI-Powered Legal Document Analysis Workspace

LegalLM is an advanced, AI-driven application designed to streamline the process of legal document analysis. It provides a secure, intuitive workspace where legal professionals can upload documents, receive intelligent summaries, identify risks, and ask complex questions in natural language.

## Features

- **Multi-Format Document Upload**: Seamlessly upload and process documents in various formats, including `.txt`, `.pdf`, and `.docx`.
- **AI-Powered Summarization**: Instantly generate concise, structured summaries of your legal documents. The AI identifies key components such as parties, term length, key obligations, and potential risks.
- **Interactive Q&A**: Engage in a conversation with your documents. Ask specific questions and get clear, context-aware answers from the AI.
- **Risk & Clause Analysis**: Proactively identify potential legal risks, important obligations, and other critical clauses within your documents.
- **Legal Jargon Definition**: Get plain-language definitions for complex legal terms, explained within the specific context of your document.
- **Source-Cited Analysis**: Every piece of information provided by the AI is backed by a citation. Clicking a citation instantly highlights the exact source text in the document viewer, ensuring transparency and trust.
- **Modern & Responsive UI**: A clean, modern, and fully responsive user interface built for an efficient and pleasant user experience.

## Tech Stack

LegalLM is built with a modern, type-safe, and performant technology stack:

- **Framework**: [Next.js](https://nextjs.org/) (using the App Router)
- **Language**: [TypeScript](https://www.typescriptlang.org/)
- **AI & GenAI**: [Genkit](https://firebase.google.com/docs/genkit) (powered by Google's Gemini family of models)
- **UI Components**: [React](https://react.dev/), [ShadCN UI](https://ui.shadcn.com/)
- **Styling**: [Tailwind CSS](https://tailwindcss.com/)
- **File Parsing**: [pdf2json](https://www.npmjs.com/package/pdf2json), [Mammoth](https://www.npmjs.com/package/mammoth) for `.docx` files.
- **Deployment**: Deployed on [Netlify](https://www.netlify.com/).

## Live Demo
This application is deployed and accessible at Netlify.
https://legallm.netlify.app

## Getting Started

Follow these instructions to get a local copy of LegalLM up and running.

### Prerequisites

- [Node.js](https://nodejs.org/en) (version 18 or later recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)

### Installation & Setup

1.  **Clone the repository:**
    ```bash
    git clone <your-repository-url>
    cd <repository-folder>
    ```

2.  **Install dependencies:**
    ```bash
    npm install
    ```

3.  **Set up environment variables:**
    Create a file named `.env` in the root of your project and add your Google AI API key. You can get a key from [Google AI Studio](https://aistudio.google.com/app/apikey).

    ```env
    GEMINI_API_KEY=your_google_ai_api_key_here
    ```

4.  **Run the Genkit development server:**
    In a separate terminal, start the Genkit development server. This runs the AI flows that power the application.
    ```bash
    npm run genkit:watch
    ```
    This will start the Genkit server, typically on port 3400, and watch for any changes in your AI flow files.

5.  **Run the Next.js development server:**
    In your main terminal, start the Next.js application.
    ```bash
    npm run dev
    ```
    The application will be available at `http://localhost:9002`.

You should now have a fully functional local instance of LegalLM running!

## Deployment

This application is deployed on Netlify.

### Deploying to Netlify

Netlify provides excellent support for Next.js applications with automatic deployments from Git.

1. **Connect your repository:**
   - Log in to [Netlify](https://app.netlify.com/)
   - Click "Add new site" → "Import an existing project"
   - Connect your Git repository (GitHub, GitLab, or Bitbucket)

2. **Configure build settings:**
   - Build command: `npm run build`
   - Publish directory: `.next`
   - Node version: 18 or later

3. **Set environment variables:**
   - In Netlify project settings → Environment variables
   - Add `GEMINI_API_KEY` with your Google AI API key from [Google AI Studio](https://aistudio.google.com/app/apikey)

4. **Deploy:**
   - Click "Deploy site"
   - Netlify will automatically build and deploy your application
   - Future commits to your main branch will trigger automatic deployments

**Note:** If your app depends on a running Genkit server for AI flows, you may need to host that service separately (Cloud Run, Railway, or another server) and configure the appropriate endpoints. Always use environment variables for API keys and never commit secrets to your repository.