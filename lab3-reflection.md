\# Lab 3 Reflection – AWS Cloud Security Fundamentals

Student: Mohammed Jarah | IT335 | March 2026



\## Summary of Configurations



\### Identity and Access Management (IAM)

I verified MFA was enabled on the root account and created a restricted IAM group called LabUsers with AmazonS3ReadOnlyAccess permissions only. I created lab-student-user and added them to the group. I verified by signing in as that user and confirmed access was denied to most services.



\### Secure Storage (S3)

I created an S3 bucket named it335-lab3-mohammedjarah-secure with all Block Public Access settings enabled. I confirmed this on the Permissions tab showing Block all public access: On.



\### Secured Compute (EC2)

I launched a Free Tier t3.micro Amazon Linux instance. I created a Security Group restricting SSH access to only my IP address 173.66.253.210/32. I avoided using 0.0.0.0/0 which would allow anyone to attempt access.



\### Visibility and Governance

I navigated to the Billing and Cost Management dashboard confirming my free plan status and reviewed the AWS CloudTrail console which logs all API activity across the account.



\## Connection to Capital One Breach



\### IAM and Least Privilege

In the Capital One breach, the attacker exploited an IAM role that had far more permissions than needed. It could list and download S3 objects across the entire account. By implementing least privilege IAM and granting only S3ReadOnlyAccess to a specific group, the blast radius of any stolen credential is minimized. Even if an attacker stole lab-student-user credentials, they could not access EC2, modify IAM, or delete resources.



\### S3 Block Public Access

The Capital One attacker exfiltrated over 100 million customer records from S3 buckets. Enabling Block All Public Access means that even if a bucket policy is misconfigured, the block acts as a final safety net preventing any anonymous or unintended external access to sensitive data.



\### EC2 Security Groups and IMDSv2

The core attack in Capital One used Server Side Request Forgery through the misconfigured WAF to reach the EC2 Instance Metadata Service version 1, which returned temporary IAM credentials without any authentication. Restricting the Security Group to SSH from my IP only means the instance is not reachable from the public internet. IMDSv2 additionally breaks SSRF attacks by requiring a session token before metadata can be read.



\### CloudTrail and Continuous Monitoring

Capital One detection systems failed to alert on unusual S3 API calls for several months. CloudTrail records every API call with timestamps and source IP. Continuous monitoring would have flagged anomalous behavior within minutes instead of months. Relying only on periodic security audits creates a window of opportunity for attackers to operate undetected.



\## Critical Analysis



The controls that felt most straightforward were IAM least privilege and S3 Block Public Access because they have clear binary outcomes. The control most prone to misconfiguration was the EC2 Security Group. It is tempting to allow 0.0.0.0/0 for SSH to avoid connectivity issues but this creates exactly the wide open attack surface that makes breaches possible.



Beyond tools, the Capital One incident reflects a failure of organizational governance and culture. AWS offered all the right tools but they were not applied correctly or monitored consistently. A security conscious culture requires regular audits, enforced standards, and a team empowered to fix misconfigurations without bureaucratic delays. Technology alone cannot compensate for a culture that does not prioritize security as an ongoing operational responsibility.

