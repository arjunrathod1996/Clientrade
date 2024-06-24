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

### JWT Token Generated
![JWT Token Generated](https://github.com/arjunrathod1996/Clientrade/assets/110610821/cb4a87d3-2609-415a-b2d5-e343bbc66fec)

### Dashboard [Same Dashboard All Roles but Here We can show Counts , Graph Example : Customer daily count, Lead Count, Transaction Count etc with respect to role wise...]
![Dashboard](https://github.com/arjunrathod1996/Clientrade/assets/110610821/d0bcef8b-25d4-4e25-9e5a-7799afe9c67e)

### Create and Edit Form [Similary For other Forms we can do like this]
![Untitled](https://github.com/arjunrathod1996/Clientrade/assets/110610821/ba69c32b-b9a2-4659-a34f-5f0fca6d178c)

### Merchant Admin and Merchant Staff Table
![Merchant andt Merchant Staff Table](https://github.com/arjunrathod1996/Clientrade/assets/110610821/25d17627-aadf-46f9-8917-115cccedb22e)

### Merchant Admin Logged In Table
![MerchantStaff](https://github.com/arjunrathod1996/Clientrade/assets/110610821/dff5a0df-cc61-4477-a873-92538580c082)

### Merchant Admin Can Assign and Edit Items/Producs For Merchant Staff with respect to categoty and different Location.
![AddAndEditItemProducts](https://github.com/arjunrathod1996/Clientrade/assets/110610821/a58b9931-e3b6-4496-a12b-0e463dbddc0d)

## After Adding or Assign All Items and Products, Now In Membership App
### Here Customer Can log in With Using Phone Number and then they can stored CUSTOMER_ROLE in database
![CustomerLoggInWithOTP](https://github.com/arjunrathod1996/Clientrade/assets/110610821/a4924e4f-3246-4dd1-9258-6aeeb8bcc2f5)

### Customer Interface After Logged In
![CustomerProfile](https://github.com/arjunrathod1996/Clientrade/assets/110610821/8255c5d1-f47b-4b4a-8611-3664891f0321)
- Here, I used the Geo Code API to fetch merchant stores based on the location of the merchant staff.
- First, we need to update the customer's first name and last name, and ensure their profile score is more than 50%. Only then can we fetch merchant stores.
  
### Merchant Stores and Activity
![CustomerMerchanMainAdminandActivity](https://github.com/arjunrathod1996/Clientrade/assets/110610821/aa244df9-baa4-406a-bb41-b267a88daf5c)
- After clicking on the respective merchant admin, we can view the merchant staff stores located in relation to the merchant admin and their category.

### Merchant Stores and Item With Respect Category and Location
![MerchantStoreWithItems](https://github.com/arjunrathod1996/Clientrade/assets/110610821/ca65ec12-853a-4082-aa92-2df1cc78892b)
- In the merchant store, we can view food items categorized by type and see the average reviews from other customers, allowing us to make informed food orders.
### Cart Item
![Added Cart Items](https://github.com/arjunrathod1996/Clientrade/assets/110610821/835f0f7c-b071-46dd-94d1-b1c23f824f02)
- Food items can be added to the cart and ordered whenever desired.
### Invoice or Purchase Item
![Invoice](https://github.com/arjunrathod1996/Clientrade/assets/110610821/38b5b9f0-3a28-4d45-9915-8e4a96a81f4d)
- When ordering, if we decide not to include a specific item or food, we can cancel it, and the updated total quantity of items will be displayed. The price will be recalculated based on the quantity, and the grand total amount will be updated accordingly.
### Purchase History
![purchase History](https://github.com/arjunrathod1996/Clientrade/assets/110610821/32512c7b-9e0d-499d-9468-d47b9b63b017)
- After completing a purchase, the cart page will be cleared. All items ordered by the customer can be tracked in the purchase history.
### Review
![Review](https://github.com/arjunrathod1996/Clientrade/assets/110610821/f69ea1c1-1f10-4ae0-9845-7784d01ad7db)
- After completing a purchase, the customer can give a review for the purchased item and update it later if needed.
### Update Profile
![update profile](https://github.com/arjunrathod1996/Clientrade/assets/110610821/a5e3ddea-16bb-4f5d-a803-6de3bffcd042)
### Refer Contact
![Refer1](https://github.com/arjunrathod1996/Clientrade/assets/110610821/ff96e323-3a2d-41ae-b338-c00ed8794db8)
![refer2](https://github.com/arjunrathod1996/Clientrade/assets/110610821/22697315-be32-4ede-a524-b26621a549f6)
- Implemented "Refer" feature in the contact manager support section.
- Users can select up to 10 contacts, similar to WhatsApp.
- Users have the flexibility to pick contacts and deselect any they choose not to refer.
- The system automatically filters out invalid and duplicate phone numbers.
- Only valid and distinct phone numbers are sent.
- Selected contacts are displayed using tagsinput.
- In the database, contacts are stored relative to the associated merchant store and the user ID of the merchant staff.
- Existing customer contacts are skipped to avoid duplication.
- The system restricts the number of successfully referred contacts to a maximum of 10.
- Displays the number of successfully referred contacts to the user. For example, if 4 contacts are selected, but only 2 of them are new and successfully referred, the system indicates that 2 contacts were successfully referred.
### Displayed Customer List in Table With Respect Merchant Staff
![MerchantStaff123](https://github.com/arjunrathod1996/Clientrade/assets/110610821/4baa5ff1-3f33-420c-b3dc-4e314d248b17)
### Dynamic Laguage Translation
![langugage](https://github.com/arjunrathod1996/Clientrade/assets/110610821/91d18bc1-42ee-46b4-8085-8400e6d71f6b)
- Implemented dynamic language support, allowing translations into Kannada and Hindi. Similar functionality can be extended to support other languages as well, ensuring accessibility for diverse user bases.

# Insight (Dashboard)
![Insight1](https://github.com/arjunrathod1996/Clientrade/assets/110610821/3ced7863-2939-44d6-9e8b-547e930117e4)
![Insight2](https://github.com/arjunrathod1996/Clientrade/assets/110610821/c8a436e6-34b5-4aee-999a-c53b0879cea1)
- The merchant admin can track the total number of customers under their management.
- Customers can be categorized based on purchased items or products.
- The system displays:
  1. Completed status counts and amounts for completed purchases.
  2. Pending status counts and amounts for pending purchases.
  3. Rejected status counts and amounts for rejected purchases.
- A 6-month bar graph visualizes the completed status counts and amounts.
- The system identifies top customers based on:
  1. The highest number of purchased items.
  2. Total spending.
- Date-wise search functionality is supported for detailed tracking and analysis.
![insight3](https://github.com/arjunrathod1996/Clientrade/assets/110610821/847d6829-932b-482e-baf7-27592a61d426)
- Clicking on a specific status count redirects the admin to the bill summary page, where they can track details with respect to individual customers.
### For Example :
![Insight4](https://github.com/arjunrathod1996/Clientrade/assets/110610821/9ee7eadd-58cb-45d6-9cce-01e0272577f5)
![Insight5](https://github.com/arjunrathod1996/Clientrade/assets/110610821/e412ab68-2ee9-4291-835f-f51b227ea980)
### Export Data in Excel Sheet and Download Invoice
![Insight6](https://github.com/arjunrathod1996/Clientrade/assets/110610821/9f271d54-f530-447e-ac71-bdc710c7bcab)
![Insight7](https://github.com/arjunrathod1996/Clientrade/assets/110610821/5af64ef2-7a58-4bd0-91ca-61e7e44567f4)
![Insight8](https://github.com/arjunrathod1996/Clientrade/assets/110610821/d493b8d9-79e0-4020-8315-355f5cda4da4)
- All data can be exported to an Excel sheet.
- To export all customer data, the admin needs to select the check box before exporting.
- To export filtered data, checking the check box is not required.
- The merchant can download invoices in PDF format.
- To download a customer invoice, the check box must be checked beforehand.
- The merchant admin can provide the relevant customer with the downloaded invoice.
### Exported Data and Invoice
![d1](https://github.com/arjunrathod1996/Clientrade/assets/110610821/5b431fc0-ab5c-46d8-958a-d31fcbf646a9)
![i1](https://github.com/arjunrathod1996/Clientrade/assets/110610821/41074c2a-d7b9-4feb-aaff-66446897aedd)

# FAQ Section Enhancement Description

### Create FAQ Section 
![faq1](https://github.com/arjunrathod1996/Clientrade/assets/110610821/8dbd0fff-16a1-4e5e-8425-2eb479001d91)
![faq2](https://github.com/arjunrathod1996/Clientrade/assets/110610821/7fd825ed-c8d3-4059-93ca-26b96b929585)
- Merchant Admin Can Create Frequenctly Asked Quesions with respect to Business For Membership App
### FAQ In Membership App
![ffff](https://github.com/arjunrathod1996/Clientrade/assets/110610821/651620aa-cee2-47b7-b127-16a85b609bb2)
In the FAQ section of the membership app, we display the most frequently asked questions related to the business. Each FAQ entry consists of a topic, multiple questions, and corresponding answers. The answers can be presented in various formats, including text, images, embedded videos, or any other multimedia format. The order of topics can be rearranged to suit the needs of the business or the preferences of the admin. When the FAQ page loads, the most popular or relevant topic is automatically expanded by default, providing users immediate access to crucial information.
## Detailed Explanation
### Topics and Questions:
  1. Each topic represents a category or subject area under which multiple questions are grouped. For example, a topic could be "Membership Plans" with questions like "What are the different membership plans?" and "How do I upgrade my plan?"
### Answers in Various Formats:
  1. Answers can be displayed as plain text, images, or embedded videos. This allows for flexibility in how information is conveyed, making it easier for users to understand complex answers.
  2. For example, an answer to a question about how to use a feature might include a step-by-step text explanation, a screenshot, and a video tutorial.
### Changing Topic Order:
  1. Merchant Admins have the ability to reorder the topics. This is useful for prioritizing the most common or important topics, ensuring that they appear at the top of the FAQ section.
### Default Open Topic:
  1. When the FAQ page loads, the system automatically opens the most relevant or frequently accessed topic by default. This provides users with immediate access to the most important information without needing to navigate through the list.
  2 The default topic can be determined based on user interaction data, such as the number of clicks or search frequency, ensuring that the most sought-after information is readily available.
### User-Friendly Interface:
  1. The FAQ section is designed to be user-friendly, with a clean and intuitive interface. Users can easily browse through topics, click on questions to reveal answers, and view multimedia content without leaving the page.
  2. The layout is responsive, ensuring a seamless experience across different devices, including desktops, tablets, and smartphones.
### Search Functionality:
  1. Users can search for specific topics or questions using a search field. This makes it easy to find relevant information quickly without browsing through all the topics.





