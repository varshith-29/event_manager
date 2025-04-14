# Event Manager

## GitHub Repo Link

[https://github.com/varshith-29/event_manager](https://github.com/varshith-29/event_manager)

## Issues

### 1. Nickname Issue While User Registration

- **Description:**  
  The nickname provided in the payload is not used or saved in the database during user registration. Instead, a new nickname is generated on the backend and stored.

- **Fix Method:**  
  Updated the `UserBase` schema to exclude `nickname` since it is auto-generated and returned to the user after registration.

- **Files Changed:**  
  - `app/routers/user_routes.py`

- **Issue URL:** [#1](https://github.com/varshith-29/event_manager/issues/1)  
- **Pull Request:** [#2](https://github.com/varshith-29/event_manager/pull/2)

---

### 2. No Password Validation Implemented

- **Description:**  
  It was possible to register a user with a simple password like `12345678`, which is a security risk.

- **Fix Method:**  
  Added password validation. Passwords must now be 8–24 characters long and include uppercase, lowercase, numeric, and special characters.

- **Files Changed:**  
  - `app/routers/user_routes.py`  
  - `app/schemas/user_schemas.py`  
  - `app/utils/password_validation.py`

- **Issue URL:** [#3](https://github.com/varshith-29/event_manager/issues/3)  
- **Pull Request:** [#4](https://github.com/varshith-29/event_manager/pull/4)

---

### 3. Nickname is Not Consistent in Schema

- **Description:**  
  The nickname field is inconsistently handled across schemas like `UserUpdate`, `UserListResponse`, and `UserResponse`. Sometimes it is hardcoded or generated dynamically, which impacts testability.

- **Fix Method:**  
  Fixed nickname handling across schemas to ensure consistency and improve test reliability.

- **Files Changed:**  
  - `app/schemas/user_schemas.py`

- **Issue URL:** [#5](https://github.com/varshith-29/event_manager/issues/5)  
- **Pull Request:** [#6](https://github.com/varshith-29/event_manager/pull/6)

---

### 4. Test Data is Incorrect in Some Places

- **Description:**  
  The `conftest` file referenced a `username` field which does not exist in the schema, causing test failures.

- **Fix Method:**  
  Replaced `username` with `nickname` and updated the user ID accordingly.

- **Files Changed:**  
  - `tests/conftest.py`

- **Issue URL:** [#7](https://github.com/varshith-29/event_manager/issues/7)  
- **Pull Request:** [#8](https://github.com/varshith-29/event_manager/pull/8)

---

## DockerHub Project Image

---

## What I Have Learned

Working on this project taught me the importance of maintaining consistency in API schemas and test data. Even minor mismatches can lead to failing tests and confusion, especially when dealing with user-facing fields like nicknames. I learned how to approach such issues methodically and ensure the changes made are reflected across all relevant components.

I also got hands-on experience implementing secure coding practices, like password validation, which is critical for protecting user data. Additionally, linking issues with pull requests helped me stay organized and improved traceability throughout the development process.

---