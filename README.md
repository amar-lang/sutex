# Sutex Website

This is the official website for Sutex, an Udyam registered IT startup specializing in web and mobile app development.

## Email Integration Setup

The website uses EmailJS to handle form submissions without requiring a backend server. Follow these steps to set up the email functionality:

### 1. Create an EmailJS Account

1. Go to [EmailJS](https://www.emailjs.com/) and create an account
2. Verify your email address

### 2. Create an Email Service

1. In your EmailJS dashboard, go to "Email Services"
2. Click "Add New Service"
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the instructions to connect your email account

### 3. Create Email Templates

You need to create two email templates:

#### Contact Form Template
1. Go to "Email Templates" in your EmailJS dashboard
2. Click "Create New Template"
3. Name it (e.g., "Contact Form")
4. Design your email template using these variables:
   - `{{from_name}}` - The name of the person contacting you
   - `{{from_email}}` - The email address of the person contacting you
   - `{{phone_number}}` - The phone number provided
   - `{{message}}` - The message content
5. Save the template and note the Template ID

#### Newsletter Template
1. Create another template for newsletter subscriptions
2. Name it (e.g., "Newsletter Subscription")
3. Design your email template using this variable:
   - `{{subscriber_email}}` - The email address of the subscriber
4. Save the template and note the Template ID

### 4. Update the Website Code

1. Open `index.html` in a code editor
2. Find this line near the top of the file:
   ```javascript
   emailjs.init("YOUR_PUBLIC_KEY");
   ```
3. Replace `YOUR_PUBLIC_KEY` with your EmailJS public key (found in Account > API Keys)

4. Find these lines in the JavaScript section:
   ```javascript
   emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)
   ```
   and
   ```javascript
   emailjs.send('YOUR_SERVICE_ID', 'YOUR_NEWSLETTER_TEMPLATE_ID', templateParams)
   ```

5. Replace:
   - `YOUR_SERVICE_ID` with your EmailJS service ID
   - `YOUR_TEMPLATE_ID` with your contact form template ID
   - `YOUR_NEWSLETTER_TEMPLATE_ID` with your newsletter template ID

### 5. Test the Forms

After setting up EmailJS and updating the code, test all forms to make sure emails are being sent correctly:
- Contact form
- Main subscription form
- Footer subscription form

## Additional Information

- The website is designed to be fully responsive
- All form submissions use client-side validation
- Success and error messages are displayed to users after form submission 