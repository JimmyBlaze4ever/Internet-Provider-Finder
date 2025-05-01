<!DOCTYPE html>
<html>
<head>
  <title>Internet Provider Finder</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 50px;
    }
    button {
      margin: 10px;
      padding: 10px 20px;
      font-size: 16px;
      border: 1px solid #ccc;
      border-radius: 5px;
      cursor: pointer;
      background-color: #f0f0f0;
    }
    table {
      margin: 0 auto;
      border-collapse: collapse;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 8px;
    }
  </style>
</head>
<body>
  <h1>Internet Provider Finder</h1>
  <p>Choose what you want to do:</p>
  <button onclick="showAll()">Show Providers</button>
  <button onclick="compare()">Compare Providers</button>
  <button onclick="faq()">FAQs</button>
  <button onclick="links()">Useful Links</button>

  <div id="output"></div>

  <script>
    const providers = [
      { name: 'Provider A', speed: '100 Mbps', price: '$50/month' },
      { name: 'Provider B', speed: '200 Mbps', price: '$70/month' },
      { name: 'Provider C', speed: '50 Mbps', price: '$30/month' }
    ];

    function showAll() {
      const list = providers.map(p => `<li>${p.name} - ${p.speed} - ${p.price}</li>`).join('');
      document.getElementById('output').innerHTML = `<ul style='list-style: none; padding: 0;'>${list}</ul>`;
    }

    function compare() {
      let rows = providers.map(p => `<tr><td>${p.name}</td><td>${p.speed}</td><td>${p.price}</td></tr>`).join('');
      document.getElementById('output').innerHTML = `
        <table>
          <tr><th>Name</th><th>Speed</th><th>Price</th></tr>
          ${rows}
        </table>`;
    }

    function faq() {
      document.getElementById('output').innerHTML = `
        <p>Q: Can I compare providers? A: Yes</p>
        <p>Q: Is speed shown? A: Yes</p>`;
    }

    function links() {
      document.getElementById('output').innerHTML = `
        <h3>Helpful Resources</h3>
        <table>
          <tr><th>Link</th><th>Description</th></tr>
          <tr><td><a href='https://www.fcc.gov/broadband' target='_blank'>FCC Broadband Info</a></td><td>Official government internet info</td></tr>
          <tr><td><a href='https://www.speedtest.net' target='_blank'>Speedtest.net</a></td><td>Test your internet speed</td></tr>
        </table>
        <h3>Compare Sites</h3>
        <table>
          <tr><th>Website</th><th>Purpose</th></tr>
          <tr><td><a href='https://www.allconnect.com' target='_blank'>AllConnect</a></td><td>Compare ISPs in your area</td></tr>
          <tr><td><a href='https://www.highspeedinternet.com' target='_blank'>HighSpeedInternet</a></td><td>See reviews and comparisons</td></tr>
        </table>
      `;
    }
  </script>
</body>
</html>
