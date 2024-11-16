
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Dropshipping Store</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Welcome to My Dropshipping Store</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Shop</a></li>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </nav>
    </header>

    <section id="products">
        <h2>Featured Products</h2>
        <div class="product-list"></div>
    </section>

    <footer>
        <p>&copy; 2024 My Dropshipping Store. All rights reserved.</p>
    </footer>

    <script src="script.js"></script>
</body>
</html>
style.css
body {
    font-family: Arial, sans-serif;
    background-color: #f0f0f0;
    color: #333;
}

header {
    background-color: #007bff;
    color: #fff;
    padding: 1em;
    text-align: center;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 10px;
}

#products {
    margin: 20px;
    text-align: center;
}

.product-list {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

.product {
    background: #fff;
    border: 1px solid #ddd;
    border-radius: 5px;
    margin: 10px;
    padding: 10px;
    width: 200px;
}

.product img {
    max-width: 100%;
    height: auto;
}

button {
    background-color: #28a745;
    color: #fff;
    border: none;
    padding: 10px;
    cursor: pointer;
}
script.js
const products = [
    { id: 1, name: "Product 1", price: "$19.99", image: "https://via.placeholder.com/200" },
    { id: 2, name: "Product 2", price: "$29.99", image: "https://via.placeholder.com/200" },
    { id: 3, name: "Product 3", price: "$39.99", image: "https://via.placeholder.com/200" },
];

function displayProducts() {
    const productList = document.querySelector('.product-list');
    productList.innerHTML = '';

    products.forEach(product => {
        const productCard = document.createElement('div');
        productCard.classList.add('product');

        productCard.innerHTML = `
            <img src="${product.image}" alt="${product.name}">
            <h3>${product.name}</h3>
            <p>${product.price}</p>
            <button onclick="addToCart(${product.id})">Add to Cart</button>
        `;

        productList.appendChild(productCard);
    });
}

function addToCart(productId) {
    const product = products.find(p => p.id === productId);
    alert(`${product.name} has been added to your cart!`);
}

document.addEventListener('DOMContentLoaded', displayProducts);
