<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AZFER STORE - Premium Gaming Services</title>
    <!-- Menggunakan Font Google Poppins untuk tampilan modern -->
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #6c5ce7;
            --primary-dark: #5a4ad1;
            --secondary: #a29bfe;
            --bg-dark: #0f0f12;
            --card-bg: #1a1a1d;
            --text-light: #ffffff;
            --text-muted: #a0a0a0;
            --accent: #00cec9;
            --success: #00b894;
            --error: #d63031;
            --vip-gold: #fdcb6e;
            --member-gradient: linear-gradient(135deg, #6c5ce7 0%, #a29bfe 100%);
            --vvip-gradient: linear-gradient(135deg, #d63031 0%, #ff7675 100%);
            --admin-gradient: linear-gradient(135deg, #2d3436 0%, #000000 100%);
            --apk-color: #ff7675;
            --netys-color: #00b894;
            --pubg-orange: #f39c12; /* Warna khusus PUBG */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* SPLASH SCREEN ANIMATION */
        #splash-screen {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at center, #1a1a2e 0%, #0f0f12 100%);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 9999;
            opacity: 1;
            transition: opacity 0.8s ease-out;
        }

        #splash-screen.hidden {
            opacity: 0;
            pointer-events: none;
        }

        .logo-container {
            text-align: center;
            animation: fadeInScale 1.5s ease-out forwards;
        }

        @keyframes fadeInScale {
            0% {
                opacity: 0;
                transform: scale(0.5);
            }
            100% {
                opacity: 1;
                transform: scale(1);
            }
        }

        .logo-svg {
            width: 280px;
            max-width: 90vw;
            filter: drop-shadow(0 0 15px rgba(108, 92, 231, 0.5));
        }

        .splash-text {
            margin-top: 20px;
            font-size: 1.2rem;
            color: #a29bfe;
            letter-spacing: 2px;
            animation: pulseText 2s infinite alternate;
        }

        @keyframes pulseText {
            0% { opacity: 0.6; }
            100% { opacity: 1; }
        }

        /* Header Modern */
        header {
            background: rgba(15, 15, 18, 0.95);
            backdrop-filter: blur(10px);
            padding: 1.5rem 2rem;
            text-align: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 1px solid rgba(255,255,255,0.05);
            box-shadow: 0 4px 20px rgba(0,0,0,0.5);
        }

        header h1 {
            font-size: 2rem;
            font-weight: 700;
            background: linear-gradient(to right, #6c5ce7, #00cec9);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: 1px;
            margin-bottom: 0.2rem;
        }

        header p {
            color: var(--text-muted);
            font-size: 0.9rem;
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* Section Titles */
        .section-header {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .section-title {
            font-size: 2rem;
            font-weight: 600;
            display: inline-block;
            margin-bottom: 10px;
        }

        .section-line {
            height: 4px;
            width: 60px;
            background: var(--primary);
            margin: 0 auto;
            border-radius: 2px;
        }

        /* Grid Layout */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        /* Cards Modern Style */
        .card {
            background-color: var(--card-bg);
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s cubic-bezier(0.25, 0.8, 0.25, 1);
            border: 1px solid rgba(255,255,255,0.05);
            position: relative;
            display: flex;
            flex-direction: column;
        }

        .card:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.4);
            border-color: rgba(108, 92, 231, 0.3);
        }

        .card-header {
            padding: 20px;
            text-align: center;
            font-weight: 700;
            font-size: 1.3rem;
            position: relative;
        }

        .ff-theme { border-top: 4px solid #ff9f43; }
        .ml-theme { border-top: 4px solid #0984e3; }
        .pubg-theme { border-top: 4px solid var(--pubg-orange); } /* Update warna PUBG */
        .vip-theme { border-top: 4px solid var(--vip-gold); }
        .member-theme .card-header { background: var(--member-gradient); color: white; }
        .vvip-theme .card-header { background: var(--vvip-gradient); color: white; }
        .admin-theme .card-header { background: var(--admin-gradient); color: white; border-bottom: 1px solid #333; }
        .apk-theme { border-left: 4px solid var(--apk-color); }
        .netys-theme { border-left: 4px solid var(--netys-color); }

        .card-body {
            padding: 25px;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .card-desc {
            font-size: 0.9rem;
            color: var(--text-muted);
            margin-bottom: 15px;
            text-align: center;
        }

        .price-tag {
            font-size: 1.8rem;
            color: var(--text-light);
            font-weight: 700;
            margin: 15px 0;
            text-align: center;
        }
        
        .price-sub {
            font-size: 0.8rem;
            color: var(--text-muted);
            font-weight: 400;
            display: block;
        }

        .features-list {
            list-style: none;
            margin-bottom: 20px;
        }

        .features-list li {
            padding: 8px 0;
            border-bottom: 1px solid rgba(255,255,255,0.05);
            font-size: 0.9rem;
            color: #ddd;
            display: flex;
            align-items: center;
        }

        .features-list li:before {
            content: "✓";
            color: var(--success);
            font-weight: bold;
            margin-right: 10px;
        }

        .stock-badge {
            background-color: rgba(225, 112, 85, 0.2);
            color: #e17055;
            padding: 4px 10px;
            border-radius: 20px;
            font-size: 0.75rem;
            font-weight: 600;
            position: absolute;
            top: 15px;
            right: 15px;
        }

        .code-info {
            background: rgba(0,0,0,0.3);
            padding: 12px;
            border-radius: 10px;
            margin: 15px 0;
            font-family: 'Courier New', monospace;
            text-align: center;
            border: 1px dashed rgba(255,255,255,0.2);
            font-size: 0.9rem;
            color: var(--secondary);
        }

        .form-group {
            margin-bottom: 15px;
            margin-top: auto;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-size: 0.85rem;
            color: var(--text-muted);
            font-weight: 500;
        }

        input {
            width: 100%;
            padding: 12px 15px;
            border-radius: 10px;
            border: 1px solid rgba(255,255,255,0.1);
            background-color: #0f0f12;
            color: white;
            transition: 0.3s;
        }

        input:focus {
            outline: none;
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(108, 92, 231, 0.2);
        }

        .coupon-container {
            display: flex;
            gap: 10px;
        }

        .btn-check-coupon {
            background-color: rgba(255,255,255,0.1);
            color: #fff;
            border: none;
            padding: 0 20px;
            border-radius: 10px;
            cursor: pointer;
            font-weight: 600;
            transition: 0.3s;
        }

        .btn-check-coupon:hover {
            background-color: var(--primary);
        }

        .coupon-message {
            font-size: 0.8rem;
            margin-top: 8px;
            min-height: 20px;
        }

        .coupon-valid { color: var(--success); }
        .coupon-invalid { color: var(--error); }

        .final-price {
            background: rgba(0, 206, 201, 0.1);
            padding: 15px;
            border-radius: 12px;
            margin-top: 15px;
            text-align: center;
            border: 1px solid rgba(0, 206, 201, 0.3);
        }

        .original-price {
            text-decoration: line-through;
            color: #666;
            font-size: 0.9rem;
        }

        .discounted-price {
            color: var(--success);
            font-weight: 700;
            font-size: 1.4rem;
        }

        .btn {
            display: block;
            width: 100%;
            padding: 14px;
            border: none;
            border-radius: 12px;
            background-color: var(--primary);
            color: white;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-align: center;
            margin-top: 15px;
            letter-spacing: 0.5px;
        }

        .btn:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(108, 92, 231, 0.4);
        }

        .btn-buy-account { background-color: #00b894; }
        .btn-buy-account:hover { background-color: #00a383; box-shadow: 0 5px 15px rgba(0, 184, 148, 0.4); }

        .btn-vip { background-color: var(--vip-gold); color: #000; }
        .btn-vip:hover { background-color: #e1b12c; box-shadow: 0 5px 15px rgba(253, 203, 110, 0.4); }

        .btn-member { background: white; color: var(--primary); }
        .btn-member:hover { background: #f0f0f0; }

        .btn-vvip { background: white; color: var(--vvip-red); }
        .btn-vvip:hover { background: #ffeaa7; }

        .btn-admin { background: #fff; color: #000; border: 2px solid #fff; }
        .btn-admin:hover { background: #000; color: #fff; }

        .btn-apk { background-color: var(--apk-color); }
        .btn-apk:hover { background-color: #ff5252; box-shadow: 0 5px 15px rgba(255, 118, 117, 0.4); }

        .btn-netys { background-color: var(--netys-color); }
        .btn-netys:hover { background-color: #00a383; box-shadow: 0 5px 15px rgba(0, 184, 148, 0.4); }
        
        .btn-pubg { background-color: var(--pubg-orange); color: #000; }
        .btn-pubg:hover { background-color: #d35400; color: #fff; box-shadow: 0 5px 15px rgba(243, 156, 18, 0.4); }

        footer {
            text-align: center;
            padding: 3rem 2rem;
            background-color: #0a0a0c;
            color: #666;
            border-top: 1px solid rgba(255,255,255,0.05);
        }

        @media (max-width: 600px) {
            header h1 { font-size: 1.5rem; }
            .grid { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>

    <!-- SPLASH SCREEN -->
    <div id="splash-screen">
        <div class="logo-container">
            <!-- Logo ID Toko Games dalam bentuk SVG -->
            <svg class="logo-svg" viewBox="0 0 400 300" xmlns="http://www.w3.org/2000/svg">
                <path d="M50,150 Q100,50 200,80 Q300,50 350,150 L330,170 Q280,100 200,120 Q120,100 70,170 Z" fill="#1a237e" stroke="#fff" stroke-width="2"/>
                <path d="M70,170 Q120,100 200,120 Q280,100 330,170 L310,190 Q260,130 200,140 Q140,130 90,190 Z" fill="#3949ab" stroke="#fff" stroke-width="1.5"/>
                <path d="M100,180 L300,180 L280,260 Q200,280 120,260 Z" fill="#0d47a1" stroke="#fff" stroke-width="2"/>
                <polygon points="180,60 185,75 200,75 188,85 192,100 180,90 168,100 172,85 160,75 175,75" fill="#ffd700"/>
                <circle cx="150" cy="70" r="5" fill="#fff"/>
                <circle cx="250" cy="70" r="5" fill="#fff"/>
                <circle cx="130" cy="80" r="3" fill="#fff"/>
                <circle cx="270" cy="80" r="3" fill="#fff"/>
                <text x="200" y="160" font-family="Arial Black, sans-serif" font-size="80" fill="#fff" text-anchor="middle" stroke="#000" stroke-width="3">ID</text>
                <text x="80" y="200" font-family="Arial, sans-serif" font-size="20" fill="#fff">20</text>
                <text x="80" y="225" font-family="Arial, sans-serif" font-size="20" fill="#fff">13</text>
                <text x="320" y="200" font-family="Arial, sans-serif" font-size="20" fill="#fff">20</text>
                <text x="320" y="225" font-family="Arial, sans-serif" font-size="20" fill="#fff">13</text>
                <rect x="60" y="270" width="280" height="40" rx="10" fill="#0d47a1" stroke="#fff" stroke-width="2"/>
                <text x="200" y="298" font-family="Arial Black, sans-serif" font-size="24" fill="#fff" text-anchor="middle">TOKO GAMES</text>
            </svg>
            
            <div class="splash-text">MEMUAT AZFER STORE...</div>
        </div>
    </div>

    <header>
        <h1>AZFER STORE</h1>
        <p>Premium Gaming Services & Digital Products</p>
    </header>

    <div class="container">
        
        <!-- BAGIAN 0: MEMBERSHIP & ADMIN -->
        <div class="section-header">
            <h2 class="section-title">Membership & Access</h2>
            <div class="section-line"></div>
        </div>

        <div class="grid">
            <!-- Membership Kelas 1 -->
            <div class="card member-theme">
                <div class="card-header">MEMBERSHIP KELAS 1</div>
                <div class="card-body">
                    <p class="card-desc">Akses eksklusif dengan diskon hingga 37% untuk semua transaksi.</p>
                    <div class="price-tag">Rp 135.000 <span class="price-sub">Bayar Sebulan Sekali</span></div>
                    <ul class="features-list">
                        <li>Prioritas Pelayanan</li>
                        <li>Akses Kupon Super Diskon</li>
                        <li>Bonus Diamond (Event Tertentu)</li>
                    </ul>
                    <div class="code-info">KODE: ****** (Beli untuk Dapatkan)</div>
                    <p style="font-size: 0.75rem; text-align: center; color: #ffd700; margin-bottom: 15px;">Kode dikirim via WhatsApp setelah pembayaran.</p>
                    <div class="form-group">
                        <label>Cek Kupon Member</label>
                        <div class="coupon-container">
                            <input type="text" id="member-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('MEMBER')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="member-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="member-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="member-final-price">Rp 0</div>
                    </div>
                    <button onclick="buyMembership()" class="btn btn-member">Beli Membership</button>
                </div>
            </div>

            <!-- Membership VVIP -->
            <div class="card vvip-theme">
                <div class="card-header">MEMBERSHIP VVIP 👑</div>
                <div class="card-body">
                    <p class="card-desc">Status tertinggi! Diskon gila-gilaan hingga 49%.</p>
                    <div class="price-tag">Rp 250.000 <span class="price-sub">Bayar Sebulan Sekali</span></div>
                    <ul class="features-list">
                        <li>Prioritas Utama (Fast Response)</li>
                        <li>Akses Kupon VVIP Diskon 49%</li>
                        <li>Gratis Ongkir Admin (Jika Ada)</li>
                    </ul>
                    <div class="code-info">KODE: ****** (Beli untuk Dapatkan)</div>
                    <p style="font-size: 0.75rem; text-align: center; color: #ffd700; margin-bottom: 15px;">Kode dikirim via WhatsApp setelah pembayaran.</p>
                    <div class="form-group">
                        <label>Cek Kupon VVIP</label>
                        <div class="coupon-container">
                            <input type="text" id="vvip-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('VVIP')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="vvip-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="vvip-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="vvip-final-price">Rp 0</div>
                    </div>
                    <button onclick="buyVvip()" class="btn btn-vvip">Beli VVIP</button>
                </div>
            </div>

            <!-- ADMIN VVIP -->
            <div class="card admin-theme">
                <div class="card-header">ADMIN VVIP 💻</div>
                <div class="card-body">
                    <p class="card-desc">Akses penuh ke sistem website AZFER STORE.</p>
                    <div class="price-tag">Rp 5.000.000</div>
                    <ul class="features-list">
                        <li>PROMO 100% (Gunakan Kupon)</li>
                        <li>DAPET AKSES WEB</li>
                        <li>DAPET AKSES ADMIN WEB</li>
                        <li>AKSES CODE CSS, HTML, JS</li>
                    </ul>
                    <div class="code-info" style="border-style: solid; color: #fff;">HUBUNGI ADMIN LANGSUNG</div>
                    <div class="form-group">
                        <label>Cek Kupon Admin</label>
                        <div class="coupon-container">
                            <input type="text" id="admin-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('ADMIN')" class="btn-check-coupon" style="background:#fff; color:#000;">Cek</button>
                        </div>
                        <div id="admin-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="admin-price-display" class="final-price" style="display:none; border-color: #fff;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="admin-final-price" style="color: #fff;">Rp 0</div>
                    </div>
                    <button onclick="buyAdmin()" class="btn btn-admin">Beli Akses Admin</button>
                </div>
            </div>
        </div>

        <!-- TOKO APK PREMIUM -->
        <div class="section-header">
            <h2 class="section-title">Premium APK Store</h2>
            <div class="section-line"></div>
        </div>

        <div class="grid">
            <!-- GTA SA -->
            <div class="card apk-theme">
                <div class="card-body">
                    <h3 style="margin-bottom:5px;">GTA SAN ANDREAS</h3>
                    <p class="card-desc">Game open world legendaris HD.</p>
                    <div class="price-tag">Rp 137.000</div>
                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="apk-gta-sa-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('APK_GTA_SA')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-gta-sa-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-gta-sa-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="apk-gta-sa-final-price">Rp 0</div>
                    </div>
                    <button onclick="buyApk('GTA SAN ANDREAS', 137000, 'APK_GTA_SA')" class="btn btn-apk">Beli APK</button>
                </div>
            </div>

            <!-- GTA VICE CITY -->
            <div class="card apk-theme">
                <div class="card-body">
                    <h3 style="margin-bottom:5px;">GTA VICE CITY</h3>
                    <p class="card-desc">Aksi kriminal era 80-an.</p>
                    <div class="price-tag">Rp 147.000</div>
                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="apk-gta-vc-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('APK_GTA_VC')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-gta-vc-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-gta-vc-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="apk-gta-vc-final-price">Rp 0</div>
                    </div>
                    <button onclick="buyApk('GTA VICE CITY', 147000, 'APK_GTA_VC')" class="btn btn-apk">Beli APK</button>
                </div>
            </div>

            <!-- POPPY PLAYTIME -->
            <div class="card apk-theme">
                <div class="card-body">
                    <h3 style="margin-bottom:5px;">POPPY PLAYTIME 1-5</h3>
                    <p class="card-desc">Bundle Chapter 1-5 Horror.</p>
                    <div class="price-tag">Rp 200.000</div>
                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="apk-poppy-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('APK_POPPY')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-poppy-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-poppy-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="apk-poppy-final-price">Rp 0</div>
                    </div>
                    <button onclick="buyApk('POPPY PLAYTIME 1-5', 200000, 'APK_POPPY')" class="btn btn-apk">Beli Bundle</button>
                </div>
            </div>

            <!-- GTA SA CHEAT -->
            <div class="card apk-theme">
                <div class="card-body">
                    <h3 style="margin-bottom:5px;">GTA SA UNLI MONEY</h3>
                    <p class="card-desc">Mod Uang Tak Terbatas.</p>
                    <div class="price-tag">Rp 138.000</div>
                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="apk-gta-cheat-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('APK_GTA_CHEAT')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-gta-cheat-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-gta-cheat-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="apk-gta-cheat-final-price">Rp 0</div>
                    </div>
                    <button onclick="buyApk('GTA SA CHEAT', 138000, 'APK_GTA_CHEAT')" class="btn btn-apk">Beli Mod</button>
                </div>
            </div>

            <!-- ROBLOX DELTA -->
            <div class="card apk-theme">
                <div class="card-body">
                    <h3 style="margin-bottom:5px;">ROBLOX DELTA</h3>
                    <p class="card-desc">Executor Script Hub Mobile.</p>
                    <div class="price-tag">Rp 20.000</div>
                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="apk-delta-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('APK_DELTA')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-delta-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-delta-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="apk-delta-final-price">Rp 0</div>
                    </div>
                    <button onclick="buyApk('ROBLOX DELTA', 20000, 'APK_DELTA')" class="btn btn-apk">Beli Executor</button>
                </div>
            </div>
        </div>

        <!-- TOP UP DIAMOND -->
        <div class="section-header">
            <h2 class="section-title">Daily Top Up</h2>
            <div class="section-line"></div>
        </div>
        
        <div class="grid">
            <!-- Free Fire -->
            <div class="card ff-theme">
                <div class="card-header">FREE FIRE</div>
                <div class="card-body">
                    <p class="card-desc">Harga per 10 Diamond = Rp 5.000</p>
                    <div class="form-group">
                        <label>ID Player</label>
                        <input type="number" id="ff-id" placeholder="123456789">
                    </div>
                    <div class="form-group">
                        <label>Jumlah Diamond</label>
                        <input type="number" id="ff-diamond" placeholder="Min. 10" min="10" step="10" oninput="calculatePrice('FF')">
                    </div>
                    
                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="ff-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('FF')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="ff-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="ff-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="ff-final-price">Rp 0</div>
                    </div>

                    <button onclick="orderTopUp('FF')" class="btn">Top Up Sekarang</button>
                </div>
            </div>

            <!-- Mobile Legends -->
            <div class="card ml-theme">
                <div class="card-header">MOBILE LEGENDS</div>
                <div class="card-body">
                    <p class="card-desc">Harga per 10 Diamond = Rp 5.000</p>
                    <div class="form-group">
                        <label>User ID & Zone</label>
                        <input type="text" id="ml-id" placeholder="12345678 (1234)">
                    </div>
                    <div class="form-group">
                        <label>Jumlah Diamond</label>
                        <input type="number" id="ml-diamond" placeholder="Min. 10" min="10" step="10" oninput="calculatePrice('ML')">
                    </div>

                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="ml-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('ML')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="ml-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="ml-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="ml-final-price">Rp 0</div>
                    </div>

                    <button onclick="orderTopUp('ML')" class="btn">Top Up Sekarang</button>
                </div>
            </div>

            <!-- PUBG MOBILE (UPDATED & ACTIVE) -->
            <div class="card pubg-theme">
                <div class="card-header">PUBG MOBILE</div>
                <div class="card-body">
                    <p class="card-desc">Harga per 50 UC/Diamond = Rp 10.000</p>
                    <div class="form-group">
                        <label>ID Player PUBG</label>
                        <input type="number" id="pubg-id" placeholder="Contoh: 5123456789">
                    </div>
                    <div class="form-group">
                        <label>Jumlah UC/Diamond</label>
                        <!-- Step 50 karena harga dasar per 50 -->
                        <input type="number" id="pubg-diamond" placeholder="Min. 50" min="50" step="50" oninput="calculatePrice('PUBG')">
                    </div>

                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="pubg-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('PUBG')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="pubg-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="pubg-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="pubg-final-price">Rp 0</div>
                    </div>

                    <button onclick="orderTopUp('PUBG')" class="btn btn-pubg">Top Up Sekarang</button>
                </div>
            </div>
        </div>

        <!-- LAYANAN KHUSUS -->
        <div class="section-header">
            <h2 class="section-title">Special Services</h2>
            <div class="section-line"></div>
        </div>

        <div class="grid">
            <!-- Fake Lag VIP -->
            <div class="card vip-theme">
                <div class="card-header">FAKE LAG VIP 👑</div>
                <div class="card-body">
                    <p class="card-desc">Smooth & Anti-lag experience.</p>
                    <div class="price-tag">Rp 15.000</div>
                    
                    <div class="form-group">
                        <label>ID Game</label>
                        <input type="text" id="vip-id" placeholder="ID Anda">
                    </div>

                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="vip-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('VIP')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="vip-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="vip-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="vip-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyVip()" class="btn btn-vip">Beli Fake Lag</button>
                </div>
            </div>

            <!-- KEY NETYS -->
            <div class="card netys-theme">
                <div class="card-header">KEY NETYS 🔑</div>
                <div class="card-body">
                    <p class="card-desc">Akses premium aplikasi Netys.</p>
                    <div class="price-tag">Rp 5.000</div>
                    
                    <ul class="features-list">
                        <li>BERLAKU SELAMANYA</li>
                        <li>GARANSI 1 TAHUN + APK</li>
                    </ul>

                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="netys-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('NETYS')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="netys-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="netys-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="netys-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyNetys()" class="btn btn-netys">Beli Key</button>
                </div>
            </div>
        </div>


        <!-- JUAL AKUN PREMIUM -->
        <div class="section-header">
            <h2 class="section-title">Premium Accounts</h2>
            <div class="section-line"></div>
        </div>

        <div class="grid">
            <!-- Akun FF -->
            <div class="card ff-theme">
                <div class="card-header">AKUN SULTAN FF <span class="stock-badge">Stok: 1</span></div>
                <div class="card-body">
                    <ul class="features-list">
                        <li>Full Skin Legend</li>
                        <li>Level Max</li>
                        <li>Win Rate Tinggi</li>
                    </ul>
                    <div class="price-tag">Rp 250.000</div>
                    <div class="code-info">KODE: AZFER.FF</div>
                    
                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="acc-ff-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('ACC_FF')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="acc-ff-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="acc-ff-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="acc-ff-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyAccount('AKUN FF', 250000, 'AZFER.FF', 'ACC_FF')" class="btn btn-buy-account">Beli Akun</button>
                </div>
            </div>

            <!-- Akun ML -->
            <div class="card ml-theme">
                <div class="card-header">AKUN MYTHIC ML <span class="stock-badge">Stok: 1</span></div>
                <div class="card-body">
                    <ul class="features-list">
                        <li>Skin Collector/Legend</li>
                        <li>Emblem Max</li>
                        <li>Winrate Bagus</li>
                    </ul>
                    <div class="price-tag">Rp 190.000</div>
                    <div class="code-info">KODE: AZFEF.ML</div>

                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="acc-ml-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('ACC_ML')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="acc-ml-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="acc-ml-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="acc-ml-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyAccount('AKUN ML', 190000, 'AZFEF.ML', 'ACC_ML')" class="btn btn-buy-account">Beli Akun</button>
                </div>
            </div>

            <!-- Akun PUBG -->
            <div class="card pubg-theme">
                <div class="card-header">AKUN VETERAN PUBG <span class="stock-badge">Stok: 1</span></div>
                <div class="card-body">
                    <ul class="features-list">
                        <li>Outfit Mythic</li>
                        <li>Senjata Upgrade</li>
                        <li>Akun Aman</li>
                    </ul>
                    <div class="price-tag">Rp 50.000</div>
                    <div class="code-info">KODE: AZFER.PUBG</div>

                    <div class="form-group">
                        <div class="coupon-container">
                            <input type="text" id="acc-pubg-coupon" placeholder="Kode Promo">
                            <button onclick="checkCoupon('ACC_PUBG')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="acc-pubg-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="acc-pubg-price-display" class="final-price" style="display:none;">
                        <div class="discounted-price" id="acc-pubg-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyAccount('AKUN PUBG', 50000, 'AZFER.PUBG', 'ACC_PUBG')" class="btn btn-buy-account">Beli Akun</button>
                </div>
            </div>
        </div>

    </div>

    <footer>
        <p>&copy; 2026 AZFER STORE. All Rights Reserved.</p>
        <p>Pembayaran via QRIS / Transfer</p>
    </footer>

    <script>
        // --- SPLASH SCREEN LOGIC ---
        document.addEventListener('DOMContentLoaded', function() {
            const splash = document.getElementById('splash-screen');
            if (!sessionStorage.getItem('splashShown')) {
                splash.classList.remove('hidden');
                setTimeout(() => {
                    splash.classList.add('hidden');
                    sessionStorage.setItem('splashShown', 'true');
                }, 3000);
            } else {
                splash.classList.add('hidden');
            }
        });

        // --- KONFIGURASI KUPON ---
        const waNumber = "6285882382854"; 
        
        const coupons = {
            "DISKON_UPDATE25": { discount: 0.25, desc: "Diskon Update 25%" }, // KUPON BARU
            "ADMIN_AZFER2013": { discount: 1.00, desc: "Diskon Admin 100% (GRATIS)" },
            "MEMBER_VVIP2013": { discount: 0.49, desc: "Diskon VVIP 49%" }, 
            "MEMBER_SHIP1": { discount: 0.37, desc: "Diskon Member 37%" }, 
            "TOKO.ID": { discount: 0.25, desc: "Diskon 25%" },
            "AZFERPROMO": { discount: 0.10, desc: "Diskon 10%" },
            "NEWUSER": { discount: 0.05, desc: "Diskon 5%" },
            "MERDEKA": { discount: 0.17, desc: "Diskon 17%" }
        };

        let activeCoupons = {
            'FF': null, 'ML': null, 'PUBG': null, 'VIP': null, 
            'ACC_FF': null, 'ACC_ML': null, 'ACC_PUBG': null,
            'MEMBER': null,
            'VVIP': null,
            'ADMIN': null,
            'NETYS': null,
            'APK_GTA_SA': null,
            'APK_GTA_VC': null,
            'APK_POPPY': null,
            'APK_GTA_CHEAT': null,
            'APK_DELTA': null
        };

        // Fungsi Cek Kupon
        function checkCoupon(sectionId) {
            let inputId, msgId;

            if (sectionId === 'FF') { inputId = 'ff-coupon'; msgId = 'ff-coupon-msg'; }
            else if (sectionId === 'ML') { inputId = 'ml-coupon'; msgId = 'ml-coupon-msg'; }
            else if (sectionId === 'PUBG') { inputId = 'pubg-coupon'; msgId = 'pubg-coupon-msg'; } // Tambahan PUBG
            else if (sectionId === 'VIP') { inputId = 'vip-coupon'; msgId = 'vip-coupon-msg'; }
            else if (sectionId === 'MEMBER') { inputId = 'member-coupon'; msgId = 'member-coupon-msg'; }
            else if (sectionId === 'VVIP') { inputId = 'vvip-coupon'; msgId = 'vvip-coupon-msg'; }
            else if (sectionId === 'ADMIN') { inputId = 'admin-coupon'; msgId = 'admin-coupon-msg'; }
            else if (sectionId === 'NETYS') { inputId = 'netys-coupon'; msgId = 'netys-coupon-msg'; }
            else if (sectionId.startsWith('APK_')) {
                const shortName = sectionId.replace('APK_', '').toLowerCase();
                inputId = `apk-${shortName}-coupon`;
                msgId = `apk-${shortName}-coupon-msg`;
            }
            else {
                const shortName = sectionId.replace('ACC_', '').toLowerCase();
                inputId = `acc-${shortName}-coupon`;
                msgId = `acc-${shortName}-coupon-msg`;
            }
            
            const codeInput = document.getElementById(inputId);
            const msgElement = document.getElementById(msgId);
            const code = codeInput.value.trim().toUpperCase();

            if (coupons[code]) {
                activeCoupons[sectionId] = coupons[code];
                msgElement.textContent = `Berhasil! ${coupons[code].desc} diterapkan.`;
                msgElement.className = "coupon-message coupon-valid";
                
                if(sectionId === 'FF' || sectionId === 'ML' || sectionId === 'PUBG') calculatePrice(sectionId);
                else if (sectionId === 'VIP') calculateVipPrice();
                else if (sectionId === 'MEMBER') calculateMemberPrice();
                else if (sectionId === 'VVIP') calculateVvipPrice();
                else if (sectionId === 'ADMIN') calculateAdminPrice();
                else if (sectionId === 'NETYS') calculateNetysPrice();
                else if (sectionId.startsWith('APK_')) calculateApkPrice(sectionId);
                else updateAccountPriceDisplay(sectionId);
            } else {
                activeCoupons[sectionId] = null;
                msgElement.textContent = "Kode tidak valid.";
                msgElement.className = "coupon-message coupon-invalid";
                
                if(sectionId === 'FF' || sectionId === 'ML' || sectionId === 'PUBG') calculatePrice(sectionId);
                else if (sectionId === 'VIP') resetVipPriceDisplay();
                else if (sectionId === 'MEMBER') resetMemberPriceDisplay();
                else if (sectionId === 'VVIP') resetVvipPriceDisplay();
                else if (sectionId === 'ADMIN') resetAdminPriceDisplay();
                else if (sectionId === 'NETYS') resetNetysPriceDisplay();
                else if (sectionId.startsWith('APK_')) resetApkPriceDisplay(sectionId);
                else resetAccountPriceDisplay(sectionId);
            }
        }

        function formatRupiah(angka) {
            return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR', maximumFractionDigits: 0 }).format(angka);
        }

        // --- LOGIKA ADMIN VVIP ---
        const ADMIN_PRICE = 5000000;
        function calculateAdminPrice() {
            const displayEl = document.getElementById('admin-price-display');
            const finalPriceEl = document.getElementById('admin-final-price');
            displayEl.style.display = 'block';
            if (activeCoupons['ADMIN']) {
                const discountAmount = ADMIN_PRICE * activeCoupons['ADMIN'].discount;
                const finalPrice = ADMIN_PRICE - discountAmount;
                finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(ADMIN_PRICE)}</span><br>${formatRupiah(finalPrice)}`;
            } else {
                finalPriceEl.textContent = formatRupiah(ADMIN_PRICE);
            }
        }
        function resetAdminPriceDisplay() { document.getElementById('admin-price-display').style.display = 'none'; }
        function buyAdmin() {
            let finalPrice = ADMIN_PRICE;
            let couponText = "";
            if (activeCoupons['ADMIN']) {
                finalPrice = ADMIN_PRICE - (ADMIN_PRICE * activeCoupons['ADMIN'].discount);
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons['ADMIN']).toUpperCase()} (${activeCoupons['ADMIN'].desc})\n`;
            }
            sendToWhatsApp("ADMIN VVIP ACCESS", finalPrice, couponText, { type: "Admin Access" });
        }

        // --- LOGIKA KEY NETYS ---
        const NETYS_PRICE = 5000;
        function calculateNetysPrice() {
            const displayEl = document.getElementById('netys-price-display');
            const finalPriceEl = document.getElementById('netys-final-price');
            displayEl.style.display = 'block';
            if (activeCoupons['NETYS']) {
                const discountAmount = NETYS_PRICE * activeCoupons['NETYS'].discount;
                const finalPrice = NETYS_PRICE - discountAmount;
                finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(NETYS_PRICE)}</span><br>${formatRupiah(finalPrice)}`;
            } else {
                finalPriceEl.textContent = formatRupiah(NETYS_PRICE);
            }
        }
        function resetNetysPriceDisplay() { document.getElementById('netys-price-display').style.display = 'none'; }
        function buyNetys() {
            let finalPrice = NETYS_PRICE;
            let couponText = "";
            if (activeCoupons['NETYS']) {
                finalPrice = NETYS_PRICE - (NETYS_PRICE * activeCoupons['NETYS'].discount);
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons['NETYS']).toUpperCase()} (${activeCoupons['NETYS'].desc})\n`;
            }
            sendToWhatsApp("KEY NETYS", finalPrice, couponText, { type: "Layanan Khusus" });
        }

        // --- LOGIKA VVIP ---
        const VVIP_PRICE = 250000;
        function calculateVvipPrice() {
            const displayEl = document.getElementById('vvip-price-display');
            const finalPriceEl = document.getElementById('vvip-final-price');
            displayEl.style.display = 'block';
            if (activeCoupons['VVIP']) {
                const discountAmount = VVIP_PRICE * activeCoupons['VVIP'].discount;
                const finalPrice = VVIP_PRICE - discountAmount;
                finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(VVIP_PRICE)}</span><br>${formatRupiah(finalPrice)}`;
            } else {
                finalPriceEl.textContent = formatRupiah(VVIP_PRICE);
            }
        }
        function resetVvipPriceDisplay() { document.getElementById('vvip-price-display').style.display = 'none'; }
        function buyVvip() {
            let finalPrice = VVIP_PRICE;
            let couponText = "";
            if (activeCoupons['VVIP']) {
                finalPrice = VVIP_PRICE - (VVIP_PRICE * activeCoupons['VVIP'].discount);
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons['VVIP']).toUpperCase()} (${activeCoupons['VVIP'].desc})\n`;
            }
            sendToWhatsApp("MEMBERSHIP VVIP", finalPrice, couponText, { type: "Membership VVIP" });
        }

        // --- LOGIKA APK ---
        function calculateApkPrice(sectionId) {
            let basePrice = 0;
            if(sectionId === 'APK_GTA_SA') basePrice = 137000;
            if(sectionId === 'APK_GTA_VC') basePrice = 147000;
            if(sectionId === 'APK_POPPY') basePrice = 200000;
            if(sectionId === 'APK_GTA_CHEAT') basePrice = 138000;
            if(sectionId === 'APK_DELTA') basePrice = 20000;

            const shortName = sectionId.replace('APK_', '').toLowerCase();
            const displayId = `apk-${shortName}-price-display`;
            const finalPriceId = `apk-${shortName}-final-price`;
            const displayEl = document.getElementById(displayId);
            const finalPriceEl = document.getElementById(finalPriceId);

            if(activeCoupons[sectionId]) {
                const discountAmount = basePrice * activeCoupons[sectionId].discount;
                const finalPrice = basePrice - discountAmount;
                displayEl.style.display = 'block';
                finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(basePrice)}</span><br>${formatRupiah(finalPrice)}`;
            } else {
                displayEl.style.display = 'none';
            }
        }
        function resetApkPriceDisplay(sectionId) {
            const shortName = sectionId.replace('APK_', '').toLowerCase();
            document.getElementById(`apk-${shortName}-price-display`).style.display = 'none';
        }
        function buyApk(itemName, basePrice, sectionId) {
            let finalPrice = basePrice;
            let couponText = "";
            if (activeCoupons[sectionId]) {
                finalPrice = basePrice - (basePrice * activeCoupons[sectionId].discount);
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons[sectionId]).toUpperCase()} (${activeCoupons[sectionId].desc})\n`;
            }
            sendToWhatsApp(itemName, finalPrice, couponText, { type: "APK Premium" });
        }

        // --- LOGIKA MEMBERSHIP KELAS 1 ---
        const MEMBER_PRICE = 135000;
        function calculateMemberPrice() {
            const displayEl = document.getElementById('member-price-display');
            const finalPriceEl = document.getElementById('member-final-price');
            displayEl.style.display = 'block';
            if (activeCoupons['MEMBER']) {
                const discountAmount = MEMBER_PRICE * activeCoupons['MEMBER'].discount;
                const finalPrice = MEMBER_PRICE - discountAmount;
                finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(MEMBER_PRICE)}</span><br>${formatRupiah(finalPrice)}`;
            } else {
                finalPriceEl.textContent = formatRupiah(MEMBER_PRICE);
            }
        }
        function resetMemberPriceDisplay() { document.getElementById('member-price-display').style.display = 'none'; }
        function buyMembership() {
            let finalPrice = MEMBER_PRICE;
            let couponText = "";
            if (activeCoupons['MEMBER']) {
                finalPrice = MEMBER_PRICE - (MEMBER_PRICE * activeCoupons['MEMBER'].discount);
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons['MEMBER']).toUpperCase()} (${activeCoupons['MEMBER'].desc})\n`;
            }
            sendToWhatsApp("MEMBERSHIP KELAS 1", finalPrice, couponText, { type: "Membership" });
        }

        // --- LOGIKA FAKE LAG VIP ---
        const VIP_PRICE = 15000;
        function calculateVipPrice() {
            const displayEl = document.getElementById('vip-price-display');
            const finalPriceEl = document.getElementById('vip-final-price');
            displayEl.style.display = 'block';
            if (activeCoupons['VIP']) {
                const discountAmount = VIP_PRICE * activeCoupons['VIP'].discount;
                const finalPrice = VIP_PRICE - discountAmount;
                finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(VIP_PRICE)}</span><br>${formatRupiah(finalPrice)}`;
            } else {
                finalPriceEl.textContent = formatRupiah(VIP_PRICE);
            }
        }
        function resetVipPriceDisplay() { document.getElementById('vip-price-display').style.display = 'none'; }
        function buyVip() {
            const idGame = document.getElementById('vip-id').value;
            if (!idGame) { alert("Mohon masukkan ID Game Anda!"); return; }
            let finalPrice = VIP_PRICE;
            let couponText = "";
            if (activeCoupons['VIP']) {
                finalPrice = VIP_PRICE - (VIP_PRICE * activeCoupons['VIP'].discount);
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons['VIP']).toUpperCase()} (${activeCoupons['VIP'].desc})\n`;
            }
            sendToWhatsApp("Fake Lag VIP", finalPrice, couponText, { idPlayer: idGame });
        }

        // --- LOGIKA AKUN ---
        function updateAccountPriceDisplay(sectionId) {
            let basePrice = 0;
            if(sectionId === 'ACC_FF') basePrice = 250000;
            if(sectionId === 'ACC_ML') basePrice = 190000;
            if(sectionId === 'ACC_PUBG') basePrice = 50000;

            const displayId = `acc-${sectionId.toLowerCase().replace('acc_', '')}-price-display`;
            const finalPriceId = `acc-${sectionId.toLowerCase().replace('acc_', '')}-final-price`;
            const displayEl = document.getElementById(displayId);
            const finalPriceEl = document.getElementById(finalPriceId);

            if(activeCoupons[sectionId]) {
                const discountAmount = basePrice * activeCoupons[sectionId].discount;
                const finalPrice = basePrice - discountAmount;
                displayEl.style.display = 'block';
                finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(basePrice)}</span><br>${formatRupiah(finalPrice)}`;
            } else {
                displayEl.style.display = 'none';
            }
        }
        function resetAccountPriceDisplay(sectionId) {
            document.getElementById(`acc-${sectionId.toLowerCase().replace('acc_', '')}-price-display`).style.display = 'none';
        }
        function buyAccount(itemName, basePrice, code, sectionId) {
            let finalPrice = basePrice;
            let couponText = "";
            if (activeCoupons[sectionId]) {
                finalPrice = basePrice - (basePrice * activeCoupons[sectionId].discount);
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons[sectionId]).toUpperCase()} (${activeCoupons[sectionId].desc})\n`;
            }
            sendToWhatsApp(itemName, finalPrice, couponText, { code: code });
        }

        // --- LOGIKA TOP UP (TERMASUK PUBG) ---
        function calculatePrice(game) {
            let diamond = 0;
            let price = 0;
            let displayId = "";
            let finalPriceId = "";

            if (game === 'FF') {
                diamond = document.getElementById('ff-diamond').value;
                displayId = "ff-price-display";
                finalPriceId = "ff-final-price";
                if (diamond > 0) price = (diamond / 10) * 5000; 
            } else if (game === 'ML') {
                diamond = document.getElementById('ml-diamond').value;
                displayId = "ml-price-display";
                finalPriceId = "ml-final-price";
                if (diamond > 0) price = (diamond / 10) * 5000;
            } else if (game === 'PUBG') {
                diamond = document.getElementById('pubg-diamond').value;
                displayId = "pubg-price-display";
                finalPriceId = "pubg-final-price";
                // Logika PUBG: 50 Diamond = 10.000 -> 1 Diamond = 200
                if (diamond > 0) price = diamond * 200;
            }

            const displayEl = document.getElementById(displayId);
            const finalPriceEl = document.getElementById(finalPriceId);
            
            if (diamond > 0) {
                displayEl.style.display = 'block';
                if (activeCoupons[game]) {
                    const discountAmount = price * activeCoupons[game].discount;
                    const finalPrice = price - discountAmount;
                    finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(price)}</span><br>${formatRupiah(finalPrice)}`;
                } else {
                    finalPriceEl.textContent = formatRupiah(price);
                }
            } else {
                displayEl.style.display = 'none';
            }
        }

        function orderTopUp(game) {
            let idPlayer = "";
            let diamond = 0;
            let basePrice = 0;
            let finalPrice = 0;
            let gameName = "";
            
            if (game === 'FF') {
                idPlayer = document.getElementById('ff-id').value;
                diamond = document.getElementById('ff-diamond').value;
                gameName = "Free Fire";
                if (!idPlayer || !diamond) { alert("Mohon isi ID Player dan Jumlah Diamond!"); return; }
                basePrice = (diamond / 10) * 5000;
            } else if (game === 'ML') {
                idPlayer = document.getElementById('ml-id').value;
                diamond = document.getElementById('ml-diamond').value;
                gameName = "Mobile Legends";
                if (!idPlayer || !diamond) { alert("Mohon isi User ID dan Jumlah Diamond!"); return; }
                basePrice = (diamond / 10) * 5000;
            } else if (game === 'PUBG') {
                idPlayer = document.getElementById('pubg-id').value;
                diamond = document.getElementById('pubg-diamond').value;
                gameName = "PUBG Mobile";
                if (!idPlayer || !diamond) { alert("Mohon isi ID Player dan Jumlah UC/Diamond!"); return; }
                basePrice = diamond * 200; // 1 Diamond = 200 Rupiah
            }

            if (activeCoupons[game]) {
                finalPrice = basePrice - (basePrice * activeCoupons[game].discount);
            } else {
                finalPrice = basePrice;
            }

            let couponText = "";
            if (activeCoupons[game]) {
                couponText = `🏷️ Kupon: ${Object.keys(coupons).find(key => coupons[key] === activeCoupons[game]).toUpperCase()} (${activeCoupons[game].desc})\n`;
            }

            sendToWhatsApp(`Top Up ${gameName}`, finalPrice, couponText, { idPlayer: idPlayer, diamond: diamond });
        }

        // --- FUNGSI KIRIM KE WHATSAPP ---
        function sendToWhatsApp(itemName, finalPrice, couponText, extraData) {
            let message = `Halo Admin, saya ingin melakukan pembelian.\n\n`;
            message += `📦 Item: ${itemName}\n`;
            
            if (extraData.idPlayer) message += `🆔 ID Player: ${extraData.idPlayer}\n`;
            if (extraData.diamond) message += `💎 Jumlah: ${extraData.diamond} Diamond/UC\n`;
            if (extraData.code) message += `🏷️ Kode Pembelian: ${extraData.code}\n`;
            if (extraData.type) message += `📂 Kategori: ${extraData.type}\n`;
            
            message += `${couponText}`;
            message += `💰 Total Harga: ${formatRupiah(finalPrice)}\n`;
            message += `💳 Metode: QRIS / Transfer\n\n`;
            message += `Mohon kirimkan QRIS untuk pembayaran. Terima kasih.`;

            const url = `https://wa.me/${waNumber}?text=${encodeURIComponent(message)}`;
            window.open(url, '_blank');
        }
    </script>
</body>
</html>
