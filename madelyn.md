---
layout: page
title: Madelyn's BTC
---

# Madelyn Owns Bitcoin!

<button id="convert-btn">Click Here</button>
<p id="conversion-result"></p>

<script>
document.getElementById('convert-btn').addEventListener('click', function() {
    fetch('https://api.coingecko.com/api/v3/simple/price?ids=bitcoin&vs_currencies=usd')
        .then(response => response.json())
        .then(data => {
            const btcPrice = data.bitcoin.usd;
            const amountBtc = (0.00231961+0.00049515);
            const usdValue = btcPrice * amountBtc;
            document.getElementById('conversion-result').textContent = `At this point in time, Madelyn has approximately $${usdValue.toFixed(2)} USD`;
        })
        .catch(error => {
            console.error('Error fetching BTC data:', error);
            document.getElementById('conversion-result').textContent = 'Error fetching data';
        });
});
</script>
