# Contact Page Setup Instructions

## Overview
A fully integrated contact page has been added to your PVHS Pathways site with:
- ✅ Bilingual support (English/Spanish)
- ✅ Responsive design matching your existing aesthetic  
- ✅ Form validation
- ✅ Email delivery via Formspree
- ✅ Success/error messaging

## Files Modified/Created

### Modified:
- `index.html` - Added contact page HTML, CSS, and JavaScript

### Created:
- `_data/contact.json` - Bilingual content for the contact page
- `contact 2.JSON` - Updated version (you can delete the original `contact.JSON`)

## Setting Up Email Delivery with Formspree

### Step 1: Create a Formspree Account
1. Go to [https://formspree.io/](https://formspree.io/)
2. Click "Get Started" and sign up (free account is perfect)
3. Verify your email address

### Step 2: Create a New Form
1. In your Formspree dashboard, click "+ New Form"
2. Give it a name like "PVHS Pathways Contact Form"
3. Click "Create Form"

### Step 3: Get Your Form ID
1. After creating the form, you'll see your form endpoint
2. It will look like: `https://formspree.io/f/YOUR_FORM_ID`
3. Copy the part that says `YOUR_FORM_ID` (e.g., `xyzabc123`)

### Step 4: Update index.html
1. Open `index.html`
2. Find this line (around line 540):
   ```javascript
   const response=await fetch('https://formspree.io/f/YOUR_FORM_ID',{
   ```
3. Replace `YOUR_FORM_ID` with your actual Formspree form ID
4. Save the file

### Step 5: Configure Formspree (Optional but Recommended)
In your Formspree dashboard, you can:
- **Set notification email**: Choose where form submissions are sent (default is your account email)
- **Add reCAPTCHA**: Prevent spam (free with Formspree)
- **Customize reply-to**: Auto-set reply address to the form submitter
- **Add webhooks**: Integrate with other services

### Step 6: Test Your Form
1. Open your site
2. Click "Contact" in the navigation
3. Fill out and submit the form
4. Check your email for the submission
5. Verify success message appears

## How It Works

1. User fills out the contact form
2. JavaScript prevents default form submission
3. Form data is sent to Formspree via API
4. Formspree forwards the email to you
5. User sees success/error message based on response
6. Form resets on successful submission

## Customization Options

### Change Contact Information
Edit `_data/contact.json`:
```json
"contact_info": {
  "phone": "(775) 727-4434",
  "email": "bodegard@nyeschools.org",
  "address": "484 S West St., Pahrump, NV 89048"
}
```

### Change Colors
The contact page uses blue (`#3b82f6`) as its accent color. To change it, search for `#3b82f6` in the contact section of `index.html` and replace with your preferred color.

### Adjust Layout
The contact page uses a 2-column grid on desktop:
- Left: Contact form (60% width)
- Right: Contact info cards (40% width)

On mobile (< 900px), it stacks vertically.

## Navigation

The contact page is automatically added to your navigation bar with:
- English label: "Contact"
- Spanish label: "Contacto"
- Blue hover color
- Seamless integration with existing nav system

## Troubleshooting

### Form not submitting
- Check browser console for errors
- Verify your Formspree form ID is correct
- Check your internet connection

### Not receiving emails
- Check spam folder
- Verify notification email in Formspree dashboard
- Check Formspree submission log

### Styling looks off
- Clear browser cache
- Check for CSS conflicts
- Verify all files are uploaded correctly

## Formspree Free Tier Limits
- 50 submissions per month
- Basic spam filtering
- Email notifications
- Form analytics

If you need more, Formspree paid plans start at $10/month for 1,000 submissions.

## Alternative: Using Your Own Backend

If you prefer not to use Formspree, you can:
1. Set up a PHP mail script
2. Use Netlify Forms (if hosted on Netlify)
3. Use AWS SES or SendGrid
4. Use any other form handling service

Just replace the fetch URL in the form handler with your endpoint.

## Support

If you need help:
- Formspree Docs: https://help.formspree.io/
- Formspree Support: support@formspree.io

---

**Created for PVHS Pathways**
*Matching your existing design system with dark theme, JetBrains Mono fonts, and responsive layout.*
