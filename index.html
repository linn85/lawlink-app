<html lang="id" class="scroll-smooth" >
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>LawLink - Jasa Hukum & Notaris Digital</title>
<script src="https://cdn.tailwindcss.com"></script>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" />
<style>
  /* Custom scrollbar for chat */
  .chat-scroll::-webkit-scrollbar {
    width: 6px;
  }
  .chat-scroll::-webkit-scrollbar-thumb {
    background-color: #3F51B5;
    border-radius: 3px;
  }
  /* Smooth fade in/out */
  .fade-enter {
    opacity: 0;
    transform: translateY(10px);
  }
  .fade-enter-active {
    opacity: 1;
    transform: translateY(0);
    transition: opacity 300ms, transform 300ms;
  }
  .fade-exit {
    opacity: 1;
    transform: translateY(0);
  }
  .fade-exit-active {
    opacity: 0;
    transform: translateY(10px);
    transition: opacity 300ms, transform 300ms;
  }
</style>
</head>
<body class="bg-gray-50 font-sans text-gray-800 min-h-screen flex flex-col">

<!-- Root container for all pages -->
<div id="app" class="flex-grow flex flex-col relative overflow-hidden">

<!-- Pages will be injected here -->

</div>

<script>
(() => {
  // Constants
  const PRIMARY_COLOR = '#3F51B5';
  const ACCENT_COLOR = '#FFD700';
  const SESSION_TIMEOUT_MINUTES = 15;

  // Data storage keys
  const STORAGE_KEYS = {
    USERS: 'lawlink_users',
    SESSION: 'lawlink_session',
    APPOINTMENTS: 'lawlink_appointments',
    DOCUMENTS: 'lawlink_documents',
    CHATS: 'lawlink_chats',
    BLOGS: 'lawlink_blogs',
    LAWYERS: 'lawlink_lawyers',
    NOTARIS: 'lawlink_notaris',
  };

  // Initial data for lawyers, notaris, blogs
  const initialLawyers = [
    {
      id: 'lawyer1',
      name: 'Andi Prasetyo',
      specialization: 'Hukum Perdata',
      photo: 'https://placehold.co/150x150/png?text=Andi+Prasetyo',
    },
    {
      id: 'lawyer2',
      name: 'Sari Dewi',
      specialization: 'Hukum Pidana',
      photo: 'https://placehold.co/150x150/png?text=Sari+Dewi',
    },
    {
      id: 'lawyer3',
      name: 'Budi Santoso',
      specialization: 'Hukum Bisnis',
      photo: 'https://placehold.co/150x150/png?text=Budi+Santoso',
    },
    {
      id: 'lawyer4',
      name: 'Rina Wulandari',
      specialization: 'Hukum Keluarga',
      photo: 'https://placehold.co/150x150/png?text=Rina+Wulandari',
    },
  ];

  const initialNotaris = [
    {
      id: 'notaris1',
      name: 'Dewi Kartika',
      specialization: 'Akta Notaris',
      photo: 'https://placehold.co/150x150/png?text=Dewi+Kartika',
    },
    {
      id: 'notaris2',
      name: 'Joko Susilo',
      specialization: 'PPAT & Legalisasi',
      photo: 'https://placehold.co/150x150/png?text=Joko+Susilo',
    },
  ];

  const initialBlogs = [
    {
      id: 'blog1',
      title: 'Prosedur Pembuatan Surat Kuasa',
      preview: 'Langkah-langkah mudah untuk membuat surat kuasa secara legal.',
      thumbnail: 'https://placehold.co/400x250/png?text=Surat+Kuasa',
      content: 'Isi lengkap artikel prosedur pembuatan surat kuasa...',
    },
    {
      id: 'blog2',
      title: 'Tips Memilih Lawyer Profesional',
      preview: 'Cara memilih lawyer yang tepat untuk kebutuhan hukum Anda.',
      thumbnail: 'https://placehold.co/400x250/png?text=Tips+Lawyer',
      content: 'Isi lengkap artikel tips memilih lawyer profesional...',
    },
    {
      id: 'blog3',
      title: 'Manfaat Jasa Notaris untuk Dokumen Anda',
      preview: 'Kenali pentingnya notaris dalam pengurusan dokumen legal.',
      thumbnail: 'https://placehold.co/400x250/png?text=Jasa+Notaris',
      content: 'Isi lengkap artikel manfaat jasa notaris...',
    },
  ];

  // Utility functions
  function saveToStorage(key, data) {
    localStorage.setItem(key, JSON.stringify(data));
  }
  function loadFromStorage(key) {
    const data = localStorage.getItem(key);
    return data ? JSON.parse(data) : null;
  }
  function generateId(prefix = '') {
    return prefix + Math.random().toString(36).substr(2, 9);
  }
  function validateEmail(email) {
    const re = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
    return re.test(email);
  }
  function validatePhone(phone) {
    const re = /^[0-9]{6,15}$/;
    return re.test(phone);
  }
  function validatePassword(password) {
    // Minimum 8 chars, at least one uppercase, one lowercase, one number
    const re = /^(?=.*[a-z])(?=.*[A-Z])(?=.*\d).{8,}$/;
    return re.test(password);
  }
  function formatDate(date) {
    return date.toLocaleDateString('id-ID', { year: 'numeric', month: 'long', day: 'numeric' });
  }
  function formatTime(date) {
    return date.toLocaleTimeString('id-ID', { hour: '2-digit', minute: '2-digit' });
  }
  function debounce(func, wait) {
    let timeout;
    return function(...args) {
      clearTimeout(timeout);
      timeout = setTimeout(() => func.apply(this, args), wait);
    };
  }

  // Session management
  let session = loadFromStorage(STORAGE_KEYS.SESSION);
  if (session && session.lastActive) {
    const lastActive = new Date(session.lastActive);
    const now = new Date();
    const diffMinutes = (now - lastActive) / 60000;
    if (diffMinutes > SESSION_TIMEOUT_MINUTES) {
      session = null;
      localStorage.removeItem(STORAGE_KEYS.SESSION);
    }
  } else {
    session = null;
  }

  // Initialize data if not present
  if (!loadFromStorage(STORAGE_KEYS.LAWYERS)) {
    saveToStorage(STORAGE_KEYS.LAWYERS, initialLawyers);
  }
  if (!loadFromStorage(STORAGE_KEYS.NOTARIS)) {
    saveToStorage(STORAGE_KEYS.NOTARIS, initialNotaris);
  }
  if (!loadFromStorage(STORAGE_KEYS.BLOGS)) {
    saveToStorage(STORAGE_KEYS.BLOGS, initialBlogs);
  }
  if (!loadFromStorage(STORAGE_KEYS.USERS)) {
    // Create a default client user for demo
    saveToStorage(STORAGE_KEYS.USERS, [
      {
        id: 'user1',
        name: 'Client Demo',
        email: 'client@lawlink.com',
        phone: '081234567890',
        password: 'DemoPass123', // plaintext for demo only
        role: 'client',
      },
      {
        id: 'lawyer1',
        name: 'Andi Prasetyo',
        email: 'andi@lawlink.com',
        phone: '081111111111',
        password: 'DemoPass123',
        role: 'lawyer',
      },
      {
        id: 'notaris1',
        name: 'Dewi Kartika',
        email: 'dewi@lawlink.com',
        phone: '082222222222',
        password: 'DemoPass123',
        role: 'notaris',
      },
    ]);
  }
  if (!loadFromStorage(STORAGE_KEYS.APPOINTMENTS)) {
    saveToStorage(STORAGE_KEYS.APPOINTMENTS, []);
  }
  if (!loadFromStorage(STORAGE_KEYS.DOCUMENTS)) {
    saveToStorage(STORAGE_KEYS.DOCUMENTS, []);
  }
  if (!loadFromStorage(STORAGE_KEYS.CHATS)) {
    saveToStorage(STORAGE_KEYS.CHATS, []);
  }

  // Global state
  let currentPage = 'splash'; // splash, onboarding, login, register, main-client, main-lawyer, main-notaris, consultation, notaris-service, legal-documents, profile, schedule, cases, notifications, history, chat, document-request, blog-detail, etc.
  let onboardingSlide = 0;
  let authMode = 'login'; // login or register
  let currentUser = session ? session.user : null;
  let inactivityTimer = null;
  let chatCurrentSessionId = null; // for chat page
  let chatCurrentWithUserId = null; // chatting with whom

  // DOM references
  const app = document.getElementById('app');

  // Helper: Clear app content
  function clearApp() {
    app.innerHTML = '';
  }

  // Helper: Show notification
  function showNotification(message, type = 'success') {
    // type: success, error, info
    const colors = {
      success: 'bg-green-500',
      error: 'bg-red-500',
      info: 'bg-blue-500',
    };
    const notif = document.createElement('div');
    notif.className = `fixed top-5 left-1/2 transform -translate-x-1/2 px-6 py-3 rounded shadow-lg text-white font-semibold z-50 ${colors[type]} animate-fade-in-out`;
    notif.textContent = message;
    document.body.appendChild(notif);
    setTimeout(() => {
      notif.classList.add('opacity-0');
      setTimeout(() => {
        notif.remove();
      }, 500);
    }, 3000);
  }

  // Helper: Loading spinner component
  function loadingSpinner(size = 6, color = PRIMARY_COLOR) {
    return `
      <svg class="animate-spin h-${size} w-${size} text-[${color}]" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
        <circle class="opacity-25" cx="12" cy="12" r="10" stroke="${color}" stroke-width="4"></circle>
        <path class="opacity-75" fill="${color}" d="M4 12a8 8 0 018-8v4a4 4 0 00-4 4H4z"></path>
      </svg>
    `;
  }

  // Helper: Create element with classes and attributes
  function createElement(tag, options = {}) {
    const el = document.createElement(tag);
    if (options.classes) el.className = options.classes;
    if (options.attrs) {
      for (const [k, v] of Object.entries(options.attrs)) {
        el.setAttribute(k, v);
      }
    }
    if (options.html) el.innerHTML = options.html;
    if (options.text) el.textContent = options.text;
    return el;
  }

  // Helper: Update session last active time
  function updateSessionActivity() {
    if (!currentUser) return;
    session.lastActive = new Date().toISOString();
    saveToStorage(STORAGE_KEYS.SESSION, session);
  }

  // Helper: Set inactivity timer
  function resetInactivityTimer() {
    if (inactivityTimer) clearTimeout(inactivityTimer);
    inactivityTimer = setTimeout(() => {
      logout(true);
    }, SESSION_TIMEOUT_MINUTES * 60 * 1000);
  }

  // Logout function
  function logout(auto = false) {
    currentUser = null;
    session = null;
    localStorage.removeItem(STORAGE_KEYS.SESSION);
    showNotification(auto ? 'Sesi Anda telah habis. Silakan masuk kembali.' : 'Berhasil logout.', auto ? 'info' : 'success');
    navigateTo('login');
  }

  // Navigation function
  function navigateTo(page, options = {}) {
    currentPage = page;
    clearApp();
    updateSessionActivity();
    resetInactivityTimer();
    switch (page) {
      case 'splash': renderSplash(); break;
      case 'onboarding': renderOnboarding(); break;
      case 'login': renderAuth('login'); break;
      case 'register': renderAuth('register'); break;
      case 'main-client': renderMainClient(); break;
      case 'main-lawyer': renderMainLawyer(); break;
      case 'main-notaris': renderMainNotaris(); break;
      case 'consultation': renderConsultation(); break;
      case 'notaris-service': renderNotarisService(); break;
      case 'legal-documents': renderLegalDocuments(); break;
      case 'profile': renderProfile(); break;
      case 'schedule': renderSchedule(); break;
      case 'cases': renderCases(); break;
      case 'notifications': renderNotifications(); break;
      case 'history': renderHistory(); break;
      case 'chat': renderChat(options.withUserId); break;
      case 'document-request': renderDocumentRequest(); break;
      case 'blog-detail': renderBlogDetail(options.blogId); break;
      default:
        app.innerHTML = `<div class="p-6 text-center text-red-600 font-bold">Halaman tidak ditemukan: ${page}</div>`;
    }
  }

  // Splash Screen (3 seconds then redirect to onboarding)
  function renderSplash() {
    const container = createElement('div', { classes: 'flex flex-col items-center justify-center h-full min-h-screen bg-white' });
    // Logo placeholder
    const logo = createElement('img', {
      attrs: { src: 'Lawlink new logo.png', alt: 'Logo aplikasi LawLink' },
      classes: 'mb-8 w-48 h-auto object-contain',
    });
    container.appendChild(logo);
    // Loading spinner
    const spinner = createElement('div', { classes: 'animate-spin border-4 border-t-[3F51B5] border-gray-300 rounded-full w-12 h-12 border-t-blue-700' });
    spinner.innerHTML = `
      <svg class="animate-spin h-12 w-12 text-[${PRIMARY_COLOR}]" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24">
        <circle class="opacity-25" cx="12" cy="12" r="10" stroke="${PRIMARY_COLOR}" stroke-width="4"></circle>
        <path class="opacity-75" fill="${PRIMARY_COLOR}" d="M4 12a8 8 0 018-8v4a4 4 0 00-4 4H4z"></path>
      </svg>
    `;
    container.appendChild(spinner);
    app.appendChild(container);

    setTimeout(() => {
      navigateTo('onboarding');
    }, 3000);
  }

  // Onboarding slides data
  const onboardingSlides = [
    {
      title: 'Solusi Hukum & Notaris Digital',
      description: 'Menyediakan layanan hukum dan notaris secara digital dengan mudah dan terpercaya.',
      image: 'https://placehold.co/400x300/png?text=Ilustrasi+Hukum+Digital',
      alt: 'Ilustrasi digital hukum dengan simbol timbangan keadilan dan dokumen digital',
    },
    {
      title: 'Konsultasi Lawyer & Notaris Profesional',
      description: 'Konsultasi langsung dengan lawyer dan notaris berpengalaman dan profesional.',
      image: 'https://placehold.co/400x300/png?text=Ikon+Konsultasi+Profesional',
      alt: 'Ikon dua orang sedang berdiskusi dengan latar belakang simbol hukum',
    },
    {
      title: 'Dokumen Legal & Akta Notaris',
      description: 'Akses dan pengurusan dokumen legal serta akta notaris dengan mudah dan cepat.',
      image: 'https://placehold.co/400x300/png?text=Ikon+Dokumen+Legal',
      alt: 'Ikon dokumen legal dengan segel resmi dan pena tanda tangan',
    },
  ];

  // Onboarding page
  function renderOnboarding() {
    const container = createElement('div', { classes: 'flex flex-col h-full min-h-screen bg-white p-6' });

    // Slide container
    const slideContainer = createElement('div', { classes: 'flex-1 flex flex-col items-center justify-center text-center' });

    function renderSlide(index) {
      slideContainer.innerHTML = '';
      const slide = onboardingSlides[index];
      const img = createElement('img', {
        attrs: { src: slide.image, alt: slide.alt },
        classes: 'mx-auto mb-6 max-w-full h-auto rounded-lg shadow-md',
      });
      const title = createElement('h2', { classes: 'text-2xl font-bold text-[${PRIMARY_COLOR}] mb-2', text: slide.title });
      const desc = createElement('p', { classes: 'text-gray-700 text-base max-w-md mx-auto', text: slide.description });
      slideContainer.appendChild(img);
      slideContainer.appendChild(title);
      slideContainer.appendChild(desc);
    }

    renderSlide(onboardingSlide);

    // Navigation dots
    const dotsContainer = createElement('div', { classes: 'flex justify-center space-x-2 mt-6' });
    onboardingSlides.forEach((_, i) => {
      const dot = createElement('button', {
        classes: `w-3 h-3 rounded-full focus:outline-none ${i === onboardingSlide ? 'bg-[${PRIMARY_COLOR}]' : 'bg-gray-300'}`,
        attrs: { 'aria-label': `Slide ${i + 1}` },
      });
      dot.addEventListener('click', () => {
        onboardingSlide = i;
        renderSlide(onboardingSlide);
        updateDots();
        updateButtons();
      });
      dotsContainer.appendChild(dot);
    });

    function updateDots() {
      Array.from(dotsContainer.children).forEach((dot, i) => {
        dot.className = `w-3 h-3 rounded-full focus:outline-none ${i === onboardingSlide ? 'bg-[${PRIMARY_COLOR}]' : 'bg-gray-300'}`;
      });
    }

    // Buttons container
    const buttonsContainer = createElement('div', { classes: 'flex justify-between mt-8' });

    const skipBtn = createElement('button', {
      classes: 'text-[${PRIMARY_COLOR}] font-semibold hover:underline focus:outline-none',
      text: 'Skip',
    });
    skipBtn.addEventListener('click', () => {
      navigateTo('login');
    });

    const nextBtn = createElement('button', {
      classes: 'bg-[${PRIMARY_COLOR}] text-white px-4 py-2 rounded hover:bg-blue-700 focus:outline-none',
      text: 'Next',
    });

    const getStartedBtn = createElement('button', {
      classes: 'bg-[${ACCENT_COLOR}] text-gray-900 px-4 py-2 rounded hover:bg-yellow-400 focus:outline-none hidden',
      text: 'Get Started',
    });

    nextBtn.addEventListener('click', () => {
      if (onboardingSlide < onboardingSlides.length - 1) {
        onboardingSlide++;
        renderSlide(onboardingSlide);
        updateDots();
        updateButtons();
      }
    });

    getStartedBtn.addEventListener('click', () => {
      navigateTo('login');
    });

    function updateButtons() {
      if (onboardingSlide === onboardingSlides.length - 1) {
        nextBtn.classList.add('hidden');
        getStartedBtn.classList.remove('hidden');
      } else {
        nextBtn.classList.remove('hidden');
        getStartedBtn.classList.add('hidden');
      }
    }

    updateButtons();

    buttonsContainer.appendChild(skipBtn);
    buttonsContainer.appendChild(nextBtn);
    buttonsContainer.appendChild(getStartedBtn);

    container.appendChild(slideContainer);
    container.appendChild(dotsContainer);
    container.appendChild(buttonsContainer);

    app.appendChild(container);
  }

  // Authentication page (login/register)
  function renderAuth(mode) {
    authMode = mode;
    const container = createElement('div', { classes: 'flex flex-col min-h-screen justify-center items-center bg-white p-6' });

    const card = createElement('div', { classes: 'w-full max-w-md bg-white shadow-lg rounded-lg p-8' });

    const title = createElement('h1', { classes: 'text-3xl font-bold mb-6 text-[${PRIMARY_COLOR}] text-center', text: mode === 'login' ? 'Masuk ke LawLink' : 'Daftar Akun LawLink' });
    card.appendChild(title);

    // Form
    const form = createElement('form', { classes: 'space-y-4' });

    // Name (register only)
    let inputName;
    if (mode === 'register') {
      const nameGroup = createElement('div', { classes: 'flex flex-col' });
      const label = createElement('label', { classes: 'mb-1 font-semibold', text: 'Nama Lengkap' });
      inputName = createElement('input', {
        classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
        attrs: { type: 'text', placeholder: 'Masukkan nama lengkap', required: 'required', id: 'inputName' },
      });
      const error = createElement('p', { classes: 'text-red-600 text-sm mt-1 hidden', text: 'Nama lengkap wajib diisi.' });
      nameGroup.appendChild(label);
      nameGroup.appendChild(inputName);
      nameGroup.appendChild(error);
      form.appendChild(nameGroup);
    }

    // Email/Phone
    const inputEmailPhoneGroup = createElement('div', { classes: 'flex flex-col' });
    const labelEmailPhone = createElement('label', { classes: 'mb-1 font-semibold', text: 'Email atau Nomor Telepon' });
    const inputEmailPhone = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'text', placeholder: 'Masukkan email atau nomor telepon', required: 'required', id: 'inputEmailPhone' },
    });
    const errorEmailPhone = createElement('p', { classes: 'text-red-600 text-sm mt-1 hidden', text: 'Format email atau nomor telepon tidak valid.' });
    inputEmailPhoneGroup.appendChild(labelEmailPhone);
    inputEmailPhoneGroup.appendChild(inputEmailPhone);
    inputEmailPhoneGroup.appendChild(errorEmailPhone);
    form.appendChild(inputEmailPhoneGroup);

    // Password
    const inputPasswordGroup = createElement('div', { classes: 'flex flex-col relative' });
    const labelPassword = createElement('label', { classes: 'mb-1 font-semibold', text: 'Password' });
    const inputPassword = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 pr-10 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'password', placeholder: 'Masukkan password', required: 'required', id: 'inputPassword' },
    });
    const togglePasswordBtn = createElement('button', {
      classes: 'absolute right-3 top-9 text-gray-500 focus:outline-none',
      attrs: { type: 'button', 'aria-label': 'Toggle password visibility' },
      html: '<i class="fas fa-eye"></i>',
    });
    const errorPassword = createElement('p', { classes: 'text-red-600 text-sm mt-1 hidden', text: 'Password tidak valid.' });
    inputPasswordGroup.appendChild(labelPassword);
    inputPasswordGroup.appendChild(inputPassword);
    inputPasswordGroup.appendChild(togglePasswordBtn);
    inputPasswordGroup.appendChild(errorPassword);
    form.appendChild(inputPasswordGroup);

    // Confirm password (register only)
    let inputConfirmPassword, errorConfirmPassword;
    if (mode === 'register') {
      const confirmGroup = createElement('div', { classes: 'flex flex-col relative' });
      const labelConfirm = createElement('label', { classes: 'mb-1 font-semibold', text: 'Konfirmasi Password' });
      inputConfirmPassword = createElement('input', {
        classes: 'border border-gray-300 rounded px-3 py-2 pr-10 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
        attrs: { type: 'password', placeholder: 'Konfirmasi password', required: 'required', id: 'inputConfirmPassword' },
      });
      const toggleConfirmBtn = createElement('button', {
        classes: 'absolute right-3 top-9 text-gray-500 focus:outline-none',
        attrs: { type: 'button', 'aria-label': 'Toggle confirm password visibility' },
        html: '<i class="fas fa-eye"></i>',
      });
      errorConfirmPassword = createElement('p', { classes: 'text-red-600 text-sm mt-1 hidden', text: 'Password konfirmasi tidak cocok.' });
      confirmGroup.appendChild(labelConfirm);
      confirmGroup.appendChild(inputConfirmPassword);
      confirmGroup.appendChild(toggleConfirmBtn);
      confirmGroup.appendChild(errorConfirmPassword);
      form.appendChild(confirmGroup);

      toggleConfirmBtn.addEventListener('click', (e) => {
        e.preventDefault();
        if (inputConfirmPassword.type === 'password') {
          inputConfirmPassword.type = 'text';
          toggleConfirmBtn.innerHTML = '<i class="fas fa-eye-slash"></i>';
        } else {
          inputConfirmPassword.type = 'password';
          toggleConfirmBtn.innerHTML = '<i class="fas fa-eye"></i>';
        }
      });
    }

    // Show/hide password toggle
    togglePasswordBtn.addEventListener('click', (e) => {
      e.preventDefault();
      if (inputPassword.type === 'password') {
        inputPassword.type = 'text';
        togglePasswordBtn.innerHTML = '<i class="fas fa-eye-slash"></i>';
      } else {
        inputPassword.type = 'password';
        togglePasswordBtn.innerHTML = '<i class="fas fa-eye"></i>';
      }
    });

    // Role selection (register only)
    let roleSelect;
    if (mode === 'register') {
      const roleGroup = createElement('div', { classes: 'flex flex-col' });
      const labelRole = createElement('label', { classes: 'mb-1 font-semibold', text: 'Jenis Pengguna' });
      roleSelect = createElement('select', {
        classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
        attrs: { id: 'roleSelect' },
      });
      ['Klien', 'Lawyer', 'Notaris'].forEach((role) => {
        const option = createElement('option', { attrs: { value: role.toLowerCase() }, text: role });
        if (role === 'Klien') option.selected = true;
        roleSelect.appendChild(option);
      });
      roleGroup.appendChild(labelRole);
      roleGroup.appendChild(roleSelect);
      form.appendChild(roleGroup);
    }

    // Terms & conditions checkbox (register only)
    let termsCheckbox, errorTerms;
    if (mode === 'register') {
      const termsGroup = createElement('div', { classes: 'flex items-center space-x-2 mt-2' });
      termsCheckbox = createElement('input', {
        classes: '',
        attrs: { type: 'checkbox', id: 'termsCheckbox', required: 'required' },
      });
      const termsLabel = createElement('label', { classes: 'text-sm', html: 'Saya setuju dengan <a href="#" class="text-[${PRIMARY_COLOR}] underline">Syarat & Ketentuan</a>' });
      errorTerms = createElement('p', { classes: 'text-red-600 text-sm mt-1 hidden', text: 'Anda harus menyetujui syarat & ketentuan.' });
      termsGroup.appendChild(termsCheckbox);
      termsGroup.appendChild(termsLabel);
      form.appendChild(termsGroup);
      form.appendChild(errorTerms);
    }

    // Submit button
    const submitBtn = createElement('button', {
      classes: `w-full bg-[${PRIMARY_COLOR}] text-white py-2 rounded font-semibold hover:bg-blue-700 focus:outline-none flex justify-center items-center`,
      attrs: { type: 'submit' },
      text: mode === 'login' ? 'Masuk' : 'Daftar',
    });

    form.appendChild(submitBtn);

    // Links
    const linksContainer = createElement('div', { classes: 'mt-4 text-center text-sm text-gray-600' });
    if (mode === 'login') {
      const forgotLink = createElement('a', { classes: 'text-[${PRIMARY_COLOR}] hover:underline cursor-pointer mr-4', text: 'Lupa password?' });
      forgotLink.addEventListener('click', (e) => {
        e.preventDefault();
        alert('Fitur lupa password belum tersedia.');
      });
      const registerLink = createElement('a', { classes: 'text-[${PRIMARY_COLOR}] hover:underline cursor-pointer', text: 'Belum punya akun? Daftar' });
      registerLink.addEventListener('click', (e) => {
        e.preventDefault();
        navigateTo('register');
      });
      linksContainer.appendChild(forgotLink);
      linksContainer.appendChild(registerLink);
    } else {
      const loginLink = createElement('a', { classes: 'text-[${PRIMARY_COLOR}] hover:underline cursor-pointer', text: 'Sudah punya akun? Masuk' });
      loginLink.addEventListener('click', (e) => {
        e.preventDefault();
        navigateTo('login');
      });
      linksContainer.appendChild(loginLink);
    }

    card.appendChild(form);
    card.appendChild(linksContainer);
    container.appendChild(card);
    app.appendChild(container);

    // Validation and form handling
    function validateInputs() {
      let valid = true;
      // Name
      if (mode === 'register') {
        if (!inputName.value.trim()) {
          inputName.nextElementSibling.classList.remove('hidden');
          valid = false;
        } else {
          inputName.nextElementSibling.classList.add('hidden');
        }
      }
      // Email/Phone
      const val = inputEmailPhone.value.trim();
      if (!(validateEmail(val) || validatePhone(val))) {
        errorEmailPhone.classList.remove('hidden');
        valid = false;
      } else {
        errorEmailPhone.classList.add('hidden');
      }
      // Password
      if (mode === 'register') {
        if (!validatePassword(inputPassword.value)) {
          errorPassword.textContent = 'Password minimal 8 karakter, mengandung huruf besar, kecil, dan angka.';
          errorPassword.classList.remove('hidden');
          valid = false;
        } else {
          errorPassword.classList.add('hidden');
        }
      } else {
        if (!inputPassword.value) {
          errorPassword.textContent = 'Password wajib diisi.';
          errorPassword.classList.remove('hidden');
          valid = false;
        } else {
          errorPassword.classList.add('hidden');
        }
      }
      // Confirm password
      if (mode === 'register') {
        if (inputConfirmPassword.value !== inputPassword.value) {
          errorConfirmPassword.classList.remove('hidden');
          valid = false;
        } else {
          errorConfirmPassword.classList.add('hidden');
        }
      }
      // Terms
      if (mode === 'register') {
        if (!termsCheckbox.checked) {
          errorTerms.classList.remove('hidden');
          valid = false;
        } else {
          errorTerms.classList.add('hidden');
        }
      }
      return valid;
    }

    // Real-time validation
    if (mode === 'register' && inputName) {
      inputName.addEventListener('input', () => {
        if (inputName.value.trim()) inputName.nextElementSibling.classList.add('hidden');
      });
    }
    inputEmailPhone.addEventListener('input', () => {
      if (validateEmail(inputEmailPhone.value.trim()) || validatePhone(inputEmailPhone.value.trim())) errorEmailPhone.classList.add('hidden');
    });
    inputPassword.addEventListener('input', () => {
      if (mode === 'register') {
        if (validatePassword(inputPassword.value)) errorPassword.classList.add('hidden');
      } else {
        if (inputPassword.value) errorPassword.classList.add('hidden');
      }
    });
    if (mode === 'register' && inputConfirmPassword) {
      inputConfirmPassword.addEventListener('input', () => {
        if (inputConfirmPassword.value === inputPassword.value) errorConfirmPassword.classList.add('hidden');
      });
    }
    if (mode === 'register' && termsCheckbox) {
      termsCheckbox.addEventListener('change', () => {
        if (termsCheckbox.checked) errorTerms.classList.add('hidden');
      });
    }

    // Submit handler
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      if (!validateInputs()) return;

      submitBtn.disabled = true;
      submitBtn.innerHTML = `<i class="fas fa-spinner fa-spin mr-2"></i>${mode === 'login' ? 'Masuk' : 'Daftar'}...`;

      setTimeout(() => {
        if (mode === 'login') {
          // Login process
          const users = loadFromStorage(STORAGE_KEYS.USERS) || [];
          const val = inputEmailPhone.value.trim();
          const user = users.find(u => (u.email === val || u.phone === val) && u.password === inputPassword.value);
          if (user) {
            currentUser = user;
            session = { user: user, lastActive: new Date().toISOString() };
            saveToStorage(STORAGE_KEYS.SESSION, session);
            showNotification('Berhasil masuk!', 'success');
            if (user.role === 'client') navigateTo('main-client');
            else if (user.role === 'lawyer') navigateTo('main-lawyer');
            else if (user.role === 'notaris') navigateTo('main-notaris');
          } else {
            showNotification('Email/Telepon atau password salah.', 'error');
            submitBtn.disabled = false;
            submitBtn.textContent = 'Masuk';
          }
        } else {
          // Register process
          const users = loadFromStorage(STORAGE_KEYS.USERS) || [];
          const val = inputEmailPhone.value.trim();
          if (users.find(u => u.email === val || u.phone === val)) {
            showNotification('Email atau nomor telepon sudah terdaftar.', 'error');
            submitBtn.disabled = false;
            submitBtn.textContent = 'Daftar';
            return;
          }
          const newUser = {
            id: generateId('user_'),
            name: inputName.value.trim(),
            email: validateEmail(val) ? val : '',
            phone: validatePhone(val) ? val : '',
            password: inputPassword.value,
            role: roleSelect.value,
          };
          users.push(newUser);
          saveToStorage(STORAGE_KEYS.USERS, users);
          showNotification('Pendaftaran berhasil! Silakan masuk.', 'success');
          navigateTo('login');
        }
      }, 1500);
    });
  }

  // Header component for main pages
  function createHeader(titleText) {
    const header = createElement('header', { classes: 'flex items-center justify-between bg-[${PRIMARY_COLOR}] text-white p-4 shadow-md sticky top-0 z-30' });
    const title = createElement('h1', { classes: 'text-xl font-bold', text: titleText });
    const rightGroup = createElement('div', { classes: 'flex items-center space-x-4' });

    // Notification button
    const notifBtn = createElement('button', {
      classes: 'relative focus:outline-none',
      attrs: { 'aria-label': 'Notifikasi' },
      html: '<i class="fas fa-bell fa-lg"></i>',
    });
    notifBtn.addEventListener('click', () => {
      navigateTo('notifications');
    });

    // Logout button
    const logoutBtn = createElement('button', {
      classes: 'focus:outline-none',
      attrs: { 'aria-label': 'Logout' },
      html: '<i class="fas fa-sign-out-alt fa-lg"></i>',
    });
    logoutBtn.addEventListener('click', () => {
      if (confirm('Apakah Anda yakin ingin logout?')) {
        logout();
      }
    });

    rightGroup.appendChild(notifBtn);
    rightGroup.appendChild(logoutBtn);

    header.appendChild(title);
    header.appendChild(rightGroup);
    return header;
  }

  // Bottom navigation bar component
  function createBottomNav(tabs, activeTab) {
    const nav = createElement('nav', { classes: 'fixed bottom-0 left-0 right-0 bg-white border-t border-gray-300 flex justify-around items-center h-14 z-40' });
    tabs.forEach(tab => {
      const btn = createElement('button', {
        classes: `flex flex-col items-center justify-center text-sm focus:outline-none ${tab.id === activeTab ? 'text-[${PRIMARY_COLOR}]' : 'text-gray-500'}`,
        attrs: { 'aria-label': tab.label },
      });
      btn.innerHTML = `<i class="${tab.icon} fa-lg mb-1"></i><span>${tab.label}</span>`;
      btn.addEventListener('click', () => {
        tab.action();
      });
      nav.appendChild(btn);
    });
    return nav;
  }

  // Main page for client
  function renderMainClient() {
    if (!currentUser || currentUser.role !== 'client') {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader(`Selamat Datang, ${currentUser.name}!`);
    container.appendChild(header);

    // Ringkasan layanan
    const summary = createElement('section', { classes: 'p-4 bg-[${PRIMARY_COLOR}] text-white rounded-b-lg shadow-md' });
    summary.innerHTML = `
      <p class="text-center text-lg max-w-xl mx-auto">LawLink menyediakan solusi hukum digital terpercaya untuk kebutuhan Anda, mulai dari konsultasi, jasa notaris, hingga pengurusan dokumen legal.</p>
    `;
    container.appendChild(summary);

    // Dashboard menu cards
    const dashboard = createElement('section', { classes: 'p-4 grid grid-cols-2 gap-4 mt-4' });
    const dashboardItems = [
      { id: 'consultation', label: 'Konsultasi Hukum', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Jasa Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen Legal', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'history', label: 'Riwayat Konsultasi', icon: 'fas fa-history', action: () => navigateTo('history') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ];
    dashboardItems.forEach(item => {
      const card = createElement('button', {
        classes: 'bg-white rounded-lg shadow p-4 flex flex-col items-center justify-center hover:shadow-lg focus:outline-none',
        attrs: { type: 'button' },
      });
      card.innerHTML = `<i class="${item.icon} fa-3x text-[${PRIMARY_COLOR}] mb-3"></i><span class="font-semibold text-center">${item.label}</span>`;
      card.addEventListener('click', item.action);
      dashboard.appendChild(card);
    });
    container.appendChild(dashboard);

    // Pintasan Layanan section
    const pintasanSection = createElement('section', { classes: 'p-4 mt-6' });
    const pintasanTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Pintasan Layanan' });
    pintasanSection.appendChild(pintasanTitle);

    const pintasanGrid = createElement('div', { classes: 'grid grid-cols-1 sm:grid-cols-2 gap-4' });

    const pintasanItems = [
      {
        id: 'consultation',
        title: 'Konsultasi Hukum',
        desc: 'Hubungi lawyer profesional untuk konsultasi online/offline.',
        icon: 'fas fa-comments',
        alt: 'Ikon chat dan video call berwarna biru',
        action: () => navigateTo('consultation'),
      },
      {
        id: 'notaris',
        title: 'Jasa Notaris',
        desc: 'Pengurusan akta, legalisasi dokumen, dan PPAT oleh notaris terpercaya.',
        icon: 'fas fa-file-signature',
        alt: 'Ikon dokumen resmi berwarna biru',
        action: () => navigateTo('notaris-service'),
      },
      {
        id: 'documents',
        title: 'Dokumen Legal',
        desc: 'Akses template dokumen hukum dan pengurusan surat secara profesional.',
        icon: 'fas fa-file-alt',
        alt: 'Ikon file dokumen berwarna biru',
        action: () => navigateTo('legal-documents'),
      },
      {
        id: 'history',
        title: 'Riwayat Konsultasi',
        desc: 'Lihat semua riwayat konsultasi Anda dengan lawyer.',
        icon: 'fas fa-history',
        alt: 'Ikon riwayat berwarna biru',
        action: () => navigateTo('history'),
      },
    ];

    pintasanItems.forEach(item => {
      const card = createElement('button', {
        classes: 'flex items-center space-x-4 bg-white rounded-lg shadow p-4 hover:shadow-lg focus:outline-none',
        attrs: { type: 'button' },
      });
      const icon = createElement('i', { classes: `${item.icon} fa-3x text-[${PRIMARY_COLOR}] flex-shrink-0`, attrs: { 'aria-hidden': 'true' } });
      const content = createElement('div', { classes: 'text-left' });
      const title = createElement('h3', { classes: 'font-semibold text-lg', text: item.title });
      const desc = createElement('p', { classes: 'text-gray-600 text-sm', text: item.desc });
      content.appendChild(title);
      content.appendChild(desc);
      card.appendChild(icon);
      card.appendChild(content);
      card.addEventListener('click', item.action);
      pintasanGrid.appendChild(card);
    });

    pintasanSection.appendChild(pintasanGrid);
    container.appendChild(pintasanSection);

    // Pilihan Lawyer & Notaris section
    const pilihanSection = createElement('section', { classes: 'p-4 mt-6' });
    const pilihanTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Pilihan Lawyer & Notaris' });
    pilihanSection.appendChild(pilihanTitle);

    const pilihanGrid = createElement('div', { classes: 'grid grid-cols-1 sm:grid-cols-2 md:grid-cols-4 gap-4' });

    const lawyers = loadFromStorage(STORAGE_KEYS.LAWYERS) || [];
    const notaris = loadFromStorage(STORAGE_KEYS.NOTARIS) || [];

    const combined = [...lawyers, ...notaris];

    combined.slice(0, 4).forEach(person => {
      const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4 flex flex-col items-center text-center' });
      const img = createElement('img', {
        attrs: { src: person.photo, alt: `Foto profil ${person.name} spesialisasi ${person.specialization}` },
        classes: 'w-24 h-24 rounded-full object-cover mb-3',
      });
      const name = createElement('h3', { classes: 'font-semibold text-lg', text: person.name });
      const spec = createElement('p', { classes: 'text-gray-600 text-sm mb-3', text: person.specialization });
      const btn = createElement('button', {
        classes: `bg-[${ACCENT_COLOR}] text-gray-900 px-4 py-1 rounded hover:bg-yellow-400 focus:outline-none`,
        text: 'Lihat Profil',
      });
      btn.addEventListener('click', () => {
        alert(`Profil ${person.name} - Spesialisasi: ${person.specialization}`);
      });
      card.appendChild(img);
      card.appendChild(name);
      card.appendChild(spec);
      card.appendChild(btn);
      pilihanGrid.appendChild(card);
    });

    pilihanSection.appendChild(pilihanGrid);
    container.appendChild(pilihanSection);

    // Artikel Terbaru/Blog Hukum section
    const blogSection = createElement('section', { classes: 'p-4 mt-6 mb-20' });
    const blogTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Artikel Terbaru/Blog Hukum' });
    blogSection.appendChild(blogTitle);

    const blogGrid = createElement('div', { classes: 'grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4' });

    const blogs = loadFromStorage(STORAGE_KEYS.BLOGS) || [];

    blogs.slice(0, 3).forEach(blog => {
      const card = createElement('div', { classes: 'bg-white rounded-lg shadow overflow-hidden flex flex-col' });
      const img = createElement('img', {
        attrs: { src: blog.thumbnail, alt: `Thumbnail artikel: ${blog.title}` },
        classes: 'w-full h-40 object-cover',
      });
      const content = createElement('div', { classes: 'p-4 flex flex-col flex-grow' });
      const title = createElement('h3', { classes: 'font-semibold text-lg mb-2', text: blog.title });
      const preview = createElement('p', { classes: 'text-gray-600 flex-grow', text: blog.preview });
      const btn = createElement('button', {
        classes: `mt-4 bg-[${PRIMARY_COLOR}] text-white px-4 py-2 rounded hover:bg-blue-700 focus:outline-none self-start`,
        text: 'Baca Selengkapnya',
      });
      btn.addEventListener('click', () => {
        navigateTo('blog-detail', { blogId: blog.id });
      });
      content.appendChild(title);
      content.appendChild(preview);
      content.appendChild(btn);
      card.appendChild(img);
      card.appendChild(content);
      blogGrid.appendChild(card);
    });

    blogSection.appendChild(blogGrid);
    container.appendChild(blogSection);

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => navigateTo('main-client') },
      { id: 'consultation', label: 'Konsultasi', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'home');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Main page for lawyer
  function renderMainLawyer() {
    if (!currentUser || currentUser.role !== 'lawyer') {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader(`Selamat Datang, ${currentUser.name}!`);
    container.appendChild(header);

    // Dashboard menu cards
    const dashboard = createElement('section', { classes: 'p-4 grid grid-cols-2 gap-4 mt-4' });
    const dashboardItems = [
      { id: 'schedule', label: 'Jadwal Konsultasi', icon: 'fas fa-calendar-alt', action: () => navigateTo('schedule') },
      { id: 'cases', label: 'Kasus Berjalan', icon: 'fas fa-briefcase', action: () => navigateTo('cases') },
      { id: 'documents', label: 'Dokumen Klien', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
      { id: 'notifications', label: 'Notifikasi', icon: 'fas fa-bell', action: () => navigateTo('notifications') },
    ];
    dashboardItems.forEach(item => {
      const card = createElement('button', {
        classes: 'bg-white rounded-lg shadow p-4 flex flex-col items-center justify-center hover:shadow-lg focus:outline-none',
        attrs: { type: 'button' },
      });
      card.innerHTML = `<i class="${item.icon} fa-3x text-[${PRIMARY_COLOR}] mb-3"></i><span class="font-semibold text-center">${item.label}</span>`;
      card.addEventListener('click', item.action);
      dashboard.appendChild(card);
    });
    container.appendChild(dashboard);

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => navigateTo('main-lawyer') },
      { id: 'schedule', label: 'Jadwal', icon: 'fas fa-calendar-alt', action: () => navigateTo('schedule') },
      { id: 'cases', label: 'Kasus', icon: 'fas fa-briefcase', action: () => navigateTo('cases') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'home');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Main page for notaris
  function renderMainNotaris() {
    if (!currentUser || currentUser.role !== 'notaris') {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader(`Selamat Datang, ${currentUser.name}!`);
    container.appendChild(header);

    // Dashboard menu cards
    const dashboard = createElement('section', { classes: 'p-4 grid grid-cols-2 gap-4 mt-4' });
    const dashboardItems = [
      { id: 'schedule', label: 'Jadwal Notaris', icon: 'fas fa-calendar-alt', action: () => navigateTo('schedule') },
      { id: 'akta', label: 'Akta yang Diproses', icon: 'fas fa-file-contract', action: () => navigateTo('cases') },
      { id: 'documents', label: 'Dokumen Klien', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'tarif', label: 'Biaya & Tarif', icon: 'fas fa-money-bill-wave', action: () => alert('Halaman Biaya & Tarif belum tersedia.') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ];
    dashboardItems.forEach(item => {
      const card = createElement('button', {
        classes: 'bg-white rounded-lg shadow p-4 flex flex-col items-center justify-center hover:shadow-lg focus:outline-none',
        attrs: { type: 'button' },
      });
      card.innerHTML = `<i class="${item.icon} fa-3x text-[${PRIMARY_COLOR}] mb-3"></i><span class="font-semibold text-center">${item.label}</span>`;
      card.addEventListener('click', item.action);
      dashboard.appendChild(card);
    });
    container.appendChild(dashboard);

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => navigateTo('main-notaris') },
      { id: 'schedule', label: 'Jadwal', icon: 'fas fa-calendar-alt', action: () => navigateTo('schedule') },
      { id: 'akta', label: 'Akta', icon: 'fas fa-file-contract', action: () => navigateTo('cases') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'home');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Consultation page (client)
  function renderConsultation() {
    if (!currentUser || currentUser.role !== 'client') {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Konsultasi Hukum');
    container.appendChild(header);

    // Booking form
    const formSection = createElement('section', { classes: 'p-4' });
    const formTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Booking Konsultasi' });
    formSection.appendChild(formTitle);

    const form = createElement('form', { classes: 'space-y-4' });

    // Date input
    const dateGroup = createElement('div', { classes: 'flex flex-col' });
    const dateLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Tanggal' });
    const dateInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'date', required: 'required', min: new Date().toISOString().split('T')[0] },
    });
    dateGroup.appendChild(dateLabel);
    dateGroup.appendChild(dateInput);
    form.appendChild(dateGroup);

    // Time input
    const timeGroup = createElement('div', { classes: 'flex flex-col' });
    const timeLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Waktu' });
    const timeInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'time', required: 'required' },
    });
    timeGroup.appendChild(timeLabel);
    timeGroup.appendChild(timeInput);
    form.appendChild(timeGroup);

    // Case type dropdown
    const caseGroup = createElement('div', { classes: 'flex flex-col' });
    const caseLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Jenis Kasus' });
    const caseSelect = createElement('select', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { required: 'required' },
    });
    ['Pilih jenis kasus', 'Perdata', 'Pidana', 'Bisnis', 'Keluarga', 'Lainnya'].forEach((opt, i) => {
      const option = createElement('option', { attrs: { value: i === 0 ? '' : opt.toLowerCase() }, text: opt });
      caseSelect.appendChild(option);
    });
    caseGroup.appendChild(caseLabel);
    caseGroup.appendChild(caseSelect);
    form.appendChild(caseGroup);

    // Description textarea
    const descGroup = createElement('div', { classes: 'flex flex-col' });
    const descLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Deskripsi Masalah' });
    const descTextarea = createElement('textarea', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}] resize-none',
      attrs: { rows: 4, placeholder: 'Jelaskan masalah hukum Anda secara singkat', required: 'required' },
    });
    descGroup.appendChild(descLabel);
    descGroup.appendChild(descTextarea);
    form.appendChild(descGroup);

    // Submit button
    const submitBtn = createElement('button', {
      classes: `w-full bg-[${PRIMARY_COLOR}] text-white py-2 rounded font-semibold hover:bg-blue-700 focus:outline-none flex justify-center items-center`,
      attrs: { type: 'submit' },
      text: 'Booking Sekarang',
    });
    form.appendChild(submitBtn);

    formSection.appendChild(form);
    container.appendChild(formSection);

    // List jadwal konsultasi
    const listSection = createElement('section', { classes: 'p-4 mt-6' });
    const listTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Jadwal Konsultasi Anda' });
    listSection.appendChild(listTitle);

    const listContainer = createElement('div', { classes: 'space-y-3' });
    listSection.appendChild(listContainer);
    container.appendChild(listSection);

    // Load appointments
    function loadAppointments() {
      const appointments = loadFromStorage(STORAGE_KEYS.APPOINTMENTS) || [];
      const userAppointments = appointments.filter(a => a.userId === currentUser.id);
      listContainer.innerHTML = '';
      if (userAppointments.length === 0) {
        listContainer.innerHTML = '<p class="text-gray-600">Belum ada jadwal konsultasi.</p>';
        return;
      }
      userAppointments.forEach(app => {
        const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4 flex justify-between items-center' });
        const info = createElement('div');
        const date = new Date(app.date + 'T' + app.time);
        info.innerHTML = `<p class="font-semibold">${formatDate(date)} - ${formatTime(date)}</p><p class="text-gray-600 capitalize">${app.caseType}</p><p class="text-gray-600">${app.description}</p>`;
        const chatBtn = createElement('button', {
          classes: `bg-[${ACCENT_COLOR}] text-gray-900 px-3 py-1 rounded hover:bg-yellow-400 focus:outline-none`,
          text: 'Chat',
        });
        chatBtn.addEventListener('click', () => {
          chatCurrentSessionId = app.id;
          chatCurrentWithUserId = app.lawyerId || null;
          navigateTo('chat', { withUserId: app.lawyerId });
        });
        card.appendChild(info);
        card.appendChild(chatBtn);
        listContainer.appendChild(card);
      });
    }
    loadAppointments();

    // Form submit handler
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      if (!dateInput.value || !timeInput.value || !caseSelect.value || !descTextarea.value.trim()) {
        showNotification('Semua field wajib diisi.', 'error');
        return;
      }
      submitBtn.disabled = true;
      submitBtn.innerHTML = `<i class="fas fa-spinner fa-spin mr-2"></i>Booking...`;

      setTimeout(() => {
        const appointments = loadFromStorage(STORAGE_KEYS.APPOINTMENTS) || [];
        // Assign a random lawyer for demo
        const lawyers = loadFromStorage(STORAGE_KEYS.LAWYERS) || [];
        const assignedLawyer = lawyers[Math.floor(Math.random() * lawyers.length)];
        const newAppointment = {
          id: generateId('app_'),
          userId: currentUser.id,
          lawyerId: assignedLawyer ? assignedLawyer.id : null,
          date: dateInput.value,
          time: timeInput.value,
          caseType: caseSelect.value,
          description: descTextarea.value.trim(),
          status: 'pending',
        };
        appointments.push(newAppointment);
        saveToStorage(STORAGE_KEYS.APPOINTMENTS, appointments);
        showNotification('Booking konsultasi berhasil!', 'success');
        form.reset();
        submitBtn.disabled = false;
        submitBtn.textContent = 'Booking Sekarang';
        loadAppointments();
      }, 1500);
    });

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => navigateTo('main-client') },
      { id: 'consultation', label: 'Konsultasi', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'consultation');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Notaris service page (client)
  function renderNotarisService() {
    if (!currentUser || currentUser.role !== 'client') {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Jasa Notaris');
    container.appendChild(header);

    // List layanan notaris
    const layananSection = createElement('section', { classes: 'p-4' });
    const layananTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Layanan Notaris' });
    layananSection.appendChild(layananTitle);

    const layananList = [
      { id: 'akta', title: 'Pembuatan Akta', desc: 'Pembuatan akta otentik sesuai kebutuhan Anda.' },
      { id: 'legalisasi', title: 'Legalisasi Dokumen', desc: 'Legalisasi dokumen resmi oleh notaris.' },
      { id: 'ppat', title: 'PPAT', desc: 'Pelayanan Pejabat Pembuat Akta Tanah.' },
    ];

    const layananContainer = createElement('div', { classes: 'space-y-4' });
    layananList.forEach(layanan => {
      const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4' });
      const title = createElement('h3', { classes: 'font-semibold text-lg mb-1', text: layanan.title });
      const desc = createElement('p', { classes: 'text-gray-600', text: layanan.desc });
      card.appendChild(title);
      card.appendChild(desc);
      layananContainer.appendChild(card);
    });
    layananSection.appendChild(layananContainer);
    container.appendChild(layananSection);

    // Form pengajuan dokumen
    const formSection = createElement('section', { classes: 'p-4 mt-6' });
    const formTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Pengajuan Dokumen' });
    formSection.appendChild(formTitle);

    const form = createElement('form', { classes: 'space-y-4' });

    // Upload file
    const fileGroup = createElement('div', { classes: 'flex flex-col' });
    const fileLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Upload File' });
    const fileInput = createElement('input', {
      classes: '',
      attrs: { type: 'file', required: 'required', accept: '.pdf,.doc,.docx,.jpg,.png' },
    });
    fileGroup.appendChild(fileLabel);
    fileGroup.appendChild(fileInput);
    form.appendChild(fileGroup);

    // Input data dokumen
    const dataGroup = createElement('div', { classes: 'flex flex-col' });
    const dataLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Data Dokumen' });
    const dataInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'text', placeholder: 'Masukkan data dokumen', required: 'required' },
    });
    dataGroup.appendChild(dataLabel);
    dataGroup.appendChild(dataInput);
    form.appendChild(dataGroup);

    // Pilih jenis akta
    const jenisGroup = createElement('div', { classes: 'flex flex-col' });
    const jenisLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Jenis Akta' });
    const jenisSelect = createElement('select', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { required: 'required' },
    });
    ['Pilih jenis akta', 'Akta Jual Beli', 'Akta Pendirian', 'Akta Hibah', 'Akta Wasiat'].forEach((opt, i) => {
      const option = createElement('option', { attrs: { value: i === 0 ? '' : opt.toLowerCase().replace(/\s/g, '-') }, text: opt });
      jenisSelect.appendChild(option);
    });
    jenisGroup.appendChild(jenisLabel);
    jenisGroup.appendChild(jenisSelect);
    form.appendChild(jenisGroup);

    // Submit button
    const submitBtn = createElement('button', {
      classes: `w-full bg-[${PRIMARY_COLOR}] text-white py-2 rounded font-semibold hover:bg-blue-700 focus:outline-none flex justify-center items-center`,
      attrs: { type: 'submit' },
      text: 'Ajukan',
    });
    form.appendChild(submitBtn);

    formSection.appendChild(form);
    container.appendChild(formSection);

    // Tracking status dokumen
    const trackingSection = createElement('section', { classes: 'p-4 mt-6' });
    const trackingTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Tracking Status Dokumen' });
    trackingSection.appendChild(trackingTitle);

    const trackingList = createElement('div', { classes: 'space-y-3' });
    trackingSection.appendChild(trackingList);
    container.appendChild(trackingSection);

    // Load documents
    function loadDocuments() {
      const documents = loadFromStorage(STORAGE_KEYS.DOCUMENTS) || [];
      const userDocs = documents.filter(d => d.userId === currentUser.id);
      trackingList.innerHTML = '';
      if (userDocs.length === 0) {
        trackingList.innerHTML = '<p class="text-gray-600">Belum ada dokumen yang diajukan.</p>';
        return;
      }
      userDocs.forEach(doc => {
        const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4 flex justify-between items-center' });
        const info = createElement('div');
        info.innerHTML = `<p class="font-semibold">${doc.data}</p><p class="text-gray-600 capitalize">${doc.jenisAkta}</p><p class="text-gray-600">Status: ${doc.status}</p>`;
        card.appendChild(info);
        trackingList.appendChild(card);
      });
    }
    loadDocuments();

    // Form submit handler
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      if (!fileInput.files.length || !dataInput.value.trim() || !jenisSelect.value) {
        showNotification('Semua field wajib diisi.', 'error');
        return;
      }
      submitBtn.disabled = true;
      submitBtn.innerHTML = `<i class="fas fa-spinner fa-spin mr-2"></i>Ajukan...`;

      setTimeout(() => {
        const documents = loadFromStorage(STORAGE_KEYS.DOCUMENTS) || [];
        const newDoc = {
          id: generateId('doc_'),
          userId: currentUser.id,
          fileName: fileInput.files[0].name,
          data: dataInput.value.trim(),
          jenisAkta: jenisSelect.value,
          status: 'diproses',
          submittedAt: new Date().toISOString(),
        };
        documents.push(newDoc);
        saveToStorage(STORAGE_KEYS.DOCUMENTS, documents);
        showNotification('Pengajuan dokumen berhasil!', 'success');
        form.reset();
        submitBtn.disabled = false;
        submitBtn.textContent = 'Ajukan';
        loadDocuments();
      }, 1500);
    });

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => navigateTo('main-client') },
      { id: 'consultation', label: 'Konsultasi', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'notaris');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Legal documents page (client)
  function renderLegalDocuments() {
    if (!currentUser) {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Dokumen Legal');
    container.appendChild(header);

    // Gallery template dokumen
    const gallerySection = createElement('section', { classes: 'p-4' });
    const galleryTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Template Dokumen' });
    gallerySection.appendChild(galleryTitle);

    const templates = [
      { id: 'template1', title: 'Surat Kuasa', file: 'surat_kuasa_template.pdf', thumbnail: 'https://placehold.co/400x250/png?text=Surat+Kuasa' },
      { id: 'template2', title: 'Perjanjian Kerja', file: 'perjanjian_kerja_template.pdf', thumbnail: 'https://placehold.co/400x250/png?text=Perjanjian+Kerja' },
      { id: 'template3', title: 'Surat Pernyataan', file: 'surat_pernyataan_template.pdf', thumbnail: 'https://placehold.co/400x250/png?text=Surat+Pernyataan' },
    ];

    const galleryGrid = createElement('div', { classes: 'grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-4' });

    templates.forEach(template => {
      const card = createElement('div', { classes: 'bg-white rounded-lg shadow overflow-hidden flex flex-col' });
      const img = createElement('img', {
        attrs: { src: template.thumbnail, alt: `Thumbnail template dokumen: ${template.title}` },
        classes: 'w-full h-40 object-cover',
      });
      const content = createElement('div', { classes: 'p-4 flex flex-col flex-grow' });
      const title = createElement('h3', { classes: 'font-semibold text-lg mb-2', text: template.title });
      const btn = createElement('button', {
        classes: `mt-auto bg-[${PRIMARY_COLOR}] text-white px-4 py-2 rounded hover:bg-blue-700 focus:outline-none self-start`,
        text: 'Download',
      });
      btn.addEventListener('click', () => {
        alert(`Download file: ${template.file} (fitur download belum aktif)`);
      });
      content.appendChild(title);
      content.appendChild(btn);
      card.appendChild(img);
      card.appendChild(content);
      galleryGrid.appendChild(card);
    });

    gallerySection.appendChild(galleryGrid);
    container.appendChild(gallerySection);

    // Form request dokumen
    const requestSection = createElement('section', { classes: 'p-4 mt-6' });
    const requestTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Request Dokumen' });
    requestSection.appendChild(requestTitle);

    const form = createElement('form', { classes: 'space-y-4' });

    // Jenis dokumen
    const jenisGroup = createElement('div', { classes: 'flex flex-col' });
    const jenisLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Jenis Dokumen' });
    const jenisSelect = createElement('select', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { required: 'required' },
    });
    ['Pilih jenis dokumen', 'Surat Kuasa', 'Perjanjian Kerja', 'Surat Pernyataan', 'Lainnya'].forEach((opt, i) => {
      const option = createElement('option', { attrs: { value: i === 0 ? '' : opt.toLowerCase().replace(/\s/g, '-') }, text: opt });
      jenisSelect.appendChild(option);
    });
    jenisGroup.appendChild(jenisLabel);
    jenisGroup.appendChild(jenisSelect);
    form.appendChild(jenisGroup);

    // Detail input
    const detailGroup = createElement('div', { classes: 'flex flex-col' });
    const detailLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Detail' });
    const detailInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'text', placeholder: 'Masukkan detail dokumen', required: 'required' },
    });
    detailGroup.appendChild(detailLabel);
    detailGroup.appendChild(detailInput);
    form.appendChild(detailGroup);

    // Submit button
    const submitBtn = createElement('button', {
      classes: `w-full bg-[${PRIMARY_COLOR}] text-white py-2 rounded font-semibold hover:bg-blue-700 focus:outline-none flex justify-center items-center`,
      attrs: { type: 'submit' },
      text: 'Request',
    });
    form.appendChild(submitBtn);

    requestSection.appendChild(form);
    container.appendChild(requestSection);

    // List dokumen saya
    const listSection = createElement('section', { classes: 'p-4 mt-6' });
    const listTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Dokumen Saya' });
    listSection.appendChild(listTitle);

    const listContainer = createElement('div', { classes: 'space-y-3' });
    listSection.appendChild(listContainer);
    container.appendChild(listSection);

    // Load requested documents
    function loadRequestedDocuments() {
      const documents = loadFromStorage(STORAGE_KEYS.DOCUMENTS) || [];
      const userDocs = documents.filter(d => d.userId === currentUser.id);
      listContainer.innerHTML = '';
      if (userDocs.length === 0) {
        listContainer.innerHTML = '<p class="text-gray-600">Belum ada dokumen yang diminta.</p>';
        return;
      }
      userDocs.forEach(doc => {
        const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4 flex justify-between items-center' });
        const info = createElement('div');
        info.innerHTML = `<p class="font-semibold">${doc.data || doc.jenisAkta || 'Dokumen'}</p><p class="text-gray-600">Status: ${doc.status || 'diproses'}</p>`;
        card.appendChild(info);
        listContainer.appendChild(card);
      });
    }
    loadRequestedDocuments();

    // Form submit handler
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      if (!jenisSelect.value || !detailInput.value.trim()) {
        showNotification('Semua field wajib diisi.', 'error');
        return;
      }
      submitBtn.disabled = true;
      submitBtn.innerHTML = `<i class="fas fa-spinner fa-spin mr-2"></i>Request...`;

      setTimeout(() => {
        const documents = loadFromStorage(STORAGE_KEYS.DOCUMENTS) || [];
        const newDoc = {
          id: generateId('doc_'),
          userId: currentUser.id,
          jenisDokumen: jenisSelect.value,
          data: detailInput.value.trim(),
          status: 'diproses',
          submittedAt: new Date().toISOString(),
        };
        documents.push(newDoc);
        saveToStorage(STORAGE_KEYS.DOCUMENTS, documents);
        showNotification('Request dokumen berhasil!', 'success');
        form.reset();
        submitBtn.disabled = false;
        submitBtn.textContent = 'Request';
        loadRequestedDocuments();
      }, 1500);
    });

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => {
        if(currentUser.role === 'client') navigateTo('main-client');
        else if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
        else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      } },
      { id: 'consultation', label: 'Konsultasi', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'documents');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Profile page (all roles)
  function renderProfile() {
    if (!currentUser) {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Profil Saya');
    container.appendChild(header);

    const profileSection = createElement('section', { classes: 'p-4 max-w-md mx-auto' });

    const form = createElement('form', { classes: 'space-y-4' });

    // Name
    const nameGroup = createElement('div', { classes: 'flex flex-col' });
    const nameLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Nama Lengkap' });
    const nameInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'text', required: 'required' },
      text: currentUser.name,
    });
    nameInput.value = currentUser.name;
    nameGroup.appendChild(nameLabel);
    nameGroup.appendChild(nameInput);
    form.appendChild(nameGroup);

    // Email
    const emailGroup = createElement('div', { classes: 'flex flex-col' });
    const emailLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Email' });
    const emailInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'email', required: 'required' },
    });
    emailInput.value = currentUser.email || '';
    emailGroup.appendChild(emailLabel);
    emailGroup.appendChild(emailInput);
    form.appendChild(emailGroup);

    // Phone
    const phoneGroup = createElement('div', { classes: 'flex flex-col' });
    const phoneLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Nomor Telepon' });
    const phoneInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'tel', required: 'required' },
    });
    phoneInput.value = currentUser.phone || '';
    phoneGroup.appendChild(phoneLabel);
    phoneGroup.appendChild(phoneInput);
    form.appendChild(phoneGroup);

    // Password change
    const passGroup = createElement('div', { classes: 'flex flex-col relative' });
    const passLabel = createElement('label', { classes: 'mb-1 font-semibold', text: 'Password Baru (kosongkan jika tidak ingin ganti)' });
    const passInput = createElement('input', {
      classes: 'border border-gray-300 rounded px-3 py-2 pr-10 focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { type: 'password' },
    });
    const togglePassBtn = createElement('button', {
      classes: 'absolute right-3 top-9 text-gray-500 focus:outline-none',
      attrs: { type: 'button', 'aria-label': 'Toggle password visibility' },
      html: '<i class="fas fa-eye"></i>',
    });
    passGroup.appendChild(passLabel);
    passGroup.appendChild(passInput);
    passGroup.appendChild(togglePassBtn);
    form.appendChild(passGroup);

    togglePassBtn.addEventListener('click', (e) => {
      e.preventDefault();
      if (passInput.type === 'password') {
        passInput.type = 'text';
        togglePassBtn.innerHTML = '<i class="fas fa-eye-slash"></i>';
      } else {
        passInput.type = 'password';
        togglePassBtn.innerHTML = '<i class="fas fa-eye"></i>';
      }
    });

    // Submit button
    const submitBtn = createElement('button', {
      classes: `w-full bg-[${PRIMARY_COLOR}] text-white py-2 rounded font-semibold hover:bg-blue-700 focus:outline-none flex justify-center items-center`,
      attrs: { type: 'submit' },
      text: 'Simpan Perubahan',
    });
    form.appendChild(submitBtn);

    profileSection.appendChild(form);
    container.appendChild(profileSection);

    // Submit handler
    form.addEventListener('submit', (e) => {
      e.preventDefault();
      if (!nameInput.value.trim() || !emailInput.value.trim() || !phoneInput.value.trim()) {
        showNotification('Nama, email, dan telepon wajib diisi.', 'error');
        return;
      }
      if (!validateEmail(emailInput.value.trim())) {
        showNotification('Format email tidak valid.', 'error');
        return;
      }
      if (!validatePhone(phoneInput.value.trim())) {
        showNotification('Format nomor telepon tidak valid.', 'error');
        return;
      }
      if (passInput.value && !validatePassword(passInput.value)) {
        showNotification('Password minimal 8 karakter, mengandung huruf besar, kecil, dan angka.', 'error');
        return;
      }
      submitBtn.disabled = true;
      submitBtn.innerHTML = `<i class="fas fa-spinner fa-spin mr-2"></i>Simpan...`;

      setTimeout(() => {
        const users = loadFromStorage(STORAGE_KEYS.USERS) || [];
        const idx = users.findIndex(u => u.id === currentUser.id);
        if (idx !== -1) {
          users[idx].name = nameInput.value.trim();
          users[idx].email = emailInput.value.trim();
          users[idx].phone = phoneInput.value.trim();
          if (passInput.value) users[idx].password = passInput.value;
          saveToStorage(STORAGE_KEYS.USERS, users);
          currentUser = users[idx];
          session.user = currentUser;
          saveToStorage(STORAGE_KEYS.SESSION, session);
          showNotification('Profil berhasil diperbarui.', 'success');
          submitBtn.disabled = false;
          submitBtn.textContent = 'Simpan Perubahan';
        } else {
          showNotification('Terjadi kesalahan saat menyimpan.', 'error');
          submitBtn.disabled = false;
          submitBtn.textContent = 'Simpan Perubahan';
        }
      }, 1500);
    });

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => {
        if(currentUser.role === 'client') navigateTo('main-client');
        else if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
        else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      } },
      { id: 'consultation', label: 'Konsultasi', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'profile');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Schedule page (lawyer/notaris)
  function renderSchedule() {
    if (!currentUser || (currentUser.role !== 'lawyer' && currentUser.role !== 'notaris')) {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Jadwal');
    container.appendChild(header);

    // List jadwal
    const listSection = createElement('section', { classes: 'p-4' });
    const listTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Jadwal Anda' });
    listSection.appendChild(listTitle);

    const listContainer = createElement('div', { classes: 'space-y-3' });
    listSection.appendChild(listContainer);
    container.appendChild(listSection);

    // Load appointments for lawyer/notaris
    function loadAppointments() {
      const appointments = loadFromStorage(STORAGE_KEYS.APPOINTMENTS) || [];
      const userAppointments = appointments.filter(a => a.lawyerId === currentUser.id || (currentUser.role === 'notaris' && a.notarisId === currentUser.id));
      listContainer.innerHTML = '';
      if (userAppointments.length === 0) {
        listContainer.innerHTML = '<p class="text-gray-600">Belum ada jadwal.</p>';
        return;
      }
      userAppointments.forEach(app => {
        const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4 flex justify-between items-center' });
        const info = createElement('div');
        const date = new Date(app.date + 'T' + app.time);
        info.innerHTML = `<p class="font-semibold">${formatDate(date)} - ${formatTime(date)}</p><p class="text-gray-600 capitalize">${app.caseType}</p><p class="text-gray-600">${app.description}</p>`;
        const chatBtn = createElement('button', {
          classes: `bg-[${ACCENT_COLOR}] text-gray-900 px-3 py-1 rounded hover:bg-yellow-400 focus:outline-none`,
          text: 'Chat',
        });
        chatBtn.addEventListener('click', () => {
          chatCurrentSessionId = app.id;
          chatCurrentWithUserId = app.userId;
          navigateTo('chat', { withUserId: app.userId });
        });
        card.appendChild(info);
        card.appendChild(chatBtn);
        listContainer.appendChild(card);
      });
    }
    loadAppointments();

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => {
        if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
        else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      } },
      { id: 'schedule', label: 'Jadwal', icon: 'fas fa-calendar-alt', action: () => navigateTo('schedule') },
      { id: 'cases', label: 'Kasus', icon: 'fas fa-briefcase', action: () => navigateTo('cases') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'schedule');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Cases page (lawyer/notaris)
  function renderCases() {
    if (!currentUser || (currentUser.role !== 'lawyer' && currentUser.role !== 'notaris')) {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Kasus Berjalan / Akta yang Diproses');
    container.appendChild(header);

    // List cases
    const listSection = createElement('section', { classes: 'p-4' });
    const listTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Daftar Kasus / Akta' });
    listSection.appendChild(listTitle);

    const listContainer = createElement('div', { classes: 'space-y-3' });
    listSection.appendChild(listContainer);
    container.appendChild(listSection);

    // Load cases (appointments for lawyer, documents for notaris)
    function loadCases() {
      listContainer.innerHTML = '';
      if (currentUser.role === 'lawyer') {
        const appointments = loadFromStorage(STORAGE_KEYS.APPOINTMENTS) || [];
        const myCases = appointments.filter(a => a.lawyerId === currentUser.id);
        if (myCases.length === 0) {
          listContainer.innerHTML = '<p class="text-gray-600">Belum ada kasus berjalan.</p>';
          return;
        }
        myCases.forEach(c => {
          const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4 flex justify-between items-center' });
          const info = createElement('div');
          const date = new Date(c.date + 'T' + c.time);
          info.innerHTML = `<p class="font-semibold">${formatDate(date)} - ${formatTime(date)}</p><p class="text-gray-600 capitalize">${c.caseType}</p><p class="text-gray-600">${c.description}</p>`;
          const chatBtn = createElement('button', {
            classes: `bg-[${ACCENT_COLOR}] text-gray-900 px-3 py-1 rounded hover:bg-yellow-400 focus:outline-none`,
            text: 'Chat',
          });
          chatBtn.addEventListener('click', () => {
            chatCurrentSessionId = c.id;
            chatCurrentWithUserId = c.userId;
            navigateTo('chat', { withUserId: c.userId });
          });
          card.appendChild(info);
          card.appendChild(chatBtn);
          listContainer.appendChild(card);
        });
      } else if (currentUser.role === 'notaris') {
        const documents = loadFromStorage(STORAGE_KEYS.DOCUMENTS) || [];
        const myDocs = documents.filter(d => d.notarisId === currentUser.id || d.status === 'diproses');
        if (myDocs.length === 0) {
          listContainer.innerHTML = '<p class="text-gray-600">Belum ada akta yang diproses.</p>';
          return;
        }
        myDocs.forEach(d => {
          const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4' });
          card.innerHTML = `<p class="font-semibold">${d.data || 'Dokumen'}</p><p class="text-gray-600 capitalize">${d.jenisAkta || ''}</p><p class="text-gray-600">Status: ${d.status}</p>`;
          listContainer.appendChild(card);
        });
      }
    }
    loadCases();

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => {
        if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
        else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      } },
      { id: 'schedule', label: 'Jadwal', icon: 'fas fa-calendar-alt', action: () => navigateTo('schedule') },
      { id: 'cases', label: 'Kasus', icon: 'fas fa-briefcase', action: () => navigateTo('cases') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'cases');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Notifications page (all roles)
  function renderNotifications() {
    if (!currentUser) {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Notifikasi');
    container.appendChild(header);

    const notifSection = createElement('section', { classes: 'p-4' });
    notifSection.innerHTML = '<p class="text-gray-600">Belum ada notifikasi.</p>';
    container.appendChild(notifSection);

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => {
        if(currentUser.role === 'client') navigateTo('main-client');
        else if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
        else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      } },
      { id: 'consultation', label: 'Konsultasi', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'notifications');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // History page (client)
  function renderHistory() {
    if (!currentUser || currentUser.role !== 'client') {
      navigateTo('login');
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header
    const header = createHeader('Riwayat Konsultasi');
    container.appendChild(header);

    const historySection = createElement('section', { classes: 'p-4' });
    const historyTitle = createElement('h2', { classes: 'text-xl font-bold mb-4 text-[${PRIMARY_COLOR}]', text: 'Riwayat Konsultasi Anda' });
    historySection.appendChild(historyTitle);

    const listContainer = createElement('div', { classes: 'space-y-3' });
    historySection.appendChild(listContainer);
    container.appendChild(historySection);

    // Load appointments
    function loadHistory() {
      const appointments = loadFromStorage(STORAGE_KEYS.APPOINTMENTS) || [];
      const userAppointments = appointments.filter(a => a.userId === currentUser.id);
      listContainer.innerHTML = '';
      if (userAppointments.length === 0) {
        listContainer.innerHTML = '<p class="text-gray-600">Belum ada riwayat konsultasi.</p>';
        return;
      }
      userAppointments.forEach(app => {
        const card = createElement('div', { classes: 'bg-white rounded-lg shadow p-4 flex justify-between items-center' });
        const info = createElement('div');
        const date = new Date(app.date + 'T' + app.time);
        info.innerHTML = `<p class="font-semibold">${formatDate(date)} - ${formatTime(date)}</p><p class="text-gray-600 capitalize">${app.caseType}</p><p class="text-gray-600">${app.description}</p>`;
        const chatBtn = createElement('button', {
          classes: `bg-[${ACCENT_COLOR}] text-gray-900 px-3 py-1 rounded hover:bg-yellow-400 focus:outline-none`,
          text: 'Chat',
        });
        chatBtn.addEventListener('click', () => {
          chatCurrentSessionId = app.id;
          chatCurrentWithUserId = app.lawyerId || null;
          navigateTo('chat', { withUserId: app.lawyerId });
        });
        card.appendChild(info);
        card.appendChild(chatBtn);
        listContainer.appendChild(card);
      });
    }
    loadHistory();

    // Bottom navigation bar
    const bottomNav = createBottomNav([
      { id: 'home', label: 'Beranda', icon: 'fas fa-home', action: () => navigateTo('main-client') },
      { id: 'consultation', label: 'Konsultasi', icon: 'fas fa-comments', action: () => navigateTo('consultation') },
      { id: 'notaris', label: 'Notaris', icon: 'fas fa-file-signature', action: () => navigateTo('notaris-service') },
      { id: 'documents', label: 'Dokumen', icon: 'fas fa-file-alt', action: () => navigateTo('legal-documents') },
      { id: 'profile', label: 'Profil', icon: 'fas fa-user', action: () => navigateTo('profile') },
    ], 'history');
    container.appendChild(bottomNav);

    app.appendChild(container);
  }

  // Chat page (client/lawyer/notaris)
  function renderChat(withUserId) {
    if (!currentUser) {
      navigateTo('login');
      return;
    }
    if (!withUserId) {
      showNotification('User chat tidak ditemukan.', 'error');
      if(currentUser.role === 'client') navigateTo('main-client');
      else if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
      else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      return;
    }
    const users = loadFromStorage(STORAGE_KEYS.USERS) || [];
    const chatUser = users.find(u => u.id === withUserId);
    if (!chatUser) {
      showNotification('User chat tidak ditemukan.', 'error');
      if(currentUser.role === 'client') navigateTo('main-client');
      else if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
      else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      return;
    }

    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header with back button
    const header = createElement('header', { classes: 'flex items-center justify-between bg-[${PRIMARY_COLOR}] text-white p-4 shadow-md sticky top-0 z-30' });
    const backBtn = createElement('button', { classes: 'focus:outline-none', attrs: { 'aria-label': 'Kembali' }, html: '<i class="fas fa-arrow-left fa-lg"></i>' });
    backBtn.addEventListener('click', () => {
      if(currentUser.role === 'client') navigateTo('consultation');
      else if(currentUser.role === 'lawyer') navigateTo('schedule');
      else if(currentUser.role === 'notaris') navigateTo('schedule');
    });
    const title = createElement('h1', { classes: 'text-xl font-bold', text: `Chat dengan ${chatUser.name}` });
    const dummy = createElement('div', { classes: 'w-6' }); // placeholder for spacing
    header.appendChild(backBtn);
    header.appendChild(title);
    header.appendChild(dummy);
    container.appendChild(header);

    // Chat messages container
    const chatContainer = createElement('div', { classes: 'flex-grow p-4 overflow-y-auto chat-scroll space-y-3 bg-gray-100' });
    container.appendChild(chatContainer);

    // Input area
    const inputArea = createElement('div', { classes: 'p-4 bg-white border-t border-gray-300 flex space-x-2' });
    const inputMsg = createElement('textarea', {
      classes: 'flex-grow border border-gray-300 rounded px-3 py-2 resize-none focus:outline-none focus:ring-2 focus:ring-[${PRIMARY_COLOR}]',
      attrs: { rows: 2, placeholder: 'Tulis pesan...' },
    });
    const sendBtn = createElement('button', {
      classes: `bg-[${PRIMARY_COLOR}] text-white px-4 py-2 rounded font-semibold hover:bg-blue-700 focus:outline-none flex items-center justify-center`,
      html: '<i class="fas fa-paper-plane"></i>',
      attrs: { 'aria-label': 'Kirim pesan' },
    });
    inputArea.appendChild(inputMsg);
    inputArea.appendChild(sendBtn);
    container.appendChild(inputArea);

    app.appendChild(container);

    // Load chat history
    function loadChat() {
      const chats = loadFromStorage(STORAGE_KEYS.CHATS) || [];
      const sessionChats = chats.filter(c =>
        (c.from === currentUser.id && c.to === withUserId) ||
        (c.from === withUserId && c.to === currentUser.id)
      );
      chatContainer.innerHTML = '';
      sessionChats.sort((a,b) => new Date(a.timestamp) - new Date(b.timestamp));
      sessionChats.forEach(c => {
        const msgDiv = createElement('div', {
          classes: `max-w-xs px-3 py-2 rounded-lg break-words ${c.from === currentUser.id ? 'bg-[${PRIMARY_COLOR}] text-white self-end' : 'bg-white text-gray-800 self-start'}`,
        });
        msgDiv.textContent = c.message;
        chatContainer.appendChild(msgDiv);
      });
      chatContainer.scrollTop = chatContainer.scrollHeight;
    }
    loadChat();

    // Send message handler
    sendBtn.addEventListener('click', () => {
      const msg = inputMsg.value.trim();
      if (!msg) return;
      const chats = loadFromStorage(STORAGE_KEYS.CHATS) || [];
      const newMsg = {
        id: generateId('chat_'),
        from: currentUser.id,
        to: withUserId,
        message: msg,
        timestamp: new Date().toISOString(),
      };
      chats.push(newMsg);
      saveToStorage(STORAGE_KEYS.CHATS, chats);
      inputMsg.value = '';
      loadChat();
    });

    // Enter key sends message
    inputMsg.addEventListener('keydown', (e) => {
      if (e.key === 'Enter' && !e.shiftKey) {
        e.preventDefault();
        sendBtn.click();
      }
    });
  }

  // Blog detail page
  function renderBlogDetail(blogId) {
    const blogs = loadFromStorage(STORAGE_KEYS.BLOGS) || [];
    const blog = blogs.find(b => b.id === blogId);
    if (!blog) {
      showNotification('Artikel tidak ditemukan.', 'error');
      if(currentUser) {
        if(currentUser.role === 'client') navigateTo('main-client');
        else if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
        else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      } else {
        navigateTo('login');
      }
      return;
    }
    const container = createElement('div', { classes: 'flex flex-col min-h-screen pb-16 bg-white' });

    // Header with back button
    const header = createElement('header', { classes: 'flex items-center justify-between bg-[${PRIMARY_COLOR}] text-white p-4 shadow-md sticky top-0 z-30' });
    const backBtn = createElement('button', { classes: 'focus:outline-none', attrs: { 'aria-label': 'Kembali' }, html: '<i class="fas fa-arrow-left fa-lg"></i>' });
    backBtn.addEventListener('click', () => {
      if(currentUser) {
        if(currentUser.role === 'client') navigateTo('main-client');
        else if(currentUser.role === 'lawyer') navigateTo('main-lawyer');
        else if(currentUser.role === 'notaris') navigateTo('main-notaris');
      } else {
        navigateTo('login');
      }
    });
    const title = createElement('h1', { classes: 'text-xl font-bold', text: blog.title });
    const dummy = createElement('div', { classes: 'w-6' }); // placeholder for spacing
    header.appendChild(backBtn);
    header.appendChild(title);
    header.appendChild(dummy);
    container.appendChild(header);

    // Content
    const contentSection = createElement('section', { classes: 'p-4 max-w-3xl mx-auto' });
    const img = createElement('img', {
      attrs: { src: blog.thumbnail, alt: `Thumbnail artikel: ${blog.title}` },
      classes: 'w-full h-64 object-cover rounded-lg mb-4',
    });
    const content = createElement('div', { classes: 'prose max-w-none' });
    content.textContent = blog.content;
    contentSection.appendChild(img);
    contentSection.appendChild(content);
    container.appendChild(contentSection);

    app.appendChild(container);
  }

  // Initial page load
  if (session && currentUser) {
    if (currentUser.role === 'client') navigateTo('main-client');
    else if (currentUser.role === 'lawyer') navigateTo('main-lawyer');
    else if (currentUser.role === 'notaris') navigateTo('main-notaris');
    else navigateTo('login');
  } else {
    navigateTo('splash');
  }

  // Global event listeners for inactivity
  ['click', 'mousemove', 'keydown', 'touchstart'].forEach(evt => {
    document.addEventListener(evt, () => {
      updateSessionActivity();
      resetInactivityTimer();
    });
  });

  // Back button handling (browser)
  window.addEventListener('popstate', (e) => {
    // For simplicity, reload page or navigate to main page
    if (currentUser) {
      if (currentUser.role === 'client') navigateTo('main-client');
      else if (currentUser.role === 'lawyer') navigateTo('main-lawyer');
      else if (currentUser.role === 'notaris') navigateTo('main-notaris');
    } else {
      navigateTo('login');
    }
  });

})();
</script>

</body>
</html>
