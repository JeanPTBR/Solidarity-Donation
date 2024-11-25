<h1 align="center">💝 Solidarity Donation 💝</h1>

![Node.js Badge](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)
![AWS Badge](https://img.shields.io/badge/Amazon%20AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=for-the-badge&logo=javascript&logoColor=F7DF1E)
![HTML Badge](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS Badge](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![Express Badge](https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white)
![Docker Badge](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Axios Badge](https://img.shields.io/badge/Axios-5A29E4?style=for-the-badge&logo=axios&logoColor=white)

This project is based on a web system designed to register charitable entities, aiming to bring visibility and donations to them.

The system adheres to the sprint objectives by utilizing technologies such as NodeJS, Docker for containerization, and AWS (Amazon Web Services) for application deployment. The selected API for system integration is ViaCEP.

Link to the API used in the project: [ViaCEP](https://viacep.com.br/)

## 📑 Index
- [📑 Index](#-index)
- [📈 Project Status](#-project-status)
- [🎨 Layout](#-layout)
  - [Web](#web)
  - [Mobile](#mobile)
- [✨ Features](#-features)
- [🗃️ Database](#️-database)
- [⚙️ Environment Variables](#️-environment-variables)
- [📦 How to Run the Application](#-how-to-run-the-application)
- [🚀 Deployment](#-deployment)
- [💻 Technologies Used](#-technologies-used)
- [📂 Directory Structure](#-directory-structure)
- [📐 Standards Used](#-standards-used)
- [📅 Development Methodology](#-development-methodology)
- [👥 Developers](#-developers)
- [📝 License](#-license)

## 📈 Project Status
Completed ✅

## 🎨 Layout

### Web

<div style="display: flex;">
  <img alt="webPageHome" title="#webPageHome" src="./public/img/webPageHome.png" style="margin-right: 10px;">

  <img alt="webPageRegister" title="#webPageRegister" src="./public/img/webPageRegister.png">
</div>

### Mobile

<div style="display: flex;">
  <img alt="webPageHome" title="#webPageHome" src="./public/img/mobilePageHome.jpg" style="margin-right: 10px;" width="300px">

  <img alt="webPageRegister" title="#webPageRegister" src="./public/img/mobilePageRegister.jpg" width="300">
</div>

## ✨ Features
1. **Entity Registration**: Allows users to register entities by filling in basic information.
2. **Record Lookup**: Enables the retrieval of all entities registered in the system.
3. **ZIP Code Lookup**: Returns address data based on the ZIP code entered by the user.
4. **Region-Based Record Search**: Users can view registered entities near them by entering their personal ZIP code.
5. **Responsiveness**: Responsive design optimized for mobile devices.

## 🗃️ Database

MongoDB Atlas, a cloud-based NoSQL database solution, was utilized in its free version, offering 512 MB of storage. The cluster was configured in the `us-east-1` region, and the connection was established using the connection string provided by MongoDB Atlas.

To run the application locally, you must configure a MongoDB Atlas cluster to create and manage the database and obtain a connection string. Follow the instructions in the **Environment Variables** section to set up the application properly.

## ⚙️ Environment Variables

This project uses environment variables for configuration. To set up your local environment:

1. Create a file named `.env` in the project's root directory.

2. Open the `.env` file and replace the example variables with real values as per the instructions provided in the file.

| Variable         | Description                             | Example                    |
|------------------|---------------------------------------|----------------------------|
| CONNECTIONSTRING | MongoDB connection string             | `mongodb+srv://username:password@cluster0.qcya0jh.mongodb.net/Entities?retryWrites=true&w=majority` |

## 📦 How to Run the Application

**Using Docker:**

** Ensure Docker is installed and running on your machine.

** To install Docker, visit the official website: [Docker](https://www.docker.com/)

1. Clone the repository to your machine using the following terminal command:

       git clone https://github.com/JeanPTBR/Solidarity-Donation.git

3. From the root directory of the application, run the following command to build the Docker image:

        docker build -t jeanptbr/solidarity-donation .

4. Then, in the terminal:

        docker run -p 3000:3000 jeanptbr/solidarity-donation

**Without Docker:**

1. Clone the repository using the following terminal command:

       git clone https://github.com/JeanPTBR/Solidarity-Donation.git

2. Install the necessary dependencies:

        npm install

3. Run the application with the following command:

       npm start

4. Access the application at: http://localhost:3000/.

## 🚀 Deployment

**Ensure you have an AWS account before proceeding.**

The following steps were followed for deployment:

1. Create a VPC with a public subnet using the AWS console VPC wizard.

2. Create an EC2 instance with the following configurations:

    - Availability Zone: `us-east-1`
    - AMI: `Ubuntu Server 24.04 LTS (HVM), EBS General Purpose (SSD)`
    - Instance Type: `t3.micro`
    - Storage: `1x8 GiB gp3`
    - SSH Key Pair
    - Enable HTTP and HTTPS Traffic
    - Associate EC2 with the public subnet and enable public access.

3. Connect to the EC2 instance via SSH.

4. Update the server.

5. Install Docker and the image available at: **jeanptbr/solidarity-donation**

6. On the server terminal, execute:

    docker run -p 80:3000 jeanptbr/solidarity-donation

## 💻 Technologies Used
- [HTML](https://www.w3.org/html/)
- [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS)
- [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
- [NodeJS](https://nodejs.org/en)
- [Express](https://expressjs.com/)
- [Axios](https://axios-http.com/)
- [Docker](https://www.docker.com/)
- [Git](https://git-scm.com/)
- [AWS Services](https://aws.amazon.com)
- [MongoDB](https://www.mongodb.com/)

## 📂 Directory Structure

Below is the project's directory structure:

    my-project/
    │
    ├── public/                 # Static files served directly
    │   ├── css/                # CSS stylesheets
    │   ├── img/                # Images used in the application
    │   └── js/                 # Frontend JavaScript scripts
    │
    ├── src/                    # Main source code
    │   ├── controllers/        # Application logic controllers
    │   ├── models/             # Data models interacting with the database
    │   ├── views/              # Application views or templates
    │
    ├── .gitignore              # Files and directories ignored by Git
    ├── Dockerfile              # Docker configuration file
    ├── README.md               # This file
    ├── server.js               # Main application server
    ├── .env                    # Application environment variables
    └── package.json            # NodeJS packages

## 📐 Standards Used  
1. **Semantic Commits**: The project's commits follow the semantic commit pattern, ensuring clarity and standardization.  
2. **MVC Structure**: The project's architecture adheres to the Model-View-Controller (MVC) pattern, organizing and separating application responsibilities.  

## 📅 Development Methodology  
The project was developed using the Scrum methodology. It was divided into three sprints:  

- **Sprint 1**: Application development.  
- **Sprint 2**: Application enhancement, Docker containerization.  
- **Sprint 3**: EC2 creation, AWS deployment, testing.  

Daily stand-ups were conducted via Microsoft Teams to ensure alignment.  

## 👥 Developers  
- [Hugo Bessa Susini Ribeiro](https://github.com/hsusini)  
- [Jean Carlos Penha Da Conceição](https://github.com/JeanPTBR)  
- [Marcel Dupret Lopes Barbosa](https://github.com/MarcelDBarbosa)  
- [Pedro Henrique Silveira Nunes](https://github.com/PedroNunesBH)  

## 📝 License  
This project is licensed under the MIT License.  

[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg)](https://opensource.org/licenses/MIT)  
