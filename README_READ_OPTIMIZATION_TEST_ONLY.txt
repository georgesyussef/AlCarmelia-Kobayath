CARMELIA - FIRESTORE READ OPTIMIZATION / TEST ONLY
=================================================
This package is a copy of the earlier Supabase preview, NOT a production release.
Changed ONLY parents.html, teacher.html and responsable.html Firestore agenda/travail listeners:
- Query server-side by selected date (YYYY-MM-DD string).
- Unsubscribe old listener and subscribe new one when date changes.
- Preserve existing layout, roles, login codes, save/delete behavior and Firestore data.
- Explicit 'all dates' restores old unlimited query and can consume many reads.
- No database migration, no rule changes, no writes or deletions introduced.

CRITICAL TEST GATES:
1. Deploy to a SEPARATE Vercel test project, never overwrite production until verified.
2. This preview STILL points at the LIVE Firebase project carmelia-school. Opening it can read production data; posting/deleting can mutate it. Do not perform write tests against production.
3. Firestore may require a COMPOSITE INDEX for queries by class/teacherId + date. Check browser console for FAILED_PRECONDITION and follow index creation link; index creation does not change existing documents. Never loosen security rules to resolve an index error.
4. Date filtering assumes date is stored as exact YYYY-MM-DD STRING. Confirm with real data; if stored as timestamp or date-time string, queries will show empty results.
5. Verify current date, yesterday, tomorrow, switching dates, parent/teacher/responsable, and explicit All Dates. Check editing older entries and subject-specific access.
6. Existing auth/security and Supabase upload problems are NOT fixed in this package. Do NOT expose this preview publicly as a secure production release. Supabase attachment API requires server configuration; key creation restriction remains unresolved.
7. Measure Firestore reads before and after under comparable real traffic. Zero savings cannot be ruled out; listener reconnections and per-query minimum reads still apply.
8. Do not change Firebase Rules, PINs, database documents, or existing production Vercel project to test this package.

Deployment: upload this full folder as a separate project (preserve api/attachments.js); set environment variables only in Vercel, never GitHub. No secrets are included.
