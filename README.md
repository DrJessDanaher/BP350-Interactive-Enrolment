# BP350-Interactive-Enrolment
<html>
<head>
    <style>
        .container {
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
        }
        .course-box {
            background-color: lightgrey;
            padding: 10px;
            margin: 5px;
            width: 300px;
            text-align: center;
            border: 1px solid black;
        }
        .red-box {
            background-color: lightcoral;
        }
        .blue-box {
            background-color: lightblue;
        }
    </style>
</head>
<body>
    <select id="majorSelection" onchange="updateCourses()">
        <option value="">Select a Science Major</option>
        <option value="NutritionScience">Nutrition Science</option>
        <option value="Statistics">Statistics</option>
        <option value="FoodScience">Food Science and Technology</option>
        <option value="Mathematics">Mathematics</option>
    </select>

    <div class="container">
        <div class="header">Year 1 - Semester 1</div>
        <div class="course-box">Data for a Scientific World</div>
        <div class="course-box">The World of Life Sciences</div>
        <div class="course-box">Physical Sciences in Action</div>
        <div class="course-box">A Mathematical Toolbox for Scientists</div>

        <div class="header">Year 1 - Semester 2</div>
        <div class="course-box">5</div>
        <div class="course-box">6</div>
        <div class="course-box">7</div>
        <div class="course-box">8</div>

        <div class="header">Year 2 - Semester 1</div>
        <div class="course-box">9</div>
        <div class="course-box">10</div>
        <div class="course-box">11</div>
        <div class="course-box">12</div>

        <div class="header">Year 2 - Semester 2</div>
        <div class="course-box">13</div>
        <div class="course-box">14</div>
        <div class="course-box">15</div>
        <div class="course-box">16</div>

        <div class="header">Year 3 - Semester 1</div>
        <div class="course-box">17</div>
        <div class="course-box">18</div>
        <div class="course-box">19</div>
        <div class="course-box">20</div>

        <div class="header">Year 3 - Semester 2</div>
        <div class="course-box">21</div>
        <div class="course-box">22</div>
        <div class="course-box">23</div>
        <div class="course-box">24</div>
    </div>

    <script>
        function updateCourses() {
            var major = document.getElementById("majorSelection").value;
            resetCourses();

            if (major === "NutritionScience") {
                updateCourse("course5", "Nutritional Physiology", "red-box");
                updateCourse("course6", "Chemistry for Food and Life Sciences", "red-box");
                updateCourse("course9", "Nutrition, Health and Disease", "red-box");
                updateCourse("course12", "Applied Nutrition", "red-box");
                updateCourse("course13", "Human Sensory Evaluation", "red-box");
                updateCourse("course17", "Plant Processing for Nutrition and Health", "red-box");
                updateCourse("course18", "Community Nutrition", "red-box");
                updateCourse("course19", "Entrepreneurship in Nutrition and Food", "red-box");
            } else if (major === "Statistics") {
                updateCourse("course5", "Statistical Methodologies", "red-box");
                updateCourse("course6", "Data Visualisation with R", "red-box");
                updateCourse("course9", "Linear Models and Experimental Design", "red-box");
                updateCourse("course12", "Time Series and Forecasting", "red-box");
                updateCourse("course13", "Machine Learning", "red-box");
                updateCourse("course17", "Analysis of Categorical Data", "red-box");
                updateCourse("course18", "Multivariate Analysis", "red-box");
                updateCourse("course19", "Statistical Inference OR Applied Bayesian Statistics", "red-box");
            } else if (major === "FoodScience") {
                updateCourse("course7", "Introduction to Microbiology for Food and Nutrition", "blue-box");
                updateCourse("course10", "Food and Nutritional Chemistry", "blue-box");
                updateCourse("course11", "Food Processing Technology", "blue-box");
                updateCourse("course15", "Rheology and Food Biophysics", "blue-box");
                updateCourse("course16", "Food Microbiology", "blue-box");
                updateCourse("course21", "Food Safety Analysis", "blue-box");
                updateCourse("course22", "Food Manufacturing: Animal Products", "blue-box");
                updateCourse("course23", "Food Packaging and Labelling", "blue-box");
            } else if (major === "Mathematics") {
                updateCourse("course7", "Vectors and Calculus", "blue-box");
                updateCourse("course10", "Advanced Linear Algebra with Vector Calculus", "blue-box");
                updateCourse("course11", "Discrete Mathematics", "blue-box");
                updateCourse("course15", "Modelling with Differential Equations", "blue-box");
                updateCourse("course16", "Real and Complex Analysis", "blue-box");
                updateCourse("course21", "Optimisation", "blue-box");
                updateCourse("course22", "Algebra for Information Security", "blue-box");
                updateCourse("course23", "Complex Networks OR Mathematical Computing and Algorithms", "blue-box");
            }
        }

        function resetCourses() {
            for (var i = 5; i <= 24; i++) {
                var courseId = "course" + i;
                updateCourse(courseId, i.toString(), "");
            }
        }

        function updateCourse(courseId, newName, newClass) {
            var courseElement = document.getElementById(courseId);
            if (courseElement) {
                courseElement.innerHTML = newName;
                courseElement.className = "course-box " + newClass;
            }
        }
    </script>
</body>
</html>
