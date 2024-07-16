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
