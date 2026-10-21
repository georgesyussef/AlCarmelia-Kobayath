AL CARMELIA - FIREBASE CONFIG CONNECTED BUILD

The HTML pages use the existing carmelia-school Firebase Web App configuration. This is NOT a test-project placeholder.

IMPORTANT: The Firebase configuration alone DOES NOT enable Storage uploads. Storage must be provisioned and its rules verified. Upload may fail with storage/unauthorized. The existing ID/PIN login is not Firebase Authentication and must not be treated as a secure identity for Storage rules. Do not make Storage public to work around this.

No Firestore data was changed by generating this ZIP. This ZIP has not been tested against the live backend and is NOT certified production-ready. Publishing to the existing Vercel site changes what parents/teachers see. Preserve a backup and test in a separate Vercel deployment before replacing the production site.

New UI: Modifier for Agenda and Travail Quotidien; optional JPG/PNG/PDF (<=5 MB) upload on Travail Quotidien; parent attachment links. Storage path: travail_quotidien/{docId}/{random}.{ext}.

Do not deploy until backend permissions and upload lifecycle are verified.
