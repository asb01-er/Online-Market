# Online Marketplace

A full-stack marketplace where users can list items for sale, browse what others are selling, and message sellers.

**Live demo:** coming soon
**Code:** https://github.com/asb01-er/Online-Market

## Features

- Browse all listings on the home page
- Sign in with Clerk authentication
- Create listings with a name, description, price and photo
- Image upload to Cloudinary with a live preview
- Listing detail pages with an in-app messaging workflow
- Sellers can read messages sent about their listings

## Tech stack

| Layer     | Technology                              |
| --------- | --------------------------------------- |
| Framework | Next.js 15 (Pages Router), TypeScript   |
| API       | tRPC with SuperJSON                     |
| Database  | MongoDB with Prisma                     |
| Auth      | Clerk                                   |
| Images    | Cloudinary                              |
| Styling   | Tailwind CSS                            |
| Forms     | React Hook Form                         |

Built from the [T3 Stack](https://create.t3.gg/).

## Getting started

### Prerequisites

- Node.js 18+
- A MongoDB database (MongoDB Atlas works well)
- A [Clerk](https://clerk.com) application
- A [Cloudinary](https://cloudinary.com) account with an unsigned upload preset

### 1. Clone and install

```bash
git clone https://github.com/asb01-er/Online-Market.git
cd Online-Market
npm install
```

### 2. Configure environment variables

Create a `.env` file in the project root:

```env
DATABASE_URL="mongodb+srv://<user>:<password>@<cluster>.mongodb.net/online-market"
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
CLOUDINARY_CLOUD_NAME=your_cloud_name
CLOUDINARY_API_KEY=your_api_key
CLOUDINARY_API_SECRET=your_api_secret
UPLOAD_PRESET=your_upload_preset
```

Never commit `.env`. The variables are validated in `src/env.js`, so a missing one stops the build.

### 3. Set up the database

```bash
npx prisma generate
npx prisma db push
```

### 4. Run the app

```bash
npm run dev
```

Open http://localhost:3000. The sell page is at `/sell-an-item`.

## Scripts

| Command           | Description                    |
| ----------------- | ------------------------------ |
| `npm run dev`     | Start the development server   |
| `npm run build`   | Create a production build      |
| `npm start`       | Run the production build       |

## Deployment

Deploys as a Render Web Service. Use `npm install && npx prisma generate && npm run build` as the build command and `npm start` as the start command, set the environment variables above, and allow Render's connection in MongoDB Atlas Network Access. Add the deployed URL to Clerk's allowed origins.

## Author

**Ernest Ekelem** — [GitHub](https://github.com/asb01-er) · [LinkedIn](https://www.linkedin.com/in/ernest-ekelem-5a771735a)
