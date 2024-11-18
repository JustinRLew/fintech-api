# **Fintech Payment Gateway**

## **Project Overview**
This project highlights a secure fintech payment gateway built with cybersecurity best practices. It prioritizes protecting sensitive financial data, ensures secure communication, and detects and addresses threats. The design simulates real-world fintech scenarios and complies with standards like PCI-DSS.

---

## **Key Features**
- **Secure Payment Processing**: Transactions are encrypted using AES-256 to protect sensitive cardholder data.
- **JWT-Based Authentication**: Secure user login and session management with JSON Web Tokens (JWT).
- **Database Security**:
  - Encrypted sensitive fields at rest.
  - Parameterized queries to prevent SQL injection.
- **Deployment on GCP**:
  - HTTPS enforced with SSL certificates.
  - Nginx reverse proxy for enhanced security.
- **Monitoring and Incident Response**:
  - Real-time logging and alerts for suspicious activities.
  - Automated database and application backups.

---

## **Technologies Used**
- **Backend**: Node.js, Express.js
- **Database**: MySQL with encryption for sensitive fields
- **Cache**: Redis (optional for performance optimization)
- **Deployment**: Google Cloud Platform (GCP)
  - Compute Engine (VM Instances)
  - Nginx for reverse proxy
  - Certbot for HTTPS
- **Monitoring**: GCP Logging and Monitoring, Cron jobs for backups

---

## **Setup Instructions**

### **1. Prerequisites**
- Node.js and npm installed locally.
- A Google Cloud Platform account.
- Domain name for HTTPS (optional).

---

### **2. Local Installation**
1. Clone the repository:
   ```bash
   git clone https://github.com/JustinRLew/fintech-api.git
   cd fintech-api


Install dependencies:

bash
npm install

Create a .env file and configure environment variables:

plaintext

ENCRYPTION_KEY=your-256-bit-key

ENCRYPTION_IV=your-16-byte-iv

JWT_SECRET=your-jwt-secret

Start the application:

bash
node server.js

Access the application at http://localhost:3000.

3. Deployment on GCP
   
Set up a Compute Engine instance:
  Deploy the Node.js application on a VM.
  Use Nginx as a reverse proxy.

Enable HTTPS:
  Use Certbot to obtain and configure SSL certificates.

Configure database access:
  Host MySQL on a separate VM instance.
  Secure connections with private IP and encryption.

4. Testing the Application
   
Use Postman to test the endpoints:
Login: POST /login
Process Payment: POST /process-payment
Simulate security attacks using tools like OWASP ZAP to verify robustness.

Endpoints
Endpoint	Method	Description
/login	POST	User authentication and JWT issue.
/process-payment	POST	Processes payment securely.
/secure-data	GET	Accesses protected resources.

Monitoring and Backup

Logging:
Tracks failed login attempts and server errors.
Accessible via GCP Logs Explorer.

Automated Backups:
Database dumps are created daily and stored in a secure Cloud Storage bucket.

Future Improvements
Implement role-based access control (RBAC).
Add Redis caching for improved performance.
Expand monitoring with anomaly detection.
