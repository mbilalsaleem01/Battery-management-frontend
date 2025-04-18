# Battery Manager - Full Stack Battery Rental Management System

A comprehensive web application for efficiently managing a battery rental business including inventory, customer rentals, due balances, credit scores, and payment history.

## Features

- **Inventory Management**: Track batteries with status indicators (available/rented/maintenance)
- **Customer Management**: Manage customer information with credit rating system
- **Rental Workflow**: Streamlined rent and return processes
- **Payments & Financial Reports**: Track payments and generate financial summaries
- **Dashboard & Analytics**: Visual overview of business performance
- **Credit Rating System**: Automatic rating based on payment history
- **Multilingual Support**: English and Urdu language options
- **PDF & Excel Exports**: Generate reports and receipts
- **WhatsApp Integration**: Share customer reports and payment receipts

## Tech Stack

### Frontend
- React.js + TypeScript
- Next.js for server-side rendering
- Tailwind CSS for styling
- shadcn/ui for UI components
- Framer Motion for animations
- Clerk for authentication
- i18next for multilingual support

### Backend
- Node.js + Express.js
- PostgreSQL database
- Prisma ORM
- Authentication with Clerk
- PDF generation with jsPDF
- Excel export with SheetJS

## Project Structure

```
battery-manager/
├── frontend/               # Next.js frontend application
│   ├── src/
│   │   ├── app/            # Next.js app router pages
│   │   ├── components/     # UI components
│   │   └── lib/            # Utility functions and API clients
│   ├── public/             # Static assets
│   └── package.json        # Frontend dependencies
│
├── backend/                # Express.js backend application
│   ├── src/                # Backend source code
│   │   ├── routes/         # API routes
│   │   └── middleware/     # Express middleware
│   ├── prisma/             # Prisma schema and migrations
│   └── package.json        # Backend dependencies
│
├── DEPLOYMENT.md           # Deployment instructions
└── README.md               # Project documentation
```

## Getting Started

### Prerequisites
- Node.js 18+ and npm
- PostgreSQL database

### Installation

1. Clone the repository
```bash
git clone https://github.com/yourusername/battery-manager.git
cd battery-manager
```

2. Install backend dependencies
```bash
cd backend
npm install
```

3. Set up environment variables
```bash
# Create a .env file in the backend directory
cp .env.example .env
# Edit the .env file with your database connection string
```

4. Run database migrations
```bash
npx prisma migrate dev
```

5. Install frontend dependencies
```bash
cd ../frontend
npm install
```

6. Set up frontend environment variables
```bash
# Create a .env.local file in the frontend directory
cp .env.example .env.local
# Edit the .env.local file with your API URL and Clerk keys
```

### Running the Application

1. Start the backend server
```bash
cd backend
npm run dev
```

2. Start the frontend development server
```bash
cd frontend
npm run dev
```

3. Open your browser and navigate to `http://localhost:3000`

## Testing

A comprehensive test page is available at `/test` to verify all features:
- PDF Export functionality
- Excel Export functionality
- Multilingual support
- WhatsApp integration
- API connectivity
- UI components

## Deployment

See [DEPLOYMENT.md](DEPLOYMENT.md) for detailed deployment instructions.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
