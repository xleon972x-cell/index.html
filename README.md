index.html
<!DOCTYPE html>
<html lang="he" dir="rtl" id="mainHtml">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Key2Lev - Premium Services</title>
    <style>
        :root {
            --gold: #d4af37;
            --dark-bg: #0a0a0a;
            --card-bg: #1a1a1a;
            --text-white: #ffffff;
        }

        body {
            font-family: 'Arial', sans-serif;
            background-color: #000;
            display: flex;
            flex-direction: column;
            align-items: center;
            padding: 20px;
            margin: 0;
        }

        /* כפתור החלפת שפה */
        .lang-switch {
            margin-bottom: 20px;
            padding: 10px 20px;
            background: var(--gold);
            border: none;
            border-radius: 20px;
            font-weight: bold;
            cursor: pointer;
            color: #000;
            transition: 0.3s;
        }

        .ad-container {
            max-width: 450px;
            background-color: var(--dark-bg);
            border: 1px solid var(--gold);
            border-radius: 30px;
            padding: 40px 20px;
            text-align: center;
            box-shadow: 0 0 50px rgba(212, 175, 55, 0.1);
        }

        .logo {
            font-size: 50px;
            font-weight: 900;
            color: var(--gold);
            text-transform: lowercase;
            margin-bottom: 0;
        }

        .tagline {
            color: var(--gold);
            font-size: 14px;
            letter-spacing: 2px;
            margin-bottom: 30px;
        }

        h1 { color: #fff; font-size: 24px; margin-bottom: 10px; }
        .subtitle { color: #ccc; font-size: 16px; margin-bottom: 30px; }

        /* כרטיסי מומחים */
        .experts-grid {
            display: flex;
            gap: 15px;
            margin-bottom: 30px;
        }

        .expert-card {
            flex: 1;
            background: var(--card-bg);
            padding: 20px;
            border-radius: 20px;
            border: 1px solid #333;
        }

        .photo-frame {
            width: 100px;
            height: 100px;
            border-radius: 50%;
            border: 2px solid var(--gold);
            margin: 0 auto 15px;
            overflow: hidden;
            background: #222;
        }

        .photo-frame img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .name { color: var(--gold); font-weight: bold; font-size: 18px; display: block; }
        .role { color: #888; font-size: 13px; }

        .features {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            margin: 30px 0;
            text-align: initial;
            border-top: 1px solid #222;
            padding-top: 20px;
        }

        .feature { color: #fff; font-size: 14px; }
        .feature::before { content: "✦ "; color: var(--gold); }

        .contact-box {
            background: linear-gradient(145deg, #1a1a1a, #000);
            padding: 20px;
            border-radius: 20px;
            border-top: 2px solid var(--gold);
        }

        .contact-item {
            display: flex;
            justify-content: space-between;
            margin: 10px 0;
            font-size: 18px;
            text-decoration: none;
            color: var(--gold);
        }

        /* שינוי כיוון לרוסית */
        .ltr { direction: ltr; text-align: left; }
        .ltr .features { text-align: left; }
    </style>
</head>
<body>

    <button class="lang-switch" onclick="toggleLanguage()">RU / HE</button>

    <div class="ad-container" id="adContent">
        <div class="logo">key2lev</div>
        <div class="tagline" id="tagline">שירותי יוקרה לבית ולעסק</div>

        <h1 id="mainTitle">צריכים שיפוץ קוסמטי?</h1>
        <p class="subtitle" id="subTitle">יש תקלת חשמל? המומחים שלנו בדרך אליכם</p>

        <div class="experts-grid">
            <div class="expert-card">
                <div class="photo-frame">
                    <img src="https://i.ibb.co/h9N5t5F/solomon.jpg" alt="Solomon">
                </div>
                <span class="name" id="name1">סולומון</span>
                <span class="role" id="role1">שיפוץ וגמר</span>
            </div>
            <div class="expert-card">
                <div class="photo-frame">
                    <img src="https://i.ibb.co/L5Q2Z1W/tom.jpg" alt="Tom">
                </div>
                <span class="name" id="name2">טום</span>
                <span class="role" id="role2">חשמלאי מוסמך</span>
            </div>
        </div>

        <div class="features" id="features">
            <div class="feature" id="f1">שירות מעל הכל</div>
            <div class="feature" id="f2">עבודה הוגנת</div>
            <div class="feature" id="f3">זמינות ואיכות</div>
            <div class="feature" id="f4">מרכז עד צפון</div>
        </div>

        <div class="contact-box">
            <a href="tel:0559804080" class="contact-item">
                <span style="color: white;">סולומון</span>
                <span>055-980-4080</span>
            </a>
            <a href="tel:0549763940" class="contact-item">
                <span style="color: white;">ארתיום</span>
                <span>054-976-3940</span>
            </a>
        </div>
    </div>

    <script>
        let currentLang = 'he';
        const data = {
            he: {
                tagline: "שירותי יוקרה לבית ולעסק",
                title: "צריכים שיפוץ קוסמטי?",
                sub: "יש תקלת חשמל? המומחים שלנו בדרך אליכם",
                role1: "שיפוץ וגמר",
                role2: "חשמלאי מוסמך",
                f1: "שירות מעל הכל", f2: "עבודה הוגנת", f3: "זמינות ואיכות", f4: "מרכז עד צפון"
            },
            ru: {
                tagline: "Премиальные услуги для дома и офиса",
                title: "Нужен косметический ремонт?",
                sub: "Проблемы с электричеством? Наши эксперты помогут вам",
                role1: "Ремонт и отделка",
                role2: "Лицензированный электрик",
                f1: "Сервис превыше всего", f2: "Честная работа", f3: "Качество и доступность", f4: "Центр и Север"
            }
        };

        function toggleLanguage() {
            const html = document.getElementById('mainHtml');
            currentLang = currentLang === 'he' ? 'ru' : 'he';
            
            html.dir = currentLang === 'he' ? 'rtl' : 'ltr';
            if(currentLang === 'ru') html.classList.add('ltr');
            else html.classList.remove('ltr');

            document.getElementById('tagline').innerText = data[currentLang].tagline;
            document.getElementById('mainTitle').innerText = data[currentLang].title;
            document.getElementById('subTitle').innerText = data[currentLang].sub;
            document.getElementById('role1').innerText = data[currentLang].role1;
            document.getElementById('role2').innerText = data[currentLang].role2;
            document.getElementById('f1').innerText = data[currentLang].f1;
            document.getElementById('f2').innerText = data[currentLang].f2;
            document.getElementById('f3').innerText = data[currentLang].f3;
            document.getElementById('f4').innerText = data[currentLang].f4;
        }
    </script>
</body>
</html>
