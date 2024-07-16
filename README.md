# EchoPDF
EchoPDF: AI-powered PDF interaction and management platform. This repo provides an overview of the project, highlighting key features, technical challenges, and implementation details of a full-stack web application built with MERN, Pinecone, Stripe, Clerk, S3, deployed on GCP.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Key Features](#key-features)
3. [Try It Out](#try-it-out)
4. [Technical Stack](#technical-stack)
5. [Architecture Overview](#architecture-overview)
6. [Core Components](#core-components)
   - [PDF Management](#pdf-management)
   - [AI-Powered Chat](#ai-powered-chat)
   - [RAG Implementation](#rag-implementation)
   - [Custom PDF Viewer](#custom-pdf-viewer)
   - [Template Gallery](#template-gallery)
7. [Key Technical Challenges](#key-technical-challenges)
8. [Custom Feature Spotlights](#custom-feature-spotlights)
   - [Custom Markdown Parser](#custom-markdown-parser)
   - [Custom Highlight Feature](#custom-highlight-feature)
9. [User Tiers and Monetization](#user-tiers-and-monetization)
10. [Development Journey](#development-journey)
    - [Timeline](#timeline)
    - [Learning Process](#learning-process)
11. [Future Development Plans](#future-development-plans)
12. [Lessons Learned](#lessons-learned)
13. [Contact Information](#contact-information)


# EchoPDF

## 1. Project Overview

EchoPDF is an AI-powered PDF interaction and management platform that enhances how users engage with PDF documents. Evolved from a final year project into a full-stack web application, EchoPDF integrates AI technology (LLM and embeddings) with document management to create an efficient experience for PDF users.

The core idea I have for EchoPDF is to bring the full power of ChatGPT and integrate it seamlessly into PDF reading and analysis. By leveraging advanced Retrieval-Augmented Generation (RAG) techniques and a customizable PDF viewer, EchoPDF aims to significantly improve user productivity when working with PDF documents. The platform's strategy focuses on providing a superior RAG system, coupled with an array of PDF management and interaction features, to set it apart from countless competitors in the current market.

Key aspects of EchoPDF:

- PDF upload and organization system
- ChatGPT API integration for intelligent document interaction
- Retrieval-Augmented Generation (RAG) for in-depth content analysis
- Customizable PDF viewer interface
- Prompt template gallery with sharing and interactable posts, and template copying functionality to personal template collection

As both a potential startup product and a comprehensive portfolio piece, EchoPDF showcases a range of technical skills across the full stack of web development, such as:

- Modern front-end development with React
- Back-end development using Node.js
- AI integration, leveraging ChatGPT API for advanced document interaction
- Vector database management (Pinecone) for efficient document retrieval
- NoSQL database management (MongoDB) for application data
- User authentication and authorization systems
- Payment processing and subscription management with Stripe
- Cloud storage solutions (AWS S3) for document management
- Responsive web design and user interface customization
- Custom integration of PDF.js, including direct wrapping with React and webpack bundling
- Prompt engineering and optimization for AI interactions
- Text embedding and vector operations for enhanced document analysis
- Custom algorithms for context-aware document content selection

EchoPDF represents a significant personal and professional journey in software development. What began as my final year project in early December 2023 evolved into a comprehensive full-stack application over the course of about seven months.

Key milestones in the project's development:

- Early December 2023: I started learning full-stack development for the first time with 4 months of internship experience with FusionEx Malaysia on front-end, am charts, kojs experience. 
- Early January 2024: I completed initial MVP for final year project, deployed on Heroku after submission
- February 2024: I completed final exams and pratically graduated with a general CS degree
- Late February 2024: I decided to expand EchoPDF into a comprehensive startup/product-like application
- July 15th 2024: Officially launched EchoPDF

This project marks a rapid transition from a beginner in full-stack development to creating and deploying a complex'ish, AI-integrated web application. The development process hopefully shows my ability to quickly learn and implement new technologies effectively:

- Learned and implemented React in just 2.5 weeks to create the application's backbone and complete the template gallery feature
- Acquired proficiency in various full-stack technologies and frameworks, all learned from scratch during the project's development
- Demonstrated initiative through several custom implementations:
  - Developed a custom markdown parser for handling ChatGPT streaming API text chunks
  - Created a custom highlight tool for PDF interaction
  - Integrated React with PDF.js by directly wrapping the PDF.js repo code, using webpack for bundling
  - Studied and customized PDF.js codebase to implement additional features and optimizations
  - Deployed with Google Cloud Platform VMs in 2 days, with some past experience failing to deploy on ElasticBeanstalk and sucessfully deploying on Heroku.
 
Note that in some areas of EchoPDF development, it is currently implemented in a basic form or not implemented:

- Complex DevOps practices
- Automated Continuous Integration/Continuous Deployment (CI/CD) pipelines
- Comprehensive unit testing
- Type safety (e.g., TypeScript)
- Caching solutions (e.g., Redis)
- Advanced deployment practices (e.g., Kubernetes, Docker)

The project currently uses a basic form of continuous deployment:
- Code is pushed directly to the GitHub repository
- Deployment is done manually via SSH, using commands to pull from the main branch, build, and restart the application

While this approach works for the current scale, it's recognized that more robust, automated CI/CD pipelines would be beneficial as the project grows.

These more advanced aspects, while crucial in larger-scale, production-level applications, were not fully implemented in the current version of EchoPDF due to its current scale and development timeline. However, their importance in professional software development is well understood.

As EchoPDF scales and I grow, there's a clear roadmap for enhancing these practices:

- Automating the CI/CD pipeline for more robust and consistent deployment processes
- Introducing comprehensive unit tests to ensure code reliability
- Considering the adoption of TypeScript for enhanced type safety
- Exploring caching solutions to improve performance
- Investigating containerization and orchestration for more scalable deployment

Given the demonstrated ability to quickly learn and implement new technologies throughout this project, there's confidence in rapidly acquiring and applying these additional skills as the project scales. The journey of EchoPDF showcases not just my current abilities, but also my capacity and willingness to continually learn and adapt to best practices in software development.
EchoPDF demonstrates not only technical skills, but also the capacity for rapid learning, problem-solving, and taking initiative in software development. It represents an ongoing journey of growth and improvement, with plans for future enhancements in PDF viewing, annotation capabilities, and overall user experience.


## 2. Key Features

EchoPDF offers a range of features designed to enhance PDF interaction and management:

1. User Authentication and Authorization
   - Secure user authentication and route protection using Clerk
   - Protected endpoints and React routes for enhanced security

2. Template Gallery
   - Browse, interact with, and use community-created prompt templates
   - Social media-like interface with real-time updates for upvotes, downvotes, and flagging
   - Categorized templates with tagging system for easy navigation
   - Sort template posts with category pages, and filters such as upvotes, creation time, etc.

3. Subscription Management
   - Flexible subscription plans with tiered access to features
   - Easy scheduling of plan switching and credit purchase options
   - Stripe webhook integration for real-time subscription updates

4. Document Management
   - Upload single or multiple PDFs with progress tracking UI
   - Organize documents in a folder structure
   - Tier-based upload limits with extensive middleware checks and error handling (React Hot Toast)
   - Secure file storage using AWS S3

5. AI-Powered PDF Interaction
   - Interact with PDFs using ChatGPT API integration
   - Advanced Retrieval-Augmented Generation (RAG) system:
     - Document embedding using OpenAI's ADA 2 
     - Efficient vector storage and retrieval with Pinecone database
     - Custom vector selection algorithm for optimal context retrieval
   - Real-time kNN query for most relevant document sections
   - Page-aware content retrieval based on user queries
   - Customizable RAG word limits based on user tier, with toggle option
   - Well-crafted system message enabling smooth, intelligent, responsive ChatGPT responses with RAG  
   - Chat history, including latest user message, formatting for enhanced AI responses
   - Interactive page navigation from AI responses to relevant PDF sections
   - Dynamic navigation and highlighting in PDF viewer of PDF content used by ChatGPT
   - Metadata of PDF content used are saved and formatted for ChatGPT interactions

6. Customizable PDF Viewer
   - Feature-rich PDF viewer built on top of PDF.js repo code, wrapped with React
   - Light, dark, and original viewing modes
   - Movable toolbar for enhanced user experience
   - Retained PDF.js features: search, zoom, thumbnail navigation

7. Chat History and Management
   - Organized chat history with PDF-specific and general chats
   - Displaying current PDF, general, and other PDF chats in sidebar
   - Efficient chat loading with scroll-based pagination
   - Chat renaming and deletion options
   - Enhanced sidebar UI given width constraints 

8. Prompt Engineering Tools
   - Template system for efficient AI interactions
   - Custom prompt formatting with template, user input, and PDF content combination for final ChatGPT response

9. Enhanced User Interface
   - Sophisticated auto-scrolling feature:
     - Automatic scroll to bottom for new chats and user prompt instances
     - Smart scroll-following for streaming AI responses with flexible user control  
   - Clickable page references in AI responses for quick navigation
   - Abort functionality for stopping AI response generation
   - Responsive design adapting to various screen sizes, but currently not mobile friendly
   - Custom dynamic markdown parser for rendering AI responses

10. Multi-Model AI Support
    - Support for multiple AI models including GPT-3.5 Turbo and GPT-4
    - Automatic token usage calculation and limits management
    - Tier-based access to advanced AI models
    - Checks and error handling for model usage limits

Coming Soon:
- Savable annotations (highlights, drawings, text)
- Image attachment feature for AI analysis
- Smart suggestion feature for chats
- One-click template copying from gallery to personal collection
- Planned feature for editing last user prompt or refreshing latest AI response
- Enhanced folder management (rename, delete, etc.)

## 6. Core Components

### 6.1 User Authentication and Authorization

EchoPDF implements a robust user authentication and authorization system using Clerk, ensuring secure access to the application's features and protecting user data.

#### Clerk Integration

- The application is wrapped with `ClerkProvider` in the root `App.js` file, providing authentication context throughout the app.
- Clerk's `SignInPage` and `SignUpPage` components are used for user registration and login, offering a seamless and secure authentication experience.

#### Protected Routes and Components

- A custom `ProtectedRoute` component is implemented using React Router and Clerk's `useAuth` hook.
- This component ensures that only authenticated users can access certain parts of the application:
  ```jsx
  const ProtectedRoute = () => {
    const { isSignedIn, isLoaded } = useAuth();
    if (!isLoaded) return <LoadingSpinner />;
    return isSignedIn ? <Outlet /> : <Navigate to="/sign-in" />;
  };
  ```
  Protected routes are wrapped with this component in the main routing structure.

User Session Management

User session data is managed through a custom UserContext and UserProvider.
This context fetches and stores user details, including subscription status and usage metrics, making this information readily available throughout the application.

Backend Authentication

The backend uses ClerkExpressRequireAuth() middleware to protect sensitive endpoints.
This middleware verifies the authentication token sent from the frontend and attaches the user ID to req.auth.
Example of a protected endpoint:
```javascript
 app.post('/api/user', ClerkExpressRequireAuth(), async (req, res) => {
  const userId = req.auth.userId;
  // Process authenticated user request
});
```

Security Considerations

All sensitive operations, both on the frontend and backend, are protected behind authentication checks.
User data is securely stored and managed using Clerk's best practices, reducing the risk of data breaches.
The application adheres to modern security standards, including HTTPS enforcement and secure cookie handling.

This authentication and authorization system ensures that EchoPDF provides a secure environment for users to interact with their PDF documents and AI features, while also demonstrating best practices in web application security.


