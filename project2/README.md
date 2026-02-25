**Implementing Least Privilege RBAC in Azure to Reduce Excessive Access Risk**

This lab demonstrates how overly permissive role assignments were identified and remediated using Role-Based Access Control (RBAC) within Microsoft Azure, aligning with Zero Trust and least privilege security principles.

## Overview

This lab demonstrates how excessive permissions on an Azure Storage Account were identified and remediated using Role-Based Access Control (RBAC). The goal was to replace an overly permissive role assignment with a least-privileged alternative, reducing the risk of unauthorized administrative actions.

The implementation was performed in the Microsoft Azure portal as part of a cloud security hardening exercise aligned with Zero Trust and least privilege principles.


## Objective

The goal was to iddentify over-permissioned access and enforce least privilege RBAC to minimize security risk.

Why does this matter?

In enterprise cloud environments, users are often granted broad permissions (e.g., Owner or Contributor) during setup. Over time, these permissions remain, creating unnecessary risk exposure. This lab simulates a real-world scenario where a security analyst must:

• Review access permissions

• Identify privilege overreach

• Implement a least-privilege access model

The goal is to reduce the potential for:

• Insider threats

• Accidental deletion of resources

• Privilege escalation abuse


## Initial Risk Identified

The user account was discovered to have been granted the Owner role on the Resource Group and could therefore delete or alter critical resources, thus violating the principle of least privilege.


## Actions Taken

Step 1: Access Review

Navigated to:

Resource Group → Access Control (IAM) → Role Assignments

Reviewed all existing role bindings associated with the resource group.


Step 2: Removal of Excessive Privilege

The Owner role assignment for the user account was removed to eliminate full administrative control over the resource.

Security reasoning:

• Prevents unrestricted configuration changes

• Reduces blast radius if account is compromised

• Enforces separation of duties

Step 3: Implement Least-Privilege Role

A more restrictive role was assigned:

New Role: Reader

Permissions Granted:

• Read-only access to Resource group data

• No ability to delete or reconfigure resources

This ensures the user can still perform required tasks (viewing data) without exposing the environment to administrative risk.


## Security Outcome

Before Remediation

• User had unrestricted administrative control

• High risk of privilege misuse

• User was able to delete virtual machine resource


After Remediation

• Access reduced to read-only permissions

• Administrative attack surface minimized

• Clear enforcement of least privilege model


## Business Impact

Applying least privilege reduces insider threat risk and ensures compliance with security best practices such as ISO 27001 access control principles.