
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Made By Me | منصة للمبدعين العرب</title>
  <meta name="description" content="أنشئ متجرك الرقمي وابدأ بيع تصاميمك مع شهر مجاني – لا تفوّت الفرصة!" />
  <!-- TailwindCSS CDN + aspect ratio plugin -->
  <script src="https://cdn.tailwindcss.com?plugins=aspect-ratio"></script>
  <!-- Google Font Tajawal -->
  <link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;700&display=swap" rel="stylesheet">
  <style>body{font-family:'Tajawal',sans-serif;}</style>
</head>
<body class="bg-gray-50 text-gray-800">
  <!-- COUNTDOWN BAR (فوق كل شيء) -->
  <div id="countdownBar" class="bg-orange-600 text-white text-center py-1 text-sm"></div>

  <!-- FOMO BANNER -->
  <div class="bg-orange-500 text-white text-center py-3">
    <p class="m-0 text-base sm:text-lg font-semibold">🎉 احصل على شهر مجانًا الآن وابدأ في إنشاء وبيع تصاميمك على المنصة!</p>
  </div>

  <!-- Navbar -->
  <header class="bg-white shadow-sm sticky top-0 z-40">
    <div class="container mx-auto px-4 py-4 flex justify-between items-center">
      <a href="#" class="text-2xl font-bold text-indigo-600">Made By Me</a>
      <a href="#subscribe" class="bg-indigo-600 text-white px-4 py-2 rounded-lg shadow hover:bg-indigo-500 transition whitespace-nowrap">انضم الآن</a>
    </div>
  </header>

  <!-- Hero Section -->
  <section class="bg-indigo-600 text-white">
    <div class="container mx-auto px-6 sm:px-4 py-16 sm:py-24 text-center">
      <h1 class="text-3xl sm:text-4xl md:text-5xl font-bold mb-4 leading-tight">منصتك العربية لبيع الإبداع الرقمي</h1>
      <p class="text-base sm:text-lg md:text-xl max-w-2xl mx-auto">حوِّل تصاميمك إلى دخل مستمر — ارفع منتجاتك واترك البقية لـ <span class="font-semibold">Made By Me</span> لتسويقها وتتبع مبيعاتك تلقائيًا.</p>
      <a href="#subscribe" class="mt-8 inline-block bg-white text-indigo-600 px-6 py-3 rounded-lg font-semibold shadow hover:bg-gray-100 transition">ابدأ الآن مجانًا</a>
    </div>
  </section>

  <!-- FAQ Section -->
  <section class="bg-white py-16 px-4 sm:px-6 lg:px-8">
    <div class="max-w-4xl mx-auto text-center">
      <h2 class="text-2xl sm:text-3xl font-bold mb-8 text-indigo-600">الأسئلة الشائعة</h2>
      <div class="text-right space-y-6">
        <div>
          <h3 class="text-lg font-semibold text-gray-800">ما هي منصة Made By Me؟</h3>
          <p class="text-gray-600">منصة عربية تتيح للمصممين والمبدعين إنشاء متاجر رقمية وبيع تصاميمهم بسهولة مع أدوات تسويق ودعم مدمجة.</p>
        </div>
        <div>
          <h3 class="text-lg font-semibold text-gray-800">ما هي العمولة على كل عملية بيع؟</h3>
          <p class="text-gray-600">5% فقط، وتقل في الخطط المدفوعة.</p>
        </div>
        <div>
          <h3 class="text-lg font-semibold text-gray-800">كيف أسحب أرباحي؟</h3>
          <p class="text-gray-600">يتم السحب يدويًا عبر التحويل البنكي.</p>
        </div>
        <div>
          <h3 class="text-lg font-semibold text-gray-800">هل يمكنني تجربة المنصة مجانًا؟</h3>
          <p class="text-gray-600">نعم، الخطة المجانية تتيح لك إنشاء متجر ورفع حتى 3 تصاميم لمدة شهر كامل.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Subscribe Section -->
  <section id="subscribe" class="bg-indigo-50 py-16 px-4 sm:px-6 lg:px-8">
    <div class="max-w-xl mx-auto text-center">
      <h2 class="text-xl sm:text-2xl font-bold text-indigo-600 mb-4">انضم الآن واحصل على شهر مجاني!</h2>
      <p class="text-gray-700 mb-6">أدخل بريدك الإلكتروني وسنرسل لك دعوة للانضمام للمنصة فور إطلاقها.</p>
      <form class="flex flex-col sm:flex-row gap-4 justify-center">
        <input type="email" required placeholder="بريدك الإلكتروني" class="w-full sm:w-auto px-4 py-3 rounded-lg border border-gray-300 focus:outline-none focus:ring-2 focus:ring-indigo-500">
        <button type="submit" class="bg-indigo-600 text-white px-6 py-3 rounded-lg font-semibold shadow hover:bg-indigo-500 transition">سجّل الآن</button>
      </form>
    </div>
  </section>

  <!-- Scripts -->
  <script>
    // إعداد العد التنازلي لمدة 15 يومًا
    const deadline = new Date(Date.now() + 15 * 24 * 60 * 60 * 1000);
    function updateCountdown() {
      const now = new Date();
      const diff = deadline - now;
      const bar = document.getElementById('countdownBar');
      if (diff <= 0) {
        bar.textContent = 'انتهى العرض!';
        return;
      }
      const days = Math.floor(diff / (1000 * 60 * 60 * 24));
      const hours = Math.floor((diff / (1000 * 60 * 60)) % 24);
      const minutes = Math.floor((diff / (1000 * 60)) % 60);
      const seconds = Math.floor((diff / 1000) % 60);
      bar.textContent = `${days} يوم : ${hours} ساعة : ${minutes} دقيقة : ${seconds} ثانية`;
    }
    updateCountdown();
    setInterval(updateCountdown, 1000);
  </script>
</body>
</html>
