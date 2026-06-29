<!DOCTYPE html>
<html lang="bn">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>প্রত্যয়ন - সকল সনদ এক ঠিকানায়</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css" rel="stylesheet">
  <style>
    body { font-family: 'Noto Sans Bengali', system-ui, sans-serif; }
    .green-btn { background-color: #15803d; color: white; }
    .green-btn:hover { background-color: #166534; }
    .section { display: none; }
    .active { display: block; }
  </style>
</head>
<body class="bg-gray-50">

  <!-- Navbar -->
  <nav class="bg-green-700 text-white sticky top-0 z-50">
    <div class="max-w-7xl mx-auto px-6 py-4 flex justify-between items-center">
      <div class="flex items-center gap-3">
        <i class="fas fa-certificate text-3xl"></i>
        <h1 class="text-2xl font-bold">প্রত্যয়ন</h1>
      </div>
      <div class="flex gap-6 items-center">
        <button onclick="navigate('home')" class="hover:underline">হোম</button>
        <button onclick="navigate('verify')" class="hover:underline">যাচাই</button>
        <button onclick="showLoginModal()" class="green-btn px-6 py-2 rounded-xl">লগইন</button>
        <button onclick="showRegisterModal()" class="bg-yellow-400 text-gray-900 px-6 py-2 rounded-xl">নিবন্ধন</button>
      </div>
    </div>
  </nav>

  <!-- HOME -->
  <div id="home" class="section active text-center py-28 hero-bg text-white" style="background: linear-gradient(rgba(0,0,0,0.65), rgba(0,0,0,0.75)), url('https://source.unsplash.com/random/1920x1080/?bangladesh') center/cover;">
    <h1 class="text-5xl font-bold mb-6">সকল সনদ এক ঠিকানায়</h1>
    <button onclick="showRegisterModal()" class="green-btn text-xl px-12 py-5 rounded-2xl">নিবন্ধন করুন</button>
  </div>

  <!-- VERIFY -->
  <div id="verify" class="section max-w-2xl mx-auto py-20 px-6">
    <div class="bg-white p-12 rounded-3xl shadow">
      <h2 class="text-3xl font-bold text-center mb-8">সনদ যাচাই করুন</h2>
      <input id="certId" type="text" placeholder="আবেদন আইডি / সনদ নং" class="w-full p-5 border rounded-2xl text-lg">
      <button onclick="verifyCert()" class="green-btn w-full mt-6 py-5 rounded-2xl text-xl">যাচাই করুন</button>
    </div>
  </div>

  <!-- DASHBOARD -->
  <div id="dashboard" class="section hidden flex min-h-screen">
    <div class="w-72 bg-white border-r p-6">
      <h3 class="font-bold text-xl mb-6">মেনু</h3>
      <ul class="space-y-3">
        <li onclick="showDashboardContent('profile')" class="cursor-pointer p-3 hover:bg-green-50 rounded-xl">প্রোফাইল</li>
        <li onclick="showDashboardContent('apply')" class="cursor-pointer p-3 hover:bg-green-50 rounded-xl">নতুন আবেদন</li>
        <li onclick="showDashboardContent('applications')" class="cursor-pointer p-3 hover:bg-green-50 rounded-xl">আমার আবেদন</li>
        <li onclick="logout()" class="cursor-pointer p-3 text-red-600 hover:bg-red-50 rounded-xl">লগআউট</li>
      </ul>
    </div>
    <div class="flex-1 p-10">
      <div id="profile-content">
        <h2 class="text-3xl font-bold mb-8">আমার প্রোফাইল</h2>
        <div class="bg-white p-8 rounded-3xl shadow" id="profileInfo"></div>
      </div>

      <div id="apply-content" class="hidden">
        <h2 class="text-3xl font-bold mb-8">নতুন আবেদন</h2>
        <select id="certType" class="w-full p-5 border rounded-2xl text-lg">
          <option>চারিত্রিক সনদ</option>
          <option>বাসস্থান সনদ</option>
          <option>আয়ের সনদ</option>
        </select>
        <button onclick="submitApplication()" class="green-btn w-full mt-8 py-6 rounded-2xl text-xl">আবেদন জমা দিন</button>
      </div>

      <div id="applications-content" class="hidden">
        <h2 class="text-3xl font-bold mb-8">আমার আবেদনসমূহ</h2>
        <p class="text-gray-600">এখনো কোনো আবেদন নেই।</p>
      </div>
    </div>
  </div>

  <!-- Login Modal -->
  <div id="loginModal" class="hidden fixed inset-0 bg-black/70 flex items-center justify-center z-50">
    <div class="bg-white rounded-3xl p-10 w-full max-w-md">
      <h2 class="text-3xl font-bold text-center mb-8">লগইন করুন</h2>
      <input id="loginMobile" placeholder="মোবাইল নম্বর" class="w-full p-4 border rounded-2xl mb-4">
      <input id="loginPass" type="password" placeholder="পাসওয়ার্ড" class="w-full p-4 border rounded-2xl mb-6">
      <button onclick="doLogin()" class="green-btn w-full py-4 rounded-2xl">লগইন</button>
      <button onclick="hideLoginModal()" class="mt-4 w-full text-gray-500">বন্ধ করুন</button>
    </div>
  </div>

  <!-- Register Modal -->
  <div id="registerModal" class="hidden fixed inset-0 bg-black/70 flex items-center justify-center z-50">
    <div class="bg-white rounded-3xl p-10 w-full max-w-md">
      <h2 class="text-3xl font-bold text-center mb-8">নতুন নিবন্ধন</h2>
      <input id="regName" placeholder="পুরো নাম" class="w-full p-4 border rounded-2xl mb-4">
      <input id="regMobile" placeholder="মোবাইল নম্বর (017...)" class="w-full p-4 border rounded-2xl mb-4">
      <input id="regPass" type="password" placeholder="পাসওয়ার্ড তৈরি করুন" class="w-full p-4 border rounded-2xl mb-6">
      <button onclick="doRegister()" class="green-btn w-full py-4 rounded-2xl">নিবন্ধন করুন</button>
      <button onclick="hideRegisterModal()" class="mt-4 w-full text-gray-500">বন্ধ করুন</button>
    </div>
  </div>

  <script>
    let currentUser = null;

    function navigate(page) {
      document.querySelectorAll('.section').forEach(s => s.classList.remove('active'));
      const el = document.getElementById(page);
      if (el) el.classList.add('active');
    }

    function showLoginModal() { document.getElementById('loginModal').classList.remove('hidden'); }
    function hideLoginModal() { document.getElementById('loginModal').classList.add('hidden'); }
    function showRegisterModal() { document.getElementById('registerModal').classList.remove('hidden'); }
    function hideRegisterModal() { document.getElementById('registerModal').classList.add('hidden'); }

    function doRegister() {
      const name = document.getElementById('regName').value.trim();
      const mobile = document.getElementById('regMobile').value.trim();
      const pass = document.getElementById('regPass').value.trim();

      if (!name || !mobile || !pass) {
        alert("সব তথ্য পূরণ করুন!");
        return;
      }

      const users = JSON.parse(localStorage.getItem('users')) || {};
      users[mobile] = { name, pass, mobile };
      localStorage.setItem('users', JSON.stringify(users));

      alert("✅ নিবন্ধন সফল হয়েছে! এখন লগইন করুন।");
      hideRegisterModal();
      showLoginModal();
    }

    function doLogin() {
      const mobile = document.getElementById('loginMobile').value.trim();
      const pass = document.getElementById('loginPass').value.trim();

      const users = JSON.parse(localStorage.getItem('users')) || {};
      const user = users[mobile];

      if (user && user.pass === pass) {
        currentUser = user;
        hideLoginModal();
        document.getElementById('home').classList.remove('active');
        document.getElementById('dashboard').classList.remove('hidden');
        showDashboardContent('profile');
        showProfile();
      } else {
        alert("❌ ভুল মোবাইল নম্বর অথবা পাসওয়ার্ড!");
      }
    }

    function showProfile() {
      if (!currentUser) return;
      document.getElementById('profileInfo').innerHTML = `
        <p><strong>নাম:</strong> ${currentUser.name}</p>
        <p><strong>মোবাইল:</strong> ${currentUser.mobile}</p>
      `;
    }

    function showDashboardContent(page) {
      document.getElementById('profile-content').classList.add('hidden');
      document.getElementById('apply-content').classList.add('hidden');
      document.getElementById('applications-content').classList.add('hidden');
      document.getElementById(page + '-content').classList.remove('hidden');
    }

    function submitApplication() {
      alert("✅ আবেদন সফলভাবে জমা হয়েছে!");
    }

    function verifyCert() {
      const id = document.getElementById('certId').value;
      if (id) alert(`✅ সনদ নং ${id} বৈধ।`);
      else alert("আইডি দিন");
    }

    function logout() {
      if (confirm("লগআউট করবেন?")) location.reload();
    }

    // শুরুতে হোম দেখাবে
    navigate('home');
  </script>
</body>
</html>
