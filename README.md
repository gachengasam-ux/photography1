   This README provides a professional overview of your project, covering the setup, features, and security considerations for the contact form.

***

# Sam's Photography Portfolio

A modern, responsive photography portfolio website designed to showcase a professional gallery and handle client inquiries through a secure contact form.

## 🚀 Features

*   **Responsive Gallery**: A dynamic grid layout that adjusts to any screen size (mobile, tablet, or desktop).
*   **Modern UI/UX**: Clean, professional aesthetic with subtle hover animations and clear typography.
*   **Optimized Contact Form**: 
    *   **Input Validation**: Uses HTML5 attributes to ensure email formatting and character limits.
    *   **Anti-Spam Honeypot**: Includes a hidden field to trap automated bots without bothering real users.
    *   **Subject Selection**: Integrated dropdown for better lead categorization.

## 📁 Project Structure

```text
.
├── index.html          # Main website structure
├── style.css           # Modern styling and layout rules
└── assets/
    └── images/         # Project images (image 1.jpg, etc.)
```

## 🛠️ Installation & Setup

1.  **Clone or Download**: Save the `index.html` and `style.css` files into your project folder.
2.  **Images**: Place your photography samples in the `assets/images/` directory. Ensure they are named `image 1.jpg`, `image 2.jpg`, etc., or update the `src` tags in the HTML.
3.  **Local Preview**: Simply open `index.html` in any modern web browser to view the site.

## 🔒 Security Implementation (Form)

The contact form is designed with a "security-in-depth" mindset:

1.  **Client-Side Validation**: `maxlength` attributes prevent excessively large data payloads, and `type="email"` ensures basic format correctness before submission.
2.  **Honeypot Logic**: The hidden `honeypot` field should be checked in your backend script (`submit_page.php`).
    *   *Backend Logic Example:* `if (!empty($_POST['honeypot'])) { die("Bot detected"); }`
3.  **POST Method**: Uses `method="post"` to ensure user data is not exposed in server logs or browser history via URL parameters.

## 📝 Backend Integration

To process the form submissions, ensure your server-side script (`submit_page.php`) handles the following:
*   Sanitization of inputs using `htmlspecialchars()` to prevent **Cross-Site Scripting (XSS)**.
*   Validation of the CSRF token (if implemented).
*   Protection against **Email Header Injection** if using the data to send an email notification.

---
*© 2024 Sam's Photography. Built for professional storytelling.*     