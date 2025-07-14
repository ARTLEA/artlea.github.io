<!DOCTYPE html>
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
