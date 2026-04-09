<!DOCTYPE html>
<html dir="rtl" lang="ar">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>متجر الخدمات الرقمية - شحن وبطاقات وتصميم</title>
    <!-- إطار CSS لتسريع التصميم (اختياري) -->
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body { background-color: #f4f7fc; font-family: 'Tajawal', sans-serif; }
        .service-card { border-radius: 15px; transition: transform 0.2s; border: none; box-shadow: 0 5px 15px rgba(0,0,0,0.05); }
        .service-card:hover { transform: translateY(-5px); }
        .category-badge { background-color: #0d6efd; color: white; padding: 5px 12px; border-radius: 30px; font-size: 14px; }
    </style>
</head>
<body>

    <!-- شريط التنقل العلوي -->
    <nav class="navbar navbar-expand-lg bg-white shadow-sm p-3 mb-4">
        <div class="container">
            <a class="navbar-brand fw-bold text-primary" href="#">⚡ الخدمات السريعة</a>
            <div class="d-flex">
                <a href="#" class="btn btn-outline-primary mx-2">تسجيل الدخول</a>
                <a href="#" class="btn btn-primary">سلة المشتريات (0)</a>
            </div>
        </div>
    </nav>

    <!-- المحتوى الرئيسي -->
    <div class="container">
        <div class="row mb-5 text-center">
            <div class="col-12">
                <h1 class="fw-bold">كل خدماتك الإلكترونية في مكان واحد</h1>
                <p class="lead text-secondary">شحن رصيد • بطاقات ألعاب • اشتراكات • خدمات مصغرة</p>
                <div class="input-group w-50 mx-auto my-4">
                    <input type="text" class="form-control p-3 rounded-4" placeholder="ابحث عن الخدمة... (مثال: ببجي، شحن سوا)">
                    <button class="btn btn-primary rounded-4 px-4">بحث</button>
                </div>
            </div>
        </div>

        <!-- أقسام الخدمات الإلكترونية -->
        <h3 class="mb-4 fw-bold">📱 خدمات شائعة</h3>
        <div class="row g-4">
            
            <!-- بطاقة خدمة 1: شحن الرصيد -->
            <div class="col-lg-3 col-md-6">
                <div class="card service-card h-100">
                    <div class="card-body text-center p-4">
                        <span class="category-badge mb-3 d-inline-block">شحن</span>
                        <img src="https://img.icons8.com/color/96/000000/sim-card.png" width="70" class="mb-3" alt="شحن">
                        <h5 class="card-title">شحن رصيد سوا</h5>
                        <p class="text-muted">فوري لجميع الشبكات</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold fs-5">20.00 ريال</span>
                            <a href="#" class="btn btn-sm btn-success">اطلب الآن</a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- بطاقة خدمة 2: بطاقات ألعاب -->
            <div class="col-lg-3 col-md-6">
                <div class="card service-card h-100">
                    <div class="card-body text-center p-4">
                        <span class="category-badge bg-danger mb-3 d-inline-block">ألعاب</span>
                        <img src="https://img.icons8.com/color/96/000000/pubg.png" width="70" class="mb-3" alt="ببجي">
                        <h5 class="card-title">شحن PUBG UC</h5>
                        <p class="text-muted">توصيل فوري للكود</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold fs-5">60.00 ريال</span>
                            <a href="#" class="btn btn-sm btn-success">اشحن</a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- بطاقة خدمة 3: اشتراكات -->
            <div class="col-lg-3 col-md-6">
                <div class="card service-card h-100">
                    <div class="card-body text-center p-4">
                        <span class="category-badge bg-warning text-dark mb-3 d-inline-block">ترفيه</span>
                        <img src="https://img.icons8.com/color/96/000000/netflix.png" width="70" class="mb-3" alt="نتفلكس">
                        <h5 class="card-title">اشتراك نتفلكس شهر</h5>
                        <p class="text-muted">حساب خاص بجودة 4K</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold fs-5">45.00 ريال</span>
                            <a href="#" class="btn btn-sm btn-success">شراء</a>
                        </div>
                    </div>
                </div>
            </div>

            <!-- بطاقة خدمة 4: خدمات مصغرة -->
            <div class="col-lg-3 col-md-6">
                <div class="card service-card h-100">
                    <div class="card-body text-center p-4">
                        <span class="category-badge bg-info mb-3 d-inline-block">خدمة</span>
                        <img src="https://img.icons8.com/color/96/000000/design.png" width="70" class="mb-3" alt="تصميم">
                        <h5 class="card-title">تصميم لوجو احترافي</h5>
                        <p class="text-muted">تسليم خلال 24 ساعة</p>
                        <div class="d-flex justify-content-between align-items-center mt-3">
                            <span class="fw-bold fs-5">150.00 ريال</span>
                            <a href="#" class="btn btn-sm btn-success">اطلب</a>
                        </div>
                    </div>
                </div>
            </div>

        </div>
        
        <!-- قسم مزايا الموقع -->
        <hr class="my-5">
        <div class="row text-center g-4">
            <div class="col-md-4">
                <div class="p-3 bg-white rounded-4 shadow-sm h-100">
                    <h5>🚀 توصيل فوري</h5>
                    <p class="small text-secondary">بطاقات الشحن والكوبونات تصل لبريدك الإلكتروني خلال ثواني.</p>
                </div>
            </div>
            <div class="col-md-4">
                <div class="p-3 bg-white rounded-4 shadow-sm h-100">
                    <h5>💳 دفع آمن</h5>
                    <p class="small text-secondary">ندعم مدى، فيزا، وماستركارد مع حماية 3D Secure.</p>
                </div>
            </div>
            <div class="col-md-4">
                <div class="p-3 bg-white rounded-4 shadow-sm h-100">
                    <h5>🌐 كل الخدمات</h5>
                    <p class="small text-secondary">إذا لم تجد خدمتك، راسلنا ونحن نوفرها لك.</p>
                </div>
            </div>
        </div>
    </div>

    <!-- تذييل الصفحة -->
    <footer class="mt-5 p-4 bg-dark text-white-50 text-center">
        <p>© 2025 متجر الخدمات الإلكترونية الشامل. جميع الحقوق محفوظة.</p>
    </footer>

</body>
</html>
