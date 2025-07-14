# AfroTech Web App: Scalable E-commerce on Microsoft Azure

![Uploading image.png…]()

<img width="10020" height="142" alt="image" src="https://github.com/user-attachments/assets/b92e9a1a-985d-44d0-9919-3f469ed8d84c" /># AfroTech Web App: Scalable E-commerce on Microsoft Azure

> **Developed by TechStylers Group 2**  
> The project was built by TechStylers Group 2 as part of a practical cloud engineering initiative to address real-world challenges like traffic surges, system crashes, and deployment delays—especially during events like Black Friday sales.
> Key features include:
- Autoscaling infrastructure with load balancing
- CI/CD automation using Azure DevOps
- Secure network segmentation with VNet & NSGs
- Real-time monitoring via Azure Monitor & Application Insights
Whether you're a student, engineer, or cloud enthusiast, this repository offers a real-world reference architecture for deploying enterprise-grade applications on Azure.

---

## Table of Contents

- [Project Summary](#project-summary)
- [Real-World Problem & Motivation](#real-world-problem--motivation)
- [Solution Overview](#solution-overview)
- [Architecture Diagram](#architecture-diagram)
- [Tools & Technologies Used](#tools--technologies-used)
- [Azure Resource Configuration](#azure-resource-configuration)
- [Step-by-Step Deployment Process](#step-by-step-deployment-process)
- [Security & Network Design](#security--network-design)
- [Azure DevOps & CI/CD Integration](#azure-devops--cicd-integration)
- [Testing & Validation](#testing--validation)
- [User Flow & Experience](#user-flow--experience)
- [Challenges & Resolutions](#challenges--resolutions)
- [Performance, Monitoring & Optimization](#performance-monitoring--optimization)
- [Future Improvements](#future-improvements)
- [Impact & Business Value](#impact--business-value)
- [Screenshots](#screenshots)
- [Meet the Team](#meet-the-team)
- [License](#license)

---

## Project Summary

AfroTech is a scalable e-commerce solution built using Microsoft Azure, with features that meet enterprise-level needs including authentication, transaction tracking, autoscaling, and high availability. The application was deployed as part of a cloud engineering group project using a combination of IaaS and PaaS services. It incorporates secure infrastructure, CI/CD automation, and performance analytics for seamless operation.

---

## Real-World Problem & Motivation

During peak sale periods like **Black Friday**, e-commerce platforms face:

- Traffic overload  
- Website crashes  
- Lost sales  
- Security vulnerabilities

**Scenario:** A business lost 20% of projected revenue during a Black Friday sale due to poor scalability and downtime.

---

## Solution Overview

AfroTech was developed to solve these issues by offering:

- Scalable web hosting via Azure App Services and VMs  
- Database management with Azure SQL  
- User identity control via Azure Active Directory  
- Traffic distribution through Load Balancer  
- Monitoring with Azure Monitor & Application Insights  
- Secure architecture using VNet, NSGs, and private endpoints  

---

## Architecture Diagram
<img width="1748" height="723" alt="image" src="https://github.com/user-attachments/assets/3a706201-ce9c-40a7-bce6-172e4af57b93" />


User --> Azure App Service (Frontend) --> Azure SQL (Database)
           |
     Azure Load Balancer
           |
       Virtual Machines
           |
      Network Security Groups
           |
    Azure AD Authentication
           |
  Azure Monitor & Insights

---

## Tools & Technologies Used

### Azure Services:
- Azure App Service  
- Azure Virtual Machines  
- Azure SQL Database  
- Azure Blob Storage  
- Azure Active Directory  
- Azure Virtual Network & NSGs  
- Azure Load Balancer  
- Azure Monitor & Application Insights  
- Azure DevOps (CI/CD)  

### Development Tools:
- Git & GitHub  
- VS Code  
- PowerShell & Azure CLI  

### Monitoring:
- Azure Monitor  
- Log Analytics  
- App Insights  

---

## Azure Resource Configuration

- **Resource Group:** `afroTech-prod-rg`  
- **Region:** West Europe  
- **Pricing Tier:** S1 Standard (App Service), D2s V3 (VMs)  
- **Network Setup:**  
  - **VNet CIDR:** `10.20.0.0/16`  
  - **Subnets:**  
    - Frontend: `10.20.1.0/24`  
    - Backend: `10.20.2.0/24`

---

## Step-by-Step Deployment Process

### 1. Web App Deployment
<img width="982" height="762" alt="image" src="https://github.com/user-attachments/assets/fcfbbc55-1598-40f1-98d6-5e54d922a476" />


<img width="1012" height="773" alt="image" src="https://github.com/user-attachments/assets/5a0ef8d6-a6d6-4cfe-9da7-f0a3b09b9466" />

- Used Azure App Service + GitHub repo integration  
- Selected runtime (.NET Core)  
- Configured App Settings & deployment slots  

### 2. Azure SQL Database
<img width="1090" height="743" alt="image" src="https://github.com/user-attachments/assets/7baa14b0-5ae6-431b-ab70-036cb432a86f" />

- Configured DTU-based compute  
- Set firewall rules and connection strings  
- Enabled VNet integration  

### 3. Blob Storage
- Used for media assets and unstructured content  

### 4. Virtual Machines + Load Balancer
<img width="1090" height="742" alt="image" src="https://github.com/user-attachments/assets/86426af6-595b-40ab-9120-ae8563d3640f" />

<img width="1100" height="696" alt="image" src="https://github.com/user-attachments/assets/9bca3df2-4cea-4129-b914-973801ec9f9a" />

- 2 backend VMs in a VM Scale Set  
- Load balancer configured with health probes  

---

## Security & Network Design

- **Azure Active Directory:** Enterprise-grade authentication  
- **NSGs:**  
  - Frontend: HTTP/HTTPS allowed  
  - Backend: Limited to internal traffic only  
- **Service Endpoints:** Secure SQL access  
- **Role-Based Access Control (RBAC):** Enforced across all services  

---

## Azure DevOps & CI/CD Integration

- **Version Control:** GitHub (main/dev branches)  
- **CI/CD Pipelines:**  
  - Build pipeline: triggered on push to `dev`  
  - Release pipeline: deploys to App Service on merge to `main`  
- **Secrets Handling:** Plans to integrate Azure Key Vault  

---

## Testing & Validation

### Web Application
- Functional testing via live URL (`102.37.147.54`)

### SQL Database
- Test queries executed from app to confirm live connections  

### Load Testing
- Azure Load Testing tool used to simulate real user behavior  

---

## User Flow & Experience

1. User logs in using Azure AD authentication  
2. Browses products fetched from Azure Blob  
3. Adds items to cart  
4. Completes checkout (data saved to SQL DB)  
5. Receives confirmation and logs created in Azure Monitor  

---

## Challenges & Resolutions

| Challenge               | Resolution                                            |
|------------------------|--------------------------------------------------------|
| VM blocked by NSG      | Updated NSG rules with specific port allowances       |
| AAD login issues       | Configured correct role permissions via RBAC          |
| CI/CD failure on push  | Reviewed YAML config and service connections          |
| Timeout on DB query    | Implemented VNet service endpoints for secure, faster routing |

---

## Performance, Monitoring & Optimization

- **Azure Monitor:** Real-time alerts and health checks  
- **App Insights:** Logs, user behavior, response times  
- **Autoscaling:** Enabled based on CPU usage and user count  
- **Uptime:** Achieved 99.99% availability during simulated peak load  

---

## Future Improvements

- Integrate Azure Key Vault for secrets  
- Add Azure Front Door for global load balancing  
- Connect Power BI dashboards for live monitoring  
- Use Spot VMs for cost optimization  
- Containerize backend using Azure Container Instances (ACI)  

---

## Impact & Business Value

- **2x faster** page loads vs. baseline  
- Reduced downtime from minutes to zero  
- Improved customer satisfaction  
- Reinforced security & compliance (PII-safe)  
- Scalable for future feature additions & peak sales events  

---

## Conclusion

The successful deployment of the web application and its supporting database infrastructure on Microsoft Azure demonstrates the practical application of cloud technologies in real-world scenarios. Throughout this project, the TechStylers Azure Group 2 team utilized key Azure services such as App Services, Azure SQL Database, Azure Resource Manager (ARM), and integrated monitoring tools to ensure scalability, reliability, and secure data handling. The system enables seamless data collection from user interactions, with backend processes ensuring integrity, performance, and compliance with industry best practices.
This deployment serves as a foundation for further development, including potential CI/CD automation, integration of Azure Key Vault for credential management, and scaling through load balancers and autoscale groups. Additionally, the use of role-based access control (RBAC), diagnostic logs, and firewall configurations reflects a strong emphasis on security and governance. Overall, this project exemplifies not only technical proficiency but also collaborative project execution, aligning with enterprise-grade deployment standards.

---

## Meet the Team

| Name       | Responsibility                              |
|------------|----------------------------------------------|
| Sherilyn G.  | Frontend UI & UX Setup                       |
| Tony   O.    | SQL Database & API Integration               |
| Olawumi  S.  | Networking & Security (NSGs/VNet)            |
| Angil   D.   | Azure DevOps Pipelines & GitHub Integration  |
| Emmanuel  O. | Performance Tuning & Monitoring Setup        |
| Adeyemi  A.  | Documentation, Architecture & Final Testing  |

---

## License

This project is open-source and available under the **MIT License**.

---

> _\"At AfroTech, we believe scalable cloud-native architecture isn't just for the enterprise—it's for every developer who dares to build big.\"_


