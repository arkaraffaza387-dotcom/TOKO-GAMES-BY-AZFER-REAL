<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AZFER STORE - Top Up, Akun, Membership & APK</title>
    <style>
        :root {
            --primary: #6c5ce7;
            --secondary: #a29bfe;
            --bg-dark: #1e1e2e;
            --card-bg: #2d2d44;
            --text-light: #ffffff;
            --accent: #00cec9;
            --success: #00b894;
            --error: #d63031;
            --vip-gold: #fdcb6e;
            --vvip-red: #ff7675;
            --admin-black: #2d3436;
            --member-gradient: linear-gradient(135deg, #6c5ce7 0%, #a29bfe 100%);
            --vvip-gradient: linear-gradient(135deg, #d63031 0%, #ff7675 100%);
            --admin-gradient: linear-gradient(135deg, #000000 0%, #434343 100%); /* Tema Gelap Mewah */
            --apk-color: #ff7675;
            --netys-color: #00b894;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-light);
            line-height: 1.6;
        }

        /* Header */
        header {
            background: linear-gradient(135deg, var(--primary), var(--card-bg));
            padding: 2rem;
            text-align: center;
            box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        }

        header h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            letter-spacing: 2px;
        }

        header p {
            color: var(--secondary);
        }

        /* Container */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Section Titles */
        .section-title {
            text-align: center;
            margin: 3rem 0 1.5rem;
            font-size: 1.8rem;
            border-bottom: 2px solid var(--primary);
            display: inline-block;
            padding-bottom: 5px;
        }

        .center-wrap {
            text-align: center;
        }

        /* Grid Layout */
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
        }

        /* Cards */
        .card {
            background-color: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            border: 1px solid rgba(255,255,255,0.1);
            position: relative;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(108, 92, 231, 0.2);
        }

        .card-header {
            padding: 15px;
            background: rgba(0,0,0,0.2);
            text-align: center;
            font-weight: bold;
            font-size: 1.2rem;
        }

        .ff-theme { border-top: 4px solid #ff9f43; }
        .ml-theme { border-top: 4px solid #0984e3; }
        .pubg-theme { border-top: 4px solid #fdcb6e; }
        .vip-theme { border-top: 4px solid var(--vip-gold); }
        .member-theme { border-top: 4px solid var(--primary); background: var(--member-gradient); }
        .vvip-theme { border-top: 4px solid var(--vvip-red); background: var(--vvip-gradient); }
        .admin-theme { border-top: 4px solid #fff; background: var(--admin-gradient); } /* Tema Admin */
        .apk-theme { border-top: 4px solid var(--apk-color); }
        .netys-theme { border-top: 4px solid var(--netys-color); }

        .card-body {
            padding: 20px;
        }

        .price-tag {
            font-size: 1.5rem;
            color: var(--accent);
            font-weight: bold;
            margin: 10px 0;
        }

        .stock-badge {
            background-color: #e17055;
            color: white;
            padding: 2px 8px;
            border-radius: 4px;
            font-size: 0.8rem;
            float: right;
        }

        .code-info {
            background: rgba(255,255,255,0.1);
            padding: 10px;
            border-radius: 8px;
            margin: 15px 0;
            font-family: monospace;
            text-align: center;
            border: 1px dashed var(--secondary);
        }

        /* Forms */
        .form-group {
            margin-bottom: 15px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            font-size: 0.9rem;
            color: #ccc;
        }

        input, select {
            width: 100%;
            padding: 10px;
            border-radius: 8px;
            border: none;
            background-color: #1e1e2e;
            color: white;
            border: 1px solid #444;
        }

        input:focus, select:focus {
            outline: none;
            border-color: var(--primary);
        }

        /* Coupon Specific Styles */
        .coupon-container {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }

        .btn-check-coupon {
            background-color: var(--secondary);
            color: #fff;
            border: none;
            padding: 0 15px;
            border-radius: 8px;
            cursor: pointer;
            font-weight: bold;
        }

        .btn-check-coupon:hover {
            background-color: var(--primary);
        }

        .coupon-message {
            font-size: 0.85rem;
            margin-top: 5px;
            min-height: 20px;
        }

        .coupon-valid { color: var(--success); }
        .coupon-invalid { color: var(--error); }

        .final-price {
            background: rgba(0, 206, 201, 0.1);
            padding: 10px;
            border-radius: 8px;
            margin-top: 15px;
            text-align: center;
            border: 1px solid var(--accent);
        }

        .original-price {
            text-decoration: line-through;
            color: #aaa;
            font-size: 0.9rem;
        }

        .discounted-price {
            color: var(--success);
            font-weight: bold;
            font-size: 1.2rem;
        }

        /* Buttons */
        .btn {
            display: block;
            width: 100%;
            padding: 12px;
            border: none;
            border-radius: 8px;
            background-color: var(--primary);
            color: white;
            font-size: 1rem;
            cursor: pointer;
            transition: background 0.3s;
            text-decoration: none;
            text-align: center;
            margin-top: 15px;
        }

        .btn:hover {
            background-color: var(--secondary);
        }

        .btn-buy-account {
            background-color: #00b894;
        }
        
        .btn-buy-account:hover {
            background-color: #55efc4;
        }

        .btn-vip {
            background-color: var(--vip-gold);
            color: #000;
            font-weight: bold;
        }
        
        .btn-vip:hover {
            background-color: #e1b12c;
        }

        .btn-member {
            background-color: #fff;
            color: var(--primary);
            font-weight: bold;
        }
        
        .btn-member:hover {
            background-color: #f0f0f0;
        }

        .btn-vvip {
            background-color: #fff;
            color: var(--vvip-red);
            font-weight: bold;
        }
        
        .btn-vvip:hover {
            background-color: #ffeaa7;
        }

        .btn-admin {
            background-color: #fff;
            color: #000;
            font-weight: bold;
            border: 2px solid #fff;
        }
        
        .btn-admin:hover {
            background-color: #000;
            color: #fff;
        }

        .btn-apk {
            background-color: var(--apk-color);
            color: white;
        }
        
        .btn-apk:hover {
            background-color: #ff5252;
        }

        .btn-netys {
            background-color: var(--netys-color);
            color: white;
        }
        
        .btn-netys:hover {
            background-color: #00a383;
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            margin-top: 3rem;
            background-color: var(--card-bg);
            color: #aaa;
        }

        /* Responsive adjustments */
        @media (max-width: 600px) {
            header h1 { font-size: 1.8rem; }
        }
    </style>
</head>
<body>

    <header>
        <h1>AZFER STORE</h1>
        <p>Solusi Top Up, Jual Akun, Membership & APK Premium</p>
    </header>

    <div class="container">
        
        <!-- BAGIAN 0: MEMBERSHIP -->
        <div class="center-wrap">
            <h2 class="section-title">👑 Membership & Hemat</h2>
        </div>

        <div class="grid">
            <!-- Membership Kelas 1 -->
            <div class="card member-theme">
                <div class="card-header" style="color: white;">MEMBERSHIP KELAS 1</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #eee; text-align: center;">Dapatkan akses eksklusif dan diskon hingga 37% untuk semua transaksi!</p>
                    
                    <div class="price-tag" style="text-align: center; color: white;">Rp 135.000 <span style="font-size:0.8rem; display:block; font-weight:normal;">(Bayar Sebulan Sekali)</span></div>
                    
                    <ul style="margin-left: 20px; margin-bottom: 15px; font-size: 0.9rem; color: #eee;">
                        <li>✅ Prioritas Pelayanan</li>
                        <li>✅ Akses Kupon Super Diskon</li>
                        <li>✅ Bonus Diamond (Event Tertentu)</li>
                    </ul>

                    <!-- Kode disembunyikan -->
                    <div class="code-info" style="border-color: white; color: white;">KODE: ****** (Beli Membership untuk Dapatkan Kode)</div>
                    <p style="font-size: 0.8rem; text-align: center; margin-bottom: 10px; color: #ffd700;">Setelah pembayaran, admin akan mengirimkan kode kupon rahasia ini kepada Anda.</p>

                    <!-- Fitur Kupon Member -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="member-coupon" placeholder="Masukkan Kode Rahasia">
                            <button onclick="checkCoupon('MEMBER')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="member-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="member-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="member-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyMembership()" class="btn btn-member">Beli Membership Sekarang</button>
                </div>
            </div>

            <!-- Membership VVIP -->
            <div class="card vvip-theme">
                <div class="card-header" style="color: white;">MEMBERSHIP VVIP 👑</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #eee; text-align: center;">Status tertinggi! Diskon gila-gilaan hingga 49% untuk semua transaksi!</p>
                    
                    <div class="price-tag" style="text-align: center; color: white;">Rp 250.000 <span style="font-size:0.8rem; display:block; font-weight:normal;">(Bayar Sebulan Sekali)</span></div>
                    
                    <ul style="margin-left: 20px; margin-bottom: 15px; font-size: 0.9rem; color: #eee;">
                        <li>✅ Prioritas Utama (Fast Response)</li>
                        <li>✅ Akses Kupon VVIP Diskon 49%</li>
                        <li>✅ Gratis Ongkir Admin (Jika Ada)</li>
                    </ul>

                    <!-- Kode disembunyikan -->
                    <div class="code-info" style="border-color: white; color: white;">KODE: ****** (Beli VVIP untuk Dapatkan Kode)</div>
                    <p style="font-size: 0.8rem; text-align: center; margin-bottom: 10px; color: #ffd700;">Setelah pembayaran, admin akan mengirimkan kode kupon rahasia ini kepada Anda.</p>

                    <!-- Fitur Kupon VVIP -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="vvip-coupon" placeholder="Masukkan Kode Rahasia VVIP">
                            <button onclick="checkCoupon('VVIP')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="vvip-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="vvip-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="vvip-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyVvip()" class="btn btn-vvip">Beli VVIP Sekarang</button>
                </div>
            </div>

            <!-- ADMIN VVIP BARU -->
            <div class="card admin-theme">
                <div class="card-header" style="color: white; text-transform: uppercase; letter-spacing: 1px;">ADMIN VVIP 💻</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc; text-align: center;">Akses penuh ke sistem website AZFER STORE.</p>
                    
                    <div class="price-tag" style="text-align: center; color: #fff;">Rp 5.000.000</div>
                    
                    <ul style="margin-left: 20px; margin-bottom: 15px; font-size: 0.9rem; color: #ddd;">
                        <li>✅ PROMO 100% (Gunakan Kupon)</li>
                        <li>✅ DAPET AKSES WEB</li>
                        <li>✅ DAPET AKSES ADMIN WEB</li>
                        <li>✅ DAPAT AKSES CODE CSS, HTML, JS WEB</li>
                    </ul>

                    <!-- Kode disembunyikan -->
                    <div class="code-info" style="border-color: #fff; color: #fff; border-style: solid;">KODE: ****** (Hubungi Admin Langsung)</div>
                    <p style="font-size: 0.8rem; text-align: center; margin-bottom: 10px; color: #fab1a0;">Item Eksklusif. Gunakan kupon khusus jika ada.</p>

                    <!-- Fitur Kupon Admin -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="admin-coupon" placeholder="Masukkan Kode Admin">
                            <button onclick="checkCoupon('ADMIN')" class="btn-check-coupon" style="background-color: #fff; color: #000;">Cek</button>
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

        <!-- BAGIAN BARU: TOKO APK PREMIUM -->
        <div class="center-wrap">
            <h2 class="section-title">📱 Toko APK Premium</h2>
        </div>

        <div class="grid">
            <!-- GTA SA -->
            <div class="card apk-theme">
                <div class="card-header">GTA SAN ANDREAS</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc;">Game open world legendaris dengan grafis HD dan kontrol yang disempurnakan.</p>
                    <div class="price-tag">Rp 137.000</div>
                    
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="apk-gta-sa-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('APK_GTA_SA')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-gta-sa-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-gta-sa-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="apk-gta-sa-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyApk('GTA SAN ANDREAS', 137000, 'APK_GTA_SA')" class="btn btn-apk">Beli APK</button>
                </div>
            </div>

            <!-- GTA VICE CITY -->
            <div class="card apk-theme">
                <div class="card-header">GTA VICE CITY</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc;">Kembali ke era 80-an dengan aksi kriminal di kota Vice City yang penuh gaya.</p>
                    <div class="price-tag">Rp 147.000</div>
                    
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="apk-gta-vc-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('APK_GTA_VC')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-gta-vc-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-gta-vc-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="apk-gta-vc-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyApk('GTA VICE CITY', 147000, 'APK_GTA_VC')" class="btn btn-apk">Beli APK</button>
                </div>
            </div>

            <!-- POPPY PLAYTIME -->
            <div class="card apk-theme">
                <div class="card-header">POPPY PLAYTIME 1-5</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc;">Bundle lengkap Chapter 1 sampai 5. Horror puzzle yang menegangkan!</p>
                    <div class="price-tag">Rp 200.000</div>
                    
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="apk-poppy-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('APK_POPPY')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-poppy-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-poppy-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="apk-poppy-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyApk('POPPY PLAYTIME 1-5', 200000, 'APK_POPPY')" class="btn btn-apk">Beli Bundle</button>
                </div>
            </div>

            <!-- GTA SA CHEAT -->
            <div class="card apk-theme">
                <div class="card-header">GTA SA CHEAT UNLI MONEY</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc;">Versi modifikasi GTA SA dengan fitur Uang Tak Terbatas sejak awal permainan.</p>
                    <div class="price-tag">Rp 138.000</div>
                    
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="apk-gta-cheat-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('APK_GTA_CHEAT')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-gta-cheat-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-gta-cheat-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="apk-gta-cheat-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyApk('GTA SA CHEAT UNLI MONEY', 138000, 'APK_GTA_CHEAT')" class="btn btn-apk">Beli Mod APK</button>
                </div>
            </div>

            <!-- ROBLOX DELTA -->
            <div class="card apk-theme">
                <div class="card-header">ROBLOX DELTA</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc;">Executor/Script hub terbaik untuk Roblox Mobile. Jalankan script dengan mudah.</p>
                    <div class="price-tag">Rp 20.000</div>
                    
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="apk-delta-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('APK_DELTA')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="apk-delta-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="apk-delta-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="apk-delta-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyApk('ROBLOX DELTA', 20000, 'APK_DELTA')" class="btn btn-apk">Beli Executor</button>
                </div>
            </div>
        </div>

        <!-- BAGIAN 1: TOP UP DIAMOND -->
        <div class="center-wrap">
            <h2 class="section-title">⚡ Top Up Harian</h2>
        </div>
        
        <div class="grid">
            <!-- Free Fire Topup -->
            <div class="card ff-theme">
                <div class="card-header">FREE FIRE (Top Up)</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc;">Harga per 10 Diamond = Rp 5.000</p>
                    <div class="form-group" style="margin-top: 15px;">
                        <label>Masukkan ID Player</label>
                        <input type="number" id="ff-id" placeholder="Contoh: 123456789">
                    </div>
                    <div class="form-group">
                        <label>Jumlah Diamond (Kelipatan 10)</label>
                        <input type="number" id="ff-diamond" placeholder="Min. 10" min="10" step="10" oninput="calculatePrice('FF')">
                    </div>
                    
                    <!-- Fitur Kupon -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="ff-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('FF')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="ff-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="ff-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="ff-final-price">Rp 0</div>
                    </div>

                    <button onclick="orderTopUp('FF')" class="btn">Beli Sekarang</button>
                </div>
            </div>

            <!-- Mobile Legends Topup -->
            <div class="card ml-theme">
                <div class="card-header">MOBILE LEGENDS (Top Up)</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc;">Harga per 10 Diamond = Rp 5.000</p>
                    <div class="form-group" style="margin-top: 15px;">
                        <label>User ID & Zone ID</label>
                        <input type="text" id="ml-id" placeholder="Contoh: 12345678 (1234)">
                    </div>
                    <div class="form-group">
                        <label>Jumlah Diamond (Kelipatan 10)</label>
                        <input type="number" id="ml-diamond" placeholder="Min. 10" min="10" step="10" oninput="calculatePrice('ML')">
                    </div>

                    <!-- Fitur Kupon -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="ml-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('ML')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="ml-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="ml-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="ml-final-price">Rp 0</div>
                    </div>

                    <button onclick="orderTopUp('ML')" class="btn">Beli Sekarang</button>
                </div>
            </div>

            <!-- PUBG Info -->
            <div class="card pubg-theme">
                <div class="card-header">PUBG MOBILE</div>
                <div class="card-body" style="text-align: center;">
                    <div style="padding: 20px 0;">
                        <svg xmlns="http://www.w3.org/2000/svg" width="50" height="50" viewBox="0 0 24 24" fill="none" stroke="#fab1a0" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="10"></circle><line x1="4.93" y1="4.93" x2="19.07" y2="19.07"></line></svg>
                        <h3 style="margin-top: 10px; color: #fab1a0;">Layanan Tidak Tersedia</h3>
                        <p style="margin-top: 10px; font-size: 0.9rem;">Maaf, layanan Top Up untuk PUBG Mobile saat ini belum bisa dilakukan.</p>
                    </div>
                </div>
            </div>
        </div>

        <!-- BAGIAN BARU: LAYANAN KHUSUS (FAKE LAG & KEY NETYS) -->
        <div class="center-wrap">
            <h2 class="section-title">🚀 Layanan Khusus</h2>
        </div>

        <div class="grid">
            <!-- Fake Lag VIP -->
            <div class="card vip-theme">
                <div class="card-header" style="color: var(--vip-gold);">FAKE LAG VIP 👑</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc; text-align: center;">Aktifkan Fake Lag untuk pengalaman bermain yang lebih smooth & anti-lag!</p>
                    
                    <div class="price-tag" style="text-align: center; color: var(--vip-gold);">Rp 15.000</div>
                    
                    <div class="form-group" style="margin-top: 15px;">
                        <label>ID Game (FF/ML/PUBG)</label>
                        <input type="text" id="vip-id" placeholder="Masukkan ID Game Anda">
                    </div>

                    <!-- Fitur Kupon -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="vip-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('VIP')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="vip-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="vip-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="vip-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyVip()" class="btn btn-vip">Beli Fake Lag VIP</button>
                </div>
            </div>

            <!-- KEY NETYS -->
            <div class="card netys-theme">
                <div class="card-header" style="color: var(--netys-color);">KEY NETYS 🔑</div>
                <div class="card-body">
                    <p style="font-size: 0.9rem; color: #ccc; text-align: center;">Akses premium aplikasi Netys dengan garansi panjang.</p>
                    
                    <div class="price-tag" style="text-align: center; color: var(--netys-color);">Rp 5.000</div>
                    
                    <ul style="margin-left: 20px; margin-bottom: 15px; font-size: 0.9rem; color: #ddd;">
                        <li>✅ BERLAKU SELAMANYA</li>
                        <li>✅ GARANSI 1 TAHUN</li>
                        <li>✅ MENDAPATKAN APK NETYS</li>
                    </ul>

                    <!-- Fitur Kupon -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="netys-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('NETYS')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="netys-coupon-msg" class="coupon-message"></div>
                    </div>

                    <div id="netys-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="netys-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyNetys()" class="btn btn-netys">Beli Key Netys</button>
                </div>
            </div>
        </div>


        <!-- BAGIAN 2: JUAL AKUN PREMIUM -->
        <div class="center-wrap">
            <h2 class="section-title">💎 Jual Akun Premium (Ready Stock)</h2>
        </div>

        <div class="grid">
            <!-- Akun FF -->
            <div class="card ff-theme">
                <div class="card-header">AKUN SULTAN FF <span class="stock-badge">Stok: 1</span></div>
                <div class="card-body">
                    <ul style="margin-left: 20px; margin-bottom: 15px; font-size: 0.9rem; color: #ddd;">
                        <li>Full Skin Legend</li>
                        <li>Level Max</li>
                        <li>Win Rate Tinggi</li>
                    </ul>
                    <div class="price-tag">Rp 250.000</div>
                    <div class="code-info">KODE: AZFER.FF</div>
                    
                    <!-- Fitur Kupon Akun -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="acc-ff-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('ACC_FF')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="acc-ff-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="acc-ff-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="acc-ff-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyAccount('AKUN FF', 250000, 'AZFER.FF', 'ACC_FF')" class="btn btn-buy-account">Beli Akun Ini</button>
                </div>
            </div>

            <!-- Akun ML -->
            <div class="card ml-theme">
                <div class="card-header">AKUN MYTHIC ML <span class="stock-badge">Stok: 1</span></div>
                <div class="card-body">
                    <ul style="margin-left: 20px; margin-bottom: 15px; font-size: 0.9rem; color: #ddd;">
                        <li>Skin Collector/Legend</li>
                        <li>Emblem Max</li>
                        <li>Winrate Bagus</li>
                    </ul>
                    <div class="price-tag">Rp 190.000</div>
                    <div class="code-info">KODE: AZFEF.ML</div>

                    <!-- Fitur Kupon Akun -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="acc-ml-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('ACC_ML')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="acc-ml-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="acc-ml-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="acc-ml-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyAccount('AKUN ML', 190000, 'AZFEF.ML', 'ACC_ML')" class="btn btn-buy-account">Beli Akun Ini</button>
                </div>
            </div>

            <!-- Akun PUBG -->
            <div class="card pubg-theme">
                <div class="card-header">AKUN VETERAN PUBG <span class="stock-badge">Stok: 1</span></div>
                <div class="card-body">
                    <ul style="margin-left: 20px; margin-bottom: 15px; font-size: 0.9rem; color: #ddd;">
                        <li>Outfit Mythic</li>
                        <li>Senjata Upgrade</li>
                        <li>Akun Aman</li>
                    </ul>
                    <div class="price-tag">Rp 50.000</div>
                    <div class="code-info">KODE: AZFER.PUBG</div>

                    <!-- Fitur Kupon Akun -->
                    <div class="form-group">
                        <label>Kode Promo / Kupon</label>
                        <div class="coupon-container">
                            <input type="text" id="acc-pubg-coupon" placeholder="Masukkan Kode">
                            <button onclick="checkCoupon('ACC_PUBG')" class="btn-check-coupon">Cek</button>
                        </div>
                        <div id="acc-pubg-coupon-msg" class="coupon-message"></div>
                    </div>
                    <div id="acc-pubg-price-display" class="final-price" style="display:none;">
                        <div>Total Bayar:</div>
                        <div class="discounted-price" id="acc-pubg-final-price">Rp 0</div>
                    </div>

                    <button onclick="buyAccount('AKUN PUBG', 50000, 'AZFER.PUBG', 'ACC_PUBG')" class="btn btn-buy-account">Beli Akun Ini</button>
                </div>
            </div>
        </div>

    </div>

    <footer>
        <p>&copy; 2026 AZFER STORE. All Rights Reserved.</p>
        <p>Pembayaran via QRIS (Scan Chat WhatsApp)</p>
    </footer>

    <script>
        const waNumber = "6285882382854"; 
        
        // --- DAFTAR KUPON TERSEDIA ---
        const coupons = {
            "ADMIN_AZFER2013": { discount: 1.00, desc: "Diskon Admin 100% (GRATIS)" }, // Kupon Admin Baru
            "MEMBER_VVIP2013": { discount: 0.49, desc: "Diskon VVIP 49%" }, 
            "MEMBER_SHIP1": { discount: 0.37, desc: "Diskon Member 37%" }, 
            "TOKO.ID": { discount: 0.25, desc: "Diskon 25%" },
            "AZFERPROMO": { discount: 0.10, desc: "Diskon 10%" },
            "NEWUSER": { discount: 0.05, desc: "Diskon 5%" },
            "MERDEKA": { discount: 0.17, desc: "Diskon 17%" }
        };

        let activeCoupons = {
            'FF': null, 'ML': null, 'VIP': null, 
            'ACC_FF': null, 'ACC_ML': null, 'ACC_PUBG': null,
            'MEMBER': null,
            'VVIP': null,
            'ADMIN': null, // Tambahan untuk Admin
            'NETYS': null,
            // Tambahan untuk APK
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
            else if (sectionId === 'VIP') { inputId = 'vip-coupon'; msgId = 'vip-coupon-msg'; }
            else if (sectionId === 'MEMBER') { inputId = 'member-coupon'; msgId = 'member-coupon-msg'; }
            else if (sectionId === 'VVIP') { inputId = 'vvip-coupon'; msgId = 'vvip-coupon-msg'; }
            else if (sectionId === 'ADMIN') { inputId = 'admin-coupon'; msgId = 'admin-coupon-msg'; }
            else if (sectionId === 'NETYS') { inputId = 'netys-coupon'; msgId = 'netys-coupon-msg'; }
            else if (sectionId.startsWith('APK_')) {
                // Logika dinamis untuk APK
                const shortName = sectionId.replace('APK_', '').toLowerCase();
                inputId = `apk-${shortName}-coupon`;
                msgId = `apk-${shortName}-coupon-msg`;
            }
            else {
                // Logika untuk Akun
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
                
                // Panggil fungsi update harga yang sesuai
                if(sectionId === 'FF' || sectionId === 'ML') calculatePrice(sectionId);
                else if (sectionId === 'VIP') calculateVipPrice();
                else if (sectionId === 'MEMBER') calculateMemberPrice();
                else if (sectionId === 'VVIP') calculateVvipPrice();
                else if (sectionId === 'ADMIN') calculateAdminPrice();
                else if (sectionId === 'NETYS') calculateNetysPrice();
                else if (sectionId.startsWith('APK_')) calculateApkPrice(sectionId);
                else updateAccountPriceDisplay(sectionId);
            } else {
                activeCoupons[sectionId] = null;
                msgElement.textContent = "Kode tidak valid atau kedaluwarsa.";
                msgElement.className = "coupon-message coupon-invalid";
                
                if(sectionId === 'FF' || sectionId === 'ML') calculatePrice(sectionId);
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
        const ADMIN_PRICE = 5000000; // Harga contoh 5 Juta

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

        function resetAdminPriceDisplay() {
            document.getElementById('admin-price-display').style.display = 'none';
        }

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

        function resetNetysPriceDisplay() {
            document.getElementById('netys-price-display').style.display = 'none';
        }

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

        function resetVvipPriceDisplay() {
            document.getElementById('vvip-price-display').style.display = 'none';
        }

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

        function resetMemberPriceDisplay() {
            document.getElementById('member-price-display').style.display = 'none';
        }

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

        function resetVipPriceDisplay() {
            document.getElementById('vip-price-display').style.display = 'none';
        }

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

        // --- LOGIKA TOP UP ---
        function calculatePrice(game) {
            let diamond = 0;
            let price = 0;
            let displayId = "";
            let finalPriceId = "";

            if (game === 'FF') {
                diamond = document.getElementById('ff-diamond').value;
                displayId = "ff-price-display";
                finalPriceId = "ff-final-price";
            } else if (game === 'ML') {
                diamond = document.getElementById('ml-diamond').value;
                displayId = "ml-price-display";
                finalPriceId = "ml-final-price";
            }

            if (diamond > 0) {
                price = (diamond / 10) * 5000; 
                const displayEl = document.getElementById(displayId);
                const finalPriceEl = document.getElementById(finalPriceId);
                displayEl.style.display = 'block';

                if (activeCoupons[game]) {
                    const discountAmount = price * activeCoupons[game].discount;
                    const finalPrice = price - discountAmount;
                    finalPriceEl.innerHTML = `<span class="original-price">${formatRupiah(price)}</span><br>${formatRupiah(finalPrice)}`;
                } else {
                    finalPriceEl.textContent = formatRupiah(price);
                }
            } else {
                document.getElementById(displayId).style.display = 'none';
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
            
            // Tambahkan detail spesifik
            if (extraData.idPlayer) message += `🆔 ID Player: ${extraData.idPlayer}\n`;
            if (extraData.diamond) message += `💎 Jumlah: ${extraData.diamond} Diamond\n`;
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
