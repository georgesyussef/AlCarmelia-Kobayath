AL CARMELIA - EDIT + REAL STORAGE CODE (ISOLATED TEST PACKAGE)

IMPORTANT: This package intentionally DOES NOT connect to the production Firebase project.
The production project ID is blocked. All Firebase config values are placeholders.
Do NOT deploy this package to the school URL or reuse its live OneSignal application.

Included: teacher and responsable Edit for Agenda and Travail Quotidien, optional Firebase Storage upload for JPG/PNG/PDF <= 5 MB, parent attachment link, admin edit. Existing data fields preserved; new optional attachment object on travail_quotidien.

BEFORE IT CAN WORK END-TO-END:
1. Create a separate Firebase TEST project and replace firebaseConfig in all pages.
2. Configure Firebase Storage, Firestore, Authentication and enforce server-side authorization (teacher IDs/PINs in the current app are client-side and NOT secure access control).
3. Deploy and validate Firestore + Storage rules for roles, class codes, file size/type and owner.
4. Test create/edit/upload/view with test accounts.

WARNING: DO NOT use permissive public Storage rules; download token URLs can be shared. The included upload code is integration-ready but not production-safe without verified authentication and rules.
No production files or data were changed.
