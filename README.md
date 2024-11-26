<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daily Health Tracker</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f9;
        }
        header {
            background-color: #4CAF50;
            color: white;
            text-align: center;
            padding: 10px 0;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        table, th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        td {
            background-color: #f9f9f9;
        }
        .container {
            width: 80%;
            margin: 0 auto;
        }
        .input-field {
            padding: 5px;
            margin: 10px 0;
            width: 100%;
        }
        button {
            background-color: #4CAF50;
            color: white;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
        .actions {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
    </style>
</head>
<body>

<header>
    <h1>Health and Routine Tracker</h1>
</header>

<div class="container">
    <h2>Track Daily Activities and Meals</h2>

    <!-- Input form for each individual -->
    <div class="input-form">
        <label for="name">Name:</label>
        <input type="text" id="name" class="input-field" placeholder="Enter Name">
        
        <div class="actions">
            <div>
                <label for="wakeup-time">Wakeup Time:</label>
                <input type="time" id="wakeup-time" class="input-field">
            </div>
            
            <div>
                <label for="activity">Physical Activity:</label>
                <input type="text" id="activity" class="input-field" placeholder="Enter activity">
            </div>
        </div>

        <div class="actions">
            <div>
                <label for="lunch">Lunch (What did you eat?):</label>
                <input type="text" id="lunch" class="input-field" placeholder="Enter lunch details">
            </div>

            <div>
                <label for="breakfast">Breakfast (What did you eat?):</label>
                <input type="text" id="breakfast" class="input-field" placeholder="Enter breakfast details">
            </div>
        </div>

        <div class="actions">
            <div>
                <label for="evening-snacks">Evening Snacks (What did you eat?):</label>
                <input type="text" id="evening-snacks" class="input-field" placeholder="Enter evening snacks details">
            </div>

            <div>
                <label for="dinner">Dinner (What did you eat?):</label>
                <input type="text" id="dinner" class="input-field" placeholder="Enter dinner details">
            </div>
        </div>

        <div class="actions">
            <div>
                <label for="akant-dhyan">Akant Dhyan:</label>
                <select id="akant-dhyan">
                    <option value="Yes">Yes</option>
                    <option value="No">No</option>
                </select>
            </div>

            <div>
                <label for="samuhik-dhyan">Samuhik Dhyan:</label>
                <select id="samuhik-dhyan">
                    <option value="Yes">Yes</option>
                    <option value="No">No</option>
                </select>
            </div>
        </div>

        <div class="actions">
            <div>
                <label for="unhealthy-food">Unhealthy Food:</label>
                <input type="text" id="unhealthy-food" class="input-field" placeholder="Enter unhealthy food">
            </div>

            <div>
                <label for="healthy-food">Healthy Food:</label>
                <input type="text" id="healthy-food" class="input-field" placeholder="Enter healthy food">
            </div>
        </div>

        <div class="actions">
            <div>
                <label for="sleep-time">Sleep Time:</label>
                <input type="time" id="sleep-time" class="input-field">
            </div>
        </div>

        <button onclick="addData()">Submit</button>
    </div>

    <!-- Display the entered data in a table -->
    <h2>Data for the Month</h2>
    <table id="data-table">
        <thead>
            <tr>
                <th>Name</th>
                <th>Wakeup Time</th>
                <th>Physical Activity</th>
                <th>Breakfast</th>
                <th>Lunch</th>
                <th>Evening Snacks</th>
                <th>Dinner</th>
                <th>Akant Dhyan</th>
                <th>Samuhik Dhyan</th>
                <th>Unhealthy Food</th>
                <th>Healthy Food</th>
                <th>Sleep Time</th>
            </tr>
        </thead>
        <tbody>
            <!-- Dynamic rows will be inserted here -->
        </tbody>
    </table>
</div>

<script>
    function addData() {
        const name = document.getElementById('name').value;
        const wakeupTime = document.getElementById('wakeup-time').value;
        const activity = document.getElementById('activity').value;
        const breakfast = document.getElementById('breakfast').value;
        const lunch = document.getElementById('lunch').value;
        const eveningSnacks = document.getElementById('evening-snacks').value;
        const dinner = document.getElementById('dinner').value;
        const akantDhyan = document.getElementById('akant-dhyan').value;
        const samuhikDhyan = document.getElementById('samuhik-dhyan').value;
        const unhealthyFood = document.getElementById('unhealthy-food').value;
        const healthyFood = document.getElementById('healthy-food').value;
        const sleepTime = document.getElementById('sleep-time').value;

        const table = document.getElementById('data-table').getElementsByTagName('tbody')[0];
        const newRow = table.insertRow();

        newRow.innerHTML = `
            <td>${name}</td>
            <td>${wakeupTime}</td>
            <td>${activity}</td>
            <td>${breakfast}</td>
            <td>${lunch}</td>
            <td>${eveningSnacks}</td>
            <td>${dinner}</td>
            <td>${akantDhyan}</td>
            <td>${samuhikDhyan}</td>
            <td>${unhealthyFood}</td>
            <td>${healthyFood}</td>
            <td>${sleepTime}</td>
        `;

        // Reset the form fields
        document.querySelector('form').reset();
    }
</script>

</body>
</html>
