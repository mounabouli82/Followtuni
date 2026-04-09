<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>Afllm Taha | مشاهدة الأفلام</title>
    <!-- Font Awesome 6 (مجاني) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Tajawal', 'Segoe UI', system-ui, sans-serif;
        }

        body {
            background: linear-gradient(145deg, #0a0f1e 0%, #0c1222 100%);
            color: #eee;
            line-height: 1.5;
        }

        /* شريط التمرير الجميل */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #1e1e2f;
        }
        ::-webkit-scrollbar-thumb {
            background: #e50914;
            border-radius: 10px;
        }

        /* الهيدر */
        .header {
            background: rgba(5, 8, 18, 0.85);
            backdrop-filter: blur(12px);
            padding: 1rem 2rem;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            align-items: center;
            border-bottom: 1px solid rgba(229, 9, 20, 0.4);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        .logo h1 {
            font-size: 2rem;
            font-weight: 800;
            background: linear-gradient(135deg, #fff, #e50914);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            letter-spacing: -0.5px;
        }
        .logo span {
            font-size: 0.8rem;
            color: #aaa;
            display: block;
        }
        .search-box {
            background: #1f1f2e;
            border-radius: 40px;
            padding: 0.5rem 1rem;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .search-box input {
            background: transparent;
            border: none;
            color: white;
            font-size: 1rem;
            outline: none;
            width: 200px;
        }
        .search-box button {
            background: none;
            border: none;
            color: #e50914;
            cursor: pointer;
            font-size: 1.2rem;
        }

        /* الحاوية الرئيسية */
        .container {
            max-width: 1400px;
            margin: 2rem auto;
            padding: 0 1.5rem;
        }

        /* الفئات */
        .categories {
            display: flex;
            gap: 1rem;
            flex-wrap: wrap;
            margin-bottom: 2rem;
            justify-content: center;
        }
        .cat-btn {
            background: #1f1f2e;
            border: none;
            color: #ddd;
            padding: 0.5rem 1.5rem;
            border-radius: 30px;
            cursor: pointer;
            transition: 0.2s;
            font-weight: bold;
        }
        .cat-btn.active, .cat-btn:hover {
            background: #e50914;
            color: white;
            box-shadow: 0 0 10px #e50914;
        }

        /* شبكة الأفلام */
        .movies-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(210px, 1fr));
            gap: 1.8rem;
            margin-bottom: 3rem;
        }
        .movie-card {
            background: #141824;
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s ease;
            cursor: pointer;
            border: 1px solid #2a2a3a;
            box-shadow: 0 10px 20px rgba(0,0,0,0.3);
        }
        .movie-card:hover {
            transform: translateY(-8px) scale(1.02);
            border-color: #e50914;
            box-shadow: 0 20px 30px rgba(229,9,20,0.2);
        }
        .poster {
            position: relative;
            height: 280px;
            overflow: hidden;
        }
        .poster img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.4s;
        }
        .movie-card:hover .poster img {
            transform: scale(1.05);
        }
        .movie-info {
            padding: 1rem;
        }
        .movie-title {
            font-weight: bold;
            font-size: 1.1rem;
            margin-bottom: 0.3rem;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .movie-year {
            color: #e50914;
            font-size: 0.8rem;
            font-weight: bold;
        }
        .watch-btn {
            background: #e50914;
            border: none;
            color: white;
            width: 100%;
            padding: 0.5rem;
            margin-top: 0.7rem;
            border-radius: 40px;
            font-weight: bold;
            cursor: pointer;
            transition: 0.2s;
            font-size: 0.9rem;
        }
        .watch-btn:hover {
            background: #b00710;
        }

        /* مشغل الفيديو */
        .player-section {
            background: #0b0e16;
            border-radius: 30px;
            padding: 1rem;
            margin-top: 2rem;
            border: 1px solid #2c2c3e;
            box-shadow: 0 8px 20px rgba(0,0,0,0.5);
        }
        .player-header {
            display: flex;
            justify-content: space-between;
            align-items: baseline;
            padding: 0.5rem 1rem;
            border-bottom: 1px solid #2a2a3a;
            margin-bottom: 1rem;
        }
        .player-header h3 {
            font-size: 1.2rem;
        }
        .player-header span {
            color: #e50914;
            font-size: 0.8rem;
        }
        .video-container {
            background: #000;
            border-radius: 20px;
            overflow: hidden;
            aspect-ratio: 16 / 9;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        video {
            width: 100%;
            height: 100%;
            outline: none;
        }
        .placeholder-player {
            text-align: center;
            color: #aaa;
            padding: 3rem;
        }
        .disclaimer {
            text-align: center;
            font-size: 0.75rem;
            color: #888;
            margin-top: 2rem;
            padding: 1rem;
            border-top: 1px solid #222;
        }
        @media (max-width: 700px) {
            .header {
                flex-direction: column;
                gap: 10px;
            }
            .movies-grid {
                grid-template-columns: repeat(auto-fill, minmax(160px, 1fr));
            }
            .poster {
                height: 220px;
            }
        }
        footer {
            text-align: center;
            padding: 1.5rem;
            color: #6c6f7e;
        }
    </style>
</head>
<body>

<div class="header">
    <div class="logo">
        <h1>Afllm Taha <i class="fas fa-film"></i></h1>
        <span>جميع الأفلام في مكان واحد</span>
    </div>
    <div class="search-box">
        <input type="text" id="searchInput" placeholder="ابحث عن فيلم...">
        <button id="searchBtn"><i class="fas fa-search"></i></button>
    </div>
</div>

<div class="container">
    <!-- أزرار التصنيف -->
    <div class="categories" id="categoriesContainer">
        <button class="cat-btn active" data-cat="all">الكل</button>
        <button class="cat-btn" data-cat="اكشن">أكشن</button>
        <button class="cat-btn" data-cat="دراما">دراما</button>
        <button class="cat-btn" data-cat="كوميدي">كوميدي</button>
        <button class="cat-btn" data-cat="خيال علمي">خيال علمي</button>
    </div>

    <!-- شبكة الأفلام (بيانات وهمية) -->
    <div class="movies-grid" id="moviesGrid"></div>

    <!-- مشغل الفيديو التجريبي -->
    <div class="player-section">
        <div class="player-header">
            <h3><i class="fas fa-play-circle"></i> المشغل الذهبي</h3>
            <span>Afllm Taha Player</span>
        </div>
        <div class="video-container" id="videoPlayerContainer">
            <div class="placeholder-player">
                <i class="fas fa-film" style="font-size: 3rem; opacity: 0.5;"></i>
                <p>اضغط على "مشاهدة" في أي فيلم لتشغيله<br>⚠️ هذا عرض توضيحي، قم باستبدال رابط الفيديو الحقيقي</p>
            </div>
        </div>
    </div>
    <div class="disclaimer">
        ⚠️ هذا الموقع نموذج تعليمي وعرض لواجهة "Afllm Taha". جميع الأفلام المعروضة وهمية لأغراض التصميم. يمكنك إضافة روابط الأفلام الخاصة بك.
    </div>
</div>
<footer>
    © 2025 Afllm Taha | استمتع بمشاهدة أفضل الأفلام
</footer>

<script>
    // قائمة الأفلام الوهمية (للعرض فقط) - يمكنك استبدال الصور والروابط لاحقاً
    const moviesData = [
        { id: 1, title: "صراع العمالقة", year: "2024", genre: "اكشن", poster: "https://picsum.photos/id/104/300/450", videoUrl: "" },
        { id: 2, title: "ليلة القبضة", year: "2023", genre: "اكشن", poster: "https://picsum.photos/id/107/300/450", videoUrl: "" },
        { id: 3, title: "حكاية دراما", year: "2022", genre: "دراما", poster: "https://picsum.photos/id/20/300/450", videoUrl: "" },
        { id: 4, title: "ضحك في الظلام", year: "2025", genre: "كوميدي", poster: "https://picsum.photos/id/26/300/450", videoUrl: "" },
        { id: 5, title: "كوكب المجرة", year: "2023", genre: "خيال علمي", poster: "https://picsum.photos/id/29/300/450", videoUrl: "" },
        { id: 6, title: "الرجل الخارق", year: "2024", genre: "اكشن", poster: "https://picsum.photos/id/155/300/450", videoUrl: "" },
        { id: 7, title: "ذكريات قلب", year: "2021", genre: "دراما", poster: "https://picsum.photos/id/169/300/450", videoUrl: "" },
        { id: 8, title: "مهمة سرية", year: "2025", genre: "اكشن", poster: "https://picsum.photos/id/177/300/450", videoUrl: "" },
        { id: 9, title: "فضائي في القاهرة", year: "2024", genre: "خيال علمي", poster: "https://picsum.photos/id/180/300/450", videoUrl: "" },
        { id: 10, title: "صديقي المهرج", year: "2023", genre: "كوميدي", poster: "https://picsum.photos/id/36/300/450", videoUrl: "" },
        { id: 11, title: "الملحمة الأخيرة", year: "2025", genre: "دراما", poster: "https://picsum.photos/id/42/300/450", videoUrl: "" },
        { id: 12, title: "السرعة القصوى", year: "2024", genre: "اكشن", poster: "https://picsum.photos/id/58/300/450", videoUrl: "" }
    ];

    let currentCategory = "all";
    let searchQuery = "";

    // دالة لعرض الأفلام بناءً على التصنيف والبحث
    function renderMovies() {
        let filtered = moviesData;
        if (currentCategory !== "all") {
            filtered = filtered.filter(movie => movie.genre === currentCategory);
        }
        if (searchQuery.trim() !== "") {
            filtered = filtered.filter(movie => movie.title.includes(searchQuery.trim()));
        }

        const grid = document.getElementById("moviesGrid");
        if (filtered.length === 0) {
            grid.innerHTML = `<div style="grid-column:1/-1; text-align:center; padding:3rem;">😢 لا توجد أفلام تطابق البحث</div>`;
            return;
        }

        grid.innerHTML = filtered.map(movie => `
            <div class="movie-card" data-id="${movie.id}">
                <div class="poster">
                    <img src="${movie.poster}" alt="${movie.title}" loading="lazy">
                </div>
                <div class="movie-info">
                    <div class="movie-title">${movie.title}</div>
                    <div class="movie-year">${movie.year} • ${movie.genre}</div>
                    <button class="watch-btn" data-id="${movie.id}"><i class="fas fa-play"></i> مشاهدة</button>
                </div>
            </div>
        `).join("");

        // إضافة مستمعين لأزرار المشاهدة
        document.querySelectorAll(".watch-btn").forEach(btn => {
            btn.addEventListener("click", (e) => {
                e.stopPropagation();
                const movieId = parseInt(btn.dataset.id);
                const movie = moviesData.find(m => m.id === movieId);
                if (movie) {
                    playMovie(movie);
                }
            });
        });
    }

    // وظيفة تشغيل الفيلم (هنا ستضع رابط الفيديو الحقيقي)
    function playMovie(movie) {
        const container = document.getElementById("videoPlayerContainer");
        // مثال: لو كان عندك رابط حقيقي يمكنك وضعه في المصفوفة مسبقاً.
        // بما أننا نستخدم بيانات وهمية، سأعرض رسالة تفيد بأنه يجب إضافة رابط الفيديو.
        // ولكن أيضاً سأعرض مشغل فيديو تجريبي يحتوي على عينة توضيحية (فيديو نموذجي من unsplash?)
        // يمكنك استبدال الرابط التالي بأي فيلم حقيقي.
        const demoVideoUrl = "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/ForBiggerBlazes.mp4"; // فيديو تجريبي قصير
        // إذا أردت أن يستخدم الفيلم رابطاً خاصاً به (من عندك) أضف خاصية videoUrl لكل فيلم.
        // سأوضح لك: لو كان movie.videoUrl موجود وغير فارغ استخدمه وإلا استخدم التجريبي.
        let sourceUrl = demoVideoUrl;
        if (movie.videoUrl && movie.videoUrl !== "") {
            sourceUrl = movie.videoUrl;
        }
        
        container.innerHTML = `
            <video controls autoplay style="width:100%; height:100%; object-fit: contain;" poster="${movie.poster}">
                <source src="${sourceUrl}" type="video/mp4">
                متصفحك لا يدعم تشغيل الفيديو.
            </video>
        `;
        // إضافة رسالة في وحدة التحكم توضيحية
        if (!movie.videoUrl) {
            console.log(`تنبيه: فيلم "${movie.title}" ليس له رابط مخصص. تم استخدام فيديو تجريبي. يمكنك إضافة رابط حقيقي عبر خاصية videoUrl.`);
        }
    }

    // أحداث البحث والفئات
    function initEvents() {
        const searchInput = document.getElementById("searchInput");
        const searchBtn = document.getElementById("searchBtn");
        const catBtns = document.querySelectorAll(".cat-btn");

        searchBtn.addEventListener("click", () => {
            searchQuery = searchInput.value;
            renderMovies();
        });
        searchInput.addEventListener("keyup", (e) => {
            if (e.key === "Enter") {
                searchQuery = searchInput.value;
                renderMovies();
            }
        });

        catBtns.forEach(btn => {
            btn.addEventListener("click", () => {
                catBtns.forEach(b => b.classList.remove("active"));
                btn.classList.add("active");
                currentCategory = btn.dataset.cat;
                renderMovies();
            });
        });
    }

    // إضافة بعض الأفلام بروابط تجريبية لتوضيح كيف يمكن إضافة روابط حقيقية
    // مثلاً يمكنك تعديل مصفوفة moviesData وإضافة videoUrl: "رابط فيلمك.mp4"
    // ولكن هنا سأضيف مثالاً لفيلمين برابط تجريبي فقط لتوضيح الفكرة
    moviesData[0].videoUrl = "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/WhatCar.mp4";
    moviesData[1].videoUrl = "https://commondatastorage.googleapis.com/gtv-videos-bucket/sample/TearsOfSteel.mp4";
    // باقي الأفلام تستخدم الفيديو التجريبي الافتراضي (ForBiggerBlazes)

    renderMovies();
    initEvents();
</script>
</body>
</html>
