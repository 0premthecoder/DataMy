<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.4/Chart.js"></script>
<body>
<table>
<tr>
<th>Average Sticks</th>
<th>Time Spents Mins</th>
</tr>
<tr>
<td id="avg">January</td>
<td  id="avg1" >$100</td>
</tr>
<h1 id="avg"></h1>
  <h1 id="avg1"></h1>
<canvas id="myChart" style="width:100%;max-width:600px"></canvas>

<script>
const yValues = [8,3,7,5,8,9,7,5,4,6,7,8,3,5,11,12,11];
const aver = yValues.reduce((a, b) => a + b, 0) / yValues.length;
const numbers = [];
for (let i = 1; i <= yValues.length; i++) {
  numbers.push(i);
}

document.getElementById("avg").innerHTML = aver;
document.getElementById("avg1").innerHTML = aver*25;


new Chart("myChart", {
  type: "bar",
  data: {
    labels: numbers,
    datasets: [{
      backgroundColor: barColors,
      data: yValues
    }]
  },
  options: {
    legend: {display: false},
    title: {
      display: true,
      text: "World Wine Production 2018"
    }
  }
});
</script>

</body>

