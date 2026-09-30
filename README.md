# Microsoft Entra Identity Governance & Access Management

<img width="900" alt="Lab diagram" src="https://github.com/user-attachments/assets/1b5857c0-e75f-4299-b1f1-f5e7c8ec9216" />


## Overview

In this project, I demonstrate how employees can request, receive, review, and eventually lose access to business resources using **Microsoft Entra Entitlement Management**.

The project uses **Microsoft Entra security groups as the governed resources**, so no third-party SaaS subscription is required.

The scenarios demonstrate:

* Access packages
* Security groups
* Access requests and approvals
* Time-limited access
* Access reviews
* Automatic access removal
* Access expiration and the leaver process

---

## Project Workflow

The overall workflow demonstrated in this project is:

**Employee → Access Package → Approval → Security Group Access → Access Review → Keep or Remove Access → Expiration**

This simulates how an organization can manage temporary or additional access without manually adding and removing users from security groups.

---

## Catalog Creation

A catalog named **Corporate Resource Access** was created to organize the resources and access packages used throughout the project.

The catalog contains the security groups used in the scenarios and their corresponding access packages.

<img width="800" alt="Creating the catalog" src="https://github.com/user-attachments/assets/5eb1a07e-4291-4d54-ac4c-939d69640d74" />

<img width="800" alt="All new SGs" src="https://github.com/user-attachments/assets/087ada36-db4b-47a1-873b-747418659123" />

<img width="800" alt="catalog resourse creation" src="https://github.com/user-attachments/assets/d55fe4ac-3aa5-439c-9ad9-bc1cfee9338e" />

---

# Scenarios

## 1. Q4 Marketing Campaign

The Q4 Marketing Campaign is starting, and only employees participating in the campaign should have access to the campaign's resources.

A security group named **Q4 Marketing Campaign** was created, along with an access package that allows eligible users to request access.

The access package is configured to expire after **90 days**.

<img width="800" alt="Access package creation" src="https://github.com/user-attachments/assets/a3efdc6c-259b-4d79-b9fb-8d717d4ca1b0" />

<img width="800" alt="Expiration and access review" src="https://github.com/user-attachments/assets/9f9699e9-6a06-4f92-9521-ec47d251c222" />

**Scenario:**

* Kaitlyn Stewart is a member of the marketing campaign.
* Kaitlyn requests access through the access package.
* Campaign Director Madison Thompson reviews and approves the request.
* Kaitlyn is automatically added to the **Q4 Marketing Campaign** security group.

This demonstrates how an access package can replace manual group membership requests with a controlled request and approval process.

<img width="800" alt="Madison approves marketing users" src="https://github.com/user-attachments/assets/165119c5-dc6d-4441-962e-4a5419a107bc" />

<img width="800" alt="KS group membership" src="https://github.com/user-attachments/assets/837970a7-d30f-4d57-923d-0454632be82b" />


---

## 2. Q4 Financial Records

The marketing campaign requires access to company financial records and projections to create a budget.

A security group named **Q4 Financial Records** was created, along with an access package for requesting access.

The access package is configured to expire after **90 days**.

**Scenario:**

* Victoria Williams is responsible for the campaign budget.
* Victoria requests access to the financial records package.
* Campaign Director Madison Thompson approves the request.
* Victoria is automatically added to the **Q4 Financial Records** security group.

This demonstrates how employees can receive temporary access to sensitive business information when it is required for a specific project.

<img width="800" alt="Madison approves marketing users" src="https://github.com/user-attachments/assets/ad9fd232-028a-49c5-9c73-d0b0734e2e39" />
<img width="800" alt="Acces request approved log " src="https://github.com/user-attachments/assets/521ef244-239a-43ee-802a-3e6e7f31dc29" />
<img width="800" alt="V will added to group" src="https://github.com/user-attachments/assets/8028437c-267d-47eb-af30-38e8bf5d8d70" />

---

## 3. SOC Internship

The Security Operations department is running an internal internship to provide selected IT employees with experience using security tools.

A security group named **SOC Interns** was created, along with an access package for requesting access.

The access package is configured to expire after **90 days**.

**Scenario:**

* Cameron Lawson is selected for the SOC internship.
* Cameron requests access to the SOC Interns package.
* SecOps1 approves the request.
* Cameron is automatically added to the **SOC Interns** security group.

This demonstrates how temporary access can be provided to employees who need additional permissions for a specific assignment.

<img width="800" alt="CL access package" src="https://github.com/user-attachments/assets/f376d451-db22-4d1c-8bc4-8710520ec567" />

<img width="800" alt="Sec ops approving CL" src="https://github.com/user-attachments/assets/30a1ff00-7fd8-498f-a0da-55cfb8c5c6ab" />

<img width="800" alt="CL group membership" src="https://github.com/user-attachments/assets/71c3ef01-ce4d-4e47-bfd6-e0f1eb859d23" />


---

# Access Reviews

An access review was created for each access package to periodically verify whether users still require access.

### Q4 Marketing Campaign

**Kaitlyn Stewart — Approved**

Kaitlyn still requires access to the campaign resources, so her access was approved and remains active.

### Q4 Financial Records

**Victoria Williams — Denied**

Victoria no longer requires access to the financial records after completing her budgeting responsibilities.

Her access was denied during the access review, and her access package assignment was removed, which resulted in her membership in the **Q4 Financial Records** security group being removed.

<img width="800" alt="Access review denied" src="https://github.com/user-attachments/assets/d35d382b-e444-46e1-9456-49356fd8c4b1" />
<img width="800" alt="EM removes access VW" src="https://github.com/user-attachments/assets/7776889f-4384-4d29-bb2e-9f1589b7cc3f" />
<img width="800" alt="Group membership removed VW" src="https://github.com/user-attachments/assets/562f80e6-a8db-47db-b997-b24abc083fad" />

### SOC Interns

**Cameron Lawson — Approved**

Cameron still requires access because the internship is still active, so the access was approved and remains active.

---

# Expiration / Leaver Scenario

The SOC internship eventually ends, and Cameron Lawson no longer requires access to the security tools.

Cameron's access package assignment reaches its expiration date, causing the assignment to expire and Cameron to be automatically removed from the **SOC Interns** security group.

This demonstrates how access can be automatically removed when temporary access is no longer required.

<img width="800" alt="entitlment ended for CL" src="https://github.com/user-attachments/assets/dae99a2e-c8bf-44bb-a746-80a267e30520" />
<img width="800" alt="CL removed from group" src="https://github.com/user-attachments/assets/31b0d39e-e353-4681-b914-eff93a15bb61" />


### Testing the Expiration

Access package assignments receive their expiration date when the assignment is created. To test the expiration process without waiting 90 days, I removed the original assignment and created a new assignment with a short expiration period.

The test assignment was configured to expire **one hour after the assignment started**.

This allowed me to verify the complete leaver workflow:

**Assignment Created → Access Granted → Assignment Expires → Access Removed**

---

# Key IAM Concepts Demonstrated

This project demonstrates several real-world Identity and Access Management concepts:

* **Entitlement Management** — Managing how users request and receive access.
* **Access Packages** — Bundling resources into controlled access requests.
* **Approval Workflows** — Requiring an authorized person to approve access.
* **Time-Limited Access** — Automatically limiting access to a defined period.
* **Access Reviews** — Periodically verifying whether users still require access.
* **Automatic Deprovisioning** — Removing access when it is denied or expires.
* **Security Groups** — Using group membership to provide access to business resources.
* **Identity Governance** — Controlling the full lifecycle of user access rather than simply granting permissions.
