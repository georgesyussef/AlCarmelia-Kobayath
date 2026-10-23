CARMELIA SUPABASE ATTACHMENTS — TEST BUILD, NOT PRODUCTION READY

1. This package preserves the original Firebase project and UI; it does not change any live data by itself. Opening the pages against production CAN modify live data if you log in and save. Use a separate Vercel preview and test records only.
2. Supabase project: https://iderqtpuwcxsklvghucw.supabase.co ; PRIVATE bucket: travail-files.
3. Deploy on Vercel with Node function and npm dependencies. Configure Vercel Environment Variables (server only):
   SUPABASE_SERVICE_ROLE_KEY = secret Supabase service_role key (NEVER put in HTML)
   FIREBASE_SERVICE_ACCOUNT_JSON = complete Firebase Admin SDK service-account JSON (server only)
   CARMELIA_SESSION_SECRET = 32+ random bytes as a long secret string
4. Existing teacher/responsable/parent PIN login is still client-side and Firestore currently may expose PIN documents. DO NOT put this on the public school domain until Firestore Rules and authentication are migrated and verified. Otherwise server-side login does not make the overall site secure.
5. This Vercel proof-of-integration limits PDF/JPG/PNG to 2.5 MB because serverless request-body limits. Original UI says 5 MB and must be aligned before rollout. Files >2.5 MB require direct signed upload URLs, not serverless base64.
6. Parent viewing needs a fresh login to obtain the attachment token; saved legacy sessions will not have one.
7. The new API allows uploads for teacher-owned work and new responsable-owned work. Old responsable records lack authorId and need a reviewed migration.
8. Existing Firebase attachments remain supported via old download URLs. New attachments are private in Supabase and retrieved through the authenticated API.
9. No Supabase policies need to be opened; service_role is server-side. Rotate any previously exposed OneSignal REST key. Existing OneSignal push code is NOT secured in this package.
10. Do not deploy without testing access control, uploads, downloads, PIN lockout/rate limits, and Firestore rules. The login endpoint currently has no rate limiting and is NOT safe for public deployment.

11. Push sending is deliberately DISABLED in this test build because the original OneSignal REST key was exposed in browser code. Rotate that key and implement server-side push before rollout.
