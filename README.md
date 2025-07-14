# ANDROID-DEVELOPMENT-TASKS
Android development
# TASK -1 Build a calculator app that can perform basic arithmetic operations.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Calculator</title>
  <style>
    body {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: #f3f4f6;
      font-family: Arial, sans-serif;
    }
    .calculator {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    }
    .display {
      width: 240px;
      height: 50px;
      text-align: right;
      padding: 10px;
      font-size: 1.5rem;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
    .buttons {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }
    .buttons button {
      padding: 15px;
      font-size: 1.2rem;
      border: none;
      border-radius: 6px;
      background-color: #e5e7eb;
      cursor: pointer;
      transition: background 0.2s;
    }
    .buttons button:hover {
      background-color: #d1d5db;
    }
    .buttons .operator {
      background-color: #f59e0b;
      color: white;
    }
    .buttons .equal {
      background-color: #10b981;
      color: white;
    }
    .buttons .clear {
      background-color: #ef4444;
      color: white;
    }
  </style>
</head>
<body>
  <div class="calculator">
    <input type="text" class="display" id="display" disabled />
    <div class="buttons">
      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button class="operator" onclick="append('/')">/</button>

      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button class="operator" onclick="append('*')">*</button>

      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button class="operator" onclick="append('-')">-</button>

      <button onclick="append('0')">0</button>
      <button onclick="append('.')">.</button>
      <button class="equal" onclick="calculate()">=</button>
      <button class="operator" onclick="append('+')">+</button>

      <button class="clear" onclick="clearDisplay()">C</button>
    </div>
  </div>

  <script>
    const display = document.getElementById('display');

    function append(value) {
      display.value += value;
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = 'Error';
      }
    }

    function clearDisplay() {
      display.value = '';
    }
  </script>
</body>
</html>

# TASK-2 TO DO LIST Create a To-Do list app that allows users to add, edit, and delete tasks.


  
    return;kbox.addEventListener("click", function () {
  li.classList.toggle("completed", checkbox.checked);
  //add the function below
  updateCounters();
});
editBtn.addEventListener("click", function () {
  const update = prompt("Edit task:", taskSpan.textContent);
  if (update !== null) {
    taskSpan.textContent = update;
    li.classList.remove("completed");
    //add the code below
    checkbox.checked = false;
    updateCounters();
  }
});

<img width="600" height="408" alt="image" src="https://github.com/user-attachments/assets/68c892ee-420f-4a4a-a1df-3e9f13c1ffb1" />

deleteBtn.addEventListener("click", function () {
  if (confirm("Are you sure you want to delete this task?")) {
    li.remove();
    updateCounters();
  }
});

<img width="600" height="375" alt="image" src="https://github.com/user-attachments/assets/5fdeb9eb-b85d-4c8b-ab46-691f15f2ea07" />

# Add CSS
body { 
  background: rgb(0,0,0);
  background: radial-gradient(circle, rgba(0,0,0,0.028124999999999956) 0%, rgba(253,187,45,1) 100%);
  font-family: Arial, sans-serif;
  text-align: center;
  margin-top: 50px;
}
#todo-container {
  background: rgb(41, 33, 33);
  width: 400px;
  margin: 0 auto;
  border: 2px solid #0033ff;
  padding: 20px;
  color: white;
  border-radius: 15px;
}
#todo-container {
  background: rgb(41, 33, 33);
  width: 400px;

    const display = document.getElementById("display");
    const startBtn = document.getElementById("startBtn");
    const pauseBtn = document.getElementById("pauseBtn");
    const resetBtn = document.getElementById("resetBtn");

    function updateDisplay(ms) {
      const minutes = Math.floor(ms / 60000);
      const seconds = Math.floor((ms % 60000) / 1000);
      const milliseconds = ms % 1000;

      display.textContent = `${String(minutes).padStart(2, "0")}:${String(
        seconds
      ).padStart(2, "0")}:${String(milliseconds).padStart(3, "0")}`;
    }

    function startTimer() {
      startTime = Date.now() - elapsed;

      timerInterval = setInterval(() => {
        elapsed = Date.now() - startTime;
        updateDisplay(elapsed);
      }, 10); // Update every 10ms for milliseconds precision

      startBtn.disabled = true;
      pauseBtn.disabled = false;
      resetBtn.disabled = false;
    }

    function pauseTimer() {
      clearInterval(timerInterval);
      startBtn.disabled = false;
      pauseBtn.disabled = true;
    }

    function resetTimer() {
      clearInterval(timerInterval);
      elapsed = 0;
      updateDisplay(elapsed);
      startBtn.disabled = false;
      pauseBtn.disabled = true;
      resetBtn.disabled = true;
    }

    startBtn.addEventListener("click", startTimer);
    pauseBtn.addEventListener("click", pauseTimer);
    resetBtn.addEventListener("click", resetTimer);
  </script>
</body>
</html>


# TASK-4 Create a QR code scanner app that allows users to scan QR codes using their device's camera. Add feature to create new QR Codes.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>QR Code Scanner & Generator</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      background: #f0f0f0;
      padding: 20px;
    }
    #reader {
      width: 300px;
      margin: 0 auto;
    }
    #qrcode {
      margin: 20px auto;
    }
    input[type="text"] {
      padding: 10px;
      width: 80%;
      margin-bottom: 10px;
      border: 1px solid #ccc;
      border-radius: 6px;
    }
    button {
      padding: 10px 20px;
      margin: 10px;
      border: none;
      border-radius: 6px;
      background-color: #4caf50;
      color: white;
      cursor: pointer;
    }
    button:hover {
      background-color: #45a049;
    }
  </style>
  <script src="https://unpkg.com/html5-qrcode"></script>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>
</head>
<body>
  <h2>QR Code Scanner</h2>
  <div id="reader"></div>
  <p><strong>Scanned Result:</strong> <span id="result">None</span></p>

  <h2>QR Code Generator</h2>
  <input type="text" id="qrText" placeholder="Enter text to generate QR code" />
  <br />
  <button onclick="generateQRCode()">Generate QR Code</button>
  <div id="qrcode"></div>

  <script>
    // QR Code Scanner
    const resultElem = document.getElementById("result");

    function onScanSuccess(decodedText) {
      resultElem.textContent = decodedText;
    }

    const html5QrCode = new Html5Qrcode("reader");

    Html5Qrcode.getCameras().then(cameras => {
      if (cameras && cameras.length) {
        html5QrCode.start(
          cameras[0].id,
          {
            fps: 10,
            qrbox: 250
          },
          onScanSuccess
        );
      }
    }).catch(err => {
      console.error("Camera error:", err);
    });

    // QR Code Generator
    function generateQRCode() {
      const qrText = document.getElementById("qrText").value;
      document.getElementById("qrcode").innerHTML = ""; // Clear previous
      new QRCode("qrcode", {
        text: qrText,
        width: 256,
        height: 256
      });
    }
  </script>
</body>
</html>

