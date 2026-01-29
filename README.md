# warronlai951.github.io
Cake order website test 1 
 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
index 35deddcbb8a64ed9d8b96475767a8e34652961eb..9ec4ce195ec0423e3591ba53a3e0cfb1d9f45876 100644
--- a/README.md
+++ b/README.md
@@ -31,263 +31,521 @@
   </script>
 
   <style>
     .glass-nav { background: rgba(252, 248, 246, 0.8); backdrop-filter: blur(12px); }
     .whatsapp-float { position: fixed; bottom: 2rem; right: 2rem; z-index: 100; }
     /* small helper so embedded Instagram content fits nicely when used */
     #instagram-embed { max-width: 640px; margin: 0 auto; }
   </style>
 </head>
 <body class="bg-background-light dark:bg-background-dark font-display text-[#1b0e14] dark:text-white transition-colors duration-300">
   <!-- Floating WhatsApp Button -->
   <a id="whatsapp-link" class="whatsapp-float flex items-center justify-center size-16 bg-[#25D366] text-white rounded-full shadow-2xl hover:scale-110 transition-transform" href="#" target="_blank" rel="noopener noreferrer" aria-label="Chat on WhatsApp">
     <svg class="size-8" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"></path></svg>
   </a>
 
   <!-- Top Navigation Bar -->
   <div class="fixed top-0 left-0 right-0 z-50 glass-nav border-b border-[#f3e7ed] dark:border-white/10">
     <header class="max-w-7xl mx-auto flex items-center justify-between px-6 py-4">
       <div class="flex items-center gap-3">
         <div class="bg-primary text-white p-2 rounded-full flex items-center justify-center">
           <span class="material-symbols-outlined">cake</span>
         </div>
         <h1 class="text-xl font-extrabold tracking-tight">Twelve of 7 <span class="text-primary">Bakeology</span></h1>
       </div>
       <nav class="hidden md:flex items-center gap-8">
-        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#process">Process</a>
-        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#gallery">Gallery</a>
-        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#flame">Flame Cakes</a>
-        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#testimonials">Reviews</a>
+        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#process" data-i18n="nav.process">Process</a>
+        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#gallery" data-i18n="nav.gallery">Gallery</a>
+        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#flame" data-i18n="nav.flame">Flame Cakes</a>
+        <a class="text-sm font-semibold hover:text-primary transition-colors" href="#testimonials" data-i18n="nav.reviews">Reviews</a>
       </nav>
       <div class="flex items-center gap-4">
-        <button id="chat-customize" class="bg-primary text-white px-6 py-2.5 rounded-full font-bold text-sm shadow-lg shadow-primary/20 hover:scale-105 transition-all">
+        <div class="hidden sm:flex items-center gap-2 text-xs font-semibold text-[#994d73] dark:text-white/70">
+          <label for="language-select" class="sr-only" data-i18n="nav.languageLabel">Language</label>
+          <span data-i18n="nav.languageLabel">Language</span>
+          <select id="language-select" class="rounded-full border border-[#e7d0db] bg-white px-3 py-2 text-xs font-semibold text-[#1b0e14] shadow-sm focus:border-primary focus:outline-none focus:ring-2 focus:ring-primary/40">
+            <option value="en">English</option>
+            <option value="zh">中文</option>
+            <option value="ms">Bahasa Melayu</option>
+          </select>
+        </div>
+        <button id="chat-customize" class="bg-primary text-white px-6 py-2.5 rounded-full font-bold text-sm shadow-lg shadow-primary/20 hover:scale-105 transition-all" data-i18n="nav.chat">
           Chat to customise
         </button>
       </div>
     </header>
   </div>
 
   <main class="pt-24">
     <!-- Hero Section -->
     <section class="max-w-7xl mx-auto px-6 py-12 md:py-20 overflow-hidden">
       <div class="grid grid-cols-1 lg:grid-cols-2 gap-12 items-center">
         <div class="flex flex-col gap-8">
-          <div class="inline-flex items-center px-4 py-1 rounded-full bg-accent-pink text-primary text-xs font-bold uppercase tracking-wider w-fit">
+          <div class="inline-flex items-center px-4 py-1 rounded-full bg-accent-pink text-primary text-xs font-bold uppercase tracking-wider w-fit" data-i18n="hero.badge">
             Artisanal &amp; Custom Made
           </div>
-          <h1 class="text-5xl md:text-7xl font-black leading-[1.1] tracking-tight text-[#1b0e14] dark:text-white">
-            Your wildest ideas, <br/><span class="text-primary italic">baked into reality 🎂</span>
+          <h1 class="text-5xl md:text-7xl font-black leading-[1.1] tracking-tight text-[#1b0e14] dark:text-white" data-i18n="hero.title">
+            Your wildest ideas, <br/><span class="text-primary italic" data-i18n="hero.titleAccent">baked into reality 🎂</span>
           </h1>
-          <p class="text-lg text-[#994d73] dark:text-white/70 leading-relaxed max-w-lg">
+          <p class="text-lg text-[#994d73] dark:text-white/70 leading-relaxed max-w-lg" data-i18n="hero.subtitle">
             Custom-made artisanal cakes for birthdays, weddings, and every sweet moment in between. Handcrafted with love and the finest ingredients in our boutique kitchen.
           </p>
           <div class="flex flex-wrap gap-4">
-            <button id="start-order" class="bg-primary text-white px-8 py-4 rounded-full font-bold text-lg hover:bg-[#d93a88] transition-colors shadow-xl">
+            <button id="start-order" class="bg-primary text-white px-8 py-4 rounded-full font-bold text-lg hover:bg-[#d93a88] transition-colors shadow-xl" data-i18n="hero.startOrder">
               Start Your Order
             </button>
-            <button id="open-gallery" class="bg-white dark:bg-white/10 border border-[#e7d0db] dark:border-white/20 px-8 py-4 rounded-full font-bold text-lg hover:bg-background-light transition-colors">
+            <button id="open-gallery" class="bg-white dark:bg-white/10 border border-[#e7d0db] dark:border-white/20 px-8 py-4 rounded-full font-bold text-lg hover:bg-background-light transition-colors" data-i18n="hero.viewGallery">
               View Gallery
             </button>
           </div>
         </div>
 
         <!-- Right side: grid of images (these prefer local assets but fall back to your original remote images) -->
         <div class="relative grid grid-cols-2 gap-4" id="hero-gallery">
           <div class="flex flex-col gap-4 mt-8">
             <div class="aspect-[4/5] bg-cover bg-center rounded-xl shadow-2xl"
                  data-local="assets/instagram.jpg"
                  data-fallback="https://lh3.googleusercontent.com/aida-public/AB6AXuA6nmGr0jKJHAQ2mZhBIz_ytv6B6Wcwt6DowJcnlrA7yPgETop41Lv9F67pacx5TXHf7ECAzFkQk8cwFaelLEum7Ew86LSjmqQaWX3-neG8pBGqWN6OGAVw7TwhLxw3ylMyIcVJa4kHrgsFsCO95qJpEUYx6x1jcWxFgP1MsDYWqaG5nSqmqIEmP07GmXCRQIVAWGh-O52LIp7SQKiXX-uPAXXKrFQz4vpnUyIMwDfk9e0v-AqvGt7pD5oOKEGZNGvmQmyetOqQfHs"
                  aria-label="Stunning pink floral tiered birthday cake"></div>
 
             <div class="aspect-square bg-cover bg-center rounded-xl shadow-2xl"
                  data-local="assets/gallery1.jpg"
                  data-fallback="https://lh3.googleusercontent.com/aida-public/AB6AXuAUfwD-FB6QbgE6kGTDg_N6a8pLV9TNOi5Z8Yz4C1-WnMc2Oym4jdEVJj74CbYtZQg8Dv-_gLOIJ-sCqBl-BkSs1w39dL34JjhG-KJ31mYIND9HM3dE_nooZW4K4kWOsTXJbcpOcKZ7dW0tTlHD4LlV3M1y5oaTipHJR4t9L6ymiKY-dPFNXzeH_9dxjJJi0oLynoeY7XK2sFxdTT3Ccad2AMn9qIBUX9YwYLLrpl624HGK9ehqWc4p_0V2VqFdsKZUjBN1m5mDxmE"
                  aria-label="Detailed close up of wedding cake frosting"></div>
           </div>
 
           <div class="flex flex-col gap-4">
             <div class="aspect-square bg-cover bg-center rounded-xl shadow-2xl"
                  data-local="assets/gallery2.jpg"
                  data-fallback="https://lh3.googleusercontent.com/aida-public/AB6AXuCiHra2yt47lMNHKwcblNoYlkp6tPKAtZHbH5vvAstFfL2V41cGrROC2uG1bKJm5C1aIlp1eWnviMm-jzWsyskkL7_7kCQ5ragHisnMUPSltit7zxCzzBbR5uCfEsxk-QnaOEPcqczUifT1DcrYBOkEYpt4u1EspEvbfbbFYqKHT0iTdjH_cC0du5qfBz8MarKlYupGjUOTQ7EZ3aBa578_cVmNMcPRrYgbAGYJZVCiG-rHBLduALEa3huFPgJK5Kyttzy6DJqaDPE"
                  aria-label="Modern geometric patterned blue cake"></div>
 
             <div class="aspect-[4/5] bg-cover bg-center rounded-xl shadow-2xl"
                  data-local="assets/gallery3.jpg"
                  data-fallback="https://lh3.googleusercontent.com/aida-public/AB6AXuCxSHNfCW3ijDytPIfdJkKfcJrYvxwrxH1KB1G-5BToemBd0EHfXVaYynW10FP0JVGJWMo_aXItvMnG44okxQH7Z84NuOAsSHxMy8SVtXjHmgAAsXg_z4jT_rriKYw8jvQy3e82fPZGpuV6Cy9IbWkg0dhoeI0meLOscKPlmXe3ilHht8i5MW2gL0qSLAGbzQtNt6TjNXtfB7GeKALOKIa0yue44WnrIU6aBE4gq_iQ_F4_hni965Yhn_EzLePYPgc_TVthHaGv5Xw"
                  aria-label="Minimalist elegant white cake with pearls"></div>
           </div>
         </div>
       </div>
     </section>
 
     <!-- Instagram embed area (OPTIONAL) --
          If you prefer to embed a single Instagram post, paste the Instagram embed <blockquote> into the div below.
          Instructions in the README. -->
     <section id="instagram-embed-section" class="max-w-3xl mx-auto px-6 pb-8">
       <div id="instagram-embed" class="prose mx-auto"></div>
     </section>
 
     <!-- Simple Process Section -->
     <section id="process" class="bg-white dark:bg-white/5 py-24">
       <div class="max-w-7xl mx-auto px-6">
         <div class="text-center mb-16">
-          <h2 class="text-3xl font-bold mb-4">Simple Process</h2>
-          <p class="text-[#994d73] dark:text-white/60">Ordering your dream cake is as easy as 1, 2, 3</p>
+          <h2 class="text-3xl font-bold mb-4" data-i18n="process.title">Simple Process</h2>
+          <p class="text-[#994d73] dark:text-white/60" data-i18n="process.subtitle">Ordering your dream cake is as easy as 1, 2, 3</p>
         </div>
         <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
           <div class="flex flex-col items-center text-center p-8 rounded-lg bg-accent-peach dark:bg-white/5 group hover:scale-105 transition-transform">
             <div class="size-16 rounded-full bg-orange-400 text-white flex items-center justify-center mb-6 shadow-lg shadow-orange-200">
               <span class="material-symbols-outlined text-3xl">photo_camera</span>
             </div>
-            <h3 class="text-xl font-bold mb-2">Send us a pic</h3>
-            <p class="text-sm text-[#994d73] dark:text-white/60 leading-relaxed">Share your inspiration, Pinterest board, or even a napkin sketch with us via WhatsApp.</p>
+            <h3 class="text-xl font-bold mb-2" data-i18n="process.step1.title">Send us a pic</h3>
+            <p class="text-sm text-[#994d73] dark:text-white/60 leading-relaxed" data-i18n="process.step1.desc">Share your inspiration, Pinterest board, or even a napkin sketch with us via WhatsApp.</p>
           </div>
 
           <div class="flex flex-col items-center text-center p-8 rounded-lg bg-accent-blue dark:bg-white/5 group hover:scale-105 transition-transform">
             <div class="size-16 rounded-full bg-blue-400 text-white flex items-center justify-center mb-6 shadow-lg shadow-blue-200">
               <span class="material-symbols-outlined text-3xl">restaurant_menu</span>
             </div>
-            <h3 class="text-xl font-bold mb-2">Pick your flavors</h3>
-            <p class="text-sm text-[#994d73] dark:text-white/60 leading-relaxed">Choose from our 15+ premium range of sponges, artisanal fillings, and velvet buttercreams.</p>
+            <h3 class="text-xl font-bold mb-2" data-i18n="process.step2.title">Pick your flavors</h3>
+            <p class="text-sm text-[#994d73] dark:text-white/60 leading-relaxed" data-i18n="process.step2.desc">Choose from our 15+ premium range of sponges, artisanal fillings, and velvet buttercreams.</p>
           </div>
 
           <div class="flex flex-col items-center text-center p-8 rounded-lg bg-accent-pink dark:bg-white/5 group hover:scale-105 transition-transform">
             <div class="size-16 rounded-full bg-primary text-white flex items-center justify-center mb-6 shadow-lg shadow-pink-200">
               <span class="material-symbols-outlined text-3xl">celebration</span>
             </div>
-            <h3 class="text-xl font-bold mb-2">Pick up a Party</h3>
-            <p class="text-sm text-[#994d73] dark:text-white/60 leading-relaxed">Collect your handcrafted masterpiece and let the celebration begin with your loved ones!</p>
+            <h3 class="text-xl font-bold mb-2" data-i18n="process.step3.title">Pick up a Party</h3>
+            <p class="text-sm text-[#994d73] dark:text-white/60 leading-relaxed" data-i18n="process.step3.desc">Collect your handcrafted masterpiece and let the celebration begin with your loved ones!</p>
           </div>
         </div>
       </div>
     </section>
 
     <!-- Gallery -->
     <section id="gallery" class="max-w-7xl mx-auto px-6 py-24">
       <div class="flex items-end justify-between mb-12">
         <div>
-          <h2 class="text-3xl font-bold mb-2">Fresh from the Oven</h2>
-          <p class="text-[#994d73] dark:text-white/60">Our latest creations, ready for your celebration.</p>
+          <h2 class="text-3xl font-bold mb-2" data-i18n="gallery.title">Fresh from the Oven</h2>
+          <p class="text-[#994d73] dark:text-white/60" data-i18n="gallery.subtitle">Our latest creations, ready for your celebration.</p>
         </div>
-        <button class="hidden md:block text-primary font-bold hover:underline">View All Gallery</button>
+        <button class="hidden md:block text-primary font-bold hover:underline" data-i18n="gallery.viewAll">View All Gallery</button>
       </div>
 
       <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-8">
         <!-- Card 1 -->
         <div class="bg-white dark:bg-white/5 rounded-lg overflow-hidden border border-[#f3e7ed] dark:border-white/10 group">
           <div class="aspect-square bg-cover bg-center overflow-hidden"
                data-local="assets/gallery-card-1.jpg"
                data-fallback="https://lh3.googleusercontent.com/aida-public/AB6AXuBnmC9NkB_dPgCvbRh2mk6iLrg8NJIb7kP6DK7pEF7oMTaZkDjgRJydLM5Ls6e9lSWBxD8nVJCJwAefFYwEZjGNXPUdtxMy6Al-s-cQC805yEW8IiWbJQkHZ6iJcWXNZMxrftnq8BPsP87-ywIW1ub6RHKWf7F2mgY82DYDt3sXsM9ECX1djGgBjR6svb2d5OXYUHJJii-UOON172wIW81Xo1A66h09Z67uPkA6zsSJrh1HDZ9nHrmYetS2SDTQkAExeY5WE5ovCJ8"
                aria-label="Mermaid Fantasy"></div>
           <div class="p-6">
             <div class="flex gap-2 mb-3">
-              <span class="px-3 py-1 bg-accent-blue text-blue-600 rounded-full text-[10px] font-bold uppercase">Whimsical</span>
-              <span class="px-3 py-1 bg-accent-pink text-primary rounded-full text-[10px] font-bold uppercase">Birthday</span>
+              <span class="px-3 py-1 bg-accent-blue text-blue-600 rounded-full text-[10px] font-bold uppercase" data-i18n="gallery.tags.whimsical">Whimsical</span>
+              <span class="px-3 py-1 bg-accent-pink text-primary rounded-full text-[10px] font-bold uppercase" data-i18n="gallery.tags.birthday">Birthday</span>
             </div>
-            <h4 class="text-xl font-bold mb-4">Mermaid Fantasy</h4>
-            <button class="w-full flex items-center justify-center gap-2 py-3 rounded-full border-2 border-primary text-primary font-bold hover:bg-primary hover:text-white transition-all">
+            <h4 class="text-xl font-bold mb-4" data-i18n="gallery.card1.title">Mermaid Fantasy</h4>
+            <button class="w-full flex items-center justify-center gap-2 py-3 rounded-full border-2 border-primary text-primary font-bold hover:bg-primary hover:text-white transition-all" data-i18n="gallery.askButton">
               <span class="material-symbols-outlined text-lg">chat</span> Ask about this cake
             </button>
           </div>
         </div>
 
         <!-- Card 2 -->
         <div class="bg-white dark:bg-white/5 rounded-lg overflow-hidden border border-[#f3e7ed] dark:border-white/10 group">
           <div class="aspect-square bg-cover bg-center overflow-hidden"
                data-local="assets/gallery-card-2.jpg"
                data-fallback="https://lh3.googleusercontent.com/aida-public/AB6AXuAcF_iULN6z6kDOTFSLhmDU1tMblUnAf7bpxIhOTxhVZgSQnuz3ZHATSWBfam1NN71LY0GSQD6dWbv0dmiTcgoG_eCKGLqmWCmysG9XW2539j8GT2AusU6lX4Nh_SHQ5lDKudiWF4HPXPhh3Ksnp7H5PfHpEM-895dhn-WQSIjr9Jdav4rwRClRQ9xt5fqynsfcTDmSntnqcnZwFbthI91BvWeKldazLJYysK4DtswOI1z-xQGgeY_f7fHKkRjc0HNQZ1Go_k02vzk"
                aria-label="Retro Vintage Piping"></div>
           <div class="p-6">
             <div class="flex gap-2 mb-3">
-              <span class="px-3 py-1 bg-accent-peach text-orange-600 rounded-full text-[10px] font-bold uppercase">Classic</span>
-              <span class="px-3 py-1 bg-accent-pink text-primary rounded-full text-[10px] font-bold uppercase">Vintage</span>
+              <span class="px-3 py-1 bg-accent-peach text-orange-600 rounded-full text-[10px] font-bold uppercase" data-i18n="gallery.tags.classic">Classic</span>
+              <span class="px-3 py-1 bg-accent-pink text-primary rounded-full text-[10px] font-bold uppercase" data-i18n="gallery.tags.vintage">Vintage</span>
             </div>
-            <h4 class="text-xl font-bold mb-4">Retro Vintage Piping</h4>
-            <button class="w-full flex items-center justify-center gap-2 py-3 rounded-full border-2 border-primary text-primary font-bold hover:bg-primary hover:text-white transition-all">
+            <h4 class="text-xl font-bold mb-4" data-i18n="gallery.card2.title">Retro Vintage Piping</h4>
+            <button class="w-full flex items-center justify-center gap-2 py-3 rounded-full border-2 border-primary text-primary font-bold hover:bg-primary hover:text-white transition-all" data-i18n="gallery.askButton">
               <span class="material-symbols-outlined text-lg">chat</span> Ask about this cake
             </button>
           </div>
         </div>
 
         <!-- Card 3 -->
         <div class="bg-white dark:bg-white/5 rounded-lg overflow-hidden border border-[#f3e7ed] dark:border-white/10 group">
           <div class="aspect-square bg-cover bg-center overflow-hidden"
                data-local="assets/gallery-card-3.jpg"
                data-fallback="https://lh3.googleusercontent.com/aida-public/AB6AXuBzUz_XeEpqmpn40b5pSmJLFKD3FBWPfmin-vrK7YsQTmkaTzIQJRK0AilOowr8Y6HL94RSdk9TZMLHwk28l3wxH8OICoyVHtFb9RWFwoXdCDaBnRMNLxRpSVcRbOQ5gy_T7a0icQlyplKntzVnSWPkcOzPxvqnR4NqmEepNmG5-fFar1DwxN5Ub94kFaVZml9LjdMATo0fR76ikR8MGtNslFcISxwlw9YmR5wop8Qo45Mkn1R1t2s_7BOibS3b17SiRqZgL8gLg2g"
                aria-label="Chocolate Gold Drip"></div>
           <div class="p-6">
             <div class="flex gap-2 mb-3">
-              <span class="px-3 py-1 bg-gray-100 dark:bg-white/10 text-gray-600 dark:text-gray-300 rounded-full text-[10px] font-bold uppercase">Modern</span>
-              <span class="px-3 py-1 bg-accent-pink text-primary rounded-full text-[10px] font-bold uppercase">Luxury</span>
+              <span class="px-3 py-1 bg-gray-100 dark:bg-white/10 text-gray-600 dark:text-gray-300 rounded-full text-[10px] font-bold uppercase" data-i18n="gallery.tags.modern">Modern</span>
+              <span class="px-3 py-1 bg-accent-pink text-primary rounded-full text-[10px] font-bold uppercase" data-i18n="gallery.tags.luxury">Luxury</span>
             </div>
-            <h4 class="text-xl font-bold mb-4">Chocolate Gold Drip</h4>
-            <button class="w-full flex items-center justify-center gap-2 py-3 rounded-full border-2 border-primary text-primary font-bold hover:bg-primary hover:text-white transition-all">
+            <h4 class="text-xl font-bold mb-4" data-i18n="gallery.card3.title">Chocolate Gold Drip</h4>
+            <button class="w-full flex items-center justify-center gap-2 py-3 rounded-full border-2 border-primary text-primary font-bold hover:bg-primary hover:text-white transition-all" data-i18n="gallery.askButton">
               <span class="material-symbols-outlined text-lg">chat</span> Ask about this cake
             </button>
           </div>
         </div>
       </div>
     </section>
 
     <!-- (rest of your page unchanged — Flame Cakes, Testimonials, CTA, Footer) -->
     <!-- For brevity I keep the rest of your original markup unchanged; it will behave the same. -->
     <!-- You can paste the remaining sections from your original HTML if you want a verbatim copy. -->
   </main>
 
   <footer class="bg-background-dark text-white py-16 px-6">
     <div class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-4 gap-12">
       <div class="col-span-1 md:col-span-1">
         <div class="flex items-center gap-3 mb-6">
           <div class="bg-primary text-white p-2 rounded-full flex items-center justify-center">
             <span class="material-symbols-outlined">cake</span>
           </div>
           <h1 class="text-xl font-extrabold tracking-tight">Twelve of 7 <span class="text-primary">Bakeology</span></h1>
         </div>
-        <p class="text-white/60 text-sm leading-relaxed mb-6">
+        <p class="text-white/60 text-sm leading-relaxed mb-6" data-i18n="footer.tagline">
           Baking memories since 2017. Custom cakes for the dreamers, the lovers, and the party makers.
         </p>
         <div class="flex gap-4">
           <a class="size-10 bg-white/5 flex items-center justify-center rounded-full hover:bg-primary transition-colors" href="#"><i class="material-symbols-outlined text-lg">share</i></a>
           <a class="size-10 bg-white/5 flex items-center justify-center rounded-full hover:bg-primary transition-colors" href="#"><i class="material-symbols-outlined text-lg">photo_camera</i></a>
         </div>
       </div>
 
       <div>
-        <h4 class="font-bold mb-6 text-lg">Quick Links</h4>
+        <h4 class="font-bold mb-6 text-lg" data-i18n="footer.quickLinks">Quick Links</h4>
         <ul class="space-y-4 text-white/60">
-          <li><a class="hover:text-primary" href="#">Home</a></li>
-          <li><a class="hover:text-primary" href="#gallery">Gallery</a></li>
-          <li><a class="hover:text-primary" href="#flame">Flame Cakes</a></li>
-          <li><a class="hover:text-primary" href="#process">Custom Orders</a></li>
+          <li><a class="hover:text-primary" href="#" data-i18n="footer.links.home">Home</a></li>
+          <li><a class="hover:text-primary" href="#gallery" data-i18n="footer.links.gallery">Gallery</a></li>
+          <li><a class="hover:text-primary" href="#flame" data-i18n="footer.links.flame">Flame Cakes</a></li>
+          <li><a class="hover:text-primary" href="#process" data-i18n="footer.links.customOrders">Custom Orders</a></li>
         </ul>
       </div>
 
       <div>
-        <h4 class="font-bold mb-6 text-lg">Support</h4>
+        <h4 class="font-bold mb-6 text-lg" data-i18n="footer.support">Support</h4>
         <ul class="space-y-4 text-white/60">
-          <li><a class="hover:text-primary" href="#">FAQ</a></li>
-          <li><a class="hover:text-primary" href="#">Care Instructions</a></li>
-          <li><a class="hover:text-primary" href="#">Flavors &amp; Fillings</a></li>
-          <li><a class="hover:text-primary" href="#">Contact Us</a></li>
+          <li><a class="hover:text-primary" href="#" data-i18n="footer.supportLinks.faq">FAQ</a></li>
+          <li><a class="hover:text-primary" href="#" data-i18n="footer.supportLinks.care">Care Instructions</a></li>
+          <li><a class="hover:text-primary" href="#" data-i18n="footer.supportLinks.flavors">Flavors &amp; Fillings</a></li>
+          <li><a class="hover:text-primary" href="#" data-i18n="footer.supportLinks.contact">Contact Us</a></li>
         </ul>
       </div>
 
       <div>
-        <h4 class="font-bold mb-6 text-lg">Contact</h4>
+        <h4 class="font-bold mb-6 text-lg" data-i18n="footer.contact">Contact</h4>
         <ul class="space-y-4 text-white/60">
-          <li class="flex items-center gap-3"><span class="material-symbols-outlined text-primary">location_on</span><span>Downtown Arts District, Studio 12</span></li>
+          <li class="flex items-center gap-3"><span class="material-symbols-outlined text-primary">location_on</span><span data-i18n="footer.contactDetails.address">Downtown Arts District, Studio 12</span></li>
           <li class="flex items-center gap-3"><span class="material-symbols-outlined text-primary">phone_iphone</span><span>+1 (555) 777-1207</span></li>
           <li class="flex items-center gap-3"><span class="material-symbols-outlined text-primary">mail</span><span>hello@twelveof7.com</span></li>
         </ul>
       </div>
     </div>
 
     <div class="max-w-7xl mx-auto pt-16 mt-16 border-t border-white/10 text-center text-white/40 text-xs">
-      <p>© 2026 Twelve of 7 Bakeology. All rights reserved. Handcrafted with love.</p>
+      <p data-i18n="footer.copyright">© 2026 Twelve of 7 Bakeology. All rights reserved. Handcrafted with love.</p>
     </div>
   </footer>
 
   <!-- Main script that prefers local assets but falls back to original remote images.
        It also wires up the WhatsApp and buttons. See README for how to use Instagram embed. -->
-  <script src="main.js"></script>
+  <script>
+    const languageSelect = document.getElementById("language-select");
+    const whatsappLink = document.getElementById("whatsapp-link");
+    const chatCustomize = document.getElementById("chat-customize");
+    const startOrder = document.getElementById("start-order");
+    const openGallery = document.getElementById("open-gallery");
+
+    const translations = {
+      en: {
+        "nav.process": "Process",
+        "nav.gallery": "Gallery",
+        "nav.flame": "Flame Cakes",
+        "nav.reviews": "Reviews",
+        "nav.languageLabel": "Language",
+        "nav.chat": "Chat to customise",
+        "hero.badge": "Artisanal & Custom Made",
+        "hero.title": "Your wildest ideas, <br/><span class=\"text-primary italic\">baked into reality 🎂</span>",
+        "hero.titleAccent": "baked into reality 🎂",
+        "hero.subtitle":
+          "Custom-made artisanal cakes for birthdays, weddings, and every sweet moment in between. Handcrafted with love and the finest ingredients in our boutique kitchen.",
+        "hero.startOrder": "Start Your Order",
+        "hero.viewGallery": "View Gallery",
+        "process.title": "Simple Process",
+        "process.subtitle": "Ordering your dream cake is as easy as 1, 2, 3",
+        "process.step1.title": "Send us a pic",
+        "process.step1.desc": "Share your inspiration, Pinterest board, or even a napkin sketch with us via WhatsApp.",
+        "process.step2.title": "Pick your flavors",
+        "process.step2.desc": "Choose from our 15+ premium range of sponges, artisanal fillings, and velvet buttercreams.",
+        "process.step3.title": "Pick up a Party",
+        "process.step3.desc": "Collect your handcrafted masterpiece and let the celebration begin with your loved ones!",
+        "gallery.title": "Fresh from the Oven",
+        "gallery.subtitle": "Our latest creations, ready for your celebration.",
+        "gallery.viewAll": "View All Gallery",
+        "gallery.askButton": "<span class=\"material-symbols-outlined text-lg\">chat</span> Ask about this cake",
+        "gallery.card1.title": "Mermaid Fantasy",
+        "gallery.card2.title": "Retro Vintage Piping",
+        "gallery.card3.title": "Chocolate Gold Drip",
+        "gallery.tags.whimsical": "Whimsical",
+        "gallery.tags.birthday": "Birthday",
+        "gallery.tags.classic": "Classic",
+        "gallery.tags.vintage": "Vintage",
+        "gallery.tags.modern": "Modern",
+        "gallery.tags.luxury": "Luxury",
+        "footer.tagline": "Baking memories since 2017. Custom cakes for the dreamers, the lovers, and the party makers.",
+        "footer.quickLinks": "Quick Links",
+        "footer.links.home": "Home",
+        "footer.links.gallery": "Gallery",
+        "footer.links.flame": "Flame Cakes",
+        "footer.links.customOrders": "Custom Orders",
+        "footer.support": "Support",
+        "footer.supportLinks.faq": "FAQ",
+        "footer.supportLinks.care": "Care Instructions",
+        "footer.supportLinks.flavors": "Flavors & Fillings",
+        "footer.supportLinks.contact": "Contact Us",
+        "footer.contact": "Contact",
+        "footer.contactDetails.address": "Downtown Arts District, Studio 12",
+        "footer.copyright": "© 2026 Twelve of 7 Bakeology. All rights reserved. Handcrafted with love.",
+        whatsappMessage: "Hi! I'd like to customize a cake order.",
+      },
+      zh: {
+        "nav.process": "流程",
+        "nav.gallery": "作品集",
+        "nav.flame": "火焰蛋糕",
+        "nav.reviews": "评价",
+        "nav.languageLabel": "语言",
+        "nav.chat": "马上咨询",
+        "hero.badge": "手工订制",
+        "hero.title": "让你的奇思妙想，<br/><span class=\"text-primary italic\">甜蜜成真 🎂</span>",
+        "hero.titleAccent": "甜蜜成真 🎂",
+        "hero.subtitle":
+          "为生日、婚礼与每个甜蜜时刻定制手工蛋糕。精选食材，在精品厨房用心打造。",
+        "hero.startOrder": "开始下单",
+        "hero.viewGallery": "浏览作品",
+        "process.title": "简单流程",
+        "process.subtitle": "下单梦想蛋糕只需 1、2、3 步",
+        "process.step1.title": "发送图片",
+        "process.step1.desc": "通过 WhatsApp 发送灵感图、Pinterest 板或手绘草图。",
+        "process.step2.title": "选择口味",
+        "process.step2.desc": "从 15+ 款蛋糕体、馅料与丝滑奶油中挑选。",
+        "process.step3.title": "欢聚取货",
+        "process.step3.desc": "领取你的手工杰作，与亲友开启庆祝时刻！",
+        "gallery.title": "新鲜出炉",
+        "gallery.subtitle": "最新作品，为你的庆祝加分。",
+        "gallery.viewAll": "查看全部",
+        "gallery.askButton": "<span class=\"material-symbols-outlined text-lg\">chat</span> 询问这款蛋糕",
+        "gallery.card1.title": "美人鱼幻想",
+        "gallery.card2.title": "复古裱花",
+        "gallery.card3.title": "巧克力金滴",
+        "gallery.tags.whimsical": "梦幻",
+        "gallery.tags.birthday": "生日",
+        "gallery.tags.classic": "经典",
+        "gallery.tags.vintage": "复古",
+        "gallery.tags.modern": "现代",
+        "gallery.tags.luxury": "奢华",
+        "footer.tagline": "自 2017 年起烘焙回忆，为梦想家、恋人和派对达人定制蛋糕。",
+        "footer.quickLinks": "快速链接",
+        "footer.links.home": "首页",
+        "footer.links.gallery": "作品集",
+        "footer.links.flame": "火焰蛋糕",
+        "footer.links.customOrders": "订制蛋糕",
+        "footer.support": "支持",
+        "footer.supportLinks.faq": "常见问题",
+        "footer.supportLinks.care": "保存说明",
+        "footer.supportLinks.flavors": "口味与夹心",
+        "footer.supportLinks.contact": "联系我们",
+        "footer.contact": "联系",
+        "footer.contactDetails.address": "市中心艺术区 12 号工作室",
+        "footer.copyright": "© 2026 Twelve of 7 Bakeology。保留所有权利。",
+        whatsappMessage: "你好！我想订制蛋糕。",
+      },
+      ms: {
+        "nav.process": "Proses",
+        "nav.gallery": "Galeri",
+        "nav.flame": "Kek Api",
+        "nav.reviews": "Ulasan",
+        "nav.languageLabel": "Bahasa",
+        "nav.chat": "Bual untuk tempahan",
+        "hero.badge": "Artisan & Tempahan Khas",
+        "hero.title": "Idea paling liar anda, <br/><span class=\"text-primary italic\">dibakar jadi nyata 🎂</span>",
+        "hero.titleAccent": "dibakar jadi nyata 🎂",
+        "hero.subtitle":
+          "Kek artisan tempahan khas untuk hari jadi, perkahwinan, dan setiap detik manis. Dihasilkan dengan kasih sayang dan bahan terbaik di dapur butik kami.",
+        "hero.startOrder": "Mulakan Tempahan",
+        "hero.viewGallery": "Lihat Galeri",
+        "process.title": "Proses Mudah",
+        "process.subtitle": "Menempah kek impian semudah 1, 2, 3",
+        "process.step1.title": "Hantar gambar",
+        "process.step1.desc": "Kongsi inspirasi, papan Pinterest, atau lakaran ringkas melalui WhatsApp.",
+        "process.step2.title": "Pilih perisa",
+        "process.step2.desc": "Pilih daripada 15+ pilihan span, inti artisan, dan buttercream baldu.",
+        "process.step3.title": "Ambil & raikan",
+        "process.step3.desc": "Ambil karya tangan anda dan mulakan sambutan bersama insan tersayang!",
+        "gallery.title": "Baru Keluar Oven",
+        "gallery.subtitle": "Koleksi terkini untuk sambutan anda.",
+        "gallery.viewAll": "Lihat Semua",
+        "gallery.askButton": "<span class=\"material-symbols-outlined text-lg\">chat</span> Tanya tentang kek ini",
+        "gallery.card1.title": "Fantasi Duyung",
+        "gallery.card2.title": "Paip Retro",
+        "gallery.card3.title": "Coklat Titis Emas",
+        "gallery.tags.whimsical": "Fantasi",
+        "gallery.tags.birthday": "Hari Jadi",
+        "gallery.tags.classic": "Klasik",
+        "gallery.tags.vintage": "Vintage",
+        "gallery.tags.modern": "Moden",
+        "gallery.tags.luxury": "Mewah",
+        "footer.tagline": "Membakar kenangan sejak 2017. Kek khas untuk pemimpi, pencinta, dan kaki parti.",
+        "footer.quickLinks": "Pautan Pantas",
+        "footer.links.home": "Laman Utama",
+        "footer.links.gallery": "Galeri",
+        "footer.links.flame": "Kek Api",
+        "footer.links.customOrders": "Tempahan Khas",
+        "footer.support": "Sokongan",
+        "footer.supportLinks.faq": "Soalan Lazim",
+        "footer.supportLinks.care": "Panduan Penjagaan",
+        "footer.supportLinks.flavors": "Perisa & Isian",
+        "footer.supportLinks.contact": "Hubungi Kami",
+        "footer.contact": "Hubungi",
+        "footer.contactDetails.address": "Daerah Seni Pusat Bandar, Studio 12",
+        "footer.copyright": "© 2026 Twelve of 7 Bakeology. Hak cipta terpelihara.",
+        whatsappMessage: "Hai! Saya ingin membuat tempahan kek khas.",
+      },
+    };
+
+    const setAssetBackgrounds = () => {
+      document.querySelectorAll("[data-local]").forEach((card) => {
+        const localSrc = card.getAttribute("data-local");
+        const fallback = card.getAttribute("data-fallback");
+        const image = new Image();
+
+        image.onload = () => {
+          card.style.backgroundImage = `url('${localSrc}')`;
+        };
+        image.onerror = () => {
+          card.style.backgroundImage = `url('${fallback}')`;
+        };
+        image.src = localSrc;
+      });
+    };
+
+    const updateWhatsAppLink = (locale) => {
+      const message = translations[locale]?.whatsappMessage || translations.en.whatsappMessage;
+      const text = encodeURIComponent(message);
+      whatsappLink.href = `https://wa.me/15557771207?text=${text}`;
+    };
+
+    const applyTranslations = (locale) => {
+      const dictionary = translations[locale] || translations.en;
+      document.documentElement.lang = locale === "zh" ? "zh" : locale === "ms" ? "ms" : "en";
+
+      document.querySelectorAll("[data-i18n]").forEach((node) => {
+        const key = node.getAttribute("data-i18n");
+        const value = dictionary[key];
+
+        if (!value) {
+          return;
+        }
+
+        if (value.includes("<") && value.includes(">")) {
+          node.innerHTML = value;
+        } else {
+          node.textContent = value;
+        }
+      });
+
+      updateWhatsAppLink(locale);
+    };
+
+    const initLanguageSwitcher = () => {
+      if (!languageSelect) {
+        return;
+      }
+
+      const saved = localStorage.getItem("preferredLanguage");
+      const defaultLocale = saved && translations[saved] ? saved : "en";
+      languageSelect.value = defaultLocale;
+      applyTranslations(defaultLocale);
+
+      languageSelect.addEventListener("change", (event) => {
+        const locale = event.target.value;
+        localStorage.setItem("preferredLanguage", locale);
+        applyTranslations(locale);
+      });
+    };
+
+    const initButtons = () => {
+      const openWhatsApp = () => {
+        if (whatsappLink) {
+          window.open(whatsappLink.href, "_blank", "noopener,noreferrer");
+        }
+      };
+
+      if (chatCustomize) {
+        chatCustomize.addEventListener("click", openWhatsApp);
+      }
+
+      if (startOrder) {
+        startOrder.addEventListener("click", openWhatsApp);
+      }
+
+      if (openGallery) {
+        openGallery.addEventListener("click", () => {
+          document.getElementById("gallery")?.scrollIntoView({ behavior: "smooth" });
+        });
+      }
+    };
+
+    setAssetBackgrounds();
+    initLanguageSwitcher();
+    initButtons();
+  </script>
 </body>
 </html>
 
EOF
)
