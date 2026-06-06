# Debut_RSVP
Built a custom, mobile-responsive digital RSVP application designed for an 18th birthday celebration (debut).


From a technical perspective, it is structured as follows:

  - Single-Page Architecture: It is written entirely in a single file using
    standard HTML, CSS, and vanilla JavaScript. This allows it to load quickly
    and run directly in any web browser without needing a complex backend
    server.
  - Regency Aesthetic: It features a classical design style with blush pink
    tones, double gold-line borders, responsive image scaling for the portrait,
    custom typography, and floral ornaments.
  - Flexible Search System: It utilizes a search function that allows guests to
    search by their first name, last name, or full name. The script scans your
    guest list to retrieve and display their specific individual or group
    invitation.
  - Dynamic Group Management: It dynamically generates customized attendance
    options ("Attending" or "Unable to Join") for each person mapped to that
    specific invitation.
  - Conditional Validation: It monitors the selected attendance options. If any
    guest in the group declines, the system automatically makes the well-wishes
    message box mandatory; if everyone is attending, it remains optional so
    guests can submit without friction.
  - Background Data Collection: It packages the guest responses and silently
    submits them to your Google Sheets document (via a Google Form) using an
    invisible iframe. This keeps your guests on your page to view their custom
    response summary and optional navigation links without redirecting them to
    Google's standard submission page.
