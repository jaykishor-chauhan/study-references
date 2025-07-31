# 📧 SendGrid Email Integration with Node.js

A simple and secure way to send transactional or test emails using [SendGrid](https://sendgrid.com) with Node.js.

---

## 🚀 Features

- 📤 Send emails using SendGrid’s Email API
- 🔐 Secure API key handling with `.env`
- 📨 Supports verified sender identity
- 🧱 Clean, modular, and easy-to-integrate code

---

## 🛠️ Requirements

- Node.js installed (v14+ recommended)
- npm or yarn
- Verified email address
- A free [SendGrid account](https://sendgrid.com)

---

## 📝 Step-by-Step Setup Guide

### ✅ 1. Create a SendGrid Account

- Visit [https://sendgrid.com](https://sendgrid.com)
- Click **Start for Free**
- Complete the signup process
- Verify your email and enable Two-Factor Authentication (2FA)

---

### ✅ 2. Generate API Key

1. Log in to SendGrid and go to **Settings → API Keys**
2. Click **Create API Key**
   - Name: `MyAppKey or any other name`
   - Permissions: Full Access or "Mail Send" only
3. Click **Create & View**
4. **Copy** the key immediately — you won’t see it again!

---

### ✅ 3. Verify a Sender Email

1. Go to **Settings → Sender Authentication**
2. Select **Single Sender Verification**
3. Enter your name and verified email address
4. Click the verification link sent to your inbox

---

### ✅ 4. Set Environment variable

```bash
// .env

SENDGRID_API_KEY= your_sendgrid_api_key_here
FROM_EMAIL= your_verified_sender_email@example.com

```

### ✅ 5. sendMail Sample Code Snipped

```javascript
// sendMail.js

const sgMail = require('@sendgrid/mail');
require('dotenv').config();

sgMail.setApiKey(process.env.SENDGRID_API_KEY);

async function sendTestEmail(recipientEmail) {
  const mailContainer = {
    from: {
      email: process.env.FROM_EMAIL,
      name: 'BusConnect - SendGrid Test'
    },
    to: recipientEmail,
    subject: 'SendGrid Test Email',
    text: 'This is a test email to verify SendGrid integration.',
    html: `
      <div style="font-family: Arial, sans-serif; background-color: #f9f9f9; padding: 20px;">
        <h2 style="color: #333;">📧 SendGrid Test Email</h2>
        <p>Hello 👋</p>
        <p>This is a test email sent using SendGrid and Node.js integration.</p>
        <p style="color: #888;">Thank you!</p>
      </div>
    `
  };

  try {
    await sgMail.send(mailContainer);
    console.log(`✅ Email sent successfully to ${recipientEmail}`);
  } catch (error) {
    console.error('❌ Failed to send email:');
    console.error(error.response?.body || error.message);
  }
}

// Example usage:
// Replace 'recipient@example.com' with your actual recipient email
sendTestEmail('recipient@example.com');


```


### ✅ 6. Install Dependencies

```bash
npm install @sendgrid/mail

```

### ✅ 7. Run

```bash
node sendMail.js

```

### ✅ 8. If successful, you’ll see

```bash
✅ Email sent successfully to recipient@example.com
```

