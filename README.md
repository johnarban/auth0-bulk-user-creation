# Auth0 Bulk User Creation

This repository contains a Jupyter Notebook designed to help you bulk create users in Auth0 using the Management API. The notebook demonstrates how to generate user data, hash passwords, and interact with Auth0's API to import users in bulk.

## Prerequisites

1. **Auth0 Account**: Ensure you have an Auth0 account and access to the Management API.
2. **API Access Token**: Obtain a Management API access token. Follow the [Auth0 documentation](https://auth0.com/docs/secure/tokens/access-tokens/management-api-access-tokens) to generate a token. For development, you can use the `API Explorer` token from the Auth0 dashboard.
3. **Dependencies**: Hashing functions are provided throught the `bcrypt` and `hashlib` libraries. Ensure you have these installed in your Python environment.

## How to Use

1. **Set Up Environment Variables**:
 - Open the notebook and set the `DOMAIN` and `MGMT_API_ACCESS_TOKEN` variables in the designated cell.
   - `DOMAIN` is your Auth0 domain (e.g., `dev-xxxx.us.auth0.com`).
   - `MGMT_API_ACCESS_TOKEN` is the token you generated earlier.

2. **Generate User Data**:
 - Be sure to set the `PREFIX` and `email_domain` variables to customize the user data generation.
   - Usernames will be generated in format `prefix_01`, etc
   - Emails will be assigned as `prefix_01@email_domain`, etc

## Key Notebook Sections

- **Password Hashing**: Demonstrates how to hash passwords using bcrypt, as recommended by Auth0.
- **User Data Generation**: Shows how to create user data in the required JSON format.
- **Auth0 API Interaction**: Includes functions to interact with the Auth0 Management API for tasks like retrieving connection IDs and starting import jobs.

## References

- [Bulk User Imports](https://auth0.com/docs/manage-users/user-migration/bulk-user-imports)
- [Create User Import Job](https://auth0.com/docs/api/management/v2/jobs/post-users-imports)
- [Management API Access Tokens](https://auth0.com/docs/secure/tokens/access-tokens/management-api-access-tokens)

## Notes

- The `API Explorer` token expires in 24 hours and has full access. Do not share this token publicly.
- For production use, consider implementing a more secure method to manage API tokens.