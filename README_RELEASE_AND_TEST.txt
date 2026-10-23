CARMELIA AGENDA - READ OPTIMIZATION / RELEASE CANDIDATE (TEST FIRST)

This ZIP is based on the supplied Carmelia Supabase preview, not a verified copy of your current production GitHub repository. DO NOT blindly overwrite the production repository.

Changed in parents.html / teacher.html / responsable.html:
- On initial load, query agenda and travail_quotidien by exact YYYY-MM-DD date in Firestore.
- When the date changes, detach the previous live listener and attach one for the new date.
- On logout, detach listeners.
- Avoid reconnecting on a no-op date selection.
- All Dates remains available, but prompts a warning because it can read the entire archive.

Unchanged: UI, existing login/PIN behavior, existing Firebase project, Firestore documents, edit/save/delete logic, admin.html.

IMPORTANT LIMITATIONS:
1. No live Firebase end-to-end tests have been performed. This is NOT a certified production release.
2. Date values MUST be strings exactly YYYY-MM-DD. Firestore may request composite indexes for teacherId+date or class+date. Do not change rules to fix indexes.
3. The Supabase attachments API in this ZIP still needs Vercel server environment variables and may fail; this optimization does NOT fix uploads or existing authentication/security flaws.
4. The code still reads classes/teachers/responsables as in the original. Those reads are NOT optimized. Admin reads are NOT optimized.
5. The ZIP points to LIVE Firebase; test pages can mutate LIVE data if you use their save/delete actions.
6. Existing PIN/OneSignal security issues are NOT resolved. Do not claim the site is secure based on this optimization.
7. Do not expose secrets in GitHub.

SMOKE TEST BEFORE PUBLIC DEPLOYMENT:
- Parent: today, yesterday, tomorrow, class isolation, agenda and travail.
- Teacher: own posts, change date, edit old post, logout/login.
- Responsable: assigned classes, change date, edit old post.
- Browser console: look for FAILED_PRECONDITION index links and permission errors.
- Compare Firebase 24h reads under comparable traffic; do not infer savings from user count alone.
- Keep a Git commit/tag and Vercel deployment available for rollback.

GitHub deployment: back up your current repo first; compare this folder with the production repository; merge only the reviewed changes. A separate preview deployment is safer for testing.
