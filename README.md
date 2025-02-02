# Magic Eight Ball Vue Application

This is a Magic Eight Ball application built with Vue.js. The application allows users to ask questions and receive answers in either a classic or sassy style. The backend API is hosted on AWS using Lambda and API Gateway.

## Features

- Ask questions and get answers in two styles: Classic and Sassy
- Responsive design
- Hosted on AWS using ECS and ALB

### Prerequisites

- Node.js (version 16 or later)
- npm or yarn
- Docker (for containerization)
- AWS CLI (for deploying to AWS)

# Getting Started

## Clone the Repository

```sh
git clone https://github.com/yourusername/magic_eight_vue.git
cd magic_eight_vue
```

## Install Dependencies
```sh 
npm install
```

## Environment Variables
Create a .env file in the root of the project and add the following:

```sh
VITE_API_BASE_URL=https://wlqzjnzakh.execute-api.us-east-2.amazonaws.com/dev
```

## Run the Application

```sh
npm run dev
```
Open your browser and navigate to http://localhost:5173.


