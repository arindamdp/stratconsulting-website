# Strat Consulting Website - Repository Configuration Documentation

**Repository:** https://github.com/arindamdp/stratconsulting-website  
**Owner:** arindamdp  
**Created:** October 2025  
**Last Updated:** October 2025

---

## 📋 Table of Contents

1. [Repository Settings](#repository-settings)
2. [Branch Protection Rules](#branch-protection-rules)
3. [Collaborator Permissions](#collaborator-permissions)
4. [Code Owners](#code-owners)
5. [Security Settings](#security-settings)
6. [Form Configuration](#form-configuration)
7. [Blocked Email List](#blocked-email-list)
8. [Git Configuration](#git-configuration)
9. [GitHub Features](#github-features)
10. [Backup & Recovery](#backup--recovery)

---

## 🏗️ Repository Settings

### Basic Information

```yaml
Repository Name: stratconsulting-website
Description: Strat Consulting - AI Solutions Website (GoDaddy Hosted)
Visibility: Private (can be made Public for branch protection)
Default Branch: main
License: None (Proprietary)
```

### Features Enabled

```yaml
✅ Issues: Enabled
✅ Projects: Enabled
✅ Wiki: Disabled (using README.md instead)
✅ Discussions: Disabled
✅ Pull Requests: Enabled
```

### Repository Topics (for discoverability if public)

```
ai-solutions
digital-transformation
sme-consulting
business-automation
html-website
formsubmit
```

---

## 🔒 Branch Protection Rules

### Status: INTENTIONALLY DISABLED

**Reason:** Private repository on free plan cannot enforce branch protection rules.

**Workaround:** Trust-based team agreement (see TEAM_AGREEMENT.md)

### Recommended Settings (If Upgraded to GitHub Team or Made Public):

```yaml
Branch: main

Protection Rules:
  ☑️ Require pull request before merging
    - Required approvals: 1
    - Dismiss stale reviews: YES
    - Require review from Code Owners: YES
  
  ☑️ Require conversation resolution before merging
  
  ☑️ Require linear history
  
  ☑️ Do not allow bypassing (apply to administrators)
  
  ☐ Require status checks (not needed currently)
  
  ☐ Require signed commits (optional, not required)
  
  ☐ Allow force pushes: NO
  
  ☐ Allow deletions: NO
```

### How to Enable (When Needed):

1. Go to: https://github.com/arindamdp/stratconsulting-website/settings/branches
2. Click "Add branch protection rule"
3. Apply settings above
4. Save changes

---

## 👥 Collaborator Permissions

### Current Team Structure

```yaml
Owner:
  - arindamdp (Admin access)

Collaborators:
  # Add team members here with their roles
  # Example:
  # - developer1 (Write access)
  # - designer1 (Write access)
  # - reviewer1 (Write access)
```

### Permission Levels Defined

```yaml
Read: 
  - Can view and clone
  - Can create issues
  - Can comment on PRs

Write:
  - All Read permissions
  - Can push to non-protected branches
  - Can create Pull Requests
  - Can merge PRs (after approval)
  - Recommended for developers

Admin:
  - All Write permissions
  - Can change repository settings
  - Can add/remove collaborators
  - Can delete repository
  - Reserved for repository owner
```

### How to Add Collaborators:

1. Go to: https://github.com/arindamdp/stratconsulting-website/settings/access
2. Click "Add people"
3. Enter GitHub username or email
4. Select permission level (Write for most team members)
5. Send invitation

---

## 📁 Code Owners (CODEOWNERS File)

### Location: `.github/CODEOWNERS`

### Current Configuration:

```
# Default owner for everything
* @arindamdp

# HTML files require review from both developer and designer
*.html @arindamdp @developer-username

# JavaScript changes need developer review
*.js @arindamdp @developer-username

# Critical: Contact form changes need senior approval
index.html @arindamdp @senior-dev-username

# Documentation
README.md @arindamdp
GITHUB_GUIDE.md @arindamdp
```

### Purpose:
- Automatically assigns reviewers based on file type
- Ensures critical files get proper review
- Distributes review workload

### How to Update:

1. Edit `.github/CODEOWNERS` file
2. Replace placeholder usernames with actual GitHub usernames
3. Commit and push changes
4. Changes take effect immediately

---

## 🔐 Security Settings

### Dependabot Alerts

```yaml
Status: Enabled (default for private repos)
Purpose: Alerts for vulnerable dependencies
Action: None needed (no npm/package.json dependencies)
```

### Secret Scanning

```yaml
Status: Enabled (for public repos)
Purpose: Detect accidentally committed secrets
Action: Review alerts if any appear
```

### Code Scanning

```yaml
Status: Not configured
Reason: Simple HTML/CSS/JS project, no CI/CD needed
Optional: Can enable GitHub Advanced Security if needed
```

### Security Advisories

```yaml
Status: Available
Purpose: Report security vulnerabilities privately
URL: https://github.com/arindamdp/stratconsulting-website/security/advisories
```

---

## 📧 Form Configuration

### FormSubmit Setup

```yaml
Service: FormSubmit.co
Action URL: https://formsubmit.co/fb959a4120719df5fa8d25498b7858e4
Method: POST

Hidden Fields:
  _subject: "New Contact Form Submission"
  _template: "table"
  _captcha: "true"  # CRITICAL - Server-side spam protection
  _honey: ""        # Honeypot field for bot detection

Form Fields:
  Required:
    - company (text)
    - name (text)
    - email (email)
    - gdprConsent (checkbox)
  
  Optional:
    - phone (tel)
    - industry (text)
    - challenges (textarea)
    - message (textarea)
    - marketingConsent (checkbox)
```

### Email Forwarding

```yaml
Encrypted Email: fb959a4120719df5fa8d25498b7858e4
Forwards To: [Your actual email - not stored in repo]
Provider: FormSubmit.co
```

### reCAPTCHA Configuration

```yaml
Status: REMOVED (as of October 2025)
Reason: Using FormSubmit's built-in captcha instead
Previous Site Key: 6LfL2tkrAAAAABh-ofugH9aoS4i9HevMW2q1K8Jg (deprecated)

Current Protection:
  - FormSubmit server-side captcha (_captcha: true)
  - Client-side email blocking
  - Client-side domain blocking
  - Honeypot field
  - Bot timing detection (3-second minimum)
```

---

## 🚫 Blocked Email List

### Purpose
Prevent spam submissions from known bad actors and disposable email services.

### Location in Code
File: `index.html`  
Section: `<script>` tag, `blockedEmails` array

### Current Blocked Emails (20 addresses)

```javascript
const blockedEmails = [
    'spam@example.com',
    'unwanted@email.com',
    'zekisuquc419@gmail.com',
    'xrumer888@outlook.com',
    'irinademenkova86@gmail.com',
    'sergoworking718@gmail.com',
    'mike@monkeydigital.co',
    'dinanikolskaya99@gmail.com',
    '123bi2@123bi.site',
    'yourmail@gmail.com',
    'yourmail344@gmail.com',
    'xroomer1st@gmail.com',
    'revers711@1ti.ru',
    'info@speed-seo.net',
    'kanemeza1959@gmail.com',
    'info@strictlydigital.net',
    'a88i2@a88i.fit',
    'info@digital-x-press.com',
    'outreachseo56@gmail.com',
    'gor.tor.14@mail.ru',
    'newsletter@wexxon.com',
    'bloomai@getmoreopportunities.info'
];
```

### Current Blocked Domains (8 domains)

```javascript
const blockedDomains = [
    'tempmail.com',
    '10minutemail.com',
    'guerrillamail.com',
    'mailinator.com',
    'throwaway.email',
    'sharklasers.com',
    'getnada.com',
    'trashmail.com'
];
```

### How to Add New Blocks

**Option 1: Direct Edit (for urgent blocks)**
```bash
# Edit index.html
nano index.html

# Find the blockedEmails array
# Add new email: 'newemail@spam.com',
# Save and commit

git add index.html
git commit -m "Block spam email: newemail@spam.com"
git push
```

**Option 2: Pull Request (recommended)**
```bash
git checkout -b fix/block-spam-email
# Edit index.html
git add index.html
git commit -m "Add spam email to blocklist"
git push -u origin fix/block-spam-email
# Create PR on GitHub
```

### Gmail Filter Configuration

**Backup protection** - Set up Gmail filters to block these emails:

```
From: formsubmit.co
Has the words: xrumer888@outlook.com OR irinademenkova86@gmail.com OR zekisuquc419@gmail.com OR [add all blocked emails with OR]
Action: Delete or Move to Spam
```

See: GITHUB_GUIDE.md section "Gmail Filter Setup" for detailed steps.

---

## ⚙️ Git Configuration

### Global Settings (for all team members)

```bash
# User configuration (each member sets their own)
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Line endings (platform-specific)
# Mac/Linux:
git config --global core.autocrlf input

# Windows:
git config --global core.autocrlf true

# Default branch name
git config --global init.defaultBranch main

# Credential helper
# Mac:
git config --global credential.helper osxkeychain

# Windows:
git config --global credential.helper manager-core
```

### Repository-Specific Settings

File: `.gitignore`

```gitignore
# GoDaddy specific files
.htaccess.bak
error_log
.ftpquota

# Temporary files
*.tmp
*.temp
*.log
*.cache

# macOS system files
.DS_Store
.AppleDouble
.LSOverride
._*

# Windows system files
Thumbs.db
desktop.ini

# Editor files
*.swp
*.swo
*~
.vscode/
.idea/

# Backup files
*.bak
*.backup
*_backup

# FTP client files
.ftpconfig
sftp-config.json

# Environment files
.env
.env.local

# Database dumps
*.sql
*.sqlite

# PHP session files
/tmp/
/sessions/
```

---

## 🚀 GitHub Features

### GitHub Actions

```yaml
Status: Not configured
Reason: Simple static site, manual deployment
Future: Could add auto-deploy to GoDaddy via FTP
```

### GitHub Pages

```yaml
Status: Not enabled
Reason: Site hosted on GoDaddy
Alternative: Could use for staging/preview
```

### GitHub Copilot

```yaml
Status: Optional (team member decision)
Cost: $10/month individual or $19/user/month business
Recommendation: Try 30-day free trial first
Documentation: See GITHUB_GUIDE.md "GitHub Copilot" section
```

### GitHub Projects

```yaml
Status: Available but not configured
Use Case: Could track features, bugs, content updates
Setup: https://github.com/arindamdp/stratconsulting-website/projects
```

### Issue Templates

```yaml
Status: Not configured
Future: Could add templates for:
  - Bug reports
  - Feature requests
  - Content updates
  - Security issues
```

---

## 💾 Backup & Recovery

### Backup Strategy

**Primary Backup:** GitHub repository itself

**Additional Backups:**

1. **Local Clone:**
   - Every team member has full repository copy
   - Location: `~/stratconsulting-website/` (Mac) or `~/Documents/stratconsulting-website/` (Windows)

2. **GoDaddy Hosting:**
   - Live site files on production server
   - Access via FTP or File Manager
   - Independent backup of GitHub

3. **Manual Backups (recommended quarterly):**
   ```bash
   # Create timestamped backup
   cd ~
   zip -r stratconsulting-backup-$(date +%Y%m%d).zip stratconsulting-website/
   ```

### Recovery Procedures

**Scenario 1: Deleted Repository**

```bash
# Repository can be restored within 90 days
# Contact GitHub Support: https://support.github.com

# Or recreate from local clone:
cd ~/stratconsulting-website
git remote add origin https://github.com/arindamdp/new-repository-name.git
git push -u origin main
```

**Scenario 2: Corrupted Files**

```bash
# Revert to last known good state
git log --oneline  # Find good commit
git reset --hard COMMIT_HASH
git push --force
```

**Scenario 3: Accidental Force Push**

```bash
# Find lost commits
git reflog

# Restore from reflog
git reset --hard HEAD@{n}
git push --force
```

**Scenario 4: Need to Restore from GoDaddy**

1. Download files from GoDaddy via FTP/File Manager
2. Compare with local repository
3. Commit any differences
4. Push to GitHub

---

## 📊 Monitoring & Maintenance

### Regular Checks (Monthly)

- [ ] Review blocked email list - add new spam addresses
- [ ] Check for security advisories
- [ ] Verify all collaborators still need access
- [ ] Review commit history for anomalies
- [ ] Test form submissions
- [ ] Verify GoDaddy hosting is in sync

### Quarterly Tasks

- [ ] Create manual backup
- [ ] Review and update documentation
- [ ] Check GitHub storage usage
- [ ] Verify SSL certificate on GoDaddy
- [ ] Update blocked domain list

### Annual Tasks

- [ ] Review GitHub subscription (stay free vs upgrade)
- [ ] Renew/rotate Personal Access Tokens
- [ ] Security audit of form handling
- [ ] Review team member access levels
- [ ] Update contact information

---

## 🔄 Migration Procedures

### Moving to New GitHub Account

If you ever need to transfer ownership:

```bash
# Option 1: Transfer repository
# Settings → General → Transfer ownership

# Option 2: Fork and update
# Fork repository to new account
# Update remote URLs:
git remote set-url origin https://github.com/new-account/stratconsulting-website.git
git push
```

### Moving to GitHub Organization

For better team management:

1. Create organization: https://github.com/organizations/new
2. Transfer repository to organization
3. Set up teams and permissions
4. Update all documentation references

---

## 📞 Emergency Contacts

### Repository Owner
- **GitHub:** @arindamdp
- **Email:** hello@stratconsulting.co.uk

### Service Providers
- **Hosting:** GoDaddy (account: [your account])
- **Domain:** GoDaddy
- **Form Service:** FormSubmit.co (no account needed)
- **GitHub Support:** https://support.github.com

### Key URLs
- **Repository:** https://github.com/arindamdp/stratconsulting-website
- **Live Site:** https://www.stratconsulting.co.uk
- **GoDaddy Dashboard:** https://www.godaddy.com/
- **FormSubmit Dashboard:** https://formsubmit.co/dashboard (if registered)

---

## 📝 Change Log

### October 2025
- ✅ Repository created
- ✅ Initial commit with website files
- ✅ Added .gitignore configuration
- ✅ Created GITHUB_GUIDE.md for team
- ✅ Configured FormSubmit form handler
- ✅ Removed Google reCAPTCHA (switched to FormSubmit captcha)
- ✅ Added 20 email addresses to block list
- ✅ Added 8 domains to block list
- ✅ Documented all configurations
- ✅ Added Windows support to guide
- ✅ Added GitHub Copilot review documentation

### Future Updates
- [ ] Enable branch protection (if upgraded or made public)
- [ ] Add CODEOWNERS file with real usernames
- [ ] Set up GitHub Actions for auto-deploy
- [ ] Configure issue templates
- [ ] Add more team members

---

## 🎓 Training Resources

**For New Team Members:**
- Read: GITHUB_GUIDE.md (comprehensive guide)
- Watch: [Record a quick loom video of workflow]
- Practice: Create test PR for review

**External Resources:**
- Git Basics: https://git-scm.com/book/en/v2
- GitHub Docs: https://docs.github.com
- FormSubmit Docs: https://formsubmit.co/documentation

---

## ✅ Configuration Verification Checklist

Use this to verify setup is correct:

**Repository Level:**
- [ ] Repository is private (or public for branch protection)
- [ ] Default branch is `main`
- [ ] All team members added as collaborators
- [ ] .gitignore file present and correct

**Security:**
- [ ] 20 emails blocked in index.html
- [ ] 8 domains blocked in index.html
- [ ] FormSubmit _captcha set to "true"
- [ ] Honeypot field present
- [ ] No sensitive data in repository

**Documentation:**
- [ ] README.md exists
- [ ] GITHUB_GUIDE.md exists and updated
- [ ] REPOSITORY_CONFIG.md exists (this file)
- [ ] All team members have access to docs

**Form Configuration:**
- [ ] FormSubmit action URL correct
- [ ] All form fields working
- [ ] Test submission successful
- [ ] Email received correctly
- [ ] Blocked email test fails (correct behavior)

**Git Configuration:**
- [ ] All team members configured Git
- [ ] Personal Access Tokens created
- [ ] First successful push completed
- [ ] Pull Request workflow tested

---

## 📄 Document Version

**Version:** 1.0  
**Created:** October 2025  
**Last Updated:** October 2025  
**Next Review:** January 2026

---

**Maintainer:** @arindamdp  
**For Questions:** hello@stratconsulting.co.uk
