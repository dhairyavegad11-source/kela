<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>FreshPick Fruit Market - 100+ Fresh Organic Fruits</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>
    <!-- Google Fonts Inter -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                }
            }
        }
    </script>
</head>
<body class="bg-emerald-50/40 text-slate-800 font-sans min-h-screen flex flex-col justify-between selection:bg-emerald-500 selection:text-white">

    <!-- Navigation Header -->
    <header class="sticky top-0 z-40 bg-white/90 backdrop-blur-md border-b border-emerald-100 shadow-sm">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-20 flex items-center justify-between">
            <!-- Logo -->
            <div class="flex items-center space-x-3 cursor-pointer" onclick="resetView()">
                <div class="w-11 h-11 bg-emerald-600 rounded-2xl flex items-center justify-center text-white shadow-lg shadow-emerald-600/30">
                    <i data-lucide="apple" class="w-6 h-6"></i>
                </div>
                <div>
                    <span class="text-2xl font-black bg-gradient-to-r from-emerald-600 to-teal-700 bg-clip-text text-transparent">FreshPick</span>
                    <span class="block text-[10px] font-bold text-emerald-600 tracking-widest uppercase">100+ FRUIT MARKET</span>
                </div>
            </div>

            <!-- Search Bar (Desktop) -->
            <div class="hidden md:flex items-center flex-1 max-w-md mx-8">
                <div class="relative w-full">
                    <span class="absolute inset-y-0 left-0 flex items-center pl-3.5 pointer-events-none text-slate-400">
                        <i data-lucide="search" class="w-4 h-4"></i>
                    </span>
                    <input type="text" id="searchInput" oninput="handleSearch(event)" placeholder="Search across 100+ fruits (apples, berries, mangoes)..." class="w-full pl-10 pr-4 py-2.5 bg-slate-50 border border-slate-200 rounded-full text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500 focus:bg-white transition">
                </div>
            </div>

            <!-- Actions (Cart) -->
            <div class="flex items-center space-x-4">
                <button onclick="toggleCartDrawer()" class="relative p-2.5 bg-emerald-50 hover:bg-emerald-100 text-emerald-700 rounded-full transition flex items-center space-x-2 px-4 shadow-sm">
                    <i data-lucide="shopping-bag" class="w-5 h-5"></i>
                    <span class="text-sm font-semibold hidden sm:inline">Cart</span>
                    <span id="cartBadge" class="absolute -top-1 -right-1 bg-rose-500 text-white text-xs font-bold w-5 h-5 rounded-full flex items-center justify-center shadow-md animate-bounce hidden">0</span>
                </button>
            </div>
        </div>
        <!-- Mobile Search -->
        <div class="md:hidden px-4 pb-3">
            <div class="relative w-full">
                <span class="absolute inset-y-0 left-0 flex items-center pl-3.5 pointer-events-none text-slate-400">
                    <i data-lucide="search" class="w-4 h-4"></i>
                </span>
                <input type="text" id="mobileSearchInput" oninput="handleSearch(event)" placeholder="Search 100+ fruits..." class="w-full pl-10 pr-4 py-2 bg-slate-50 border border-slate-200 rounded-full text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
            </div>
        </div>
    </header>

    <main class="flex-grow">
        <!-- Hero Section -->
        <section class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
            <div class="bg-gradient-to-r from-emerald-600 via-teal-600 to-emerald-700 rounded-3xl p-8 sm:p-12 text-white shadow-xl relative overflow-hidden flex flex-col md:flex-row items-center justify-between">
                <div class="absolute right-0 bottom-0 opacity-15 transform translate-x-10 translate-y-10 pointer-events-none">
                    <i data-lucide="citrus" class="w-96 h-96"></i>
                </div>
                <div class="max-w-xl z-10 text-center md:text-left mb-6 md:mb-0">
                    <span class="inline-block bg-emerald-500/40 text-emerald-100 text-xs font-semibold px-3 py-1 rounded-full uppercase tracking-wider mb-4 backdrop-blur-sm">Massive Catalog: 100+ Farm Fresh Varieties</span>
                    <h1 class="text-3xl sm:text-5xl font-extrabold tracking-tight leading-tight mb-4">Pure Organic Fruits Delivered Fresh</h1>
                    <p class="text-emerald-100 text-sm sm:text-base mb-6 leading-relaxed">Explore our gigantic catalog of over 100+ farm-fresh, chemical-free exotic and seasonal fruits delivered straight to your doorstep within 45 minutes.</p>
                    <div class="flex flex-wrap gap-3 justify-center md:justify-start">
                        <button onclick="scrollToProducts()" class="bg-white text-emerald-700 font-semibold px-6 py-3 rounded-xl shadow-lg hover:bg-emerald-50 transition transform hover:-translate-y-0.5">Explore 100+ Fruits</button>
                        <div class="flex items-center space-x-2 px-4 py-3 bg-emerald-700/50 backdrop-blur-sm rounded-xl text-sm font-medium">
                            <i data-lucide="truck" class="w-4 h-4 text-emerald-300"></i>
                            <span>Express Delivery</span>
                        </div>
                    </div>
                </div>
                <div class="z-10 grid grid-cols-2 gap-3 w-full md:w-auto max-w-xs">
                    <div class="bg-white/10 backdrop-blur-md p-4 rounded-2xl border border-white/20 text-center">
                        <span class="block text-2xl font-bold">100+</span>
                        <span class="text-xs text-emerald-200">Fruit Varieties</span>
                    </div>
                    <div class="bg-white/10 backdrop-blur-md p-4 rounded-2xl border border-white/20 text-center">
                        <span class="block text-2xl font-bold">100%</span>
                        <span class="text-xs text-emerald-200">Organic & Safe</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Categories & Filter Section -->
        <section id="productsSection" class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
            <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 mb-6">
                <!-- Categories Pills -->
                <div id="categoryContainer" class="flex items-center gap-2 overflow-x-auto pb-2 scrollbar-none">
                    <!-- Injected via JS -->
                </div>

                <!-- Sorting Dropdown -->
                <div class="flex items-center space-x-2 self-end md:self-auto">
                    <span class="text-xs text-slate-500 font-medium whitespace-nowrap">Sort By:</span>
                    <select id="sortSelect" onchange="handleSort(event)" class="bg-white border border-slate-200 text-slate-700 text-sm rounded-xl px-3 py-2 focus:outline-none focus:ring-2 focus:ring-emerald-500 shadow-sm cursor-pointer">
                        <option value="featured">Featured (100+ Items)</option>
                        <option value="price-low">Price: Low to High</option>
                        <option value="price-high">Price: High to Low</option>
                        <option value="name">Name: A to Z</option>
                    </select>
                </div>
            </div>

            <!-- Product Grid -->
            <div id="productGrid" class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
                <!-- Injected via JS -->
            </div>
            
            <!-- Empty state -->
            <div id="emptyState" class="hidden text-center py-16 bg-white rounded-3xl border border-slate-100 mt-4 shadow-sm">
                <div class="w-16 h-16 bg-emerald-50 text-emerald-600 rounded-full flex items-center justify-center mx-auto mb-4">
                    <i data-lucide="search-x" class="w-8 h-8"></i>
                </div>
                <h3 class="text-lg font-bold text-slate-700 mb-1">No fruits found</h3>
                <p class="text-sm text-slate-500 mb-4">Try searching for another fruit or resetting filters.</p>
                <button onclick="clearFilters()" class="bg-emerald-600 text-white font-medium px-4 py-2 rounded-xl text-sm hover:bg-emerald-700 transition">Reset Filters</button>
            </div>
        </section>
    </main>

    <!-- Cart Slide-over Drawer -->
    <div id="cartOverlay" class="fixed inset-0 bg-slate-900/50 backdrop-blur-sm z-50 hidden transition-opacity opacity-0" onclick="toggleCartDrawer()"></div>
    <div id="cartDrawer" class="fixed inset-y-0 right-0 max-w-md w-full bg-white shadow-2xl z-50 transform translate-x-full transition-transform duration-300 ease-in-out flex flex-col justify-between">
        <!-- Drawer Header -->
        <div class="p-6 border-b border-slate-100 flex items-center justify-between bg-emerald-50/50">
            <div class="flex items-center space-x-2">
                <i data-lucide="shopping-bag" class="w-5 h-5 text-emerald-600"></i>
                <h2 class="text-lg font-bold text-slate-800">Your Fresh Cart</h2>
                <span id="cartItemCount" class="bg-emerald-600 text-white text-xs font-bold px-2 py-0.5 rounded-full">0</span>
            </div>
            <button onclick="toggleCartDrawer()" class="p-2 text-slate-400 hover:text-slate-600 rounded-full hover:bg-white transition">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>
        </div>

        <!-- Drawer Body (Items List) -->
        <div id="cartItemsList" class="flex-grow overflow-y-auto p-6 divide-y divide-slate-100">
            <!-- Injected via JS -->
        </div>

        <!-- Drawer Footer (Summary & Checkout) -->
        <div id="cartFooter" class="p-6 border-t border-slate-100 bg-slate-50/50 hidden">
            <div class="space-y-2 mb-4 text-sm">
                <div class="flex justify-between text-slate-600">
                    <span>Subtotal</span>
                    <span id="cartSubtotal" class="font-semibold text-slate-800">₹0</span>
                </div>
                <div class="flex justify-between text-slate-600">
                    <span>Delivery Charges</span>
                    <span id="cartDelivery" class="font-semibold text-emerald-600">₹40</span>
                </div>
                <div class="border-t border-slate-200 pt-2 flex justify-between text-base font-bold text-slate-900">
                    <span>Grand Total</span>
                    <span id="cartGrandTotal" class="text-emerald-700">₹0</span>
                </div>
            </div>
            <button onclick="openCheckoutModal()" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-semibold py-3.5 rounded-2xl shadow-lg shadow-emerald-600/30 transition flex items-center justify-center space-x-2">
                <span>Proceed to Checkout</span>
                <i data-lucide="arrow-right" class="w-4 h-4"></i>
            </button>
        </div>
    </div>

    <!-- Product Details Modal -->
    <div id="productModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-2xl w-full overflow-hidden shadow-2xl relative transform transition-all animate-in fade-in zoom-in duration-200" onclick="event.stopPropagation()">
            <button onclick="closeProductModal()" class="absolute top-4 right-4 z-10 p-2 bg-white/80 hover:bg-white text-slate-600 rounded-full backdrop-blur-md shadow-md transition">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>
            <div id="modalContent" class="grid grid-cols-1 md:grid-cols-2">
                <!-- Injected via JS -->
            </div>
        </div>
    </div>

    <!-- Checkout Modal -->
    <div id="checkoutModal" class="fixed inset-0 bg-slate-900/60 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4 overflow-y-auto">
        <div class="bg-white rounded-3xl max-w-xl w-full overflow-hidden shadow-2xl relative my-8" onclick="event.stopPropagation()">
            <div class="p-6 border-b border-slate-100 flex items-center justify-between bg-emerald-50/50">
                <div class="flex items-center space-x-2">
                    <i data-lucide="shield-check" class="w-5 h-5 text-emerald-600"></i>
                    <h2 class="text-lg font-bold text-slate-800">Secure Checkout</h2>
                </div>
                <button onclick="closeCheckoutModal()" class="p-2 text-slate-400 hover:text-slate-600 rounded-full hover:bg-white transition">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>
            
            <form id="checkoutForm" onsubmit="handleCheckoutSubmit(event)" class="p-6 space-y-6 max-h-[75vh] overflow-y-auto">
                <!-- Step 1: Customer Details -->
                <div>
                    <h3 class="text-sm font-bold text-slate-700 uppercase tracking-wider mb-3">1. Customer Information & Delivery Slot</h3>
                    <div class="space-y-3">
                        <div>
                            <label class="block text-xs font-medium text-slate-600 mb-1">Full Name</label>
                            <input type="text" id="custName" required placeholder="Aarav Sharma" class="w-full px-4 py-2.5 bg-slate-50 border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
                        </div>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                            <div>
                                <label class="block text-xs font-medium text-slate-600 mb-1">Phone Number</label>
                                <input type="tel" id="custPhone" required placeholder="9876543210" pattern="[0-9]{10}" class="w-full px-4 py-2.5 bg-slate-50 border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
                            </div>
                            <div>
                                <label class="block text-xs font-medium text-slate-600 mb-1">Email Address</label>
                                <input type="email" id="custEmail" required placeholder="aarav@example.com" class="w-full px-4 py-2.5 bg-slate-50 border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
                            </div>
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-600 mb-1">Delivery Address</label>
                            <textarea id="custAddress" required rows="2" placeholder="House No, Street, Landmark, City, Pincode" class="w-full px-4 py-2.5 bg-slate-50 border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500 resize-none"></textarea>
                        </div>
                        <div>
                            <label class="block text-xs font-medium text-slate-600 mb-1">Preferred Delivery Slot</label>
                            <select id="custSlot" class="w-full px-4 py-2.5 bg-slate-50 border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500 cursor-pointer">
                                <option value="Express (45 Mins)">Express Delivery (Within 45 Mins)</option>
                                <option value="Morning Slot (7 AM - 10 AM)">Morning Slot (7:00 AM - 10:00 AM)</option>
                                <option value="Evening Slot (4 PM - 7 PM)">Evening Slot (4:00 PM - 7:00 PM)</option>
                            </select>
                        </div>
                    </div>
                </div>

                <!-- Step 2: Payment Option -->
                <div>
                    <h3 class="text-sm font-bold text-slate-700 uppercase tracking-wider mb-3">2. Select Payment Method</h3>
                    <div class="grid grid-cols-3 gap-3 mb-4">
                        <label class="border border-slate-200 rounded-2xl p-4 flex flex-col items-center justify-center cursor-pointer hover:border-emerald-500 transition has-[:checked]:border-emerald-600 has-[:checked]:bg-emerald-50/50">
                            <input type="radio" name="paymentMethod" value="UPI" checked onchange="togglePaymentSection('UPI')" class="hidden">
                            <i data-lucide="smartphone" class="w-6 h-6 text-emerald-600 mb-1"></i>
                            <span class="text-xs font-semibold text-slate-700">UPI</span>
                        </label>
                        <label class="border border-slate-200 rounded-2xl p-4 flex flex-col items-center justify-center cursor-pointer hover:border-emerald-500 transition has-[:checked]:border-emerald-600 has-[:checked]:bg-emerald-50/50">
                            <input type="radio" name="paymentMethod" value="Card" onchange="togglePaymentSection('Card')" class="hidden">
                            <i data-lucide="credit-card" class="w-6 h-6 text-emerald-600 mb-1"></i>
                            <span class="text-xs font-semibold text-slate-700">Card</span>
                        </label>
                        <label class="border border-slate-200 rounded-2xl p-4 flex flex-col items-center justify-center cursor-pointer hover:border-emerald-500 transition has-[:checked]:border-emerald-600 has-[:checked]:bg-emerald-50/50">
                            <input type="radio" name="paymentMethod" value="COD" onchange="togglePaymentSection('COD')" class="hidden">
                            <i data-lucide="banknote" class="w-6 h-6 text-emerald-600 mb-1"></i>
                            <span class="text-xs font-semibold text-slate-700">Cash on Delivery</span>
                        </label>
                    </div>

                    <!-- Dynamic Payment Sub-sections -->
                    <div id="paymentUPI" class="p-4 bg-slate-50 rounded-2xl border border-slate-200 text-center space-y-3">
                        <p class="text-xs text-slate-600">Scan QR code using GPay, PhonePe, or Paytm</p>
                        <div class="w-36 h-36 bg-white p-2 rounded-xl mx-auto shadow-sm border border-slate-200 flex items-center justify-center">
                            <svg viewBox="0 0 100 100" class="w-full h-full text-slate-800">
                                <path fill="currentColor" d="M0 0h30v30H0zM10 10h10v10H10zM40 0h20v10H40zM70 0h30v30H70zM80 10h10v10H80zM0 40h10v20H0zM20 40h10v10H20zM40 40h20v10H40zM70 40h10v10H70zM90 40h10v10H90zM30 50h10v20H30zM50 50h10v10H50zM0 70h30v30H0zM10 80h10v10H10zM40 70h10v30H40zM70 70h20v20H70zM60 80h10v20H60zM90 90h10v10H90z"/>
                            </svg>
                        </div>
                        <span class="inline-block text-xs font-bold text-emerald-700 bg-emerald-100 px-3 py-1 rounded-full">UPI ID: freshpick@okaxis</span>
                    </div>

                    <div id="paymentCard" class="p-4 bg-slate-50 rounded-2xl border border-slate-200 space-y-3 hidden">
                        <div>
                            <label class="block text-xs font-medium text-slate-600 mb-1">Card Number</label>
                            <input type="text" placeholder="4111 2222 3333 4444" class="w-full px-3 py-2 bg-white border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
                        </div>
                        <div class="grid grid-cols-2 gap-2">
                            <div>
                                <label class="block text-xs font-medium text-slate-600 mb-1">Expiry (MM/YY)</label>
                                <input type="text" placeholder="12/28" class="w-full px-3 py-2 bg-white border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
                            </div>
                            <div>
                                <label class="block text-xs font-medium text-slate-600 mb-1">CVV</label>
                                <input type="password" placeholder="123" maxlength="4" class="w-full px-3 py-2 bg-white border border-slate-200 rounded-xl text-sm focus:outline-none focus:ring-2 focus:ring-emerald-500">
                            </div>
                        </div>
                    </div>

                    <div id="paymentCOD" class="p-4 bg-emerald-50/50 rounded-2xl border border-emerald-200 text-center text-xs text-emerald-800 hidden">
                        <i data-lucide="info" class="w-4 h-4 inline mr-1 text-emerald-600"></i>
                        Please keep exact cash ready at the time of delivery. Verification OTP will be sent.
                    </div>
                </div>

                <!-- Submit Button -->
                <button type="submit" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3.5 rounded-2xl shadow-lg shadow-emerald-600/30 transition">
                    Place Order (₹<span id="checkoutModalTotal">0</span>)
                </button>
            </form>
        </div>
    </div>

    <!-- Order Success Modal / Screen -->
    <div id="successModal" class="fixed inset-0 bg-slate-900/70 backdrop-blur-md z-50 hidden flex items-center justify-center p-4">
        <div class="bg-white rounded-3xl max-w-md w-full p-8 text-center shadow-2xl relative animate-in zoom-in duration-300">
            <div class="w-20 h-20 bg-emerald-100 text-emerald-600 rounded-full flex items-center justify-center mx-auto mb-5 shadow-inner">
                <i data-lucide="check-circle-2" class="w-10 h-10"></i>
            </div>
            <h2 class="text-2xl font-black text-slate-800 mb-1">Order Placed Successfully!</h2>
            <p class="text-sm text-slate-500 mb-6">Thank you for shopping with FreshPick. Your 100% organic fruit order is on the way.</p>
            
            <div class="bg-slate-50 border border-slate-100 rounded-2xl p-4 mb-6 text-left space-y-2 text-xs">
                <div class="flex justify-between">
                    <span class="text-slate-500">Order ID:</span>
                    <span id="successOrderId" class="font-bold text-slate-800">#FP-98421</span>
                </div>
                <div class="flex justify-between">
                    <span class="text-slate-500">Delivery Slot:</span>
                    <span id="successSlot" class="font-bold text-emerald-600">Express (45 Mins)</span>
                </div>
                <div class="flex justify-between">
                    <span class="text-slate-500">Payment Mode:</span>
                    <span id="successPayMode" class="font-bold text-slate-800">UPI</span>
                </div>
                <div class="border-t border-slate-200 pt-2 flex justify-between text-sm font-bold text-slate-900">
                    <span>Total Paid:</span>
                    <span id="successTotal" class="text-emerald-700">₹0</span>
                </div>
            </div>

            <button onclick="closeSuccessModal()" class="w-full bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3 rounded-2xl shadow-lg shadow-emerald-600/30 transition">
                Continue Shopping
            </button>
        </div>
    </div>

    <!-- Footer -->
    <footer class="bg-white border-t border-emerald-100 mt-16 py-8">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 flex flex-col md:flex-row items-center justify-between gap-4 text-center md:text-left">
            <div class="flex items-center space-x-2">
                <div class="w-8 h-8 bg-emerald-600 rounded-xl flex items-center justify-center text-white">
                    <i data-lucide="apple" class="w-4 h-4"></i>
                </div>
                <span class="font-bold text-lg text-slate-800">FreshPick Fruit Market</span>
            </div>
            <p class="text-xs text-slate-500">&copy; 2026 FreshPick Inc. All rights reserved. 100+ Organic & Farm Fresh Varieties.</p>
            <div class="flex space-x-4 text-xs text-slate-600 font-medium">
                <a href="#" class="hover:text-emerald-600 transition">Privacy Policy</a>
                <a href="#" class="hover:text-emerald-600 transition">Terms of Service</a>
                <a href="#" class="hover:text-emerald-600 transition">Support</a>
            </div>
        </div>
    </footer>

    <!-- JavaScript Application Logic -->
    <script>
        // Comprehensive pool of fruit types and image banks to generate 100+ rich products
        const baseFruitTemplates = [
            { name: "Kashmiri Organic Apples", category: "Orchard Apples", price: 180, unit: "1 kg", badge: "Bestseller", image: "https://images.unsplash.com/photo-1560806887-1e4cd0b6cbd6?auto=format&fit=crop&q=80&w=800", desc: "Crisp and juicy organic apples directly from Kashmir valleys." },
            { name: "Robusta Bananas", category: "Tropical & Exotic", price: 60, unit: "1 dozen", badge: "Fresh", image: "https://images.unsplash.com/photo-1571771894821-ce9b6c11b08e?auto=format&fit=crop&q=80&w=800", desc: "Naturally ripened sweet Robusta bananas loaded with potassium." },
            { name: "Fresh Strawberries", category: "Fresh Berries", price: 250, unit: "250g pack", badge: "Organic", image: "https://images.unsplash.com/photo-1464965911861-746a04b4bca6?auto=format&fit=crop&q=80&w=800", desc: "Plump, sweet, and tangy organic strawberries harvested at peak ripeness." },
            { name: "Alpine Blueberries", category: "Fresh Berries", price: 350, unit: "125g pack", badge: "Superfood", image: "https://images.unsplash.com/photo-1498557850523-fd3d118b962e?auto=format&fit=crop&q=80&w=800", desc: "Packed with powerful antioxidants. Plump mountain-grown blueberries." },
            { name: "Alphonso Mangoes", category: "Seasonal Picks", price: 499, unit: "1 kg (4 pcs)", badge: "King of Fruits", image: "https://images.unsplash.com/photo-1553279768-865429fa0078?auto=format&fit=crop&q=80&w=800", desc: "Legendary Hapus mangoes with unmatched aroma and creaminess." },
            { name: "Hass Avocados", category: "Tropical & Exotic", price: 299, unit: "2 pcs", badge: "Exotic", image: "https://images.unsplash.com/photo-1523049673857-eb18f1d7b578?auto=format&fit=crop&q=80&w=800", desc: "Creamy, nutrient-dense Hass avocados loaded with healthy fats." },
            { name: "Red Dragon Fruit", category: "Tropical & Exotic", price: 199, unit: "1 pc (~400g)", badge: "Exotic", image: "https://images.unsplash.com/photo-1527324789755-91b685d4f0f0?auto=format&fit=crop&q=80&w=800", desc: "Vibrant pitaya with delicate sweet flavor and crunchy seeds." },
            { name: "Nagpur Juicy Oranges", category: "Citrus & Oranges", price: 120, unit: "1 kg", badge: "Fresh", image: "https://images.unsplash.com/photo-1547514701-42782101795e?auto=format&fit=crop&q=80&w=800", desc: "Farm-fresh Nagpur oranges bursting with zesty citrus juice." },
            { name: "Green Kiwi Fruits", category: "Tropical & Exotic", price: 160, unit: "Pack of 3", badge: "Imported", image: "https://images.unsplash.com/photo-1585059895050-32a514d7c0e1?auto=format&fit=crop&q=80&w=800", desc: "Tangy-sweet kiwis rich in Vitamin C and dietary fiber." },
            { name: "Kiran Watermelon", category: "Seasonal Picks", price: 110, unit: "1 pc (~2.5 kg)", badge: "Juicy", image: "https://images.unsplash.com/photo-1587049352847-4a222e784d38?auto=format&fit=crop&q=80&w=800", desc: "Super hydrating, crisp, and naturally sweet red watermelon." },
            { name: "Sweet Pineapples", category: "Tropical & Exotic", price: 130, unit: "1 pc (~1 kg)", badge: "Fresh", image: "https://images.unsplash.com/photo-1550258987-190a2d41a8ba?auto=format&fit=crop&q=80&w=800", desc: "Tropical golden pineapples with sweet and tart flavor." },
            { name: "Dark Sweet Cherries", category: "Fresh Berries", price: 399, unit: "250g pack", badge: "Organic", image: "https://images.unsplash.com/photo-1528821128474-27f963b062bf?auto=format&fit=crop&q=80&w=800", desc: "Luxurious, dark red sweet cherries loaded with antioxidants." },
            { name: "Ruby Pomegranates", category: "Seasonal Picks", price: 180, unit: "1 kg", badge: "Fresh", image: "https://images.unsplash.com/photo-1615485290382-441e4d049cb5?auto=format&fit=crop&q=80&w=800", desc: "Ruby-red arils bursting with antioxidant-rich juices." },
            { name: "Ripe Papaya", category: "Tropical & Exotic", price: 90, unit: "1 pc (~1.2 kg)", badge: "Organic", image: "https://images.unsplash.com/photo-1617112848923-cc2234394a8d?auto=format&fit=crop&q=80&w=800", desc: "Naturally sweet and buttery ripe papaya with digestive enzymes." },
            { name: "Black Shine Grapes", category: "Fresh Berries", price: 150, unit: "500g pack", badge: "Seedless", image: "https://images.unsplash.com/photo-1537640538966-79f369143f8f?auto=format&fit=crop&q=80&w=800", desc: "Juicy, crisp seedless black grapes packed with resveratrol." }
        ];

        const adjectives = ["Premium", "Super Sweet", "Royal", "Valley Fresh", "Grand", "Handpicked", "Crisp", "Exotic", "Golden", "Organic Elite"];
        
        // Automatically generate 105 unique products to ensure a massive catalog
        let products = [];
        let idCounter = 1;

        while (products.length < 105) {
            baseFruitTemplates.forEach(template => {
                if (products.length >= 105) return;
                const adj = adjectives[products.length % adjectives.length];
                const variantName = products.length < 15 ? template.name : `${adj} ${template.name} #${Math.floor(products.length / 15) + 1}`;
                const priceOffset = (products.length % 7) * 15;
                const finalPrice = Math.max(40, template.price + (products.length % 2 === 0 ? priceOffset : -priceOffset));
                const ratingNum = (4.5 + ((products.length % 5) * 0.1)).toFixed(1);

                products.push({
                    id: idCounter++,
                    name: variantName,
                    category: template.category,
                    price: finalPrice,
                    unit: template.unit,
                    rating: parseFloat(ratingNum) > 5.0 ? 5.0 : parseFloat(ratingNum),
                    reviewsCount: 40 + (products.length * 7) % 250,
                    stock: 10 + (products.length * 3) % 40,
                    badge: products.length % 3 === 0 ? "Bestseller" : (products.length % 4 === 0 ? "Organic" : template.badge),
                    image: template.image,
                    description: template.desc + ` Sourced from prime micro-climates to ensure ultimate freshness and vitamin density.`,
                    nutritionalInfo: `Calories: ${45 + (products.length % 30)} kcal | Fiber: ${(1.2 + (products.length % 3) * 0.5).toFixed(1)}g | Vitamin C: ${(15 + (products.length % 40))}% DV`
                });
            });
        }

        let cart = [];
        let currentCategory = 'All';
        let searchQuery = '';
        let currentSort = 'featured';
        const deliveryCharge = 40;

        const categories = ['All', 'Fresh Berries', 'Tropical & Exotic', 'Citrus & Oranges', 'Orchard Apples', 'Seasonal Picks'];

        window.addEventListener('DOMContentLoaded', () => {
            renderCategories();
            renderProducts();
            updateCartUI();
            lucide.createIcons();
        });

        function renderCategories() {
            const container = document.getElementById('categoryContainer');
            container.innerHTML = categories.map(cat => `
                <button onclick="setCategory('${cat}')" class="px-5 py-2.5 rounded-2xl text-sm font-semibold whitespace-nowrap transition shadow-sm ${currentCategory === cat ? 'bg-emerald-600 text-white shadow-emerald-600/30' : 'bg-white text-slate-600 border border-slate-200 hover:bg-emerald-50'}">
                    ${cat}
                </button>
            `).join('');
            lucide.createIcons();
        }

        function setCategory(cat) {
            currentCategory = cat;
            renderCategories();
            renderProducts();
        }

        function handleSearch(e) {
            searchQuery = e.target.value.toLowerCase().trim();
            document.getElementById('searchInput').value = searchQuery;
            document.getElementById('mobileSearchInput').value = searchQuery;
            renderProducts();
        }

        function handleSort(e) {
            currentSort = e.target.value;
            renderProducts();
        }

        function clearFilters() {
            currentCategory = 'All';
            searchQuery = '';
            document.getElementById('searchInput').value = '';
            document.getElementById('mobileSearchInput').value = '';
            document.getElementById('sortSelect').value = 'featured';
            currentSort = 'featured';
            renderCategories();
            renderProducts();
        }

        function scrollToProducts() {
            document.getElementById('productsSection').scrollIntoView({ behavior: 'smooth' });
        }

        function renderProducts() {
            let filtered = products.filter(p => {
                const matchesCategory = currentCategory === 'All' || p.category === currentCategory;
                const matchesSearch = p.name.toLowerCase().includes(searchQuery) || p.description.toLowerCase().includes(searchQuery);
                return matchesCategory && matchesSearch;
            });

            if (currentSort === 'price-low') {
                filtered.sort((a, b) => a.price - b.price);
            } else if (currentSort === 'price-high') {
                filtered.sort((a, b) => b.price - a.price);
            } else if (currentSort === 'name') {
                filtered.sort((a, b) => a.name.localeCompare(b.name));
            }

            const grid = document.getElementById('productGrid');
            const emptyState = document.getElementById('emptyState');

            if (filtered.length === 0) {
                grid.innerHTML = '';
                emptyState.classList.remove('hidden');
                return;
            }

            emptyState.classList.add('hidden');
            grid.innerHTML = filtered.map(p => `
                <div class="bg-white rounded-3xl border border-slate-100 shadow-sm hover:shadow-xl transition-all duration-300 flex flex-col justify-between overflow-hidden group">
                    <div>
                        <!-- Image Container -->
                        <div class="relative h-48 overflow-hidden bg-slate-100 cursor-pointer" onclick="openProductModal(${p.id})">
                            <img src="${p.image}" alt="${p.name}" class="w-full h-full object-cover group-hover:scale-105 transition duration-500" onerror="this.src='https://placehold.co/400x300/10b981/ffffff?text=Fresh+Fruit'">
                            <div class="absolute top-3 left-3 bg-white/90 backdrop-blur-md text-emerald-700 text-xs font-bold px-2.5 py-1 rounded-full shadow-md">
                                ${p.badge}
                            </div>
                            <div class="absolute bottom-3 right-3 bg-black/60 backdrop-blur-md text-white text-xs px-2.5 py-1 rounded-full flex items-center space-x-1">
                                <i data-lucide="star" class="w-3.5 h-3.5 fill-amber-400 text-amber-400"></i>
                                <span>${p.rating}</span>
                            </div>
                        </div>

                        <!-- Content -->
                        <div class="p-5">
                            <span class="text-xs font-medium text-emerald-600 uppercase tracking-wider">${p.category}</span>
                            <h3 class="font-bold text-slate-800 text-base mt-1 cursor-pointer hover:text-emerald-600 transition truncate" onclick="openProductModal(${p.id})">${p.name}</h3>
                            <p class="text-xs text-slate-500 mt-1 line-clamp-2">${p.description}</p>
                        </div>
                    </div>

                    <!-- Price & Add to Cart -->
                    <div class="p-5 pt-0 flex items-center justify-between border-t border-slate-50 mt-2">
                        <div>
                            <span class="text-lg font-black text-slate-900">₹${p.price}</span>
                            <span class="text-xs text-slate-500 font-medium"> / ${p.unit}</span>
                        </div>
                        <button onclick="addToCart(${p.id})" class="bg-emerald-600 hover:bg-emerald-700 text-white p-2.5 rounded-2xl shadow-md shadow-emerald-600/30 transition transform active:scale-95 flex items-center justify-center">
                            <i data-lucide="plus" class="w-5 h-5"></i>
                        </button>
                    </div>
                </div>
            `).join('');

            lucide.createIcons();
        }

        function toggleCartDrawer() {
            const drawer = document.getElementById('cartDrawer');
            const overlay = document.getElementById('cartOverlay');
            const isOpen = !drawer.classList.contains('translate-x-full');

            if (isOpen) {
                drawer.classList.add('translate-x-full');
                overlay.classList.add('opacity-0');
                setTimeout(() => overlay.classList.add('hidden'), 300);
            } else {
                overlay.classList.remove('hidden');
                setTimeout(() => overlay.classList.remove('opacity-0'), 10);
                drawer.classList.remove('translate-x-full');
            }
        }

        function addToCart(productId) {
            const product = products.find(p => p.id === productId);
            const existing = cart.find(item => item.id === productId);

            if (existing) {
                existing.quantity += 1;
            } else {
                cart.push({ ...product, quantity: 1 });
            }

            updateCartUI();
            
            const drawer = document.getElementById('cartDrawer');
            if (drawer.classList.contains('translate-x-full')) {
                toggleCartDrawer();
            }
        }

        function updateQuantity(productId, change) {
            const item = cart.find(i => i.id === productId);
            if (!item) return;

            item.quantity += change;
            if (item.quantity <= 0) {
                removeFromCart(productId);
            } else {
                updateCartUI();
            }
        }

        function removeFromCart(productId) {
            cart = cart.filter(i => i.id !== productId);
            updateCartUI();
        }

        function updateCartUI() {
            const badge = document.getElementById('cartBadge');
            const itemCount = document.getElementById('cartItemCount');
            const list = document.getElementById('cartItemsList');
            const footer = document.getElementById('cartFooter');

            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);

            if (totalItems > 0) {
                badge.innerText = totalItems;
                badge.classList.remove('hidden');
                itemCount.innerText = totalItems;
                footer.classList.remove('hidden');
            } else {
                badge.classList.add('hidden');
                itemCount.innerText = '0';
                footer.classList.add('hidden');
            }

            if (cart.length === 0) {
                list.innerHTML = `
                    <div class="text-center py-16">
                        <div class="w-16 h-16 bg-emerald-50 text-emerald-600 rounded-full flex items-center justify-center mx-auto mb-4">
                            <i data-lucide="shopping-bag" class="w-8 h-8"></i>
                        </div>
                        <h4 class="font-bold text-slate-700 mb-1">Your cart is empty</h4>
                        <p class="text-xs text-slate-500">Explore our 100+ fresh fruits collection and add items.</p>
                    </div>
                `;
                lucide.createIcons();
                return;
            }

            list.innerHTML = cart.map(item => `
                <div class="py-4 flex items-center justify-between gap-4">
                    <div class="flex items-center space-x-3">
                        <img src="${item.image}" alt="${item.name}" class="w-16 h-16 rounded-2xl object-cover bg-slate-100 flex-shrink-0">
                        <div>
                            <h4 class="font-bold text-sm text-slate-800">${item.name}</h4>
                            <span class="text-xs text-slate-500">₹${item.price} / ${item.unit}</span>
                            <div class="flex items-center space-x-2 mt-2">
                                <button onclick="updateQuantity(${item.id}, -1)" class="w-6 h-6 rounded-lg bg-slate-100 hover:bg-emerald-100 text-slate-600 hover:text-emerald-700 flex items-center justify-center transition">
                                    <i data-lucide="minus" class="w-3 h-3"></i>
                                </button>
                                <span class="text-xs font-bold text-slate-800 w-5 text-center">${item.quantity}</span>
                                <button onclick="updateQuantity(${item.id}, 1)" class="w-6 h-6 rounded-lg bg-slate-100 hover:bg-emerald-100 text-slate-600 hover:text-emerald-700 flex items-center justify-center transition">
                                    <i data-lucide="plus" class="w-3 h-3"></i>
                                </button>
                            </div>
                        </div>
                    </div>
                    <div class="text-right flex flex-col justify-between h-full">
                        <button onclick="removeFromCart(${item.id})" class="text-slate-400 hover:text-rose-500 transition">
                            <i data-lucide="trash-2" class="w-4 h-4"></i>
                        </button>
                        <span class="text-sm font-black text-slate-900 mt-6">₹${item.price * item.quantity}</span>
                    </div>
                </div>
            `).join('');

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const grandTotal = subtotal + (subtotal > 0 ? deliveryCharge : 0);

            document.getElementById('cartSubtotal').innerText = `₹${subtotal}`;
            document.getElementById('cartDelivery').innerText = subtotal > 0 ? `₹${deliveryCharge}` : `₹0`;
            document.getElementById('cartGrandTotal').innerText = `₹${grandTotal}`;

            lucide.createIcons();
        }

        function openProductModal(productId) {
            const product = products.find(p => p.id === productId);
            if (!product) return;

            const modal = document.getElementById('productModal');
            const content = document.getElementById('modalContent');

            content.innerHTML = `
                <div class="relative h-72 md:h-full bg-slate-100">
                    <img src="${product.image}" alt="${product.name}" class="w-full h-full object-cover" onerror="this.src='https://placehold.co/400x400/10b981/ffffff?text=Fresh+Fruit'">
                    <div class="absolute top-4 left-4 bg-white/90 backdrop-blur-md text-emerald-700 text-xs font-bold px-3 py-1 rounded-full shadow-md">
                        ${product.badge}
                    </div>
                </div>
                <div class="p-6 md:p-8 flex flex-col justify-between">
                    <div>
                        <span class="text-xs font-semibold text-emerald-600 uppercase tracking-wider">${product.category}</span>
                        <h2 class="text-2xl font-black text-slate-800 mt-1 mb-2">${product.name}</h2>
                        
                        <div class="flex items-center space-x-3 mb-4">
                            <div class="flex items-center space-x-1 text-amber-500 text-xs font-bold">
                                <i data-lucide="star" class="w-4 h-4 fill-amber-400"></i>
                                <span>${product.rating}</span>
                            </div>
                            <span class="text-slate-300">•</span>
                            <span class="text-xs text-slate-500">${product.reviewsCount} verified reviews</span>
                            <span class="text-slate-300">•</span>
                            <span class="text-xs text-emerald-600 font-medium">${product.stock} in stock</span>
                        </div>

                        <p class="text-sm text-slate-600 mb-4 leading-relaxed">${product.description}</p>

                        <div class="bg-emerald-50/50 border border-emerald-100 rounded-2xl p-4 mb-6">
                            <h4 class="text-xs font-bold text-emerald-800 uppercase tracking-wider mb-1 flex items-center space-x-1">
                                <i data-lucide="heart-pulse" class="w-4 h-4 text-emerald-600"></i>
                                <span>Nutritional Value</span>
                            </h4>
                            <p class="text-xs text-emerald-900 font-medium">${product.nutritionalInfo}</p>
                        </div>
                    </div>

                    <div class="flex items-center justify-between pt-4 border-t border-slate-100">
                        <div>
                            <span class="text-2xl font-black text-slate-900">₹${product.price}</span>
                            <span class="text-xs text-slate-500 font-medium"> / ${product.unit}</span>
                        </div>
                        <button onclick="addToCart(${product.id}); closeProductModal();" class="bg-emerald-600 hover:bg-emerald-700 text-white font-semibold px-6 py-3 rounded-2xl shadow-lg shadow-emerald-600/35 transition flex items-center space-x-2">
                            <i data-lucide="shopping-bag" class="w-4 h-4"></i>
                            <span>Add to Cart</span>
                        </button>
                    </div>
                </div>
            `;

            modal.classList.remove('hidden');
            lucide.createIcons();
        }

        function closeProductModal() {
            document.getElementById('productModal').classList.add('hidden');
        }

        function openCheckoutModal() {
            if (cart.length === 0) return;
            toggleCartDrawer();

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const grandTotal = subtotal + deliveryCharge;
            document.getElementById('checkoutModalTotal').innerText = grandTotal;

            document.getElementById('checkoutModal').classList.remove('hidden');
        }

        function closeCheckoutModal() {
            document.getElementById('checkoutModal').classList.add('hidden');
        }

        function togglePaymentSection(method) {
            document.getElementById('paymentUPI').classList.add('hidden');
            document.getElementById('paymentCard').classList.add('hidden');
            document.getElementById('paymentCOD').classList.add('hidden');

            if (method === 'UPI') {
                document.getElementById('paymentUPI').classList.remove('hidden');
            } else if (method === 'Card') {
                document.getElementById('paymentCard').classList.remove('hidden');
            } else if (method === 'COD') {
                document.getElementById('paymentCOD').classList.remove('hidden');
            }
        }

        function handleCheckoutSubmit(e) {
            e.preventDefault();
            
            const paymentMethod = document.querySelector('input[name="paymentMethod"]:checked').value;
            const deliverySlot = document.getElementById('custSlot').value;

            const subtotal = cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
            const grandTotal = subtotal + deliveryCharge;
            const orderId = '#FP-' + Math.floor(10000 + Math.random() * 90000);

            document.getElementById('successOrderId').innerText = orderId;
            document.getElementById('successSlot').innerText = deliverySlot;
            document.getElementById('successPayMode').innerText = paymentMethod;
            document.getElementById('successTotal').innerText = `₹${grandTotal}`;

            closeCheckoutModal();

            cart = [];
            updateCartUI();
            document.getElementById('checkoutForm').reset();

            document.getElementById('successModal').classList.remove('hidden');
            lucide.createIcons();
        }

        function closeSuccessModal() {
            document.getElementById('successModal').classList.add('hidden');
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }

        function resetView() {
            clearFilters();
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    </script>
</body>
</html>
