# Code-Alpha-task-3
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Issue Tracker</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Issue Tracker</h1>
    </header>

    <div class="container">
        <div id="issueForm">
            <h2>Create a New Issue</h2>
            <form id="newIssueForm">
                <label for="issueTitle">Title:</label>
                <input type="text" id="issueTitle" required>

                <label for="issueDescription">Description:</label>
                <textarea id="issueDescription" required></textarea>

                <button type="button" onclick="addIssue()">Create Issue</button>
            </form>
        </div>

        <div id="issuesList">
            <h2>Current Issues</h2>
            <div id="issueContainer"></div>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>
body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    margin: 0;
    padding: 0;
    background-color: #f8f8f8;
}

header {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1em;
}

.container {
    display: flex;
    justify-content: space-around;
    flex-wrap: wrap;
}

#issueForm, #issuesList {
    width: 45%;
    margin: 20px 0;
    padding: 20px;
    background-color: #fff;
    border-radius: 8px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

#issueForm {
    order: 1;
}

#issuesList {
    order: 2;
}

.issue {
    margin-bottom: 15px;
    padding: 15px;
    background-color: #f0f0f0;
    border-radius: 8px;
}

button {
    background-color: #333;
    color: white;
    padding: 10px 20px;
    border: none;
    border-radius: 4px;
    cursor: pointer;
}

button:hover {
    background-color: #555;
}

input, textarea {
    width: 100%;
    padding: 10px;
    margin-bottom: 10px;
    border: 1px solid #ddd;
    border-radius: 4px;
    box-sizing: border-box;
}
function addIssue() {
    var title = document.getElementById('issueTitle').value;
    var description = document.getElementById('issueDescription').value;

    if (title && description) {
        var issueContainer = document.getElementById('issueContainer');

        var issueDiv = document.createElement('div');
        issueDiv.className = 'issue';

        var issueTitle = document.createElement('h3');
        issueTitle.textContent = title;

        var issueDescription = document.createElement('p');
        issueDescription.textContent = description;

        issueDiv.appendChild(issueTitle);
        issueDiv.appendChild(issueDescription);

        issueContainer.appendChild(issueDiv);

        // Clear the form
        document.getElementById('newIssueForm').reset();
    } else {
        alert('Please fill in both title and description.');
    }
}
