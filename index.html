<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>감수분열 퀴즈</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: Arial, "Noto Sans KR", sans-serif;
  background: linear-gradient(135deg, #dbeafe, #ede9fe);
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  color: #222;
}

.container {
  width: 95%;
  max-width: 720px;
  background: white;
  border-radius: 25px;
  padding: 30px;
  box-shadow: 0 10px 35px rgba(0,0,0,0.15);
}

.screen {
  display: none;
}

.screen.active {
  display: block;
}

h1 {
  text-align: center;
}

input {
  width: 100%;
  padding: 15px;
  margin: 10px 0;
  font-size: 18px;
  border: 2px solid #ddd;
  border-radius: 12px;
}

button {
  width: 100%;
  padding: 15px;
  margin-top: 10px;
  border: none;
  border-radius: 12px;
  background: #6366f1;
  color: white;
  font-size: 18px;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background: #4f46e5;
}

.info {
  display: flex;
  justify-content: space-between;
  background: #f3f4f6;
  padding: 12px;
  border-radius: 12px;
  margin-bottom: 20px;
  font-weight: bold;
  gap: 8px;
}

#timer {
  color: #ef4444;
}

#scoreDisplay {
  color: #6366f1;
}

.question-number {
  color: #6366f1;
  font-weight: bold;
  margin-bottom: 10px;
}

.question {
  font-size: 21px;
  line-height: 1.8;
  font-weight: bold;
  margin-bottom: 20px;
}

.answer-input {
  margin-bottom: 10px;
}

.result-score {
  text-align: center;
  font-size: 42px;
  font-weight: bold;
  color: #6366f1;
  margin: 20px 0;
}

.result-info {
  background: #f3f4f6;
  padding: 15px;
  border-radius: 15px;
  line-height: 1.9;
}

.ranking {
  margin-top: 30px;
}

.ranking li {
  margin: 8px 0;
  padding: 10px;
  background: #f8fafc;
  border-radius: 8px;
}

.review {
  margin-top: 30px;
}

.review-item {
  padding: 15px;
  margin: 12px 0;
  border-radius: 12px;
  background: #fafafa;
}

.correct {
  border-left: 6px solid #22c55e;
}

.wrong {
  border-left: 6px solid #ef4444;
}

.small {
  color: #666;
  font-size: 14px;
}

.loading {
  text-align: center;
  color: #666;
}

.blank {
  display: inline-block;
  min-width: 90px;
  border-bottom: 2px solid #6366f1;
  margin: 0 4px;
}
</style>
</head>

<body>

<div class="container">

<!-- ================= 시작 화면 ================= -->

<div id="startScreen" class="screen active">

  <h1>🧬 감수분열 퀴즈</h1>

  <p style="text-align:center;">
    감수분열의 과정을 얼마나 잘 알고 있을까?
  </p>

  <input
    id="nickname"
    type="text"
    maxlength="20"
    placeholder="닉네임을 입력하세요"
  >

  <button onclick="startGame()">
    게임 시작
  </button>

</div>


<!-- ================= 퀴즈 화면 ================= -->

<div id="quizScreen" class="screen">

  <div class="info">

    <span id="progress">1 / 10</span>

    <span>
      ⏱ <span id="timer">0.00</span>초
    </span>

    <span>
      🏆 <span id="scoreDisplay">0</span>점
    </span>

  </div>

  <div
    id="questionNumber"
    class="question-number">
  </div>

  <div
    id="questionText"
    class="question">
  </div>

  <div id="answerContainer"></div>

  <button onclick="submitAnswer()">
    정답 제출
  </button>

</div>


<!-- ================= 결과 화면 ================= -->

<div id="resultScreen" class="screen">

  <h1>🎉 퀴즈 종료!</h1>

  <div
    id="finalScore"
    class="result-score">
    0점
  </div>

  <div class="result-info">

    <div>
      👤 닉네임:
      <span id="finalName"></span>
    </div>

    <div>
      ✅ 정답:
      <span id="finalCorrect"></span> / 10
    </div>

    <div>
      ⏱ 총 시간:
      <span id="finalTime"></span>초
    </div>

    <div>
      🔥 최고 연속 정답:
      <span id="finalStreak"></span>
    </div>

  </div>


  <div class="ranking">

    <h2>🏆 전체 TOP 15</h2>

    <ol id="rankingList">

      <li class="loading">
        불러오는 중...
      </li>

    </ol>

  </div>


  <div class="review">

    <h2>📝 문제별 결과</h2>

    <div id="reviewList"></div>

  </div>


  <button onclick="location.reload()">
    다시 하기
  </button>

</div>

</div>


<script type="module">

/* =================================================
   Firebase
================================================= */

import { initializeApp }
from "https://www.gstatic.com/firebasejs/12.3.0/firebase-app.js";

import {
  getFirestore,
  collection,
  addDoc,
  query,
  orderBy,
  limit,
  getDocs,
  serverTimestamp
}
from "https://www.gstatic.com/firebasejs/12.3.0/firebase-firestore.js";


const firebaseConfig = {

  apiKey:
    "AIzaSyCe5NTMsC6nAA2LJ_CYWIiMT6vsVaAxUk",

  authDomain:
    "ssb117-eb0c1.firebaseapp.com",

  projectId:
    "ssb117-eb0c1",

  storageBucket:
    "ssb117-eb0c1.firebasestorage.app",

  messagingSenderId:
    "872109001831",

  appId:
    "1:872109001831:web:ecf760e2cb7a860c2b98c2",

  measurementId:
    "G-115T5T0QD8"
};


const app = initializeApp(firebaseConfig);

const db = getFirestore(app);


/* =================================================
   문제 데이터
================================================= */

const questions = [

  {
    number: 1,
    phase: "1분열 전",
    text: "1분열 전 (      )가 복제된다.",
    answers: ["DNA"]
  },


  {
    number: 2,
    phase: "2 전기",
    text: "(      )이 사라지고, (      )가 결합하여 나타난다.",
    answers: [
      "핵막",
      "상동 염색체"
    ]
  },


  {
    number: 3,
    phase: "3 중기",
    text: "(      )가 세포 (      )에 배열한다.",
    answers: [
      "결합한 상동염색체",
      "가운데"
    ]
  },


  {
    number: 4,
    phase: "4 후기",

    /* ★ 4번 수정 */
    text:
      "(      )가 분리되고, 각 (      )가 세포 (      )으로 이동한다.",

    answers: [
      "상동 염색체",
      "염색체",
      "양쪽 끝"
    ]
  },


  {
    number: 5,
    phase: "5 말기",
    text: "(      )이 나타나고, (      )이 나누어진다.",
    answers: [
      "핵막",
      "세포질"
    ]
  },


  {
    number: 6,
    phase: "2분열 전기",

    text:
      "각 세포에 (      )개의 (      )로 이루어진 (      )가 있고, (      )이 사라진다.",

    answers: [
      "두",
      "염색 분체",
      "염색체",
      "핵막"
    ]
  },


  {
    number: 7,
    phase: "2분열 중기",

    text:
      "(      )가 세포 (      )에 배열한다.",

    answers: [
      "염색체",
      "가운데"
    ]
  },


  {
    number: 8,
    phase: "2분열 후기",

    text:
      "각 염색체의 (      )가 분리되어 세포 (      )으로 이동한다.",

    answers: [
      "염색 분체",
      "양쪽 끝"
    ]
  },


  {
    number: 9,
    phase: "말기 및 세포질 분열",

    text:
      "(      )이 나누어지고, (      )가 만들어진다.",

    answers: [
      "세포질",
      "딸세포 네 개"
    ]
  },


  {
    number: 10,
    phase: "생식세포 형성",

    text:
      "(      )는 (      ) 또는 (      )가 된다.",

    answers: [
      "딸세포",
      "정자",
      "난자"
    ]
  }

];


/* =================================================
   게임 변수
================================================= */

let gameQuestions = [];

let currentIndex = 0;

let nickname = "";

let totalScore = 0;

let correctCount = 0;

let currentStreak = 0;

let bestStreak = 0;

let questionStartTime = 0;

let totalStartTime = 0;

let timerInterval = null;

let answerHistory = [];


/* =================================================
   화면 전환
================================================= */

function showScreen(id) {

  document
    .querySelectorAll(".screen")
    .forEach(screen => {

      screen.classList.remove("active");

    });

  document
    .getElementById(id)
    .classList.add("active");
}


/* =================================================
   띄어쓰기 무시
================================================= */

function normalizeAnswer(answer) {

  return String(answer)
    .replace(/\s+/g, "")
    .toLowerCase()
    .trim();

}


/* =================================================
   HTML 안전 처리
================================================= */

function escapeHTML(text) {

  return String(text)

    .replace(/&/g, "&amp;")

    .replace(/</g, "&lt;")

    .replace(/>/g, "&gt;")

    .replace(/"/g, "&quot;")

    .replace(/'/g, "&#039;");
}


/* =================================================
   점수 계산
================================================= */

/*
  0~6초          → 1000점 +25%
  6초 초과~13초  → 500점 +15%
  13초 초과~20초 → 300점 +5%
  20초 초과      → 100점 +3%
*/

function calculateScore(time, streak) {

  let baseScore;
  let bonusRate;


  if (time <= 6) {

    baseScore = 1000;
    bonusRate = 0.25;

  }

  else if (time <= 13) {

    baseScore = 500;
    bonusRate = 0.15;

  }

  else if (time <= 20) {

    baseScore = 300;
    bonusRate = 0.05;

  }

  else {

    baseScore = 100;
    bonusRate = 0.03;

  }


  return Math.round(
    baseScore *
    Math.pow(
      1 + bonusRate,
      streak - 1
    )
  );
}


/* =================================================
   게임 시작
================================================= */

window.startGame = function() {

  nickname =
    document
      .getElementById("nickname")
      .value
      .trim();


  if (!nickname) {

    alert("닉네임을 입력해주세요.");

    return;
  }


  gameQuestions =
    [...questions]
      .sort(() => Math.random() - 0.5);


  currentIndex = 0;

  totalScore = 0;

  correctCount = 0;

  currentStreak = 0;

  bestStreak = 0;

  answerHistory = [];

  totalStartTime = performance.now();


  document
    .getElementById("scoreDisplay")
    .textContent = "0";


  showScreen("quizScreen");

  showQuestion();

};


/* =================================================
   문제 표시
================================================= */

function showQuestion() {

  clearInterval(timerInterval);


  const q =
    gameQuestions[currentIndex];


  document
    .getElementById("progress")
    .textContent =
      `${currentIndex + 1} / ${gameQuestions.length}`;


  document
    .getElementById("questionNumber")
    .textContent =
      `${q.number}번 · ${q.phase}`;


  document
    .getElementById("questionText")
    .textContent =
      q.text;


  const container =
    document.getElementById(
      "answerContainer"
    );


  container.innerHTML = "";


  q.answers.forEach((answer, index) => {

    const input =
      document.createElement("input");


    input.type = "text";

    input.className =
      "answer-input";


    input.placeholder =
      `${index + 1}번째 빈칸`;


    input.autocomplete = "off";


    container.appendChild(input);

  });


  questionStartTime =
    performance.now();


  timerInterval =
    setInterval(updateTimer, 10);


  const firstInput =
    container.querySelector("input");


  if (firstInput) {

    firstInput.focus();

  }

}


/* =================================================
   타이머
================================================= */

function updateTimer() {

  const elapsed =
    (performance.now() -
      questionStartTime) / 1000;


  document
    .getElementById("timer")
    .textContent =
      elapsed.toFixed(2);

}


/* =================================================
   정답 제출
================================================= */

window.submitAnswer = function() {

  clearInterval(timerInterval);


  const q =
    gameQuestions[currentIndex];


  const inputs =
    document
      .getElementById("answerContainer")
      .querySelectorAll("input");


  const userAnswers =
    Array.from(inputs)
      .map(input => input.value);


  const elapsed =
    (performance.now() -
      questionStartTime) / 1000;


  let isCorrect = true;


  /*
    각 빈칸을 개별적으로 비교
    띄어쓰기는 무시
  */

  for (
    let i = 0;
    i < q.answers.length;
    i++
  ) {

    const user =
      normalizeAnswer(
        userAnswers[i] || ""
      );


    const correct =
      normalizeAnswer(
        q.answers[i]
      );


    if (user !== correct) {

      isCorrect = false;

      break;
    }

  }


  let earnedScore = 0;


  if (isCorrect) {

    correctCount++;

    currentStreak++;

    if (
      currentStreak >
      bestStreak
    ) {

      bestStreak =
        currentStreak;

    }


    earnedScore =
      calculateScore(
        elapsed,
        currentStreak
      );


    totalScore +=
      earnedScore;

  }

  else {

    currentStreak = 0;

    earnedScore = 0;

  }


  answerHistory.push({

    number: q.number,

    phase: q.phase,

    question: q.text,

    userAnswers: userAnswers,

    correctAnswers: q.answers,

    correct: isCorrect,

    time: elapsed,

    earnedScore: earnedScore

  });


  document
    .getElementById("scoreDisplay")
    .textContent =
      totalScore;


  setTimeout(() => {

    currentIndex++;


    if (
      currentIndex <
      gameQuestions.length
    ) {

      showQuestion();

    }

    else {

      finishGame();

    }

  }, 500);

};


/* =================================================
   게임 종료
================================================= */

async function finishGame() {

  clearInterval(timerInterval);


  const totalTime =
    (
      performance.now() -
      totalStartTime
    ) / 1000;


  document
    .getElementById("finalName")
    .textContent =
      nickname;


  document
    .getElementById("finalScore")
    .textContent =
      `${totalScore}점`;


  document
    .getElementById("finalCorrect")
    .textContent =
      correctCount;


  document
    .getElementById("finalTime")
    .textContent =
      totalTime.toFixed(2);


  document
    .getElementById("finalStreak")
    .textContent =
      bestStreak;


  showAnswerReview();


  showScreen("resultScreen");


  await saveRecord();


  await loadRanking();

}


/* =================================================
   Firebase 기록 저장
================================================= */

async function saveRecord() {

  try {

    await addDoc(
      collection(
        db,
        "quizScores"
      ),
      {

        name: nickname,

        score: totalScore,

        correct: correctCount,

        totalTime:
          Number(
            (
              (
                performance.now() -
                totalStartTime
              ) / 1000
            ).toFixed(2)
          ),

        bestStreak: bestStreak,

        createdAt:
          serverTimestamp()

      }
    );

  }

  catch (error) {

    console.error(
      "점수 저장 실패:",
      error
    );

  }

}


/* =================================================
   TOP 15
================================================= */

async function loadRanking() {

  const rankingList =
    document
      .getElementById(
        "rankingList"
      );


  rankingList.innerHTML =
    "<li>불러오는 중...</li>";


  try {

    const rankingQuery =
      query(

        collection(
          db,
          "quizScores"
        ),

        orderBy(
          "score",
          "desc"
        ),

        limit(15)

      );


    const snapshot =
      await getDocs(
        rankingQuery
      );


    rankingList.innerHTML = "";


    if (snapshot.empty) {

      rankingList.innerHTML =
        "<li>아직 기록이 없습니다.</li>";

      return;

    }


    let rank = 1;


    snapshot.forEach(doc => {

      const data =
        doc.data();


      const li =
        document.createElement("li");


      li.innerHTML =
        `<strong>${rank}위</strong>
         &nbsp; ${escapeHTML(data.name || "익명")}
         — ${data.score || 0}점`;


      rankingList.appendChild(li);


      rank++;

    });

  }

  catch (error) {

    console.error(
      "랭킹 불러오기 실패:",
      error
    );


    rankingList.innerHTML =

      "<li>랭킹을 불러오지 못했습니다.</li>";

  }

}


/* =================================================
   문제별 결과
================================================= */

function showAnswerReview() {

  const reviewList =
    document
      .getElementById(
        "reviewList"
      );


  reviewList.innerHTML = "";


  answerHistory.forEach(
    (item, index) => {

      const div =
        document.createElement(
          "div"
        );


      div.className =
        "review-item " +
        (
          item.correct
            ? "correct"
            : "wrong"
        );


      const userAnswer =
        item.userAnswers
          .map(
            answer =>
              escapeHTML(
                answer || "(미입력)"
              )
          )
          .join(", ");


      const correctAnswer =
        item.correctAnswers
          .map(
            answer =>
              escapeHTML(answer)
          )
          .join(", ");


      div.innerHTML = `

        <strong>
          ${index + 1}번 · ${escapeHTML(item.phase)}
        </strong>

        <p>
          ${item.correct ? "✅ 정답" : "❌ 오답"}
        </p>

        <p>
          ⏱ ${item.time.toFixed(2)}초
        </p>

        <p>
          💰 획득 점수:
          ${item.earnedScore}점
        </p>

        <p class="small">
          내 답:
          ${userAnswer}
        </p>

        <p class="small">
          정답:
          ${correctAnswer}
        </p>

      `;


      reviewList.appendChild(div);

    }
  );

}


/* =================================================
   Enter 키로 제출
================================================= */

document.addEventListener(
  "keydown",
  function(event) {

    if (
      event.key === "Enter" &&
      document
        .getElementById(
          "quizScreen"
        )
        .classList.contains("active")
    ) {

      submitAnswer();

    }

  }
);

</script>

</body>
</html>
