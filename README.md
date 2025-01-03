# Auth FastAPI Keycloak

This project is a template for integrating Keycloak authentication with a FastAPI application.

## Features

- User authentication with Keycloak
- Role-based access control
- Secure API endpoints
- Easy configuration

## Requirements

- Python 3.8+
- FastAPI
- Keycloak

## Setup Keycloak
Setup Keycloak using Docker:
```bash
docker run -d --name keycloak-server -p 8083:8080 -e KC_BOOTSTRAP_ADMIN_USERNAME=admin -e KC_BOOTSTRAP_ADMIN_PASSWORD=admin quay.io/keycloak/keycloak:26.0.7 start-dev
```
- Access Keycloak at `http://localhost:8083
- Create a new realm and client in Keycloak
- Create a new user and assign roles to the user


## Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/auth_fastapi_keycloak.git
    cd auth_fastapi_keycloak
    ```

2. Create a virtual environment and activate it:

    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the dependencies:

    ```bash
    poetry install
    ```

4. Configure Keycloak settings in `keycloak.py`.

## Usage

1. Run the FastAPI application:

    ```bash
    uvicorn main:app --reload
    ```

2. Access the API documentation at `http://127.0.0.1:8000/docs`.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## When to Use FastAPI Depends vs Security 
### Depends:
-  `Depends` is a general-purpose dependency injection tool in FASTAPI. It declares a dependency that endpoint needs to function, whether it's a database connection, a configuration setting, or a user authentication token.

- it is a powerful feature that allows you to define dependencies for your API endpoints. You can use Depends to perform authentication, authorization, and other tasks before executing the endpoint function.

- It is a great choice when you need to perform complex operations before executing an endpoint function. For example, you can use Depends to authenticate users, authorize access to resources, and validate input data.

### Security:
- `Security` is a specific type of dependency that deals with user authentication and authorization. It's used to protect endpoints that require a user to be logged in or have specific permissions.## Installation

However, if you only need to perform simple operations before executing an endpoint function, you can use FastAPI's request parameters instead of Depends. For example, you can use request parameters to access the request body, query parameters, and path parameters.
