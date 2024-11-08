Gym Management Microservices Project Documentation

Project Overview

This project aims to develop a scalable, microservice-based application to manage a gym’s member and membership information. The application consists of two microservices:

	1.	Member Service: Manages core member information such as name, age, gender, contact details, and membership status.
	2.	Membership Service: Manages membership details, including start and expiry dates, linked to each member.

Objectives

	1.	Design and implement two microservices to handle gym member and membership data.
	2.	Deploy the microservices in a local Kubernetes (Minikube) environment.
	3.	Enable inter-service communication between member_service and membership_service using REST API calls.
Microservice Components

	1.	Member Service: Handles member-related information and communicates with membership_service to fetch membership details.
	2.	Membership Service: Stores membership-related data and provides member-specific membership details to member_service upon request.

Communication Mechanism

	•	Services communicate via HTTP REST APIs.
	•	member_service interacts with membership_service to retrieve membership details based on member_id.

Part 1: Project Setup

1.	Project Directory Structure
gym_management/
├── member_service/
│   ├── member_service.py            # Flask app for member service
│   ├── models.py                    # Database models for member service
│   ├── requirements.txt             # Python dependencies for member service
│   ├── Dockerfile                   # Docker configuration for member service
│   └── venv/                        # Virtual environment for member service
├── membership_service/
│   ├── membership_service.py        # Flask app for membership service
│   ├── models.py                    # Database models for membership service
│   ├── requirements.txt             # Python dependencies for membership service
│   ├── Dockerfile                   # Docker configuration for membership service
│   └── venv/                        # Virtual environment for membership service
└── k8s_deployments/
    ├── member_service_deployment.yaml   # Kubernetes deployment file for member service
    └── membership_service_deployment.yaml # Kubernetes deployment file for membership service
