# coreGPA.html
<!-- Braxdon Simmons, Dylan Mattern, Mckay Abott, Blake McAvoy, Saxon Cullimore, Aly Leavitt -->
<!-- HTML Core GPA group assignment -->


<!DOCTYPE html>
<html>
<head>
 <title>Core GPA Calculator</title>
</head>
<body>
 <h1>Core GPA Calculator</h1>
  <form>
   <label for="overallGPA">Overall GPA:</label>
   <input type="number" step="0.01" id="overallGPA" name="overallGPA"><br><br>


   <label for="last30CreditsGPA">Last 30 Credits GPA:</label>
   <input type="number" step="0.01" id="last30CreditsGPA" name="last30CreditsGPA"><br><br>


   <label for="accounting200Grade">Accounting 200 Grade:</label>
   <select id="accounting200Grade" name="accounting200Grade">
       <option value="A">A</option>
       <option value="A-">A-</option>
       <option value="B+">B+</option>
       <option value="B">B</option>
       <option value="B-">B-</option>
       <option value="C+">C+</option>
       <option value="C">C</option>
       <option value="C-">C-</option>
   </select><br><br>


   <label for="is201Grade">IS 201 Grade:</label>
   <select id="is201Grade" name="is201Grade">
       <option value="A">A</option>
       <option value="A-">A-</option>
       <option value="B+">B+</option>
       <option value="B">B</option>
       <option value="B-">B-</option>
       <option value="C+">C+</option>
       <option value="C">C</option>
       <option value="C-">C-</option>
   </select><br><br>


   <label for="is303Grade">IS 303 Grade:</label>
   <select id="is303Grade" name="is303Grade">
       <option value="A">A</option>
       <option value="A-">A-</option>
       <option value="B+">B+</option>
       <option value="B">B</option>
       <option value="B-">B-</option>
       <option value="C+">C+</option>
       <option value="C">C</option>
       <option value="C-">C-</option>
   </select><br><br>


   <label for="essayScore">Essay Score (0-4):</label>
   <input type="number" step="1" id="essayScore" name="essayScore" min="0" max="4"><br><br>


   <button type="button" onclick="calculateGPA()">Calculate GPA</button>
   <label id="calculatedGPA"></label>
 </form>


 <script>
   // JavaScript function to calculate the GPA
   function calculateGPA() {
     // Read input values
     var overallGPA = parseFloat(document.getElementById("overallGPA").value);
     var last30CreditsGPA = parseFloat(document.getElementById("last30CreditsGPA").value);
     var accounting200Grade = document.getElementById("accounting200Grade").value;
     var is201Grade = document.getElementById("is201Grade").value;
     var is303Grade = document.getElementById("is303Grade").value;
     var essayScore = parseFloat(document.getElementById("essayScore").value);


     // Convert letter grades to grade points
     var gradePoints = {
       "A": 4.0,
       "A-": 3.7,
       "B+": 3.3,
       "B": 3.0,
       "B-": 2.7,
       "C+": 2.3,
       "C": 2.0,
       "C-": 1.7,
       "D+": 1.3,
       "D": 1.0,
       "F": 0.0
     };
     var accounting200Points = gradePoints[accounting200Grade];
     var is201Points = gradePoints[is201Grade];
     var is303Points = gradePoints[is303Grade];


     // Calculate the Core GPA
       var coreGPA = (overallGPA * 0.12 + last30CreditsGPA * 0.18 + (accounting200Points * 0.05) +
                    (is201Points * 0.3) + (is303Points * 0.3) + (essayScore * 0.05));
     // Display the calculated GPA
     document.getElementById("calculatedGPA").innerHTML = "Calculated GPA: " + coreGPA.toFixed(2);
   }
 </script>
</body>
</html>



