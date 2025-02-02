# Magic Eight Ball Vue Application

This is a Magic Eight Ball application built with Vue.js. The application allows users to ask questions and receive answers in either a classic or sassy style. The backend API is hosted on AWS using Lambda and API Gateway.

### Features

- Ask questions and get answers in two styles: Classic and Sassy
- Responsive design
- Hosted on AWS using ECS and ALB

### Prerequisites

- Node.js (version 16 or later)
- npm or yarn
- Docker (for containerization)
- AWS CLI (for deploying to AWS)

## Getting Started

### Clone the Repository

```sh
git clone https://github.com/yourusername/magic_eight_vue.git
cd magic_eight_vue
```

### Install Dependencies
```sh 
npm install
```

### Environment Variables
Create a .env file in the root of the project and add the following:

```sh
VITE_API_BASE_URL=https://wlqzjnzakh.execute-api.us-east-2.amazonaws.com/dev
```

### Run the Application

```sh
npm run dev
```
Open your browser and navigate to http://localhost:5173.


## Building and Running with Docker
### Build the Docker Image
```sh
docker build -t magic-eight-ball-app .
```
### Run the Docker Container
```sh
docker run -p 5000:5000 magic-eight-ball-app
```


## Deploying to AWS
### Create an ECR Repository
```sh
aws ecr create-repository --repository-name magic-eight-ball-app
```
### Authenticate Docker to ECR
```sh
aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin <your-account-id>.dkr.ecr.us-east-2.amazonaws.com
```
### Tag and Push the Docker Image
```sh
docker tag magic-eight-ball-app:latest <your-account-id>.dkr.ecr.us-east-2.amazonaws.com/magic-eight-ball-app:latest
docker push <your-account-id>.dkr.ecr.us-east-2.amazonaws.com/magic-eight-ball-app:latest
```

## License
This project is licensed under the MIT License. See the LICENSE file for details.