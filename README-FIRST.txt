RAISME ANVAYA WEBSITE + ADMIN DASHBOARD

UPLOAD
Upload these files into the ROOT of your existing GitHub repository:
- index.html (replace existing)
- data.js (replace existing)
- admin.html
- admin.js
- config.js
- supabase/schema.sql (keep the supabase folder)

SUPABASE ONE-TIME SETUP
1. Create a Supabase project.
2. Open SQL Editor -> New query; paste and run supabase/schema.sql.
3. In Authentication -> Users, create an admin user with your email and a strong password.
4. Run this SQL, replacing the email with the exact admin email:
   insert into public.club_admins (user_id)
   select id from auth.users where email = 'YOUR-ADMIN-EMAIL'
   on conflict (user_id) do nothing;
5. In Project Settings -> API, copy Project URL and anon/public key.
6. Edit config.js in GitHub and replace the two placeholder values.
   Use ONLY the anon/public key. NEVER put the service_role key in website files.

OPEN
Public website: https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY/
Admin dashboard: https://YOUR-GITHUB-USERNAME.github.io/YOUR-REPOSITORY/admin.html

NOTES
- USNs are stored for admin reference and are not shown publicly.
- Only approved admin accounts can add/edit/delete.
- Public visitors see only records marked published.
- Existing static content remains as fallback until Supabase is configured.
- Registration continues to use the existing Google Form.
- Member photo field accepts a public HTTPS image URL; direct file upload is not included yet.
- Confirm all member names, roles and consent before publishing.
- Never share your Supabase password or service_role key.
