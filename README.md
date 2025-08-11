# Give-your-opinion-
<html lang=”en”>
<head>
<meta charset=”UTF-8”>
<meta name=”viewport” content=”width=device-width, initial-scale=1.0”>
<title>Policy Suggestion Portal</title>
<style>
    Body {
        Font-family: Arial, sans-serif;
        Background-color: #ffffff;
        Color: #004d26;
        Margin: 0;
        Padding: 0;
    }
    Header {
        Background-color: #006633;
        Color: white;
        Padding: 15px;
        Text-align: center;
        Font-size: 1.5em;
        Font-weight: bold;
    }
    .container {
        Max-width: 800px;
        Margin: 20px auto;
        Padding: 15px;
    }
    Select, textarea, button {
        Width: 100%;
        Padding: 10px;
        Margin-top: 10px;
        Font-size: 1em;
        Border: 1px solid #ccc;
        Border-radius: 5px;
    }
    Button {
        Background-color: #006633;
        Color: white;
        Cursor: pointer;
        Border: none;
    }
    Button:hover {
        Background-color: #004d26;
    }
    .suggestions {
        Margin-top: 20px;
    }
    .suggestion {
        Border: 1px solid #ccc;
        Border-left: 5px solid #006633;
        Padding: 10px;
        Margin-bottom: 10px;
        Background: #f9f9f9;
    }
</style>
</head>
<body>

<header>Shape the Future — Your Policy Ideas Matter</header>

<div class=”container”>
    <h2>Submit Your Suggestion</h2>
    <select id=”department”>
        <option value=””>Select Department</option>
        <option>Education</option>
        <option>Health</option>
        <option>Infrastructure</option>
        <option>Security</option>
        <option>Transport</option>
        <option>Energy</option>
        <option>Environment</option>
        <option>Economy</option>
    </select>
    <textarea id=”opinion” placeholder=”Write your policy suggestion here…” rows=”4”></textarea>
    <button onclick=”submitOpinion()”>Submit</button>

    <h2>View Suggestions</h2>
    <select id=”viewDept” onchange=”viewSuggestions()”>
        <option value=””>Select Department</option>
        <option>Education</option>
        <option>Health</option>
        <option>Infrastructure</option>
        <option>Security</option>
        <option>Transport</option>
        <option>Energy</option>
        <option>Environment</option>
        <option>Economy</option>
    </select>
    
    <div class=”suggestions” id=”suggestionsList”></div>
</div>

<script>
    Let data = {};

    Function submitOpinion() {
        Const dept = document.getElementById(‘department’).value;
        Const opinion = document.getElementById(‘opinion’).value.trim();
        
        If (!dept || !opinion) {
            Alert(“Please select a department and write your suggestion.”);
            Return;
        }
        
        If (!data[dept]) data[dept] = [];
        Data[dept].push(opinion);
        
        Document.getElementById(‘opinion’).value = “”;
        Alert(“Your suggestion has been added!”);
    }

    Function viewSuggestions() {
        Const dept = document.getElementById(‘viewDept’).value;
        Const listDiv = document.getElementById(‘suggestionsList’);
        listDiv.innerHTML = “”;
        
        if (!dept || !data[dept] || data[dept].length === 0) {
            listDiv.innerHTML = “<p>No suggestions yet for this department.</p>”;
            return;
        }
        
        Data[dept].forEach(op => {
            Const div = document.createElement(‘div’);
            div.className = ‘suggestion’;
            div.textContent = op;
            listDiv.appendChild(div);
        });
    }
</script>

</body>
</html>
