# Finance Tracker on Two VMs

## Description
This project, Finance Tracker, is designed to help individuals efficiently manage and analyze their financial data. The program is deployed on two virtual machines (VMs), one acting as the main server and the other as a backup. Both VMs are connected to a database server. The project utilizes Microsoft Azure for cloud services, Visual Studio for development, and Nginx as a web server.

## Technologies Used
- Microsoft Azure
- Visual Studio
- Nginx
- HTML
- SQL
- JavaScript
- Python
  - Flask
  - SQLAlchemy

## Problem Statement
Many individuals struggle with maintaining their personal finances, and there is a lack of user-friendly and accessible tools for tracking income, expenses, and budget planning. Existing finance trackers are often limited to specific devices, restricting accessibility.

## Goal
The goal of Finance Tracker is to empower users to efficiently manage and analyze their financial data. By utilizing the cloud (Microsoft Azure), the project aims to provide accessibility from any device with internet connectivity, eliminating the need for desktop-only applications or physical records.

## Features
- User-friendly landing page with sign-in functionality
- Dashboard providing a snapshot of the user's recent transactions
- Transaction Page allowing users to add new transactions
- Budget page allowing users to add and update budgets

## Installation
- Install Flask, SQLAlchemy, and Nginx on both VMs.
- Configure the Flask application to connect to the database server.
- Set up Nginx to serve the Flask application.

## Usage
1. Access the landing page of the Finance Tracker application.
2. Sign in with your credentials.
3. Navigate to the dashboard to view recent transactions.
4. Use the budget page to add or update budgets.

### Project Structure:
1. **`/app`**: 
    - Contains the backend Python code for the application.
    - `main.py`: 
        - This script tests the connection to the database and prints the contents of the users table.
    - `users.py`: 
        - Implements a Flask application responsible for user management.
        - Provides endpoints for user registration, login, profile updates, and retrieving user data from the SQL Server database.
        - Dependencies: Flask, SQLAlchemy
    - `transactions.py`: 
        - Extends the user management application to handle transactions.
        - Implements endpoints for adding, updating, and retrieving transaction data.
        - Dependencies: Flask, SQLAlchemy
    - `reports.py`: 
        - Builds upon previous functionality to generate an expenses report for a specified user within a given date range.
        - Dependencies: Flask, SQLAlchemy
    - `budgets.py`: 
        - Extends the application to include functionalities for managing budgets.
        - Provides endpoints for adding, updating, and deleting budget data.
        - Dependencies: Flask, SQLAlchemy
2. **`/db`**: 
    - Contains the SQL code and database used by the application.
    - `cc_db.sql`: 
        - SQL script for creating the database schema and tables.
        - Includes tables for users, transactions, and budgets.
3. **`/webapp`**: 
    - Contains the frontend code for the application.
    - `Landing_Page.html`: 
        - Displays the sign-in page.
    - `Dashboard_Page.html`: 
        - Displays the dashboard, showing balance and recent transactions.
    - `Transaction_Page.html`: 
        - Allows users to add new transactions.
    - `Budget_Page.html`: 
        - Allows users to add/update budgets.

### Dependencies:
To run the Finance Tracker application, you'll need the following dependencies:
- Flask: A lightweight WSGI web application framework.
    - Version: 2.0.2
- SQLAlchemy: An SQL toolkit and Object-Relational Mapping (ORM) library for Python.
    - Version: 1.4.31
- PyODBC: A Python module for connecting to ODBC databases.
    - Version: 4.0.32
- Nginx: A web server that can also be used as a reverse proxy, load balancer, and HTTP cache.
    - Version: 1.21.0
- Bootstrap: A front-end framework for building responsive and mobile-first websites.
    - Version: 4.3.1

Make sure to install these dependencies before running the application to ensure smooth operation.
Here's how you can explain the process step by step:

1. **Setting Up Project Directory and Dependencies on Main VM**:
   - Opened the command line interface on the main VM.
   - Created a directory named `cc_project` using the `mkdir` command.
   - Used `pip install` to download and install Flask and SQLAlchemy within the `cc_project` directory.
   - Developed Python Flask applications within this directory and tested them to ensure functionality.
   - Added HTML files, such as `Landing_Page.html`, `Dashboard_Page.html`, `Transaction_Page.html`, and `Budget_Page.html`, to the `cc_project` directory.

2. **Configuring Static DNS on Azure Portal**:
   - Navigated to the Azure Portal and accessed the main VM.
   - Created a static DNS (Domain Name System) for the main VM to provide a stable domain name for the website.

3. **Setting Up Nginx on Main VM**:
   - Returned to the command line interface on the main VM.
   - Downloaded and installed Nginx within the main VM directory.
   - Created a directory named `/var/www/domainname-server` to store the website files that Nginx will serve.
   - Copied the HTML files and other necessary assets from the `cc_project` directory to `/var/www/domainname-server`.
   - Configured Nginx to serve the website by setting up server blocks or modifying the default configuration file to point to the website files in `/var/www/domainname-server`.

This step-by-step explanation provides a clear overview of the process involved in setting up the project directory, installing dependencies, configuring DNS, and setting up Nginx to serve the website on the main VM.

### Sources:
1. Azure Virtual Machine: Ubuntu:
    - This tutorial provides detail on how to create a Azure VM. 
    - Link [Azure VM Guide](https://learn.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-portal?tabs=ubuntu)

2. NGINX Deployment Guide for Microsoft Azure Virtual Machines:
   - These tutorial provided detailed instructions on deploying NGINX on Microsoft Azure Virtual Machines.
   - Link: [NGINX Deployment Guide](https://docs.nginx.com/nginx/deployment-guides/microsoft-azure/virtual-machines-for-nginx/)
   - Link: [NGINX Deployment Guide 2](https://jgefroh.medium.com/a-guide-to-using-nginx-for-static-websites-d96a9d034940)
   
3. Flask Guide:
   - The official Flask Guide was referenced for how to make a web application using flask.
   - Link: [Flask Guide](https://www.digitalocean.com/community/tutorials/how-to-make-a-web-application-using-flask-in-python-3)

This README outline provides a structured overview of the Finance Tracker project, including its description, technologies used, problem statement, goal, features, installation instructions, usage guidelines, files included, contribution guidelines, credits, license, and contact information. 