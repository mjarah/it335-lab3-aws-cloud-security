# \# 🔐 Lab 3 – AWS Cloud Security Fundamentals

# 

# ---

# 

# \## 📋 Project Overview

# 

# This lab applies the lessons from the \*\*Capital One cloud breach\*\* by configuring foundational AWS security controls. As a student security engineer, I implemented essential protections across identity, storage, compute, and monitoring to demonstrate how proper configuration prevents real-world breaches.

# 

# ---

# 

# \## 🎯 Key Learning Objectives

# 

# \- 🔑 \*\*IAM Least Privilege:\*\* Creating restricted users and groups to limit credential blast radius

# \- 🪣 \*\*S3 Access Control:\*\* Blocking public access to prevent unauthorized data exfiltration

# \- 💻 \*\*EC2 Network Security:\*\* Restricting inbound traffic using Security Groups and IMDSv2

# \- 👁️ \*\*Continuous Monitoring:\*\* Understanding CloudTrail, AWS Config, and Billing dashboards

# 

# ---

# 

# \## 🛠️ What I Configured

# 

# \- 🔑 \*\*Identity (IAM):\*\* Enabled MFA on root account, created `lab-student-user` and `LabUsers` group with read-only permissions

# \- 🪣 \*\*Storage (S3):\*\* Created private bucket `it335-lab3-mohammedjarah-secure` with Block All Public Access enabled

# \- 💻 \*\*Compute (EC2):\*\* Launched Free Tier instance with Security Group restricted to my IP only, avoiding 0.0.0.0/0

# \- 👁️ \*\*Visibility:\*\* Reviewed CloudTrail logging and Billing dashboard for governance awareness

# 

# ---

# 

# \## 📁 Files in This Lab

# 

# \- 📸 `screenshots/before/` — Baseline AWS dashboards before any configuration

# \- ✅ `screenshots/after/` — Proof of all security configurations

# \- 📝 `lab3-reflection.md` — Written analysis connecting configurations to the Capital One breach

# \- 💻 `terminal-proof.md` — Evidence of terminal-based Git workflow and commit history



# 

# \## 👨‍💻 Student Information

# 

# | | |

# |---|---|

# | 👤 \*\*Student\*\* | Mohammed Jarah |

# | 📚 \*\*Course\*\* | IT335 – Cloud Security |

# | 🏫 \*\*University\*\* | Marymount University |

# | 📅 \*\*Due Date\*\* | March 17, 2026 |

