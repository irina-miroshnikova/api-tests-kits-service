# API Tests for Kits Service

This repository contains automated API tests for a REST service that creates user kits.

The project demonstrates basic API testing and test automation skills using Python, pytest, and requests.

## What is tested

* Kit creation via API
* Validation of the kit `name` field
* Positive test scenarios
* Negative test scenarios
* Boundary value checks
* API response status codes
* Response body validation

## Tools and Technologies

* Python
* pytest
* requests
* Git / GitHub

## Project Structure

```text
api-tests-kits-service/
├── configuration.py              # Base URL and API paths
├── data.py                       # Test data
├── sender_stand_request.py       # API request helper functions
├── create_kit_name_kit_test.py   # Automated API tests
├── README.md                     # Project documentation
└── .gitignore                    # Ignored local and generated files
```

## How to Run Tests

Install dependencies:

```bash
pip install pytest requests
```

Run tests:

```bash
pytest
```

## QA Focus

The project focuses on checking how the API handles valid and invalid values in the kit `name` field.

The tests help verify that the API returns expected status codes and handles input validation correctly.

## Notes

This is a training QA project.

No real credentials, tokens, or confidential data are stored in this repository.
