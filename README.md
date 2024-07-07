Name- Jatin Poonia , Id - CT04WD2272

Project Overview
This project is a simple, user-friendly to-do list web application built using HTML, CSS, and JavaScript. It allows users to add, complete, and delete tasks easily. The application aims to provide an intuitive interface for managing daily tasks.

Features
Add Tasks: Users can add tasks by typing into an input field and clicking the "Add Task" button or pressing the "Enter" key.
Complete Tasks: Users can mark tasks as completed by clicking on the task. Completed tasks are visually differentiated with a strikethrough and color change.
Delete Tasks: Users can delete tasks by clicking the "Delete" button next to each task.
Project Structure
vbnet
Copy code
to-do-list/
│
├── index.html
├── styles.css
└── script.js
index.html: The main HTML file containing the structure of the web application.
styles.css: The CSS file for styling the application.
script.js: The JavaScript file containing the functionality of the application.
How to Run the Project
Download or clone the project repository.
Open index.html in a web browser.
Code Files
index.html
html
Copy code
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do List</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>To-Do List</h1>
        <input type="text" id="new-task" placeholder="Add a new task">
        <button id="add-task">Add Task</button>
        <ul id="task-list"></ul>
    </div>
    <script src="script.js"></script>
</body>
</html>
styles.css
css
Copy code
body {
    font-family: Arial, sans-serif;
    background-color: #f7f7f7;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}

.container {
    background-color: #fff;
    padding: 20px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    width: 300px;
    text-align: center;
}

h1 {
    margin-bottom: 20px;
}

input[type="text"] {
    width: 80%;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 4px;
    margin-bottom: 10px;
}

button {
    padding: 10px 15px;
    border: none;
    background-color: #5cb85c;
    color: white;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #4cae4c;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    padding: 10px;
    border-bottom: 1px solid #ddd;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

li:last-child {
    border-bottom: none;
}

li.completed {
    text-decoration: line-through;
    color: #999;
}

li button {
    background-color: #d9534f;
    padding: 5px 10px;
}

li button:hover {
    background-color: #c9302c;
}
script.js
javascript
Copy code
document.addEventListener('DOMContentLoaded', () => {
    const addTaskButton = document.getElementById('add-task');
    const newTaskInput = document.getElementById('new-task');
    const taskList = document.getElementById('task-list');

    addTaskButton.addEventListener('click', () => {
        const taskText = newTaskInput.value.trim();
        if (taskText !== '') {
            const taskItem = document.createElement('li');
            taskItem.textContent = taskText;

            const deleteButton = document.createElement('button');
            deleteButton.textContent = 'Delete';
            deleteButton.addEventListener('click', () => {
                taskList.removeChild(taskItem);
            });

            taskItem.appendChild(deleteButton);
            taskItem.addEventListener('click', () => {
                taskItem.classList.toggle('completed');
            });

            taskList.appendChild(taskItem);
            newTaskInput.value = '';
        }
    });

    newTaskInput.addEventListener('keypress', (e) => {
        if (e.key === 'Enter') {
            addTaskButton.click();
        }
    });
});
![image](https://github.com/pooniajatin/CodTeh-Task-1/assets/141109606/c1f27ed2-6c3d-46de-9b0e-c9e581284721)
