# Getting Started with Glific WhatsApp Bot

Follow these step-by-step instructions to set up the Glific WhatsApp bot locally for development.

## Prerequisites

1. **Node.js**: Ensure you have Node.js installed. You can download it from [Node.js official website](https://nodejs.org/).
2. **Git**: Make sure Git is installed. You can download it from [Git's official website](https://git-scm.com/).
3. **npm**: npm (Node Package Manager) is included with Node.js installation.

## Setup Instructions

### Step 1: Clone the Repository

Open your terminal (command prompt) and run the following command:
```bash
git clone https://github.com/nontechbgsid001/Suraksha-saathi.git
```

### Step 2: Navigate to the Project Directory

Change into the project directory:
```bash
cd Suraksha-saathi
```

### Step 3: Install Dependencies

Install the required dependencies using npm:
```bash
npm install
```

### Step 4: Set Up Environment Variables

Create a `.env` file in the root of the project directory and add the following required environment variables:
```bash
WHATSAPP_API_KEY=your_api_key_here
DB_CONNECTION_STRING=your_database_connection_string_here
```
Make sure to replace the placeholders with your actual API key and database connection string.

### Step 5: Start the Development Server

Run the application in development mode:
```bash
npm start
```

### Step 6: Testing the Bot

Use Postman or any API testing tool to test the WhatsApp bot endpoints.

## Conclusion

You should now have a working version of the Glific WhatsApp bot running locally. Happy coding!