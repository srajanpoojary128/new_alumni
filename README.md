# Alumni and Student Connection Portal

Welcome to the **Alumni and Student Connection Portal** — a full-featured platform connecting alumni with current students for networking, mentorship, and collaboration.

## Project Structure

```
new alumni/
├── alumni_portal.html    ← Main app (renamed from index.html)
├── docker-compose.yml
├── package.json
├── tsconfig.json
├── .env.example
└── README.md
```

## Features

- 🔐 **User Authentication** — Registration & login for students, alumni, and admins
- 👤 **Profiles** — Showcase skills, experience, and education
- 💼 **Job Board** — Alumni can post opportunities; students can browse
- 📅 **Event Calendar** — Schedule and view upcoming alumni events
- 💬 **Messaging** — Direct communication between users
- 📊 **Admin Dashboard** — User management, analytics, CSV export
- ✅ **Full Validation** — Client-side validation on all forms (inline errors, password strength, char counters)

## Validation Coverage

| Form | Rules Applied |
|---|---|
| Registration | Name (letters only, 2–80 chars), email format, password min 6 chars, CGPA 0–10, valid URLs |
| Login | Email format, required fields, credential match |
| Post Job | Title (3–120 chars), company required, description max 1000 chars |
| Create Event | Title required, future date required, venue/desc length limits |
| Send Message | Recipient lookup, body required, subject/body length limits, no self-messaging |
| Edit Profile | Name format, password min 6, CGPA range, LinkedIn URL |
| Add Admin | Name, email format, password, duplicate email check |
| Admin Settings | Name format, password length |

## Getting Started

### Prerequisites
- Node.js (v14+), npm, Docker

### Installation

```bash
git clone <repository-url>
cd "new alumni"

# Install server dependencies
cd server && npm install

# Install client dependencies
cd ../client && npm install

# Copy env file
cp .env.example .env
# Fill in your values in .env
```

### Running the Application

**With Docker:**
```bash
docker-compose up
```

**Without Docker:**
```bash
# Terminal 1 — Server
cd server && npm start

# Terminal 2 — Client
cd client && npm start
```

**Quick Start (single HTML file):**
Open `alumni_portal.html` directly in any browser — no server needed. All data is stored in `localStorage`.

## Default Admin Credentials

When the app first loads, seed an admin account via the registration form (select "Admin" role), then use those credentials to log in.

## Environment Variables

```env
DATABASE_URL=your_database_url_here
JWT_SECRET=your_jwt_secret_here
NODE_ENV=development
PORT=5000
CLIENT_URL=http://localhost:3000
API_URL=http://localhost:5000/api
```

## Contributing

Pull requests are welcome! Please open an issue first for major changes.

## License

MIT License — see LICENSE file for details.
