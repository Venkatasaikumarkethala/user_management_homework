# User Management System

A comprehensive user management solution with enhanced data validation, security features, and bug fixes.

## 🔍 Overview

This repository contains improvements to a user management system, focusing on:
- Enhanced data validation
- Improved security measures
- Bug fixes and performance optimizations

## 🐛 Resolved Issues

### Security Enhancements

**🔒 Issue #1: No Input Sanitization**
- Implemented proper sanitization to prevent SQL injection attacks
- [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/tree/main/app/schemas/user_schemas.py)
- [View issue](https://github.com/Venkatasaikumarkethala/user_management_homework/issues/1)

### Performance Optimizations

**⚡ Issue #2: Missing Database Indexing**
- Added indexes on frequently queried fields like email and nickname
- Improved database performance for growing user bases
- [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/tree/main/app/models/user_model.py)
- [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/issues/3)

**🔒 Issue #4: Insufficient Input Validation**
- Enhanced validation for email formats and password complexity requirements
- [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/tree/main/app/schemas/user_schemas.py)
- [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/issues/4)

**🔒 Issue #5: Improper JWT Token Validation**
- Fixed token expiration and signature verification to prevent security vulnerabilities
- [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/tree/main/app/services/jwt_service.py)
- [View issue](https://github.com/Venkatasaikumarkethala/user_management_homework/issues/5)


### Reliability Improvements

**📧 Issue #3: Improper Error Handling in Email Service**
- Added robust exception handling for email operations
- [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/tree/main/app/services/email_service.py)
- [View issue](https://github.com/Venkatasaikumarkethala/user_management_homework/issues/3)

## 🧪 Test Suite

Our comprehensive PyTest suite covers all critical features with asyncio support [View code](https://github.com/Venkatasaikumarkethala/user_management_homework/tree/main/tests/test_api/test_users_api.py).

### Authentication Tests
- Account locking after failed attempts
- Login validation with various credentials

### User Registration Tests
- Validation of user registration with proper data
- Verification processes for new accounts

### Password Management
- Password reset request functionality
- Token validation for password resets

### User Profile Management
- Profile updating capabilities
- Role management for administrators

## ✨ New Features

### Advanced User Search
Advanced User Search
I have implemented an endpoint at GET /users/search that allows administrators to perform powerful, criteria-based lookups across the user base. Using the UserSearchParams schema, clients can filter by name, email, role, verification or lock status, professional status, and creation date ranges, then sort by any field in ascending or descending order. Under the hood, the service builds dynamic SQLAlchemy queries—leveraging indexed columns for performance—and returns paginated results alongside HATEOAS links (self, first, prev, next, last) so clients can easily navigate through pages. I wrote five new tests (tests/test_search_users.py) covering edge cases such as empty results, mixed‐criteria searches, and invalid parameters, and documented the feature in features.md and system_documentation.md.

### Profile Management
To empower users and administrators with richer account control, I added two new endpoints:
	•	PUT /me/profile lets authenticated users update their profile attributes (first/last name, bio, nickname, and social links). It filters out any unauthorized fields and returns a fully HATEOAS-linked UserResponse.
	•	PUT /users/{user_id}/professional-status enables admins and managers to toggle a user’s is_professional flag. This endpoint checks role permissions, updates the database, and returns the updated user with navigational links.

I extended the test suite with five tests in tests/test_profile_management.py to verify field restrictions, self-update flows, and professional-status transitions, and updated the README and finalproject.md to reflect usage examples and configuration notes.

## 🐳 Deployment

View our Docker images on [DockerHub](https://hub.docker.com/r/venkatasaikumar200/user_management_homework/tags)
