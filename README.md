# DnLocK
<!DOCTYPE html>
<html lang="mn">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="description" content="DnLocK бол iOS төхөөрөмжүүдийн firmware уншуулах, restore хийх, системийн алдаа засах боломжтой програм хангамж юм." />
  <meta name="keywords" content="DnLocK, DnLocK програм, iOS firmware, iPhone restore, Монгол програм хангамж, DnLockS Software, Erdenesukh" />
  <meta name="author" content="DnLockS Software" />
  <title>DnLocK - iOS төхөөрөмжийн програм хангамж</title>

  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet" />
  <link rel="icon" href="favicon.ico" type="image/x-icon" />

  <style>
    /* CSS Хувьсагчид */
    :root {
      --primary-color: #3f6ce4; /* Илүү хөх өнгө */
      --primary-dark: #2a52b6;
      --secondary-color: #e0e7ff; /* Зөөлөн хөх */
      --text-color: #333;
      --light-text-color: #555;
      --bg-color: #f8faff; /* Илүү цайвар дэвсгэр */
      --card-bg: #ffffff;
      --border-color: #e6eaf3;
      --shadow: 0 8px 25px rgba(0,0,0,0.08);
      --border-radius: 12px;
      --spacing-sm: 0.75rem;
      --spacing-md: 1.25rem;
      --spacing-lg: 2rem;
    }

    /* Reset болон үндсэн стиль */
    *, *::before, *::after {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }
    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--bg-color);
      color: var(--text-color);
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
    }

    .container {
      max-width: 800px; /* Илүү өргөн болгосон */
      background: var(--card-bg);
      margin: var(--spacing-lg) auto;
      padding: var(--spacing-lg) var(--spacing-md);
      border-radius: var(--border-radius);
      box-shadow: var(--shadow);
      flex-grow: 1; /* Агуулгыг төвлөрүүлэхэд тусална */
    }

    h1, h2 {
      color: var(--primary-color);
      margin-top: 0;
      font-weight: 700;
      line-height: 1.2;
    }
    h1 {
      font-size: 2.5rem; /* Томруулсан */
      text-align: center;
      margin-bottom: var(--spacing-lg);
      padding-bottom: var(--spacing-sm);
      border-bottom: 2px solid var(--secondary-color);
    }
    h2 {
      font-size: 1.6rem;
      border-bottom: 1px solid var(--border-color); /* Зөөлөн хүрээ */
      padding-bottom: var(--spacing-sm);
      margin-top: var(--spacing-lg);
      margin-bottom: var(--spacing-md);
    }
    p {
      margin-bottom: var(--spacing-md);
      font-size: 1rem;
    }
    ul {
      padding-left: 1.5rem;
      margin-bottom: var(--spacing-md);
    }
    ul li {
      margin-bottom: 0.6rem;
      font-size: 1rem;
      color: var(--light-text-color);
    }
    strong {
        font-weight: 600;
        color: var(--text-color);
    }

    .contact {
      background-color: var(--secondary-color);
      padding: var(--spacing-md) var(--spacing-lg);
      border-radius: var(--border-radius);
      margin-top: var(--spacing-lg);
    }
    .contact h2 {
      margin-top: 0;
      margin-bottom: var(--spacing-sm);
      border-bottom: none; /* Зайлуулсан */
    }
    .contact p {
        margin-bottom: 0.5rem;
    }
    .contact p:last-child {
        margin-bottom: 0;
    }

    a {
      color: var(--primary-color);
      text-decoration: none;
      transition: color 0.3s ease, text-decoration 0.3s ease;
      font-weight: 600;
    }
    a:hover,
    a:focus {
      color: var(--primary-dark);
      text-decoration: underline;
      outline: none;
    }

    /* Татаж авах товчлуур */
    .download-btn {
      display: block;
      width: fit-content;
      margin: var(--spacing-lg) auto var(--spacing-lg) auto; /* Төвд байрлуулах */
      padding: 0.9rem 2rem;
      background-color: var(--primary-color);
      color: #fff;
      text-align: center;
      border-radius: 8px;
      font-size: 1.1rem;
      font-weight: 600;
      transition: background-color 0.3s ease, transform 0.2s ease;
      box-shadow: 0 4px 10px rgba(63, 108, 228, 0.3); /* Товчлуурын сүүдэр */
    }
    .download-btn:hover,
    .download-btn:focus {
      background-color: var(--primary-dark);
      text-decoration: none;
      transform: translateY(-2px); /* Бага зэрэг дээшлэх эффект */
      box-shadow: 0 6px 15px rgba(63, 108, 228, 0.4);
    }

    /* Сошиал медиа холбоосууд */
    .social-links {
        display: flex;
        gap: var(--spacing-md);
        margin-top: var(--spacing-md);
        justify-content: center; /* Төвд байрлуулах */
        flex-wrap: wrap; /* Жижиг дэлгэц дээр доошлуулах */
    }
    .social-links a {
        display: inline-flex;
        align-items: center;
        padding: 0.6rem 1.2rem;
        background-color: var(--primary-color);
        color: #fff;
        border-radius: 8px;
        font-weight: 500;
        transition: background-color 0.3s ease, transform 0.2s ease, box-shadow 0.3s ease;
        box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .social-links a:hover {
        background-color: var(--primary-dark);
        transform: translateY(-1px);
        text-decoration: none;
        box-shadow: 0 4px 8px rgba(0,0,0,0.15);
    }
    .social-links a svg {
        margin-right: 0.5rem;
        width: 18px;
        height: 18px;
        fill: currentColor; /* SVG өнгийг текстний өнгөөр тааруулах */
    }

    footer {
      text-align: center;
      font-size: 0.85rem;
      color: var(--light-text-color);
      margin-top: var(--spacing-lg);
      margin-bottom: var(--spacing-lg);
      padding: 0 var(--spacing-md);
      user-select: none;
    }

    /* Гар утасны хариуцлагатай дизайн (Responsive Design) */
    @media (max-width: 768px) {
      .container {
        margin: var(--spacing-md) var(--spacing-sm);
        padding: var(--spacing-md) var(--spacing-sm);
      }
      h1 {
        font-size: 2rem;
        margin-bottom: var(--spacing-md);
      }
      h2 {
        font-size: 1.4rem;
        margin-top: var(--spacing-md);
        margin-bottom: var(--spacing-sm);
      }
      p, ul li {
        font-size: 0.95rem;
      }
      .download-btn {
        font-size: 1rem;
        padding: 0.8rem 1.5rem;
      }
      .contact {
        padding: var(--spacing-md) var(--spacing-sm);
      }
      .social-links {
        flex-direction: column; /* Жижиг дэлгэц дээр босоо байрлуулах */
        align-items: center; /* Төвд байрлуулах */
      }
      .social-links a {
        width: 100%; /* Бүх өргөнийг эзлэх */
        max-width: 250px; /* Макс өргөн */
        justify-content: center;
      }
    }

    @media (max-width: 480px) {
        h1 {
            font-size: 1.7rem;
        }
        h2 {
            font-size: 1.2rem;
        }
        p, ul li {
            font-size: 0.9rem;
        }
        .download-btn {
            padding: 0.7rem 1.2rem;
            font-size: 0.95rem;
        }
        .social-links a {
            padding: 0.5rem 1rem;
            font-size: 0.9rem;
        }
    }
  </style>
</head>
<body>
  <main class="container" role="main">
    <h1>DnLocK Програм хангамж</h1>

    <p><strong>Хувилбарууд:</strong> DnLocK v4.1 (2019), DnLocK v7.6 (2021)</p>

    <a href="#" class="download-btn" aria-label="DnLocK програмыг татаж авах">
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="20" height="20" fill="currentColor" style="margin-right: 8px;">
        <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-1 14H9v-4H7v-2h2V8h2v2h2v2h-2v4zm4-7h-2V8h2v1zM17 14h-2v-4h2v4z"/>
      </svg>
      Татаж авах
    </a>

    <section aria-labelledby="about-program">
      <h2 id="about-program">Программын тухай</h2>
      <p>
        DnLocK нь iOS үйлдлийн системтэй бүх төрлийн төхөөрөмжийн firmware уншуулах, Restore хийх, системийн алдааг засах зэрэг үйлдлүүдийг гүйцэтгэх зориулалттай Монголын гаралтай програм хангамж юм.
      </p>
    </section>

    <section aria-labelledby="features">
      <h2 id="features">Үндсэн боломжууд:</h2>
      <ul>
        <li>iOS firmware уншуулах</li>
        <li>iPhone/iPad Restore хийх</li>
        <li>Системийн алдааг илрүүлж шийдэх</li>
        <li>Олон төрлийн iOS төхөөрөмжид хэрэглэж болно</li>
      </ul>
    </section>

    <section aria-labelledby="technology">
      <h2 id="technology">Технологи:</h2>
      <p><strong>Python</strong> болон <strong>Visual Studio C++</strong> ашиглан хөгжүүлсэн.</p>
    </section>

    <section class="contact" aria-labelledby="contact-info">
      <h2 id="contact-info">Холбоо барих:</h2>
      <p><strong>Утас:</strong> +976 96265205</p>
      <p><strong>Бренд:</strong> DnLockS Software</p>
      <div class="social-links">
        <a href="https://facebook.com/Erdenesukh8827" target="_blank" rel="noopener noreferrer">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="18" height="18">
                <path d="M22 12c0-5.52-4.48-10-10-10S2 6.48 2 12c0 4.84 3.44 8.87 8 9.8V15h-2v-3h2V9.5C10 7.57 11.57 6 13.5 6H16v3h-2c-.55 0-1 .45-1 1v2h3v3h-3v6.95c5.05-.5 9-4.76 9-9.95z"/>
            </svg>
            Facebook
        </a>
        <a href="#" target="_blank" rel="noopener noreferrer">
            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="18" height="18">
                <path d="M20.21 2.37A2.08 2.08 0 0 0 18.06 2h-12a2.08 2.08 0 0 0-2.15 2.37l1.91 9.53a.52.52 0 0 0 .5.38h10.95a.52.52 0 0 0 .5-.38L20.21 2.37zM8.5 16H6.5v2h2v-2zm10 0h-2v2h2v-2zM12 16h-2v2h2v-2zm3-6h-2v2h2v-2zM9 10h-2v2h2v-2zm-3-4H4.5l1.91-9.53a.52.52 0 0 0-.5-.38H4.21a.52.52 0 0 0-.5-.38l-1.91 9.53a.52.52 0 0 0 .5.38H5.5L7.41 16H9.5V6zm10 0h-2v2h2v-2z"/>
            </svg>
            Discord (Холбоос нэмэх)
        </a>
      </div>
    </section>
  </main>

  <footer>
    © 2025 DnLockS Software. Бүх эрх хуулиар хамгаалагдсан.
  </footer>
</body>
</html>


    
