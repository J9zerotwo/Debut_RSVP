# RSVP-Trisha_XVIII ⚜️

A beautiful, responsive, single-page digital RSVP application designed for **Trisha Jia's 18th Birthday Celebration (A Decade & Eight)**. Built with a classical Bridgerton-inspired theme, this app provides an elegant and intuitive experience for guests to search for their invitation and submit their attendance responses.

Live Demo: https://debutrsvp.vercel.app/

---

## ⚜️ Key Features

- **Bridgerton Regency Aesthetic:** Designed with soft blush pink accents, semi-transparent ivory parchment glassmorphism, gold gradients, elegant borders, and classical serif typography (`Cinzel`, `Cormorant Garamond`, `Great Vibes`).
- **Flexible Guest Search (Fuzzy Matching):** Guests can search for their invitation by typing their first name, last name, or full name. The search engine scans both the grouping keys and individual member lists dynamically.
- **Dynamic Group Attendance:** Generates custom attendance radio buttons for each guest under a single invitation (handling individuals, duos, and larger groups seamlessly).
- **Conditional Message Requirements:** If any guest in the group declines, the system automatically prompts and requires a message for the debutante; otherwise, the field remains optional.
- **Silent Background Submissions:** Submits responses in the background to a Google Sheets database (via Google Forms) using an invisible iframe, preventing cross-origin redirection blocks and keeping the user on the custom success page.
- **Integrated Navigation:** Features custom buttons on the home screen to "Preview the Invitation" and on the confirmation screen to go "Back to Invitation."

---

## 🛠️ Technology Stack

- **Markup:** HTML5
- **Styling:** CSS3 (Flexbox, custom CSS animations, Google Fonts integration)
- **Scripting:** Vanilla JavaScript (ES6+)
- **Database Backend:** Google Forms / Google Sheets (via silent URL-encoded POST submissions)
- **Deployment:** Vercel

---

## ⚙️ How It Works

### 1. Verification & Selection
The guest types their name. The JavaScript loops through the guestDatabase structure:
"javascript const guestDatabase = {"caila ruado": { type: "group", members: ["Caila Ruado", "1+ Guest"] }, };"

If a match is found, the interface smoothly transitions (using CSS animations) to display custom radio selections for each member of that group.

2. Silent Google Sheet Submission

When the submit button is clicked, JavaScript captures the values, writes them
to hidden inputs mapped to your Google Form entry.xxxxxxxxx IDs, and triggers a
native HTML submit targeting an invisible <iframe>:

<form id="rsvp-form" action="https://docs.google.com/forms/d/e/.../formResponse" method="POST" target="hidden_iframe">

This bypasses browser CORS restrictions when running locally or on static hosts,
recording responses directly into your Google Sheets spreadsheet without
reloading the page.

🚀 How to Customize This for Your Event

1. Update the Guest List

Locate the guestDatabase object inside the <script> tag and replace the names
with your own guest structure. You can generate this block of code easily
from a spreadsheet using an Excel/Google Sheets formula:

=""""&LOWER(TRIM(A2))&""": { type: ""group"", members: ["&IF(B2<>"", """"&B2&"""", "")&IF(C2<>"", ", """&C2&"""", "")&"] },"

2. Update Google Form Mapping

In the HTML <form> block, update the action attribute with your unique Google
Form /formResponse URL, and replace the entry.xxxxxxxxx input name attributes
with your actual form field entry codes.

