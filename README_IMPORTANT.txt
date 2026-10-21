CARMELIA OPTIONAL FILES — INTEGRATION TEST (UI ONLY)

Built from Carmelia_Date_TEST_Admin_Fixed(1).zip.

Only teacher.html and responsable.html were edited.
A non-required file input (JPG/PNG/PDF, max 5 MB) and local preview were added to the existing Travail Quotidien modal.
The original forms, subjects, class choices, date filters, and saving logic without an attachment remain unchanged.

IMPORTANT: File upload is NOT connected to Firebase Storage. If a file is selected, Save is deliberately blocked with a clear message to prevent losing an attachment silently. Saving without a file follows the ORIGINAL Firestore logic.

DO NOT DEPLOY OR LOG IN TO THESE COPIES. They still contain the production Firebase configuration and may access real data. This ZIP is source code for offline review by a developer only, NOT an isolated Firebase test environment.

To enable real uploads safely: configure separate Firebase test project, authentication, Storage and Firestore security rules; test access controls; then connect storage and add metadata to travail_quotidien. Keep production untouched until explicit approval.
