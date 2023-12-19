# Astrid Architecture Deep Dive:

A secure and flexible solution for advanced analytics and metric gathering with identification.

## Core Components:
### Zephyr (backend):
Technology: Python3.11 RESTful FastAPI (Rust in future)
DB: MongoDB
#### Functionality:
- Secure data storage in MongoDB.
- Device footprint generation and validation.
- User management and access control.
- Analytics processing and reporting.
- API endpoints for data access and manipulation.

#### Security:
- HTTPS communication with TLS encryption.
- Data at rest encryption in MongoDB.
- Secure authentication and authorization protocols.
- Regular security updates and vulnerability assessments.

### Vega (client-side):
At this stage Vega is only javascript library which can be mounted to the web page and will be able to send metrics without any addictional tools.  
Technology: JavaScript?

#### Functionality:
- Device fingerprinting with secure hashing algorithms.
- Secure data transmission to Zephyr API endpoints.
- API wrapper for easy integration with diverse platforms (websites, apps, bots, etc.).
- Customization options for specific data collection needs.

#### Privacy:
- Clear user consent mechanisms for data collection.
- Fine-grained control over what data is collected and shared.
- Data retention policies customizable by users.

### Interaction Flow:
Vega gathers user data (screen resolution, browser, etc.) through device fingerprinting.  
User might consents to data sharing through platform-specific mechanisms.  
Vega securely transmits data to Zephyr's API endpoint via HTTPS.  

Zephyr validates and sanitizes incoming data.  
A unique and secure device footprint is generated.  
Data is stored in MongoDB with appropriate security measures.  

Zephyr processes and analyzes collected data.  
Reports and insights are generated for platform administrators.  

### Flexibility and Customization:
Vega's API wrapper allows integration with any platform, offering versatility.  
Astrid can be tailored to specific data collection needs through configuration options.  
Organizations can develop custom analytics dashboards and reports based on gathered data.  
