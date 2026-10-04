<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Liliana Quiz ♡</title>
<style>
* {
    box-sizing: border-box;
    -webkit-tap-highlight-color: transparent;
}
html, body {
    margin: 0;
    padding: 0;
    min-height: 100%;
}
body {
    min-height: 100vh;
    font-family: Georgia, "Times New Roman", serif;
    background:
        radial-gradient(
            circle at 20% 0%,
            #ffe8f1 0%,
            #f7bdd2 38%,
            #d77e9f 70%,
            #8d4968 100%
        );
    color: #4a2033;
    padding: 12px;
    overflow-x: hidden;
}
/* ================================
   MAIN PHONE CONTAINER
================================ */
.container {
    width: 100%;
    max-width: 520px;
    margin: 0 auto;
}
/* ================================
   CARD
================================ */
.card {
    width: 100%;
    background: rgba(255, 249, 252, 0.98);
    border-radius: 24px;
    padding: 24px 18px;
    box-shadow:
        0 10px 35px rgba(70, 20, 40, 0.25);
    margin-bottom: 15px;
}
.hidden {
    display: none !important;
}
/* ================================
   START SCREEN
================================ */
.heart {
    text-align: center;
    font-size: 42px;
    margin-bottom: 5px;
}
h1 {
    text-align: center;
    font-size: 31px;
    line-height: 1.15;
    margin: 5px 0 12px;
}
.subtitle {
    text-align: center;
    font-size: 16px;
    line-height: 1.5;
    color: #75445a;
    margin: 0 5px 25px;
}
/* ================================
   NAME INPUT
================================ */
input[type="text"] {
    display: block;
    width: 100%;
    height: 52px;
    padding: 0 15px;
    border: 2px solid #dfa0b9;
    border-radius: 13px;
    background: white;
    color: #4a2033;
    font-size: 16px;
    font-family: Georgia, serif;
    outline: none;
    -webkit-appearance: none;
    margin-bottom: 12px;
}
input[type="text"]:focus {
    border-color: #b85880;
}
/* ================================
   BUTTONS
================================ */
button {
    width: 100%;
    min-height: 52px;
    border: none;
    border-radius: 13px;
    background: #b85880;
    color: white;
    font-size: 17px;
    font-family: Georgia, serif;
    font-weight: bold;
    padding: 13px 18px;
    cursor: pointer;
    touch-action: manipulation;
    transition: transform 0.15s,
                background 0.15s;
}
button:active {
    transform: scale(0.98);
    background: #963c64;
}
/* ================================
   QUESTION HEADER
================================ */
.question-number {
    font-size: 14px;
    font-weight: bold;
    color: #a0476d;
    margin-bottom: 9px;
}
/* ================================
   PROGRESS BAR
================================ */
.progress {
    width: 100%;
    height: 9px;
    background: #f0cedb;
    border-radius: 20px;
    overflow: hidden;
    margin-bottom: 23px;
}
.progress-bar {
    height: 100%;
    width: 0%;
    background: #b85880;
    border-radius: 20px;
    transition: width 0.25s ease;
}
/* ================================
   QUESTION
================================ */
.question {
    font-size: 21px;
    font-weight: bold;
    line-height: 1.35;
    margin-bottom: 18px;
}
/* ================================
   ANSWER OPTIONS
================================ */
.option {
    display: flex;
    align-items: center;
    width: 100%;
    min-height: 55px;
    padding: 12px 13px;
    margin: 9px 0;
    border-radius: 13px;
    border: 2px solid #edb4c9;
    background: #ffe9f1;
    font-size: 16px;
    line-height: 1.3;
    cursor: pointer;
    touch-action: manipulation;
    transition:
        background 0.15s,
        border 0.15s,
        transform 0.1s;
}
.option:active {
    transform: scale(0.985);
}
.option.selected {
    background: #f2b8ce;
    border-color: #b85880;
}
.option input {
    flex: 0 0 auto;
    width: 19px;
    height: 19px;
    margin: 0 11px 0 0;
    accent-color: #b85880;
}
/* ================================
   NEXT BUTTON
================================ */
#nextButton {
    margin-top: 8px;
}
/* ================================
   RESULTS
================================ */
.result {
    text-align: center;
}
.result h1 {
    margin-bottom: 5px;
}
#resultName {
    font-size: 17px;
    margin-bottom: 5px;
}
.score {
    font-size: 58px;
    font-weight: bold;
    color: #a33f68;
    line-height: 1;
    margin: 18px 0 8px;
}
.percentage {
    font-size: 22px;
    font-weight: bold;
    color: #75445a;
}
.message {
    font-size: 17px;
    line-height: 1.45;
    margin: 18px 0 24px;
}
/* ================================
   LEADERBOARD
================================ */
.leaderboard {
    margin-top: 30px;
    border-top: 1px solid #edc1d1;
    padding-top: 22px;
}
.leaderboard h2 {
    font-size: 24px;
    margin: 0 0 15px;
}
.leaderboard-entry {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
    width: 100%;
    min-height: 50px;
    padding: 11px 12px;
    margin: 7px 0;
    border-radius: 12px;
    background: #ffe6ef;
    font-size: 15px;
    text-align: left;
}
.leaderboard-entry span {
    min-width: 0;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
}
.leaderboard-entry strong {
    flex-shrink: 0;
    font-size: 14px;
}
.gold {
    background: #ffe6b5;
}
.silver {
    background: #eeeeee;
}
.bronze {
    background: #f3d0b4;
}
.rank {
    font-weight: bold;
    margin-right: 5px;
}
.empty {
    text-align: center;
    color: #80556a;
}
.small-note {
    text-align: center;
    font-size: 12px;
    line-height: 1.4;
    color: #896274;
    margin-top: 15px;
}
/* ================================
   VERY SMALL PHONES
================================ */
@media (max-width: 360px) {
    body {
        padding: 8px;
    }
    .card {
        padding: 20px 14px;
        border-radius: 20px;
    }
    h1 {
        font-size: 27px;
    }
    .question {
        font-size: 19px;
    }
    .option {
        font-size: 15px;
        min-height: 52px;
        padding: 11px;
    }
    .score {
        font-size: 52px;
    }
}
/* ================================
   TALL PHONES
================================ */
@media (min-height: 800px) and (max-width: 600px) {
    .card {
        padding-top: 28px;
        padding-bottom: 28px;
    }
}
</style>
</head>
<body>
<div class="container">
<!-- =================================
     START SCREEN
================================= -->
<div class="card" id="startScreen">
    <div class="heart">
        ♡
    </div>
    <h1>
        How Well Do You Know Liliana?
    </h1>
    <p class="subtitle">
        50 questions about Liliana.
        <br>
        Let's see who knows her best. 💗
    </p>
    <input
        type="text"
        id="playerName"
        placeholder="Enter your name"
        maxlength="30"
        autocomplete="off"
    >
    <button onclick="startQuiz()">
        Start Quiz ♡
    </button>
</div>
<!-- =================================
     QUIZ SCREEN
================================= -->
<div
    class="card hidden"
    id="quizScreen"
>
    <div
        class="question-number"
        id="questionNumber"
    ></div>
    <div class="progress">
        <div
            class="progress-bar"
            id="progressBar"
        ></div>
    </div>
    <div
        class="question"
        id="question"
    ></div>
    <div id="options"></div>
    <button
        id="nextButton"
        onclick="nextQuestion()"
    >
        Next Question →
    </button>
</div>
<!-- =================================
     RESULT SCREEN
================================= -->
<div
    class="card hidden result"
    id="resultScreen"
>
    <div class="heart">
        ♡
    </div>
    <h1>
        Quiz Complete!
    </h1>
    <p id="resultName"></p>
    <div
        class="score"
        id="score"
    ></div>
    <div
        class="percentage"
        id="percentage"
    ></div>
    <div
        class="message"
        id="resultMessage"
    ></div>
    <button onclick="restartQuiz()">
        Take Quiz Again
    </button>
    <div class="leaderboard">
        <h2>
            🏆 Liliana Leaderboard
        </h2>
        <div id="leaderboard"></div>
        <p class="small-note">
            Scores are saved on this device.
        </p>
    </div>
</div>
</div>
<script>
/* ==========================================
   QUESTIONS
========================================== */
const questions = [
{
q:"What is Liliana’s birthday?",
options:["July 12th","July 22nd","June 22nd","August 22nd"],
answer:"July 22nd"
},
{
q:"What is Liliana’s favourite colour?",
options:["Pink","Baby pink","Rose pink","Baby blue"],
answer:"Baby pink"
},
{
q:"What is Liliana’s favourite number?",
options:["7","13","3","8"],
answer:"3"
},
{
q:"What is Liliana’s favourite food?",
options:["Ramen","Sushi","Seafood","Pasta"],
answer:"Sushi"
},
{
q:"What is Liliana’s favourite drink?",
options:["Lemonade","Sparkling water","Lemon water","Iced tea"],
answer:"Lemon water"
},
{
q:"What is Liliana’s favourite dessert?",
options:["Strawberry cheesecake","Strawberry shortcake","New York cheesecake","Chocolate cheesecake"],
answer:"Strawberry cheesecake"
},
{
q:"What are Liliana’s favourite flowers?",
options:["Roses and tulips","Sunflowers and lilies","Roses and sunflowers","Daisies and roses"],
answer:"Roses and sunflowers"
},
{
q:"What is Liliana’s favourite animal?",
options:["Dolphins","Whales","Seals","Sharks"],
answer:"Dolphins"
},
{
q:"What is Liliana’s favourite movie?",
options:["The Notebook","Me Before You","Five Feet Apart","The Fault in Our Stars"],
answer:"Me Before You"
},
{
q:"What is Liliana’s favourite song?",
options:["Before It Sinks In","Before It Ends","Let It Sink In","Before We Fall"],
answer:"Before It Sinks In"
},
{
q:"What is Liliana’s favourite music genre?",
options:["Soul","R&B","Pop","Hip-hop"],
answer:"R&B"
},
{
q:"What is Liliana’s favourite season?",
options:["Winter","Spring","Autumn","Summer"],
answer:"Autumn"
},
{
q:"What is Liliana’s favourite holiday?",
options:["Halloween","Christmas","Thanksgiving","New Year’s"],
answer:"Christmas"
},
{
q:"What is Liliana’s favourite place?",
options:["The beach","Her childhood home","Mum’s house","Her favourite restaurant"],
answer:"Mum’s house"
},
{
q:"What is Liliana’s favourite hobby?",
options:["Playing cards","Watching movies","Gambling","Reading"],
answer:"Gambling"
},
{
q:"What is Liliana’s favourite thing to do in her free time?",
options:["Go shopping","Go to concerts","Watch films","Go out to eat"],
answer:"Go to concerts"
},
{
q:"What is Liliana’s favourite type of weather?",
options:["Sunny and warm","Rain and snow","Windy and cloudy","Cold and sunny"],
answer:"Rain and snow"
},
{
q:"What is Liliana’s favourite catchphrase?",
options:["No way","That’s crazy","That’s wild","Are you serious?"],
answer:"That’s crazy"
},
{
q:"What is Liliana’s preference in women?",
options:["Femme","Stem","Masc","Butch"],
answer:"Stem"
},
{
q:"What is Liliana’s favourite social media platform?",
options:["Instagram","TikTok","Twitter","Snapchat"],
answer:"Twitter"
},
{
q:"What is Liliana’s zodiac sign?",
options:["Cancer","Leo","Virgo","Gemini"],
answer:"Leo"
},
{
q:"What colour are Liliana’s eyes?",
options:["Hazel","Blue","Green","Grey"],
answer:"Green"
},
{
q:"How many siblings does Liliana have?",
options:["4","5","6","3"],
answer:"5"
},
{
q:"How many nieces does Liliana have?",
options:["2","3","1","0"],
answer:"1"
},
{
q:"How many nephews does Liliana have?",
options:["1","2","3","4"],
answer:"2"
},
{
q:"How many dogs does Liliana have?",
options:["1","2","3","4"],
answer:"2"
},
{
q:"What are Liliana’s dogs’ names?",
options:["Arlo & Aayla","Arlo & Ava","Aayla & Aria","Archie & Aayla"],
answer:"Arlo & Aayla"
},
{
q:"How many tattoos does Liliana have?",
options:["None","1","2","3"],
answer:"1"
},
{
q:"How many piercings does Liliana have?",
options:["2","3","4","5"],
answer:"4"
},
{
q:"What did Liliana study at university?",
options:["Sociology","Psychology","Criminology","Social Work"],
answer:"Psychology"
},
{
q:"What is Liliana’s biggest fear?",
options:["Being alone","Losing the people she loves","Losing her family home","Being forgotten"],
answer:"Losing the people she loves"
},
{
q:"What is Liliana’s biggest dream?",
options:["To travel the world","To create a foundation she never had","To become a psychologist","To own her own business"],
answer:"To create a foundation she never had"
},
{
q:"What is Liliana’s biggest goal in life?",
options:["To travel and see the world","To get married and have a family","To become financially independent","To have a successful career"],
answer:"To get married and have a family"
},
{
q:"What is something Liliana really wants to experience?",
options:["A long-distance relationship","A Filipina","Falling in love","Living overseas"],
answer:"A Filipina"
},
{
q:"What does Liliana absolutely hate?",
options:["Being ignored","Being lied to","Being interrupted","Being criticised"],
answer:"Being interrupted"
},
{
q:"What instantly makes Liliana happy?",
options:["Friends","Music","Family","Food"],
answer:"Family"
},
{
q:"What instantly makes Liliana angry?",
options:["Cheaters","Rude people","Liars","Spam callers"],
answer:"Liars"
},
{
q:"What always makes Liliana laugh?",
options:["Sarcasm","Dark humour","Dad jokes","Slapstick humour"],
answer:"Dark humour"
},
{
q:"What does Liliana do when she is bored?",
options:["Scroll through Twitter","Watch Netflix","Go on HelloTalk","Play games"],
answer:"Go on HelloTalk"
},
{
q:"What does Liliana do when she is sad?",
options:["Sleep","Talk to someone","Listen to sad music and cry","Go for a walk"],
answer:"Listen to sad music and cry"
},
{
q:"What is Liliana’s best personality trait?",
options:["Kindness","Loyalty","Honesty","Confidence"],
answer:"Honesty"
},
{
q:"What is Liliana’s worst habit?",
options:["Staying up too late","Smoking","Overthinking","Procrastinating"],
answer:"Smoking"
},
{
q:"What is Liliana’s biggest pet peeve?",
options:["Telemarketers","Spam callers","People talking loudly","Being interrupted"],
answer:"Spam callers"
},
{
q:"What is Liliana really good at?",
options:["Making people laugh","Giving advice","Keeping secrets","Reading people"],
answer:"Giving advice"
},
{
q:"What is Liliana terrible at?",
options:["Asking for help","Giving advice","Taking advice","Admitting when she is wrong"],
answer:"Taking advice"
},
{
q:"What is Liliana afraid to try?",
options:["Marriage","Moving overseas","Long-distance relationship","Dating apps"],
answer:"Long-distance relationship"
},
{
q:"What could Liliana never live without?",
options:["Music","Her dogs","Family","Her phone"],
answer:"Family"
},
{
q:"What is Liliana particularly sentimental about?",
options:["Photographs","Jewellery","Birthday cards","Love letters"],
answer:"Birthday cards"
},
{
q:"What is one thing Liliana wants to accomplish before she dies?",
options:["Travel the world","Buy herself a house","Buy her mum a house","Start her own business"],
answer:"Buy her mum a house"
},
{
q:"Does Liliana like tits or ass?",
options:["Ass","Both","Tits","Neither"],
answer:"Tits"
}
];
/* ==========================================
   VARIABLES
========================================== */
let currentQuestion = 0;
let score = 0;
let player = "";
let quizQuestions = [];
/* ==========================================
   SHUFFLE
========================================== */
function shuffle(array) {
    const result = [...array];
    for (
        let i = result.length - 1;
        i > 0;
        i--
    ) {
        const j =
            Math.floor(
                Math.random() * (i + 1)
            );
        [
            result[i],
            result[j]
        ] =
        [
            result[j],
            result[i]
        ];
    }
    return result;
}
/* ==========================================
   START
========================================== */
function startQuiz() {
    player =
        document
        .getElementById("playerName")
        .value
        .trim();
    if (!player) {
        alert(
            "Please enter your name first ♡"
        );
        return;
    }
    currentQuestion = 0;
    score = 0;
    /*
       Shuffle the answer choices
       independently for every quiz.
    */
    quizQuestions =
        questions.map(question => ({
            q: question.q,
            answer: question.answer,
            options:
                shuffle(question.options)
        }));
    document
        .getElementById("startScreen")
        .classList
        .add("hidden");
    document
        .getElementById("quizScreen")
        .classList
        .remove("hidden");
    window.scrollTo({
        top: 0,
        behavior: "instant"
    });
    showQuestion();
}
/* ==========================================
   DISPLAY QUESTION
========================================== */
function showQuestion() {
    const question =
        quizQuestions[currentQuestion];
    document
        .getElementById("questionNumber")
        .textContent =
        `Question ${currentQuestion + 1} of 50`;
    document
        .getElementById("question")
        .textContent =
        question.q;
    const container =
        document.getElementById("options");
    container.innerHTML = "";
    question.options.forEach(
        (option, index) => {
            const label =
                document.createElement("label");
            label.className = "option";
            label.innerHTML = `
                <input
                    type="radio"
                    name="answer"
                    value="${escapeHTML(option)}"
                >
                <span>
                    ${String.fromCharCode(65 + index)}.
                    ${escapeHTML(option)}
                </span>
            `;
            label.addEventListener(
                "click",
                function() {
                    document
                        .querySelectorAll(".option")
                        .forEach(
                            item =>
                            item.classList.remove(
                                "selected"
                            )
                        );
                    label.classList.add(
                        "selected"
                    );
                }
            );
            container.appendChild(label);
        }
    );
    document
        .getElementById("progressBar")
        .style.width =
        `${(currentQuestion / 50) * 100}%`;
    document
        .getElementById("nextButton")
        .textContent =
        currentQuestion === 49
        ? "Finish Quiz ♡"
        : "Next Question →";
    window.scrollTo({
        top: 0,
        behavior: "instant"
    });
}
/* ==========================================
   SECURITY / HTML ESCAPE
========================================== */
function escapeHTML(text) {
    const div =
        document.createElement("div");
    div.textContent = text;
    return div.innerHTML;
}
/* ==========================================
   NEXT
========================================== */
function nextQuestion() {
    const selected =
        document.querySelector(
            'input[name="answer"]:checked'
        );
    if (!selected) {
        alert(
            "Please choose an answer first ♡"
        );
        return;
    }
    if (
        selected.value ===
        quizQuestions[currentQuestion].answer
    ) {
        score++;
    }
    currentQuestion++;
    if (currentQuestion < 50) {
        showQuestion();
    } else {
        finishQuiz();
    }
}
/* ==========================================
   FINISH
========================================== */
function finishQuiz() {
    document
        .getElementById("quizScreen")
        .classList
        .add("hidden");
    document
        .getElementById("resultScreen")
        .classList
        .remove("hidden");
    window.scrollTo({
        top: 0,
        behavior: "instant"
    });
    const percentage =
        Math.round(
            (score / 50) * 100
        );
    document
        .getElementById("resultName")
        .textContent =
        `${player}, your final score is:`;
    document
        .getElementById("score")
        .textContent =
        `${score} / 50`;
    document
        .getElementById("percentage")
        .textContent =
        `${percentage}%`;
    let message;
    if (score === 50) {
        message =
        "🏆 PERFECT SCORE! You know Liliana better than anyone!";
    }
    else if (score >= 45) {
        message =
        "💗 Incredible! You know Liliana extremely well!";
    }
    else if (score >= 40) {
        message =
        "🌸 You know Liliana REALLY well!";
    }
    else if (score >= 35) {
        message =
        "💕 Very impressive! You definitely know your Liliana facts.";
    }
    else if (score >= 25) {
        message =
        "😏 Not bad! But there are still some Liliana facts to learn.";
    }
    else if (score >= 15) {
        message =
        "😂 You might need to study Liliana a little more!";
    }
    else {
        message =
        "😭 Liliana is going to be disappointed in you!";
    }
    document
        .getElementById("resultMessage")
        .textContent =
        message;
    saveScore();
    displayLeaderboard();
}
/* ==========================================
   SAVE SCORE
========================================== */
function saveScore() {
    let leaderboard =
        JSON.parse(
            localStorage.getItem(
                "lilianaLeaderboard"
            )
        ) || [];
    leaderboard.push({
        name: player,
        score: score,
        percentage:
            Math.round(
                (score / 50) * 100
            ),
        date:
            new Date().toLocaleDateString()
    });
    leaderboard.sort(
        (a, b) =>
        b.score - a.score
    );
    /*
       Keep the top 20 scores.
    */
    leaderboard =
        leaderboard.slice(0, 20);
    localStorage.setItem(
        "lilianaLeaderboard",
        JSON.stringify(leaderboard)
    );
}
/* ==========================================
   LEADERBOARD
========================================== */
function displayLeaderboard() {
    const leaderboard =
        JSON.parse(
            localStorage.getItem(
                "lilianaLeaderboard"
            )
        ) || [];
    const container =
        document.getElementById(
            "leaderboard"
        );
    container.innerHTML = "";
    if (!leaderboard.length) {
        container.innerHTML =
        `<p class="empty">
            No scores yet.
        </p>`;
        return;
    }
    leaderboard.forEach(
        (entry, index) => {
            const div =
                document.createElement("div");
            div.className =
                "leaderboard-entry";
            if (index === 0) {
                div.classList.add("gold");
            }
            else if (index === 1) {
                div.classList.add("silver");
            }
            else if (index === 2) {
                div.classList.add("bronze");
            }
            let medal = "";
            if (index === 0) {
                medal = "🥇";
            }
            else if (index === 1) {
                medal = "🥈";
            }
            else if (index === 2) {
                medal = "🥉";
            }
            div.innerHTML = `
                <span>
                    <span class="rank">
                        ${medal}
                        ${index + 1}.
                    </span>
                    ${escapeHTML(entry.name)}
                </span>
                <strong>
                    ${entry.score}/50
                </strong>
            `;
            container.appendChild(div);
        }
    );
}
/* ==========================================
   RESTART
========================================== */
function restartQuiz() {
    document
        .getElementById("resultScreen")
        .classList
        .add("hidden");
    document
        .getElementById("startScreen")
        .classList
        .remove("hidden");
    document
        .getElementById("playerName")
        .value = "";
    currentQuestion = 0;
    score = 0;
    window.scrollTo({
        top: 0,
        behavior: "instant"
    });
}
/* ==========================================
   LOAD LEADERBOARD
========================================== */
window.addEventListener(
    "load",
    displayLeaderboard
);
</script>
</body>
</html>
