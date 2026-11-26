RAILWAY PHOTO HUNT - Cloud connected frontend bundle

Files:
- index.html: student registration, group PIN login, photo upload queue, teacher dashboard
- sw.js: caches the app shell and Supabase JS library for reopening the app offline after first successful online load

Backend:
Supabase project: bvswvjzkfvfjprlgwvzf
Edge Function: railway-student-api
Storage bucket: railway-photos (private)

IMPORTANT SETUP BEFORE STUDENT USE:
1. Host index.html and sw.js together at the root of an HTTPS website. The website URL becomes the student QR-code URL.
2. In Supabase Dashboard > Authentication > Users, create the teacher account (one account only).
3. Share the teacher account email with the project administrator so its auth user ID can be added to public.railway_admins. Never share the password.
4. Test one student group, one upload, teacher login, signed image viewing, approval, and resubmission before distributing the QR code.

Students register a group with 2-3 names, class, and a 6-digit PIN. The server generates a group access code. Keep both the access code and PIN safe.
Photos are compressed in the browser and stored locally in IndexedDB until uploaded. Uploads resume when the page is online/open; the service worker caches the app for reopening offline after the first online visit.
