# Hive_Server

**Hive_Server** is a general-purpose backend server designed to manage requests for the Hive ecosystem. Built using **Python Flask**, it handles tasks such as video uploads, queue management, user authentication, and profile picture generation. The server integrates with AWS services and **Supabase** for efficient processing and storage.

---

## Features

### 1. **Request and Queue Management**
- Handles video upload requests and places them into a processing queue managed via **Supabase**.
- In the future, the server will leverage AWS's auto-scaling capabilities to handle high traffic volumes efficiently.

### 2. **Profile Picture Generation**
- Uses **FFmpeg** to generate and compress profile pictures.
- Stores generated images in **AWS S3** for integration with user data across the Hive ecosystem.

### 3. **User Authentication**
- Implements cookie-based authentication for session management.
- Plans to migrate to **OAuth providers** for enhanced security and ease of integration with external authentication services.

### 4. **Bulk Operations**
- Supports **bulk video deletion**, simplifying content management for users.
- Future updates will expand this feature to support **batch updates**, enabling efficient edits to multiple videos simultaneously.

---

## Technology Stack

### Backend Framework
- **Python Flask**: Lightweight and flexible framework for handling API requests and server logic.

### Libraries and Tools
- **Boto3**: Used for interacting with AWS services, including S3 for storage.
- **Supabase**: Manages the processing queue and facilitates real-time updates.
- **FFmpeg**: Utilized for media manipulation, such as generating profile pictures.

---

## Deployment Plan

- The server is designed to be deployed on the **AWS ecosystem** to take advantage of:
  - **Elastic Load Balancers** for managing traffic.
  - **Auto-scaling groups** for handling variable workloads.
- Deployment will follow a containerized approach (e.g., **Docker**) for portability and scalability.

---

## Future Enhancements

### 1. **Improved Security**
- Transition to **OAuth providers** for secure and streamlined user authentication.

### 2. **Enhanced Media Management**
- Extend bulk operations to include **batch updates** for video metadata and configurations.

### 3. **Advanced Queue Management**
- Implement dynamic queue prioritization to ensure critical tasks are processed first.

---

## Getting Started

### Prerequisites
- **Python 3.9+**
- AWS credentials for S3 storage
- Supabase account and API keys

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/HiveOrg89/Hive_Server.git
   cd Hive_Server
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Configure environment variables:
   - Create a `.env` file with your AWS and Supabase credentials:
     ```env
     AWS_ACCESS_KEY_ID=your-access-key
     AWS_SECRET_ACCESS_KEY=your-secret-key
     SUPABASE_URL=your-supabase-url
     SUPABASE_KEY=your-supabase-key
     ```
4. Run the server:
   ```bash
   flask run
   ```
