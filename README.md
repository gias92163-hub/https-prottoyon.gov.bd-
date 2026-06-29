<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>প্রত্যয়ন | অনলাইন সনদপত্র</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
  <style>
    body { font-family: 'Noto Sans Bengali', system-ui, sans-serif; }
    .hero { background: linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.7)), url('https://source.unsplash.com/random/1920x1080/?bangladesh-government') center/cover; }
  </style>
</head>
<body class="bg-gray-50">

<nav class="bg-green-700 text-white py-4">
  <div class="max-w-7xl mx-auto px-6 flex justify-between items-center">
    <div class="flex items-center gap-3">
      <i class="fas fa-certificate text-4xl"></i>
      <div>
        <h1 class="text-3xl font-bold">প্রত্যয়ন</h1>
        <p class="text-xs">সকল সনদ এক ঠিকানায়</p>
      </div>
    </div>
    <div class="flex gap-8">
      <button onclick="navigate('home')" class="hover:underline">হোম</button>
      <button onclick="navigate('services')" class="hover:underline">সেবাসমূহ</button>
      <button onclick="navigate('verify')" class="hover:underline">সনদ যাচাই</button>
      <button onclick="showLogin()" class="bg-white text-green-700 px-6 py-2 rounded-xl font-semibold">লগইন</button>
      <button onclick="showRegister()" class="bg-yellow-400 text-gray-900 px-6 py-2 rounded-xl font-semibold">নিবন্ধন</button>
    </div>
  </div>
</nav>

<!-- HOME -->
<div id="home" class="hero text-white py-32 text-center">
  <h1 class="text-5xl font-bold mb-4">অনলাইন ভিত্তিক সকল সনদপত্র</h1>
  <p class="text-2xl">ইউনিয়ন পরিষদ, পৌরসভা ও সিটি কর্পোরেশনের সেবা</p>
</div>

<!-- SERVICES -->
<div id="services" class="hidden max-w-7xl mx-auto py-12 px-6">
  <h2 class="text-4xl font-bold text-center mb-12">সকল ধরনের সনদ</h2>
  <div class="grid grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4">
    <div class="bg-white p-5 rounded-2xl shadow">চারিত্রিক সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">স্থায়ী বাসিন্দা সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">বার্ষিক আয়ের সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">ওয়ারিশ সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">অবিবাহিত সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">মৃত্যু প্রত্যয়ন</div>
    <div class="bg-white p-5 rounded-2xl shadow">বিধবা প্রত্যয়ন</div>
    <div class="bg-white p-5 rounded-2xl shadow">প্রতিবন্ধী সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">মুক্তিযোদ্ধা প্রত্যয়ন</div>
    <div class="bg-white p-5 rounded-2xl shadow">রোহিঙ্গা নয় প্রত্যয়ন</div>
    <div class="bg-white p-5 rounded-2xl shadow">ট্রেড লাইসেন্স</div>
    <div class="bg-white p-5 rounded-2xl shadow">হোল্ডিং ট্যাক্স</div>
    <div class="bg-white p-5 rounded-2xl shadow">পারিবারিক সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">উত্তরাধিকার সনদ</div>
    <div class="bg-white p-5 rounded-2xl shadow">নিঃসন্তান প্রত্যয়ন</div>
    <div class="bg-white p-5 rounded-2xl shadow">বিবিধ সনদ</div>
  </div>
</div>

<!-- VERIFY -->
<div id="verify" class="hidden max-w-xl mx-auto py-20 px-6">
  <div class="bg-white rounded-3xl shadow-2xl p-12">
    <h2 class="text-4xl font-bold text-center mb-10">সনদ যাচাই করুন</h2>
    <input id="certInput" type="text" placeholder="আবেদন আইডি বা সনদ নং" class="w-full p-6 border-2 rounded-2xl text-xl">
    <button onclick="verifyCertificate()" class="w-full mt-8 bg-green-700 text-white py-6 rounded-2xl text-2xl font-semibold">যাচাই করুন</button>
  </div>
</div>

<!-- DASHBOARD -->
<div id="dashboard" class="hidden flex min-h-screen">
  <div class="w-80 bg-white border-r p-8">
    <h2 class="text-2xl font-bold mb-8">ড্যাশবোর্ড</h2>
    <ul class="space-y-4">
      <li onclick="showTab('profile')" class="cursor-pointer p-4 hover:bg-green-50 rounded-xl">প্রোফাইল</li>
      <li onclick="showTab('apply')" class="cursor-pointer p-4 hover:bg-green-50 rounded-xl">নতুন আবেদন</li>
      <li onclick="showTab('myapps')" class="cursor-pointer p-4 hover:bg-green-50 rounded-xl">আমার আবেদন</li>
      <li onclick="logout()" class="cursor-pointer p-4 text-red-600 hover:bg-red-50 rounded-xl">লগ আউট</li>
    </ul>
  </div>
  <div class="flex-1 p-12">
    <div id="profile" class="tab-content">প্রোফাইল এখানে দেখাবে</div>
    <div id="apply" class="tab-content hidden">
      <h3 class="text-2xl font-bold mb-6">নতুন সনদ আবেদন</h3>
      <select id="serviceSelect" class="w-full p-5 border rounded-2xl text-lg">
        <option>চারিত্রিক সনদ</option>
        <option>স্থায়ী বাসিন্দা সনদ</option>
        <option>আয়ের সনদ</option>
        <option>ওয়ারিশ সনদ</option>
        <option>মৃত্যু প্রত্যয়ন</option>
        <!-- আরও যোগ করা যাবে -->
      </select>
      <button onclick="submitApp()" class="mt-8 w-full bg-green-700 text-white py-6 rounded-2xl text-xl">আবেদন জমা দিন</button>
    </div>
    <div id="myapps" class="tab-content hidden">
      <h3 class="text-2xl font-bold">আমার আবেদনসমূহ</h3>
      <p class="mt-6">কোনো আবেদন পাওয়া যায়নি।</p>
    </div>
  </div>
</div>

<!-- Login & Register Modals -->
<div id="loginModal" class="hidden fixed inset-0 bg-black/70 flex items-center justify-center z-50">
  <div class="bg-white p-10 rounded-3xl w-full max-w-md">
    <h2 class="text-3xl font-bold mb-8 text-center">লগইন</h2>
    <input id="lMobile" class="w-full p-4 border rounded-xl mb-4" placeholder="মোবাইল নম্বর">
    <input id="lPass" type="password" class="w-full p-4 border rounded-xl mb-6" placeholder="পাসওয়ার্ড">
    <button onclick="loginUser()" class="w-full bg-green-700 text-white py-4 rounded-xl">লগইন করুন</button>
  </div>
</div>

<div id="regModal" class="hidden fixed inset-0 bg-black/70 flex items-center justify-center z-50">
  <div class="bg-white p-10 rounded-3xl w-full max-w-md">
    <h2 class="text-3xl font-bold mb-8 text-center">নিবন্ধন</h2>
    <input id="rName" class="w-full p-4 border rounded-xl mb-4" placeholder="নাম">
    <input id="rMobile" class="w-full p-4 border rounded-xl mb-4" placeholder="মোবাইল">
    <input id="rPass" type="password" class="w-full p-4 border rounded-xl mb-6" placeholder="পাসওয়ার্ড">
    <button onclick="registerUser()" class="w-full bg-green-700 text-white py-4 rounded-xl">নিবন্ধন করুন</button>
  </div>
</div>

<script>
  function navigate(page) {
    document.querySelectorAll('#home, #services, #verify, #dashboard').forEach(el => el.classList.add('hidden'));
    document.getElementById(page).classList.remove('hidden');
  }

  function showLogin() { document.getElementById('loginModal').classList.remove('hidden'); }
  function showRegister() { document.getElementById('regModal').classList.remove('hidden'); }

  function registerUser() {
    alert("✅ নিবন্ধন সফল হয়েছে। লগইন করুন।");
    document.getElementById('regModal').classList.add('hidden');
    showLogin();
  }

  function loginUser() {
    alert("✅ লগইন সফল!");
    document.getElementById('loginModal').classList.add('hidden');
    document.getElementById('dashboard').classList.remove('hidden');
  }

  function verifyCertificate() {
    const val = document.getElementById('certInput').value;
    alert(val ? `✅ সনদ ${val} বৈধ` : "আইডি দিন");
  }

  function submitApp() {
    alert("✅ আবেদন জমা দেওয়া হয়েছে!");
  }

  function showTab(tab) {
    document.querySelectorAll('.tab-content').forEach(t => t.classList.add('hidden'));
    document.getElementById(tab).classList.remove('hidden');
  }

  function logout() {
    if(confirm("লগআউট করবেন?")) location.reload();
  }

  // শুরুতে হোম দেখাবে
  navigate('home');
</script>
</body>
</html>
