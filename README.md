# ANDROID-DEVELOPMENT-TASKS
Android development
# TASK -1 Build a calculator app that can perform basic arithmetic operations.
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Calculator</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="calculator">
    <input type="text" id="display" disabled />
    <div class="buttons">
      <button onclick="clearDisplay()">C</button>
      <button onclick="append('/')">÷</button>
      <button onclick="append('*')">×</button>
      <button onclick="append('-')">−</button>

      <button onclick="append('7')">7</button>
      <button onclick="append('8')">8</button>
      <button onclick="append('9')">9</button>
      <button onclick="append('+')">+</button>

      <button onclick="append('4')">4</button>
      <button onclick="append('5')">5</button>
      <button onclick="append('6')">6</button>
      <button onclick="calculate()">=</button>

      <button onclick="append('1')">1</button>
      <button onclick="append('2')">2</button>
      <button onclick="append('3')">3</button>
      <button onclick="append('0')">0</button>
      <button onclick="append('.')">.</button>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>

OUTPUT:

C ÷ × − 7 8 9 + 4 5 6 = 1 2 3 0 .


# TASK-2 TO DO LIST Create a To-Do list app that allows users to add, edit, and delete tasks.
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>TO-DO List</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <script type="text/javascript" src="script.js"></script>
  </body>
</html>
<!DOCTYPE html>
<html lang="en">
  <head>
    <title>TO-DO List</title>
    <link rel="stylesheet" href="style.css" />
  </head>
  <body>
    <!-- create a container for the todo list -->
    <div id="todo-container">
      <!-- todo list header -->
      <div id="header">
        <h1>To Do List</h1>
      </div>

      <!-- create input box -->
      <div id="todo-form">
        <input
          type="text"
          class="input-item"
          name="input_box"
          id="input-box"
          placeholder="Add Task"
        />

        <!-- add button -->
        <button id="input-button" onclick="addTask()">Add</button>
      </div>

      <!-- task list -->
      <h2>Task List</h2>
      <ul id="list-container"></ul>
    </div>

    <script type="text/javascript" src="script.js"></script>
  </body>
</html>
<img width="1084" height="618" alt="image" src="https://github.com/user-attachments/assets/37d130f0-7999-4768-8ab3-4512fe2558b2" />

# Add Counters
<hr />
<!-- task list counter -->
<div class="counter-container">
  <div id="task-counters">
    Completed: <span id="completed-counter">0</span> | Uncompleted:
    <span id="uncompleted-counter">0</span>
  </div>
</div>
<img width="662" height="521" alt="image" src="https://github.com/user-attachments/assets/67f3e5b5-2e89-49a0-a63b-a59561125ece" />

# Add JavaScript
const inputBox = document.getElementById("input-box");
const listContainer = document.getElementById("list-container");
function addTask() {
  const task = inputBox.value.trim();
  if (!task) {
    alert("Please write down a task");
    return;
  }
}
const li = document.createElement("li");
li.innerHTML = `
  <label>
    <input type="checkbox">
    <span>${task}</span>
  </label>
  <span class="edit-btn">Edit</span>
  <span class="delete-btn">Delete</span>
`;
listContainer.appendChild(li);

<img width="600" height="557" alt="image" src="https://github.com/user-attachments/assets/291fdfee-5b78-4630-bb1b-fb0c1d9b2ea0" />

inputBox.value = "";
function addTask() {
  const task = inputBox.value.trim();
  if (!task) {
    alert("Please write down a task");
    return;
  }

  li.innerHTML = `
    <label>
      <input type="checkbox">
      <span>${task}</span>
    </label>
    <span class="edit-btn">Edit</span>
    <span class="delete-btn">Delete</span>
    `;

  listContainer.appendChild(li);
  inputBox.value = "";
}

# Activate Task Buttons
const checkbox = li.querySelector("input");
const editBtn = li.querySelector(".edit-btn");
const taskSpan = li.querySelector("span");
const deleteBtn = li.querySelector(".delete-btn");
checkbox.addEventListener("click", function () {
  li.classList.toggle("completed", checkbox.checked);
});
.completed {
  text-decoration: line-through;
  color: gray;
  border: 1px solid gray;
}
editBtn.addEventListener("click", function () {
  const update = prompt("Edit task:", taskSpan.textContent);
  if (update !== null) {
    taskSpan.textContent = update;
    li.classList.remove("completed");
  }
});
li.classList.remove("completed");
const completedCounter = document.getElementById("completed-counter");
const uncompletedCounter = document.getElementById("uncompleted-counter");
function updateCounters() {
  const completedTasks = document.querySelectorAll(".completed").length;
  const uncompletedTasks =
    document.querySelectorAll("li:not(.completed)").length;

  completedCounter.textContent = completedTasks;
  uncompletedCounter.textContent = uncompletedTasks;
}
updateCounters();
checkbox.addEventListener("click", function () {
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
  margin: 0 auto;
  border: 2px solid #0033ff;
  padding: 20px;
  color: white;
  border-radius: 15px;
}
#header {
  margin: 5px;
  font-size: 20px;
  text-align: center;
}
h1 {
  margin-bottom: 20px; 
}
#input-box {
  width: 200px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  margin-right: 5px;
  font-size: 20px;
}
#input-button {
  font-size: 20px;
  cursor: pointer;
  transition: 0.4s;
  padding: 10px;
  border: none;
  border-radius: 5px;
  background-color: #2e60ea;
}

#input-button:hover {
  background-color: #9eb7fd; 
}
ul {
  list-style: none;
  padding: 0;
  margin-top: 20px;
  text-align:left;
}
li {
border: 1px solid white;
border-radius: 5px;
margin-bottom: 10px;
padding: 10px;
margin-top: 10px;
}
.edit-btn, .delete-btn {
  float: right;
  color:crimson;
  cursor: pointer;
  margin: 3px 5px;
  border: none;
  padding: 3px 5px;
  background: none;
} 
.completed {
  text-decoration: line-through;
  color: gray;
  border: 1px solid gray;
}

<img width="1328" height="1172" alt="image" src="https://github.com/user-attachments/assets/164a5558-5087-4933-b859-0e5107c55c27" />





