# 🏗️ Azure Resource Hierarchy Lab

![Azure](https://img.shields.io/badge/Azure-AZ--104-0078D4?logo=microsoftazure) ![Terraform](https://img.shields.io/badge/Terraform-1.7+-purple?logo=terraform) ![License](https://img.shields.io/badge/License-MIT-green)

> Azure governance lab: Management Groups, Subscriptions, Resource Groups, RBAC, and Azure Policy — fully codified in Terraform IaC with GitHub Actions CI/CD.

## 🎯 What This Lab Demonstrates

- Management Group hierarchy design (Tenant Root → Root MG → Workloads MG)
- Subscription scoped under management group for policy inheritance
- Resource Group naming and tagging strategy (env, owner, costcenter, tier)
- RBAC least-privilege assignments at Management Group and Subscription scope
- Azure Policy assignments: tag enforcement (Audit) + allowed locations (Deny)
- Terraform IaC with remote state stored in Azure Blob Storage
- GitHub Actions pipeline: plan on PR, apply on main merge

## 🏛️ Architecture

Tenant Root Group → mg-jjadams-root → mg-jjadams-workloads → Subscription → RGs

| Resource Group | Region | Purpose |
|---|---|---|
| rg-hierarchy-core | East US | Governance, Key Vault, Log Analytics |
| rg-hierarchy-network | East US | VNet, NSG, Subnets |
| rg-hierarchy-compute | East US | VMs, AKS, Storage |

## 📁 Repository Structure

terraform/  Terraform modules and environments
policies/   Azure Policy definitions and assignments
scripts/    Azure CLI and PowerShell scripts
docs/       Architecture docs and screenshots

## 📸 Lab Evidence

### Management Group Hierarchy
![Tenant Root Group](docs/01-tenant-root-group.png)
![MG Hierarchy](docs/02-mg-hierarchy.png)
![Subscription Under Workloads](docs/03-sub-under-workloads-mg.png)

### Resource Groups and Tags
![Resource Groups List](docs/04-resource-groups-list.png)
![RG Tags](docs/05-rg-tags.png)

### RBAC and Identity
![RBAC Role Assignments](docs/06-rbac-role-assignments.png)
![Service Principal](docs/07-sp-app-registration.png)

### Policy and Cost Controls
![Policy Assignments](docs/08-policy-assignments.png)
![Policy Compliance](docs/09-policy-compliance.png)
![Budget Alert](docs/10-budget-alert.png)

## 🧑‍💼 Author

Jubril Adams · Azure Administrator (AZ-104) · CompTIA Cloud+ · AWS SAA
[LinkedIn](https://linkedin.com/in/jubriladams) · [GitHub](https://github.com/jubriladams78)
