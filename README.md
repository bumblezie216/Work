<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>How Well Do You Know Liliana?</title>
<style>
* {
    box-sizing: border-box;
}
body {
    margin: 0;
    min-height: 100vh;
    padding: 20px;
    font-family: Georgia, serif;
    background:
        radial-gradient(
            circle at top,
            #ffd8e8 0%,
            #f2a9c6 40%,
            #9b5875 100%
        );
    color: #4b2034;
}
.container {
    max-width: 850px;
    margin: auto;
}
.card {
    background: rgba(255, 247, 251, 0.97);
    border-radius: 28px;
    padding: 35px;
    margin-bottom: 25px;
    box-shadow:
        0 18px 50px rgba(80, 20, 45, 0.28);
}
.hidden {
    display: none;
}
.heart {
    text-align: center;
    font-size: 38px;
}
h1 {
    text-align: center;
    font-size: 42px;
    margin: 10px 0;
}
h2 {
    text-align: center;
}
.subtitle {
    text-align: center;
    font-size: 18px;
    color: #75445a;
    margin-bottom: 30px;
}
input[type="text"] {
    width: 100%;
    padding: 16px;
    border: 2px solid #dfa0b9;
    border-radius: 14px;
    font-size: 17px;
    margin-bottom: 15px;
    outline: none;
}
button {
    border: none;
    background: #b85880;
    color: white;
    padding: 15px 25px;
    border-radius: 14px;
    font-size: 17px;
    font-family: Georgia, serif;
    cursor: pointer;
    transition: 0.2s;
}
button:hover {
    background: #963c64;
    transform: translateY(-2px);
}
#nextButton {
    margin-top: 15px;
}
.question-number {
    color: #a0476d;
    font-weight: bold;
    margin-bottom: 8px;
}
.question {
    font-size: 26px;
    font-weight: bold;
    line-height: 1.4;
    margin-bottom: 22px;
}
.progress {
    height: 12px;
    background: #f1c7d7;
    border-radius: 20px;
    overflow: hidden;
    margin-bottom: 28px;
}
.progress-bar {
    height: 100%;
    width: 0%;
    background: #b85880;
    transition: width 0.3s ease;
}
.option {
    display: block;
    background: #ffe7f0;
    border: 2px solid #edb4c9;
    padding: 15px;
    margin: 11px 0;
    border-radius: 14px;
    cursor: pointer;
    transition: 0.2s;
}
.option:hover {
    background: #f8cada;
}
.option.selected {
    background: #eeb0c7;
    border-color: #b85880;
}
.option input {
    margin-right: 10px;
}
.result {
    text-align: center;
}
.score {
    font-size: 65px;
    font-weight: bold;
    color: #a33f68;
    margin: 20px 0;
}
.percentage {
    font-size: 24px;
}
.message {
    font-size: 21px;
    margin: 20px 0 30px;
}
.leaderboard {
    margin-top: 35px;
}
.leaderboard-entry {
    display: flex;
    justify-content: space-between;
    align-items: center;
    background: #ffe5ef;
    padding: 15px 18px;
    margin: 9px 0;
    border-radius: 14px;
    font-size: 17px;
}
.rank {
    font-weight: bold;
    margin-right: 8px;
}
.gold {
    background: #ffe5b5;
}
.silver {
    background: #eeeeee;
}
.bronze {
    background: #f3d0b4;
}
.empty {
    text-align: center;
    color: #80556a;
}
.small-note {
    text-align: center;
    font-size: 13px;
    color: #896274;
    margin-top: 20px;
}
@media (max-width: 600px) {
    body {
        padding: 12px;
    }
    .card {
        padding: 22px;
        border-radius: 22px;
    }
    h1 {
        font-size: 32px;
    }
    .question {
        font-size: 21px;
    }
    .score {
        font-size: 52px;
    }
}
</style>
</head>
<body>
<div class="container">
<!-- =========================
     START SCREEN
========================= -->
<div class="card" id="startScreen">
    <div class="heart">♡</div>
    <h1>How Well Do You Know Liliana?</h1>
    <p class="subtitle">
        50 questions. 4 possible answers.
        Only one is correct.
        <br>
        Let's see who knows Liliana best.
    </p>
    <input
        type="text"
        id="playerName"
        placeholder="Enter your name"
        maxlength="30"
    >
    <button
        onclick="startQuiz()"
        style="width:100%;"
    >
        Start Quiz ♡
    </button>
</div>
<!-- =========================
     QUIZ SCREEN
========================= -->
<div class="card hidden" id="quizScreen">
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
        onclick="nextQuestion()"
        id="nextButton"
    >
        Next Question →
    </button>
</div>
<!-- =========================
     RESULT SCREEN
========================= -->
<div class="card hidden result" id="resultScreen">
    <div class="heart">♡</div>
    <h1>Quiz Complete!</h1>
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
        <h2>🏆 Liliana Leaderboard</h2>
        <div id="leaderboard"></div>
        <p class="small-note">
            Scores are saved in this browser.
        </p>
    </div>
</div>
</div>
<script>
/* ==========================================
   LILIANA QUESTIONS
========================================== */
const questions = [
{
q: "What is Liliana’s birthday?",
options: [
"July 12th",
"July 22nd",
"June 22nd",
"August 22nd"
],
answer: "July 22nd"
},
{
q: "What is Liliana’s favourite colour?",
options: [
"Pink",
"Baby pink",
"Rose pink",
"Baby blue"
],
answer: "Baby pink"
},
{
q: "What is Liliana’s favourite number?",
options: [
"7",
"13",
"3",
"8"
],
answer: "3"
},
{
q: "What is Liliana’s favourite food?",
options: [
"Ramen",
"Sushi",
"Seafood",
"Pasta"
],
answer: "Sushi"
},
{
q: "What is Liliana’s favourite drink?",
options: [
"Lemonade",
"Sparkling water",
"Lemon water",
"Iced tea"
],
answer: "Lemon water"
},
{
q: "What is Liliana’s favourite dessert?",
options: [
"Strawberry cheesecake",
"Strawberry shortcake",
"New York cheesecake",
"Chocolate cheesecake"
],
answer: "Strawberry cheesecake"
},
{
q: "What are Liliana’s favourite flowers?",
options: [
"Roses and tulips",
"Sunflowers and lilies",
"Roses and sunflowers",
"Daisies and roses"
],
answer: "Roses and sunflowers"
},
{
q: "What is Liliana’s favourite animal?",
options: [
"Dolphins",
"Whales",
"Seals",
"Sharks"
],
answer: "Dolphins"
},
{
q: "What is Liliana’s favourite movie?",
options: [
"The Notebook",
"Me Before You",
"Five Feet Apart",
"The Fault in Our Stars"
],
answer: "Me Before You"
},
{
q: "What is Liliana’s favourite song?",
options: [
"Before It Sinks In",
"Before It Ends",
"Let It Sink In",
"Before We Fall"
],
answer: "Before It Sinks In"
},
{
q: "What is Liliana’s favourite music genre?",
options: [
"Soul",
"R&B",
"Pop",
"Hip-hop"
],
answer: "R&B"
},
{
q: "What is Liliana’s favourite season?",
options: [
"Winter",
"Spring",
"Autumn",
"Summer"
],
answer: "Autumn"
},
{
q: "What is Liliana’s favourite holiday?",
options: [
"Halloween",
"Christmas",
"Thanksgiving",
"New Year’s"
],
answer: "Christmas"
},
{
q: "What is Liliana’s favourite place?",
options: [
"The beach",
"Her childhood home",
"Mum’s house",
"Her favourite restaurant"
],
answer: "Mum’s house"
},
{
q: "What is Liliana’s favourite hobby?",
options: [
"Playing cards",
"Watching movies",
"Gambling",
"Reading"
],
answer: "Gambling"
},
{
q: "What is Liliana’s favourite thing to do in her free time?",
options: [
"Go shopping",
"Go to concerts",
"Watch films",
"Go out to eat"
],
answer: "Go to concerts"
},
{
q: "What is Liliana’s favourite type of weather?",
options: [
"Sunny and warm",
"Rain and snow",
"Windy and cloudy",
"Cold and sunny"
],
answer: "Rain and snow"
},
{
q: "What is Liliana’s favourite catchphrase?",
options: [
"No way",
"That’s crazy",
"That’s wild",
"Are you serious?"
],
answer: "That’s crazy"
},
{
q: "What is Liliana’s preference in women?",
options: [
"Femme",
"Stem",
"Masc",
"Butch"
],
answer: "Stem"
},
{
q: "What is Liliana’s favourite social media platform?",
options: [
"Instagram",
"TikTok",
"Twitter",
"Snapchat"
],
answer: "Twitter"
},
{
q: "What is Liliana’s zodiac sign?",
options: [
"Cancer",
"Leo",
"Virgo",
"Gemini"
],
answer: "Leo"
},
{
q: "What colour are Liliana’s eyes?",
options: [
"Hazel",
"Blue",
"Green",
"Grey"
],
answer: "Green"
},
{
q: "How many siblings does Liliana have?",
options: [
"4",
"5",
"6",
"3"
],
answer: "5"
},
{
q: "How many nieces does Liliana have?",
options: [
"2",
"3",
"1",
"0"
],
answer: "1"
},
{
q: "How many nephews does Liliana have?",
options: [
"1",
"2",
"3",
"4"
],
answer: "2"
},
{
q: "How many dogs does Liliana have?",
options: [
"1",
"2",
"3",
"4"
],
answer: "2"
},
{
q: "What are Liliana’s dogs’ names?",
options: [
"Arlo & Aayla",
"Arlo & Ava",
"Aayla & Aria",
"Archie & Aayla"
],
answer: "Arlo & Aayla"
},
{
q: "How many tattoos does Liliana have?",
options: [
"None",
"1",
"2",
"3"
],
answer: "1"
},
{
q: "How many piercings does Liliana have?",
options: [
"2",
"3",
"4",
"5"
],
answer: "4"
},
{
q: "What did Liliana study at university?",
options: [
"Sociology",
"Psychology",
"Criminology",
"Social Work"
],
answer: "Psychology"
},
{
q: "What is Liliana’s biggest fear?",
options: [
"Being alone",
"Losing the people she loves",
"Losing her family home",
"Being forgotten"
],
answer: "Losing the people she loves"
},
{
q: "What is Liliana’s biggest dream?",
options: [
"To travel the world",
"To create a foundation she never had",
"To become a psychologist",
"To own her own business"
],
answer: "To create a foundation she never had"
},
{
q: "What is Liliana’s biggest goal in life?",
options: [
"To travel and see the world",
"To get married and have a family",
"To become financially independent",
"To have a successful career"
],
answer: "To get married and have a family"
},
{
q: "What is something Liliana really wants to experience?",
options: [
"A long-distance relationship",
"A Filipina",
"Falling in love",
"Living overseas"
],
answer: "A Filipina"
},
{
q: "What does Liliana absolutely hate?",
options: [
"Being ignored",
"Being lied to",
"Being interrupted",
"Being criticised"
],
answer: "Being interrupted"
},
{
q: "What instantly makes Liliana happy?",
options: [
"Friends",
"Music",
"Family",
"Food"
],
answer: "Family"
},
{
q: "What instantly makes Liliana angry?",
options: [
"Cheaters",
"Rude people",
"Liars",
"Spam callers"
],
answer: "Liars"
},
{
q: "What always makes Liliana laugh?",
options: [
"Sarcasm",
"Dark humour",
"Dad jokes",
"Slapstick humour"
],
answer: "Dark humour"
},
{
q: "What does Liliana do when she is bored?",
options: [
"Scroll through Twitter",
"Watch Netflix",
"Go on HelloTalk",
"Play games"
],
answer: "Go on HelloTalk"
},
{
q: "What does Liliana do when she is sad?",
options: [
"Sleep",
"Talk to someone",
"Listen to sad music and cry",
"Go for a walk"
],
answer: "Listen to sad music and cry"
},
{
q: "What is Liliana’s best personality trait?",
options: [
"Kindness",
"Loyalty",
"Honesty",
"Confidence"
],
answer: "Honesty"
},
{
q: "What is Liliana’s worst habit?",
options: [
"Staying up too late",
"Smoking",
"Overthinking",
"Procrastinating"
],
answer: "Smoking"
},
{
q: "What is Liliana’s biggest pet peeve?",
options: [
"Telemarketers",
"Spam callers",
"People talking loudly",
"Being interrupted"
],
answer: "Spam callers"
},
{
q: "What is Liliana really good at?",
options: [
"Making people laugh",
"Giving advice",
"Keeping secrets",
"Reading people"
],
answer: "Giving advice"
},
{
q: "What is Liliana terrible at?",
options: [
"Asking for help",
"Giving advice",
"Taking advice",
"Admitting when she is wrong"
],
answer: "Taking advice"
},
{
q: "What is Liliana afraid to try?",
options: [
"Marriage",
"Moving overseas",
"Long-distance relationship",
"Dating apps"
],
answer: "Long-distance relationship"
},
{
q: "What could Liliana never live without?",
options: [
"Music",
"Her dogs",
"Family",
"Her phone"
],
answer: "Family"
},
{
q: "What is Liliana particularly sentimental about?",
options: [
"Photographs",
"Jewellery",
"Birthday cards",
"Love letters"
],
answer: "Birthday cards"
},
{
q: "What is one thing Liliana wants to accomplish before she dies?",
options: [
"Travel the world",
"Buy herself a house",
"Buy her mum a house",
"Start her own business"
],
answer: "Buy her mum a house"
},
{
q: "Does Liliana like tits or ass?",
options: [
"Ass",
"Both",
"Tits",
"Neither"
],
answer: "Tits"
}
];
/* ==========================================
   QUIZ VARIABLES
========================================== */
let currentQuestion = 0;
let score = 0;
let player = "";
let quizQuestions = [];
/* ==========================================
   SHUFFLE FUNCTION
========================================== */
function shuffle(array) {
    const shuffled = [...array];
    for (
        let i = shuffled.length - 1;
        i > 0;
        i--
    ) {
        const j =
            Math.floor(Math.random() * (i + 1));
        [
            shuffled[i],
            shuffled[j]
        ] =
        [
            shuffled[j],
            shuffled[i]
        ];
    }
    return shuffled;
}
/* ==========================================
   START QUIZ
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
       Create a fresh copy of the questions.
       The QUESTIONS themselves stay in the
       same order, but their ANSWER CHOICES
       are shuffled.
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
    showQuestion();
}
/* ==========================================
   SHOW QUESTION
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
    const optionsContainer =
        document.getElementById("options");
    optionsContainer.innerHTML = "";
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
                ${String.fromCharCode(65 + index)}.
                ${escapeHTML(option)}
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
            optionsContainer.appendChild(label);
        }
    );
    const progress =
        (currentQuestion / 50) * 100;
    document
        .getElementById("progressBar")
        .style.width =
        progress + "%";
    document
        .getElementById("nextButton")
        .textContent =
        currentQuestion === 49
        ? "Finish Quiz ♡"
        : "Next Question →";
}
/* ==========================================
   ESCAPE HTML
========================================== */
function escapeHTML(text) {
    const div =
        document.createElement("div");
    div.textContent = text;
    return div.innerHTML;
}
/* ==========================================
   NEXT QUESTION
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
   FINISH QUIZ
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
    const percent =
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
        `${percent}%`;
    let message;
    if (score === 50) {
        message =
        "🏆 PERFECT SCORE! You know Liliana better than anyone!";
    } else if (score >= 45) {
        message =
        "💗 Incredible! You know Liliana extremely well!";
    } else if (score >= 40) {
        message =
        "🌸 You know Liliana REALLY well!";
    } else if (score >= 35) {
        message =
        "💕 Very impressive! You definitely know your Liliana facts.";
    } else if (score >= 25) {
        message =
        "😏 Not bad! But there are still some Liliana facts to learn.";
    } else if (score >= 15) {
        message =
        "😂 You might need to spend a little more time studying Liliana!";
    } else {
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
        (a, b) => {
            if (b.score !== a.score) {
                return b.score - a.score;
            }
            return a.name.localeCompare(
                b.name
            );
        }
    );
    /*
       Keep the best 20 scores.
    */
    leaderboard =
        leaderboard.slice(0, 20);
    localStorage.setItem(
        "lilianaLeaderboard",
        JSON.stringify(leaderboard)
    );
}
/* ==========================================
   DISPLAY LEADERBOARD
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
    if (leaderboard.length === 0) {
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
            } else if (index === 1) {
                div.classList.add("silver");
            } else if (index === 2) {
                div.classList.add("bronze");
            }
            let medal = "";
            if (index === 0) {
                medal = "🥇";
            } else if (index === 1) {
                medal = "🥈";
            } else if (index === 2) {
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
                    (${entry.percentage}%)
                </strong>
            `;
            container.appendChild(div);
        }
    );
}
/* ==========================================
   RESTART QUIZ
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
}
/* ==========================================
   LOAD LEADERBOARD ON PAGE LOAD
========================================== */
window.onload = function() {
    displayLeaderboard();
};
</script>
</body>
</html>
