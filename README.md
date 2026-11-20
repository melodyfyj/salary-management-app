# Salary Management System

A full-stack web app where an administrator manages employee accounts and salaries, and employees log in to view their own profile and salary information.

Built with **ASP.NET Core Web API (.NET 10)** and **Angular 22**.

## Demo

https://user-images.githubusercontent.com/93577252/151668965-c41279be-0bb2-40d0-a416-07bf04b7baa2.mp4

## Tech stack

| Layer | Technology |
| --- | --- |
| Back end | .NET 10, ASP.NET Core Web API, Entity Framework Core 10 |
| Database | SQL Server |
| Front end | Angular 22, TypeScript |
| API docs | Swagger (Swashbuckle) |

## Features

- **Login** with email and hashed password, with separate admin and employee access
- **Admin:** view all employees, add new employees, update salaries
- **Employee:** view personal, work, bank and salary details; update personal and bank details; change password
- Deactivated accounts cannot log in

## Project structure

```
backend/    ASP.NET Core Web API (SalaryManagement.sln)
frontend/   Angular application
```

## Getting started

### Prerequisites

- [.NET 10 SDK](https://dotnet.microsoft.com/download)
- [Node.js](https://nodejs.org/) (LTS)
- SQL Server (Express or Developer edition)
- Visual Studio 2022 or later (recommended for running the API)

### 1. Set up the database

The connection string is in `backend/SalaryManagement/appsettings.json` and uses `Server=.` with Windows authentication. If you use SQL Server Express, change it to `Server=.\SQLEXPRESS`.

Then create the database and seed sample data:

```bash
cd backend/SalaryManagement
dotnet tool restore
dotnet ef database update
```

### 2. Run the API

Open `backend/SalaryManagement.sln` in Visual Studio, select the **IIS Express** profile and press **F5**.

The API runs at `https://localhost:44392`, and Swagger opens automatically at `https://localhost:44392/swagger`.

### 3. Run the front end

```bash
cd frontend
npm install
npm start
```

Open `http://localhost:4200`. API calls are forwarded to the back end through `proxy.conf.json`.

### Demo accounts

The database is seeded with sample (fictional) employees:

| Role | Email | Password |
| --- | --- | --- |
| Admin | mich@gmail.com | 123 |
| Employee | trish@gmail.com | 123 |
