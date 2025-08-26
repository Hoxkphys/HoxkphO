<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>📚 Study Tracker</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<style>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 20px;
    /* Thay nền bằng hình */
    background: url('Thumbnail3.png') no-repeat center center fixed;
    background-size: cover;
    color: #2c3e50;
}

h1 {
    text-align: center;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
    background: rgba(255,255,255,0.85); /* Giữ bảng trong suốt để thấy nền */
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}

th, td {
    border: 1px solid #ddd;
    padding: 8px;
    text-align: center;
}

th {
    background: #3498db;
    color: white;
}

input, select, textarea {
    width: 90%;
    padding: 5px;
    border: 1px solid #ccc;
    border-radius: 4px;
}

button {
    margin: 10px 10px 0;
    padding: 10px 20px;
    border: none;
    border-radius: 6px;
    cursor: pointer;
}

button:hover {
    opacity: 0.9;
}

.add-btn { background: #2980b9; color: white; }
.save-btn { background: #27ae60; color: white; }
.delete-btn { background: #e74c3c; color: white; padding: 5px 10px; border-radius: 4px; cursor: pointer; }
.delete-btn:hover { opacity: 0.9; }

.notes-section, .chart-section {
    margin-top: 20px;
    padding: 15px;
    background: rgba(255,255,255,0.85); /* Bảng trong suốt */
    border-radius: 8px;
    box-shadow: 0 4px 10px rgba(0,0,0,0.2);
}

.focus-emoji { font-size: 1.2em; }
#summary { margin-top: 10px; font-weight: bold; }
</style>
</head>
<body>
<h1>📅 Study Tracker</h1>

<table id="studyTable">
<tr>
    <th>Date</th>
    <th>Start Time</th>
    <th>Category</th>
    <th>Study Time (minutes)</th>
    <th>Focus Rating</th>
    <th>Action</th>
</tr>
<tr>
    <td><input type="date"></td>
    <td><input type="time"></td>
    <td>
        <select>
            <option value="">-- Select --</option>
            <option value="Math">📐 Math</option>
            <option value="Physics">🔭 Physics</option>
            <option value="English">📘 English</option>
            <option value="Chemistry">⚗️ Chemistry</option>
            <option value="Coding">💻 Coding</option>
        </select>
    </td>
    <td><input type="number" min="0" placeholder="90" oninput="updateFocus(this)"></td>
    <td><span class="focus-emoji">❔</span></td>
    <td><button class="delete-btn" onclick="deleteRow(this)">❌</button></td>
</tr>
</table>

<button class="add-btn" onclick="addRow()">➕ Add Row</button>
<button class="save-btn" onclick="saveData()">💾 Save Progress</button>

<div class="notes-section">
<h2>📝 Daily Description</h2>
<textarea id="notes" rows="4" placeholder="Write more details about your study here..."></textarea>
</div>

<div class="chart-section">
<h2>📊 Study Progress</h2>
<label for="timeFilter">Select Time Range:</label>
<select id="timeFilter" onchange="updateChart()">
    <option value="hour">Hour of Day</option>
    <option value="day">Day of Week</option>
    <option value="week">Week of Month</option>
    <option value="month">Month of Year</option>
</select>
<canvas id="studyChart" width="400" height="200"></canvas>
<div id="summary"></div>
</div>

<script>
const focusMap=[
    {min:0, emoji:"💤", text:"Very Low"},
    {min:20, emoji:"😐", text:"Low"},
    {min:40, emoji:"⚡", text:"Medium"},
    {min:60, emoji:"💪", text:"High"},
    {min:90, emoji:"🏆🔥", text:"Excellent"}
];

const categoryEmoji={
    "Math":"📐",
    "Physics":"🔭",
    "English":"📘",
    "Chemistry":"⚗️",
    "Coding":"💻"
};

function updateFocus(input){
    const span=input.parentElement.nextElementSibling;
    let minutes=parseInt(input.value||0);
    input.value=minutes;
    let best=focusMap[0];
    for(let f of focusMap){
        if(minutes>=f.min) best=f;
    }
    span.textContent=`${best.emoji} ${best.text}`;
}

function addRow(){
    const table=document.getElementById("studyTable");
    const row=table.insertRow(-1);
    row.innerHTML=`
    <td><input type="date"></td>
    <td><input type="time"></td>
    <td>
        <select>
            <option value="">-- Select --</option>
            <option value="Math">📐 Math</option>
            <option value="Physics">🔭 Physics</option>
            <option value="English">📘 English</option>
            <option value="Chemistry">⚗️ Chemistry</option>
            <option value="Coding">💻 Coding</option>
        </select>
    </td>
    <td><input type="number" min="0" placeholder="90" oninput="updateFocus(this)"></td>
    <td><span class="focus-emoji">❔</span></td>
    <td><button class="delete-btn" onclick="deleteRow(this)">❌</button></td>
    `;
}

function deleteRow(btn){
    btn.parentElement.parentElement.remove();
}

function saveData(){
    alert("✅ Data saved (demo only).");
}

function isLeapYear(year){
    return (year%4===0 && year%100!==0) || (year%400===0);
}

function daysInMonth(month,year){
    if([1,3,5,7,8,10,12].includes(month)) return 31;
    if([4,6,9,11].includes(month)) return 30;
    return isLeapYear(year)?29:28;
}

let chart;

function updateChart(){
    const table=document.getElementById("studyTable");
    const filter=document.getElementById("timeFilter").value;
    let labels=[], datasets=[], summaryText="";
    const allData=[];

    for(let i=1;i<table.rows.length;i++){
        const row=table.rows[i];
        const date=row.cells[0].querySelector("input").value;
        const time=row.cells[1].querySelector("input").value;
        const category=row.cells[2].querySelector("select").value;
        const minutes=parseInt(row.cells[3].querySelector("input").value||0);
        const focus=row.cells[4].querySelector("span").textContent;
        if(date && time && category && minutes>0){
            allData.push({date,time,category,minutes,focus});
        }
    }

    const todayStr=new Date().toISOString().slice(0,10);

    if(filter==="hour"){
        labels=Array.from({length:24},(_,i)=>i+1+"h");
        const data=Array(24).fill(0);
        const bgColors=Array(24).fill('rgba(54,162,235,0.6)');
        let totalMinutes=0;
        allData.forEach(d=>{
            if(d.date===todayStr){
                const h=parseInt(d.time.split(":")[0]);
                data[h]+=d.minutes/60;
                totalMinutes+=d.minutes;
            }
        });
        datasets.push({label:"Hours", data, backgroundColor:bgColors});
        summaryText=`Total minutes today: ${totalMinutes}`;
    }

    if(filter==="day"){
        labels=["Mon","Tue","Wed","Thu","Fri","Sat","Sun"];
        const data=Array(7).fill(0);
        const bgColors=labels.map(()=> 'rgba(54,162,235,0.6)');
        let totalDays=0;
        allData.forEach(d=>{
            const day=new Date(d.date).getDay();
            const index=(day===0?6:day-1);
            data[index]+=d.minutes;
        });
        totalDays=data.reduce((a,b)=>b>0?a+1:a,0);
        datasets.push({label:"Minutes", data, backgroundColor:bgColors});
        summaryText=`Total active days this week: ${totalDays}`;
    }

    if(chart) chart.destroy();
    const ctx=document.getElementById("studyChart").getContext("2d");
    chart=new Chart(ctx,{
        type:'bar',
        data:{labels, datasets},
        options:{
            responsive:true,
            plugins:{legend:{display:false}},
            scales:{y:{beginAtZero:true}}
        }
    });

    document.getElementById("summary").textContent=summaryText;
}

document.getElementById("studyTable").addEventListener("input", updateChart);
window.onload=updateChart;
</script>
</body>
</html>

