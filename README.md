# Student Scholarship Monitoring System - Standalone Demo

This version does NOT require Supabase. Login and demo data run in the browser using localStorage.

## Demo Login

Admin
- Email: admin@gmail.com
- Password: Admin@12345

Student
- Email: student@gmail.com
- Password: Student@12345

## Run

Open `index.html` in a browser. No database, API key, server, or Supabase setup is required.

## Features

Admin: dashboard, scholar management, scholarship programs, grade submissions, verification, compliance monitoring.

Student: dashboard, scholarship information, grades, grade submission, compliance status.

## Reset demo data

Open browser Developer Tools > Console and run:

localStorage.removeItem('scholarship_demo_database_v1'); location.reload();

## Note

This is for academic/demo use. Passwords are intentionally stored client-side and are NOT secure for production. For a real deployment, use server-side authentication and a database.
