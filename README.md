# IAM-Troubleshooting-Guide

### 1. Introduction

This guide provides standardized troubleshooting steps for resolving common Identidty and Access Management (IAM) issues within an environment. It is designed for help desk technicians and IAM support staff who handle:

- User authentication issues
- Account lockouts
- Password resets
- Access requests
- SSO/MFA failures
- Permission errors

### 2. IAM Support Workflow Overview

#### Tier 1 Respobsibilites:

- Gather initial information
- Verify user identity
- Perform basic troubleshooting
- Resolve common issues (password resets, lockouts)

#### Tier 2 Responsibilities:

- Handle escalated issues
- Modify or investigate permissions
- Coordinate with IAM engineering
- Review logs for failure patterns

#### General Workflow:

1. Validate the user's identity.
2. Identify the system involved
3. Determine the failure point (authentication, authorization, MFA, SSO)
4. Follow the relevant troubleshooting steps
5. Document actions in the ticket
6. Escalate if necessary

### 3. Common IAM Issues and Troubleshooting Steps

#### A. Password  reset Issues
#### Symptoms:
- User cannot log in
- System states `incorrect password`
- User forgot password

#### Troubleshooting Steps:
- Verify user identity following the company process
- Check account status in the identity directory (AD/IDM system)
- If locked -> unlock account
- Initiate password reset
- Verify password meets securty policy
- Confirm user can log in again

#### When to Escalate:
- Password resets succeed but authentication still fails
- Account is not visible in the identity directory

#### B. Account Lockout
#### Symptoms:
- `Account is locked` message
- Too many failed login attempts

#### Troubleshooting Steps:
- Verify the lockout in IAM system (Active Directory, Okta, etc)
- Unlock account
- Check if the user is logged in elsewhere causing repeated failures
- Confirm user is entering correct credentials
- Ask the user to try logging in again

#### When to Escalate:
- Recurrent lockouts (indicate sync or device issues)

#### C. MFA (Multi-Factor Authentication) Failure
#### Symptoms:
- Can't receive authentication code
- Authentication app not working
- Wrong verification method

#### Troubleshooting Steps:
- Verify user's MFA enrollment
- Ask what type of MFA they use (SMS, email, authenticator app)
- Check device time sync (common authenticator issue)
- Reset MFA tokens if necessary
- Re-enroll user in MFA
- Test authentication

#### When to Escalate:
- MFA service outage
- Token mismatch in IAM system logs
