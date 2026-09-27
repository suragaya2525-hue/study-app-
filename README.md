# study-app-
here you can explore and create your own study timetable and can make use of it really well.
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>My Reading Timetable</title>

    <style>
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: Arial, sans-serif;
        }

        body {
            background: #f4f7fb;
            color: #222;
            transition: 0.3s;
        }

        header {
            background: linear-gradient(135deg, #4f46e5, #7c3aed);
            color: white;
            text-align: center;
            padding: 30px 15px;
        }

        header h1 {
            font-size: 32px;
            margin-bottom: 8px;
        }

        header p {
            font-size: 16px;
        }

        .container {
            max-width: 1000px;
            margin: 25px auto;
            padding: 0 15px;
        }

        .top-bar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        button {
            border: none;
            padding: 10px 16px;
            border-radius: 8px;
            cursor: pointer;
            font-size: 14px;
        }

        .dark-btn {
            background: #222;
            color: white;
        }

        .reset-btn {
            background: #ef4444;
            color: white;
        }

        .progress-box {
            background: white;
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 25px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
        }

        .progress-title {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-weight: bold;
        }

        .progress-bar {
            width: 100%;
            height: 15px;
            background: #e5e7eb;
            border-radius: 20px;
            overflow: hidden;
        }

        .progress-fill {
            height: 100%;
            width: 0%;
            background: linear-gradient(90deg, #22c55e, #16a34a);
            transition: width 0.4s;
        }

        .timetable {
            display: grid;
            gap: 15px;
        }

        .day {
            background: white;
            border-radius: 15px;
            padding: 20px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.08);
        }

        .day h2 {
            color: #4f46e5;
            margin-bottom: 15px;
        }

        .session {
            display: grid;
            grid-template-columns: 130px 1fr 100px;
            align-items: center;
            gap: 15px;
            padding: 15px;
            margin: 10px 0;
            background: #f8fafc;
            border-radius: 10px;
            border-left: 5px solid #4f46e5;
        }

        .time {
            font-weight: bold;
            color: #555;
        }

        .subject {
            font-weight: bold;
        }

        .type {
            font-size: 13px;
            color: #666;
            margin-top: 4px;
        }

        .complete-btn {
            background: #4f46e5;
            color: white;
        }

        .complete-btn.completed {
            background: #22c55e;
        }

        footer {
            text-align: center;
            padding: 30px;
            color: #666;
        }

        /* DARK MODE */

        body.dark {
            background: #111827;
            color: white;
        }

        body.dark .progress-box,
        body.dark .day {
            background: #1f2937;
        }

        body.dark .session {
            background: #374151;
        }

        body.dark .time,
        body.dark .type {
            color: #d1d5db;
        }

        body.dark .progress-bar {
            background: #4b5563;
        }

        body.dark .dark-btn {
            background: white;
            color: #111;
        }

        @media (max-width: 650px) {

            header h1 {
                font-size: 25px;
            }

            .session {
                grid-template-columns: 1fr;
                gap: 8px;
            }

            .complete-btn {
                width: 100%;
            }
        }
    </style>
</head>

<body>

<header>
    <h1>📚 My Reading Timetable</h1>
    <p>Study smart • Read daily • Grow every day</p>
</header>

<div class="container">

    <div class="top-bar">

        <h2>Weekly Reading Plan</h2>

        <div>
            <button class="dark-btn" onclick="toggleDarkMode()">
                🌙 Dark Mode
            </button>

            <button class="reset-btn" onclick="resetProgress()">
                🔄 Reset
            </button>
        </div>

    </div>

    <!-- PROGRESS -->

    <div class="progress-box">

        <div class="progress-title">
            <span>📊 Weekly Progress</span>
            <span id="progressText">0%</span>
        </div>

        <div class="progress-bar">
            <div class="progress-fill" id="progressFill"></div>
        </div>

    </div>


    <!-- TIMETABLE -->

    <div class="timetable">

        <!-- MONDAY -->

        <div class="day">

            <h2>📅 Monday</h2>

            <div class="session">
                <div class="time">5:00 PM – 5:30 PM</div>

                <div>
                    <div class="subject">📘 Mathematics</div>
                    <div class="type">Read theory & examples</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>
            </div>

            <div class="session">

                <div class="time">7:00 PM – 7:30 PM</div>

                <div>
                    <div class="subject">📖 English</div>
                    <div class="type">Read a story</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

        </div>


        <!-- TUESDAY -->

        <div class="day">

            <h2>📅 Tuesday</h2>

            <div class="session">

                <div class="time">5:00 PM – 5:30 PM</div>

                <div>
                    <div class="subject">🔬 Science</div>
                    <div class="type">Read textbook chapter</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

            <div class="session">

                <div class="time">7:00 PM – 7:30 PM</div>

                <div>
                    <div class="subject">🌍 Social Science</div>
                    <div class="type">Read & make notes</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

        </div>


        <!-- WEDNESDAY -->

        <div class="day">

            <h2>📅 Wednesday</h2>

            <div class="session">

                <div class="time">5:00 PM – 5:30 PM</div>

                <div>
                    <div class="subject">📘 Mathematics</div>
                    <div class="type">Practice problems</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

            <div class="session">

                <div class="time">7:00 PM – 7:30 PM</div>

                <div>
                    <div class="subject">📚 Tamil</div>
                    <div class="type">Read literature</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

        </div>


        <!-- THURSDAY -->

        <div class="day">

            <h2>📅 Thursday</h2>

            <div class="session">

                <div class="time">5:00 PM – 5:30 PM</div>

                <div>
                    <div class="subject">🔬 Science</div>
                    <div class="type">Revision</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

            <div class="session">

                <div class="time">7:00 PM – 7:30 PM</div>

                <div>
                    <div class="subject">📖 English</div>
                    <div class="type">Vocabulary reading</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

        </div>


        <!-- FRIDAY -->

        <div class="day">

            <h2>📅 Friday</h2>

            <div class="session">

                <div class="time">5:00 PM – 5:30 PM</div>

                <div>
                    <div class="subject">🌍 Social Science</div>
                    <div class="type">Read textbook</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

            <div class="session">

                <div class="time">7:00 PM – 7:30 PM</div>

                <div>
                    <div class="subject">📝 Weekly Revision</div>
                    <div class="type">Review everything learned</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

        </div>


        <!-- SATURDAY -->

        <div class="day">

            <h2>📅 Saturday</h2>

            <div class="session">

                <div class="time">10:00 AM – 11:00 AM</div>

                <div>
                    <div class="subject">📕 Story Book</div>
                    <div class="type">Free reading</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

            <div class="session">

                <div class="time">5:00 PM – 6:00 PM</div>

                <div>
                    <div class="subject">🧠 General Knowledge</div>
                    <div class="type">Read & learn new facts</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

        </div>


        <!-- SUNDAY -->

        <div class="day">

            <h2>📅 Sunday</h2>

            <div class="session">

                <div class="time">10:00 AM – 11:00 AM</div>

                <div>
                    <div class="subject">📚 Weekly Reading</div>
                    <div class="type">Read anything you enjoy</div>
                </div>

                <button class="complete-btn"
                    onclick="completeSession(this)">
                    Complete
                </button>

            </div>

        </div>

    </div>

</div>


<footer>
    <p>📚 Keep Reading • Keep Learning • Keep Growing 🚀</p>
</footer>


<script>

    // COMPLETE SESSION

    function completeSession(button) {

        if (button.classList.contains("completed")) {

            button.classList.remove("completed");
            button.innerText = "Complete";

        } else {

            button.classList.add("completed");
            button.innerText = "✓ Done";

        }

        updateProgress();
    }


    // UPDATE PROGRESS

    function updateProgress() {

        const buttons =
            document.querySelectorAll(".complete-btn");

        const completed =
            document.querySelectorAll(".complete-btn.completed");

        const percentage =
            Math.round((completed.length / buttons.length) * 100);

        document.getElementById("progressText")
            .innerText = percentage + "%";

        document.getElementById("progressFill")
            .style.width = percentage + "%";

    }


    // DARK MODE

    function toggleDarkMode() {

        document.body.classList.toggle("dark");

    }


    // RESET

    function resetProgress() {

        const buttons =
            document.querySelectorAll(".complete-btn");

        buttons.forEach(button => {

            button.classList.remove("completed");

            button.innerText = "Complete";

        });

        updateProgress();

    }

</script>

</body>
</html>
