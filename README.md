<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>A T L Data</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background: #f4f7f6;
      color: #222;
    }

    header {
      background: #075e54;
      color: white;
      padding: 18px 20px;
      text-align: center;
    }

    header h1 {
      font-size: 28px;
    }

    header p {
      margin-top: 5px;
      font-size: 14px;
    }

    .hero {
      background: white;
      margin: 20px auto;
      padding: 25px 20px;
      max-width: 600px;
      text-align: center;
      border-radius: 15px;
      box-shadow: 0 4px 15px rgba(0,0,0,0.08);
    }

    .hero h2 {
      color: #075e54;
      margin-bottom: 10px;
    }

    .hero p {
      color: #666;
      margin-bottom: 20px;
    }

    .container {
      max-width: 600px;
      margin: auto;
      padding: 0 15px 30px;
    }

    .card {
      background: white;
      padding: 20px;
      margin-bottom: 15px;
      border-radius: 15px;
      box-shadow: 0 3px 12px rgba(0,0,0,0.06);
    }

    .card h3 {
      margin-bottom: 15px;
      color: #075e54;
    }

    label {
      display: block;
      margin: 10px 0 6px;
      font-weight: bold;
    }

    select,
    input {
      width: 100%;
      padding: 13px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }

    .plans {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
      margin-top: 10px;
    }

    .plan {
      border: 1px solid #ddd;
      padding: 15px;
      border-radius: 10px;
      text-align: center;
      cursor: pointer;
      background: #fafafa;
    }

    .plan:hover {
      border-color: #075e54;
    }

    .plan strong {
      display: block;
      color: #075e54;
      margin-bottom: 5px;
    }

    button {
      width: 100%;
      padding: 14px;
      margin-top: 18px;
      border: none;
      border-radius: 9px;
      background: #075e54;
      color: white;
      font-size: 17px;
      font-weight: bold;
      cursor: pointer;
    }

    button:hover {
      background: #064c44;
    }

    .services {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
    }

    .service {
      background: #f0f7f5;
      padding: 18px;
      border-radius: 10px;
      text-align: center;
    }

    footer {
      background: #075e54;
      color: white;
      text-align: center;
      padding: 20px;
      margin-top: 20px;
      font-size: 14px;
    }

    @media (max-width: 400px) {
      .plans,
      .services {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>

<body>

  <header>
    <h1>A T L Data</h1>
    <p>Fast • Simple • Reliable</p>
  </header>

  <section class="hero">
    <h2>Buy Data Easily</h2>
    <p>Choose your network and data plan below.</p>
  </section>

  <main class="container">

    <div class="card">
      <h3>📱 Buy Data</h3>

      <label for="network">Network</label>
      <select id="network">
        <option value="">Select Network</option>
        <option value="MTN">MTN</option>
        <option value="Airtel">Airtel</option>
        <option value="Glo">Glo</option>
        <option value="9mobile">9mobile</option>
      </select>

      <label for="phone">Phone Number</label>
      <input
        type="tel"
        id="phone"
        placeholder="08012345678"
        maxlength="11"
      >

      <label>Choose Data Plan</label>

      <div class="plans">
        <div class="plan" onclick="selectPlan('500MB', '₦150')">
          <strong>500MB</strong>
          ₦150
        </div>

        <div class="plan" onclick="selectPlan('1GB', '₦300')">
          <strong>1GB</strong>
          ₦300
        </div>

        <div class="plan" onclick="selectPlan('2GB', '₦600')">
          <strong>2GB</strong>
          ₦600
        </div>

        <div class="plan" onclick="selectPlan('5GB', '₦1,500')">
          <strong>5GB</strong>
          ₦1,500
        </div>
      </div>

      <input type="hidden" id="selectedPlan">

      <button onclick="buyData()">Buy Data</button>
    </div>


    <div class="card">
      <h3>⚡ Our Services</h3>

      <div class="services">
        <div class="service">📱 Data</div>
        <div class="service">☎️ Airtime</div>
        <div class="service">💳 Bills Payment</div>
        <div class="service">👤 User Account</div>
      </div>
    </div>


    <div class="card">
      <h3>📞 Contact A T L Data</h3>
      <p>Need help? Contact our support team.</p>

      <button onclick="contactWhatsApp()">
        Chat on WhatsApp
      </button>
    </div>

  </main>


  <footer>
    © 2026 A T L Data. All Rights Reserved.
  </footer>


  <script>

    let selectedPlan = "";

    function selectPlan(plan, price) {
      selectedPlan = plan + " - " + price;

      document.getElementById("selectedPlan").value = selectedPlan;

      alert("Selected: " + selectedPlan);
    }


    function buyData() {

      const network =
        document.getElementById("network").value;

      const phone =
        document.getElementById("phone").value;

      if (network === "") {
        alert("Please select your network.");
        return;
      }

      if (phone.length !== 11) {
        alert("Please enter a valid 11-digit phone number.");
        return;
      }

      if (selectedPlan === "") {
        alert("Please select a data plan.");
        return;
      }

      alert(
        "Order received!\\n\\n" +
        "Network: " + network + "\\n" +
        "Phone: " + phone + "\\n" +
        "Plan: " + selectedPlan
      );

      /*
        LATER:
        We will connect this button to:
        1. Payment Gateway
        2. Data Vending API
        3. Backend
        4. Transaction Database
      */
    }


    function contactWhatsApp() {

      const phoneNumber = "234XXXXXXXXXX";

      const message =
        "Hello A T L Data, I need help with my order.";

      window.open(
        "https://wa.me/" +
        phoneNumber +
        "?text=" +
        encodeURIComponent(message),
        "_blank"
      );
    }

  </script>

</body>
</html>
