# VolleyPortal
<!doctype html>
<html lang="uk">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Волейбол — Портал | Історія, гравці, чемпіонати</title>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#f4f7fb;
      --card:#ffffff;
      --accent:#ff7a18; /* помаранчевий м'яча */
      --primary:#045a8d; /* темно-синій */
      --muted:#6b7280;
      --radius:14px;
      --glass: rgba(255,255,255,0.65);
    }
    *{box-sizing:border-box}
    body{font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial; margin:0; background:var(--bg); color:#112; -webkit-font-smoothing:antialiased}
    .container{max-width:1200px;margin:0 auto;padding:24px}

    header.site-header{position:sticky;top:0;z-index:40;background:linear-gradient(90deg, rgba(4,90,141,0.96), rgba(6,125,186,0.96));box-shadow:0 6px 18px rgba(4,90,141,0.12)}
    .site-header .container{display:flex;align-items:center;gap:20px}
    .logo{display:flex;align-items:center;gap:12px;color:white;text-decoration:none}
    .logo .ball{width:44px;height:44px;border-radius:50%;background:linear-gradient(135deg,var(--accent),#ffd27a);display:flex;align-items:center;justify-content:center;font-weight:800;color:#2b2b2b}
    nav.main-nav{margin-left:auto;display:flex;gap:14px}
    nav.main-nav a{color:rgba(255,255,255,0.95);text-decoration:none;font-weight:600;padding:10px;border-radius:10px}
    nav.main-nav a:hover{background:rgba(255,255,255,0.06)}

    /* Hero */
    .hero{display:grid;grid-template-columns:1fr 420px;gap:28px;align-items:center;padding:64px 0}
    .hero .content h1{font-family:Montserrat, Inter; font-size:44px;margin:0 0 12px;color:var(--primary)}
    .hero .content p{margin:0 0 18px;color:var(--muted);font-size:16px}
    .cta{display:flex;gap:12px}
    .btn{background:var(--accent);border:none;padding:12px 18px;border-radius:10px;color:#1b1b1b;font-weight:700;cursor:pointer}
    .btn.ghost{background:transparent;border:2px solid var(--accent);color:var(--accent)}

    .hero .hero-card{background:linear-gradient(180deg,#fff, #fbfcff);border-radius:16px;padding:18px;box-shadow:0 10px 30px rgba(4,90,141,0.08)}
    .hero .hero-card img{width:100%;height:260px;object-fit:cover;border-radius:10px}

    /* Sections */
    section{margin:40px 0}
    .grid{display:grid;gap:18px}
    .grid.cols-3{grid-template-columns:repeat(3,1fr)}
    .card{background:var(--card);border-radius:var(--radius);padding:18px;box-shadow:0 8px 20px rgba(16,24,40,0.04);transition:transform .22s, box-shadow .22s}
    .card:hover{transform:translateY(-8px);box-shadow:0 18px 40px rgba(16,24,40,0.08)}
    h2.section-title{font-family:Montserrat;margin:0 0 12px;color:var(--primary)}

    /* Players */
    .players{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:16px}
    .player img{width:100%;height:160px;object-fit:cover;border-radius:10px}
    .player .meta{display:flex;align-items:center;justify-content:space-between;margin-top:10px}

    /* Tournaments */
    .tournaments{display:flex;flex-direction:column;gap:12px}
    .tournaments .row{display:flex;align-items:center;gap:12px}
    .badge{background:var(--primary);color:white;padding:6px 10px;border-radius:8px;font-weight:700}

    /* Gallery slider */
    .slider{position:relative;overflow:hidden;border-radius:12px}
    .slides{display:flex;transition:transform .5s ease}
    .slides img{width:100%;min-width:100%;height:420px;object-fit:cover}
    .slider .controls{position:absolute;top:50%;left:12px;right:12px;display:flex;justify-content:space-between;transform:translateY(-50%)}
    .ctrl{background:rgba(0,0,0,0.45);color:white;padding:8px 10px;border-radius:8px;border:none;cursor:pointer}

    /* Contact */
    form.contact-form{display:grid;gap:12px}
    input,textarea,select{padding:12px;border-radius:10px;border:1px solid #e6eef7;background:transparent}
    button.submit{background:var(--primary);color:white;border:none;padding:12px;border-radius:10px;cursor:pointer}

    footer{padding:36px 0;background:linear-gradient(90deg,#022f40,#013b54);color:white;margin-top:40px}

    /* Responsive */
    @media(max-width:980px){
      .hero{grid-template-columns:1fr;}
      .hero .hero-card img{height:200px}
    }

    /* Dark mode */
    .dark{--bg:#071022;--card:#071a2b;--accent:#ffb86b;--primary:#60a5fa;--muted:#9aa9bf;--glass:rgba(255,255,255,0.04);color:#e6f0ff}
    .dark body{background:var(--bg)}

  </style>
</head>
<body id="page">
  <header class="site-header">
    <div class="container">
      <a class="logo" href="#">
        <div class="ball">VB</div>
        <div>
          <div style="font-weight:800">VolleyPortal</div>
          <div style="font-size:12px;opacity:.9">спорт · новини · історії</div>
        </div>
      </a>

      <nav class="main-nav">
        <a href="#about">Про гру</a>
        <a href="#history">Історія</a>
        <a href="#players">Гравці</a>
        <a href="#tournaments">Чемпіонати</a>
        <a href="#gallery">Галерея</a>
        <a href="#contact">Контакти</a>
        <button class="btn" id="themeToggle">🌙</button>
      </nav>
    </div>
  </header>

  <main class="container">
    <!-- HERO -->
    <section class="hero">
      <div class="content">
        <h1>Волейбол — швидкість, техніка і командний дух</h1>
        <p>Дізнайся історію гри, знайомся з легендами волейболу, слідкуй за головними чемпіонатами і натхнися фото з матчів.</p>
        <div class="cta">
          <a class="btn" href="#gallery">Переглянути галерею</a>
          <a class="btn ghost" href="#players">Відомі гравці</a>
        </div>

        <div style="margin-top:20px;display:flex;gap:12px;flex-wrap:wrap">
          <div class="card" style="display:flex;gap:12px;align-items:center">
            <div class="badge">25 000+</div>
            <div>
              <div style="font-weight:700">Матчів у базі</div>
              <div style="color:var(--muted);font-size:13px">Статистика та архіви</div>
            </div>
          </div>
          <div class="card" style="display:flex;gap:12px;align-items:center">
            <div class="badge">120+</div>
            <div>
              <div style="font-weight:700">Гравців</div>
              <div style="color:var(--muted);font-size:13px">Біографії та досягнення</div>
            </div>
          </div>
        </div>
      </div>

      <div class="hero-card">
        <img src="https://picsum.photos/id/1012/900/600" alt="волейбол банер">
        <div style="display:flex;gap:10px;margin-top:12px;align-items:center">
          <div class="card" style="flex:1">
            <div style="font-weight:700">Останній матч</div>
            <div style="color:var(--muted);font-size:14px">Суперлига · 21 вересня 2025 · СуперКоманда 3:2 Чемпіон</div>
          </div>
          <div class="card" style="width:140px;text-align:center;align-items:center;display:flex;flex-direction:column;justify-content:center">
            <div style="font-size:18px;font-weight:800">Матч дня</div>
            <div style="color:var(--muted);font-size:13px">Дивитися анонс</div>
          </div>
        </div>
      </div>
    </section>

    <!-- ABOUT -->
    <section id="about">
      <h2 class="section-title">Про гру</h2>
      <div class="grid cols-3">
        <div class="card">
          <h3 style="margin-top:0">Що таке волейбол</h3>
          <p style="color:var(--muted)">Волейбол — командний вид спорту, що зародився наприкінці XIX століття. Гра вимагає від гравців швидкості, координації і злагодженої командної роботи.</p>
        </div>
        <div class="card">
          <h3 style="margin-top:0">Суть</h3>
          <p style="color:var(--muted)">Команди обмінюються ударами по м'ячу, намагаючись зробити так, щоб м'яч торкнувся майданчика суперника або змусити суперника зробити помилку.</p>
        </div>
        <div class="card">
          <h3 style="margin-top:0">Переваги</h3>
          <ul style="color:var(--muted)">
            <li>Розвиток витривалості</li>
            <li>Командна взаємодія</li>
            <li>Координація рухів</li>
          </ul>
        </div>
      </div>
    </section>

    <!-- HISTORY -->
    <section id="history">
      <h2 class="section-title">Коротка історія</h2>
      <div class="card">
        <p style="color:var(--muted)">Волейбол був винайдений у 1895 році в США Вільямом Морганом як менш контактна альтернатива баскетболу. Гра швидко набрала популярності і стала олімпійським видом спорту в 1964 році. Згодом з'явилися пляжний волейбол і безліч професійних турнірів по всьому світу.</p>
        <div style="display:flex;gap:10px;margin-top:14px;flex-wrap:wrap">
          <div class="card" style="padding:10px">
            <div style="font-weight:800">1895</div>
            <div style="color:var(--muted);font-size:13px">Винайдення волейболу</div>
          </div>
          <div class="card" style="padding:10px">
            <div style="font-weight:800">1964</div>
            <div style="color:var(--muted);font-size:13px">Поява у Олімпіаді</div>
          </div>
          <div class="card" style="padding:10px">
            <div style="font-weight:800">1996</div>
            <div style="color:var(--muted);font-size:13px">Пляжний волейбол на Олімпіаді</div>
          </div>
        </div>
      </div>
    </section>

    <!-- RULES -->
    <section id="rules">
      <h2 class="section-title">Основні правила</h2>
      <div class="grid cols-3">
        <div class="card">
          <h4>Склад команди</h4>
          <p style="color:var(--muted)">6 гравців на полі; заміни за правилами змагань.</p>
        </div>
        <div class="card">
          <h4>Контакт з м'ячем</h4>
          <p style="color:var(--muted)">Не дозволяється ловити або кидати м'яч; максимум 3 торкання однієї команди.</p>
        </div>
        <div class="card">
          <h4>Сети</h4>
          <p style="color:var(--muted)">Матч складається з сетів до 25 очок (попросо), останній сет до 15 — з перевагою 2 очок.</p>
        </div>
      </div>
    </section>

    <!-- PLAYERS -->
    <section id="players">
      <h2 class="section-title">Відомі гравці</h2>
      <div class="players">
        <article class="player card">
          <img src="https://picsum.photos/id/1005/600/400" alt="Гравець 1">
          <h4 style="margin:10px 0 4px">Андрій Іванов</h4>
          <div class="meta"><div style="color:var(--muted)">Натуральна позиція: ліберо</div><div style="font-weight:700">Олімпійський медаліст</div></div>
        </article>
        <article class="player card">
          <img src="https://picsum.photos/id/1006/600/400" alt="Гравець 2">
          <h4 style="margin:10px 0 4px">Марія Петренко</h4>
          <div class="meta"><div style="color:var(--muted)">Натуральна позиція: атакуюча</div><div style="font-weight:700">Краща нападниця сезону</div></div>
        </article>
        <article class="player card">
          <img src="https://picsum.photos/id/1008/600/400" alt="Гравець 3">
          <h4 style="margin:10px 0 4px">Дмитро Коваленко</h4>
          <div class="meta"><div style="color:var(--muted)">Натуральна позиція: догравальник</div><div style="font-weight:700">Рекордсмен блоків</div></div>
        </article>
      </div>
    </section>

    <!-- TOURNAMENTS -->
    <section id="tournaments">
      <h2 class="section-title">Головні чемпіонати</h2>
      <div class="card tournaments">
        <div class="row"><div class="badge">Олімпійські ігри</div><div style="color:var(--muted)">Найпрестижніший турнір для національних збірних; волейбол входить у програму з 1964 року.</div></div>
        <div class="row"><div class="badge">Чемпіонат світу</div><div style="color:var(--muted)">Проводиться під егідою FIVB; збирає топ-збірні кожні 4 роки.</div></div>
        <div class="row"><div class="badge">Ліга націй</div><div style="color:var(--muted)">Щорічний турнір найсильніших збірних — заміна Ліги націй/Світової ліги.</div></div>
      </div>
    </section>

    <!-- GALLERY SLIDER -->
    <section id="gallery">
      <h2 class="section-title">Галерея</h2>
      <div class="slider card" id="slider">
        <div class="slides" id="slides">
          <img src="https://picsum.photos/id/1011/1200/700" alt="slide1">
          <img src="https://picsum.photos/id/1025/1200/700" alt="slide2">
          <img src="https://picsum.photos/id/1037/1200/700" alt="slide3">
        </div>
        <div class="controls">
          <button class="ctrl" id="prev">◀</button>
          <button class="ctrl" id="next">▶</button>
        </div>
      </div>
    </section>

    <!-- CONTACT -->
    <section id="contact">
      <h2 class="section-title">Контакти</h2>
      <div class="grid" style="grid-template-columns:1fr 360px;align-items:start">
        <div class="card">
          <p style="color:var(--muted)">Маєш матеріал, фото або хочеш запропонувати статтю? Напиши нам — ми із задоволенням подумаємо над співпрацею.</p>
          <form class="contact-form" onsubmit="event.preventDefault(); alert('Дякуємо! Ми отримали ваше повідомлення.');">
            <input placeholder="Ім'я" required>
            <input placeholder="Email" type="email" required>
            <select><option>Тема: Загальне</option><option>Партнерство</option><option>Матеріали</option></select>
            <textarea rows="5" placeholder="Повідомлення" required></textarea>
            <button class="submit">Надіслати</button>
          </form>
        </div>
        <div class="card" style="padding:18px">
          <h4 style="margin:0 0 8px">Контактна інформація</h4>
          <div style="color:var(--muted)">Email: info@volleyportal.example</div>
          <div style="color:var(--muted)">Телефон: +38 0xx xxx xxxx</div>
          <div style="margin-top:12px">
            <div style="font-weight:700">Підписка на новини</div>
            <div style="margin-top:8px;display:flex;gap:8px">
              <input placeholder="Ваша пошта" style="flex:1;padding:10px;border-radius:8px;border:1px solid #e6eef7">
              <button class="btn">Підписатися</button>
            </div>
          </div>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container" style="display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:12px">
      <div>
        <div style="font-weight:800">VolleyPortal</div>
        <div style="font-size:13px;opacity:.9">Все про волейбол — історія, гравці, фото</div>
      </div>
      <div style="color:rgba(255,255,255,0.85)">© 2025 VolleyPortal. Всі права захищені.</div>
    </div>
  </footer>

  <script>
    // Простий слайдер
    (function(){
      const slides = document.getElementById('slides');
      const prev = document.getElementById('prev');
      const next = document.getElementById('next');
      let index = 0;
      const total = slides.children.length;
      function show(i){
        index = (i + total) % total;
        slides.style.transform = 'translateX(' + (-index * 100) + '%)';
      }
      prev.addEventListener('click', ()=> show(index-1));
      next.addEventListener('click', ()=> show(index+1));
      // автопрокрутка
      let auto = setInterval(()=> show(index+1), 5000);
      [prev,next,slides].forEach(el=> el.addEventListener('mouseenter', ()=> clearInterval(auto)));
      [prev,next,slides].forEach(el=> el.addEventListener('mouseleave', ()=> auto = setInterval(()=> show(index+1), 5000)));
    })();

    // Dark mode toggle
    (function(){
      const btn = document.getElementById('themeToggle');
      const root = document.documentElement;
      const saved = localStorage.getItem('vp_theme');
      if(saved === 'dark') document.documentElement.classList.add('dark');
      btn.addEventListener('click', ()=>{
        document.documentElement.classList.toggle('dark');
        const isDark = document.documentElement.classList.contains('dark');
        localStorage.setItem('vp_theme', isDark ? 'dark' : 'light');
        btn.textContent = isDark ? '☀️' : '🌙';
      });
    })();

    // Smooth scroll for internal links
    document.querySelectorAll('a[href^="#"]').forEach(a=>{
      a.addEventListener('click', function(e){
        e.preventDefault();
        const id = this.getAttribute('href').slice(1);
        const el = document.getElementById(id);
        if(el) el.scrollIntoView({behavior:'smooth', block:'start'});
      });
    });
  </script>
</body>
</html>
