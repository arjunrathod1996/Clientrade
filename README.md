# Clientrade
RevitalizeCRM: Empowering businesses with a comprehensive Retail CRM and Customer Engagement platform. Seamlessly enhance online and offline interactions to capture the complete customer journey. (Currently in development to include offline interactions.) Continuously evolving to deliver excellence.

# Role Hierarchy:
![Slide 1 of Presentation1](https://github.com/arjunrathod1996/Clientrade/assets/110610821/5829bc6b-f897-401f-9da0-28db137401d2)

# Merchant Admins:
- An admin can create multiple merchant admins within each business.
- Each merchant admin has authority over a specific aspect or category within the business, such as food, electronics, etc.
- Merchant admins can create items/products within their assigned category.

# Merchant Staff:
- Merchant admins can manage multiple merchant staff members within their category.
- Merchant staff members work under a specific merchant admin and are responsible for day-to-day operations.
- Each staff member may be assigned to a specific location or area within the business.

# Example Scenario:
- Business: Restaurant
- Admin creates Merchant Admin 1 (Food) for managing food-related items.
- Merchant Admin 1 creates items/products for different food categories (e.g., appetizers, main courses, desserts).
- Merchant Admin 1 assigns Merchant Staff 1 to handle orders and operations in one location (e.g., Bansankari) and Merchant Staff 2 for another location (e.g., BTM).
- Each Merchant Staff member manages orders and ensures smooth operations within their assigned location.

# JWTAuthFilter Class:
- This class extends OncePerRequestFilter, which ensures that the filter is only applied once per request.
- It intercepts incoming requests and performs JWT authentication.
- It extracts the JWT token from the request and validates it.
- If the token is valid, it sets the authentication in the SecurityContextHolder.
- If the token is not valid, it logs a warning.
- It also has a method to check if the given username is an email or phone number.
- The extractTokenFromRequest method extracts the JWT token from the request cookies.

# SecurityConfig Class:
- This class is annotated with @Configuration and @EnableWebSecurity, indicating that it defines security configurations for the web application.
- It configures authentication and authorization settings.
- It defines beans for various security-related components such as PasswordEncoder, DaoAuthenticationProvider, AuthenticationManager, etc.
- It configures HTTP security rules using HttpSecurity.
- It sets up CORS, CSRF protection, and session management.
- It configures URL-based access control using .authorizeRequests().
- It defines exception handling for authentication and access denied cases.
- It adds JWTAuthFilter before UsernamePasswordAuthenticationFilter in the filter chain.
- It defines success and failure handlers for OAuth2 authentication.

# OAuthenticationSuccessHandler Class:
- This class handles successful OAuth2 authentication.
- It retrieves user information from the OAuth2 principal and determines the provider.
- It extracts user details such as email, first name, last name from the OAuth2 principal.
- It saves the customer if not already existing and creates a new user.
- It generates a JWT token for the authenticated user and sets it in the response cookie.
- It redirects the user to the access page after successful authentication.

# UsersVerification Class:
- This class represents the entity for storing user verification information.
- It defines enums for status and content type.
- It has fields for user, content, verification code, and status.
- It sets creation time and update time before persisting.

# Controller Methods:
- These methods handle HTTP POST requests for generating and verifying OTP.
- The authenticateAndGetGeneratedOtp method generates a random 4-digit OTP, retrieves the user by mobile number, and saves the OTP in the database.
- The generateOTP method generates a random OTP and Automatically Taken OTP field.
- The verifyOtp method verifies the OTP entered by the user, generates a JWT token for the user, and sets it in the response cookie. Finally, it redirects the user to the access page.
  
## Screenshots

### Home
![AboutContactUsServices](https://github.com/arjunrathod1996/Clientrade/assets/110610821/8b94fb05-6773-4564-955e-961263690046)

### Admin Login Page
![AdminLogin](https://github.com/arjunrathod1996/Clientrade/assets/110610821/2afb152d-89f0-4b8d-bbd2-736dadd5a38d)

### Dashboard [Same Dashboard All Roles but Here We can show Counts , Graph Example : Customer daily count, Lead Count, Transaction Count etc with respect to role wise...]
![Dashboard](https://github.com/arjunrathod1996/Clientrade/assets/110610821/d0bcef8b-25d4-4e25-9e5a-7799afe9c67e)

### Create and Edit Form [Similary For other Forms we can do like this]
![Untitled](https://github.com/arjunrathod1996/Clientrade/assets/110610821/ba69c32b-b9a2-4659-a34f-5f0fca6d178c)

### Create and Edit Form [Merchant Admin and Merchant Staff Table]
![Merchant andt Merchant Staff Table](https://github.com/arjunrathod1996/Clientrade/assets/110610821/25d17627-aadf-46f9-8917-115cccedb22e)


