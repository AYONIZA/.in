<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AYONIZA | Purity with Grace</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,400&family=Montserrat:wght@200;300;400;500;600&display=swap" rel="stylesheet">
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        'ayoniza-bg': '#FAF8F5',
                        'ayoniza-card': '#FFFFFF',
                        'ayoniza-dark': '#1C1917',
                        'ayoniza-gold': '#D4AF37',
                        'ayoniza-rose': '#E8C3B9',
                        'ayoniza-accent': '#B8860B',
                        'ayoniza-muted': '#78716C'
                    },
                    fontFamily: {
                        serif: ['Cormorant Garamond', 'serif'],
                        sans: ['Montserrat', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #FAF8F5;
            color: #1C1917;
            font-family: 'Montserrat', sans-serif;
        }
        h1, h2, h3, .brand-font {
            font-family: 'Cormorant Garamond', serif;
        }
        .gold-gradient-text {
            background: linear-gradient(135deg, #B8860B 0%, #D4AF37 50%, #E8C3B9 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .btn-gold {
            background: linear-gradient(135deg, #1C1917 0%, #2B2B2B 100%);
            border: 1px solid #D4AF37;
            transition: all 0.4s ease;
        }
        .btn-gold:hover {
            background: linear-gradient(135deg, #D4AF37 0%, #B8860B 100%);
            color: #1C1917;
            box-shadow: 0 10px 25px -5px rgba(212, 175, 55, 0.4);
        }
        .toast-slide {
            animation: slideIn 0.3s forwards, fadeOut 0.5s 2.5s forwards;
        }
        @keyframes slideIn {
            from { transform: translateY(-100%); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }
        @keyframes fadeOut {
            from { opacity: 1; }
            to { opacity: 0; }
        }
    </style>
</head>
<body class="antialiased selection:bg-ayoniza-rose selection:text-ayoniza-dark">

    <!-- Top Announcement Bar -->
    <div class="bg-ayoniza-dark text-amber-100 text-xs tracking-widest py-2 text-center uppercase font-light">
        Complimentary Express Worldwide Shipping on Orders Over $150
    </div>

    <!-- Navigation Header -->
    <header class="sticky top-0 z-50 bg-ayoniza-bg/90 backdrop-blur-md border-b border-stone-200/60 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="flex items-center justify-between h-24">
                
                <!-- Desktop Left Links -->
                <nav class="hidden md:flex space-x-8 text-xs tracking-widest uppercase font-medium text-stone-700">
                    <a href="#home" class="hover:text-ayoniza-gold transition-colors">Home</a>
                    <a href="#collection" class="hover:text-ayoniza-gold transition-colors">Collection</a>
                    <a href="#about" class="hover:text-ayoniza-gold transition-colors">Our Story</a>
                </nav>

                <!-- Brand Logo Center -->
                <div class="text-center flex-1 md:flex-initial">
                    <a href="#home" class="inline-block group">
                        <h1 class="text-3xl sm:text-4xl tracking-widest font-semibold brand-font text-stone-900 group-hover:text-ayoniza-gold transition-colors">
                            AYONIZA
                        </h1>
                        <p class="text-[9px] sm:text-[10px] tracking-[0.3em] text-stone-500 uppercase -mt-1 font-light">
                            Purity With Grace
                        </p>
                    </a>
                </div>

                <!-- Right Menu / Cart -->
                <div class="hidden md:flex items-center space-x-6 text-stone-700">
                    <a href="#reviews" class="text-xs tracking-widest uppercase hover:text-ayoniza-gold transition-colors">Reviews</a>
                    <a href="#contact" class="text-xs tracking-widest uppercase hover:text-ayoniza-gold transition-colors">Contact</a>
                    <button onclick="toggleCartDrawer()" class="relative p-2 text-stone-800 hover:text-ayoniza-gold transition-colors focus:outline-none">
                        <i class="fa-solid fa-bag-shopping text-lg"></i>
                        <span id="cart-count" class="absolute -top-1 -right-1 bg-ayoniza-gold text-stone-900 text-[10px] font-bold rounded-full w-4 h-4 flex items-center justify-center">0</span>
                    </button>
                </div>

                <!-- Mobile Hamburger Button -->
                <div class="md:hidden flex items-center space-x-4">
                    <button onclick="toggleCartDrawer()" class="relative p-2 text-stone-800 hover:text-ayoniza-gold transition-colors">
                        <i class="fa-solid fa-bag-shopping text-lg"></i>
                        <span id="cart-count-mobile" class="absolute -top-1 -right-1 bg-ayoniza-gold text-stone-900 text-[10px] font-bold rounded-full w-4 h-4 flex items-center justify-center">0</span>
                    </button>
                    <button id="mobile-menu-btn" class="p-2 text-stone-800 focus:outline-none">
                        <i class="fa-solid fa-bars text-xl"></i>
                    </button>
                </div>

            </div>
        </div>

        <!-- Mobile Navigation Menu -->
        <div id="mobile-menu" class="hidden md:hidden bg-ayoniza-bg border-b border-stone-200 px-6 pt-4 pb-6 space-y-4 text-center">
            <a href="#home" class="block text-sm tracking-widest uppercase text-stone-700 hover:text-ayoniza-gold" onclick="toggleMobileMenu()">Home</a>
            <a href="#collection" class="block text-sm tracking-widest uppercase text-stone-700 hover:text-ayoniza-gold" onclick="toggleMobileMenu()">Collection</a>
            <a href="#about" class="block text-sm tracking-widest uppercase text-stone-700 hover:text-ayoniza-gold" onclick="toggleMobileMenu()">Our Story</a>
            <a href="#reviews" class="block text-sm tracking-widest uppercase text-stone-700 hover:text-ayoniza-gold" onclick="toggleMobileMenu()">Reviews</a>
            <a href="#contact" class="block text-sm tracking-widest uppercase text-stone-700 hover:text-ayoniza-gold" onclick="toggleMobileMenu()">Contact Us</a>
        </div>
    </header>

    <!-- Hero Section -->
    <section id="home" class="relative min-h-[85vh] flex items-center justify-center overflow-hidden bg-stone-900">
        <!-- Background Overlay Image -->
        <div class="absolute inset-0 z-0">
            <img src="https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?q=80&w=2000&auto=format&fit=crop" 
                 alt="Luxury Jewelry Banner" 
                 class="w-full h-full object-cover object-center opacity-40 scale-105 transform hover:scale-100 transition-transform duration-10000">
            <div class="absolute inset-0 bg-gradient-to-t from-stone-950 via-stone-950/40 to-transparent"></div>
        </div>

        <!-- Hero Content -->
        <div class="relative z-10 max-w-4xl mx-auto text-center px-4 sm:px-6 py-20">
            <span class="inline-block text-ayoniza-rose text-xs sm:text-sm tracking-[0.4em] uppercase mb-4 font-medium">
                The Essence of Luxury
            </span>
            <h2 class="text-4xl sm:text-6xl md:text-7xl font-light text-amber-50 mb-6 leading-tight brand-font">
                Elegance Redefined,<br><span class="italic font-normal gold-gradient-text">Grace Embodied.</span>
            </h2>
            <p class="text-stone-300 text-sm sm:text-base font-light max-w-2xl mx-auto mb-10 leading-relaxed tracking-wide">
                Discover AYONIZA's curated ensemble of handcrafted fine jewelry and premium personal care. Created for those who embody natural elegance and timeless purity.
            </p>
            <div class="flex flex-col sm:flex-row items-center justify-center gap-4">
                <a href="#collection" class="btn-gold text-amber-50 px-8 py-4 text-xs tracking-[0.2em] uppercase font-medium rounded-full w-full sm:w-auto">
                    Explore Collection
                </a>
                <a href="#about" class="border border-stone-400 text-stone-200 hover:bg-stone-100 hover:text-stone-900 px-8 py-4 text-xs tracking-[0.2em] uppercase font-medium rounded-full transition-all duration-300 w-full sm:w-auto">
                    Discover Our Story
                </a>
            </div>
        </div>
    </section>

    <!-- Featured Collections -->
    <section id="collection" class="py-24 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        
        <div class="text-center max-w-2xl mx-auto mb-16">
            <h2 class="text-xs text-ayoniza-accent tracking-[0.3em] uppercase font-semibold mb-2">Curated Elegance</h2>
            <p class="text-3xl sm:text-5xl font-light brand-font text-stone-900">Featured Creations</p>
            <div class="w-12 h-0.5 bg-ayoniza-gold mx-auto mt-4"></div>
        </div>

        <!-- Product Grid -->
        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
            
            <!-- Product 1 -->
            <div class="group bg-ayoniza-card rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500 flex flex-col border border-stone-200/70">
                <div class="relative overflow-hidden aspect-square bg-stone-100">
                    <img src="https://images.unsplash.com/photo-1599643478518-a784e5dc4c8f?q=80&w=800&auto=format&fit=crop" 
                         alt="Celestial Diamond Pendant" 
                         class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
                    <span class="absolute top-4 left-4 bg-stone-900 text-amber-100 text-[10px] tracking-widest uppercase px-3 py-1 rounded-full font-light">Best Seller</span>
                </div>
                <div class="p-6 flex flex-col flex-grow text-center">
                    <p class="text-[10px] tracking-widest uppercase text-stone-400 mb-1">Fine Jewelry</p>
                    <h3 class="brand-font text-xl text-stone-900 mb-2 font-medium">Celestial Pearl Drop Necklace</h3>
                    <p class="text-stone-500 text-xs mb-4 font-light line-clamp-2">Pure freshwater pearls set in 18k handcrafted gold-plated silver chain.</p>
                    <div class="mt-auto flex items-center justify-between pt-4 border-t border-stone-100">
                        <span class="text-lg font-medium text-stone-800">$185</span>
                        <button onclick="addToCart('Celestial Pearl Drop Necklace', 185)" class="bg-stone-900 hover:bg-ayoniza-gold hover:text-stone-900 text-stone-100 p-3 rounded-full transition-colors duration-300">
                            <i class="fa-solid fa-plus text-xs"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Product 2 -->
            <div class="group bg-ayoniza-card rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500 flex flex-col border border-stone-200/70">
                <div class="relative overflow-hidden aspect-square bg-stone-100">
                    <img src="https://images.unsplash.com/photo-1630019852942-f89202989a59?q=80&w=800&auto=format&fit=crop" 
                         alt="Rose Radiance Elixir" 
                         class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
                    <span class="absolute top-4 left-4 bg-ayoniza-rose text-stone-900 text-[10px] tracking-widest uppercase px-3 py-1 rounded-full font-medium">Organic</span>
                </div>
                <div class="p-6 flex flex-col flex-grow text-center">
                    <p class="text-[10px] tracking-widest uppercase text-stone-400 mb-1">Personal Care</p>
                    <h3 class="brand-font text-xl text-stone-900 mb-2 font-medium">Grace Botanical Facial Oil</h3>
                    <p class="text-stone-500 text-xs mb-4 font-light line-clamp-2">Infused with cold-pressed botanical oils and natural rose essence for glowing skin.</p>
                    <div class="mt-auto flex items-center justify-between pt-4 border-t border-stone-100">
                        <span class="text-lg font-medium text-stone-800">$72</span>
                        <button onclick="addToCart('Grace Botanical Facial Oil', 72)" class="bg-stone-900 hover:bg-ayoniza-gold hover:text-stone-900 text-stone-100 p-3 rounded-full transition-colors duration-300">
                            <i class="fa-solid fa-plus text-xs"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Product 3 -->
            <div class="group bg-ayoniza-card rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500 flex flex-col border border-stone-200/70">
                <div class="relative overflow-hidden aspect-square bg-stone-100">
                    <img src="https://images.unsplash.com/photo-1635767798638-3e25273a8236?q=80&w=800&auto=format&fit=crop" 
                         alt="Aura Gold Hoops" 
                         class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
                </div>
                <div class="p-6 flex flex-col flex-grow text-center">
                    <p class="text-[10px] tracking-widest uppercase text-stone-400 mb-1">Earrings</p>
                    <h3 class="brand-font text-xl text-stone-900 mb-2 font-medium">Aura Sculpted Gold Hoops</h3>
                    <p class="text-stone-500 text-xs mb-4 font-light line-clamp-2">Lightweight organic wave design crafted with hypoallergenic gold finish.</p>
                    <div class="mt-auto flex items-center justify-between pt-4 border-t border-stone-100">
                        <span class="text-lg font-medium text-stone-800">$110</span>
                        <button onclick="addToCart('Aura Sculpted Gold Hoops', 110)" class="bg-stone-900 hover:bg-ayoniza-gold hover:text-stone-900 text-stone-100 p-3 rounded-full transition-colors duration-300">
                            <i class="fa-solid fa-plus text-xs"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Product 4 -->
            <div class="group bg-ayoniza-card rounded-2xl overflow-hidden shadow-sm hover:shadow-xl transition-all duration-500 flex flex-col border border-stone-200/70">
                <div class="relative overflow-hidden aspect-square bg-stone-100">
                    <img src="https://images.unsplash.com/photo-1608248597262-838239a04f36?q=80&w=800&auto=format&fit=crop" 
                         alt="Velvet Glow Body Butter" 
                         class="w-full h-full object-cover group-hover:scale-110 transition-transform duration-700">
                </div>
                <div class="p-6 flex flex-col flex-grow text-center">
                    <p class="text-[10px] tracking-widest uppercase text-stone-400 mb-1">Personal Care</p>
                    <h3 class="brand-font text-xl text-stone-900 mb-2 font-medium">Velvet Silk Body Soufflé</h3>
                    <p class="text-stone-500 text-xs mb-4 font-light line-clamp-2">Ultra-rich shea butter with subtle notes of white jasmine and gold shimmer.</p>
                    <div class="mt-auto flex items-center justify-between pt-4 border-t border-stone-100">
                        <span class="text-lg font-medium text-stone-800">$64</span>
                        <button onclick="addToCart('Velvet Silk Body Soufflé', 64)" class="bg-stone-900 hover:bg-ayoniza-gold hover:text-stone-900 text-stone-100 p-3 rounded-full transition-colors duration-300">
                            <i class="fa-solid fa-plus text-xs"></i>
                        </button>
                    </div>
                </div>
            </div>

        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="py-24 bg-stone-900 text-amber-50 relative overflow-hidden">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 relative z-10">
            <div class="grid grid-cols-1 lg:grid-cols-2 gap-16 items-center">
                
                <!-- Brand Imagery Showcase -->
                <div class="relative">
                    <div class="aspect-[4/5] rounded-3xl overflow-hidden shadow-2xl">
                        <img src="https://images.unsplash.com/photo-1515562141207-7a88fb7ce338?q=80&w=1000&auto=format&fit=crop" 
                             alt="AYONIZA Brand Craftsmanship" 
                             class="w-full h-full object-cover">
                    </div>
                    <!-- Decorative Badge -->
                    <div class="absolute -bottom-8 -right-8 bg-ayoniza-gold text-stone-950 p-8 rounded-2xl hidden sm:block shadow-xl">
                        <p class="brand-font text-3xl font-bold">100%</p>
                        <p class="text-xs uppercase tracking-widest font-semibold">Pure & Ethical</p>
                    </div>
                </div>

                <!-- Brand Story Content -->
                <div>
                    <span class="text-ayoniza-rose text-xs tracking-[0.3em] uppercase mb-3 block">The AYONIZA Philosophy</span>
                    <h2 class="text-4xl sm:text-5xl font-light brand-font mb-6 leading-tight">
                        Crafted for the Soul that Values <span class="italic font-normal text-ayoniza-gold">Purity & Grace</span>
                    </h2>
                    <p class="text-stone-300 text-sm sm:text-base leading-relaxed font-light mb-6">
                        AYONIZA was born out of a desire to create adornments and self-care rituals that celebrate the authentic aura of modern individuals. We believe that true luxury is subtle, enduring, and deeply conscious.
                    </p>
                    <p class="text-stone-400 text-sm leading-relaxed font-light mb-8">
                        Every piece of jewelry is thoughtfully designed using ethically sourced materials, while our personal care line utilizes pristine natural formulations designed to soothe and elevate your daily life.
                    </p>

                    <!-- Core Value Badges -->
                    <div class="grid grid-cols-3 gap-6 pt-6 border-t border-stone-800 text-center">
                        <div>
                            <i class="fa-solid fa-gem text-ayoniza-gold text-xl mb-2"></i>
                            <p class="text-xs uppercase tracking-wider text-stone-300 font-medium">Fine Quality</p>
                        </div>
                        <div>
                            <i class="fa-solid fa-leaf text-ayoniza-gold text-xl mb-2"></i>
                            <p class="text-xs uppercase tracking-wider text-stone-300 font-medium">Pure Ingredients</p>
                        </div>
                        <div>
                            <i class="fa-solid fa-hand-holding-heart text-ayoniza-gold text-xl mb-2"></i>
                            <p class="text-xs uppercase tracking-wider text-stone-300 font-medium">Ethical Grace</p>
                        </div>
                    </div>
                </div>

            </div>
        </div>
    </section>

    <!-- Testimonials Section -->
    <section id="reviews" class="py-24 max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
        <div class="text-center max-w-2xl mx-auto mb-16">
            <h2 class="text-xs text-ayoniza-accent tracking-[0.3em] uppercase font-semibold mb-2">Patron Words</h2>
            <p class="text-3xl sm:text-5xl font-light brand-font text-stone-900">Stories of Grace</p>
            <div class="w-12 h-0.5 bg-ayoniza-gold mx-auto mt-4"></div>
        </div>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
            <!-- Review 1 -->
            <div class="bg-ayoniza-card p-8 rounded-2xl shadow-sm border border-stone-200/70 flex flex-col justify-between">
                <div>
                    <div class="text-ayoniza-gold text-xs space-x-1 mb-4">
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                    </div>
                    <p class="text-stone-600 text-sm italic font-light mb-6 leading-relaxed">
                        "The Celestial Pearl necklace exceeded my expectations. The subtle sheen and delicate craftsmanship make it my absolute favorite accessory for every evening occasion."
                    </p>
                </div>
                <div>
                    <p class="brand-font text-lg font-semibold text-stone-900">Sophia Thorne</p>
                    <p class="text-[11px] text-stone-400 uppercase tracking-widest">Verified Buyer</p>
                </div>
            </div>

            <!-- Review 2 -->
            <div class="bg-ayoniza-card p-8 rounded-2xl shadow-sm border border-stone-200/70 flex flex-col justify-between">
                <div>
                    <div class="text-ayoniza-gold text-xs space-x-1 mb-4">
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                    </div>
                    <p class="text-stone-600 text-sm italic font-light mb-6 leading-relaxed">
                        "AYONIZA's Grace Botanical Facial Oil has completely transformed my skincare routine. It feels so pure on the skin and leaves an effortless glow without being heavy."
                    </p>
                </div>
                <div>
                    <p class="brand-font text-lg font-semibold text-stone-900">Aria Chen</p>
                    <p class="text-[11px] text-stone-400 uppercase tracking-widest">Verified Buyer</p>
                </div>
            </div>

            <!-- Review 3 -->
            <div class="bg-ayoniza-card p-8 rounded-2xl shadow-sm border border-stone-200/70 flex flex-col justify-between">
                <div>
                    <div class="text-ayoniza-gold text-xs space-x-1 mb-4">
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                        <i class="fa-solid fa-star"></i>
                    </div>
                    <p class="text-stone-600 text-sm italic font-light mb-6 leading-relaxed">
                        "Unboxing AYONIZA feels like receiving a gift from royalty. From the packaging to the jewelry quality, everything breathes pure elegance."
                    </p>
                </div>
                <div>
                    <p class="brand-font text-lg font-semibold text-stone-900">Elena Rostova</p>
                    <p class="text-[11px] text-stone-400 uppercase tracking-widest">Verified Buyer</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Newsletter / VIP Section -->
    <section class="bg-stone-200/50 py-20 border-y border-stone-300/40">
        <div class="max-w-4xl mx-auto px-4 text-center">
            <span class="text-ayoniza-accent text-xs tracking-[0.3em] uppercase mb-2 block">Exclusive Access</span>
            <h2 class="text-3xl sm:text-4xl font-light brand-font text-stone-900 mb-4">Join the AYONIZA Private Circle</h2>
            <p class="text-stone-600 text-xs sm:text-sm font-light max-w-xl mx-auto mb-8">
                Subscribe to receive early access to new collections, secret drops, and bespoke self-care rituals.
            </p>
            
            <form onsubmit="handleNewsletter(event)" class="flex flex-col sm:flex-row max-w-md mx-auto gap-3">
                <input type="email" required placeholder="Enter your email address" 
                       class="px-6 py-3.5 rounded-full text-xs text-stone-900 bg-white border border-stone-300 focus:outline-none focus:border-ayoniza-gold flex-grow">
                <button type="submit" class="bg-stone-900 hover:bg-ayoniza-gold hover:text-stone-900 text-stone-100 text-xs tracking-widest uppercase px-8 py-3.5 rounded-full transition-colors duration-300 font-medium">
                    Subscribe
                </button>
            </form>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact" class="bg-stone-950 text-stone-400 py-16 border-t border-stone-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-1 md:grid-cols-4 gap-10 mb-12">
                
                <!-- Brand Column -->
                <div class="md:col-span-1">
                    <h3 class="text-2xl brand-font text-amber-50 font-semibold tracking-widest mb-2">AYONIZA</h3>
                    <p class="text-[10px] tracking-[0.3em] text-ayoniza-rose uppercase mb-4">Purity With Grace</p>
                    <p class="text-xs text-stone-400 font-light leading-relaxed">
                        Redefining luxury through timeless jewelry and pure botanical personal care creations.
                    </p>
                </div>

                <!-- Quick Links -->
                <div>
                    <h4 class="text-xs uppercase tracking-widest text-amber-100 font-medium mb-4">Collections</h4>
                    <ul class="space-y-2 text-xs font-light">
                        <li><a href="#collection" class="hover:text-ayoniza-gold transition-colors">Fine Jewelry</a></li>
                        <li><a href="#collection" class="hover:text-ayoniza-gold transition-colors">Earrings & Rings</a></li>
                        <li><a href="#collection" class="hover:text-ayoniza-gold transition-colors">Botanical Oils</a></li>
                        <li><a href="#collection" class="hover:text-ayoniza-gold transition-colors">Personal Care Soufflé</a></li>
                    </ul>
                </div>

                <!-- Concierge -->
                <div>
                    <h4 class="text-xs uppercase tracking-widest text-amber-100 font-medium mb-4">Concierge</h4>
                    <ul class="space-y-2 text-xs font-light">
                        <li><a href="#" class="hover:text-ayoniza-gold transition-colors">Shipping & Returns</a></li>
                        <li><a href="#" class="hover:text-ayoniza-gold transition-colors">Care Guide</a></li>
                        <li><a href="#" class="hover:text-ayoniza-gold transition-colors">Bespoke Orders</a></li>
                        <li><a href="#" class="hover:text-ayoniza-gold transition-colors">Contact Support</a></li>
                    </ul>
                </div>

                <!-- Connect -->
                <div>
                    <h4 class="text-xs uppercase tracking-widest text-amber-100 font-medium mb-4">Follow Us</h4>
                    <div class="flex space-x-4 mb-4">
                        <a href="#" class="w-9 h-9 rounded-full bg-stone-900 border border-stone-800 flex items-center justify-center text-stone-300 hover:text-ayoniza-gold hover:border-ayoniza-gold transition-colors">
                            <i class="fa-brands fa-instagram text-xs"></i>
                        </a>
                        <a href="#" class="w-9 h-9 rounded-full bg-stone-900 border border-stone-800 flex items-center justify-center text-stone-300 hover:text-ayoniza-gold hover:border-ayoniza-gold transition-colors">
                            <i class="fa-brands fa-pinterest-p text-xs"></i>
                        </a>
                        <a href="#" class="w-9 h-9 rounded-full bg-stone-900 border border-stone-800 flex items-center justify-center text-stone-300 hover:text-ayoniza-gold hover:border-ayoniza-gold transition-colors">
                            <i class="fa-brands fa-facebook-f text-xs"></i>
                        </a>
                    </div>
                    <p class="text-xs text-stone-500">concierge@ayoniza.com</p>
                </div>

            </div>

            <div class="pt-8 border-t border-stone-900 flex flex-col sm:flex-row justify-between items-center text-xs text-stone-600 font-light gap-4">
                <p>&copy; 2026 AYONIZA. All rights reserved.</p>
                <div class="flex space-x-6">
                    <a href="#" class="hover:text-stone-400">Privacy Policy</a>
                    <a href="#" class="hover:text-stone-400">Terms of Service</a>
                </div>
            </div>
        </div>
    </footer>

    <!-- Sliding Cart Drawer Overlay -->
    <div id="cart-drawer" class="fixed inset-0 z-50 overflow-hidden hidden">
        <div class="absolute inset-0 bg-stone-950/60 backdrop-blur-sm transition-opacity" onclick="toggleCartDrawer()"></div>
        
        <div class="fixed inset-y-0 right-0 max-w-full flex pl-10">
            <div class="w-screen max-w-md bg-ayoniza-bg shadow-2xl flex flex-col">
                <!-- Cart Header -->
                <div class="p-6 border-b border-stone-200 flex items-center justify-between">
                    <h3 class="brand-font text-2xl text-stone-900 font-semibold">Your Selection</h3>
                    <button onclick="toggleCartDrawer()" class="text-stone-400 hover:text-stone-900 p-2">
                        <i class="fa-solid fa-xmark text-lg"></i>
                    </button>
                </div>

                <!-- Cart Body -->
                <div id="cart-items" class="p-6 overflow-y-auto flex-grow space-y-4">
                    <p id="empty-cart-msg" class="text-center text-stone-400 text-xs py-10 font-light">Your shopping bag is currently empty.</p>
                </div>

                <!-- Cart Footer -->
                <div class="p-6 border-t border-stone-200 bg-white">
                    <div class="flex justify-between text-sm font-medium text-stone-900 mb-4">
                        <span>Subtotal</span>
                        <span id="cart-subtotal">$0</span>
                    </div>
                    <button onclick="checkout()" class="w-full btn-gold text-amber-50 py-3.5 text-xs tracking-widest uppercase font-medium rounded-full text-center">
                        Proceed to Checkout
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- Notification Toast Container -->
    <div id="toast-container" class="fixed bottom-6 right-6 z-50 space-y-2 pointer-events-none"></div>

    <!-- Dynamic Interactive Scripts -->
    <script>
        let cart = [];

        // Toggle Mobile Menu
        function toggleMobileMenu() {
            const menu = document.getElementById('mobile-menu');
            menu.classList.toggle('hidden');
        }

        document.getElementById('mobile-menu-btn').addEventListener('click', toggleMobileMenu);

        // Toggle Cart Drawer
        function toggleCartDrawer() {
            const drawer = document.getElementById('cart-drawer');
            drawer.classList.toggle('hidden');
        }

        // Add Item To Cart
        function addToCart(title, price) {
            const existingIndex = cart.findIndex(item => item.title === title);
            if (existingIndex > -1) {
                cart[existingIndex].quantity += 1;
            } else {
                cart.push({ title, price, quantity: 1 });
            }

            updateCartUI();
            showToast(`Added "${title}" to your cart.`);
        }

        // Update Cart UI Component
        function updateCartUI() {
            const totalCount = cart.reduce((sum, item) => sum + item.quantity, 0);
            document.getElementById('cart-count').innerText = totalCount;
            document.getElementById('cart-count-mobile').innerText = totalCount;

            const cartContainer = document.getElementById('cart-items');
            const emptyMsg = document.getElementById('empty-cart-msg');

            if (cart.length === 0) {
                cartContainer.innerHTML = '<p id="empty-cart-msg" class="text-center text-stone-400 text-xs py-10 font-light">Your shopping bag is currently empty.</p>';
                document.getElementById('cart-subtotal').innerText = '$0';
                return;
            }

            let html = '';
            let subtotal = 0;

            cart.forEach((item, index) => {
                subtotal += item.price * item.quantity;
                html += `
                    <div class="flex items-center justify-between p-4 bg-white rounded-xl border border-stone-200">
                        <div>
                            <h4 class="brand-font text-base text-stone-900 font-medium">${item.title}</h4>
                            <p class="text-xs text-stone-500 font-light">$${item.price} x ${item.quantity}</p>
                        </div>
                        <div class="flex items-center space-x-3">
                            <button onclick="removeFromCart(${index})" class="text-stone-400 hover:text-red-500 text-xs p-1">
                                <i class="fa-solid fa-trash"></i>
                            </button>
                        </div>
                    </div>
                `;
            });

            cartContainer.innerHTML = html;
            document.getElementById('cart-subtotal').innerText = `$${subtotal}`;
        }

        // Remove Item From Cart
        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCartUI();
        }

        // Toast Notification Function
        function showToast(message) {
            const container = document.getElementById('toast-container');
            const toast = document.createElement('div');
            toast.className = 'toast-slide bg-stone-900 text-amber-100 text-xs px-5 py-3 rounded-xl shadow-2xl border border-ayoniza-gold flex items-center space-x-2';
            toast.innerHTML = `<i class="fa-solid fa-check text-ayoniza-gold"></i><span>${message}</span>`;
            
            container.appendChild(toast);
            setTimeout(() => {
                toast.remove();
            }, 3000);
        }

        // Newsletter Form Handler
        function handleNewsletter(event) {
            event.preventDefault();
            showToast('Thank you for joining the AYONIZA Private Circle.');
            event.target.reset();
        }

        // Checkout Button Action
        function checkout() {
            if (cart.length === 0) {
                showToast('Your cart is empty.');
                return;
            }
            showToast('Redirecting to secure checkout...');
        }
    </script>
</body>
</html>
