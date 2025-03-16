<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>E-Vehicle Services</title>
    <style>
        body { font-family: Arial, sans-serif; text-align: center; margin: 50px; }
        .service-card { border: 1px solid #ccc; padding: 20px; margin: 10px; display: inline-block; }
        button { background-color: green; color: white; padding: 10px 15px; border: none; }
    </style>
</head>
<body>
    <h1>Welcome to E-Vehicle Services</h1>
    <div class="service-card">
        <h3>Battery Swap</h3>
        <p>Quick battery replacement for your e-vehicle.</p>
        <button onclick="bookService('Battery Swap')">Book Now</button>
    </div>
    <div class="service-card">
        <h3>EV Charging</h3>
        <p>Find nearby EV charging stations.</p>
        <button onclick="bookService('EV Charging')">Book Now</button>
    </div>
    <script>
        function bookService(service) {
            fetch('/book-service', {
                method: 'POST',
                headers: { 'Content-Type': 'application/json' },
                body: JSON.stringify({ service: service })
            }).then(response => response.json())
            .then(data => alert(data.message))
            .catch(error => console.error('Error:', error));
        }
    </script>
</body>
</html>
