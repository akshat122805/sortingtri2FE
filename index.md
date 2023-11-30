<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CrunkinCryptos Dashboard</title>
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            margin: 0;
            padding: 0;
            color: #333;
            background-color: #f4f4f4;
        }

        nav {
            background-color: navy;
            color: white;
            display: flex;
            justify-content: space-between;
            padding: 10px;
            align-items: center;
        }

        .brand-name {
            font-size: 24px;
            font-weight: bold;
        }

        #search-box {
            font-size: 16px;
            padding: 5px;
            margin-left: auto;
        }

        #nav-links a {
            color: white;
            text-decoration: none;
            margin: 0 10px;
        }

        #nav-links a:hover {
            text-decoration: underline;
        }

        .container {
            padding: 20px;
        }

        .section {
            margin-bottom: 40px;
        }

        .section h2 {
            color: navy;
        }

        .section p {
            line-height: 1.6;
        }
    </style>
</head>
<body>
    <nav>
        <span class="brand-name">CrunchCrypto</span>
        <div id="nav-links">
            <a href="#cryptocurrencies">Cryptocurrencies</a>
            <a href="#about">About</a>
            <a href="#news">News</a>
        </div>
        <input type="text" id="search-box" placeholder="Search ticker...">
    </nav>

    <div class="container">
        <div id="cryptocurrencies" class="section">
            <h2>Cryptocurrencies</h2>
            <p>Explore the world of cryptocurrencies. Discover the latest trends, prices, and news about Bitcoin, Ethereum, and more.</p>
        </div>

        <div id="about" class="section">
            <h2>About Crunch Crypto</h2>
            <p>Crunch Crypto is your go-to platform for all things crypto. We provide up-to-date information, analysis, and insights into the dynamic world of digital currencies.</p>
        </div>

        <div id="news" class="section">
            <h2>Latest Crypto News</h2>
            <p>Stay informed with the latest news in the cryptocurrency world. Our news section covers everything from market trends to regulatory changes.</p>
        </div>
    </div>
</body>
</html>

<script>
    function searchCrypto() {
        var ticker = document.getElementById('search-box').value;

        // Making an AJAX request to your Spring Boot backend
        fetch(`/api/crypto/market/${ticker}`)
            .then(response => response.json())
            .then(data => {
                // Process and display the data
                console.log(data); // Replace this with actual code to update your page
            })
            .catch(error => console.error('Error:', error));
    }

    // Add an event listener to the search box
    document.getElementById('search-box').addEventListener('keyup', function(event) {
        if (event.key === 'Enter') {
            searchCrypto();
        }
    });
</script>
