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

## 3. Try It Out
Experience EchoPDF firsthand at [https://echopdf.com](https://echopdf.com). For your convenience and security, all HTTP and www routes are automatically redirected to the secure HTTPS version of the site. Here's how you can get started:

1. Visit EchoPDF.com and create a free tier account using any email address or your Gmail account.
2. Once registered, you'll have immediate access to:
   * Upload up to 200 PDF pages
   * Ask 100 questions using the GPT-3.5-turbo model
   * Explore all core features of the application
3. Free tier users can fully experience the power of EchoPDF, including:
   * AI-powered PDF interaction
   * Custom PDF viewer with adjustable layout
   * Template gallery for efficient prompts
   * Basic document management features

I encourage you to explore the application, test its capabilities, and see how EchoPDF can enhance your PDF interaction experience. If you find the service valuable as a user, consider upgrading to the paid tiers for increased limits and additional premium features.

Feel free to reach out with any questions or feedback - I'm always looking to improve your experience with EchoPDF!

For EchoPDF-related matters, please contact: echopdf.service@gmail.com
For employment opportunities, partnerships, or project collaborations, you can reach me directly at: marvinnlhy@gmail.com

As a solo developer, I'm excited to hear from users, potential collaborators, and anyone interested in the project. Your feedback and ideas are invaluable in shaping the future of EchoPDF. Whether you're a user with suggestions, a company looking to integrate similar technology, or just someone curious about the project, don't hesitate to get in touch. I'm always open to discussions that could lead to improving EchoPDF or exploring new opportunities in the tech world.

## 4. Technical Stack
### Overview
**Final Year Project:**
- Frontend: Vanilla JavaScript, pdf.js
- Backend: Node.js, Express
- Database: MongoDB
- Authentication: Clerk
- Storage: AWS S3
- AI: ChatGPT API
- Deployment: Heroku

**EchoPDF:**
- Frontend: React, pdf.js
- Backend: Node.js, Express
- Database: MongoDB
- Authentication: Clerk
- Storage: AWS S3
- Vector Database: Pinecone
- Payment: Stripe
- AI: ChatGPT API (GPT-3.5, GPT-4)
- Deployment: Google Cloud Platform (Compute Engine)

### PDF Viewer Selection
When I started building EchoPDF, it began as my final year project - a much simpler version of what it is now. One of the toughest decisions early on was choosing a PDF viewer library. Being my first real development project, I wanted to stick with vanilla JavaScript, ruling out npm packages like react-pdf. This left me with either pdf.js dist or the pdf.js repo.
I was pretty set on including as many essential PDF features as possible - annotations, sidebar, word search, you name it. This bias stuck with me even as EchoPDF evolved. I ended up choosing the pdf.js repo code, despite it being more challenging to work with, because it offered the full range of features I wanted.

### Frontend Framework
For the framework, I went with React. It's popular, which usually means good community support, and I liked how the latest updates seemed to clean up a lot of the code complexity. Plus, it plays nice with Clerk and Stripe, offering component support which is a huge plus.
Integrating pdf.js with React was a bit of a head-scratcher. I had to decide between migrating pdf.js to my Create React App setup (where I'd already built the template gallery and auth routing) or bringing React into pdf.js. In the end, I moved React into pdf.js and used webpack to run JSX. I had to wrap the pdf.js web viewer with React to make it work as a component, mainly because I needed the viewer to take up half the screen width with an adjustable bar.

### CSS Framework
For styling, I chose Tailwind CSS. It was a bit of a learning curve at first, but I quickly found it incredibly efficient for rapid UI development. The utility-first approach allowed me to create consistent designs without leaving my HTML (or JSX in this case). It also integrates well with React, making component styling a breeze. The purge feature in production builds keeps the final CSS bundle small, which is great for performance. Overall, Tailwind CSS proved to be a great choice for building a responsive and visually appealing interface for EchoPDF.

### Backend
For the backend, I went with Express. It just seems like the go-to for JavaScript backends, and I didn't see any close seconds. MongoDB was my choice for the database. It's easy to use and efficient to query. For this kind of app, with lots of component-based data that doesn't really need to talk to each other much, NoSQL felt like a better fit than SQL.

### Payment Processing
Stripe was the obvious choice for payments. Their test environment, reasonable pricing (1 MYR + 3%), and CLI tools for webhook testing were crucial for building a solid, bug-free payment system.

### Authentication
I picked Clerk for authentication somewhat impulsively. It's popular, has a free tier, and offers components for both vanilla JS and React. In hindsight, since I deployed on Google Cloud, Firebase might have been a more cohesive choice, offering centralized auth and database services. But I stuck with Clerk and MongoDB since I was already familiar with them.

### Vector Database
For vector storage, I went with Pinecone DB. I learned about it through a YouTube tutorial that taught me the basics of vectorizing PDF content and using OpenAI's Ada 2 for embeddings. The pricing is very reasonable with their serverless tier.

### File Storage
I stuck with AWS S3 for file storage because I'd used it in my final year project and found it reliable and easy to set up. Again, Firebase storage could have been an option for more centralization, but I went with what I knew.

### AI Model
ChatGPT was really the only game in town for the AI model. The 3.5 model works great for the base offer, with GPT-4 Turbo and GPT-4 offered as premium options. I'm considering adding Anthropic models in the future, especially since their Sonnet 3.5 is probably the best model out there right now.

### Deployment
For deployment, I went with Google Cloud Platform, using a Compute Engine VM with 10GB RAM and 2 cores running Debian Linux. It took two full days to deploy, but I think it was worth it for the customization options. I'm using Nginx to route traffic to my proxy server on port 3001, and I've set up SSL certs which are crucial for Stripe and for user trust.

### DevOps
My DevOps setup is pretty basic - I'm using GitHub for version control, pulling code to my VM, and using PM2 to manage my server instance. This setup allows for near-zero downtime during code pushes.
I haven't gotten into Docker or Kubernetes yet - for now, this setup is working well for the scale of EchoPDF.

## 5.0 Architecture Overview

### 5.1 Overall System Architecture

EchoPDF follows a modern web application architecture, combining a Single Page Application (SPA) frontend with a RESTful API backend. This setup is implemented as a "Single-Repository Decoupled Architecture" or a "Monorepo with Decoupled Frontend and Backend."

**Current Implementation:**
- Frontend: React-based SPA
- Backend: Node.js with Express.js framework
- Repository Structure: Monorepo (frontend and backend in one repository)
- Build Process: Webpack for bundling frontend code
- Deployment: PM2 runs the server, which serves static files from the public build directory

The frontend, built with React, handles the user interface and client-side logic. It communicates with the backend through RESTful API calls. The backend, powered by Node.js and Express.js, processes these requests, interacts with the database and external services, and sends responses back to the frontend.

**Key Architectural Aspects:**
1. Component-Based Frontend: React's component architecture allows for modular, reusable UI elements.
2. Single Page Application: Provides a fluid, desktop-like user experience with minimal page reloads.
3. RESTful Backend: Express.js server structured to handle API requests efficiently.
4. Decoupled Design: Despite being in one repository, frontend and backend concerns are separated.

**Alternatives Considered:**
1. Multi-Page Application (MPA): Traditional website structure with separate HTML pages.
   - Pros: Better SEO out of the box, simpler architecture for very simple sites.
   - Cons: Slower navigation, more server load, less fluid user experience.

2. Server-Side Rendering (SSR):
   - Pros: Better initial load times, improved SEO.
   - Cons: More complex setup, potentially unnecessary for EchoPDF's core functionality.

3. Microservices Architecture:
   - Pros: Highly scalable, allows independent scaling of different features.
   - Cons: More complex to set up and manage, potentially overkill for the current scale of EchoPDF.

**Reasoning:**
The chosen architecture strikes a balance between development simplicity and application performance. The SPA approach is well-suited for EchoPDF's interactive nature, providing a smooth user experience for PDF viewing and AI interactions. The monorepo structure simplifies development and deployment processes while still maintaining a clear separation of frontend and backend concerns.

**Considerations for Improvement:**
1. SEO Optimization: If needed, implement SSR for specific routes (e.g., landing page, documentation) using a framework like Next.js.
2. State Management: As the application grows, consider introducing a more robust state management solution.
3. Code Splitting: Implement lazy loading for different parts of the application to improve initial load times.
4. API Gateway: For future scaling, consider introducing an API gateway for better request management and potential microservices integration.

This architecture provides a solid foundation for EchoPDF's current needs while leaving room for future scaling and feature additions. The modular nature of this setup allows for incremental improvements and optimizations as the user base and feature set grow.

## 5.2 Frontend Architecture

EchoPDF's frontend is built using React, embracing a component-based architecture that prioritizes modularity, reusability, and clear separation of concerns. This approach allows for efficient development and easier maintenance as the application grows.

### Key Components:
1. React: The core library used for building the user interface.
2. Context API: Used for state management, avoiding the need for more complex solutions like Redux.
3. Tailwind CSS: Utilized for styling, providing a utility-first approach to CSS.

### State Management:
1. Context API is the primary method for managing global state.
2. The application follows a rule of allowing one level of prop drilling. Any state that needs to be passed down more than one level is managed through Context.
3. This approach balances the simplicity of prop passing with the power of centralized state management.

### Component Structure:
The frontend is organized into several key directories:

1. **Pages**:
   - Contains top-level components that represent entire pages.
   - Each page component is responsible for layout and composing smaller components.

2. **Components**:
   - Houses reusable UI components.
   - Organized into sub-folders based on the specific pages or features they relate to.
   - This structure helps in quickly locating and managing related components.

3. **Layout**:
   - Contains components that define the overall structure of the application (e.g., headers, footers, navigation).

4. **Utils**:
   - Includes utility functions and helper code used across the application.

### Performance Optimizations:
1. **Code Splitting**: Utilizes React.lazy() and Suspense for lazy-loading components.
   - This approach improves initial load times by only loading necessary components.
   - Particularly beneficial for larger features or less frequently accessed parts of the application.

2. **Dynamic Imports**: Employed for route-based code splitting, ensuring that code for each route is loaded on demand.

### Styling Approach:
1. Tailwind CSS is used for styling components.
2. This utility-first approach allows for rapid UI development and consistent design across the application.

### Design Principles:
1. Modularity: Components are designed to be self-contained and reusable where possible.
2. Separation of Concerns: Each component has a clear, specific responsibility.
3. Hierarchical Structure: The component tree is organized to reflect the natural hierarchy of the UI.

### Data Flow:
1. API calls are typically made from page-level components or custom hooks using fetch.
2. Data is then passed down to child components via props or made available through Context.
3. Components use local state (useState hook) for managing component-specific data.

### Considerations and Future Improvements:
1. Performance Optimization: Regular audits using React DevTools to identify and resolve performance bottlenecks.
2. Accessibility: Ensure all components meet WCAG guidelines for accessibility.
3. Testing: Implement a comprehensive testing strategy, including unit tests, using frameworks like Cypress for frontend and Mocha for backend, for utility functions and components.

---

This frontend architecture provides a balance between simplicity and scalability. The use of Context API for state management keeps the application's data flow straightforward, while the modular component structure allows for easy expansion and maintenance. As EchoPDF grows, this architecture can be easily adapted to incorporate more advanced patterns or optimizations as needed.

## 5.3 Backend Architecture

EchoPDF's backend is built on Node.js with Express.js, following a modular and scalable architecture. The server is structured to handle various aspects of the application efficiently, with clear separation of concerns and well-organized API endpoints.

### Server Setup:
* The main server runs on localhost:3001
* CORS is configured to handle requests from the EchoPDF domain
* Express.js is used as the web application framework

### API Structure:
The API endpoints are organized into logical groups based on functionality:

1. **Document Handling API** (/api/documents):
   * Manages PDF upload, retrieval, and deletion
   * Interacts with AWS S3 for file storage

2. **Template API** (/api/templates):
   * Handles CRUD operations for prompt templates
   * Manages template categories and user interactions

3. **ChatGPT Integration API** (/api/chat):
   * Processes chat requests and interactions with the ChatGPT model
   * Manages token usage and model selection

4. **Vector Database API** (/api/vector):
   * Interfaces with Pinecone for vector storage and retrieval
   * Handles document embedding and semantic search operations

5. **User Management API** (/api/users):
   * Manages user profiles, settings, and subscription information

6. **Subscription and Payment API** (/api/subscription):
   * Handles subscription management and integrates with Stripe

### Middleware:
The application uses a combination of custom middleware and third-party solutions:

1. **Authentication Middleware**:
   * Utilizes ClerkRequireAuth for protecting sensitive endpoints
   * Ensures that only authenticated users can access protected resources

2. **Usage Limit Middleware**:
   * Checks and enforces PDF upload limits based on user tiers
   * Manages ChatGPT token usage and credit deduction
   * Implements context truncation for ChatGPT API requests

3. **Pinecone Database Management Middleware**:

   * Ensures namespace allocation for users in the Pinecone vector database
   * Manages index creation and maintenance for efficient vector storage and retrieval
   * Automatically handles resource allocation based on user tiers and usage patterns

4. **Error Handling Middleware**:
   * Centralized error handling to ensure consistent error responses

### Webhook Handling:
A dedicated webhook handler is implemented to process Stripe events:
* Manages various subscription-related events (e.g., invoice paid, subscription updated/deleted)
* Handles checkout session completion
* Includes logging functions for auditing and debugging purposes

### Database Interaction:
* Utilizes Mongoose for MongoDB interactions
* Models are defined for various entities (User, Document, Template, etc.)
* Implements efficient querying patterns to optimize database operations

### External Service Integration:
* AWS S3 for file storage
* Pinecone for vector database operations
* OpenAI API for ChatGPT interactions
* Stripe for payment processing

### Logging and Monitoring:
* Implements comprehensive logging for critical operations and errors
* Utilizes a centralized logging system for easier debugging and monitoring

### Security Measures:
* Implements rate limiting to prevent abuse
* Uses helmet.js for setting various HTTP headers for security
* Ensures secure handling of sensitive information (API keys, user data)

### Scalability Considerations:
* The modular structure allows for easy scaling of individual components
* Stateless design principles are followed to allow for horizontal scaling

  

## 5.4 Database Architecture

EchoPDF utilizes MongoDB, a NoSQL database, which perfectly aligns with the application's data structure and scalability needs. The database architecture is designed to be flexible, efficient, and easily scalable, supporting the various features of the application without the need for complex relationships.

### Schema Design

#### 1. User Schema
- Comprehensive user model capturing authentication, subscription, usage, and preferences
- Includes methods for updating usage, managing subscriptions, and credit operations

#### 2. Chat and Message Schemas
- Separate schemas for chat sessions and individual messages
- Efficiently stores chat history with references to PDFs and AI model preferences

#### 3. PDF File and Vector Schemas
- Manages PDF file metadata and associated vector data for AI operations
- Optimized for quick retrieval and association with user accounts

#### 4. Template Schemas
- Supports both system-wide templates and user-specific template collections
- Flexible structure to accommodate various template types and parameters

#### 5. Folder Schema
- Implements a hierarchical structure for organizing PDF files
- Optimized for efficient querying of user's folder structure

#### 6. Category and Tag Schemas
- Supports categorization and tagging of templates
- Enables efficient filtering and organization of content

#### 7. Interaction Schema
- Tracks user interactions with templates (upvotes, downvotes, flags)
- Designed for efficient updating and querying of user interactions

#### 8. Counter Schemas
- Manages namespace and index allocation for Pinecone database
- Supports efficient scaling and resource management

### Key Design Principles

1. **Denormalization**
   - Data is strategically denormalized to optimize read performance
   - Reduces the need for complex joins, enhancing query efficiency

2. **Indexing**
   - Strategic indexes are implemented on frequently queried fields
   - Improves query performance, especially for user-specific and time-based queries

3. **Embedded Documents**
   - Utilizes embedded documents for closely related data (e.g., template parameters)
   - Enhances read performance and maintains data locality

4. **Reference-based Relationships**
   - Uses references for looser relationships (e.g., chats referencing PDF files)
   - Balances between data consistency and query performance

5. **Schema Methods**
   - Implements schema-level methods for common operations
   - Encapsulates business logic at the data model level, promoting code reusability and maintainability

### Scalability Considerations

1. **Sharding Readiness**
   - Schemas are designed with potential sharding in mind (e.g., userId as a common field)
   - Enables horizontal scaling as the application grows

2. **Flexible Schema**
   - MongoDB's flexible schema allows for easy additions to data models as new features are developed

3. **Efficient Querying**
   - Schema design prioritizes the most common query patterns in the application

### Data Integrity and Consistency

1. **Validation**
   - Utilizes Mongoose schema validations to ensure data integrity
   - Implements custom validation logic where necessary

2. **Atomic Operations**
   - Uses MongoDB's atomic operations for critical updates (e.g., credit management)

3. **Timestamps**
   - Automatic timestamp management for tracking document creation and updates

---

This database architecture provides a solid foundation for EchoPDF, offering flexibility, performance, and scalability. The NoSQL approach of MongoDB aligns well with the application's needs, allowing for rapid development and easy adaptation to changing requirements. The thoughtful schema design, with its focus on denormalization and efficient querying, ensures that the database can handle the application's current needs while being prepared for future growth and feature additions.

## 5. Deployment Architecture

EchoPDF is deployed on Google Cloud Platform (GCP), leveraging its robust infrastructure to ensure reliability and scalability. Here's an overview of the deployment setup:

### 5.1 Google Cloud Platform Configuration

- **Zone**: us-east4-c
- **Machine Type**: e2-medium
- **CPU Platform**: Intel Broadwell
- **Architecture**: x86/64
- **Operating System**: Debian 12 Bookworm

### 5.2 Networking

- **Public IP**: 35.245.124.145 (Ephemeral)
- **Internal IP**: 10.150.0.2
- **Network Tier**: Premium
- **Firewalls**: HTTP and HTTPS traffic enabled
- **Network Tags**: http-server, https-server

### 5.3 Storage

- **Boot Disk**: 10 GB Balanced Persistent Disk
- **Interface Type**: SCSI
- **Encryption**: Google-managed

### 5.4 Nginx Configuration

I use Nginx as a reverse proxy to handle incoming requests and route them to the application server. Key aspects of the Nginx configuration include:

- HTTP to HTTPS redirection
- WWW to non-WWW redirection
- SSL certificate management using Let's Encrypt
- Proxy settings for the Node.js application running on port 3001
- Security headers (X-Frame-Options, X-XSS-Protection, X-Content-Type-Options)
- Custom error page for 502 errors

### 5.5 SSL Certificate Management

SSL certificates are obtained and managed using Let's Encrypt. I've set up a Python script to automatically renew the certificates periodically, ensuring uninterrupted HTTPS support.

### 5.6 Application Deployment

The Node.js application is run using PM2, a process manager for Node.js applications. This setup allows for:

- Automatic restarts in case of crashes
- Load balancing (if needed in the future)
- Easy log management

### 5.7 Scalability and Future Considerations

While the current setup is suitable for the present scale of EchoPDF, the use of GCP allows for easy scaling in the future. Potential upgrades could include:

- Increasing machine resources (CPU, RAM) as demand grows
- Implementing a load balancer for distributing traffic across multiple instances
- Setting up auto-scaling groups to handle traffic spikes automatically

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

### 6.2 Template Gallery
The Template Gallery is a core feature of EchoPDF, providing users with a rich collection of community-created prompt templates. This feature enhances user experience by offering ready-to-use templates and fostering community engagement.

#### Template Post Structure and Functionality

Schema Design: The Template schema includes fields for title, description, tags, user information, template content, application type, interaction metrics (upvotes, downvotes, flags), creation timestamp, categories, and copy count.
Rich Content: Each template post contains detailed information including the author's profile, creation date, and a comprehensive template structure with customizable parameters.

```javascript
const templateSchema = new Schema({
  title: { type: String, required: true },
  description: { type: String, required: true },
  tags: [{ type: String }],
  userId: { type: String, required: true },
  username: { type: String, required: true },
  profileImageUrl: { type: String, required: false, default: null },
  template: {
    name: { type: String, required: true },
    parameters: [
      {
        key: { type: String, required: true },
        value: { type: String, required: true },
      },
    ],
    description: { type: String, required: false },
  },
  applyTo: { type: String, required: true },
  upvotes: { type: Number, default: 0 },
  downvotes: { type: Number, default: 0 },
  flags: { type: Number, default: 0 },
  createdAt: { type: Date, default: Date.now },
  categories: [{ type: Schema.Types.ObjectId, ref: "Category" }],
  parentCategories: [{ type: Schema.Types.ObjectId, ref: "Category" }],
  copyCount: { type: Number, default: 0 },
});
```
#### Real-time Interaction Features

Voting System: Users can upvote or downvote templates, with real-time updates reflected in the UI.
Flagging Mechanism: A flagging system is implemented for community moderation.
Interaction Tracking: User interactions (votes, flags) are tracked using a separate Interaction schema, ensuring one interaction per user per post.

```javascript
const [interactionCounts, setInteractionCounts] = useState({
  upvotes,
  downvotes,
  flags,
});

const handleUpvote = async () => {
  const newCounts = { ...interactionCounts };
  if (userInteraction?.vote === "upvote") {
    newCounts.upvotes -= 1;
  } else {
    newCounts.upvotes += 1;
    if (userInteraction?.vote === "downvote") {
      newCounts.downvotes -= 1;
    }
  }
  setInteractionCounts(newCounts);
  await updateInteraction(postId, "upvote");
};
```
Categorization and Tagging System

Hierarchical Categories: Templates are associated with both immediate and parent categories for flexible querying.
Tag Categories: A separate schema manages tag categories, allowing for organized and searchable tag collections.

```javascript
const tagCategorySchema = new Schema({
  name: { type: String, required: true },
  tags: [{ type: String, required: true }],
});
```
#### Sorting and Filtering Implementation

Server-side Sorting: The API supports sorting templates based on various criteria (e.g., upvotes, creation date).
Pagination: Implemented to manage large numbers of templates efficiently.
Category-based Filtering: Templates can be filtered by category, including subcategories.

```javascript
app.get("/api/templates", async (req, res) => {
  try {
    const { categoryID, sort, page, limit = 12 } = req.query;
    const skip = (page - 1) * limit;
    let query = {};
    if (categoryID) {
      query = {
        $or: [{ categories: categoryID }, { parentCategories: categoryID }],
      };
    }

    const templates = await Template.find(query)
      .sort({ [sort]: -1 })
      .skip(skip)
      .limit(Number(limit));
    res.json(templates);
  } catch (error) {
    console.error("Error fetching templates:", error);
    res.status(500).json({ error: error.message });
  }
});
```
#### UI Components and Interaction

Template Post Card: A custom React component (TemplatePostCard) displays template information in a visually appealing, responsive, and interactive card format.
Modal View: Clicking on a template opens a detailed modal view (PostTemplate) for a comprehensive look at the template.
Category Navigation: The CategoryPage component provides an intuitive interface for browsing templates within specific categories.

```jsx
const CategoryPage = () => {
  // ... (other code)

  return (
    <div className="flex flex-col items-center mb-2">
      <div className="p-8">
        <h1 className="text-5xl font-bold mb-4">{categoryData.name}</h1>
      </div>
      <div className="pb-10"></div>
      <div className="flex flex-col">
        <div className="w-full px-8">
          <div className="container mx-auto">
            <div className={`grid ${gridClass}`}>
              {renderSubcategories(categoryData.children)}
            </div>
          </div>
        </div>
        {/* ... (other UI elements) */}
        <div className="w-full px-8 pb-12">
          <div className="container mx-auto">
            <div className="grid md:grid-cols-1 lg:grid-cols-2 gap-4">
              {templates.map((template, index) => (
                <TemplatePostCard
                  key={index}
                  {...template}
                  template={template.template}
                  postId={template._id}
                />
              ))}
            </div>
          </div>
        </div>
      </div>
      <Pagination currentPage={currentPage} setCurrentPage={setCurrentPage} />
    </div>
  );
};
```

This comprehensive template gallery system provides users with a powerful tool for discovering, sharing, and interacting with prompt templates, significantly enhancing the overall functionality and user experience of EchoPDF. The implementation showcases the use of React for dynamic UI rendering, state management for real-time interactions, and efficient backend querying for template retrieval and filtering.

### 6.3 Subscription Management
EchoPDF's subscription management system is a core component that seamlessly integrates with Stripe for payment processing and user tier management. This system is designed to handle various subscription scenarios, from free tier users to premium subscribers, while also incorporating a flexible credit purchase system for advanced features.
At the heart of the subscription management is the User model, which includes detailed fields for tracking subscription status, tier, credit balance, and payment history. This comprehensive data model allows for granular control over user permissions and feature access based on their subscription status.
The system employs a robust middleware check to ensure that user tiers are always up-to-date:
```javascript
const checkSubscription = async (req, res, next) => {
  const user = await User.findOne({ clerkUserId: req.auth.userId });
  if (user.tier !== "free" && !user.isSubscriptionActive()) {
    user.tier = "free";
    await user.save();
    console.log(
      `User ${user.clerkUserId} downgraded to free tier due to inactive subscription`
    );
  }
  next();
};
```

This middleware automatically downgrades users to the free tier if their subscription becomes inactive, ensuring that access to premium features is properly restricted.
The Subscription Manager component provides users with a comprehensive interface to manage their subscription. For subscribed users, it displays current subscription details, including the plan name, status, and next billing date. Users can cancel their current subscription directly from this interface. The system also handles subscription changes, allowing users to upgrade or downgrade their plan.

On the pricing page, the system dynamically adjusts the display and functionality of plan buttons based on the user's current subscription status. For instance, the button for the user's current plan is disabled to prevent unnecessary repurchases. Other plan buttons are labeled "Change to this Plan," enabling users to switch their subscription. This change isn't immediate; instead, it schedules the switch to occur at the end of the current billing cycle. Users also have the option to cancel this scheduled switch if they change their mind before it takes effect.
The backend of the subscription system is built around Stripe's webhook system, allowing real-time updates to user subscriptions. The webhook handler processes various events such as subscription creation, updates, cancellations, and successful payments. Here's an example of how the system handles a subscription update:

```javascript
async function handleSubscriptionUpdated(subscription) {
  const user = await User.findOne({ stripeCustomerId: subscription.customer });
  if (!user) return;

  const subscriptionItem = subscription.items.data[0];
  const newTier = mapPriceIdToTier(subscriptionItem.price.id);
  const planName = mapPriceIdToName(subscriptionItem.price.id);

  user.subscription = {
    status: subscription.status,
    stripeSubscriptionId: subscription.id,
    currentPeriodEnd: new Date(subscription.current_period_end * 1000),
    stripePriceId: subscriptionItem.price.id,
    planName: planName,
  };

  user.tier = newTier;
  await user.save();

  logSubscriptionUpdated(user.id, subscription, newTier, user.tier, planName);
  updateUserSubscriptionHistory(user, "SUBSCRIPTION_UPDATED", {
    newTier: newTier,
    oldTier: user.tier,
    planName: planName,
    endDate: user.subscription.currentPeriodEnd,
  });
}
```

This function updates the user's subscription details, adjusts their tier, and logs the change for tracking purposes.
The credit system is integrated into the subscription management, allowing users with active subscriptions to purchase additional credits for advanced features. The system offers tiered credit packages with bonus credits for larger purchases, incentivizing users to buy in bulk.

Overall, EchoPDF's subscription management system demonstrates a careful approach to handling user subscriptions, integrating seamlessly with Stripe for payment processing, and managing a flexible credit system. It showcases the ability to handle complex payment scenarios, maintain detailed user subscription states, and process real-time updates through webhooks, all while providing a user-friendly interface for subscription management.

### 6.4 Document Management
EchoPDF's document management system is a core component of the application, handling PDF uploads, storage, and organization. This system is designed with scalability, security, and user experience in mind, while implementing tiered access controls.

PDF Upload Process and Progress Tracking

The upload process utilizes Multer for handling multipart/form-data and implements real-time progress tracking:

```javascript
const upload = multer({
  storage: multer.memoryStorage(),
  fileFilter: (req, file, cb) => {
    if (file.mimetype === "application/pdf") {
      cb(null, true);
    } else {
      cb(new multer.MulterError("LIMIT_UNEXPECTED_FILE"), false);
    }
  },
  limits: { fileSize: 100 * 1024 * 1024, files: 1 }, // 100 MB file size limit
});
```
Real-time progress tracking is implemented using Server-Sent Events (SSE):
```javascript
app.get("/progress", (req, res) => {
  res.writeHead(200, {
    "Content-Type": "text/event-stream",
    "Cache-Control": "no-cache",
    Connection: "keep-alive",
  });
  clients.push(res);
  req.on("close", () => {
    clients = clients.filter(client => client !== res);
  });
});

const sendProgress = (fileId, progress) => {
  clients.forEach(client => {
    client.write(`data: ${JSON.stringify({ fileId, progress })}\n\n`);
  });
};
```

#### Tiered Upload Limits

EchoPDF implements a simple tiered system with different upload limits for each subscription level:
```javascript
const tierLimits = {
  free: {
    totalPages: 200,
    perFilePages: Infinity,
    size: 10 * 1024 * 1024,
    maxFiles: 50,
  },
  echoplus: {
    totalPages: Infinity,
    perFilePages: 550,
    size: 50 * 1024 * 1024,
    maxFiles: 100,
  },
  echopro: {
    totalPages: Infinity,
    perFilePages: 800,
    size: 70 * 1024 * 1024,
    maxFiles: 200,
  },
};
```

#### Middleware Checks for Upload Limits and File Validation

A custom middleware uploadTierCheckMiddleware enforces these limits:
```javascript
const uploadTierCheckMiddleware = async (req, res, next) => {
  const user = await User.findOne({ clerkUserId: req.auth.userId });
  if (!user) {
    return res.status(404).json({
      errorType: "USER_NOT_FOUND",
      message: "User authentication error. Please try logging out and back in.",
    });
  }

  const limit = tierLimits[user.tier];
  const tierName = tierDisplayNames[user.tier];

  // Check max files upload limit
  if (user.usage.filesUploaded >= limit.maxFiles) {
    return res.status(403).json({
      errorType: "TIER_MAX_FILES_EXCEEDED",
      message: `You've reached the maximum number of file space for your ${tierName} tier. Please delete existing PDF files to make space for new uploads.`,
      currentFiles: user.usage.filesUploaded,
      limit: limit.maxFiles,
      upgradeRequired: user.tier !== "echopro",
    });
  }

  // Additional checks for file size, page count, and total pages...

  req.user = user;
  req.pageCount = pageCount;
  next();
};
```

#### AWS S3 Integration for Secure File Storage

Files are securely stored in AWS S3, with progress tracking:

```javascript
const managedUpload = s3.upload(uploadParams);

managedUpload.on("httpUploadProgress", progress => {
  const progressPercentage = Math.round((progress.loaded / progress.total) * 100);
  sendProgress(uuid, progressPercentage);
});

const uploadResult = await managedUpload.promise();
```

#### Database Integration

After successful S3 upload, file metadata is stored in MongoDB:

```javascript
const pdfFile = new PdfFile({
  uuid: uuid,
  name: stripPdfExtension(file.originalname),
  folderId: new mongoose.Types.ObjectId(folderId),
  userId: userId,
  s3Url: uploadResult.Location,
  key: `${userId}/${uuid}`,
  fileSize: file.size,
});

await pdfFile.save();
```

#### Folder Structure Implementation

A MongoDB schema defines the folder structure:
```javascript
const folderSchema = new Schema({
  name: { type: String, required: true },
  parentId: { type: Schema.Types.ObjectId, ref: "Folder", default: null },
  userId: { type: String, required: true },
  createdAt: { type: Date, default: Date.now },
  openedAt: { type: Date, default: Date.now },
});
folderSchema.index({ userId: 1, parentId: 1 });
```

#### User Interface for Document Management

The DisplayFileList component provides a user-friendly interface for managing uploaded files:
```jsx
const DisplayFileList = ({ files, setFiles, selectedFiles, setSelectedFiles, folders, currentFolder }) => {
  // ... component logic

  return (
    <div className="overflow-x-auto flex-grow select-none">
      <table className="min-w-full h-full">
        <thead>
          {/* ... table headers */}
        </thead>
        <tbody>
          {sortedFiles.map(file => (
            <tr key={file._id} className={`relative ${selectedFiles.includes(file._id) ? "bg-gray-200" : ""} group hover:bg-background-light`}>
              {/* ... file row content */}
            </tr>
          ))}
        </tbody>
      </table>
      {/* ... modals for delete and move actions */}
    </div>
  );
};
```

#### Security Measures

Files are stored in S3 with user-specific prefixes: ${userId}/${uuid}
Clerk authentication ensures users can only access their own files
Custom middleware validates user permissions for each file operation

#### Performance Optimizations
1. Asynchronous Operations
EchoPDF utilizes asynchronous programming extensively throughout the upload process, which is needed for maintaining application responsiveness:
```javascript
app.post("/api/upload-pdf-to-s3", upload.single("file"), async (req, res) => {
  try {
    // Asynchronous operations
    await req.user.updateFileUploadUsage(req.pageCount);
    const uploadResult = await managedUpload.promise();
    await pdfFile.save();
    // ...
  } catch (err) {
    // Error handling
  }
});
```
This approach prevents long-running operations from blocking the event loop, allowing the server to handle multiple requests concurrently.
2. Streaming Uploads
Instead of loading entire files into memory, EchoPDF implements streaming uploads to S3:
javascriptCopyconst managedUpload = s3.upload(uploadParams);
managedUpload.on("httpUploadProgress", progress => {
  const progressPercentage = Math.round((progress.loaded / progress.total) * 100);
  sendProgress(uuid, progressPercentage);
});
This method is more memory-efficient, especially for large files, as it doesn't require the entire file to be buffered in memory before uploading.
3. Efficient Database Queries
EchoPDF implements indexing on the folder schema to optimize database queries:
javascriptCopyfolderSchema.index({ userId: 1, parentId: 1 });
This compound index allows for faster queries when retrieving folders for a specific user and parent folder, which is a common operation in the folder structure.
4. Middleware Chain Optimization
The middleware chain is structured to fail fast. For example, the checkPdfProtection middleware runs before more intensive operations:
```javascript
app.post(
  "/api/upload-pdf-to-s3",
  upload.single("file"),
  checkPdfProtection,
  ClerkExpressRequireAuth(),
  checkSubscription,
  uploadTierCheckMiddleware,
  async (req, res) => {
    // ...
  }
);
```
This order ensures that invalid requests are rejected early in the process, saving server resources.


This document management system forms a critical part of EchoPDF, showcasing the integration of various technologies (MongoDB, AWS S3, Multer) while addressing important aspects such as security, performance, and user experience. The tiered upload system demonstrates a well rounded approach to user management and resource allocation, crucial for a SaaS product like EchoPDF.
