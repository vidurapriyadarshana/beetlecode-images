# BeetleCode Email Design System & Template Guide

A complete reference guide and design specification for creating clean, minimalist, and highly compatible email templates for **BeetleCode (`BEETLECODE (PVT) LTD`)**.

---

## 1. Design Principles

* **Minimalist & Professional**: Pure white card, high-contrast typography, no flashy animations, and no hover effects.
* **Email Client Bulletproof**: Optimized for 100% consistent rendering across Gmail (Desktop & Mobile), Apple Mail, Microsoft Outlook (Desktop, Web, App), and Yahoo Mail.
* **Table-Based Layout**: Uses fixed-width container tables (`600px` max width) with responsive CSS media queries for smaller mobile screens (`max-width: 620px`).
* **Official Brand Footprint**: Standardized footer pointing to the official website [https://beetlecode.com](https://beetlecode.com) with legal entity details and confidentiality disclaimers.

---

## 2. Color Palette & Design Tokens

| Token Name | Hex Code | Visual Sample | Usage |
| :--- | :--- | :--- | :--- |
| **Primary Brand Red** | `#FA0913` | 🔴 | CTA Buttons, brand highlights, active links |
| **Primary Dark Text** | `#111827` | ⬛ | Headings (`h1`-`h3`), greeting titles, company name |
| **Body Text** | `#374151` | ◼️ | Main paragraph body text, detailed descriptions |
| **Muted Text / Labels** | `#6B7280` | ◽ | Field labels (`Date:`, `Time:`), subtitle notes |
| **Footer Muted Text** | `#9CA3AF` | ◽ | Copyright notice, confidentiality disclaimers |
| **Email Canvas Background** | `#F6F7F9` | ⬜ | Outer wrapper background (outside the email card) |
| **Card Background** | `#FFFFFF` | ⬜ | Main container email body |
| **Info / Details Box Bg** | `#FAFAFA` | ⬜ | Structured data boxes (Interview Details, Program Outline) |
| **Footer Background** | `#FBFCFD` | ⬜ | Bottom footer block |
| **Border / Divider** | `#E5E7EB` | ◽ | Container borders, card outlines, header dividers |
| **Inner Divider** | `#F0F2F5` | ◽ | Sub-section dividers in header & footer |

---

## 3. Typography & Spacing Specifications

### Font Family
Always use the system font stack for instant loading without external font rendering delays:
```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
```

### Type Scale
* **Greeting / Main Headers**: `15px` – `16px` | Weight: `600` / `700` | Line Height: `1.5` | Color: `#111827`
* **Body Paragraphs**: `14.5px` | Weight: `400` | Line Height: `1.7` | Color: `#374151`
* **Section / Card Titles**: `14px` | Weight: `700` | Line Height: `1.4` | Color: `#111827`
* **Field Labels**: `13.5px` | Weight: `600` | Line Height: `1.6` | Color: `#6B7280`
* **CTA Button Text**: `14px` | Weight: `600` | Color: `#FFFFFF`
* **Footer Company Name**: `13px` | Weight: `700` | Color: `#111827`
* **Footer Subtitle & Links**: `12px` | Weight: `400` / `600` | Color: `#4B5563` / `#FA0913`
* **Footer Legal / Disclaimer**: `11.5px` | Weight: `400` | Line Height: `1.6` | Color: `#9CA3AF`

### Sizing & Grid Dimensions
* **Container Max Width**: `600px` (centered).
* **Outer Padding**: `30px 0 40px 0` on desktop, `0 12px` horizontal gutter.
* **Content Padding**: `36px 36px 28px 36px` on desktop, `24px 20px` on mobile.
* **Header Padding**: `24px 32px` on desktop, `20px 20px` on mobile.
* **Footer Padding**: `28px 36px` on desktop, `24px 20px` on mobile.
* **Border Radius**: `4px` on main container and details boxes.

---

## 4. Hosted Brand Assets

* **BeetleCode Dark Logo**:
  ```html
  https://raw.githubusercontent.com/vidurapriyadarshana/beetlecode-images/main/images/BeetleCode-logo-dark.png
  ```
  *(Display dimensions: `width="135"` | `height="auto"`)*

* **Hero Banner Graphic**:
  ```html
  https://raw.githubusercontent.com/vidurapriyadarshana/beetlecode-images/main/images/Screenshot_From_2026-08-29_21-46-21.png
  ```
  *(Display dimensions: `width="600"` | `max-width: 600px` | full width of container)*

---

## 5. Standard Component Snippets

### A. Top Header (Logo + Banner)
```html
<!-- 1. Top Logo Header -->
<tr>
    <td class="header-padding" align="center" style="background-color: #ffffff; padding: 24px 32px; border-bottom: 1px solid #f0f2f5;">
        <a href="https://beetlecode.com" target="_blank" style="text-decoration: none; display: inline-block;">
            <img src="https://raw.githubusercontent.com/vidurapriyadarshana/beetlecode-images/main/images/BeetleCode-logo-dark.png" alt="BeetleCode" width="135" style="display: block; width: 135px; max-width: 100%; height: auto; margin: 0 auto; border: 0;">
        </a>
    </td>
</tr>

<!-- 2. Top Banner Image -->
<tr>
    <td style="padding: 0; margin: 0; background-color: #ffffff; line-height: 0;">
        <img src="https://raw.githubusercontent.com/vidurapriyadarshana/beetlecode-images/main/images/Screenshot_From_2026-08-29_21-46-21.png" alt="BeetleCode Banner" width="600" style="display: block; width: 100%; max-width: 600px; height: auto; margin: 0 auto; border: 0;">
    </td>
</tr>
```

---

### B. Minimalist Details Box (Without Side Red Line)
```html
<!-- Details Box -->
<table width="100%" cellpadding="0" cellspacing="0" border="0" style="background-color: #fafafa; border: 1px solid #e5e7eb; border-radius: 4px; margin: 0 0 24px 0;">
    <tbody>
        <tr>
            <td class="details-cell" style="padding: 18px 20px;">
                <p style="margin: 0 0 12px 0; color: #111827; font-size: 14px; font-weight: 700;">
                    Details Title
                </p>
                <table width="100%" cellpadding="0" cellspacing="0" border="0" style="font-size: 13.5px; line-height: 1.6;">
                    <tbody>
                        <tr>
                            <td width="95" valign="top" style="color: #6b7280; font-weight: 600; padding: 4px 0;">Field 1:</td>
                            <td valign="top" style="color: #111827; font-weight: 600; padding: 4px 0;">Value 1</td>
                        </tr>
                        <tr>
                            <td width="95" valign="top" style="color: #6b7280; font-weight: 600; padding: 4px 0;">Field 2:</td>
                            <td valign="top" style="color: #374151; padding: 4px 0;">Value 2 description</td>
                        </tr>
                    </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>
```

---

### C. Flat Minimalist CTA Button
```html
<!-- CTA Button -->
<table width="100%" cellpadding="0" cellspacing="0" border="0" style="margin: 0 0 28px 0;">
    <tbody>
        <tr>
            <td align="left">
                <a href="https://example.com" target="_blank" class="btn-cta" style="display: inline-block; background-color: #fa0913; color: #ffffff; text-decoration: none; font-size: 14px; font-weight: 600; padding: 11px 24px; border-radius: 3px; text-align: center;">
                    Action Button Text
                </a>
            </td>
        </tr>
    </tbody>
</table>
```

---

### D. Official Website Branded Footer
```html
<!-- 4. Clean Professional HTML Footer -->
<tr>
    <td class="footer-padding" style="background-color: #fbfcfd; border-top: 1px solid #e5e7eb; padding: 28px 36px; text-align: left;">
        <table width="100%" cellpadding="0" cellspacing="0" border="0">
            <tbody>
                <tr>
                    <td style="padding-bottom: 12px;">
                        <a href="https://beetlecode.com" target="_blank" style="text-decoration: none; color: #111827; font-size: 13px; font-weight: 700; letter-spacing: 0.3px;">
                            BEETLECODE (PVT) LTD
                        </a>
                        <p style="margin: 4px 0 0 0; color: #6b7280; font-size: 12px; line-height: 1.5;">
                            AI-Driven Software &bull; IoT Ecosystems &bull; Digital Growth Solutions
                        </p>
                    </td>
                </tr>
                <tr>
                    <td style="padding: 10px 0; border-top: 1px solid #f0f2f5; border-bottom: 1px solid #f0f2f5;">
                        <table cellpadding="0" cellspacing="0" border="0">
                            <tbody>
                                <tr>
                                    <td style="padding-right: 16px;">
                                        <a href="https://beetlecode.com" target="_blank" style="color: #fa0913; font-size: 12px; font-weight: 600; text-decoration: none;">
                                            Official Website
                                        </a>
                                    </td>
                                    <td style="padding-right: 16px; color: #d1d5db;">|</td>
                                    <td style="padding-right: 16px;">
                                        <a href="https://beetlecode.com/contact" target="_blank" style="color: #4b5563; font-size: 12px; text-decoration: none;">
                                            Contact Us
                                        </a>
                                    </td>
                                    <td style="padding-right: 16px; color: #d1d5db;">|</td>
                                    <td>
                                        <a href="mailto:info@beetlecode.com" style="color: #4b5563; font-size: 12px; text-decoration: none;">
                                            info@beetlecode.com
                                        </a>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </td>
                </tr>
                <tr>
                    <td style="padding-top: 12px;">
                        <p style="margin: 0; color: #9ca3af; font-size: 11.5px; line-height: 1.6;">
                            &copy; 2026 BEETLECODE (PVT) LTD. All rights reserved.<br>
                            This message and any attachments are confidential and intended solely for the intended recipient.
                        </p>
                    </td>
                </tr>
            </tbody>
        </table>
    </td>
</tr>
```

---

## 6. Complete Starter Template (Copy-Paste Ready)

Use this complete boilerplate whenever creating a new email template:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>{{email_subject}} - BeetleCode</title>
    <style>
        body, table, td, p, a, li {
            -webkit-text-size-adjust: 100%;
            -ms-text-size-adjust: 100%;
        }
        table, td {
            mso-table-lspace: 0pt;
            mso-table-rspace: 0pt;
        }
        img {
            -ms-interpolation-mode: bicubic;
            border: 0;
            outline: none;
            text-decoration: none;
            display: block;
        }
        body {
            margin: 0;
            padding: 0;
            width: 100% !important;
            min-width: 100%;
            background-color: #f6f7f9;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            color: #2b2f38;
            -webkit-font-smoothing: antialiased;
        }
        @media only screen and (max-width: 620px) {
            .email-container {
                width: 100% !important;
                border-radius: 0 !important;
            }
            .content-padding {
                padding: 24px 20px !important;
            }
            .header-padding {
                padding: 20px 20px !important;
            }
            .footer-padding {
                padding: 24px 20px !important;
            }
            .details-cell {
                padding: 16px !important;
            }
            .btn-cta {
                display: block !important;
                width: 100% !important;
                box-sizing: border-box !important;
            }
        }
    </style>
</head>
<body style="margin: 0; padding: 0; background-color: #f6f7f9; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;">
    <table width="100%" cellpadding="0" cellspacing="0" border="0" style="background-color: #f6f7f9; padding: 30px 0 40px 0;">
        <tbody>
            <tr>
                <td align="center" style="padding: 0 12px;">
                    
                    <!-- Main Container Card -->
                    <table class="email-container" width="600" cellpadding="0" cellspacing="0" border="0" style="width: 100%; max-width: 600px; background-color: #ffffff; border: 1px solid #e5e7eb; border-radius: 4px; overflow: hidden;">
                        <tbody>

                            <!-- 1. Top Logo Header -->
                            <tr>
                                <td class="header-padding" align="center" style="background-color: #ffffff; padding: 24px 32px; border-bottom: 1px solid #f0f2f5;">
                                    <a href="https://beetlecode.com" target="_blank" style="text-decoration: none; display: inline-block;">
                                        <img src="https://raw.githubusercontent.com/vidurapriyadarshana/beetlecode-images/main/images/BeetleCode-logo-dark.png" alt="BeetleCode" width="135" style="display: block; width: 135px; max-width: 100%; height: auto; margin: 0 auto; border: 0;">
                                    </a>
                                </td>
                            </tr>

                            <!-- 2. Top Banner Image -->
                            <tr>
                                <td style="padding: 0; margin: 0; background-color: #ffffff; line-height: 0;">
                                    <img src="https://raw.githubusercontent.com/vidurapriyadarshana/beetlecode-images/main/images/Screenshot_From_2026-08-29_21-46-21.png" alt="BeetleCode Banner" width="600" style="display: block; width: 100%; max-width: 600px; height: auto; margin: 0 auto; border: 0;">
                                </td>
                            </tr>

                            <!-- 3. Body Content Area -->
                            <tr>
                                <td class="content-padding" style="padding: 36px 36px 28px 36px;">

                                    <!-- Greeting -->
                                    <p style="margin: 0 0 16px 0; color: #111827; font-size: 15px; font-weight: 600; line-height: 1.5;">
                                        Hi {{recipient_name}},
                                    </p>

                                    <!-- Body Message -->
                                    <p style="margin: 0 0 16px 0; color: #374151; font-size: 14.5px; line-height: 1.7;">
                                        Enter your main email body message here. Keep paragraphs concise and easy to read.
                                    </p>

                                    <!-- Details Box (Optional) -->
                                    <table width="100%" cellpadding="0" cellspacing="0" border="0" style="background-color: #fafafa; border: 1px solid #e5e7eb; border-radius: 4px; margin: 0 0 24px 0;">
                                        <tbody>
                                            <tr>
                                                <td class="details-cell" style="padding: 18px 20px;">
                                                    <p style="margin: 0 0 12px 0; color: #111827; font-size: 14px; font-weight: 700;">
                                                        Overview
                                                    </p>
                                                    <table width="100%" cellpadding="0" cellspacing="0" border="0" style="font-size: 13.5px; line-height: 1.6;">
                                                        <tbody>
                                                            <tr>
                                                                <td width="95" valign="top" style="color: #6b7280; font-weight: 600; padding: 4px 0;">Item:</td>
                                                                <td valign="top" style="color: #111827; font-weight: 600; padding: 4px 0;">Value Details</td>
                                                            </tr>
                                                        </tbody>
                                                    </table>
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>

                                    <!-- CTA Button -->
                                    <table width="100%" cellpadding="0" cellspacing="0" border="0" style="margin: 0 0 28px 0;">
                                        <tbody>
                                            <tr>
                                                <td align="left">
                                                    <a href="{{action_url}}" target="_blank" class="btn-cta" style="display: inline-block; background-color: #fa0913; color: #ffffff; text-decoration: none; font-size: 14px; font-weight: 600; padding: 11px 24px; border-radius: 3px; text-align: center;">
                                                        Take Action
                                                    </a>
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>

                                    <!-- Closing -->
                                    <p style="margin: 0 0 20px 0; color: #111827; font-size: 14.5px; font-weight: 600; line-height: 1.5;">
                                        We look forward to connecting with you!
                                    </p>

                                    <!-- Sign-off -->
                                    <p style="margin: 0; color: #4b5563; font-size: 14px; line-height: 1.6;">
                                        Warm regards,<br>
                                        <strong style="color: #111827;">The BeetleCode Team</strong>
                                    </p>

                                </td>
                            </tr>

                            <!-- 4. Clean Professional HTML Footer -->
                            <tr>
                                <td class="footer-padding" style="background-color: #fbfcfd; border-top: 1px solid #e5e7eb; padding: 28px 36px; text-align: left;">
                                    <table width="100%" cellpadding="0" cellspacing="0" border="0">
                                        <tbody>
                                            <tr>
                                                <td style="padding-bottom: 12px;">
                                                    <a href="https://beetlecode.com" target="_blank" style="text-decoration: none; color: #111827; font-size: 13px; font-weight: 700; letter-spacing: 0.3px;">
                                                        BEETLECODE (PVT) LTD
                                                    </a>
                                                    <p style="margin: 4px 0 0 0; color: #6b7280; font-size: 12px; line-height: 1.5;">
                                                        AI-Driven Software &bull; IoT Ecosystems &bull; Digital Growth Solutions
                                                    </p>
                                                </td>
                                            </tr>
                                            <tr>
                                                <td style="padding: 10px 0; border-top: 1px solid #f0f2f5; border-bottom: 1px solid #f0f2f5;">
                                                    <table cellpadding="0" cellspacing="0" border="0">
                                                        <tbody>
                                                            <tr>
                                                                <td style="padding-right: 16px;">
                                                                    <a href="https://beetlecode.com" target="_blank" style="color: #fa0913; font-size: 12px; font-weight: 600; text-decoration: none;">
                                                                        Official Website
                                                                    </a>
                                                                </td>
                                                                <td style="padding-right: 16px; color: #d1d5db;">|</td>
                                                                <td style="padding-right: 16px;">
                                                                    <a href="https://beetlecode.com/contact" target="_blank" style="color: #4b5563; font-size: 12px; text-decoration: none;">
                                                                        Contact Us
                                                                    </a>
                                                                </td>
                                                                <td style="padding-right: 16px; color: #d1d5db;">|</td>
                                                                <td>
                                                                    <a href="mailto:info@beetlecode.com" style="color: #4b5563; font-size: 12px; text-decoration: none;">
                                                                        info@beetlecode.com
                                                                    </a>
                                                                </td>
                                                            </tr>
                                                        </tbody>
                                                    </table>
                                                </td>
                                            </tr>
                                            <tr>
                                                <td style="padding-top: 12px;">
                                                    <p style="margin: 0; color: #9ca3af; font-size: 11.5px; line-height: 1.6;">
                                                        &copy; 2026 BEETLECODE (PVT) LTD. All rights reserved.<br>
                                                        This message and any attachments are confidential and intended solely for the intended recipient.
                                                    </p>
                                                </td>
                                            </tr>
                                        </tbody>
                                    </table>
                                </td>
                            </tr>

                        </tbody>
                    </table>

                </td>
            </tr>
        </tbody>
    </table>
</body>
</html>
```

---

## 7. Existing Templates Reference

* **[intern_send.html](file:///d:/BeetleCode/HR/beetlecode-images/intern_send.html)**: Internship shortlist announcement and 6-month breakdown.
* **[inern.html](file:///d:/BeetleCode/HR/beetlecode-images/inern.html)**: Interview invitation with meeting instructions and Google Meet CTA.
* **[reshedule.html](file:///d:/BeetleCode/HR/beetlecode-images/reshedule.html)**: Interview reschedule notification with updated date/time.
* **[intern_selected.html](file:///d:/BeetleCode/HR/beetlecode-images/intern_selected.html)**: Official internship selection & offer acceptance email.
* **[rejection.html](file:///d:/BeetleCode/HR/beetlecode-images/rejection.html)**: Professional application rejection letter with talent network retention note.
