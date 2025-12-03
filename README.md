<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>เกมทายประเทศจากแผนที่โลก 🌍</title>

<style>
  body {
    font-family: "TH Sarabun New", sans-serif;
    background: #e3f2fd;
    margin: 0;
    padding: 0;
    text-align: center;
  }

  h1 {
    color: #0d47a1;
    margin-top: 14px;
    font-size: 34px;
  }

  .container {
    max-width: 1000px;
    margin: auto;
    padding: 20px;
  }

  #map-container {
    margin-top: 10px;
    border: 3px solid #90caf9;
    border-radius: 12px;
    overflow: hidden;
  }

  svg path.country {
    fill: #cfe8fc;
    stroke: #0d47a1;
    stroke-width: 0.5;
    cursor: pointer;
    transition: 0.2s;
  }

  svg path.country:hover {
    fill: #90caf9;
  }

  .correct {
    fill: #a5d6a7 !important;
  }

  .wrong {
    fill: #ef9a9a !important;
  }

  #question-box {
    font-size: 26px;
    margin: 18px 0;
    color: #0d47a1;
  }

  #next-btn {
    border: none;
    background: #1e88e5;
    color: white;
    padding: 10px 26px;
    border-radius: 999px;
    font-size: 22px;
    cursor: pointer;
    margin-top: 10px;
  }

  #score {
    margin-top: 12px;
    font-size: 24px;
  }

  /* เพิ่มการตอบสนองสำหรับมือถือ */
  @media (max-width: 600px) {
    h1 { font-size: 24px; }
    #question-box { font-size: 20px; }
    #next-btn { font-size: 18px; padding: 8px 18px; }
  }
</style>
</head>

<body>
<h1>เกมทายประเทศจากแผนที่โลก 🌍</h1>

<div class="container">
  <div id="question-box">คลิกที่ประเทศ: <b id="target-country">เริ่มเกม…</b></div>

  <div id="map-container" aria-label="แผนที่โลกแบบจำลอง" role="img">
    <!-- แผนที่แบบง่าย (Simplified World Map) -->
    <svg
      version="1.1"
      xmlns="http://www.w3.org/2000/svg"
      viewBox="0 0 2000 1000"
      style="width:100%; height:auto;"
      aria-hidden="false"
    >
      <!-- อเมริกาเหนือ -->
      <path id="CAN" class="country" d="M250 220 L480 220 L520 260 L520 290 L250 290 Z" tabindex="0" data-name="แคนาดา"></path>
      <path id="USA" class="country" d="M260 290 L520 290 L540 340 L530 380 L260 380 Z" tabindex="0" data-name="สหรัฐอเมริกา"></path>
      <path id="MEX" class="country" d="M320 380 L530 380 L520 430 L430 450 L360 440 Z" tabindex="0" data-name="เม็กซิโก"></path>

      <!-- อเมริกาใต้ -->
      <path id="BRA" class="country" d="M520 500 L620 480 L700 520 L710 620 L640 680 L560 660 L530 590 Z" tabindex="0" data-name="บราซิล"></path>
      <path id="ARG" class="country" d="M580 660 L640 680 L650 780 L610 820 L560 800 Z" tabindex="0" data-name="อาร์เจนตินา"></path>

      <!-- ยุโรป -->
      <path id="GBR" class="country" d="M770 220 L800 230 L800 270 L770 280 L740 260 Z" tabindex="0" data-name="สหราชอาณาจักร"></path>
      <path id="FRA" class="country" d="M800 280 L860 290 L880 330 L850 360 L800 350 L780 320 Z" tabindex="0" data-name="ฝรั่งเศส"></path>
      <path id="ESP" class="country" d="M770 330 L830 350 L820 390 L760 380 Z" tabindex="0" data-name="สเปน"></path>
      <path id="DEU" class="country" d="M860 260 L900 270 L920 310 L900 340 L860 330 L840 300 Z" tabindex="0" data-name="เยอรมนี"></path>
      <path id="ITA" class="country" d="M900 340 L940 360 L930 400 L900 430 L880 410 Z" tabindex="0" data-name="อิตาลี"></path>
      <path id="RUS" class="country" d="M900 200 L1200 200 L1300 230 L1320 290 L1200 310 L950 300 Z" tabindex="0" data-name="รัสเซีย"></path>

      <!-- แอฟริกา -->
      <path id="EGY" class="country" d="M920 380 L980 380 L990 430 L950 450 L910 430 Z" tabindex="0" data-name="อียิปต์"></path>
      <path id="NGA" class="country" d="M880 460 L950 460 L960 500 L910 520 L870 500 Z" tabindex="0" data-name="ไนจีเรีย"></path>
      <path id="KEN" class="country" d="M990 520 L1030 520 L1050 570 L1020 600 L980 580 Z" tabindex="0" data-name="เคนยา"></path>
      <path id="ZAF" class="country" d="M950 650 L1030 650 L1060 710 L1030 770 L960 760 L930 720 Z" tabindex="0" data-name="แอฟริกาใต้"></path>

      <!-- ตะวันออกกลาง -->
      <path id="SAU" class="country" d="M1020 430 L1080 440 L1100 480 L1080 520 L1020 510 L1000 470 Z" tabindex="0" data-name="ซาอุดีอาระเบีย"></path>
      <path id="TUR" class="country" d="M980 360 L1060 360 L1080 390 L1040 410 L980 400 Z" tabindex="0" data-name="ตุรกี"></path>
      <path id="IRN" class="country" d="M1100 430 L1160 430 L1180 480 L1150 510 L1100 500 Z" tabindex="0" data-name="อิหร่าน"></path>

      <!-- เอเชียใต้ & เอเชียตะวันออกเฉียงใต้ -->
      <path id="IND" class="country" d="M1060 500 L1120 510 L1140 560 L1120 610 L1080 620 L1040 580 Z" tabindex="0" data-name="อินเดีย"></path>
      <path id="THA" class="country" d="M1150 570 L1180 580 L1190 620 L1170 650 L1130 630 Z" tabindex="0" data-name="ประเทศไทย"></path>
      <path id="IDN" class="country" d="M1180 660 L1260 670 L1300 700 L1280 730 L1200 720 Z" tabindex="0" data-name="อินโดนีเซีย"></path>

      <!-- เอเชียตะวันออก -->
      <path id="CHN" class="country" d="M1180 430 L1280 430 L1330 470 L1320 520 L1260 540 L1200 520 Z" tabindex="0" data-name="จีน"></path>
      <path id="JPN" class="country" d="M1350 430 L1370 440 L1380 470 L1360 490 L1340 470 Z" tabindex="0" data-name="ญี่ปุ่น"></path>
      <path id="KOR" class="country" d="M1320 410 L1345 420 L1345 440 L1320 445 Z" tabindex="0" data-name="เกาหลีใต้"></path>

      <!-- โอเชียเนีย -->
      <path id="AUS" class="country" d="M1400 720 L1540 730 L1580 780 L1540 830 L1440 840 L1390 800 Z" tabindex="0" data-name="ออสเตรเลีย"></path>
    </svg>
  </div>

  <button id="next-btn" aria-label="ข้อต่อไป">ข้อต่อไป ➜</button>

  <div id="score" aria-live="polite">คะแนน: 0</div>
</div>

<!-- เสียงตอบถูก / ผิด -->
<audio id="sound-correct" src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_5997bfd3b0.mp3?filename=correct-2-46134.mp3" preload="auto"></audio>
<audio id="sound-wrong"   src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_545f3d5d44.mp3?filename=wrong-2-46065.mp3" preload="auto"></audio>

<script>
  // รายชื่อประเทศ (ต้องตรงกับ id ของ path ใน SVG)
  const countries = [
    { id: "THA", name: "ประเทศไทย" },
    { id: "JPN", name: "ญี่ปุ่น" },
    { id: "CHN", name: "จีน" },
    { id: "KOR", name: "เกาหลีใต้" },
    { id: "IND", name: "อินเดีย" },
    { id: "IDN", name: "อินโดนีเซีย" },

    { id: "USA", name: "สหรัฐอเมริกา" },
    { id: "CAN", name: "แคนาดา" },
    { id: "MEX", name: "เม็กซิโก" },
    { id: "BRA", name: "บราซิล" },
    { id: "ARG", name: "อาร์เจนตินา" },

    { id: "GBR", name: "สหราชอาณาจักร" },
    { id: "FRA", name: "ฝรั่งเศส" },
    { id: "ESP", name: "สเปน" },
    { id: "DEU", name: "เยอรมนี" },
    { id: "ITA", name: "อิตาลี" },
    { id: "RUS", name: "รัสเซีย" },

    { id: "EGY", name: "อียิปต์" },
    { id: "NGA", name: "ไนจีเรีย" },
    { id: "KEN", name: "เคนยา" },
    { id: "ZAF", name: "แอฟริกาใต้" },

    { id: "SAU", name: "ซาอุดีอาระเบีย" },
    { id: "IRN", name: "อิหร่าน" },
    { id: "TUR", name: "ตุรกี" },

    { id: "AUS", name: "ออสเตรเลีย" }
  ];

  let score = 0;
  let current = null;
  let locked = false; // กันคลิกหลายครั้งในคำถามเดียว

  const targetEl = document.getElementById("target-country");
  const scoreEl = document.getElementById("score");
  const nextBtn = document.getElementById("next-btn");

  const soundCorrect = document.getElementById("sound-correct");
  const soundWrong   = document.getElementById("sound-wrong");

  function randomCountry() {
    return countries[Math.floor(Math.random() * countries.length)];
  }

  function resetMapColors() {
    document.querySelectorAll("svg path.country").forEach(p => {
      p.classList.remove("correct", "wrong");
      p.setAttribute("aria-pressed", "false");
    });
  }

  function setQuestion() {
    resetMapColors();
    current = randomCountry();
    locked = false;
    targetEl.textContent = current.name;
    // focus hint for accessibility
    nextBtn.focus();
  }

  // เมื่อคลิกประเทศในแผนที่
  document.querySelectorAll("svg path.country").forEach(el => {
    el.addEventListener("click", () => {
      if (!current || locked) return; // ถ้าตอบไปแล้วไม่คิดคะแนนซ้ำ

      if (el.id === current.id) {
        el.classList.add("correct");
        el.setAttribute("aria-pressed", "true");
        soundCorrect.currentTime = 0;
        soundCorrect.play().catch(()=>{});
        score++;
      } else {
        el.classList.add("wrong");
        el.setAttribute("aria-pressed", "true");
        soundWrong.currentTime = 0;
        soundWrong.play().catch(()=>{});
        // ไฮไลต์ประเทศที่ถูกต้อง
        const correctEl = document.getElementById(current.id);
        if (correctEl) correctEl.classList.add("correct");
      }

      scoreEl.textContent = "คะแนน: " + score;
      locked = true;
    });

    // เพิ่มการรองรับคลิกด้วยคีย์บอร์ด (Enter / Space)
    el.addEventListener("keydown", (e) => {
      if (e.key === "Enter" || e.key === " ") {
        e.preventDefault();
        el.click();
      }
    });
  });

  nextBtn.onclick = setQuestion;
  nextBtn.addEventListener("keydown", (e) => {
    if (e.key === "Enter" || e.key === " ") {
      e.preventDefault();
      setQuestion();
    }
  });

  // เริ่มเกมครั้งแรก
  setQuestion();
</script>

</body>
</html>
