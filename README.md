<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>MHA Check Up - Health Checkup & Appointment Booking</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@0.446.0/dist/umd/lucide.min.js"></script>
    <style>
      html { scroll-behavior: smooth; }
      [id] { scroll-margin-top: 6rem; }
      .reveal { opacity: 0; transform: translateY(16px); transition: opacity 0.6s ease, transform 0.6s ease; }
      .reveal.is-visible { opacity: 1; transform: none; }
      .spinner { width: 1.1rem; height: 1.1rem; border: 2px solid rgba(255, 255, 255, 0.4); border-top-color: #fff; border-radius: 9999px; animation: spin 0.8s linear infinite; }
      @keyframes spin { to { transform: rotate(360deg); } }
      @media (prefers-reduced-motion: reduce) {
        html { scroll-behavior: auto; }
        .reveal { opacity: 1; transform: none; transition: none; }
        .spinner { animation-duration: 2.5s; }
      }
    </style>
  </head>
  <body class="min-h-screen bg-slate-50 font-sans text-slate-900 antialiased">

    <header class="sticky top-0 z-50 border-b border-slate-200/80 bg-white/90 backdrop-blur-md">
      <div class="mx-auto flex h-20 max-w-7xl items-center justify-between px-6">
        <a href="#hero" class="flex items-center gap-3 text-xl font-semibold text-slate-900">
          <span class="flex h-10 w-10 items-center justify-center rounded-xl bg-teal-600 text-white">
            <i data-lucide="heart-pulse" class="h-5 w-5"></i>
          </span>
          MHA Check Up
        </a>
        <nav class="hidden items-center gap-8 md:flex">
          <a href="#hero" class="text-sm font-medium text-slate-600 transition-colors hover:text-teal-700">Home</a>
          <a href="#packages" class="text-sm font-medium text-slate-600 transition-colors hover:text-teal-700">Packages</a>
          <a href="#services" class="text-sm font-medium text-slate-600 transition-colors hover:text-teal-700">Services</a>
          <a href="#doctors" class="text-sm font-medium text-slate-600 transition-colors hover:text-teal-700">Doctors</a>
        </nav>
        <div class="flex items-center gap-3">
          <button type="button" data-open-booking class="hidden rounded-full bg-teal-600 px-5 py-2.5 text-sm font-semibold text-white shadow-sm transition hover:bg-teal-700 md:inline-flex">Book Appointment</button>
          <button type="button" id="menu-toggle" aria-label="Open menu" aria-expanded="false" class="inline-flex h-10 w-10 items-center justify-center rounded-lg text-slate-700 transition hover:bg-slate-100 md:hidden">
            <i data-lucide="menu" class="h-5 w-5" id="menu-icon"></i>
          </button>
        </div>
      </div>
      <div id="mobile-menu" class="hidden border-t border-slate-200 bg-white px-6 py-4 md:hidden">
        <nav class="flex flex-col gap-1">
          <a href="#hero" class="mobile-link rounded-lg px-3 py-3 text-base font-medium text-slate-700 hover:bg-slate-50">Home</a>
          <a href="#packages" class="mobile-link rounded-lg px-3 py-3 text-base font-medium text-slate-700 hover:bg-slate-50">Packages</a>
          <a href="#services" class="mobile-link rounded-lg px-3 py-3 text-base font-medium text-slate-700 hover:bg-slate-50">Services</a>
          <a href="#doctors" class="mobile-link rounded-lg px-3 py-3 text-base font-medium text-slate-700 hover:bg-slate-50">Doctors</a>
        </nav>
        <button type="button" data-open-booking class="mt-3 w-full rounded-full bg-teal-600 py-3 text-sm font-semibold text-white">Book Appointment</button>
      </div>
    </header>

    <main>
      <section id="hero" class="relative isolate overflow-hidden">
        <img src="https://images.pexels.com/photos/6129450/pexels-photo-6129450.jpeg?auto=compress&cs=tinysrgb&h=650&w=940" alt="" class="absolute inset-0 -z-10 h-full w-full object-cover" />
        <div class="absolute inset-0 -z-10 bg-gradient-to-br from-teal-950/95 via-teal-900/90 to-teal-800/80"></div>
        <div class="mx-auto max-w-7xl px-6 py-24 md:py-32">
          <p class="reveal inline-flex items-center gap-2 rounded-full border border-white/20 bg-white/10 px-4 py-1.5 text-sm font-medium text-white">
            <i data-lucide="shield-check" class="h-4 w-4"></i>
            Trusted preventive care
          </p>
          <h1 class="reveal mt-6 max-w-3xl text-4xl font-bold leading-tight text-white md:text-6xl">Preventive Healthcare for Everyone</h1>
          <p class="reveal mt-6 max-w-2xl text-lg leading-relaxed text-teal-50">Take charge of your health with our comprehensive health checkup packages.</p>
          <div class="reveal mt-10 flex flex-col gap-4 sm:flex-row">
            <button type="button" data-open-booking class="inline-flex items-center justify-center gap-2 rounded-full bg-white px-7 py-3.5 text-base font-semibold text-teal-900 shadow-lg transition hover:-translate-y-0.5 hover:bg-teal-50">
              <i data-lucide="calendar-check" class="h-5 w-5"></i>
              Book Appointment
            </button>
            <a href="#packages" class="inline-flex items-center justify-center gap-2 rounded-full border border-white/50 px-7 py-3.5 text-base font-semibold text-white transition hover:bg-white/10">
              Explore Checkups
              <i data-lucide="arrow-right" class="h-5 w-5"></i>
            </a>
          </div>
          <dl class="reveal mt-16 grid grid-cols-2 gap-4 md:grid-cols-4">
            <div class="rounded-2xl border border-white/15 bg-white/10 p-6 backdrop-blur-sm transition hover:-translate-y-1 hover:bg-white/15">
              <dt class="text-sm font-medium text-teal-50">Doctors</dt>
              <dd class="mt-2 text-3xl font-bold text-white">100+</dd>
            </div>
            <div class="rounded-2xl border border-white/15 bg-white/10 p-6 backdrop-blur-sm transition hover:-translate-y-1 hover:bg-white/15">
              <dt class="text-sm font-medium text-teal-50">Patients</dt>
              <dd class="mt-2 text-3xl font-bold text-white">1000+</dd>
            </div>
            <div class="rounded-2xl border border-white/15 bg-white/10 p-6 backdrop-blur-sm transition hover:-translate-y-1 hover:bg-white/15">
              <dt class="text-sm font-medium text-teal-50">Checkups</dt>
              <dd class="mt-2 text-3xl font-bold text-white">5000+</dd>
            </div>
            <div class="rounded-2xl border border-white/15 bg-white/10 p-6 backdrop-blur-sm transition hover:-translate-y-1 hover:bg-white/15">
              <dt class="text-sm font-medium text-teal-50">Years Experience</dt>
              <dd class="mt-2 text-3xl font-bold text-white">10+</dd>
            </div>
          </dl>
        </div>
      </section>

      <section id="packages" class="bg-white py-24">
        <div class="mx-auto max-w-7xl px-6">
          <div class="reveal mx-auto max-w-2xl text-center">
            <p class="text-sm font-semibold uppercase tracking-widest text-teal-700">Packages</p>
            <h2 class="mt-3 text-3xl font-bold leading-tight text-slate-900 md:text-4xl">Health Checkup Packages</h2>
            <p class="mt-4 text-base leading-relaxed text-slate-600">Clear, transparent pricing for every stage of life. Choose the package that fits you and book in minutes.</p>
          </div>
          <div id="packages-grid" class="mt-14 grid gap-6 md:grid-cols-2 xl:grid-cols-4"></div>
        </div>
      </section>

      <section id="services" class="bg-slate-50 py-24">
        <div class="mx-auto max-w-7xl px-6">
          <div class="reveal mx-auto max-w-2xl text-center">
            <p class="text-sm font-semibold uppercase tracking-widest text-teal-700">Services</p>
            <h2 class="mt-3 text-3xl font-bold leading-tight text-slate-900 md:text-4xl">Our Health Services</h2>
            <p class="mt-4 text-base leading-relaxed text-slate-600">Specialist care under one roof, so your checkup results connect to the right treatment.</p>
          </div>
          <div id="services-grid" class="mt-14 grid gap-6 sm:grid-cols-2 lg:grid-cols-4"></div>
        </div>
      </section>

      <section id="doctors" class="bg-white py-24">
        <div class="mx-auto max-w-7xl px-6">
          <div class="reveal mx-auto max-w-2xl text-center">
            <p class="text-sm font-semibold uppercase tracking-widest text-teal-700">Our Team</p>
            <h2 class="mt-3 text-3xl font-bold leading-tight text-slate-900 md:text-4xl">Meet Our Doctors</h2>
            <p class="mt-4 text-base leading-relaxed text-slate-600">Experienced physicians who take the time to explain your results and plan your next steps.</p>
          </div>
          <div id="doctors-grid" class="mt-14 grid gap-8 sm:grid-cols-2 lg:mx-auto lg:max-w-4xl"></div>
        </div>
      </section>

      <section id="appointment" class="bg-slate-50 py-24">
        <div class="mx-auto max-w-7xl px-6">
          <div class="reveal mx-auto max-w-2xl text-center">
            <p class="text-sm font-semibold uppercase tracking-widest text-teal-700">Booking</p>
            <h2 class="mt-3 text-3xl font-bold leading-tight text-slate-900 md:text-4xl">Book Your Appointment</h2>
            <p class="mt-4 text-base leading-relaxed text-slate-600">Tell us a little about yourself and when you would like to visit.</p>
          </div>

          <div class="mt-14 grid gap-12 lg:grid-cols-5 lg:gap-16">
            <ul class="reveal space-y-6 lg:col-span-2">
              <li class="flex items-start gap-4">
                <span class="flex h-11 w-11 shrink-0 items-center justify-center rounded-xl bg-teal-100 text-teal-700"><i data-lucide="calendar-check" class="h-5 w-5"></i></span>
                <p class="pt-2 text-base leading-relaxed text-slate-700">Choose a package, doctor, and time that suit you.</p>
              </li>
              <li class="flex items-start gap-4">
                <span class="flex h-11 w-11 shrink-0 items-center justify-center rounded-xl bg-teal-100 text-teal-700"><i data-lucide="shield-check" class="h-5 w-5"></i></span>
                <p class="pt-2 text-base leading-relaxed text-slate-700">Get a registration number straight away for your records.</p>
              </li>
              <li class="flex items-start gap-4">
                <span class="flex h-11 w-11 shrink-0 items-center justify-center rounded-xl bg-teal-100 text-teal-700"><i data-lucide="clock" class="h-5 w-5"></i></span>
                <p class="pt-2 text-base leading-relaxed text-slate-700">Your request stays pending until our team confirms the slot.</p>
              </li>
            </ul>

            <div class="reveal lg:col-span-3">
              <div id="booking-success" class="hidden flex-col items-center rounded-3xl border border-teal-200 bg-white p-10 text-center shadow-sm">
                <span class="flex h-16 w-16 items-center justify-center rounded-full bg-teal-600 text-white">
                  <i data-lucide="circle-check" class="h-8 w-8"></i>
                </span>
                <h3 class="mt-6 text-2xl font-bold text-slate-900">Appointment request received</h3>
                <p class="mt-3 max-w-md text-sm leading-relaxed text-slate-600">Keep this registration number for your records. Your booking stays pending until our team confirms it.</p>
                <p id="registration-number" class="mt-6 rounded-xl bg-teal-50 px-6 py-4 font-mono text-lg font-semibold tracking-wide text-teal-800"></p>
                <button type="button" id="new-booking" class="mt-8 inline-flex items-center gap-2 rounded-full border border-slate-300 px-6 py-2.5 text-sm font-semibold text-slate-700 transition hover:bg-slate-50">
                  <i data-lucide="rotate-ccw" class="h-4 w-4"></i>
                  Book another appointment
                </button>
              </div>

              <form id="appointment-form" novalidate class="rounded-3xl border border-slate-200 bg-white p-6 shadow-sm md:p-10">
                <div id="form-alert" role="alert" class="hidden mb-8 rounded-xl border border-rose-200 bg-rose-50 px-4 py-3 text-sm font-medium text-rose-700"></div>

                <fieldset id="form-fields" class="grid gap-6 md:grid-cols-2">
                  <p class="text-xs font-semibold uppercase tracking-widest text-slate-500 md:col-span-2">Patient details</p>

                  <div class="flex flex-col gap-2">
                    <label for="fullName" class="text-sm font-medium text-slate-700">Full name</label>
                    <input id="fullName" name="fullName" type="text" autocomplete="name" class="field-input" />
                    <p class="field-error" data-error-for="fullName"></p>
                  </div>
                  <div class="flex flex-col gap-2">
                    <label for="mobile" class="text-sm font-medium text-slate-700">Mobile number</label>
                    <input id="mobile" name="mobile" type="tel" autocomplete="tel" class="field-input" />
                    <p class="field-error" data-error-for="mobile"></p>
                  </div>
                  <div class="flex flex-col gap-2">
                    <label for="email" class="text-sm font-medium text-slate-700">Email</label>
                    <input id="email" name="email" type="email" autocomplete="email" class="field-input" />
                    <p class="field-error" data-error-for="email"></p>
                  </div>
                  <div class="grid grid-cols-2 gap-6">
                    <div class="flex flex-col gap-2">
                      <label for="age" class="text-sm font-medium text-slate-700">Age</label>
                      <input id="age" name="age" type="number" min="0" max="120" class="field-input" />
                      <p class="field-error" data-error-for="age"></p>
                    </div>
                    <div class="flex flex-col gap-2">
                      <label for="gender" class="text-sm font-medium text-slate-700">Gender</label>
                      <select id="gender" name="gender" class="field-input">
                        <option value="">Select</option>
                        <option value="male">Male</option>
                        <option value="female">Female</option>
                        <option value="other">Other</option>
                      </select>
                      <p class="field-error" data-error-for="gender"></p>
                    </div>
                  </div>
                  <div class="flex flex-col gap-2">
                    <label for="city" class="text-sm font-medium text-slate-700">City</label>
                    <input id="city" name="city" type="text" autocomplete="address-level2" class="field-input" />
                    <p class="field-error" data-error-for="city"></p>
                  </div>

                  <p class="mt-4 text-xs font-semibold uppercase tracking-widest text-slate-500 md:col-span-2">Appointment</p>

                  <div class="flex flex-col gap-2">
                    <label for="packageName" class="text-sm font-medium text-slate-700">Health checkup package</label>
                    <select id="packageName" name="packageName" class="field-input"></select>
                  </div>
                  <div class="flex flex-col gap-2">
                    <label for="doctorName" class="text-sm font-medium text-slate-700">Preferred doctor</label>
                    <select id="doctorName" name="doctorName" class="field-input"></select>
                  </div>
                  <div class="flex flex-col gap-2">
                    <label for="specialty" class="text-sm font-medium text-slate-700">Preferred specialty</label>
                    <select id="specialty" name="specialty" class="field-input"></select>
                  </div>
                  <div class="hidden md:block" aria-hidden="true"></div>
                  <div class="flex flex-col gap-2">
                    <label for="date" class="text-sm font-medium text-slate-700">Appointment date</label>
                    <input id="date" name="date" type="date" class="field-input" />
                    <p class="field-error" data-error-for="date"></p>
                  </div>
                  <div class="flex flex-col gap-2">
                    <label for="time" class="text-sm font-medium text-slate-700">Appointment time</label>
                    <input id="time" name="time" type="time" class="field-input" />
                    <p class="field-error" data-error-for="time"></p>
                  </div>
                  <div class="flex flex-col gap-2 md:col-span-2">
                    <label for="notes" class="text-sm font-medium text-slate-700">Additional notes</label>
                    <textarea id="notes" name="notes" rows="4" maxlength="2000" class="field-input resize-y"></textarea>
                  </div>
                  <div class="md:col-span-2">
                    <button type="submit" id="submit-button" class="inline-flex w-full items-center justify-center gap-2 rounded-full bg-teal-600 py-3.5 text-base font-semibold text-white shadow-sm transition hover:bg-teal-700 disabled:cursor-not-allowed disabled:bg-teal-400">
                      <span id="submit-spinner" class="spinner hidden"></span>
                      <span id="submit-label">Submit booking</span>
                    </button>
                  </div>
                </fieldset>
              </form>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="bg-slate-900 py-12 text-slate-300">
      <div class="mx-auto flex max-w-7xl flex-col items-center justify-between gap-6 px-6 md:flex-row">
        <div class="flex items-center gap-3 text-lg font-semibold text-white">
          <span class="flex h-9 w-9 items-center justify-center rounded-xl bg-teal-600"><i data-lucide="heart-pulse" class="h-5 w-5"></i></span>
          MHA Check Up
        </div>
        <nav class="flex flex-wrap justify-center gap-6">
          <a href="#hero" class="text-sm transition hover:text-white">Home</a>
          <a href="#packages" class="text-sm transition hover:text-white">Packages</a>
          <a href="#services" class="text-sm transition hover:text-white">Services</a>
          <a href="#doctors" class="text-sm transition hover:text-white">Doctors</a>
          <a href="#appointment" class="text-sm transition hover:text-white">Book</a>
        </nav>
        <p class="text-sm text-slate-400">&copy; <span id="year"></span> MHA Check Up. All rights reserved.</p>
      </div>
    </footer>

    <style>
      .field-input { width: 100%; border-radius: 0.75rem; border: 1px solid #cbd5e1; background: #fff; padding: 0.75rem 1rem; font-size: 0.875rem; color: #0f172a; transition: border-color 0.2s, box-shadow 0.2s; }
      .field-input:focus { outline: none; border-color: #0d9488; box-shadow: 0 0 0 4px #ccfbf1; }
      .field-input.is-invalid { border-color: #fb7185; }
      .field-error { min-height: 0; font-size: 0.75rem; font-weight: 500; color: #e11d48; }
      .field-error:empty { display: none; }
      fieldset:disabled { opacity: 0.85; }
    </style>

    <script>
      const SUPABASE_URL = 'REPLACE_WITH_SUPABASE_URL';
      const SUPABASE_ANON_KEY = 'REPLACE_WITH_SUPABASE_ANON_KEY';
      const isConfigured = !SUPABASE_URL.startsWith('REPLACE') && !SUPABASE_ANON_KEY.startsWith('REPLACE');

      const packages = [
        { name: 'Basic Wellness Package', description: 'Essential screenings for everyday health monitoring.', price: 50, highlights: ['Complete blood count', 'Blood sugar screening', 'Blood pressure check', 'General physician review'] },
        { name: 'Executive Health Package', description: 'A comprehensive checkup designed for busy professionals.', price: 150, highlights: ['Full body blood panel', 'Cardiac risk assessment', 'Liver and kidney function', 'Detailed consultation'], featured: true },
        { name: 'Senior Citizen Package', description: 'Health checks tailored to the needs of older adults.', price: 100, highlights: ['Bone density screening', 'Heart health panel', 'Vision and hearing tests', 'Geriatric consultation'] },
        { name: "Women's Health Package", description: 'Specialized health checks for women at every stage of life.', price: 80, highlights: ['Thyroid panel', 'Hormone profile', 'Breast health screening', 'Gynecology consultation'] },
      ];

      const services = [
        { name: 'Cardiology', description: 'Heart health evaluations and long-term cardiac care.', icon: 'heart' },
        { name: 'Neurology', description: 'Diagnosis and management of brain and nerve conditions.', icon: 'brain' },
        { name: 'Orthopedics', description: 'Care for bones, joints, and musculoskeletal health.', icon: 'bone' },
        { name: 'Pediatrics', description: 'Compassionate medical care for infants and children.', icon: 'baby' },
        { name: 'General Medicine', description: 'Everyday illness care and whole-person check-ins.', icon: 'stethoscope' },
        { name: 'Dermatology', description: 'Skin, hair, and nail conditions treated with precision.', icon: 'sparkles' },
        { name: 'Nutrition & Wellness', description: 'Personalized diet plans and lifestyle guidance.', icon: 'salad' },
        { name: 'Preventive Health', description: 'Screenings that catch problems before they start.', icon: 'shield-check' },
      ];

      const doctors = [
        { name: 'Dr. John Doe', specialty: 'Cardiologist', image: 'https://images.pexels.com/photos/32160037/pexels-photo-32160037.jpeg?auto=compress&cs=tinysrgb&h=650&w=940', imageAlt: 'Portrait of Dr. John Doe, cardiologist' },
        { name: 'Dr. Jane Smith', specialty: 'Pediatrician', image: 'https://images.pexels.com/photos/7578810/pexels-photo-7578810.jpeg?auto=compress&cs=tinysrgb&h=650&w=940', imageAlt: 'Portrait of Dr. Jane Smith, pediatrician' },
      ];

      const packagesGrid = document.getElementById('packages-grid');
      const servicesGrid = document.getElementById('services-grid');
      const doctorsGrid = document.getElementById('doctors-grid');

      packagesGrid.innerHTML = packages.map((pkg, index) => `
        <article class="reveal relative flex flex-col rounded-3xl border p-8 transition hover:-translate-y-1 hover:shadow-xl ${pkg.featured ? 'border-teal-500 bg-teal-50/60 shadow-lg' : 'border-slate-200 bg-white shadow-sm'}">
          ${pkg.featured ? '<span class="absolute -top-3 left-8 rounded-full bg-teal-600 px-3 py-1 text-xs font-semibold text-white">Most Popular</span>' : ''}
          <h3 class="text-xl font-semibold text-slate-900">${pkg.name}</h3>
          <p class="mt-2 text-sm leading-relaxed text-slate-600">${pkg.description}</p>
          <p class="mt-6 text-4xl font-bold text-slate-900">$${pkg.price}</p>
          <ul class="mt-6 flex-1 space-y-3">
            ${pkg.highlights.map((item) => `<li class="flex items-start gap-3 text-sm text-slate-700"><i data-lucide="check" class="mt-0.5 h-4 w-4 shrink-0 text-teal-600"></i>${item}</li>`).join('')}
          </ul>
          <button type="button" data-book-package="${index}" class="mt-8 w-full rounded-full bg-teal-600 py-3 text-sm font-semibold text-white transition hover:bg-teal-700">Book Now</button>
        </article>`).join('');

      servicesGrid.innerHTML = services.map((service) => `
        <div class="reveal group rounded-2xl border border-slate-200 bg-white p-6 transition hover:-translate-y-1 hover:border-teal-200 hover:shadow-lg">
          <span class="flex h-12 w-12 items-center justify-center rounded-xl bg-teal-50 text-teal-700 transition group-hover:bg-teal-600 group-hover:text-white">
            <i data-lucide="${service.icon}" class="h-6 w-6"></i>
          </span>
          <h3 class="mt-5 text-lg font-semibold text-slate-900">${service.name}</h3>
          <p class="mt-2 text-sm leading-relaxed text-slate-600">${service.description}</p>
        </div>`).join('');

      doctorsGrid.innerHTML = doctors.map((doctor, index) => `
        <article class="reveal group overflow-hidden rounded-3xl border border-slate-200 bg-white shadow-sm transition hover:-translate-y-1 hover:shadow-xl">
          <div class="aspect-[4/5] overflow-hidden bg-slate-100">
            <img src="${doctor.image}" alt="${doctor.imageAlt}" loading="lazy" class="h-full w-full object-cover transition duration-500 group-hover:scale-105" />
          </div>
          <div class="p-6">
            <h3 class="text-xl font-semibold text-slate-900">${doctor.name}</h3>
            <p class="mt-1 text-sm font-medium text-teal-700">${doctor.specialty}</p>
            <button type="button" data-book-doctor="${index}" class="mt-5 w-full rounded-full border border-teal-600 py-2.5 text-sm font-semibold text-teal-700 transition hover:bg-teal-600 hover:text-white">Book with ${doctor.name}</button>
          </div>
        </article>`).join('');

      const form = document.getElementById('appointment-form');
      const fieldset = document.getElementById('form-fields');
      const formAlert = document.getElementById('form-alert');
      const successPanel = document.getElementById('booking-success');
      const submitButton = document.getElementById('submit-button');
      const submitLabel = document.getElementById('submit-label');
      const submitSpinner = document.getElementById('submit-spinner');

      const packageSelect = document.getElementById('packageName');
      const doctorSelect = document.getElementById('doctorName');
      const specialtySelect = document.getElementById('specialty');
      const dateInput = document.getElementById('date');

      const fillOptions = (select, placeholder, values) => {
        select.innerHTML = [`<option value="">${placeholder}</option>`, ...values].join('');
      };
      fillOptions(packageSelect, 'Not sure yet', packages.map((pkg) => `<option value="${pkg.name}">${pkg.name} ($${pkg.price})</option>`));
      fillOptions(doctorSelect, 'No preference', doctors.map((doctor) => `<option value="${doctor.name}">${doctor.name}</option>`));
      fillOptions(specialtySelect, 'No preference', services.map((service) => `<option value="${service.name}">${service.name}</option>`));

      const todayIsoDate = () => {
        const now = new Date();
        const local = new Date(now.getTime() - now.getTimezoneOffset() * 60000);
        return local.toISOString().slice(0, 10);
      };
      dateInput.min = todayIsoDate();
      document.getElementById('year').textContent = new Date().getFullYear();

      const readForm = () => {
        const data = new FormData(form);
        const get = (key) => String(data.get(key) ?? '').trim();
        return {
          fullName: get('fullName'),
          mobile: get('mobile'),
          email: get('email'),
          age: get('age'),
          gender: get('gender'),
          city: get('city'),
          packageName: get('packageName'),
          doctorName: get('doctorName'),
          specialty: get('specialty'),
          date: get('date'),
          time: get('time'),
          notes: get('notes'),
        };
      };

      const validate = (data) => {
        const errors = {};
        const age = Number(data.age);
        if (!data.fullName) errors.fullName = 'Please enter your full name.';
        if (!/^\+?[0-9\s-]{6,20}$/.test(data.mobile)) errors.mobile = 'Enter a valid mobile number.';
        if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(data.email)) errors.email = 'Enter a valid email address.';
        if (data.age === '' || !Number.isInteger(age) || age < 0 || age > 120) errors.age = 'Enter an age between 0 and 120.';
        if (!['male', 'female', 'other'].includes(data.gender)) errors.gender = 'Select a gender.';
        if (!data.city) errors.city = 'Please enter your city.';
        if (!data.date) errors.date = 'Choose an appointment date.';
        else if (data.date < todayIsoDate()) errors.date = 'The appointment date cannot be in the past.';
        if (!data.time) errors.time = 'Choose an appointment time.';
        return errors;
      };

      const setFieldError = (name, message) => {
        const input = form.elements[name];
        const errorText = form.querySelector(`[data-error-for="${name}"]`);
        if (input) input.classList.toggle('is-invalid', Boolean(message));
        if (errorText) errorText.textContent = message || '';
      };

      const clearErrors = () => {
        formAlert.classList.add('hidden');
        formAlert.textContent = '';
        ['fullName', 'mobile', 'email', 'age', 'gender', 'city', 'date', 'time'].forEach((name) => setFieldError(name, ''));
      };

      const showFormAlert = (message) => {
        formAlert.textContent = message;
        formAlert.classList.remove('hidden');
      };

      const setSubmitting = (isSubmitting) => {
        fieldset.disabled = isSubmitting;
        submitButton.disabled = isSubmitting;
        submitSpinner.classList.toggle('hidden', !isSubmitting);
        submitLabel.textContent = isSubmitting ? 'Submitting...' : 'Submit booking';
      };

      const createRegistrationNumber = () => {
        const alphabet = 'ABCDEFGHJKLMNPQRSTUVWXYZ23456789';
        const bytes = crypto.getRandomValues(new Uint8Array(6));
        const code = Array.from(bytes, (byte) => alphabet[byte % alphabet.length]).join('');
        return `MHA-${new Date().getFullYear()}-${code}`;
      };

      const optionalText = (value) => value || null;

      const insertAppointment = async (data, registrationNumber) => {
        const response = await fetch(`${SUPABASE_URL}/rest/v1/appointments`, {
          method: 'POST',
          headers: {
            apikey: SUPABASE_ANON_KEY,
            Authorization: `Bearer ${SUPABASE_ANON_KEY}`,
            'Content-Type': 'application/json',
            Prefer: 'return=minimal',
          },
          body: JSON.stringify({
            registration_number: registrationNumber,
            full_name: data.fullName,
            mobile: data.mobile,
            email: data.email,
            age: Number(data.age),
            gender: data.gender,
            city: data.city,
            package_name: optionalText(data.packageName),
            doctor_name: optionalText(data.doctorName),
            specialty: optionalText(data.specialty),
            appointment_date: data.date,
            appointment_time: data.time,
            notes: optionalText(data.notes),
          }),
        });
        if (!response.ok) throw new Error(`Booking request failed with status ${response.status}`);
      };

      form.addEventListener('input', (event) => {
        if (event.target.name) setFieldError(event.target.name, '');
      });

      form.addEventListener('submit', async (event) => {
        event.preventDefault();
        clearErrors();

        const data = readForm();
        const errors = validate(data);
        Object.entries(errors).forEach(([name, message]) => setFieldError(name, message));
        if (Object.keys(errors).length > 0) {
          showFormAlert('Please fix the highlighted fields and try again.');
          return;
        }

        if (!isConfigured) {
          showFormAlert('Bookings are not connected yet. Add the database connection details at the top of this file.');
          return;
        }

        setSubmitting(true);
        const registrationNumber = createRegistrationNumber();
        try {
          await insertAppointment(data, registrationNumber);
          document.getElementById('registration-number').textContent = registrationNumber;
          form.classList.add('hidden');
          successPanel.classList.remove('hidden');
          successPanel.classList.add('flex');
          form.reset();
          lucide.createIcons();
        } catch (error) {
          console.error(error);
          showFormAlert('We could not submit your booking. Please check your details and try again.');
        } finally {
          setSubmitting(false);
        }
      });

      document.getElementById('new-booking').addEventListener('click', () => {
        successPanel.classList.add('hidden');
        successPanel.classList.remove('flex');
        form.classList.remove('hidden');
      });

      const openBooking = (preset = {}) => {
        if (preset.packageIndex !== undefined) packageSelect.value = packages[preset.packageIndex].name;
        if (preset.doctorIndex !== undefined) doctorSelect.value = doctors[preset.doctorIndex].name;
        document.getElementById('appointment').scrollIntoView({ behavior: 'smooth' });
      };

      document.addEventListener('click', (event) => {
        const packageButton = event.target.closest('[data-book-package]');
        if (packageButton) return openBooking({ packageIndex: Number(packageButton.dataset.bookPackage) });
        const doctorButton = event.target.closest('[data-book-doctor]');
        if (doctorButton) return openBooking({ doctorIndex: Number(doctorButton.dataset.bookDoctor) });
        if (event.target.closest('[data-open-booking]')) openBooking();
      });

      const menuToggle = document.getElementById('menu-toggle');
      const mobileMenu = document.getElementById('mobile-menu');
      menuToggle.addEventListener('click', () => {
        const isOpen = mobileMenu.classList.toggle('hidden') === false;
        menuToggle.setAttribute('aria-expanded', String(isOpen));
        menuToggle.setAttribute('aria-label', isOpen ? 'Close menu' : 'Open menu');
        menuToggle.querySelector('svg, i')?.replaceWith(Object.assign(document.createElement('i'), { dataset: { lucide: isOpen ? 'x' : 'menu' }, className: 'h-5 w-5' }));
        lucide.createIcons();
      });
      document.querySelectorAll('.mobile-link').forEach((link) => {
        link.addEventListener('click', () => {
          mobileMenu.classList.add('hidden');
          menuToggle.setAttribute('aria-expanded', 'false');
        });
      });

      const revealObserver = new IntersectionObserver((entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            entry.target.classList.add('is-visible');
            revealObserver.unobserve(entry.target);
          }
        });
      }, { threshold: 0.12 });
      document.querySelectorAll('.reveal').forEach((element) => revealObserver.observe(element));

      lucide.createIcons();
    </script>
  </body>
</html>
