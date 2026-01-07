# Judix

Hey! This is my task management app that I built using React and Express. It's got JWT auth, full CRUD for tasks, and I've tried to make the UI look pretty clean and modern.

## Repositories

- **Server:** [Link to Server Repo](https://github.com/username/judix-server)
- **Client:** [Link to Client Repo](https://github.com/username/judix-client)
- **Monorepo (if applicable):** [Link to Repo](https://github.com/username/judix)

## What I Used

**Backend:**
- Node.js with Express
- MongoDB (using Mongoose)
- JWT for auth
- bcryptjs to hash passwords
- express-validator for checking inputs

**Frontend:**
- React with Vite (way faster than CRA!)
- Tailwind CSS
- React Router
- Axios for API calls

## Getting It Running

You'll need Node.js (v18+) and MongoDB installed. I use MongoDB Atlas for the cloud DB but local works fine too.

**Setup:**

1. Clone the repository
```bash
git clone <repository-url>
cd judix
```

2. Backend setup
```bash
cd server
npm install
```

3. Make a `.env` file in the server folder:
```
PORT=5000
MONGODB_URI=mongodb://localhost:27017/judix
JWT_SECRET=your_super_secret_key_here
JWT_EXPIRES_IN=7d
NODE_ENV=development
```

4. Frontend setup
```bash
cd ../client
npm install
```

5. Make a `.env` file in the client folder:
```
VITE_API_URL=http://localhost:5000/api/v1
```

**Running it:**

Start the backend:
```bash
cd server
npm run dev
```

Then in another terminal, start the frontend:
```bash
cd client
npm run dev
```

Head to `http://localhost:5173` and you should be good to go!

## How It's Organized

```
judix/
├── server/
│   ├── src/
│   │   ├── config/         # DB setup
│   │   ├── controllers/    # Route logic
│   │   ├── middleware/     # Auth & validation stuff
│   │   ├── models/         # Mongoose models
│   │   ├── routes/         # API routes
│   │   ├── utils/          # Helper functions
│   │   ├── validators/     # Input validation
│   │   └── index.js        # Main entry point
│   ├── .env
│   └── package.json
│
├── client/
│   ├── src/
│   │   ├── api/            # Axios setup
│   │   ├── components/     # Reusable components
│   │   ├── context/        # Context API stuff
│   │   ├── pages/          # Main pages
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── .env
│   └── package.json
│
├── README.md
├── SCALING.md
└── openapi.json

## API Routes

**Auth:**
- `POST /api/v1/auth/register` - Sign up
- `POST /api/v1/auth/login` - Log in
- `GET /api/v1/auth/me` - Get your profile
- `PUT /api/v1/auth/profile` - Update profile

**Tasks:**
- `GET /api/v1/tasks` - Get all your tasks (supports filtering & pagination)
- `POST /api/v1/tasks` - Create a task
- `GET /api/v1/tasks/:id` - Get one task
- `PUT /api/v1/tasks/:id` - Update a task
- `DELETE /api/v1/tasks/:id` - Delete a task

## What It Does

- Sign up and log in with JWT
- Passwords are hashed with bcrypt (obviously)
- Protected routes that need auth
- Full CRUD for tasks
- Filter tasks by status and priority
- Search through your tasks
- Pagination for when you have tons of tasks
- Works on mobile and desktop
- Decent error messages

## Security Stuff

I've tried to keep things secure:
- Passwords get hashed with bcrypt
- Using JWT for auth (stateless, so it scales better)
- Middleware to check tokens on protected routes
- Input validation on everything
- CORS is configured properly
- Centralized error handling so nothing leaks

## License

ISC
