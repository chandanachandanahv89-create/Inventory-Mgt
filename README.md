# Inventory Management System

A simple full-stack **Inventory Management System** built using **React, Node.js, Express.js, and MongoDB**. The application allows users to add, view, update, delete, search, and filter products and identify products that are low in stock.

## Features

* Add new products
* View all products
* Update product details
* Delete products
* Search products by name
* Filter products by category
* Highlight low-stock products
* Dashboard with inventory statistics
* Low-stock products API
* Form validation
* Error handling
* Responsive user interface
* RESTful APIs
* MongoDB database integration

## Technologies Used

### Frontend

* React
* Vite
* JavaScript
* Axios
* CSS

### Backend

* Node.js
* Express.js
* Mongoose
* MongoDB
* CORS
* dotenv

## Product Fields

Each product contains:

| Field     | Description           |
| --------- | --------------------- |
| id        | Unique product ID     |
| name      | Product name          |
| category  | Product category      |
| price     | Product price         |
| quantity  | Available quantity    |
| minStock  | Minimum stock level   |
| createdAt | Product creation date |

A product is considered **Low Stock** when:

```text
quantity <= minStock
```

## Project Structure

```text
inventory-management-system/
│
├── backend/
│   ├── config/
│   │   └── db.js
│   ├── controllers/
│   │   └── productController.js
│   ├── models/
│   │   └── Product.js
│   ├── routes/
│   │   └── productRoutes.js
│   ├── middleware/
│   │   └── errorMiddleware.js
│   ├── .env.example
│   ├── package.json
│   └── server.js
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── ProductForm.jsx
│   │   │   ├── ProductTable.jsx
│   │   │   ├── SearchFilter.jsx
│   │   │   └── Navbar.jsx
│   │   ├── services/
│   │   │   └── productService.js
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   └── index.css
│   ├── .env.example
│   └── package.json
│
├── .gitignore
└── README.md
```

## REST API

Base URL:

```text
http://localhost:5000/api
```

### 1. Add Product

```http
POST /api/products
```

Example request:

```json
{
  "name": "Laptop",
  "category": "Electronics",
  "price": 55000,
  "quantity": 10,
  "minStock": 3
}
```

### 2. Get All Products

```http
GET /api/products
```

Returns all products.

### 3. Update Product

```http
PUT /api/products/:id
```

Example:

```http
PUT /api/products/PRODUCT_ID
```

### 4. Delete Product

```http
DELETE /api/products/:id
```

Example:

```http
DELETE /api/products/PRODUCT_ID
```

### 5. Get Low Stock Products

```http
GET /api/products/low-stock
```

Returns products where:

```text
quantity <= minStock
```

## Prerequisites

Install the following before running the project:

* Node.js
* npm
* MongoDB
* Git

Check Node.js:

```bash
node --version
```

Check npm:

```bash
npm --version
```

## MongoDB Setup

Make sure MongoDB is installed and running.

The application uses the database:

```text
inventoryDB
```

Default local MongoDB connection:

```text
mongodb://127.0.0.1:27017/inventoryDB
```

## Backend Setup

Open a terminal and run:

```bash
cd backend
npm install
```

Create a `.env` file inside the `backend` folder:

```env
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/inventoryDB
```

Start the backend:

```bash
npm run dev
```

Or:

```bash
npm start
```

Backend will run at:

```text
http://localhost:5000
```

## Frontend Setup

Open another terminal:

```bash
cd frontend
npm install
```

Create a `.env` file inside the `frontend` folder:

```env
VITE_API_URL=http://localhost:5000/api
```

Start the frontend:

```bash
npm run dev
```

Open the URL shown by Vite, usually:

```text
http://localhost:5173
```

## How the Application Works

1. User opens the Inventory Dashboard.
2. Existing products are loaded from MongoDB through the backend API.
3. User can add a new product using the form.
4. Products are displayed in a table.
5. User can search products by name.
6. User can filter products by category.
7. Low-stock products are automatically highlighted.
8. User can edit product information.
9. User can delete products after confirmation.
10. Dashboard statistics update according to the inventory data.

## Validation

The application validates:

* Product name is required.
* Category is required.
* Price cannot be negative.
* Quantity cannot be negative.
* Minimum stock cannot be negative.
* Invalid product IDs are handled.
* Non-existent products return an appropriate error.
* Database and server errors are handled properly.

## Error Handling

The backend provides meaningful error responses such as:

```json
{
  "success": false,
  "message": "Product not found"
}
```

The frontend displays appropriate error and success messages to the user.

## Assumptions

* Authentication is not required for this assignment.
* MongoDB is running locally.
* Product names are required.
* Price, quantity and minimum stock cannot be negative.
* A product is considered low stock when `quantity <= minStock`.
* The application is designed for basic inventory management.

## Future Improvements

Possible future improvements include:

* User authentication
* Admin and user roles
* Product images
* Pagination
* Sorting
* Inventory history
* Stock-in and stock-out transactions
* Dashboard charts
* Low-stock notifications
* CSV/PDF export
* MongoDB Atlas
* Cloud deployment

## Testing

The following functionality was tested:

* Add product
* View products
* Update product
* Delete product
* Search by name
* Filter by category
* Low-stock detection
* Low-stock highlighting
* Invalid input handling
* Invalid product ID
* Non-existent product
* Empty product list
* Database/API error handling

API endpoints can also be tested using Postman.

## Screenshots

Add screenshots of the application here.

Example:

```text
1. Dashboard
2. Add Product
3. Product List
4. Edit Product
5. Low Stock Products
```

## Demo Video

Add the demo video link here after recording the project demonstration.

The demo should show:

```text
1. Dashboard
2. Add a product
3. View products
4. Search product
5. Filter by category
6. Edit product
7. Delete product
8. Show low-stock product
```

## GitHub Submission

Initialize Git:

```bash
git init
```

Add files:

```bash
git add .
```

Commit:

```bash
git commit -m "Initial Inventory Management System"
```

Add your public GitHub repository:

```bash
git remote add origin YOUR_GITHUB_REPOSITORY_URL
```

Push the project:

```bash
git branch -M main
git push -u origin main
```

Make sure the GitHub repository is **Public** and contains all required files.

## Conclusion

The Inventory Management System provides a simple and efficient way to manage products and monitor inventory levels using a modern full-stack architecture with **React, Node.js, Express.js, and MongoDB**.
