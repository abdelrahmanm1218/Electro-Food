# Electro Food - Frontend

A modern, responsive food ordering application built with React and Vite. The frontend provides both customer and admin interfaces for managing food orders and menu items.

## Features

### Customer Features
- **Menu Browsing**: Browse available food items with images, descriptions, and prices
- **Shopping Cart**: Add items to cart with quantity management
- **Order Placement**: Place orders with payment method selection (Online/Cash on Delivery)
- **Order Tracking**: View order history and track order status
- **Multi-language Support**: English and Arabic language support
- **User Authentication**: Register and login with secure authentication

### Admin Features
- **Order Management**: View and manage all customer orders
- **Order Status Updates**: Update order status (pending, confirmed, preparing, on the way, delivered)
- **Order Filtering**: Filter orders by date
- **Menu Management**: Create, edit, and delete menu items
- **Item Availability**: Toggle item availability status
- **Dashboard**: Central admin dashboard for order and inventory management

## Tech Stack

- **Frontend Framework**: React 18
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **Component Library**: Custom UI components (Card, Button, Table, Dialog, Select, etc.)
- **State Management**: React Context (Auth, Cart)
- **HTTP Client**: Axios
- **Internationalization**: react-i18next (i18n)
- **Icons**: Lucide React
- **Notifications**: Sonner
- **Routing**: React Router

## Project Structure

```
src/
├── components/          # Reusable UI components
│   ├── AdminSidebar.jsx    # Admin navigation
│   ├── Navbar.jsx          # Main navigation bar
│   └── ui/                 # UI component library
│       ├── badge.jsx
│       ├── button.jsx
│       ├── card.jsx
│       ├── dialog.jsx
│       ├── table.jsx
│       ├── select.jsx
│       └── ... (other components)
├── context/             # React Context providers
│   ├── AuthContext.jsx     # Authentication state
│   └── CartContext.jsx     # Shopping cart state
├── pages/               # Page components
│   ├── admin/
│   │   ├── AdminOrdersPage.jsx        # Order management
│   │   ├── AdminOrderDetailsPage.jsx  # Order details
│   │   ├── AdminMenuItemsPage.jsx     # Menu management
│   │   └── AdminMenuItemDetailsPage.jsx
│   └── user/
│       ├── MenuPage.jsx           # Browse menu items
│       ├── CartPage.jsx           # Shopping cart
│       ├── OrdersPage.jsx         # Order history
│       ├── LoginPage.jsx          # User login
│       └── RegisterPage.jsx       # User registration
├── hooks/               # Custom React hooks
│   └── use-mobile.js       # Mobile detection
├── lib/                 # Utility functions
│   └── utils.js            # Helper utilities
├── api.js               # Axios API configuration
├── i18n.js              # i18n configuration
├── App.jsx              # Main app component
├── main.jsx             # Entry point
└── App.css              # Global styles

public/                  # Static assets
```

## Setup Instructions

### Prerequisites
- Node.js (v14 or higher)
- npm or yarn

### Installation

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd frontend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure environment variables**
   Create a `.env` file in the root directory:
   ```env
   VITE_API_URL=http://localhost:8000/api
   ```

4. **Start the development server**
   ```bash
   npm run dev
   ```

   The application will be available at `http://localhost:5173`

## Build & Deployment

### Development Build
```bash
npm run dev
```

### Production Build
```bash
npm run build
```

### Preview Production Build
```bash
npm run preview
```

## Key Components

### AdminOrdersPage
- Displays all customer orders in a paginated table
- Filter orders by date
- Update order status via dropdown selector
- Pagination with page indicator

### AdminMenuItemsPage
- Manage menu items (create, edit, delete)
- View item details (name, price, description, availability)
- Pagination support

### MenuPage
- Responsive grid layout (2 columns on mobile, 4 columns on medium+ screens)
- Display menu items with images and descriptions
- Add to cart functionality
- Multi-language support for item details

### CartPage
- View cart items with quantities
- Proceed to checkout
- Order summary with total price

### OrdersPage
- View user's order history
- Track order status
- Order details and timeline

## Authentication

The app uses a Context-based authentication system:
- User state is managed in `AuthContext`
- Token is stored and sent with all API requests
- Protected routes require authentication
- Login/Register pages for new users

## Internationalization

The app supports multiple languages using react-i18next:
- Currently supports English (en) and Arabic (ar)
- Language can be switched from the Navbar
- All UI text is translatable
- RTL support for Arabic

## API Integration

The frontend communicates with a Django REST API backend:
- Base configuration in `src/api.js`
- Endpoints for:
  - User authentication (`/auth/`)
  - Menu items (`/menu/items/`)
  - Orders (`/orders/`)
  - Cart management (`/orders/cart/`)
  - Admin operations (`/orders/admin/`, `/menu/admin/`)

## Styling

The project uses Tailwind CSS for styling:
- Responsive design patterns
- Dark mode support (via CSS variables)
- Custom component library built on top of Tailwind
- Consistent color scheme and typography

## Development Workflow

1. Create a feature branch
2. Make changes in the appropriate component/page
3. Test locally with `npm run dev`
4. Build with `npm run build` to check for errors
5. Submit a pull request

## Troubleshooting

- **Port already in use**: Change the port in `vite.config.js`
- **API connection errors**: Verify the backend is running and `VITE_API_URL` is correct
- **Build errors**: Clear `node_modules` and reinstall with `npm install`
- **Cache issues**: Clear browser cache or use incognito mode

## License

[Add your license information here]

## Contact

For questions or issues, please contact the development team.

