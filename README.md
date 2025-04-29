<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Modern Age Calculator</title>
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: linear-gradient(135deg, #1f4037, #99f2c8);
      display: flex;
      align-items: center;
      justify-content: center;
      min-height: 100vh;
      padding: 20px;
      overflow: hidden;
    }

    .container {
      background: rgba(255, 255, 255, 0.1);
      backdrop-filter: blur(15px);
      border-radius: 20px;
      box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
      padding: 40px;
      width: 100%;
      max-width: 400px;
      text-align: center;
      color: #fff;
      animation: fadeIn 1s ease-out;
    }

    .container h1 {
      font-size: 2rem;
      margin-bottom: 25px;
    }

    input[type="date"] {
      padding: 15px;
      font-size: 16px;
      border: none;
      border-radius: 12px;
      width: 100%;
      margin-bottom: 20px;
      background-color: rgba(255, 255, 255, 0.2);
      color: #fff;
      outline: none;
      backdrop-filter: blur(5px);
    }

    button {
      background: linear-gradient(to right, #00c6ff, #0072ff);
      border: none;
      padding: 12px 25px;
      color: white;
      font-size: 16px;
      border-radius: 12px;
      cursor: pointer;
      transition: 0.3s ease;
      width: 100%;
    }

    button:hover {
      background: linear-gradient(to right, #0072ff, #00c6ff);
      transform: scale(1.03);
    }

    .result {
      margin-top: 25px;
      font-size: 1.3rem;
      font-weight: 600;
    }

    @keyframes fadeIn {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }

    ::placeholder {
      color: #eee;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🎂 Age Calculator</h1>
    <input type="date" id="dob" />
    <button onclick="calculateAge()">Calculate Age</button>
    <div class="result" id="result"></div>
  </div>

  <script>
    function calculateAge() {
      const input = document.getElementById("dob").value;
      const result = document.getElementById("result");

      if (!input) {
        result.textContent = "Please select your date of birth!";
        result.style.color = "#ffcccb";
        return;
      }

      const birthDate = new Date(input);
      const today = new Date();

      let ageYears = today.getFullYear() - birthDate.getFullYear();
      const m = today.getMonth() - birthDate.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < birthDate.getDate())) {
        ageYears--;
      }

      result.textContent = `🎉 You are ${ageYears} years old.`;
      result.style.color = "#ffffff";
    }
  </script>
</body>
</html>
