# Event Manager

## GitHub Repo Link

`https://github.com/varshith-29/event_manager`

## Issues

- ### Nickname issue while user registration
    Description: The nickname provided in the payload is not used and saved in the database while user registration rather a new nickname is generated on the backend and is saved in the database

    Fix Method: Updated the UserBase schema to not include nickname since it is auto generated on the backend and returned to user after user registration
    Files Added/Changed:
        - (app/routers/user_routes.py)
    Issue URL: `https://github.com/varshith-29/event_manager/issues/1`
    Pull Request: `https://github.com/varshith-29/event_manager/pull/2`

- ### No password validation implemented
    Description: During testing I was able to register a user with a very simple password of 12345678 which shouldn't be allowed from a security stand point

    Fix Method: Added Password Validation - Password must be 8-24 characters long and contain uppercase, lowercase, numbers, and special characters
    Files Added/Changed: 
        - (app/routers/user_routes.py)
        - (app/schemas/user_schemas.py)
        - (app/utils/password_validation.py)
    Issue URL: `https://github.com/varshith-29/event_manager/issues/3`
    Pull Request: `https://github.com/varshith-29/event_manager/pull/4`

- ### Nickname is not consistent in schema
    Description: The nickname is not consistent in user schema. For UserUpdate, UserListResponse and UserResponse the nickname is either hard-coded or generated using function at runtime which shouldn't be the case.

    Fix Method: Fixed the inconsistency in the user schema for user's nickname for better testing environment
    Files Added/Changed: 
        - (app/schemas/user_schemas.py)
    Issue URL: `https://github.com/varshith-29/event_manager/issues/5`
    Pull Request: `https://github.com/varshith-29/event_manager/pull/6`

- ### Test data is incorrect at some place
    Description: In conftest the data is schema is incorrect as username is being considered but the actual schema has not field named username. It was causing test cases to fail.

    Fix Method: Replaced username with nickname and also updated user id as well
    Files Added/Changed: 
        - (tests/conftest.py)
    Issue URL: `https://github.com/varshith-29/event_manager/issues/7`
    Pull Request: `https://github.com/varshith-29/event_manager/pull/8`

## DockerHub Project Image 


## What I have learned
