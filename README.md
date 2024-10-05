# Peniel Veículos Dealership Website

This repository hosts the source code for the Peniel Veículos dealership website. The platform is powered by Server-Side Rendering (SSR) and utilizes data managed by the Peniel Veículos DMS (Dealership Management System) as the authoritative source for vehicle inventory, ensuring that the website always reflects up-to-date information. Built with technologies like Golang, Fiber, templ, htmx, Tailwind CSS, Amazon S3 and Amazon DynamoDB, it delivers robust performance and a responsive, user-friendly interface while supporting key dealership website functionalities.

## Overview

The Peniel Veículos website is a monolithic application designed for simplicity, reliability, and high performance. Its architecture is built as a unified system rather than a microservice or micro-monolith structure, prioritizing ease of development and maintenance. Despite its monolithic nature, it supports horizontal scaling to accommodate increased traffic, ensuring a consistent and stable user experience even as demand grows.

### Core Features

The platform is designed to support the core functions of a modern dealership website, including:

- **Car Listing and Search**: Displays the dealership's available inventory with advanced filter options including model, brand, price, body type and color.
- **Car Details Page**: Provides detailed information on each vehicle, including specifications, photos and pricing.
- **Contact Form**: Facilitates direct communication between potential customers and the dealership.
- **Form for Submitting a Financial Quote**: Allows users to request a personalized financing quote for a particular vehicle.
- **Vehicle Submission Form**: Enables users to send vehicle information to the dealership, making it easy to put their car up for sale.
- **Featured and Highlighted Vehicles**: Showcases select vehicles to promote special offers and high-demand models.
- **Responsive Design**: Ensures an optimized browsing experience across various devices and screen sizes.

### Platform Enhancements

To support these features, the platform includes several enhancements for a fully-featured dealership website, focusing on:

- **Security:** Implemented with advanced security measures to protect sensitive data and prevent vulnerabilities.
- **Performance & Reliability:** Optimized for rapid response times and built to withstand high traffic demands.
- **Scalability:** Architected to easily scale both horizontally and vertically, ensuring future growth.
- **Extensibility:** Designed for seamless integration of new features.
- **Maintainability:** Structured for easy upkeep with clean, well-documented code.
- **Quality:** Developed with strict testing and quality assurance protocols.
- **Accessibility:** Compliant with web accessibility standards (e.g., WCAG) to ensure usability for all users.
- **Innovation:** Leveraging the latest technologies and industry best practices for a modern solution.
- **Sustainability:** Implemented with features that minimize environmental impact and promote social responsibility.

Together, these features ensure that the Peniel Veículos platform is well-equipped to handle the evolving needs of a modern car dealership, delivering a reliable, secure, and engaging user experience.

## Technology Stack

The website utilizes a modern technology stack to deliver a superior user experience.

**Backend Development**:

- **Go (Golang):** A highly efficient and reliable programming language for building robust server-side applications [See more...](https://go.dev).
- **Fiber:** An ultrafast web framework designed for performance and flexibility [See more...](https://gofiber.io).
- **templ:** A lightweight templating engine for dynamic, server-side rendering [See more...](https://templ.guide).

**Frontend Development**:

- **htmx:** Enables dynamic, interactive elements without the complexity of traditional JavaScript frameworks [See more...](https://htmx.org).
- **Tailwind CSS:** A utility-first CSS framework for building responsive and highly customizable user interfaces [See more...](https://tailwindcss.com).

**Development Tools**:

- **Air:** Enables live reloading for a more agile and responsive development process [See more...](https://github.com/air-verse/air).
- **godotenv:** A Go library for managing environment variables, ensuring secure and flexible configuration [See more...](https://github.com/joho/godotenv).

**Storage & Data Management**:

- **Amazon DynamoDB:** A scalable, fully managed NoSQL database for high-performance data storage [See more...](https://aws.amazon.com/dynamodb).
- **Amazon S3:** Secure object storage, ideal for handling large volumes of static assets [See more...](https://aws.amazon.com/s3).

**DevOps & CI/CD**:

- **GitHub Actions:** Automates continuous integration and deployment, ensuring seamless development and delivery workflows [See more...](https://github.com/features/actions).
- **Docker/Podman:** Provides containerization for easy deployment and management of the application [See more...](https://podman.io).
- **Amazon ECS with Fargate:** A serverless container orchestration service that simplifies deployment, management and scaling of applications by eliminating the need to manage servers, offering a scalable and cost-effective hosting solution [See more...](https://aws.amazon.com/fargate).

## Development Workflow

This project employs a trunk-based branching strategy, a streamlined approach ideal for single-developer projects or small teams. By using a simple branching model, it prioritizes rapid integration, minimizes conflicts, and ensures that the `main` branch remains in a stable, deployable state at all times.

### Trunk-Based Branching Strategy

In this strategy, all development is centered around the `main` branch, minimizing the use of long-lived branches:

- **Main Branch (`main`)**: The main branch is the source of truth for the project. All changes are integrated into it frequently, ensuring that it always contains the latest stable code.
- **Short-Lived Feature Branches**: If necessary, feature branches are used for specific tasks like developing a new feature or fixing a bug. These branches are short-lived and merged back into `main` as soon as the work is completed to avoid divergence and reduce merge conflicts.

This approach makes the codebase easier to manage and helps maintain a consistent, clean history, making it ideal for small-scale projects with limited contributors.

### Conventional Commits

The project adheres to the Conventional Commits specification to maintain a consistent and meaningful commit history. This practice enforces a standardized format for commit messages, making it easier to track changes, generate changelogs, and understand the context behind each modification.

For more details on the specification and examples, see the [Conventional Commits documentation](https://www.conventionalcommits.org/en/v1.0.0/).

## Directory Structure

The Peniel Veículos Website repository is organized into several directories and files, each serving a specific purpose in the development and operation of the system. Below is a breakdown of the directory structure and key files:

### Root Directory

- **`README.md`**: Provides an overview and documentation for the project.
- **`go.mod`** and **`go.sum`**: Manage dependencies for the Go project.
- **`.gitignore`**: Specifies files and directories to be ignored by Git.
- **`.air.toml`**: Configuration file for the Air live reloading tool.
- **`Dockerfile`**: Defines the instructions for building the Docker container image to be deployed.

### `/cmd`

- **`main.go`**: The entry point for the application. This file initializes and starts the server.

## Prerequisites

- **Go (Golang)**: Ensure that Go 1.23.1 or higher is installed. You can download and install it from the [Official Website](https://golang.org/dl/).

1. Verify the installation:

    ```sh
    $ go version
    ```

2. If Go’s bin directory is not already in your PATH, add it:

    ```sh
    $ echo 'export PATH=$PATH:$(go env GOPATH)/bin' >> ~/.bashrc
    $ source ~/.bashrc
    ```

- **Air**: Air is required for live reloading during development.

1. Install Air using `go install`:

    ```sh
    $ go install github.com/air-verse/air@latest
    ```

2. Verify the installation:

    ```sh
    $ air -v
    ```

- **templ**: templ is used for server-side rendering.

1. Install TEMPL using `go install`:

    ```sh
    $ go install github.com/a-h/templ/cmd/templ@latest
    ```
   
2. Verify the installation:

    ```sh
    $ templ version
    ```
   
- **Tailwind CSS**: Tailwind CSS is required for styling the website. The steps below outline how to install the standalone version:

1. Download the executable from the [Tailwind CSS CLI GitHub Releases](https://github.com/tailwindlabs/tailwindcss/releases/latest).

2. Rename the executable to `tailwindcss` and move it to `/usr/local/bin`:

    ```sh
    $ sudo mv your-download-path/tailwindcss-os-arch /usr/local/bin/tailwindcss
    ```
   
3. Make the file executable:

    ```sh
    $ sudo chmod +x /usr/local/bin/tailwindcss
    ```

4. Verify the installation:

    ```sh
    $ tailwindcss -h
    ```

## Getting Started

- Navigate to your desired installation directory.

1. Clone the repository:

    ```sh
    $ git clone github.com/dainfoo/penielveiculos-website
    $ cd penielveiculos-website
    ```

2. Add Go module dependencies:

    ```sh
    $ go mod tidy
    ```

3. Launch the development server with live reloading:

    ```sh
    $ make dev
    ```
