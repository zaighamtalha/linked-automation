# 🔑 API Keys Reference Guide
## Complete Guide to Getting All Required Keys

This guide shows you exactly what each API key looks like and where to find them.

---

## 📋 **Required Keys Overview**

| **Service** | **Key Type** | **Format** | **Where to Get** |
|-------------|--------------|------------|------------------|
| **GitHub** | Personal Access Token | `ghp_...` | GitHub Settings |
| **LinkedIn** | Organization ID | `123456789` | LinkedIn Company Page |
| **Google** | Gemini API Key | `AIza...` | Google AI Studio |
| **Email** | SMTP Credentials | Username/Password | Your Email Provider |

---

## 🐙 **GitHub Personal Access Token**

### **What It Looks Like:**
```
ghp_1234567890abcdef1234567890abcdef12345678
```
- **Length:** 40 characters
- **Starts with:** `ghp_` (classic) or `gho_` (fine-grained)
- **Contains:** Letters and numbers only

### **How to Get It:**

1. **Go to GitHub.com** and sign in
2. **Click your profile picture** (top right) → **Settings**
3. **Scroll down** in the left sidebar → **Developer settings**
4. **Click "Personal access tokens"** → **"Tokens (classic)"**
5. **Click "Generate new token"** → **"Generate new token (classic)"**

### **Token Settings:**
```
Note: LinkedIn Automation
Expiration: 90 days (or your preference)
Scopes (check these boxes):
✅ repo (Full control of private repositories)
✅ read:user (Read user profile data)  
✅ read:org (Read org and team membership)
```

### **Important:**
- ⚠️ **Copy immediately** - you won't see it again!
- 🔒 **Keep it secret** - don't share with anyone
- 📅 **Set expiration** - tokens expire for security

---

## 💼 **LinkedIn Organization ID**

### **What It Looks Like:**
```
123456789
```
- **Format:** 9-digit number
- **Example:** `108924016`
- **Found in:** LinkedIn company page URL

### **How to Get It:**

#### **Option A: From Existing Company Page**
1. **Go to LinkedIn.com** and sign in
2. **Click "Work"** → **"Company pages"**
3. **Click your company page**
4. **Look at the URL:** `https://www.linkedin.com/company/123456789/`
5. **Copy the number:** `123456789`

#### **Option B: Create New Company Page**
1. **Go to LinkedIn.com** → **"Work"**
2. **Click "Create a company page"**
3. **Fill in company details**
4. **After creation, check the URL for your ID**

### **Example URLs:**
```
https://www.linkedin.com/company/microsoft/ → ID: 1035
https://www.linkedin.com/company/google/ → ID: 1441
https://www.linkedin.com/company/123456789/ → ID: 123456789
```

---

## 🤖 **Google Gemini API Key**

### **What It Looks Like:**
```
AIzaSyCLZkBl_BM3MV27Pt6yBSJNs88dvcUzih4
```
- **Length:** 39 characters
- **Starts with:** `AIza`
- **Contains:** Letters, numbers, and underscores

### **How to Get It:**

1. **Go to [Google AI Studio](https://aistudio.google.com/)**
2. **Sign in** with your Google account
3. **Click "Get API Key"** (top right)
4. **Click "Create API Key"**
5. **Choose project** (or create new one)
6. **Copy the key** (starts with `AIza`)

### **Important:**
- 🔒 **Keep it secure** - don't share publicly
- 💰 **Free tier available** - check usage limits
- 🔄 **Regenerate if compromised** - security best practice

---

## 📧 **Email SMTP Credentials**

### **Gmail Setup (Recommended)**

#### **What You Need:**
```
SMTP Server: smtp.gmail.com
Port: 587
Username: your-email@gmail.com
Password: your-app-password (NOT your regular password)
Security: STARTTLS
```

#### **How to Get Gmail App Password:**

1. **Go to [Google Account Settings](https://myaccount.google.com/)**
2. **Security** → **2-Step Verification** (enable if not already)
3. **Security** → **App passwords**
4. **Select app:** Mail
5. **Select device:** Other (name it "n8n")
6. **Copy the 16-character password**

#### **Example Gmail Credentials:**
```
Host: smtp.gmail.com
Port: 587
User: john.doe@gmail.com
Password: abcd efgh ijkl mnop
Secure: STARTTLS
```

### **Outlook Setup**

#### **What You Need:**
```
SMTP Server: smtp-mail.outlook.com
Port: 587
Username: your-email@outlook.com
Password: your-regular-password
Security: STARTTLS
```

#### **Example Outlook Credentials:**
```
Host: smtp-mail.outlook.com
Port: 587
User: jane.smith@outlook.com
Password: YourRegularPassword123
Secure: STARTTLS
```

### **Other Email Providers:**

#### **Yahoo:**
```
Host: smtp.mail.yahoo.com
Port: 587
Security: STARTTLS
```

#### **Custom Domain:**
```
Host: mail.yourdomain.com
Port: 587 or 465
Security: STARTTLS or SSL
```

---

## 🔐 **Security Best Practices**

### **Key Management:**
- 🔒 **Never commit keys to code**
- 🔄 **Rotate keys regularly**
- 📝 **Use environment variables**
- 🚫 **Don't share keys in chat/email**

### **Storage:**
- 💾 **Save keys in password manager**
- 📱 **Use secure notes app**
- 🗂️ **Keep backup copies**
- ⏰ **Set expiration reminders**

### **Usage:**
- 🎯 **Use least privilege principle**
- 📊 **Monitor usage regularly**
- 🚨 **Set up alerts for unusual activity**
- 🔍 **Review access logs**

---

## 🧪 **Testing Your Keys**

### **GitHub Token Test:**
```bash
curl -H "Authorization: token YOUR_GITHUB_TOKEN" \
     https://api.github.com/user
```

### **LinkedIn Organization Test:**
```bash
curl -H "Authorization: Bearer YOUR_LINKEDIN_TOKEN" \
     https://api.linkedin.com/v2/organizations/YOUR_ORG_ID
```

### **Gemini API Test:**
```bash
curl -H "Authorization: Bearer YOUR_GEMINI_KEY" \
     -H "Content-Type: application/json" \
     -d '{"contents":[{"parts":[{"text":"Hello"}]}]}' \
     https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent
```

### **Email SMTP Test:**
Use n8n's built-in credential tester or any SMTP testing tool.

---

## ❓ **Common Issues & Solutions**

### **"Invalid GitHub Token"**
- ✅ Check token has correct scopes
- ✅ Verify token hasn't expired
- ✅ Ensure repository is accessible

### **"LinkedIn Organization Not Found"**
- ✅ Verify Organization ID is correct
- ✅ Check you have admin access
- ✅ Ensure company page exists

### **"Gemini API Quota Exceeded"**
- ✅ Check usage in Google AI Studio
- ✅ Wait for quota reset
- ✅ Consider upgrading plan

### **"SMTP Authentication Failed"**
- ✅ Use app password for Gmail
- ✅ Check username/password
- ✅ Verify SMTP settings

---

## 📞 **Getting Help**

### **If You're Stuck:**
1. **Check this guide** for your specific service
2. **Verify key format** matches examples
3. **Test keys individually** before using
4. **Check service documentation**

### **Support Resources:**
- **GitHub:** [Personal Access Tokens Guide](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token)
- **LinkedIn:** [Organization API Documentation](https://docs.microsoft.com/en-us/linkedin/)
- **Google:** [Gemini API Documentation](https://ai.google.dev/docs)
- **n8n:** [Community Forum](https://community.n8n.io)

---

## ✅ **Quick Checklist**

Before setting up your automation, ensure you have:

- [ ] **GitHub Personal Access Token** (40 characters, starts with `ghp_`)
- [ ] **LinkedIn Organization ID** (9-digit number)
- [ ] **Google Gemini API Key** (39 characters, starts with `AIza`)
- [ ] **Email SMTP Credentials** (username, password, server, port)
- [ ] **All keys saved securely**
- [ ] **Keys tested individually**

---

**You're ready to set up your LinkedIn automation!** 🚀

*Last updated: September 2025*
