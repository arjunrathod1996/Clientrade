<img width="1363" height="676" alt="After login leads2" src="https://github.com/user-attachments/assets/12683bf7-86a5-4d57-8c06-dc378139e4f7" /><div align="center">

# 🚀 Clientrade — Full Stack CRM & Trade Platform

### *Empowering businesses with intelligent customer engagement, AI-driven insights, and enterprise-grade security*

[![Java](https://img.shields.io/badge/Java-17+-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://www.java.com/)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.x-6DB33F?style=for-the-badge&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Thymeleaf](https://img.shields.io/badge/Thymeleaf-005F0F?style=for-the-badge&logo=thymeleaf&logoColor=white)](https://www.thymeleaf.org/)
[![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Claude API](https://img.shields.io/badge/Claude_API-AI_Chatbot-8B5CF6?style=for-the-badge&logo=anthropic&logoColor=white)](https://www.anthropic.com/)
[![Bootstrap](https://img.shields.io/badge/Bootstrap-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)](https://getbootstrap.com/)

---

> **Not just another CRM.** Clientrade is a production-grade retail CRM & customer engagement platform with an integrated **Claude API AI Chatbot**, DB trigger audit trails, OTP rate limiting, 3-tier role hierarchy, JWT + OTP + OAuth2 security, and full lead lifecycle management — built entirely from scratch.

---

</div>

## 📋 Table of Contents

| # | Section |
|---|---------|
| 1 | [✨ What Makes Clientrade Different](#-what-makes-clientrade-different) |
| 2 | [🤖 AI Chatbot Assistant — Claude API](#-ai-chatbot-assistant--claude-api) |
| 3 | [🏗️ Architecture & Tech Stack](#%EF%B8%8F-architecture--tech-stack) |
| 4 | [👥 Role Hierarchy](#-role-hierarchy) |
| 5 | [🔐 Security & Authentication](#-security--authentication) |
| 6 | [📋 DB Trigger Audit Trail](#-db-trigger-audit-trail) |
| 7 | [🩺 Health Monitoring System](#-health-monitoring-system) |
| 8 | [🎯 Lead CRM — Full Lifecycle](#-lead-crm--full-lifecycle) |
| 9 | [🛒 Cart, Billing & Invoice System](#-cart-billing--invoice-system) |
| 10 | [📊 Insights Dashboard](#-insights-dashboard) |
| 11 | [🎰 Lucky Draw / Raffle System](#-lucky-draw--raffle-system) |
| 12 | [❓ FAQ System](#-faq-system) |
| 13 | [📱 PWA & Browser API Features](#-pwa--browser-api-features) |
| 14 | [🌐 Language Translation](#-language-translation) |
| 15 | [🔧 Feature Toggle System](#-feature-toggle-system) |
| 16 | [📁 Project Structure](#-project-structure) |
| 17 | [🚀 Getting Started](#-getting-started) |

---

## ✨ What Makes Clientrade Different

Most CRM demos show a basic CRUD app. Clientrade is built with production patterns:

```
✅ AI Chatbot (Claude API) — domain-scoped, context-aware, rate-limited
✅ DB-level audit trails via MySQL triggers (not application code)
✅ OTP rate limiting with 429 Too Many Requests enforcement
✅ Role-based data isolation enforced at the SQL query level
✅ JWT + OTP + OAuth2 (Google & GitHub) — all three in one system
✅ Apache POI Excel & ITextRenderer PDF — zero disk I/O, in-memory streaming
✅ Spring @Scheduled health monitoring with HTML email reports
✅ PWA: Web OTP API, Contact Picker API, Geo Code API
✅ 3-tier role hierarchy with category + location scoping
```

---

## 🤖 AI Chatbot Assistant — Claude API

> The flagship feature. Not a generic chatbot — a **CRM-aware AI assistant** that understands your live business data.

### How It Works

```
User asks: "What is the priority for QR Code & UPI Payment Setup lead?"
      ↓
AI fetches live CRM context (leads, contacts, activities from DB)
      ↓
Claude API processes domain-scoped prompt
      ↓
"Priority for QR Code & UPI Payment Setup is Critical. Entity type: LEAD."
```

### Dual AI Personalities

| State | AI Mode | Behaviour |
|-------|---------|-----------|
| **Before Login** | 🤖 AI Robo Assistant | General-purpose, available on homepage. Answers broad questions — "What is Java?", "Explain REST APIs" |
| **After Login** | 🧠 CRM AI Assistant | Domain-restricted to CRM data only. Activates with your role-scoped lead/contact/activity data |

### Domain Scoping — Out-of-Scope Rejection

```
User: "What is React?"
AI:   "I can assist only with CRM-related queries.
       Please ask about: Leads, Contacts, Activities, Follow-ups, Sales insights."
```

The system prompt is engineered to **reject** any non-CRM question and redirect politely — keeping the assistant professional and focused.

### What the CRM AI Can Answer

| Query Type | Example | AI Response |
|------------|---------|-------------|
| Lead Count | "Total leads?" | "Total leads: 2. Entity types: LEAD." |
| Lead Names | "Give me lead names" | Lists all lead names with IDs |
| Priority | "What is priority for X?" | "Priority for X is Critical. Entity type: LEAD." |
| Contacts | "Total contacts?" | "Total contacts: 4. Entity type: CONTACT." |
| Phone Numbers | "Contact names and phone numbers" | Returns full structured contact list |
| Full Details | "Name, designation, and email for all contacts" | Returns complete contact profiles |
| Activities | "Any follow-ups scheduled?" | Pulls from LeadActivity table |
| Sales Insights | "Summary of leads by status?" | Aggregated CRM intelligence |

### Screenshots

#### Before Login — AI Robo Assistant (General)
> <img width="1347" height="679" alt="Before login" src="https://github.com/user-attachments/assets/91b57917-48f4-4db5-bdb5-947e7f2316ab" />
> *Homepage general AI Robo — answers broad questions, available to all visitors*

#### After Login — CRM AI Assistant Activated
> <img width="1360" height="672" alt="After login leads" src="https://github.com/user-attachments/assets/e50347bc-bf87-4451-b565-16671fcca526" />
> *Post-login CRM AI greets user, lists its scope: Leads, Contacts, Activities, Follow-ups, Sales insights*

#### Out-of-Scope Query Rejection
> <img width="1361" height="680" alt="out scope domain" src="https://github.com/user-attachments/assets/46ca0005-8fed-47c2-857e-365c2b99ace1" />
> *Asking "What is Java?" → AI correctly rejects and redirects to CRM topics only*

#### Lead Intelligence — Count & Names
> <img width="1363" height="676" alt="After login leads2" src="https://github.com/user-attachments/assets/ad4a1965-7598-421c-96d6-76793441c44b" />
> *"Total leads?" → 2. "Give me lead names" → lists QR Code & UPI Payment Setup, New POS System Upgrade*

#### Priority Query — Real-Time DB Context
> <img width="1360" height="672" alt="After login leads" src="https://github.com/user-attachments/assets/5cb241dd-a90f-4c30-962f-d543e8bfb8b2" />
> *"Priority for QR Code & UPI Payment Setup?" → "Critical. Entity type: LEAD."*

#### Contact Intelligence — Phone Numbers
> <img width="1358" height="686" alt="After login leads4" src="https://github.com/user-attachments/assets/b2fefa05-aaec-477f-bccb-b11257a527c1" />
> *Returns full contact list with phone numbers from live database*

#### Full Contact Details — Designation + Email
> <img width="1360" height="684" alt="After login leads5" src="https://github.com/user-attachments/assets/19fff9f0-0571-4bc8-9f4a-ce19fc39ecce" />
> *Structured output: name, designation, email — all from live CRM data*

### Implementation Highlights

```java
// Domain-scoped system prompt (simplified)
String systemPrompt = """
    You are a CRM Assistant for Clientrade.
    You ONLY answer questions about: Leads, Contacts, Activities, Follow-ups, Sales Insights.
    If asked about anything else (Java, React, general topics), respond:
    "I can assist only with CRM-related queries. Please ask about: Leads, Contacts, 
     Activities, Follow-ups, Sales insights."
    
    Current user CRM context:
    %s
    """.formatted(buildCrmContext(userId));

// Rate limiting on AI endpoint
@RateLimiter(name = "aiEndpoint", fallbackMethod = "aiRateLimitFallback")
public ResponseEntity<?> askAI(@RequestBody AiRequest request) { ... }
```

---

## 🏗️ Architecture & Tech Stack

```
┌─────────────────────────────────────────────────────────────────┐
│                        CLIENTRADE PLATFORM                      │
├─────────────────────┬───────────────────────────────────────────┤
│   PRESENTATION      │  Thymeleaf + Bootstrap + Tailwind CSS     │
│   LAYER             │  AJAX / jQuery · Responsive UI · PWA      │
├─────────────────────┼───────────────────────────────────────────┤
│   SECURITY          │  Spring Security · JWTAuthFilter          │
│   LAYER             │  OAuth2 (Google/GitHub) · OTP Auth        │
│                     │  Rate Limiting · CORS / CSRF              │
├─────────────────────┼───────────────────────────────────────────┤
│   BUSINESS          │  Spring Boot · Spring MVC                 │
│   LAYER             │  @Scheduled Cron Jobs                     │
│                     │  Claude API (AI Chatbot)                  │
│                     │  JavaMailSender (Health Reports)          │
├─────────────────────┼───────────────────────────────────────────┤
│   DATA              │  Spring Data JPA · Hibernate              │
│   LAYER             │  MySQL · DB Triggers (Audit Trail)        │
│                     │  Liquibase Migrations                     │
├─────────────────────┼───────────────────────────────────────────┤
│   EXPORT            │  Apache POI (Excel .xlsx)                 │
│   LAYER             │  ITextRenderer / Flying Saucer (PDF)      │
│                     │  StreamingResponseBody (zero disk I/O)    │
└─────────────────────┴───────────────────────────────────────────┘
```

### Technology Breakdown

| Category | Technologies |
|----------|-------------|
| **Backend** | Java 17+, Spring Boot 3.x, Spring MVC, Spring Security, Hibernate / JPA |
| **Frontend** | Thymeleaf, Bootstrap, Tailwind CSS, AJAX, jQuery |
| **Database** | MySQL, Spring Data JPA, DB Triggers, Liquibase |
| **AI** | Claude API (Anthropic), Domain-scoped prompts, Rate limiting |
| **Security** | JWT, Spring Security, OAuth2 (Google, GitHub), OTP Auth, BCrypt |
| **File Export** | Apache POI (XSSFWorkbook), ITextRenderer (Flying Saucer), PDF streaming |
| **Health** | Spring @Scheduled, JavaMailSender, REST health endpoints |
| **PWA / Browser APIs** | Web OTP API, Contact Picker API, Geo Code API |
| **i18n** | Spring LocaleResolver (EN / Hindi / Kannada / Spanish) |
| **Build** | Maven, Git |

---

## 👥 Role Hierarchy

```
                        ┌─────────────┐
                        │    ADMIN    │
                        │  (Platform) │
                        └──────┬──────┘
                               │  Creates businesses + Merchant Admins
                    ┌──────────┴──────────┐
                    │                     │
             ┌──────┴──────┐       ┌──────┴──────┐
             │  MERCHANT   │       │  MERCHANT   │
             │ ADMIN (Food)│       │ADMIN (Elec.)│
             └──────┬──────┘       └──────┬──────┘
                    │ Creates staff           │
         ┌──────────┼──────────┐             │
         │          │          │             │
   ┌─────┴────┐ ┌───┴────┐ ┌──┴─────┐   ┌──┴─────┐
   │  STAFF   │ │ STAFF  │ │ STAFF  │   │ STAFF  │
   │Bansankari│ │  BTM   │ │Koramng.│   │Indiranr│
   └──────────┘ └────────┘ └────────┘   └────────┘
```

![Role Hierarchy](https://github.com/arjunrathod1996/Clientrade/assets/110610821/5829bc6b-f897-401f-9da0-28db137401d2)

### Key Isolation Rules

- **Admin** → Full platform visibility across all businesses
- **Merchant Admin** → Sees only their category (e.g., Food) within their business
- **Merchant Staff** → Sees only their assigned location data
- **Same role, different user = zero data overlap** — enforced at the **SQL query level**, not UI filtering

### Example Scenario

```
Business: Restaurant

Admin creates:
  └── Merchant Admin 1 (Food Category)
          ├── Creates food items: Appetizers, Main Courses, Desserts
          ├── Staff 1 → Bansankari location (handles orders there)
          └── Staff 2 → BTM layout location (handles orders there)
```

---

## 🔐 Security & Authentication

### Three Authentication Modes in One System

```
         ┌──────────────────────────────────────────┐
         │           LOGIN OPTIONS                   │
         ├──────────────┬───────────────┬────────────┤
         │  Phone OTP   │  Google OAuth │ GitHub     │
         │  (4-digit)   │  OAuth2       │ OAuth2     │
         └──────┬───────┴───────┬───────┴────┬───────┘
                │               │            │
                └───────────────┴────────────┘
                                │
                    ┌───────────▼───────────┐
                    │   JWT Token Generated  │
                    │   Set in HTTP Cookie   │
                    └───────────┬───────────┘
                                │
                    ┌───────────▼───────────┐
                    │   JWTAuthFilter        │
                    │   (OncePerRequestFilter│
                    │   Validates every req) │
                    └───────────────────────┘
```

### JWTAuthFilter

```java
// Extends OncePerRequestFilter — runs exactly once per request
public class JWTAuthFilter extends OncePerRequestFilter {

    @Override
    protected void doFilterInternal(HttpServletRequest request,
                                    HttpServletResponse response,
                                    FilterChain filterChain) {
        // 1. Extract JWT from cookie
        String token = extractTokenFromRequest(request);
        
        // 2. Validate token
        if (token != null && jwtService.isTokenValid(token)) {
            // 3. Set authentication in SecurityContext
            UsernamePasswordAuthenticationToken auth = ...;
            SecurityContextHolder.getContext().setAuthentication(auth);
        } else {
            log.warn("Invalid or missing JWT token");
        }
        
        filterChain.doFilter(request, response);
    }
}
```

### OAuth2 Success Handler

```java
public class OAuthenticationSuccessHandler extends SimpleUrlAuthenticationSuccessHandler {

    @Override
    public void onAuthenticationSuccess(...) {
        OAuth2User oAuth2User = (OAuth2AuthenticationToken) authentication;
        
        // Extract: email, firstName, lastName from Google/GitHub principal
        String email = oAuth2User.getAttribute("email");
        
        // Save customer if not already existing
        customerService.saveIfNotExists(email, firstName, lastName);
        
        // Generate JWT token
        String jwtToken = jwtService.generateToken(userDetails);
        
        // Set JWT in response cookie
        Cookie cookie = new Cookie("JWT_TOKEN", jwtToken);
        response.addCookie(cookie);
        
        // Redirect to access page
        response.sendRedirect("/access");
    }
}
```

### OTP Rate Limiting — 429 Protection

```java
@PostMapping("/generate-otp")
public ResponseEntity<?> generateOtp(@RequestParam String mobileNumber,
                                      HttpServletRequest request) {
    // Check rate limit: last OTP generated within 60 seconds?
    if (otpService.isRateLimited(mobileNumber)) {
        return ResponseEntity
            .status(HttpStatus.TOO_MANY_REQUESTS)    // 429
            .body("Too many requests. Please wait 60 seconds before trying again.");
    }
    
    // Generate 4-digit OTP, save to DB, send via SMS
    String otp = generateRandomOtp();
    otpService.saveOtp(mobileNumber, otp);
    smsService.send(mobileNumber, otp);
    
    return ResponseEntity.ok("OTP sent successfully.");
}
```

#### OTP Rate Limiting Screenshot
> <img width="982" height="502" alt="Too Many OTP Requested" src="https://github.com/user-attachments/assets/2b9ce638-477e-4cdd-a907-fc428e8b6099" />
> *HTTP 429 response: "Too many requests. Please wait 60 seconds before trying again."*

### Role-Based Data Isolation

```java
// ❌ WRONG — returns all data, no isolation
@Query("SELECT l FROM Lead l WHERE l.status = :status")
List<Lead> findByStatus(String status);

// ✅ RIGHT — scoped to the authenticated user's business/role
@Query("SELECT l FROM Lead l WHERE l.merchantAdmin.id = :adminId AND l.status = :status")
List<Lead> findByMerchantAdminAndStatus(Long adminId, String status);
```

#### Data Isolation Screenshot
> <img width="1364" height="684" alt="another user same role without data" src="https://github.com/user-attachments/assets/a1373f0c-6532-4d7a-9cff-1e5c4d969569" />
> *Same Merchant Admin role, different user → "No data available in table" / "No relevant CRM data found"*

### Security Config Overview

```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {
    // PasswordEncoder (BCrypt)
    // DaoAuthenticationProvider
    // AuthenticationManager
    // CORS + CSRF configuration
    // Session management (STATELESS — JWT-based)
    // URL-based access control (.authorizeHttpRequests())
    // OAuth2 login with custom success/failure handlers
    // JWTAuthFilter injected before UsernamePasswordAuthenticationFilter
    // Custom 401 / 404 error pages
}
```

---

## 📋 DB Trigger Audit Trail

> **Zero application code for auditing.** MySQL AFTER triggers capture every data change automatically.

### How It Works

```sql
-- Trigger on the `user` table (example)
DELIMITER $$

CREATE TRIGGER after_user_update
AFTER UPDATE ON user
FOR EACH ROW
BEGIN
    INSERT INTO sec.audit_log (
        table_name,
        operation_type,
        row_id,
        old_data,
        new_data,
        changed_by,
        changed_at
    ) VALUES (
        'user',
        'UPDATE',
        OLD.id,
        JSON_OBJECT('phone_number', OLD.phone_number, 'email', OLD.email, ...),
        JSON_OBJECT('phone_number', NEW.phone_number, 'email', NEW.email, ...),
        USER(),
        NOW()
    );
END$$

DELIMITER ;
```

### Audit Log Table Structure

| Column | Type | Description |
|--------|------|-------------|
| `id` | BIGINT AUTO_INCREMENT | Unique audit record ID |
| `table_name` | VARCHAR | Which table was modified |
| `operation_type` | ENUM | `INSERT` / `UPDATE` / `DELETE` |
| `row_id` | BIGINT | Primary key of the affected row |
| `old_data` | JSON | Full field values **before** the change |
| `new_data` | JSON | Full field values **after** the change |
| `changed_by` | VARCHAR | DB user or application user who made the change |
| `changed_at` | TIMESTAMP | Exact timestamp of the change |

### Triggered Tables

```
user          → All user account changes (password, phone, email)
lead          → Lead status transitions, priority changes
lead_contact  → Contact add/update/remove
lead_activity → Activity completion, follow-up updates
cart          → Cart modifications
billing       → Payment status changes
```

### Real Audit Trail Example

```
Record 1:
  table: user | op: UPDATE | row: 6
  old_data: { "phone_number": "8095075541" }
  new_data: { "phone_number": "8095075540" }
  changed_by: root@localhost

Record 2:
  table: user | op: UPDATE | row: 6
  old_data: { "phone_number": "8095075540" }
  new_data: { "phone_number": "8095075541" }
  changed_by: root@localhost
```

> Complete field-level change history. Before/after values as JSON. No application code required.

### Screenshots

#### Audit Log Record — UPDATE with Before/After Values
> ![Audit Log 1](Audit%201.JPG)
> *Full audit record: table=user, operation=UPDATE, old_data JSON, new_data JSON, changed_by*

#### Sequential Audit History — Full Trail
> ![Audit Log 2](Audit%202.JPG)
> *Multiple audit records for the same row — complete change history visible*

---

## 🩺 Health Monitoring System

> Automated multi-layer health checks with scheduled HTML email reports.

### What Gets Monitored

```
┌─────────────────────────────────────────────────────────┐
│                 HEALTH CHECK LAYERS                     │
├──────────────────────┬──────────────────────────────────┤
│  INFRASTRUCTURE      │  MySQL · Kafka · Redis           │
│                      │  Groq AI · Ollama                │
├──────────────────────┼──────────────────────────────────┤
│  BUSINESS MODULES    │  Leads API · Contacts API        │
│                      │  Activities API                   │
├──────────────────────┼──────────────────────────────────┤
│  UI AVAILABILITY     │  /home · /login endpoints        │
└──────────────────────┴──────────────────────────────────┘
```

### Scheduled Execution

```java
@Component
public class HealthCheckScheduler {

    // Runs at 10 AM, 1 PM, and 7 PM IST every day
    @Scheduled(cron = "0 0 10,13,19 * * ?", zone = "Asia/Kolkata")
    public void runScheduledHealthCheck() {
        HealthReport report = healthCheckService.runAllChecks();
        String htmlReport = reportGenerator.generateHtmlReport(report);
        
        // Email the HTML report
        emailService.sendHtmlEmail(
            "arjundargurathod@gmail.com",
            "Clientrade Health Report — " + LocalDate.now(),
            htmlReport
        );
        
        // Save to DB
        healthReportRepository.save(report);
    }

    // Nightly cleanup: delete reports older than 30 days
    @Scheduled(cron = "0 0 2 * * ?")
    public void cleanupOldReports() {
        healthReportRepository.deleteOlderThan(
            LocalDateTime.now().minusDays(30)
        );
    }
}
```

### Manual REST Endpoints

```
GET  /api/health/run       → Trigger health check immediately
GET  /api/health/latest    → Get most recent health report
GET  /api/health/history   → List past reports
```

### Each Component Tracks

- ✅ / ❌ Status (UP / DOWN)
- ⏱️ Response time in milliseconds
- 📝 Error message (if any)
- 🕐 Timestamp of check

### Screenshots

#### Health Monitoring Dashboard — Infrastructure & Business Modules
> ![Health Check 1](Healthcheck1.JPG)
> *All layers monitored: MySQL, Kafka, Redis, Groq AI, Ollama, Leads, Contacts, Activities, UI endpoints*

#### Automated HTML Email Report
> ![Health Check Email](Healthcheck2.JPG)
> *Color-coded HTML email report sent at 10 AM, 1 PM, 7 PM IST via JavaMailSender*

---

## 🎯 Lead CRM — Full Lifecycle

### Lead Status Flow

```
OPEN → INPROCESS → PROPOSAL → CLOSURE
   ↘                              ↗
        INVALID (at any stage)
```

### Data Model

```
LeadMain
├── source         (Store Visit / Enquiry / Campaign / Other)
├── category       (Industry type)
├── priority       (LOW / MEDIUM / HIGH / CRITICAL)
├── isImportant    (boolean flag)
├── status         (OPEN → INPROCESS → PROPOSAL → CLOSURE)
│
├── LeadContact[]
│   ├── name, designation
│   ├── phone, email
│   └── socialMediaLinks
│
└── LeadActivity[]
    ├── type         (CALL / EMAIL / MEETING)
    ├── status       (OPEN / COMPLETE / CANCEL)
    ├── followUpDate
    └── assignedTo   (Merchant Staff)
```

### Screenshots

#### Lead Main Table
> ![Lead Main](https://github.com/arjunrathod1996/Clientrade/assets/110610821/92652ce2-815a-435a-a5e6-9d4c1991c628)
> *Lead list with source, category, priority, importance flag — all role-scoped*

#### Lead Contact
> ![Lead Contact](https://github.com/arjunrathod1996/Clientrade/assets/110610821/4d00cccd-ffae-4c16-8354-097e80e12b59)
> *Multiple contacts per lead with designation, phone, email, social links*

#### Lead Activity
> ![Lead Activity](https://github.com/arjunrathod1996/Clientrade/assets/110610821/dece12c7-e327-4f66-8e29-968bf8650ad2)
> *Call/Email/Meeting activities with follow-up scheduling and staff assignment*

#### Assign Lead from Merchant Admin
> ![Assign Lead](https://github.com/arjunrathod1996/Clientrade/assets/110610821/e33493d6-c04c-414d-9357-a53f5a8297e9)
> *Admin assigns lead activities to merchant staff members*

---

## 🛒 Cart, Billing & Invoice System

### Billing Lifecycle

```
CART (PENDING)
      ↓
  Item confirmed
      ↓
  COMPLETED ←→ Item cancelled mid-order → quantity recalculated
      ↓
  CANCELLED (if fully cancelled)
```

### Key Features

```java
// Quantity delta recalculation on item cancel
public void cancelCartItem(Long cartItemId) {
    CartItem item = cartItemRepo.findById(cartItemId);
    Cart cart = item.getCart();
    
    // Recalculate total
    cart.setTotalItems(cart.getTotalItems() - item.getQuantity());
    cart.setGrandTotal(cart.getGrandTotal() - (item.getPrice() * item.getQuantity()));
    
    item.setStatus(ItemStatus.CANCELLED);
    cartItemRepo.save(item);
    cartRepo.save(cart);
}
```

### PDF Invoice — Zero Disk I/O

```java
// Thymeleaf template → ITextRenderer → Streamed directly to browser
@GetMapping("/invoice/{billId}/download")
public void downloadInvoice(@PathVariable Long billId, HttpServletResponse response) {
    
    BillingDTO billing = billingService.findById(billId);
    
    // Render Thymeleaf template to HTML string
    String html = templateEngine.process("invoice-template", context);
    
    // Convert HTML → PDF in memory (no temp files)
    response.setContentType("application/pdf");
    response.setHeader("Content-Disposition", "attachment; filename=invoice_" + billId + ".pdf");
    
    ITextRenderer renderer = new ITextRenderer();
    renderer.setDocumentFromString(html);
    renderer.layout();
    renderer.createPDF(response.getOutputStream());  // Stream directly
}
```

### Screenshots

> ![Cart](https://github.com/arjunrathod1996/Clientrade/assets/110610821/835f0f7c-b071-46dd-94d1-b1c23f824f02)
> *Cart with items, quantities, add/remove controls*

> ![Invoice](https://github.com/arjunrathod1996/Clientrade/assets/110610821/38b5b9f0-3a28-4d45-9915-8e4a96a81f4d)
> *Live invoice with cancelled items recalculated — grand total updates dynamically*

> ![Purchase History](https://github.com/arjunrathod1996/Clientrade/assets/110610821/32512c7b-9e0d-499d-9468-d47b9b63b017)
> *Complete purchase history per customer*

---

## 📊 Insights Dashboard

### What the Dashboard Shows

```
┌──────────────────────────────────────────────────────────────┐
│                    INSIGHTS DASHBOARD                        │
├──────────────────┬───────────────────────────────────────────┤
│  6-MONTH         │  Bar graph: completed counts + amounts    │
│  TREND           │  per month (AJAX-powered, date-filterable)│
├──────────────────┼───────────────────────────────────────────┤
│  STATUS          │  COMPLETED: count + total amount          │
│  BREAKDOWN       │  PENDING:   count + total amount          │
│                  │  CANCELLED: count + total amount          │
├──────────────────┼───────────────────────────────────────────┤
│  TOP CUSTOMERS   │  By purchase count (most frequent buyer)  │
│                  │  By total spend (highest value customer)  │
├──────────────────┼───────────────────────────────────────────┤
│  DRILL-DOWN      │  Click any status count →                 │
│                  │  Redirects to filtered bill summary page  │
└──────────────────┴───────────────────────────────────────────┘
```

### Screenshots

> ![Insight 1](https://github.com/arjunrathod1996/Clientrade/assets/110610821/3ced7863-2939-44d6-9e8b-547e930117e4)
> *6-month bar graph with completed counts and amounts*

> ![Insight 2](https://github.com/arjunrathod1996/Clientrade/assets/110610821/c8a436e6-34b5-4aee-999a-c53b0879cea1)
> *Status breakdowns + Top customers by purchase count and spend*

> ![Insight 3 — Drill Down](https://github.com/arjunrathod1996/Clientrade/assets/110610821/847d6829-932b-482e-baf7-27592a61d426)
> *Click status count → filtered bill summary page*

### Excel Export — Apache POI

```java
// Full dataset OR filtered export — styled headers, zero disk I/O
@GetMapping("/export/excel")
public void exportToExcel(@RequestParam boolean exportAll,
                           HttpServletResponse response) throws IOException {

    List<BillingDTO> data = exportAll 
        ? billingService.findAll()
        : billingService.findFiltered(filterCriteria);

    XSSFWorkbook workbook = new XSSFWorkbook();
    XSSFSheet sheet = workbook.createSheet("Billing Data");

    // Bold header row
    CellStyle headerStyle = workbook.createCellStyle();
    Font font = workbook.createFont();
    font.setBold(true);
    headerStyle.setFont(font);

    Row header = sheet.createRow(0);
    String[] columns = {"Customer", "Date", "Items", "Amount", "Status"};
    for (int i = 0; i < columns.length; i++) {
        Cell cell = header.createCell(i);
        cell.setCellValue(columns[i]);
        cell.setCellStyle(headerStyle);
    }

    // Data rows...

    response.setContentType("application/vnd.openxmlformats-officedocument.spreadsheetml.sheet");
    response.setHeader("Content-Disposition", "attachment; filename=billing_export.xlsx");
    workbook.write(response.getOutputStream());
    workbook.close();
}
```

---

## 🎰 Lucky Draw / Raffle System

### How Tickets Work

```
Ticket Format: PREFIX-DATE-SEQUENCE
Example:       CLNT-20250615-001
               CLNT-20250615-002
               CLNT-20250615-003
```

### System Components

| Component | Description |
|-----------|-------------|
| **Raffle Pot** | Container for a draw event (name, date, status) |
| **Ticket** | Auto-generated on customer purchase / entry |
| **Prize Config** | Position (1st, 2nd, 3rd), count, gift description |
| **Draw Engine** | Randomised selection from eligible tickets |
| **Spin UI** | Real-time animated spin wheel — reveals winner live |

### Screenshots

> *(Add screenshot: Raffle management page)*

> *(Add screenshot: Real-time spin UI with winner reveal)*

---

## ❓ FAQ System

### Features

```
✅ Topics + Q&A structure (topic → multiple questions → answers)
✅ Answer formats: Plain text, Image, Embedded video
✅ Topic reordering (drag and drop — admin controlled)
✅ Auto-expand: Most popular topic opens by default on page load
✅ Search: Across topic names and question text
✅ Responsive collapsible UI (works on all screen sizes)
```

### Data Structure

```
FAQTopic
├── title
├── orderIndex    (admin can reorder)
├── isDefault     (auto-expand on load)
│
└── FAQQuestion[]
    ├── questionText
    ├── answerType   (TEXT / IMAGE / VIDEO)
    └── answerContent
```

### Screenshots

> ![FAQ Admin](https://github.com/arjunrathod1996/Clientrade/assets/110610821/8dbd0fff-16a1-4e5e-8425-2eb479001d91)
> *Admin creates FAQ topics and questions with multimedia answers*

> ![FAQ Membership App](https://github.com/arjunrathod1996/Clientrade/assets/110610821/651620aa-cee2-47b7-b127-16a85b609bb2)
> *Customer-facing FAQ: most popular topic auto-expanded, search enabled, all formats supported*

---

## 📱 PWA & Browser API Features

### Web OTP API — Auto-Read OTP from SMS

```javascript
// Automatically reads OTP sent via SMS — no manual typing
if ('OTPCredential' in window) {
    const ac = new AbortController();
    
    navigator.credentials.get({
        otp: { transport: ['sms'] },
        signal: ac.signal
    }).then(otp => {
        document.getElementById('otpInput').value = otp.code;
        // Auto-submit after 1.5s
        setTimeout(() => submitOtpForm(), 1500);
        ac.abort();
    });
}
```

### Contact Picker API — Referral Feature

```javascript
// Select up to 10 contacts for referral
async function pickContacts() {
    const contacts = await navigator.contacts.select(
        ['name', 'tel'],
        { multiple: true }
    );
    
    // Filter: max 10, no duplicates, no invalid numbers
    const validContacts = contacts
        .filter(c => isValidIndianMobile(c.tel[0]))
        .filter(c => !existingCustomers.includes(c.tel[0]))
        .slice(0, 10);
    
    displayAsTags(validContacts);
}
```

### Geo Code API — Merchant Store Discovery

```javascript
// Find merchant stores near the customer's location
navigator.geolocation.getCurrentPosition(async position => {
    const { latitude, longitude } = position.coords;
    
    const stores = await fetchNearbyStores(latitude, longitude);
    renderStoreCards(stores);
});
```

> **Note:** Customer profile must be ≥ 50% complete before store discovery is enabled.

### Screenshots

> ![Customer Login OTP](https://github.com/arjunrathod1996/Clientrade/assets/110610821/a4924e4f-3246-4dd1-9258-6aeeb8bcc2f5)
> *OTP login with Web OTP API auto-read from SMS*

> ![Customer Profile](https://github.com/arjunrathod1996/Clientrade/assets/110610821/8255c5d1-f47b-4b4a-8611-3664891f0321)
> *Customer profile with Geo Code API for store discovery*

> ![Refer Contacts](https://github.com/arjunrathod1996/Clientrade/assets/110610821/ff96e323-3a2d-41ae-b338-c00ed8794db8)
> *Contact Picker API — select up to 10 contacts for referral*

> ![Merchant Stores](https://github.com/arjunrathod1996/Clientrade/assets/110610821/aa244df9-baa4-406a-bb41-b267a88daf5c)
> *Merchant stores discovered via Geo Code API with category and location filtering*

---

## 🌐 Language Translation

### Supported Languages

| Language | Code | Status |
|----------|------|--------|
| English  | `en` | ✅ Default |
| Hindi    | `hi` | ✅ Active |
| Kannada  | `kn` | ✅ Active |
| Spanish  | `es` | ✅ Active |

### Implementation — No Page Reload

```java
// Spring LocaleResolver — reads locale from cookie
@Bean
public LocaleResolver localeResolver() {
    CookieLocaleResolver resolver = new CookieLocaleResolver();
    resolver.setDefaultLocale(Locale.ENGLISH);
    return resolver;
}

// Locale change interceptor
@Bean
public LocaleChangeInterceptor localeChangeInterceptor() {
    LocaleChangeInterceptor interceptor = new LocaleChangeInterceptor();
    interceptor.setParamName("lang");
    return interceptor;
}
```

```javascript
// AJAX language switch — no page reload
function changeLanguage(lang) {
    fetch('/change-lang?lang=' + lang, { method: 'POST' })
        .then(() => location.reload());
}
```

### Screenshot

> ![Language Translation](https://github.com/arjunrathod1996/Clientrade/assets/110610821/91d18bc1-42ee-46b4-8085-8400e6d71f6b)
> *Dynamic language switching: English → Kannada / Hindi — no page reload*

---

## 🔧 Feature Toggle System

> Admin controls which features are active in the Membership App — no code changes needed.

### Toggleable Features

| Feature | Description |
|---------|-------------|
| **Appointment** | Customer can book appointments with staff |
| **Submit Bill** | Customer can submit/upload bills |

### How It Works

```java
// Feature config stored in DB
@Entity
public class FeatureConfig {
    private String featureName;      // "APPOINTMENT", "SUBMIT_BILL"
    private boolean enabled;
    private Long merchantAdminId;    // Scoped per business
}

// Checked in Thymeleaf template
// th:if="${featureConfig.isEnabled('APPOINTMENT')}"
```

### Screenshots

> ![Feature Enable](https://github.com/arjunrathod1996/Clientrade/assets/110610821/48b4cade-8676-4f70-b5f8-0c810816dedc)
> *Admin enables features for the Membership App*

> ![Feature Disable](https://github.com/arjunrathod1996/Clientrade/assets/110610821/5ed47a4e-cb43-4687-91e1-fda551a9acd3)
> *Disabled feature immediately disappears from Membership App — no deployment needed*

---

## 📁 Project Structure

```
clientrade/
│
├── src/main/java/com/clientrade/
│   ├── config/
│   │   ├── SecurityConfig.java          ← Spring Security + OAuth2 + JWT
│   │   ├── JWTAuthFilter.java           ← OncePerRequestFilter JWT validation
│   │   └── OAuthenticationSuccessHandler.java
│   │
│   ├── controller/
│   │   ├── AuthController.java          ← OTP generate/verify, JWT cookie
│   │   ├── LeadController.java
│   │   ├── BillingController.java
│   │   ├── AiChatController.java        ← Claude API integration
│   │   └── HealthCheckController.java
│   │
│   ├── service/
│   │   ├── JWTService.java
│   │   ├── OtpService.java              ← Rate limiting logic
│   │   ├── ClaudeAiService.java         ← AI chatbot with domain scoping
│   │   ├── HealthCheckService.java
│   │   ├── PdfExportService.java        ← ITextRenderer streaming
│   │   └── ExcelExportService.java      ← Apache POI XSSFWorkbook
│   │
│   ├── model/
│   │   ├── User.java
│   │   ├── LeadMain.java
│   │   ├── LeadContact.java
│   │   ├── LeadActivity.java
│   │   ├── Cart.java / CartItem.java
│   │   ├── Billing.java
│   │   ├── AuditLog.java
│   │   └── HealthReport.java
│   │
│   └── scheduler/
│       └── HealthCheckScheduler.java    ← @Scheduled cron + email reports
│
├── src/main/resources/
│   ├── templates/                       ← Thymeleaf HTML templates
│   │   ├── invoice-template.html
│   │   ├── health-report-email.html
│   │   └── ...
│   ├── messages.properties              ← EN translations
│   ├── messages_hi.properties           ← Hindi translations
│   ├── messages_kn.properties           ← Kannada translations
│   ├── messages_es.properties           ← Spanish translations
│   └── application.properties
│
├── src/main/resources/db/
│   ├── migration/                       ← Liquibase changesets
│   └── triggers/
│       ├── audit_user_trigger.sql
│       ├── audit_lead_trigger.sql
│       └── ...
│
└── pom.xml
```

---

## 🚀 Getting Started

### Prerequisites

```
Java 17+
MySQL 8.0+
Maven 3.8+
Claude API Key (Anthropic) — for AI chatbot
Gmail App Password — for health report emails
```

### Configuration

```yaml
# application.properties

# Database
spring.datasource.url=jdbc:mysql://localhost:3306/clientrade
spring.datasource.username=root
spring.datasource.password=yourpassword

# JWT
jwt.secret=your-jwt-secret-key
jwt.expiration=86400000

# Claude API (AI Chatbot)
claude.api.key=your-claude-api-key
claude.model=claude-sonnet-4-6
claude.max.tokens=1000

# OAuth2 - Google
spring.security.oauth2.client.registration.google.client-id=your-google-client-id
spring.security.oauth2.client.registration.google.client-secret=your-secret

# OAuth2 - GitHub
spring.security.oauth2.client.registration.github.client-id=your-github-client-id
spring.security.oauth2.client.registration.github.client-secret=your-secret

# Health Check Email
spring.mail.host=smtp.gmail.com
spring.mail.port=587
spring.mail.username=your-email@gmail.com
spring.mail.password=your-app-password
health.report.recipient=arjundargurathod@gmail.com
```

### Run

```bash
git clone https://github.com/arjunrathod1996/Clientrade.git
cd Clientrade

# Configure application.properties (see above)

mvn clean install
mvn spring-boot:run

# Application starts at: http://localhost:8080
```

### DB Trigger Setup

```bash
# After schema is created by Hibernate/Liquibase, run triggers:
mysql -u root -p clientrade < src/main/resources/db/triggers/audit_triggers.sql
```

---

<div align="center">

## 👨‍💻 Built By

**Arjun Rathod** — Full Stack Java Developer · Bengaluru, India

[![GitHub](https://img.shields.io/badge/GitHub-arjunrathod1996-181717?style=for-the-badge&logo=github)](https://github.com/arjunrathod1996)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-arjundr-0A66C2?style=for-the-badge&logo=linkedin)](https://www.linkedin.com/in/arjundr/)
[![Email](https://img.shields.io/badge/Email-arjundargurathod@gmail.com-EA4335?style=for-the-badge&logo=gmail)](mailto:arjundargurathod@gmail.com)

---

*3 years · 2 companies · Java + Spring Boot + React + AI*

*Societe Generale (financial compliance & IAM) · Slingloft Technologies (enterprise CRM)*

</div>
