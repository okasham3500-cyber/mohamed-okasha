<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mohamed Okasha — 2nd Year Baccalaureate Student</title>
  <link href="https://googleapis.com" rel="stylesheet">
  <style>
    :root {
      --bg: #0f172a;
      --card: #1e293b;
      --text: #f8fafc;
      --muted: #94a3b8;
      --accent: #38bdf8;
      --accent-hover: #0284c7;
      --border: #334155;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Cairo', sans-serif; }
    body { background-color: var(--bg); color: var(--text); line-height: 1.6; padding-bottom: 50px; }
    
    /* الهيدر */
    header {
      background: rgba(15, 23, 42, 0.9);
      backdrop-filter: blur(10px);
      padding: 15px 5%;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid var(--border);
      position: sticky;
      top: 0;
      z-index: 100;
    }
    .logo { font-weight: 800; font-size: 1.2rem; letter-spacing: 1px; }
    .logo span { color: var(--accent); }
    nav a { color: var(--text); text-decoration: none; margin-right: 15px; font-size: 0.95rem; transition: 0.3s; }
    nav a:hover { color: var(--accent); }

    /* القسم الرئيسي */
    .hero {
      text-align: center;
      padding: 60px 20px 40px;
      max-width: 750px;
      margin: auto;
    }
    .badge {
      display: inline-block;
      background: rgba(56, 189, 248, 0.1);
      color: var(--accent);
      padding: 5px 15px;
      border-radius: 20px;
      font-size: 0.8rem;
      font-weight: 700;
      margin-bottom: 15px;
      letter-spacing: 1px;
    }
    .hero h1 { font-size: 2.2rem; margin-bottom: 15px; font-weight: 800; }
    .hero p { color: var(--muted); font-size: 1.05rem; margin-bottom: 25px; }
    .avatar {
      width: 70px; height: 70px;
      background: linear-gradient(135deg, var(--accent), #6366f1);
      border-radius: 50%;
      display: flex; align-items: center; justify-content: center;
      font-weight: 800; font-size: 1.4rem;
      margin: 0 auto 30px;
      box-shadow: 0 10px 25px rgba(56, 189, 248, 0.3);
    }

    /* الحاوية العامة */
    .container { max-width: 950px; margin: auto; padding: 0 20px; }
    .section-title { text-align: center; margin: 40px 0 25px; }
    .section-title h2 { font-size: 1.6rem; margin-bottom: 5px; }
    .section-title p { color: var(--muted); font-size: 0.95rem; }

    /* البطاقات التعريفية */
    .cards-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
      gap: 20px;
      margin-bottom: 40px;
    }
    .card {
      background: var(--card);
      padding: 25px;
      border-radius: 15px;
      border: 1px solid var(--border);
      text-align: center;
      transition: transform 0.3s;
    }
    .card:hover { transform: translateY(-5px); border-color: var(--accent); }
    .card .icon { font-size: 2.2rem; margin-bottom: 10px; }
    .card h3 { margin-bottom: 8px; font-size: 1.2rem; }
    .card p { color: var(--muted); font-size: 0.9rem; }

    /* صندوق الحماية بكلمة مرور */
    .lock-box {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 35px 20px;
      max-width: 450px;
      margin: 30px auto;
      text-align: center;
    }
    .lock-box input {
      width: 100%;
      padding: 12px 15px;
      margin: 15px 0;
      border-radius: 8px;
      border: 1px solid var(--border);
      background: var(--bg);
      color: var(--text);
      font-size: 1rem;
      text-align: center;
    }
    .btn {
      background: var(--accent);
      color: #0f172a;
      border: none;
      padding: 10px 24px;
      border-radius: 8px;
      font-weight: 700;
      cursor: pointer;
      font-size: 0.95rem;
      transition: 0.3s;
    }
    .btn:hover { background: var(--accent-hover); color: white; }
    .btn-danger { background: #ef4444; color: white; }

    /* الأقسام الداخلية بعد الفتح */
    .content-box {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 25px;
      margin-bottom: 30px;
    }
    .upload-area {
      display: flex;
      flex-wrap: wrap;
      gap: 10px;
      align-items: center;
      justify-content: center;
      margin: 15px 0 25px;
      padding: 15px;
      border: 1px dashed var(--border);
      border-radius: 10px;
    }
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
      gap: 15px;
    }
    .gallery-item {
      background: var(--bg);
      border-radius: 10px;
      overflow: hidden;
      border: 1px solid var(--border);
      text-align: center;
      padding-bottom: 10px;
    }
    .gallery-item img { width: 100%; height: 180px; object-fit: cover; }
    .gallery-item p { font-size: 0.85rem; color: var(--muted); padding: 8px 5px 0; word-break: break-all; }

    .file-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      background: var(--bg);
      padding: 12px 15px;
      border-radius: 8px;
      margin-bottom: 10px;
      border: 1px solid var(--border);
    }
    .file-item a { color: var(--accent); text-decoration: none; font-weight: 600; }

    textarea {
      width: 100%;
      height: 150px;
      background: var(--bg);
      color: var(--text);
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 15px;
      font-size: 1rem;
      margin-bottom: 15px;
      resize: vertical;
    }

    footer {
      text-align: center;
      color: var(--muted);
      font-size: 0.9rem;
      margin-top: 50px;
      padding-top: 20px;
      border-top: 1px solid var(--border);
    }
  </style>
</head>
<body>

  <header>
    <div class="logo">MOHAMED <span>OKASHA</span></div>
    <nav>
      <a href="#home">الرئيسية</a>
      <a href="#private-zone">خاص 🔒</a>
    </nav>
  </header>

  <section id="home" class="hero">
    <div class="badge">MOHAMED OKASHA · 2ND YEAR BACCALAUREATE STUDENT</div>
    <h1>مساحتي، بصمتي في الطريق.</h1>
    <p>مساحة شخصية أشارك فيها لحظاتي، اهتماماتي، وملامح رحلتي كطالب نحو المستقبل.</p>
    <div class="avatar">M O</div>
  </section>

  <div class="container">
    <div class="section-title">
      <h2>داخل مساحتي</h2>
      <p>أقسام مساحتي الشخصية المحفوظة في السحابة</p>
    </div>

    <div class="cards-grid">
      <div class="card">
        <div class="icon">📸</div>
        <h3>ألبوم الصور</h3>
        <p>لحظات وصور محفوظة دائماً في السحابة.</p>
      </div>
      <div class="card">
        <div class="icon">📁</div>
        <h3>ملفات ومحتوى</h3>
        <p>ملفات ومستندات دراسية وشخصية متاحة في أي وقت.</p>
      </div>
      <div class="card">
        <div class="icon">📝</div>
        <h3>مذكرات خاصة</h3>
        <p>أفكار وكتابات محمية بكلمة مرور ومحفوظة سحابياً.</p>
      </div>
    </div>

    <!-- القسم المحمي بكلمة مرور -->
    <div id="private-zone">
      <div id="login-box" class="lock-box">
        <div style="font-size: 2.5rem; margin-bottom: 10px;">🔒</div>
        <h3>منطقة خاصة بمحمد عكاشة</h3>
        <p style="color: var(--muted); font-size: 0.9rem;">أدخل كلمة المرور لعرض وإضافة الصور والملفات والمذكرات</p>
        <input type="password" id="password-input" placeholder="اكتب كلمة المرور هنا...">
        <button class="btn" onclick="unlockSpace()">فتح المساحة الخاصة</button>
        <p id="error-msg" style="color: #ef4444; display: none; margin-top: 10px; font-size: 0.9rem;">كلمة المرور غير صحيحة!</p>
      </div>

      <!-- المحتوى الذي يظهر بعد إدخال كلمة المرور -->
      <div id="secret-content" style="display: none;">
        
        <!-- 1. ألبوم الصور -->
        <div class="content-box">
          <h3>📸 ألبوم الصور (حفظ دائم)</h3>
          <p style="color: var(--muted); font-size: 0.9rem;">اختر صورة لرفعها وحفظها في قاعدة البيانات (الحد الأقصى 800 كيلوبايت للصورة)</p>
          <div class="upload-area">
            <input type="file" id="cloud-image-input" accept="image/*">
            <button class="btn" id="btn-upload-img" onclick="uploadToCloud('cloud-image-input', 'image')">+ رفع وحفظ الصورة</button>
          </div>
          <div id="cloud-gallery" class="gallery-grid"></div>
        </div>

        <!-- 2. ملفاتي -->
        <div class="content-box">
          <h3>📁 ملفاتي (حفظ دائم)</h3>
          <p style="color: var(--muted); font-size: 0.9rem;">ارفع ملفاتك لتبقى محفوظة وتصل إليها من أي جهاز (الحد الأقصى 800 كيلوبايت للملف)</p>
          <div class="upload-area">
            <input type="file" id="cloud-file-input">
            <button class="btn" id="btn-upload-file" onclick="uploadToCloud('cloud-file-input', 'file')">+ رفع وحفظ الملف</button>
          </div>
          <div id="cloud-files"></div>
        </div>

        <!-- 3. مذكرات خاصة -->
        <div class="content-box">
          <h3>📝 مذكرات خاصة (محفوظة سحابياً)</h3>
          <p style="color: var(--muted); font-size: 0.9rem; margin-bottom: 10px;">اكتب مذكراتك هنا واضغط حفظ لتبقى محفوظة معك في أي مكان</p>
          <textarea id="cloud-notes" placeholder="اكتب أفكارك ومذكراتك هنا..."></textarea>
          <button class="btn" onclick="saveNotesToCloud()">💾 حفظ المذكرات في السحابة</button>
          <button class="btn btn-danger" onclick="lockSpace()" style="margin-right: 10px;">قفل المساحة 🔒</button>
        </div>

      </div>
    </div>
  </div>

  <footer>
    Mohamed Okasha · 2nd Year Baccalaureate Student — مساحة خاصة من اختياري ✦
  </footer>

  <!-- كود التحقق من كلمة المرور والربط مع Firebase -->
  <script>
    // تغيير كلمة المرور من هنا
    const MY_SECRET_PASSWORD = "1234";

    function unlockSpace() {
      const input = document.getElementById("password-input").value;
      if (input === MY_SECRET_PASSWORD) {
        document.getElementById("login-box").style.display = "none";
