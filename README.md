<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0,maximum-scale=1.0,user-scalable=no">
<meta name="theme-color" content="#0b0b0d">
<title>البصمة العطرية V6.1</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Arabic:wght@400;500;600;700&display=swap" rel="stylesheet">

<style>
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent;}

:root{
  --bg:#0b0b0d;
  --line:#29292f;
  --text:#f3f0ea;
  --muted:#9d9aa1;

  /* Men (default) — gold */
  --accent:#d8b36a;
  --accent2:#ead09a;
  --accent-rgb:216,179,106;
  --accent2-rgb:234,208,154;
}

body.women{
  /* Women — rose gold */
  --accent:#d987a8;
  --accent2:#f0c0d4;
  --accent-rgb:217,135,168;
  --accent2-rgb:240,192,212;
}

body.unisex{
  /* Unisex — soft silver */
  --accent:#a8b8d0;
  --accent2:#cdd8e6;
  --accent-rgb:168,184,208;
  --accent2-rgb:205,216,230;
}

html,body{margin:0;padding:0;min-height:100%;background:var(--bg);}

body{
  color:var(--text);
  font-family:"Noto Sans Arabic","Cairo",Arial,sans-serif;
}

button{font-family:inherit;}

/* Smooth transitions when catalog colors change */
.logoMark,
.modeCard,
.modeBadge,
.catalogPill,
.option,
.progressBar,
.next,
.fingerprint,
.tag,
.perfume,
.questionKicker,
.check,
.restartBig{
  transition:
    background .4s ease,
    background-color .4s ease,
    border-color .4s ease,
    box-shadow .4s ease,
    color .4s ease;
}

.app{
  width:100%;max-width:520px;min-height:100vh;
  margin:auto;padding:18px 16px 35px;
}

.screen{display:none;}
.screen.active{display:block;}

.logo{text-align:center;padding-top:22px;}

.logoMark{
  width:72px;height:72px;
  border:1px solid rgba(var(--accent-rgb),.5);
  border-radius:50%;
  margin:0 auto 20px;
  display:flex;align-items:center;justify-content:center;
  font-size:30px;color:var(--accent2);
  box-shadow:
    0 0 40px rgba(var(--accent-rgb),.12),
    inset 0 0 20px rgba(var(--accent-rgb),.05);
}

h1{font-size:29px;margin:0 0 9px;font-weight:600;letter-spacing:-.5px;}

.subtitle{
  color:var(--muted);font-size:14px;line-height:1.9;
  max-width:390px;margin:0 auto;
}

.catalogRow{
  display:flex;flex-wrap:wrap;justify-content:center;align-items:center;
  gap:8px;margin-top:26px;
}

.catalogLabel{color:#77757a;font-size:11px;}

.catalogPill{
  border:1px solid #29292f;
  background:transparent;
  color:#9d9aa1;
  border-radius:30px;
  padding:6px 14px;
  font-size:12px;
  cursor:pointer;
}

.catalogPill:active{transform:scale(.97);}

.catalogPill.active{
  border-color:var(--accent);
  color:var(--accent2);
  background:rgba(var(--accent-rgb),.1);
}

.catalogPill.empty{opacity:.55;}

.catalogPill.empty::after{
  content:" · قريباً";
  font-size:10px;
  opacity:.75;
}

.modeIntro{margin-top:32px;}

.modeCard{
  background:linear-gradient(145deg,#19191d,#111115);
  border:1px solid var(--line);
  border-radius:20px;padding:22px 20px;
  margin-bottom:13px;cursor:pointer;
}

.modeCard:active{transform:scale(.985);}
.modeCard.recommended{border-color:rgba(var(--accent-rgb),.48);}

.modeBadge{
  display:inline-block;color:#111;background:var(--accent);
  border-radius:30px;padding:4px 10px;font-size:11px;
  font-weight:600;margin-bottom:11px;
}

.modeBadge.soft{
  background:transparent;
  border:1px solid rgba(var(--accent-rgb),.5);
  color:var(--accent2);font-weight:500;
}

.modeTitle{font-size:20px;font-weight:600;margin-bottom:7px;}
.modeDesc{color:var(--muted);font-size:13px;line-height:1.8;}
.modeTime{margin-top:14px;color:#c7c4bd;font-size:12px;}

.note{
  text-align:center;color:#77757a;font-size:11px;
  line-height:1.8;margin-top:24px;
}

.top{padding-top:5px;}

.topLine{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:13px;
}

.counter{color:var(--muted);font-size:12px;}

.selectionCounter{
  color:#9b969c;font-size:12px;margin-top:3px;
  display:flex;align-items:center;gap:8px;
}

.dots{display:inline-flex;gap:4px;}

.dot{
  width:7px;height:7px;border-radius:50%;
  background:#33333a;
  transition:background .3s ease, box-shadow .3s ease;
}

.dot.on{
  background:var(--accent);
  box-shadow:0 0 6px rgba(var(--accent-rgb),.5);
}

.restart{
  border:0;background:none;color:#8a878e;
  font-size:12px;padding:5px;
}

.progress{
  height:4px;background:#222228;border-radius:5px;
  overflow:hidden;margin-bottom:34px;
}

.progressBar{
  height:100%;
  background:linear-gradient(90deg,var(--accent),var(--accent2));
  width:0%;border-radius:5px;
  transition:width .35s ease, background .4s ease;
}

.questionKicker{
  color:var(--accent);font-size:11px;
  letter-spacing:.5px;margin-bottom:9px;
}

.question{
  font-size:25px;line-height:1.45;font-weight:600;
  margin-bottom:9px;letter-spacing:-.3px;
}

.hint{
  color:#8d8a91;font-size:12px;
  line-height:1.8;margin-bottom:22px;
}

.options{display:grid;gap:10px;}

.option{
  width:100%;
  background:rgba(22,22,27,.94);
  border:1px solid #29292f;color:#e8e5df;
  border-radius:15px;padding:15px;min-height:54px;
  text-align:right;font-size:14px;line-height:1.55;
  display:flex;align-items:center;gap:11px;
}

.option:active{transform:scale(.985);}

.option.selected{
  border-color:rgba(var(--accent-rgb),.85);
  background:linear-gradient(145deg,#252119,#1b1915);
  color:var(--accent2);
  box-shadow:0 4px 20px rgba(var(--accent-rgb),.15);
}

.check{
  width:19px;height:19px;
  border:1px solid #55545b;border-radius:50%;
  flex:none;display:flex;align-items:center;justify-content:center;
  font-size:11px;color:transparent;
}

.option.selected .check{
  border-color:var(--accent);
  background:var(--accent);color:#111;
}

.fadeGroup{animation:fadeIn .28s ease;}

@keyframes fadeIn{
  from{opacity:0;transform:translateY(6px);}
  to{opacity:1;transform:translateY(0);}
}

.footer{margin-top:25px;}

.next{
  width:100%;border:0;border-radius:15px;
  background:var(--accent);color:#111;
  padding:15px;font-size:15px;font-weight:700;
}

.next:not(:disabled){
  background:linear-gradient(145deg,var(--accent),var(--accent2));
  box-shadow:0 6px 22px rgba(var(--accent-rgb),.18);
}

.next:disabled{opacity:.35;box-shadow:none;}

.back{
  width:100%;margin-top:8px;
  border:1px solid #29292f;background:#1a1a1e;
  color:#c8c4bc;border-radius:15px;
  padding:12px;font-size:13px;
  transition:transform .2s ease;
}

.back:active{transform:scale(.985);}

.resultHeader{text-align:center;padding-top:15px;}
.resultHeader h2{margin:0 0 7px;font-size:28px;}
.resultHeader p{margin:0;color:var(--muted);font-size:13px;}

.fingerprint{
  margin:26px 0 20px;
  background:linear-gradient(145deg,#191814,#131316);
  border:1px solid rgba(var(--accent-rgb),.27);
  border-radius:21px;padding:21px;
}

.fingerprintTitle{
  color:var(--accent);font-size:11px;margin-bottom:14px;
}

.tags{display:flex;flex-wrap:wrap;gap:8px;}

.tag{
  border:1px solid rgba(var(--accent-rgb),.35);
  background:linear-gradient(145deg,rgba(var(--accent-rgb),.08),#1a1a1e);
  border-radius:30px;padding:8px 13px;
  font-size:13px;color:var(--accent2);
}

.resultIntro{
  font-size:13px;color:#9b989e;
  line-height:1.8;margin:0 0 15px;
}

.perfume{
  background:#151519;border:1px solid #29292f;
  border-radius:19px;padding:19px;
  margin-bottom:12px;
}

.perfume.first{
  border-color:rgba(var(--accent-rgb),.55);
  background:linear-gradient(145deg,rgba(var(--accent-rgb),.08),#151519);
  padding:22px;
  box-shadow:0 10px 32px rgba(var(--accent-rgb),.08);
}

.perfumeRank{color:var(--accent);font-size:11px;margin-bottom:8px;}
.perfume.first .perfumeRank{font-size:12px;font-weight:600;}
.perfumeName{font-size:20px;font-weight:600;margin-bottom:8px;}
.perfume.first .perfumeName{font-size:23px;color:var(--accent2);}

.notes{color:#8f8c93;font-size:12px;line-height:1.7;margin-bottom:13px;}

.matchReason{
  border-top:1px solid #27272c;padding-top:11px;
  color:#c8c4bc;font-size:12px;line-height:1.75;
}

.perfume.first .matchReason{
  border-top-color:rgba(var(--accent-rgb),.2);
}

.matchReason strong{color:var(--accent2);}

.matchScore{
  color:var(--accent2);font-size:12.5px;
  margin-top:9px;font-weight:500;
}

.emptyCatalog{
  text-align:center;
  padding:40px 20px;
  color:#8d8a91;
  font-size:14px;
  line-height:1.9;
  border:1px dashed #29292f;
  border-radius:19px;
}

.restartBig{
  width:100%;margin-top:14px;
  border:1px solid #37343a;background:#151519;
  color:#ddd9d1;border-radius:15px;
  padding:14px;font-size:13px;
}

@media(max-width:360px){
  .question{font-size:22px;}
  .app{padding-left:13px;padding-right:13px;}
}
</style>
</head>

<body>

<div class="app">

<section id="home" class="screen active">
  <div class="logo">
    <div class="logoMark">✦</div>
    <h1>البصمة العطرية</h1>
    <p class="subtitle">
      تجربة قصيرة لاكتشاف نوع الروائح التي تنجذب إليها
      بشكل طبيعي.
    </p>
  </div>

  <div class="catalogRow" id="catalogRow">
    <span class="catalogLabel">الكتالوج:</span>
    <button class="catalogPill active" data-catalog="men" onclick="setCatalog('men')">رجالي</button>
    <button class="catalogPill" data-catalog="women" onclick="setCatalog('women')">نسائي</button>
    <button class="catalogPill empty" data-catalog="unisex" onclick="setCatalog('unisex')">للجنسين</button>
  </div>

  <div class="modeIntro">
    <div class="modeCard recommended" onclick="startTest('quick')">
      <div class="modeBadge">الأسرع</div>
      <div class="modeTitle">⚡ السريع — 6 أسئلة</div>
      <div class="modeDesc">
        أسئلة قليلة ومركّزة للوصول بسرعة إلى
        العطور الأقرب إلى ذوقك.
      </div>
      <div class="modeTime">حوالي دقيقتين</div>
    </div>

    <div class="modeCard" onclick="startTest('deep')">
      <div class="modeBadge soft">تجربة أعمق</div>
      <div class="modeTitle">✦ المعمّق — 12 سؤالاً</div>
      <div class="modeDesc">
        تجربة حسية أوسع تشمل الروائح اليومية،
        الأصوات، الموسيقى، الأجواء وطريقة حضور العطر.
      </div>
      <div class="modeTime">حوالي 3–4 دقائق</div>
    </div>
  </div>

  <div class="note">
    لا توجد إجابات صحيحة أو خاطئة.<br>
    اختر ما يجذبك تلقائياً.
  </div>
</section>


<section id="quiz" class="screen">
  <div class="top">
    <div class="topLine">
      <div>
        <div class="counter" id="counter">01 / 06</div>
        <div class="selectionCounter" id="selectionCounter"></div>
      </div>
      <button class="restart" onclick="goHome()">تغيير التجربة</button>
    </div>

    <div class="progress">
      <div class="progressBar" id="progressBar"></div>
    </div>

    <div id="fadeGroup" class="fadeGroup">
      <div class="questionKicker" id="questionKicker">البصمة الحسية</div>
      <div class="question" id="question"></div>
      <div class="hint" id="hint"></div>
      <div class="options" id="options"></div>
    </div>

    <div class="footer">
      <button class="next" id="nextBtn" onclick="nextQuestion()">التالي</button>
      <button class="back" id="backBtn" onclick="previousQuestion()">السابق</button>
    </div>
  </div>
</section>


<section id="result" class="screen">
  <div class="resultHeader">
    <h2>بصمتك العطرية</h2>
    <p>قراءة لذوقك الحسي، وليست اختباراً للشخصية.</p>
  </div>

  <div class="fingerprint">
    <div class="fingerprintTitle">الملامح الأقرب إلى اختياراتك</div>
    <div class="tags" id="tags"></div>
  </div>

  <p class="resultIntro">
    بناءً على اختياراتك، هذه هي العطور الثلاثة
    الأقرب إلى ذوقك داخل المجموعة.
  </p>

  <div id="results"></div>

  <button class="restartBig" onclick="goHome()">تجربة جديدة</button>
</section>

</div>


<script>

/* =========================================================
   CATALOGS
   ========================================================= */

const CATALOGS = {

  men: [
    { name:"Dunhill Fresh", notes:"نعناع، برغموت، ريحان، لافندر، وخشب الصندل", type:"men", vector:[88,28,48,12,22,28,55,45,42,12,88,18] },
    { name:"Desire Blue", notes:"ليتشي، برغموت، نوتات بحرية، عنبر، ومسك", type:"men", vector:[78,82,8,25,30,30,45,48,45,5,5,20] },
    { name:"Azzaro Chrome", notes:"ليمون، برغموت، إكليل الجبل، أناناس، وخشب الأرز", type:"men", vector:[91,35,42,20,18,28,55,52,45,8,68,15] },
    { name:"Azzaro Pour Homme", notes:"لافندر، يانسون، ريحان، خشب الصندل، وجلد", type:"men", vector:[48,5,65,15,48,58,68,62,58,28,58,48] },
    { name:"Azzaro Wanted", notes:"ليمون، زنجبيل، هيل، خشب العرعر، وتونكا", type:"men", vector:[62,8,52,55,58,52,62,72,65,72,22,38] },
    { name:"Burberry Hero", notes:"برغموت، فلفل أسود، وثلاثة أنواع من أخشاب الأرز", type:"men", vector:[55,5,88,8,32,52,72,60,58,48,10,35] },
    { name:"Bvlgari Homme Soir", notes:"شاي دارجيلنغ، برغموت، عنبر، ونبات البردي", type:"men", vector:[55,15,38,20,48,55,82,48,50,8,42,48] },
    { name:"CK One", notes:"برغموت، هيل، أناناس، ياسمين، مسك، وعنبر", type:"men", vector:[78,25,8,25,28,30,52,42,38,25,12,15] },
    { name:"CK Euphoria Men", notes:"زنجبيل، فلفل، ريحان أسود، أرز، وخشب الصندل", type:"men", vector:[38,5,72,12,48,58,62,60,58,78,55,42] },
    { name:"CK Defy", notes:"برغموت، لافندر، نجيل الهند، وأرز", type:"men", vector:[70,10,65,8,25,48,70,52,52,5,55,35] },
    { name:"212 Men", notes:"نوتات خضراء، برغموت، زنجبيل، غاردينيا، ومسك", type:"men", vector:[78,18,12,18,25,32,62,52,48,32,82,22] },
    { name:"212 VIP Men", notes:"ليمون حامض، فلفل، زنجبيل، جين، فودكا، وجلد", type:"men", vector:[58,8,25,18,48,52,58,70,62,78,8,45] },
    { name:"212 Sexy Men", notes:"ماندارين، برغموت، هيل، فلفل، وفانيليا", type:"men", vector:[58,5,8,62,68,48,58,65,62,68,5,38] },
    { name:"Cartier Déclaration", notes:"برغموت، بيتيغرين، هيل، زنجبيل، وأرز", type:"men", vector:[65,5,68,8,30,52,82,55,55,58,48,48] },
    { name:"Chanel Allure Homme Sport", notes:"أورانج، نوتات بحرية، فلفل، فانيليا، وعنبر", type:"men", vector:[72,68,18,42,48,42,78,68,62,38,5,25] },
    { name:"Bleu de Chanel", notes:"جريب فروت، ليمون، نعناع، بخور، وأرز", type:"men", vector:[82,18,62,8,28,52,86,65,62,25,42,48] },
    { name:"Chanel Égoïste Platinum", notes:"إكليل الجبل، لافندر، بيتيغرين، وعنبر", type:"men", vector:[62,5,35,8,42,52,88,68,65,22,72,42] },
    { name:"Dior Homme Intense", notes:"لافندر، زهرة السوسن، مسك الروم، وأرز", type:"men", vector:[32,2,58,42,58,78,92,65,82,5,12,72] },
    { name:"Dior Fahrenheit", notes:"جوزة الطيب، لافندر، جلد، نجيل الهند، وعنبر", type:"men", vector:[42,2,62,12,62,82,78,72,82,55,45,78] },
    { name:"Dior Bois d'Argent", notes:"سوسن، مر، عنبر، ومسك", type:"men", vector:[28,2,42,18,62,82,95,55,78,5,5,88] },
    { name:"Creed Aventus", notes:"أناناس، برغموت، تفاح، خشب البتولا، وعنبر الحوت", type:"men", vector:[72,5,62,28,35,62,86,72,78,18,28,48] },
    { name:"Diesel Fuel for Life", notes:"يانسون نجمي، جريب فروت، لافندر، وتوت العليق", type:"men", vector:[62,5,5,55,42,38,45,62,55,48,18,32] },
    { name:"Faberge Brut", notes:"لافندر، أنيس، برغموت، ياسمين، وفانيليا", type:"men", vector:[58,3,8,42,42,45,58,55,48,42,18,35] },
    { name:"Davidoff Cool Water", notes:"نعناع، نوتات مائية، لافندر، وخشب الصندل", type:"men", vector:[88,90,35,8,18,28,58,58,52,8,52,18] },
    { name:"MFK Baccarat Rouge 540", notes:"زعفران، ياسمين، خشب الأرز، وأمبروكسان", type:"men", vector:[38,2,55,48,62,72,88,90,92,48,3,78] },
    { name:"Givenchy Pi", notes:"ريحان، إكليل الجبل، ماندارين، بنزوين، وفانيليا", type:"men", vector:[48,3,18,65,72,62,62,62,65,22,42,48] },
    { name:"Armani Code", notes:"ليمون، برغموت، زهر الزيتون، أنيس، وتونكا", type:"men", vector:[55,3,12,58,62,55,78,62,65,42,18,52] },
    { name:"Acqua Di Gio", notes:"نوتات بحرية، برغموت، إكليل الجبل، وباتشولي", type:"men", vector:[85,82,18,5,18,35,68,58,48,8,48,18] },
    { name:"Stronger With You", notes:"هيل، فلفل وردي، ميرمية، وفانيليا كستناء", type:"men", vector:[32,2,8,82,82,62,62,78,82,65,32,42] },
    { name:"Gucci Guilty", notes:"لافندر، ليمون، زهر البرتقال، وباتشولي", type:"men", vector:[58,3,28,18,38,45,68,58,55,12,38,35] },
    { name:"Terre d'Hermès", notes:"برتقال، جريب فروت، فلفل، ونجيل الهند", type:"men", vector:[72,3,58,5,32,62,92,62,68,52,38,62] },
    { name:"Hugo Boss Hugo", notes:"تفاح أخضر، لافندر، ميرمية، وأرز", type:"men", vector:[72,5,48,18,22,38,58,48,45,8,68,22] },
    { name:"Boss Bottled", notes:"تفاح، قرفة، ماهوجني، فانيليا، وأخشاب", type:"men", vector:[45,3,58,55,65,55,72,65,62,58,8,38] },
    { name:"JPG Ultra Male", notes:"كمثرى، لافندر، نعناع، قرفة، وفانيليا سوداء", type:"men", vector:[48,2,8,88,78,55,48,88,88,58,8,42] },
    { name:"JPG Le Male", notes:"نعناع، لافندر، قرفة، زهر البرتقال، وفانيليا", type:"men", vector:[52,3,8,68,65,52,62,72,68,55,12,38] },
    { name:"Lacoste L.12.12 Blanc", notes:"جريب فروت، هيل، توبيروز، وجلد سوييد", type:"men", vector:[68,5,28,18,32,38,68,48,45,42,12,32] },
    { name:"Memo Russian Leather", notes:"ريحان، صنوبر، إكليل الجبل، وجلد", type:"men", vector:[52,2,72,5,38,68,72,62,68,18,82,68] },
    { name:"Montblanc Legend", notes:"لافندر، برغموت، تفاح أحمر، وطحلب البلوط", type:"men", vector:[65,3,38,28,28,42,65,55,52,5,48,28] },
    { name:"Nikos Sculpture", notes:"زهر البرتقال، ليمون، برغموت، وتونكا", type:"men", vector:[70,3,5,48,48,42,62,58,52,5,12,28] },
    { name:"Paco Rabanne 1 Million", notes:"ماندارين، قرفة، ورد، وجلد دافئ", type:"men", vector:[48,2,18,52,72,62,62,82,78,72,3,48] },
    { name:"Paco Rabanne Invictus", notes:"جريب فروت، نوتات بحرية، ورق الغار، وباتشولي", type:"men", vector:[78,82,18,22,28,38,55,78,72,18,35,22] },
    { name:"Ralph Lauren Polo Blue", notes:"خيار، بطيخ، ريحان، ميرمية، ومسك", type:"men", vector:[82,58,8,18,20,28,55,48,45,5,62,15] },
    { name:"Tom Ford Black Orchid", notes:"كمأة سوداء، أوركيد أسود، فانيليا، وبخور", type:"men", vector:[18,2,18,58,78,88,88,78,85,38,5,92] },
    { name:"Tom Ford Bitter Peach", notes:"خوخ، برتقال دموي، رم، وفانيليا", type:"men", vector:[48,2,3,78,75,58,65,72,68,18,2,52] },
    { name:"YSL La Nuit De L'Homme", notes:"هيل، برغموت، لافندر، وأرز", type:"men", vector:[52,3,48,18,48,52,82,52,48,68,25,58] },
    { name:"YSL L'Homme Intense", notes:"ليمون، برغموت، فلفل أسود، وأورانج أزهار", type:"men", vector:[62,3,18,15,38,42,78,58,55,52,15,38] },
    { name:"YSL M7", notes:"ماندارين، روزوود، عود، ونجيل الهند", type:"men", vector:[42,2,82,12,58,78,78,72,78,18,32,82] },
    { name:"غبار ذهبي", notes:"عود نقي، مسك أبيض، عنبر ذهبي، بخور، زعفران", type:"men", vector:[12,1,82,35,88,92,82,82,90,62,2,88] },
    { name:"مضيلة", notes:"عود نقي، مسك أبيض، عنبر ذهبي، بخور، زعفران", type:"men", vector:[15,1,78,38,85,88,80,78,88,58,2,84] },
    { name:"كلمات", notes:"عود نقي، مسك أبيض، عنبر ذهبي، بخور، زعفران", type:"men", vector:[18,1,75,42,82,85,82,75,86,55,2,82] }
  ],

  women: [
    { name:"Avon Célèbre", notes:"سيكلامين، فواكه، فلفل، بيوني، فريزيا، ياسمين، ماغنوليا، زنبق الوادي، أرز، صندل", type:"women", vector:[55,10,45,45,40,42,65,45,45,22,25,25] },
    { name:"Azzaro Wanted Girl", notes:"زهرة الزنجبيل، براعم البرتقال، فلفل وردي، رمان، حليب دولسي دي ليتشي، داتورا، تونكا، باتشولي، نجيل الهند", type:"women", vector:[42,5,38,72,68,55,58,65,65,42,12,35] },
    { name:"Burberry Weekend for Women", notes:"ماندرين، مريمية، مخملية، نكتارين، ياقوتية زرقاء، زهر الخوخ، سوسن، مسك، صندل، أرز", type:"women", vector:[65,12,42,35,35,40,68,45,42,8,42,22] },
    { name:"Burberry Brit Rhythm for Her", notes:"لافندر، فلفل وردي، نيرولي، زهر البرتقال، سوسن، توت أسود، مسك، نوتات خشبية، كومارين، أرز، نجيل الهند", type:"women", vector:[52,8,55,30,42,52,68,55,55,32,42,32] },
    { name:"My Burberry", notes:"بازلاء حلوة، برغموت، يوسفي، جريب فروت، سفرجل، فريزيا، إبرة الراعي، خوخ، غاردينيا، ورد، باتشولي، مسك، جلود", type:"women", vector:[55,5,42,42,52,62,82,62,65,12,28,42] },
    { name:"Burberry Her", notes:"فراولة، توت العليق، توت أسود، كرز حامض، يوسفي، بنفسج، ياسمين، مسك، فانيليا، عنبر، كشمير، باتشولي", type:"women", vector:[48,3,22,78,62,55,58,68,68,12,8,32] },
    { name:"Bvlgari Rose Goldea", notes:"ورد، رمان، مسك، برغموت، ورد جوري، بيوني، ياسمين، خوخ، صندل، بخور، فانيليا", type:"women", vector:[48,5,42,55,52,58,82,55,62,8,10,38] },
    { name:"Britney Spears Midnight Fantasy", notes:"برقوق، كرز حامض، توت العليق، أوركيد، سوسن، فريزيا، فانيليا، عنبر، مسك", type:"women", vector:[38,2,8,78,65,48,45,65,62,5,5,30] },
    { name:"Britney Spears Fantasy", notes:"كيوي، ليتشي أحمر، سفرجل، شوكولاتة بيضاء، كب كيك، أوركيد، ياسمين، مسك، جذر السوسن، أخشاب", type:"women", vector:[42,3,12,88,68,52,42,75,72,8,5,28] },
    { name:"Byredo Super Cedar", notes:"بتلات الورد، خشب الأرز الفيرجيني، نجيل الهند، مسك", type:"women", vector:[35,2,92,12,32,62,82,55,65,8,12,52] },
    { name:"Calvin Klein Euphoria for Women", notes:"رمان، كاكي، نوتات خضراء، أوركيد أسود، لوتس، ماهوجني، عنبر، بنفسج أسود، كريمة مخفوقة", type:"women", vector:[38,8,42,58,65,72,72,65,72,25,22,68] },
    { name:"Cacharel Amor Amor", notes:"كشمش أسود، برتقال، يوسفي، برغموت، ورد، مشمش، ياسمين، زنبق الوادي، فانيليا، تونكا، مسك، عنبر، أرز", type:"women", vector:[48,2,22,72,65,48,52,68,65,12,8,28] },
    { name:"Cacharel Yes I Am", notes:"توت العليق، يوسفي، ليمون، برغموت، زهرة الزنجبيل، غاردينيا، ياسمين، زهر البرتقال، ورد، حليب، كراميل، فانيليا، هيل، عرقسوس، صندل", type:"women", vector:[42,2,12,88,75,58,55,72,72,32,3,32] },
    { name:"Carolina Herrera 212 VIP", notes:"روم، باشن فروت، غاردينيا، مسك، فانيليا، تونكا", type:"women", vector:[48,3,8,75,68,52,62,72,68,18,5,32] },
    { name:"Carolina Herrera 212 Sexy", notes:"فلفل وردي، يوسفي، برغموت، غزل البنات، غاردينيا، أزهار، ورد، فانيليا، مسك، صندل، كراميل، باتشولي", type:"women", vector:[45,2,18,82,68,52,55,70,68,22,3,30] },
    { name:"Carolina Herrera Good Girl", notes:"لوز، قهوة، برغموت، ليمون، توبروز، ياسمين سامباك، زهر البرتقال، سوسن، ورد بلغاري، تونكا، كاكاو، فانيليا، برالين، صندل، عنبر، كشمير، باتشولي", type:"women", vector:[32,2,22,78,78,72,75,82,82,25,3,52] },
    { name:"Carolina Herrera CH Privée", notes:"أوسمانثوس، كافيار، فلفل وردي، جلود، ورد، فانيليا، باتشولي، مسك", type:"women", vector:[35,2,42,48,68,75,82,72,78,38,5,72] },
    { name:"Chanel Chance Eau de Parfum", notes:"فلفل وردي، ياسمين، سوسن، باتشولي، فانيليا، مسك", type:"women", vector:[42,2,28,52,62,62,82,58,68,22,8,45] },
    { name:"Chanel No 5", notes:"ألدهيدات، يلانغ يلانغ، نيرولي، برغموت، خوخ، سوسن، ياسمين، ورد، زنبق الوادي، صندل، فانيليا، طحلب البلوط، نجيل الهند، باتشولي", type:"women", vector:[52,5,45,35,48,72,95,65,72,8,28,55] },
    { name:"Chanel Coco Eau de Parfum", notes:"ورد بلغاري، كزبرة، خوخ، ياسمين، يوسفي، قرنفل، ورد، ميموزا، زهر البرتقال، عنبر، صندل، تونكا، أوبوبوناكس، فانيليا", type:"women", vector:[38,2,48,55,72,75,85,72,82,42,8,68] },
    { name:"Chanel Allure Eau de Parfum", notes:"ليمون، برغموت، يوسفي، خوخ، باشن فروت، ياسمين، زنبق الماء، صفيراء، ماغنوليا، ورد، بيوني، فانيليا، صندل، عنبر، نجيل الهند", type:"women", vector:[58,12,32,42,42,52,82,55,62,5,22,38] },
    { name:"Chanel Coco Mademoiselle", notes:"برتقال، يوسفي، برغموت، زهر البرتقال، ورد تركي، ياسمين، ميموزا، يلانغ يلانغ، باتشولي، مسك أبيض، فانيليا، نجيل الهند، تونكا", type:"women", vector:[58,5,35,45,52,62,88,72,75,12,22,48] },
    { name:"Chanel Gabrielle", notes:"جريب فروت، يوسفي، كشمش أسود، زهر البرتقال، ياسمين، يلانغ يلانغ، توبروز، كمثرى، مسك، صندل، كشميران، سوسن", type:"women", vector:[58,5,35,42,42,55,88,62,65,5,18,38] },
    { name:"Dior Miss Dior Chérie", notes:"فراولة برية، كرز، أناناس، يوسفي، فشار، كراميل، ورد، ياسمين، باتشولي، عنبر، مسك", type:"women", vector:[52,2,12,82,62,52,58,68,62,8,5,30] },
    { name:"Dior Miss Dior Blooming Bouquet", notes:"يوسفي صقلي، بيوني وردي، ورد جوري، مشمش، خوخ، مسك أبيض", type:"women", vector:[62,8,8,48,32,38,78,48,48,3,22,22] },
    { name:"Dior J'adore", notes:"كمثرى، شمام، ماغنوليا، خوخ، يوسفي، برغموت، ياسمين، زنبق الوادي، توبروز، فريزيا، ورد، أوركيد، مسك، فانيليا، توت أسود، أرز", type:"women", vector:[62,8,22,52,48,58,88,68,68,5,15,38] },
    { name:"Dior Poison Girl", notes:"برتقال مر، ليمون، ورد جوري، وردة غراس، زهر البرتقال، فانيليا، تونكا، لوز، صندل، كشميران", type:"women", vector:[42,2,22,78,75,68,72,72,78,12,3,52] },
    { name:"Dior Hypnotic Poison", notes:"برقوق، جوز الهند، مشمش، توبروز، ياسمين، كراوية، خشب الورد البرازيلي، ورد، فانيليا، لوز، صندل، مسك", type:"women", vector:[32,2,32,82,78,72,72,75,82,18,3,62] },
    { name:"Dior Addict Eau de Parfum", notes:"توت أسود، أوراق اليوسفي، ياسمين، ملكة الليل، زهر البرتقال، ورد، فانيليا، تونكا، صندل", type:"women", vector:[42,2,22,72,68,62,72,68,72,8,12,48] },
    { name:"D&G 3 L'Impératrice", notes:"كيوي، راوند، فلفل وردي، بطيخ، سيكلامين، ياسمين، ليمون، مسك، صندل", type:"women", vector:[72,15,22,42,28,35,62,48,42,8,22,18] },
    { name:"Dolce & Gabbana The One for Women", notes:"خوخ، ليتشي، يوسفي، برغموت، زنبق أبيض، برقوق، ياسمين، زنبق الوادي، فانيليا، عنبر، مسك، نجيل الهند", type:"women", vector:[48,3,22,68,68,58,78,62,68,12,5,42] },
    { name:"Dolce & Gabbana Rose The One", notes:"جريب فروت وردي، يوسفي، كشمش أسود، ورد، بيوني، زنبق الوادي، ليتشي، فانيليا، مسك، صندل", type:"women", vector:[58,5,22,55,48,52,78,55,62,5,15,32] },
    { name:"Dolce & Gabbana The One Desire", notes:"ليتشي، يوسفي، برغموت، زنبق الوادي، توبروز، كراميل، فانيليا، عنبر، صندل", type:"women", vector:[45,2,18,78,72,65,75,72,72,8,3,48] },
    { name:"Dolce & Gabbana Pour Femme", notes:"توت العليق، نيرولي، يوسفي، زهر البرتقال، ياسمين، مارشملو، فانيليا، صندل، هيليوتروب", type:"women", vector:[48,2,15,85,72,55,68,72,68,5,3,35] },
    { name:"Dolce & Gabbana Light Blue Pour Femme", notes:"ليمون صقلي، تفاح، أرز، زهرة الجرس، خيزران، ياسمين، ورد أبيض، مسك، عنبر", type:"women", vector:[88,45,32,25,22,35,68,55,52,3,42,15] },
    { name:"Dolce & Gabbana The One Mysterious Night", notes:"زعفران، جريب فروت، ورد، عود، مريمية، عنبر، أخشاب ثمينة، تونكا، أوبوبوناكس", type:"women", vector:[32,2,72,38,78,82,82,75,85,62,5,85] },
    { name:"Dsquared2 Wood for Her", notes:"أوراق التوت العليق، يوسفي، ماغنوليا، زنبق الوادي، أوسمانثوس، ياسمين، أخشاب بيضاء، أرز، أمبروكسان", type:"women", vector:[62,8,62,35,32,48,72,55,58,3,42,32] },
    { name:"Escada Magnetism", notes:"توت أحمر، كشمش أسود، ليتشي، أناناس، بطيخ، أوراق خضراء، فريزيا، ريحان، ياسمين، سوسن، ورد، فانيليا، كراميل، عنبر، باتشولي، مسك، صندل", type:"women", vector:[55,5,22,75,68,62,62,68,68,12,32,42] },
    { name:"Escada Rockin' Rio", notes:"بابايا، أناناس، يوسفي، خوخ، بينا كولادا، قصب السكر، جوز الهند، مسك، صندل", type:"women", vector:[72,18,8,72,48,35,42,55,48,3,15,15] },
    { name:"Escada Cherry in the Air", notes:"كرز حامض، توت العليق، يوسفي، مارشملو، فانيليا، أوركيد، غاردينيا، صندل، مسك، بلوط، جلد أبيض", type:"women", vector:[55,5,15,82,55,42,48,58,52,3,8,22] },
    { name:"Escada Collection", notes:"برقوق، كراميل، ياسمين، زهر البرتقال، أزهار بيضاء، تونكا، صندل، عنبر، أرز", type:"women", vector:[42,2,28,78,75,62,65,65,68,12,3,45] },
    { name:"Escada Moon Sparkle", notes:"فراولة، كشمش أسود، تفاح أحمر، حمضيات، بازلاء حلوة، فريزيا، ياسمين، ورد، توت العليق، مسك، صندل، عنبر", type:"women", vector:[62,8,12,72,48,42,52,58,52,5,15,22] },
    { name:"Escada Signature", notes:"خيار، برغموت، كشمش أسود، ليمون، فريزيا، ماغنوليا، ياسمين، ورد، زنبق الوادي، مسك، نكتارين، عنبر، باتشولي، فانيليا", type:"women", vector:[75,22,15,42,38,48,68,52,55,3,42,25] },
    { name:"Escada Taj Sunset", notes:"مانجو، نكتارين، برتقال أحمر، توت العليق، زنبق الماء، لوتس، جوز الهند، مسك، صندل", type:"women", vector:[68,15,10,68,48,38,48,58,52,3,12,18] },
    { name:"Elie Saab Le Parfum", notes:"زهر البرتقال الأفريقي، ياسمين سامباك، عسل، باتشولي، ورد، أرز", type:"women", vector:[48,2,32,62,58,62,88,68,72,5,15,42] },
    { name:"Givenchy Very Irresistible", notes:"أوراق الكشمش، لويزة، يانسون نجمي، ورد، بيوني، ماغنوليا، ورد طائفي", type:"women", vector:[58,5,15,45,42,48,75,55,58,22,32,28] },
    { name:"Givenchy Hot Couture", notes:"توت العليق، برغموت، برتقال، فلفل أسود، نجيل الهند، ماغنوليا، صندل، عنبر، مسك", type:"women", vector:[48,2,32,62,62,55,68,62,62,42,5,42] },
    { name:"Moschino Fresh Couture", notes:"برغموت، يوسفي، يلانغ يلانغ، بيوني، توت العليق، باتشولي أبيض، أمبروكسان، أخشاب، أرز", type:"women", vector:[78,22,32,35,28,38,68,55,52,3,32,22] },
    { name:"Givenchy Very Irresistible Electrique Rose", notes:"توت أزرق، ليمون، ريحان، لويزة، ورد، يانسون، أوراق البنفسج، أرز، مسك", type:"women", vector:[68,8,28,42,32,42,68,55,55,12,42,25] },
    { name:"Emporio Armani Lei / Elle", notes:"ليمون، توبروز، برغموت، كمثرى، أناناس، يوسفي، هيليوتروب، جذور السوسن، ياسمين، زنبق الوادي، صندل، فانيليا، أرز، مسك، تونكا", type:"women", vector:[68,8,28,42,38,48,78,55,58,3,22,32] },
    { name:"Armani Sì Rose Signature", notes:"ورد مايو، ورد جوري، برغموت، يوسفي، فريزيا، كشمش أسود، سوسن، أوسمانثوس، فانيليا، باتشولي، أمبريت", type:"women", vector:[58,5,28,48,52,58,85,62,68,5,22,42] },
    { name:"Armani Sì", notes:"براعم الكشمش الأسود، ورد مايو، فريزيا، فانيليا، باتشولي، أخشاب، أمبروكسان", type:"women", vector:[52,3,35,45,52,62,88,68,72,5,22,48] },
    { name:"Armani Privé Rouge Malachite", notes:"توبروز، مريمية، فلفل وردي، زهر البرتقال، يلانغ يلانغ، ياسمين، كشميران، عنبر", type:"women", vector:[42,2,28,55,68,72,88,78,82,32,12,58] },
    { name:"Flora by Gucci", notes:"بيوني، حمضيات، يوسفي، ورد، أوسمانثوس، صندل، باتشولي، فلفل وردي", type:"women", vector:[62,5,28,48,38,48,78,55,58,22,22,32] },
    { name:"Gucci Guilty Pour Femme", notes:"فلفل وردي، يوسفي، برغموت، ليلك، خوخ، إبرة الراعي، ياسمين، كشمش أسود، باتشولي، عنبر، مسك أبيض، فانيليا", type:"women", vector:[52,3,22,55,58,58,78,65,68,28,15,42] },
    { name:"Gucci Première", notes:"برغموت، زهر البرتقال، زهور بيضاء، مسك، جلود، نوتات خشبية", type:"women", vector:[52,2,42,38,52,62,85,62,65,8,8,52] },
    { name:"Gucci Rush", notes:"خوخ، غاردينيا كاليفورنيا، فريزيا أفريقية، كزبرة، ورد جوري، ياسمين، باتشولي، فانيليا، نجيل الهند", type:"women", vector:[45,2,22,65,62,62,68,72,72,18,8,48] },
    { name:"Guerlain La Petite Robe Noire", notes:"كرز حامض، لوز، توت أحمر، برغموت، عرقسوس، ورد، ورد طائفي، شاي، فانيليا، تونكا، يانسون، باتشولي، سوسن", type:"women", vector:[38,2,22,85,72,68,72,78,82,25,5,55] },
    { name:"Guerlain Mon Guerlain", notes:"لافندر، برغموت، ياسمين سامباك، سوسن، ورد، فانيليا تاهيتي، كومارين، صندل أسترالي، جاوي", type:"women", vector:[48,2,38,55,62,62,88,65,72,8,32,48] },
    { name:"Guerlain Insolence", notes:"بنفسج، توت العليق، توت أحمر، برغموت، ورد، زهر البرتقال، سوسن، تونكا، صموغ، صندل، مسك", type:"women", vector:[42,2,18,72,52,55,78,62,65,5,12,38] },
    { name:"Guerlain Shalimar", notes:"حمضيات، برغموت، ليمون، أرز، يوسفي، سوسن، باتشولي، نجيل الهند، ياسمين، ورد، فانيليا، بخور، جلد، أوبوبوناكس، صندل", type:"women", vector:[32,2,42,62,78,82,88,72,82,25,8,68] },
    { name:"Hugo Boss Hugo Woman", notes:"تفاح أخضر، سيكلامين، شمام، بابايا، خوخ، ياسمين الماء، زنبق، سوسن، أرز فيرجيني، صندل، فانيليا، عنبر", type:"women", vector:[72,18,22,55,38,42,58,55,52,3,32,22] },
    { name:"Hugo Boss Boss Woman", notes:"مانجو، يوسفي، فريزيا، جذور البنفسج، أرز أبيض، صندل", type:"women", vector:[72,12,28,48,32,38,58,48,45,3,22,18] },
    { name:"Hugo Boss Boss Orange Woman", notes:"تفاح أحمر، زهور بيضاء، زهر البرتقال الأفريقي، فانيليا، صندل، شجر الزيتون", type:"women", vector:[58,5,22,62,55,45,52,55,52,3,12,25] },
    { name:"Issey Miyake L'Eau d'Issey Pure Pétale de Nectar", notes:"عسل، كمثرى، ورد، كشميران، عنبر، صندل", type:"women", vector:[48,5,28,72,62,55,72,58,62,3,8,35] },
    { name:"I Am Juicy Couture", notes:"باشن فروت، توت العليق، جريب فروت، غاردينيا، بازلاء حلوة، هيليوتروب، ورد، عنبر، خشب الكشمير، مسك", type:"women", vector:[55,5,22,78,62,52,62,68,65,5,8,32] },
    { name:"Viva La Juicy Bowdacious", notes:"حليب جوز الهند، شمام، كمثرى، زهرة التياري، زنبق أبيض، ياسمين، تونكا، أخشاب طافية", type:"women", vector:[58,15,15,72,55,45,52,62,58,3,8,25] },
    { name:"Jimmy Choo Illicit", notes:"زنجبيل، برتقال مر، ورد، ياسمين سامباك، زهر البرتقال، عسل، كراميل، عنبر، فانيليا، صندل، كشمير", type:"women", vector:[42,2,22,78,72,62,68,72,75,32,3,45] },
    { name:"Kenzo World", notes:"فواكه حمراء، بيوني، نوتات زهرية، ياسمين مصري، أمبروكسان", type:"women", vector:[58,8,15,55,42,42,72,62,58,3,12,32] },
    { name:"Aqua Kenzo Pour Femme", notes:"أوراق التوت العليق، ماندارين، حمضيات، ماغنوليا، ورد، ياسمين، نوتات خضراء، نجيل الهند، فانيليا، خشب الكشمير، صندل، باتشولي", type:"women", vector:[75,35,28,42,38,48,72,52,55,3,42,28] },
    { name:"Lacoste Love of Pink", notes:"باشن فروت، برتقال أحمر، ليمون، ماغنوليا وردية، ستيفانوتيس، فانيليا، أرز، مسك", type:"women", vector:[75,12,22,52,35,38,58,48,45,3,22,18] },
    { name:"Eau de Lacoste Pour Femme", notes:"أناناس، يوسفي، برغموت، أوراق الأناناس، ياسمين سامباك، زهر البرتقال، فانيليا، صندل، بلسم بيرو، نجيل الهند", type:"women", vector:[72,8,28,48,42,48,68,55,58,3,22,28] }
  ],

  unisex: []

};

let selectedCatalog = "men";

function setCatalog(type){
  if(!CATALOGS[type]) return;
  selectedCatalog = type;
  document.querySelectorAll(".catalogPill").forEach(function(p){
    p.classList.toggle("active", p.getAttribute("data-catalog") === type);
  });
  document.body.classList.remove("women","unisex");
  if(type === "women") document.body.classList.add("women");
  if(type === "unisex") document.body.classList.add("unisex");
}

function getAllPerfumes(){
  return CATALOGS[selectedCatalog] || [];
}


/* =========================================================
   INTERNAL DIMENSIONS
   ========================================================= */

const DIM = [
  "الانتعاش","المائية","الخشبية","الحلاوة","الدفء","العمق",
  "الأناقة","الحضور","الثبات","البهارية","الخضرة","الغموض"
];


/* =========================================================
   MEN SHARED QUESTION VECTORS
   ========================================================= */

const atmosphereOptions = [
["البحر والهواء المفتوح",[20,30,-5,-5,-5,-5,4,0,0,0,5,-2]],
["الغابة والأرض والخشب",[-5,0,25,-5,8,18,3,0,3,0,20,10]],
["مدينة أنيقة ومرتبة",[8,0,5,0,0,4,22,10,5,0,5,4]],
["مكتبة قديمة وهادئة",[-10,0,15,0,5,25,20,0,5,0,3,22]],
["مكان فاخر ودافئ",[-8,0,8,20,22,20,18,15,12,5,0,12]],
["ليل هادئ وغامض",[-15,0,10,5,15,25,12,5,8,5,0,28]],
["مقهى هادئ في مساء بارد",[-3,0,3,8,16,12,12,5,6,5,2,12]],
["طريق مفتوح وهواء نقي",[15,8,5,0,0,4,5,4,2,0,12,2]]
];

const scentOptions = [
["النقود والأوراق النقدية",[0,0,10,0,5,12,5,4,4,0,0,12]],
["الكتب والورق والحبر",[-4,0,10,0,3,18,14,0,3,0,0,18]],
["الخشب والجلد",[0,0,24,0,10,16,8,3,7,2,4,15]],
["المطر والتراب المبلل",[8,12,5,0,3,7,2,0,2,0,12,8]],
["القهوة والشاي",[0,0,2,8,12,8,7,3,4,8,3,5]],
["البخور والدخان",[0,0,12,3,18,22,8,8,8,15,0,20]],
["الصابون والملابس النظيفة",[14,4,0,0,-2,-3,10,0,2,0,5,-2]],
["البحر والملح والهواء",[8,18,0,0,0,0,4,0,0,0,5,0]],
["الحبر والجلد في ورشة قديمة",[-2,0,16,0,8,20,7,4,7,3,2,20]],
["رائحة سيارة أو مرآب بعد المطر",[-3,0,12,0,8,18,3,7,5,4,0,17]],
["الخبز والحلويات الدافئة",[0,0,0,24,20,8,2,5,5,3,0,3]],
["الملابس القطنية بعد الغسيل",[16,3,0,0,-3,-3,8,0,3,0,5,0]],
["لا شيء من هذه",[0,0,0,0,0,0,0,0,0,0,0,0]]
];

const soundOptions = [
["المطر على النافذة",[5,10,0,0,3,7,0,0,0,0,8,5]],
["أمواج البحر",[5,18,0,0,0,0,2,0,0,0,5,0]],
["صوت النار",[0,0,5,3,15,12,0,5,4,4,0,8]],
["خشخشة الورق",[0,0,6,0,2,10,8,0,2,0,0,10]],
["القطار والمدينة",[3,0,3,0,4,5,4,6,2,2,0,5]],
["أصوات الطبيعة والغابة",[8,8,5,0,2,5,2,0,0,0,15,5]],
["الهدوء التام",[0,0,0,0,0,10,8,0,2,0,2,15]],
["صوت المطر الغزير والرعد",[2,8,3,0,7,15,0,5,4,2,5,18]],
["حركة المدينة ليلاً",[0,0,4,2,7,10,5,10,3,4,0,12]],
["صوت البحر مع الريح",[8,16,0,0,2,5,3,3,1,0,5,7]]
];

const musicOptions = [
["كلاسيكية",[0,0,5,0,4,12,15,2,5,0,2,10]],
["Jazz",[0,0,5,4,8,10,15,5,5,4,2,12]],
["موسيقى سينمائية",[0,0,8,3,8,18,10,12,7,4,0,18]],
["Ambient وهادئة",[3,4,0,0,0,15,8,0,2,0,4,15]],
["Rock",[0,0,10,0,8,8,2,18,8,10,0,5]],
["إلكترونية",[5,4,2,5,6,8,5,18,6,5,0,8]],
["موسيقى عربية تقليدية",[0,0,7,5,10,12,10,5,5,8,3,12]],
["Rap / Hip-Hop",[0,0,2,5,8,7,3,18,6,5,0,5]],
["Blues",[0,0,7,4,9,15,10,5,5,3,2,18]],
["Soul / R&B",[0,0,2,10,14,9,10,8,7,4,0,9]],
["موسيقى شعبية / Chaabi",[0,0,4,8,12,7,5,12,5,7,3,4]],
["موسيقى صوفية / روحانية",[0,0,8,2,10,20,10,4,6,4,4,24]]
];

const feelingOptions = [
["انتعاش ونظافة",[20,8,0,-3,-3,-5,5,2,0,0,5,-2]],
["هدوء وأناقة",[0,0,3,0,2,5,18,2,3,0,2,7]],
["دفء وراحة",[-3,0,2,14,20,12,5,5,8,4,0,4]],
["قوة وحضور",[-3,0,3,2,10,7,5,25,15,8,0,5]],
["غموض وعمق",[-8,0,8,5,12,22,8,8,8,5,0,28]],
["اختلاف وتميز",[0,0,8,5,8,15,8,14,7,5,0,20]]
];

const presenceOptions = [
["يبقى قريباً مني",[0,0,0,0,0,2,5,-18,-3,0,0,2]],
["يُلاحظ بلطف",[0,0,0,0,2,2,5,2,3,0,0,2]],
["يترك أثراً بعد مروري",[0,0,0,0,5,5,4,18,12,2,0,5]],
["له حضور واضح ولا يُنسى",[0,0,0,0,8,8,4,28,18,4,0,8]]
];

const familyOptions = [
["منعشة ونظيفة",[18,7,0,0,-3,-4,5,2,0,0,6,0]],
["مائية وباردة",[8,25,0,0,-3,-3,4,3,0,0,3,0]],
["خضراء وطبيعية",[5,4,8,0,0,3,4,0,2,0,24,3]],
["خشبية وجافة",[-2,0,28,-4,5,18,10,4,8,3,3,15]],
["دافئة وحلوة",[-5,0,0,25,25,12,5,10,10,8,0,5]],
["شرقية وعميقة",[-10,0,18,8,20,28,12,12,15,12,0,30]]
];

const balanceOptions = [
["نظيف وخفيف",[20,8,0,0,-8,-10,3,0,0,0,5,-4]],
["متوازن",[5,3,5,4,5,5,8,5,5,3,3,5]],
["عميق وثقيل",[-15,0,18,8,22,28,10,12,15,10,0,28]]
];

const textureOptions = [
["جاف وخشبي",[0,0,25,-5,4,15,6,3,7,2,3,15]],
["ناعم وكريمي",[0,0,0,18,15,7,5,5,6,2,0,5]],
["بين الاثنين",[0,0,8,8,8,8,8,5,5,2,0,8]]
];

const discoveryOptions = [
["أريد شيئاً أعرف أنه يناسبني",[0,0,0,0,0,0,8,0,4,0,0,2]],
["أحب التوازن بين المألوف والجديد",[0,0,3,3,3,5,8,5,5,2,0,8]],
["أحب تجربة شيء جديد",[0,0,8,5,5,12,5,10,5,4,0,15]],
["أبحث عن شيء لا يشبه المعتاد",[0,0,12,7,8,18,5,16,8,6,0,25]]
];

const imageOptions = [
["نظيف ومرتب",[12,3,0,0,0,-2,10,2,2,0,5,0]],
["هادئ وراقٍ",[0,0,4,0,2,7,20,3,5,0,2,8]],
["واثق وحاضر",[0,0,5,3,8,6,10,22,12,6,0,5]],
["دافئ وجذاب",[0,0,0,15,18,8,5,12,10,5,0,5]],
["غامض ومثير للاهتمام",[0,0,8,5,10,20,8,8,8,5,0,25]],
["مختلف عن المعتاد",[0,0,10,7,8,15,6,14,7,5,0,22]]
];

const messageOptions = [
["هذا يشبهني تماماً",[0,0,0,0,0,5,8,3,3,0,0,8]],
["هذا هو الجانب الذي أريد إظهاره",[0,0,3,3,6,7,10,12,7,2,0,12]],
["أريد عطراً له حضور",[0,0,3,2,8,7,8,24,15,5,0,8]],
["أريد شيئاً مختلفاً عن المعتاد",[0,0,10,5,8,16,6,15,8,5,0,24]]
];


/* =========================================================
   WOMEN OPTION VECTORS
   ========================================================= */

const womenAtmosphereOptions = [
["صباح مشمس وحديقة مليئة بالحياة",[18,5,-3,8,3,0,8,3,0,0,20,-5]],
["شاطئ هادئ ونسمة مالحة",[10,25,-5,0,3,3,8,0,0,0,3,0]],
["مقهى أنيق ومزدحم قليلًا",[3,0,5,8,10,8,15,12,5,3,0,5]],
["بيت دافئ وإضاءة خافتة",[-8,0,5,15,22,15,8,0,8,3,0,12]],
["شارع ليلي مليء بالأضواء",[-5,0,3,3,10,15,8,20,8,3,0,18]],
["فندق فاخر في مساء هادئ",[-8,0,8,8,10,15,25,8,10,3,0,18]],
["مكان أخضر بعد نزول المطر",[15,12,3,0,3,5,3,0,0,0,25,3]],
["سوق قديم مليء بالتفاصيل والروائح",[-8,0,8,8,18,22,5,8,8,22,5,18]]
];

const womenScentOptions = [
["وردة قُطفت للتو",[3,0,3,8,8,8,20,5,5,0,5,3]],
["فاكهة ناضجة وحلوة",[12,3,0,22,8,3,5,8,5,0,3,0]],
["قهوة وحلوى في مكان دافئ",[-3,0,0,22,20,12,5,5,8,8,0,5]],
["ملابس نظيفة خرجت من الخزانة",[20,3,0,0,-3,-5,10,0,2,0,5,-3]],
["خشب جديد وأثاث أنيق",[-5,0,22,0,8,15,15,5,8,3,0,8]],
["كتاب قديم وورق",[-8,0,12,0,8,20,15,0,5,0,3,15]],
["بخور أو دخان خفيف",[-10,0,8,3,15,22,8,8,10,15,0,22]],
["جلد وحقيبة أو مقعد جديد",[-5,0,18,3,12,18,12,8,10,5,0,18]],
["مطر وتراب مبلل",[12,15,3,0,3,5,3,0,0,0,20,5]],
["شامبو أو صابون نظيف",[22,8,0,0,-3,-5,8,0,0,0,3,-3]],
["كريمة أو فانيلا وحلوى",[-5,0,0,25,22,10,5,8,10,3,0,3]],
["هواء البحر",[10,25,-5,0,0,3,5,0,0,0,3,0]]
];

const womenExpressionOptions = [
["هدوء وثقة",[0,0,3,3,5,10,18,8,8,0,0,8]],
["حيوية ومرح",[18,8,0,12,3,0,5,12,5,0,8,-3]],
["دفء وقرب",[-3,0,3,12,20,8,5,5,8,3,0,0]],
["أناقة ورقي",[-5,0,8,5,5,15,25,8,10,0,0,8]],
["قوة وحضور",[-3,0,5,3,10,12,8,25,15,5,0,10]],
["غموض يثير الفضول",[-8,0,8,3,10,22,10,12,10,5,0,28]],
["نعومة ورقة",[5,0,0,15,8,5,12,0,3,0,3,3]],
["اختلاف لا يشبه الآخرين",[-3,0,10,5,8,15,8,15,8,5,0,22]]
];

const womenImpactOptions = [
["لا يكاد يُلاحظ إلا من يقترب",[0,0,0,0,3,3,8,-20,-3,0,0,5]],
["لمسة جميلة يلاحظها من حولي",[0,0,0,3,3,3,8,2,3,0,0,3]],
["أثر واضح للحظات",[0,0,0,3,5,5,5,18,10,3,0,5]],
["حضور يبقى في الذاكرة",[0,0,0,5,10,12,8,28,22,5,0,15]]
];

const womenMoodOptions = [
["خفيفة ومنتعشة",[22,12,-3,3,-3,-5,5,3,0,0,5,-3]],
["هادئة ومتزنة",[0,0,5,3,5,8,15,3,5,0,3,8]],
["دافئة ومريحة",[-5,0,3,12,22,10,5,5,8,3,0,3]],
["مرحة ومفعمة بالحياة",[15,5,0,12,5,0,5,12,5,0,8,-3]],
["أنيقة وواثقة",[-3,0,5,5,5,10,22,15,10,0,0,8]],
["عميقة وغامضة",[-10,0,10,5,12,25,10,10,12,5,0,28]]
];

const womenFinalChoiceOptions = [
["«هكذا أحب أن أشعر.»",[0,0,0,3,5,5,5,3,3,0,0,5]],
["«هذا يشبهني فعلًا.»",[0,0,3,3,3,8,8,3,5,0,0,8]],
["«أريد أن يلاحظني الآخرون.»",[0,0,0,3,5,5,8,22,12,3,0,3]],
["«أريد أن يكتشفني الآخرون تدريجيًا.»",[-3,0,5,3,8,15,10,5,8,3,0,18]],
["«لا أريد شيئًا يشبه المعتاد.»",[0,0,8,5,8,15,5,12,8,5,0,22]],
["«أريد شيئًا أعود إليه دائمًا.»",[0,0,3,8,10,8,10,5,8,0,0,5]]
];

const womenDeepPlaceOptions = [
["حديقة في الصباح",[15,3,-3,5,3,0,8,3,0,0,18,-3]],
["بحر وسماء مفتوحة",[8,28,-5,0,3,3,5,0,0,0,3,0]],
["مدينة أنيقة",[3,0,5,8,8,8,18,12,5,3,0,5]],
["بيت دافئ وهادئ",[-8,0,5,12,22,12,8,0,8,3,0,10]],
["ليلة مليئة بالأضواء",[-5,0,3,3,10,18,10,22,10,3,0,18]],
["مكان قديم له شخصية",[-8,0,10,5,15,22,10,5,8,12,3,22]],
["طريق أخضر بعد المطر",[15,12,3,0,3,5,3,0,0,0,25,3]],
["مكان فاخر بإضاءة خافتة",[-8,0,8,8,10,18,25,10,10,3,0,20]]
];

const womenDeepMemoryOptions = [
["زهور طازجة",[3,0,3,10,8,8,20,5,5,0,5,3]],
["فواكه ناضجة",[12,3,0,22,8,3,5,8,5,0,3,0]],
["حلويات أو مخبوزات",[-3,0,0,22,20,10,5,8,8,3,0,3]],
["قهوة أو مشروب دافئ",[-3,0,0,18,20,12,5,5,8,8,0,5]],
["ملابس نظيفة",[20,3,0,0,-3,-5,10,0,2,0,5,-3]],
["خشب وكتب",[-8,0,20,0,8,18,15,0,5,3,0,15]],
["مطر وتراب",[12,15,3,0,3,5,3,0,0,0,20,5]],
["بخور ودخان",[-10,0,8,3,15,22,8,8,10,15,0,22]],
["جلد",[-5,0,18,3,12,18,12,8,10,5,0,18]],
["بحر وهواء مالح",[10,25,-5,0,0,3,5,0,0,0,3,0]]
];

const womenDeepDetailOptions = [
["البساطة",[10,3,0,0,3,-3,10,-3,0,0,5,-3]],
["الحيوية",[18,8,0,8,3,0,5,12,5,0,8,-3]],
["الأناقة",[-3,0,5,3,3,12,25,8,10,0,0,8]],
["الدفء",[-5,0,3,12,22,10,5,5,8,3,0,3]],
["القوة",[-5,0,8,3,10,15,10,22,15,5,0,12]],
["الغموض",[-10,0,8,3,10,25,12,10,12,5,0,28]],
["التفاصيل غير المعتادة",[-3,0,10,5,8,15,8,12,8,8,0,22]]
];

const womenDeepContrastOptions = [
["ناعم لكن واثق",[5,0,0,12,8,8,15,12,8,0,3,5]],
["حلو لكن غامض",[-5,0,3,20,12,15,10,10,12,3,0,22]],
["منعش لكن دافئ",[15,8,0,8,15,5,8,8,5,0,5,3]],
["أنيق لكن جريء",[-5,0,8,5,8,12,20,20,12,5,0,12]],
["رقيق لكن حاضر",[3,0,0,12,5,5,12,15,8,0,3,5]],
["مألوف لكن غير متوقع",[0,0,5,8,8,12,8,12,8,5,0,15]]
];

const womenDeepFeelingOptions = [
["انتعاش",[22,10,-3,0,-3,-3,5,3,0,0,5,-3]],
["راحة",[-3,0,3,10,18,8,10,0,5,3,0,3]],
["نعومة",[3,0,0,15,8,5,12,0,3,0,3,3]],
["ثقة",[-3,0,5,3,8,10,15,22,12,3,0,8]],
["جاذبية",[-8,0,5,8,12,15,10,18,12,3,0,22]],
["أناقة",[-5,0,5,3,3,10,25,10,10,0,0,8]],
["دفء",[-5,0,3,12,22,10,5,5,8,3,0,3]],
["غموض",[-10,0,8,3,10,25,10,8,10,5,0,28]],
["حيوية",[18,5,0,10,3,0,5,12,5,0,8,-3]]
];

const womenDeepPresenceOptions = [
["يبقى لي وحدي تقريبًا",[0,0,0,0,3,3,8,-22,-5,0,0,3]],
["يشعر به من يقترب",[0,0,0,0,3,3,8,-8,-3,0,0,3]],
["يلاحظه من حولي",[0,0,0,3,3,3,8,8,5,0,0,3]],
["يسبقني قليلًا",[0,0,0,3,5,5,8,20,12,3,0,8]],
["يبقى بعد مغادرتي",[0,0,0,5,8,8,5,25,22,3,0,12]]
];

const womenDeepSweetnessOptions = [
["فاكهة ناضجة ومنعشة",[15,5,0,22,5,0,5,8,5,0,3,0]],
["حلوى ناعمة",[-3,0,0,22,12,5,5,8,5,0,0,3]],
["فانيلا وكريمة",[-5,0,0,25,20,12,5,8,12,3,0,5]],
["كراميل وشوكولاتة",[-8,0,3,25,22,15,5,12,15,5,0,8]],
["لمسة حلوة فقط دون أن تطغى",[3,0,5,8,5,5,12,3,5,0,3,5]],
["لا أحب الحلاوة كثيرًا",[5,3,10,-12,-3,8,12,0,5,3,5,12]]
];

const womenDeepFloralOptions = [
["خفة ونضارة",[18,5,-3,8,-3,-3,12,3,0,0,8,-3]],
["نعومة ورقة",[5,0,0,12,8,5,15,0,3,0,3,3]],
["أناقة واضحة",[-3,0,5,5,3,10,25,10,10,0,0,8]],
["دفء وحميمية",[-3,0,0,12,20,12,10,5,8,3,0,5]],
["حضور فاخر",[-8,0,5,8,10,18,22,20,15,3,0,15]],
["غموض وإغراء",[-8,0,8,8,12,22,15,15,12,5,0,28]]
];

const womenDeepTextureOptions = [
["قماش قطني نظيف",[18,3,0,3,0,-3,8,0,3,0,5,-3]],
["حرير ناعم",[3,0,0,15,8,8,18,5,5,0,0,8]],
["كريم دافئ",[-3,0,0,20,20,8,8,8,8,3,0,5]],
["خشب مصقول",[-5,0,25,0,5,12,15,5,8,3,0,8]],
["جلد ناعم",[-5,0,15,3,15,18,12,10,12,5,0,18]],
["هواء بارد",[18,18,-5,0,-5,3,5,3,0,0,8,3]],
["مسحوق ناعم",[8,0,0,15,8,5,15,-3,3,0,0,5]],
["شيء داكن وثقيل",[-10,0,12,5,15,25,10,15,15,8,0,28]]
];

const womenDeepFamiliarityOptions = [
["أريد شيئًا قريبًا منه",[0,0,0,0,0,0,8,0,5,0,0,2]],
["أبحث عن نسخة مختلفة قليلًا",[0,0,3,3,3,5,8,5,5,2,0,8]],
["أبحث عن شيء أكثر جرأة",[-3,0,5,5,5,10,8,12,8,5,0,15]],
["أريد أن أفاجئ نفسي",[-3,0,8,5,5,12,5,12,5,5,0,18]],
["أترك المألوف وأجرب شيئًا لا أعرفه",[-5,0,12,5,8,18,5,15,8,8,0,25]]
];

const womenDeepImageOptions = [
["هادئة وراقية",[3,0,3,3,5,8,22,3,5,0,0,8]],
["مشرقة وحيوية",[18,8,0,12,5,0,5,15,5,0,8,-3]],
["ناعمة وقريبة",[3,0,0,12,12,5,10,0,3,0,3,3]],
["واثقة وجذابة",[-3,0,5,8,10,12,15,22,12,3,0,12]],
["دافئة ومريحة",[-3,0,3,12,22,10,8,3,5,3,0,3]],
["غامضة ولا تُقرأ بسهولة",[-8,0,8,5,10,22,12,10,10,5,0,28]],
["مختلفة ولا تشبه الآخرين",[-3,0,10,5,8,15,8,15,8,5,0,22]]
];

const womenDeepFingerprintOptions = [
["الإحساس الذي يمنحني إياه",[0,0,0,3,8,8,8,3,3,0,0,8]],
["الطريقة التي يجعلني أبدو بها",[-3,0,0,3,5,5,10,18,10,0,0,5]],
["الذكرى التي يتركها",[-3,0,5,5,10,15,10,8,10,3,0,18]],
["الأثر الذي يتركه في الآخرين",[0,0,0,3,5,8,5,22,15,0,0,8]],
["إحساس أنه «هذا عطري أنا»",[0,0,5,5,5,10,12,8,10,0,0,12]],
["عنصر المفاجأة والاختلاف",[0,0,10,5,8,15,5,15,8,5,0,25]]
];


/* =========================================================
   QUESTIONS
   ========================================================= */

function makeQ(title,question,hint,type,max,options){
  return {title,question,hint,type,max,options};
}


const quickQuestions = [
makeQ("الأجواء","أي أجواء تجذبك من النظرة الأولى؟","اختر حتى أربعة أجواء تشعر أنك تريد الدخول إليها.","multi",4,atmosphereOptions),
makeQ("الروائح","أي روائح من الحياة اليومية تجد فيها شيئاً جميلاً؟","اختر حتى أربعة. ليست هناك إجابة صحيحة.","multi",4,scentOptions),
makeQ("الإحساس","ما الإحساس الذي تبحث عنه أكثر في العطر؟","اختر حتى اثنين.","multi",2,feelingOptions),
makeQ("الحضور","كيف تحب أن يُلاحظ عطرك؟","فكّر في الأثر الذي تريد أن يتركه العطر.","single",1,presenceOptions),
makeQ("الصورة","ما الصورة التي تريد أن يتركها عطرك؟","اختر حتى اثنين.","multi",2,imageOptions),
makeQ("الرسالة","لو كان عطرك رسالة عنك، ماذا تريد أن يقول؟","اختر الجملة التي تشعر أنها الأقرب.","single",1,messageOptions)
];


const deepQuestions = [
makeQ("الأجواء","لو استطعت أن تنتقل الآن إلى أي أجواء، ماذا تختار؟","اختر حتى أربعة أجواء تجذبك تلقائياً.","multi",4,atmosphereOptions),
makeQ("الروائح","أي روائح من الحياة اليومية تجد فيها شيئاً جميلاً؟","اختر حتى أربعة. هذه ليست عطوراً؛ إنها إشارات إلى ذوقك الحسي.","multi",4,scentOptions),
makeQ("الصوت","أي أصوات يمكن أن تجعلك تستمتع بالمكان أكثر؟","اختر حتى أربعة.","multi",4,soundOptions),
makeQ("الموسيقى","أي أجواء موسيقية أقرب إلى ذوقك؟","اختر حتى أربعة. لا تحتاج إلى التفكير كثيراً.","multi",4,musicOptions),
makeQ("الإحساس","أي إحساس تبحث عنه أكثر في العطر؟","يمكنك اختيار اثنين.","multi",2,feelingOptions),
makeQ("الحضور","إلى أي مدى تحب أن يصل عطرك إلى الآخرين؟","فكّر في الأثر الذي يتركه العطر في المكان.","single",1,presenceOptions),
makeQ("العائلة العطرية","أي عالم من الروائح يجذبك أكثر؟","اختر حتى اثنين.","multi",2,familyOptions),
makeQ("الميزان","إلى أي جهة تميل؟","اختر الاتجاه الأقرب إلى أنفك.","single",1,balanceOptions),
makeQ("الملمس","أي إحساس أقرب إلى أنفك؟","تخيل العطر على الورق، لا شكله.","single",1,textureOptions),
makeQ("الاكتشاف","عندما تختار عطراً، أين تجد نفسك؟","اختر الطريقة الأقرب إليك.","single",1,discoveryOptions),
makeQ("الصورة","ما الصورة التي تريد أن يتركها عطرك؟","اختر حتى اثنين.","multi",2,imageOptions),
makeQ("الرسالة","لو كان عطرك رسالة عنك، ماذا تريد أن يقول؟","اختر الجملة التي تشعر أنها الأقرب.","single",1,messageOptions)
];


const womenQuickQuestions = [

makeQ("الأجواء","حين تدخلين مكانًا لأول مرة، أي أجواء تشد انتباهك تلقائيًا؟","اختاري حتى ثلاثة.","multi",3,womenAtmosphereOptions),

makeQ("التفاصيل الحسية","أحيانًا تكون هناك رائحة بسيطة تجعل المكان أجمل. أيها أقرب إليك؟","اختاري حتى أربعة. هذه ليست عطوراً؛ إنها إشارات إلى حواسك.","multi",4,womenScentOptions),

makeQ("التعبير عن الذات","إذا أردتِ أن يلتقط شخص ما شيئًا من شخصيتك من دون أن تتكلمي، ماذا تفضلين أن يشعر؟","اختاري اثنين.","multi",2,womenExpressionOptions),

makeQ("الأثر","حين تغادرين مكانًا، أي أثر يعجبك أن يبقى منك؟","فكّري في الأثر الذي تريدين أن يتركه العطر.","single",1,womenImpactOptions),

makeQ("المزاج","أي حالة تشعرين أنها الأقرب إلى مزاجك حين تكونين على طبيعتك؟","اختاري اثنين.","multi",2,womenMoodOptions),

makeQ("الاختيار الأخير","لو كان عطرك لا يقول عنك إلا جملة واحدة، أي جملة تختارين؟","اختاري الجملة التي تشعرين أنها الأقرب.","single",1,womenFinalChoiceOptions)

];


const womenDeepQuestions = [

makeQ("المكان","لو استطعتِ أن تحتفظي بمشهد واحد حولك طوال اليوم، أي مشهد تختارين؟","اختاري حتى أربعة.","multi",4,womenDeepPlaceOptions),

makeQ("الذاكرة الحسية","أي رائحة يمكن أن تعيدك فورًا إلى لحظة جميلة؟","اختاري حتى أربعة. هذه ليست عطوراً؛ إنها ذكريات.","multi",4,womenDeepMemoryOptions),

makeQ("التفاصيل","حين تعجبك شخصية أو مكان، ما الذي يجذبك فيه أولًا؟","اختاري حتى اثنين.","multi",2,womenDeepDetailOptions),

makeQ("التناقض","أي تركيبة من هذه التناقضات تجدينها أكثر إثارة؟","اختاري اثنين. التناقضات تكشف الذوق أكثر من الإجابات المتوقعة.","multi",2,womenDeepContrastOptions),

makeQ("الإحساس","ما الإحساس الذي تريدين أن يمنحك إياه عطرك عندما تضعينه؟","اختاري اثنين.","multi",2,womenDeepFeelingOptions),

makeQ("الحضور","هل تريدين أن يكون عطرك جزءًا من مساحتك أم أن يدخل إلى مساحة الآخرين؟","اختاري ما يصف رغبتك الفعلية.","single",1,womenDeepPresenceOptions),

makeQ("الحلاوة","حين تدخل الحلاوة في شيء تحبينه، أي شكل منها يجذبك؟","اختاري اثنين.","multi",2,womenDeepSweetnessOptions),

makeQ("الجانب الزهري","عندما تكون الرائحة زهرية، أي إحساس تريدين أن تأتي به؟","اختاري اثنين.","multi",2,womenDeepFloralOptions),

makeQ("الملمس","لو كان عطرك شيئًا يمكنك لمسه، أي ملمس تتخيلينه؟","اختاري اثنين. تخيّلي الإحساس، لا الشكل.","multi",2,womenDeepTextureOptions),

makeQ("علاقتك بالمألوف","عندما تجدين عطرًا يعجبك، ماذا تفعلين عادة؟","اختاري ما يشبهك فعلاً.","single",1,womenDeepFamiliarityOptions),

makeQ("الصورة","أي صورة تشعرين أنها الأقرب إلى الطريقة التي تريدين أن يراك بها الآخرون؟","اختاري اثنين.","multi",2,womenDeepImageOptions),

makeQ("البصمة","لو اختفى اسم العطر وقارورته وكل ما يعرفه الناس عنه، ماذا تريدين أن يبقى منه؟","هذا آخر سؤال. اختاري الجملة التي تلمس جوهر ما تبحثين عنه.","single",1,womenDeepFingerprintOptions)

];


/* =========================================================
   STATE
   ========================================================= */

let mode = "quick";
let questions = quickQuestions;
let current = 0;
let answers = [];
let profile = Array(12).fill(50);


/* =========================================================
   SCREEN
   ========================================================= */

function showScreen(id){
  document.querySelectorAll(".screen").forEach(function(x){
    x.classList.remove("active");
  });
  document.getElementById(id).classList.add("active");
  window.scrollTo(0,0);
}


/* =========================================================
   START
   ========================================================= */

function startTest(selectedMode){

  mode = selectedMode;

  let bank;

  if(selectedCatalog === "women"){
    bank = (mode === "quick") ? womenQuickQuestions : womenDeepQuestions;
  }else{
    bank = (mode === "quick") ? quickQuestions : deepQuestions;
  }

  questions = bank;

  current = 0;

  answers = questions.map(function(){ return []; });

  profile = Array(12).fill(50);

  showScreen("quiz");

  renderQuestion();
}


/* =========================================================
   RENDER
   ========================================================= */

function renderQuestion(){

  const q = questions[current];

  document.getElementById("counter").textContent =
    String(current+1).padStart(2,"0") + " / " + String(questions.length).padStart(2,"0");

  document.getElementById("progressBar").style.width =
    ((current+1)/questions.length*100) + "%";

  document.getElementById("questionKicker").textContent = q.title;
  document.getElementById("question").textContent = q.question;
  document.getElementById("hint").textContent = q.hint || "";

  const selectionCounter = document.getElementById("selectionCounter");

  if(q.type === "multi"){
    const selected = answers[current].length;
    let dots = "";
    for(let i=0;i<q.max;i++){
      dots += '<span class="dot' + (i < selected ? " on" : "") + '"></span>';
    }
    selectionCounter.innerHTML =
      '<span>' + selected + ' / ' + q.max + '</span>' +
      '<span class="dots">' + dots + '</span>';
  }else{
    selectionCounter.textContent = "اختيار واحد";
  }

  const fadeGroup = document.getElementById("fadeGroup");
  fadeGroup.classList.remove("fadeGroup");
  void fadeGroup.offsetWidth;
  fadeGroup.classList.add("fadeGroup");

  const box = document.getElementById("options");
  box.innerHTML = "";

  q.options.forEach(function(opt,index){

    const btn = document.createElement("button");
    btn.type = "button";
    btn.className = "option";

    const check = document.createElement("span");
    check.className = "check";
    check.textContent = "✓";

    const text = document.createElement("span");
    text.textContent = opt[0];

    btn.appendChild(check);
    btn.appendChild(text);

    if(answers[current].includes(index)){
      btn.classList.add("selected");
    }

    btn.onclick = function(){
      selectOption(index);
    };

    box.appendChild(btn);
  });

  document.getElementById("backBtn").style.visibility =
    current === 0 ? "hidden" : "visible";

  updateNextButton();
}


/* =========================================================
   NOTHING OPTION DETECTION
   ========================================================= */

function isNothingOption(opt){
  const v = opt[1];
  for(let i=0;i<12;i++){
    if(v[i] !== 0) return false;
  }
  return true;
}


/* =========================================================
   SELECT
   ========================================================= */

function selectOption(index){

  const q = questions[current];
  const opt = q.options[index];
  const isNothing = isNothingOption(opt);

  if(q.type === "single"){

    answers[current] = [index];

  }else{

    let selected = answers[current].slice();

    if(isNothing){

      if(selected.includes(index)){
        selected = [];
      }else{
        selected = [index];
      }

    }else{

      if(selected.includes(index)){

        selected = selected.filter(function(x){ return x !== index; });

      }else{

        selected = selected.filter(function(x){
          return !isNothingOption(q.options[x]);
        });

        if(selected.length >= q.max){
          selected.shift();
        }

        selected.push(index);

      }

    }

    answers[current] = selected;

  }

  renderQuestion();
}


/* =========================================================
   NEXT BUTTON
   ========================================================= */

function updateNextButton(){
  const btn = document.getElementById("nextBtn");
  if(answers[current].length === 0){
    btn.disabled = true;
    btn.textContent = "اختر أولاً";
  }else{
    btn.disabled = false;
    btn.textContent =
      current === questions.length-1 ? "اكتشف بصمتك" : "التالي";
  }
}


/* =========================================================
   NAVIGATION
   ========================================================= */

function nextQuestion(){
  if(answers[current].length === 0){
    return;
  }
  if(current < questions.length-1){
    current++;
    renderQuestion();
  }else{
    calculateResult();
  }
}


function previousQuestion(){
  if(current > 0){
    current--;
    renderQuestion();
  }
}


/* =========================================================
   DYNAMIC BOUNDS
   ========================================================= */

function computeBounds(qs){

  const B = Array(12).fill(0);
  const UP = Array(12).fill(0);
  const DOWN = Array(12).fill(0);

  qs.forEach(function(q){

    for(let d=0;d<12;d++){

      let sum = 0;
      let count = 0;
      let maxVal = -Infinity;
      let minVal = Infinity;

      q.options.forEach(function(opt){

        if(isNothingOption(opt)) return;

        const v = opt[1][d];

        sum += v;
        count += 1;

        if(v > maxVal) maxVal = v;
        if(v < minVal) minVal = v;

      });

      if(count === 0) return;

      const avg = sum / count;

      B[d] += avg;
      UP[d] += maxVal;
      DOWN[d] += minVal;

    }

  });

  for(let d=0;d<12;d++){

    const upDelta = UP[d] - B[d];
    const downDelta = B[d] - DOWN[d];

    UP[d] = upDelta > 0.5 ? upDelta : 0.5;
    DOWN[d] = downDelta > 0.5 ? downDelta : 0.5;

  }

  return { B:B, UP:UP, DOWN:DOWN };
}


/* =========================================================
   PROFILE (MODEL C)
   ========================================================= */

function calculateResult(){

  const bounds = computeBounds(questions);

  const R = Array(12).fill(0);

  questions.forEach(function(q,questionIndex){

    const selected = answers[questionIndex];

    if(!selected.length){
      return;
    }

    const realSelected = selected.filter(function(i){
      return !isNothingOption(q.options[i]);
    });

    if(!realSelected.length){
      return;
    }

    const averaged = Array(12).fill(0);

    realSelected.forEach(function(i){
      const v = q.options[i][1];
      for(let d=0;d<12;d++){
        averaged[d] += v[d];
      }
    });

    for(let d=0;d<12;d++){
      averaged[d] = averaged[d] / realSelected.length;
      R[d] += averaged[d];
    }

  });

  profile = Array(12).fill(0);

  for(let d=0;d<12;d++){

    const delta = R[d] - bounds.B[d];

    let value;

    if(delta >= 0){
      value = 50 + 50 * delta / bounds.UP[d];
    }else{
      value = 50 + 50 * delta / bounds.DOWN[d];
    }

    profile[d] = Math.max(0, Math.min(100, value));

  }

  showResults();
}


/* =========================================================
   SIMILARITY
   ========================================================= */

function similarity(a,b){

  const weights = [1.15,.95,1.10,1.05,1.00,1.10,1.05,1.00,.90,.80,.90,1.10];

  let total = 0;
  let weight = 0;

  for(let i=0;i<12;i++){
    const diff = Math.abs(a[i]-b[i]);
    const sim = 100 - diff;
    total += sim * weights[i];
    weight += 100 * weights[i];
  }

  return (total / weight) * 100;
}


/* =========================================================
   RESULTS
   ========================================================= */

function showResults(){

  const catalog = getAllPerfumes();

  if(catalog.length === 0){

    document.getElementById("tags").innerHTML = "";

    document.getElementById("results").innerHTML =
      '<div class="emptyCatalog">' +
      'لا توجد عطور في هذا الكتالوج بعد.<br>' +
      'اختر كتالوجاً آخر أو عُد لاحقاً.' +
      '</div>';

    showScreen("result");
    return;
  }

  const scored = catalog.map(function(p){
    return {
      name:p.name,
      notes:p.notes,
      vector:p.vector,
      score:similarity(profile,p.vector)
    };
  });

  scored.sort(function(a,b){ return b.score - a.score; });

  const top = scored.slice(0,3);

  document.getElementById("tags").innerHTML =
    buildTags().map(function(x){
      return '<span class="tag">' + escapeHTML(x) + '</span>';
    }).join("");

  document.getElementById("results").innerHTML =
    top.map(function(p,index){

      let rank =
        index === 0 ? "الأقرب إلى بصمتك" :
        index === 1 ? "اقتراح ثانٍ" : "اقتراح ثالث";

      const scoreText =
        index === 0
        ? "يناسبك بنسبة " + Math.round(p.score) + "%"
        : "قريب من ذوقك بنسبة " + Math.round(p.score) + "%";

      return '<div class="perfume' + (index === 0 ? ' first' : '') + '">' +
        '<div class="perfumeRank">' + rank + '</div>' +
        '<div class="perfumeName">' + escapeHTML(p.name) + '</div>' +
        '<div class="notes">' + escapeHTML(p.notes) + '</div>' +
        '<div class="matchReason">' + buildReason(p.vector) + '</div>' +
        '<div class="matchScore">' + scoreText + '</div>' +
        '</div>';

    }).join("");

  showScreen("result");
}


/* =========================================================
   TAGS
   ========================================================= */

function buildTags(){

  const definitions = [
    ["انتعاش واضح",0,70],
    ["أجواء مائية",1,68],
    ["خشبية",2,68],
    ["ناعمة وحلوة",3,68],
    ["دافئة",4,68],
    ["عميقة",5,68],
    ["راقية",6,75],
    ["حضور واضح",7,70],
    ["ثبات",8,70],
    ["بهارية",9,65],
    ["خضراء",10,68],
    ["غامضة",11,68]
  ];

  const tags = [];

  definitions.forEach(function(item){
    if(profile[item[1]] >= item[2]){
      tags.push(item[0]);
    }
  });

  if(tags.length < 3){
    const ranked = profile.map(function(value,index){
      return {value:value, index:index};
    }).sort(function(a,b){ return b.value - a.value; });

    ranked.forEach(function(item){
      const definition = definitions.find(function(x){
        return x[1] === item.index;
      });
      if(definition && !tags.includes(definition[0]) && tags.length < 4){
        tags.push(definition[0]);
      }
    });
  }

  return tags.slice(0,4);
}


/* =========================================================
   REASON
   ========================================================= */

function buildReason(vector){

  const similarities = vector.map(function(value,index){
    return { index:index, diff:Math.abs(profile[index]-value) };
  });

  similarities.sort(function(a,b){ return a.diff - b.diff; });

  const a = DIM[similarities[0].index];
  const b = DIM[similarities[1].index];

  return 'اقتراح قريب من ميلك نحو <strong>' +
    escapeHTML(a) + '</strong> و<strong>' +
    escapeHTML(b) + '</strong>، مع توازن عام مناسب لاختياراتك.';
}


/* =========================================================
   ESCAPE
   ========================================================= */

function escapeHTML(text){
  return String(text)
    .replaceAll("&","&amp;")
    .replaceAll("<","&lt;")
    .replaceAll(">","&gt;")
    .replaceAll('"',"&quot;")
    .replaceAll("'","&#039;");
}


/* =========================================================
   HOME
   ========================================================= */

function goHome(){
  current = 0;
  answers = [];
  profile = Array(12).fill(50);
  showScreen("home");
}

</script>

</body>
</html>
