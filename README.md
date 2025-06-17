# SmartCare
This repository contains the source code for a project that includes the following components:

1. **.NET Core API Project**: A backend API built using .NET Core that serves as the primary source for handling all business logic and data interaction.
2. **Blazor Admin & Report Project**: A Blazor-based admin panel for managing the application and generating reports.
3. **React Web Project**: A frontend web application built using React, which communicates with the .NET Core API to display data and manage user interactions.

## Table of Contents

- [Project Overview](#project-overview)
- [Getting Started](#getting-started)
  - [Prerequisites](#prerequisites)
  - [Setting up the Environment](#setting-up-the-environment)
  - [Running the Application](#running-the-application)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Contributing](#contributing)

## Project Overview

This project is a full-stack application consisting of:

- A **.NET Core API** that serves as the backend for handling the data and business logic.
- A **Blazor Admin & Report** interface for admin management and reporting functionalities.
- A **React Web Project** that acts as the user-facing frontend application, interacting with the API.

## Getting Started

To run this project locally, follow the steps below.

### Prerequisites

Ensure you have the following installed:

1. **.NET 8 SDK**: You need .NET Core 8 or later to build and run the backend API. [Download .NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0).
   
2. **Node.js**: Required for the React project. [Install Node.js](https://nodejs.org/).

3. **Yarn** (Optional): A package manager for managing JavaScript dependencies. Install it via npm:

    ```bash
    npm install --global yarn
    ```

4. **React 18.2.0**: Ensure you are using React 18.2.0 or later for the frontend. You can install it by running:

    ```bash
    yarn add react@18.2.0 react-dom@18.2.0
    ```

5. **PostgreSQL**: This application uses PostgreSQL as the database. [Install PostgreSQL](https://www.postgresql.org/download/) or use a hosted version.

6. **Entity Framework Core**: Entity Framework Core is used for ORM (Object-Relational Mapping). Ensure you have installed the necessary packages for EF Core with PostgreSQL support. You can install the required NuGet packages:

    ```bash
    dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL --version 8.0.0
    ```

7. **Visual Studio / Visual Studio Code**:
   - **Visual Studio**: Make sure you have Visual Studio 2022 or later with the **ASP.NET Core** and **Blazor** workloads installed.
   - **Visual Studio Code**: If you prefer, you can use VS Code with the C# extension and PostgreSQL extensions.

8. **Blazor Server App**: To run the Blazor server app, you need a supported environment, such as Visual Studio with the **Blazor** workload.

### Setting up the Environment


1. **Clone the repository**:

    ```bash
    git clone https://github.com/smartcaresystems/SmartCare.git
    cd your-project-name
    ```

2. **Backend Setup** (for .NET 8 API):

    - Open the `.NET Core API` project folder (`/Api`).
    - Restore the dependencies:

      ```bash
      dotnet restore
      ```

    - Update your `appsettings.json` file to match your PostgreSQL database connection string:

      ```json
      "ConnectionStrings": {
        "DefaultConnection": "Host=localhost;Port=5432;Username=youruser;Password=yourpassword;Database=yourdatabase"
      }
      ```

    - Build and run the API:

      ```bash
      dotnet build
      dotnet run
      ```

    The API will be available at `http://localhost:5000`.

3. **Frontend Setup** (for React):

    - Open the `/React` folder.
    - Install dependencies:

      ```bash
      yarn install
      ```

    - Start the React development server:

      ```bash
      yarn start
      ```

    The React app will be available at `http://localhost:3000`.

4. **Blazor Server App Setup**:

    - Open the `/Blazor` folder in your IDE or editor.
    - Build and run the Blazor app in Visual Studio or VS Code with the **Blazor** workload.

    The Blazor admin panel will be available at `http://localhost:5001` (or the port you have set).


### Running the Application

To run the full stack application:

- Ensure the **.NET Core API** is running.
- Start the **React Web Project** and **Blazor Admin & Report** projects.
- Access the React app in your browser to interact with the system.

## Project Structure

```plaintext
SC.Business/
│
├── API/
│   ├── AuthenticationHandler/
│   ├── Controllers/
│   ├── DISALogProcessor/
│   ├── LoggingMiddleware/
│   ├── Serilogs/
│   └── Views/
│
└── Domain/
    ├── CSVMaps/
    ├── DataModelForReporting/
    ├── Dto/
    ├── Entities/
    └── Validators/

SC.Data/
│
└── Infrastructure/
    ├── Contracts/
    ├── Migrations/
    └── Repositories/

SC.Utilities/
│
└── Utilities/
    ├── Constants/
    ├── Encryptions/
    └── SMS/

SC.Admin/
│
├── Admin/
│   ├── wwwroot/
│   ├── Components/
│   ├── Helper/
│   ├── HttpServices/
│   └── Services/
│
└── Admin.Utilities/
    ├── Constants/
    ├── Domain/
    └── Encryption/

SC.Application/
│
└── App/
    ├── public/
    │   ├── assets/
    │   └── meta/
    ├── src/
    │   ├── app/
    │   ├── assets/
    │   ├── components/
    │   ├── constants/
    │   ├── data/
    │   ├── enum/
    │   ├── features/
    │   ├── hooks/
    │   ├── interface/
    │   ├── layout/
    │   ├── library/
    │   ├── meta/
    │   ├── pages/
    │   ├── routers/
    │   ├── types/
    │   ├── utilities/
    │   └── validation-models/

 SC.Report/
│
├── Application/
│   ├── Component/
│   │   ├── wwwroot/
│   │   └── ChildComponents/
│   │
│   └── WEB/
│       ├── wwwroot/
│       ├── Components/
│       ├── HttpServices/
│       ├── Reports/
│       └── Services/
│
├── Business/
│   └── Report.Domain/
│       ├── Data/
│       ├── Dto/
│       └── Entities/
│
└── Utilities/
    └── Report.Utilities/
        ├── Constants/
        ├── Encryptions/
        └── SMS/
```
## Usage

- **.NET Core API**: The API serves as the backend for the entire application, exposing endpoints that can be consumed by both the Blazor and React projects.
- **Blazor Admin & Report**: The Blazor project provides an interface for administrators to manage the system and generate reports.
- **React Web Project**: The React frontend allows users to interact with the application and consume data from the API.

## Contributing

We welcome contributions from the community! To contribute to this project:

1. **Fork the repository**: Create your own fork of the repository.
2. **Create a branch**: Create a new feature or bugfix branch from the main branch.
3. **Make changes**: Make the necessary changes or additions.
4. **Write tests** (if applicable): Write tests to ensure your code works as expected.
5. **Commit changes**: Commit your changes with descriptive commit messages.
6. **Submit a pull request**: Once your changes are ready, submit a pull request to merge them into the main repository.

Please ensure that your contributions adhere to the coding style and conventions already in place, and that they are thoroughly tested.
