# Currency Converter

## Overview

This project is a simple webpage designed to convert amounts between three major currencies: USD (United States Dollar), EUR (Euro), and INR (Indian Rupee). It features an input box where users can enter the amount they wish to convert, a dropdown menu to select the currencies for conversion, and a "Convert" button that calculates and displays the converted value.

## Setup

To set up the project, simply clone this repository and open the `index.html` file in any web browser. No additional software or dependencies are required.

```bash
git clone <repository-url>
cd currency-converter
open index.html
```

## Usage

1. Open the `index.html` file in your preferred web browser.
2. You will see an input box; enter the amount you want to convert there.
3. Select the currency you wish to convert from using the first dropdown menu.
4. Select the currency you wish to convert to using the second dropdown menu.
5. Click on the "Convert" button.
6. The converted value will be displayed on the page.

## Code Explanation

Here's a brief explanation of the code that powers this project:

### index.html

This file contains the HTML structure and JavaScript logic required for the currency converter to function. The structure is simple and consists of the following main components:

- **Input Box**: An `<input>` element where users can enter the amount for conversion.
- **Dropdown Menus**: Two `<select>` elements for choosing the 'from' and 'to' currencies.
- **Convert Button**: A `<button>` element that triggers the conversion process when clicked.
- **Result Display**: A `<div>` or `<span>` element where the converted value is displayed after calculation.

#### JavaScript

The JavaScript portion includes:

- An event listener for the "Convert" button that retrieves the input amount and selected currencies.
- A conversion function that uses predefined exchange rates to calculate the converted amount.
- A DOM manipulation to display the converted result.

Example:
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Currency Converter</title>
</head>
<body>
    <h1>Currency Converter</h1>
    <input type="number" id="amount" placeholder="Enter amount" />
    <select id="fromCurrency">
        <option value="USD">USD</option>
        <option value="EUR">EUR</option>
        <option value="INR">INR</option>
    </select>
    <select id="toCurrency">
        <option value="USD">USD</option>
        <option value="EUR">EUR</option>
        <option value="INR">INR</option>
    </select>
    <button id="convertBtn">Convert</button>
    <div id="result"></div>

    <script>
        document.getElementById('convertBtn').addEventListener('click', function() {
            const amount = parseFloat(document.getElementById('amount').value);
            const fromCurrency = document.getElementById('fromCurrency').value;
            const toCurrency = document.getElementById('toCurrency').value;

            const exchangeRates = {
                'USD': {'EUR': 0.85, 'INR': 75},
                'EUR': {'USD': 1.18, 'INR': 88},
                'INR': {'USD': 0.013, 'EUR': 0.011}
            };

            const convertedAmount = amount * exchangeRates[fromCurrency][toCurrency];
            document.getElementById('result').innerText = `Converted Amount: ${convertedAmount.toFixed(2)} ${toCurrency}`;
        });
    </script>
</body>
</html>
```

## License

This project is licensed under the MIT License. For more information, please refer to the `LICENSE` file included in this repository.