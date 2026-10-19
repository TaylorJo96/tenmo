# TEnmo 💸

A peer-to-peer payment app: a secured RESTful API and a command-line client
that let users send, request and approve transfers of "TE Bucks."

Built as the Module 2 capstone at Tech Elevator (2022) by a team of 3.

**Tech:** C# · ASP.NET Core 3.1 Web API · SQL Server · ADO.NET (DAO pattern) ·
JWT authentication · RestSharp · .NET console client

## Features
- Register and log in; new accounts start with 1,000 TE Bucks
- Check your balance
- Send TE Bucks to another user (with balance validation)
- Request TE Bucks; approve or deny pending requests
- View transfer history and details for any transfer

All 9 use cases, including the optional request/approve flow, are implemented.

## My role
I worked across the full stack with my team: API controllers, data access
layer, SQL Server database, and the console client.

## Architecture
- **TenmoServer:** ASP.NET Core Web API with JWT-protected endpoints for accounts, users and transfers
- **TenmoClient:** console app that calls the API via RestSharp
- **database:** SQL Server schema ([ERD](img/Tenmo_erd.png))

## Running locally
Requires SQL Server Express and the .NET Core 3.1 SDK.

1. Run [`database/tenmo.sql`](database/tenmo.sql) against SQL Server Express
2. Trust the .NET HTTPS development certificate (one-time): `dotnet dev-certs https --trust`
3. Start the API: `cd TenmoServer && dotnet run`
4. In a second terminal, start the client: `cd TenmoClient && dotnet run`
5. Register a user, then log in

The original Tech Elevator assignment is in [ASSIGNMENT.md](ASSIGNMENT.md).
