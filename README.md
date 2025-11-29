<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Triamudom Smart Canteen</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #ff6b9d 0%, #ffa500 100%);
            min-height: 100vh;
            padding: 20px;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            background: white;
            border-radius: 20px;
            box-shadow: 0 20px 60px rgba(0,0,0,0.3);
            overflow: hidden;
        }

        .header {
            background: linear-gradient(135deg, #ff6b9d 0%, #ffa500 100%);
            color: #1e3a8a;
            padding: 30px;
            text-align: center;
            position: relative;
        }

        .school-logo {
            position: absolute;
            left: 20px;
            top: 50%;
            transform: translateY(-50%);
            width: 60px;
            height: auto;
        }

        .header h1 {
            font-size: 2.5em;
            margin-bottom: 10px;
        }

        .header p {
            opacity: 0.9;
        }

        .content {
            padding: 30px;
        }

        .page {
            display: none;
        }

        .page.active {
            display: block;
        }

        .form-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #333;
        }

        input, select, textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 8px;
            font-size: 16px;
            transition: border-color 0.3s;
        }

        input:focus, select:focus, textarea:focus {
            outline: none;
            border-color: #ff6b9d;
        }

        .btn {
            background: linear-gradient(135deg, #ff6b9d 0%, #ffa500 100%);
            color: white;
            padding: 15px 30px;
            border: none;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            width: 100%;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(255, 107, 157, 0.6);
        }

        .btn:active {
            transform: translateY(0);
        }

        .btn-secondary {
            background: #6c757d;
            margin-top: 10px;
        }

        .btn-group {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }

        .btn-group button {
            flex: 1;
        }

        .product-item {
            background: #f8f9fa;
            padding: 15px;
            border-radius: 8px;
            margin-bottom: 15px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .product-info {
            flex: 1;
        }

        .product-info h3 {
            color: #333;
            margin-bottom: 5px;
        }

        .product-info p {
            color: #666;
            font-size: 14px;
        }

        .product-price {
            font-size: 1.5em;
            font-weight: bold;
            color: #ff8c00;
        }

        #orderSummary {
            background: #f8f9fa;
            padding: 20px;
            border-radius: 8px;
            margin-top: 20px;
        }

        .summary-item {
            display: flex;
            justify-content: space-between;
            padding: 10px 0;
            border-bottom: 1px solid #e0e0e0;
        }

        .summary-total {
            font-size: 1.3em;
            font-weight: bold;
            color: #ff8c00;
            margin-top: 10px;
        }

        .success-message {
            text-align: center;
            padding: 40px;
        }

        .success-icon {
            font-size: 4em;
            color: #28a745;
            margin-bottom: 20px;
        }

        .loading {
            display: none;
            text-align: center;
            padding: 20px;
        }

        .spinner {
            border: 4px solid #f3f3f3;
            border-top: 4px solid #ff6b9d;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto;
        }

        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }

        .nav-buttons {
            display: flex;
            gap: 10px;
            margin-top: 20px;
        }

        .error-message {
            background: #f8d7da;
            color: #721c24;
            padding: 10px;
            border-radius: 8px;
            margin-top: 10px;
            display: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <img src="prakao.png" alt="พระเกี้ยวโรงเรียนเตรียมอุดมศึกษา" class="school-logo">
            <h1>🍽️ Triamudom Smart Canteen</h1>
            <p>ระบบสั่งอาหารออนไลน์ โรงเรียนเตรียมอุดมศึกษา</p>
        </div>

        <div class="content">
            <!-- Page 1: Dashboard/Home -->
            <div id="page-home" class="page active">
                <h2 style="margin-bottom: 20px;">🎉 ยินดีต้อนรับ! เริ่มต้นการสั่งอาหารของคุณ 🎉</h2>
                <p style="margin-bottom: 20px; color: #666; text-align: center; font-size: 2em;">
                    🍜 🍛 🍕 🍔 🍱 🥗 🍰 🧋
                </p>
                <p style="margin-bottom: 30px; color: #666;">
                    เลือกเมนูอาหารที่คุณต้องการและทำการชำระเงินผ่านระบบออนไลน์
                </p>
                
                <div class="form-group">
                    <label for="canteenLocation">📍 เลือกโรงอาหาร</label>
                    <select id="canteenLocation">
                        <option value="">-- เลือกโรงอาหาร --</option>
                        <option value="โรงใหญ่">🏢 โรงใหญ่</option>
                        <option value="โดมทอง">⭐ โดมทอง</option>
                    </select>
                </div>

                <button class="btn" onclick="goToPage('add-product')">
                    🛒 เริ่มสั่งอาหาร
                </button>
            </div>

            <!-- Page 2: Add Product -->
            <div id="page-add-product" class="page">
                <h2 style="margin-bottom: 20px;">📝 เพิ่มรายการอาหาร 🍴</h2>
                
                <div class="form-group">
                    <label for="shopName">🏪 ชื่อร้านอาหาร</label>
                    <select id="shopName">
                        <option value="">-- เลือกร้านอาหาร --</option>
                        <option value="ร้านข้าวมันไก่">🍗 ร้านข้าวมันไก่</option>
                        <option value="ร้านก่วยเตี๋ยว">🍜 ร้านก่วยเตี๋ยว</option>
                        <option value="ร้านอาหารตามสั่ง">🍳 ร้านอาหารตามสั่ง</option>
                        <option value="ร้านเครื่องดื่ม">🧋 ร้านเครื่องดื่ม</option>
                        <option value="ร้านข้าวราดแกง">🍛 ร้านข้าวราดแกง</option>
                        <option value="ร้านอาหารญี่ปุ่น">🍱 ร้านอาหารญี่ปุ่น</option>
                        <option value="ร้านสเต็ก">🥩 ร้านสเต็ก</option>
                        <option value="ร้านขนมหวาน">🍰 ร้านขนมหวาน</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="productName">🍽️ ชื่ออาหาร</label>
                    <input type="text" id="productName" placeholder="ระบุชื่ออาหาร">
                </div>

                <div class="form-group">
                    <label for="productCategory">🏷️ ประเภทอาหาร</label>
                    <select id="productCategory">
                        <option value="">-- เลือกประเภท --</option>
                        <option value="ข้าวราด">🍛 ข้าวราด</option>
                        <option value="ก่วยเตี๋ยว">🍜 ก่วยเตี๋ยว</option>
                        <option value="อาหารตามสั่ง">🍳 อาหารตามสั่ง</option>
                        <option value="เครื่องดื่ม">🧋 เครื่องดื่ม</option>
                        <option value="ของหวาน">🍰 ของหวาน</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="productPrice">💰 ราคา (บาท)</label>
                    <input type="number" id="productPrice" placeholder="0.00" step="0.01">
                </div>

                <div class="form-group">
                    <label for="productDescription">📋 รายละเอียด</label>
                    <textarea id="productDescription" rows="3" placeholder="รายละเอียดเพิ่มเติม"></textarea>
                </div>

                <div id="errorMessage" class="error-message"></div>
                <div id="loading" class="loading">
                    <div class="spinner"></div>
                    <p style="margin-top: 10px;">กำลังบันทึกข้อมูล...</p>
                </div>

                <div class="nav-buttons">
                    <button class="btn btn-secondary" onclick="goToPage('home')">กลับ</button>
                    <button class="btn" onclick="addProduct()">เพิ่มรายการ</button>
                </div>
                <button class="btn" onclick="goToPage('payment')" style="margin-top: 10px;">
                    ไปหน้าชำระเงิน
                </button>
            </div>

            <!-- Page 3: Payment Page -->
            <div id="page-payment" class="page">
                <h2 style="margin-bottom: 20px;">💳 ชำระเงิน 💵</h2>
                
                <div class="form-group">
                    <label for="customerName">👤 ชื่อ-นามสกุล</label>
                    <input type="text" id="customerName" placeholder="ระบุชื่อ-นามสกุล">
                </div>

                <div class="form-group">
                    <label for="tableNumber">🪑 หมายเลขโต๊ะ</label>
                    <input type="text" id="tableNumber" placeholder="ระบุหมายเลขโต๊ะ">
                </div>

                <div class="form-group">
                    <label for="paymentMethod">💰 วิธีการชำระเงิน</label>
                    <select id="paymentMethod">
                        <option value="">-- เลือกวิธีการชำระเงิน --</option>
                        <option value="เงินสด">💵 เงินสด</option>
                        <option value="โอนเงิน">📱 โอนเงิน</option>
                        <option value="บัตรเครดิต">💳 บัตรเครดิต</option>
                    </select>
                </div>

                <div id="orderSummary">
                    <h3 style="margin-bottom: 15px;">📝 สรุปรายการสั่งซื้อ</h3>
                    <div id="summaryItems"></div>
                    <div class="summary-item summary-total">
                        <span>ยอดรวมทั้งหมด</span>
                        <span id="totalAmount">0.00 บาท</span>
                    </div>
                </div>

                <div id="paymentError" class="error-message"></div>
                <div id="paymentLoading" class="loading">
                    <div class="spinner"></div>
                    <p style="margin-top: 10px;">กำลังดำเนินการชำระเงิน...</p>
                </div>

                <div class="nav-buttons">
                    <button class="btn btn-secondary" onclick="goToPage('add-product')">กลับ</button>
                    <button class="btn" onclick="processPayment()">ยืนยันการชำระเงิน</button>
                </div>
                <button class="btn" onclick="goToPage('sales-report')" style="margin-top: 10px;">
                    ดูรายงานยอดขาย
                </button>
            </div>

            <!-- Page 4: Sales Report -->
            <div id="page-sales-report" class="page">
                <h2 style="margin-bottom: 20px;">📊 รายงานยอดขาย 📈</h2>
                
                <div class="form-group">
                    <label for="reportDate">📅 วันที่ต้องการดูรายงาน</label>
                    <input type="date" id="reportDate">
                </div>

                <div class="form-group">
                    <label for="reportCategory">🏷️ ประเภทอาหาร</label>
                    <select id="reportCategory">
                        <option value="ทั้งหมด">📋 ทั้งหมด</option>
                        <option value="ข้าวราด">🍛 ข้าวราด</option>
                        <option value="ก่วยเตี๋ยว">🍜 ก่วยเตี๋ยว</option>
                        <option value="อาหารตามสั่ง">🍳 อาหารตามสั่ง</option>
                        <option value="เครื่องดื่ม">🧋 เครื่องดื่ม</option>
                        <option value="ของหวาน">🍰 ของหวาน</option>
                    </select>
                </div>

                <div id="reportSummary" style="background: #f8f9fa; padding: 20px; border-radius: 8px; margin-top: 20px; display: none;">
                    <h3 style="margin-bottom: 15px;">📊 สรุปยอดขาย</h3>
                    <div class="summary-item">
                        <span>จำนวนรายการ</span>
                        <span id="reportCount">0</span>
                    </div>
                    <div class="summary-item">
                        <span>ยอดขายรวม</span>
                        <span id="reportTotal">0.00 บาท</span>
                    </div>
                </div>

                <div id="reportError" class="error-message"></div>
                <div id="reportLoading" class="loading">
                    <div class="spinner"></div>
                    <p style="margin-top: 10px;">กำลังโหลดรายงาน...</p>
                </div>

                <div class="nav-buttons">
                    <button class="btn btn-secondary" onclick="goToPage('payment')">กลับ</button>
                    <button class="btn" onclick="loadSalesReport()">ดูรายงาน</button>
                </div>
                <button class="btn btn-secondary" onclick="goToPage('home')" style="margin-top: 10px;">
                    กลับหน้าแรก
                </button>
            </div>

            <!-- Success Page -->
            <div id="page-success" class="page">
                <div class="success-message">
                    <div class="success-icon">✅</div>
                    <h2 style="margin-bottom: 10px;">🎉 การชำระเงินสำเร็จ! 🎊</h2>
                    <p style="color: #666; margin-bottom: 30px;">
                        ขอบคุณที่ใช้บริการ Triamudom Smart Canteen 🙏<br>
                        โปรดรอรับอาหารที่โต๊ะของคุณ 🍴
                    </p>
                    <button class="btn" onclick="resetOrder()">🔄 สั่งอาหารใหม่</button>
                </div>
            </div>
        </div>
    </div>

    <script>
        // ตัวแปรสำหรับเก็บข้อมูล
        let currentOrder = [];
        
        // URL ของ Google Apps Script Web App
        const SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbyFkTt7Sq5ApZtp7L0A2UQyQL_FW0FYZjWoXl_Orp1bF484WG4UjQBEimY25bauSCl/exec';

        // ฟังก์ชันเปลี่ยนหน้า
        function goToPage(pageName) {
            // ตรวจสอบว่าเลือกโรงอาหารแล้วหรือยัง ก่อนไปหน้า add-product
            if (pageName === 'add-product') {
                const location = document.getElementById('canteenLocation').value;
                if (!location) {
                    alert('กรุณาเลือกโรงอาหารก่อน');
                    return;
                }
                // เก็บข้อมูลโรงอาหารที่เลือก
                localStorage.setItem('selectedLocation', location);
            }
            
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            document.getElementById('page-' + pageName).classList.add('active');
        }

        // ฟังก์ชันเพิ่มสินค้า
        async function addProduct() {
            const shopName = document.getElementById('shopName').value;
            const name = document.getElementById('productName').value.trim();
            const category = document.getElementById('productCategory').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const description = document.getElementById('productDescription').value.trim();
            const location = localStorage.getItem('selectedLocation') || '';

            // ตรวจสอบข้อมูล
            if (!shopName) {
                showError('errorMessage', 'กรุณาเลือกร้านอาหาร');
                return;
            }

            if (!name || !category || !price) {
                showError('errorMessage', 'กรุณากรอกข้อมูลให้ครบถ้วน');
                return;
            }

            if (price <= 0) {
                showError('errorMessage', 'กรุณาระบุราคาที่ถูกต้อง');
                return;
            }

            // แสดง loading
            showLoading('loading');

            try {
                // ส่งข้อมูลไป Google Sheets
                const formData = new FormData();
                formData.append('action', 'addProduct');
                formData.append('location', location);
                formData.append('shopName', shopName);
                formData.append('name', name);
                formData.append('category', category);
                formData.append('price', price);
                formData.append('description', description);

                const response = await fetch(SCRIPT_URL, {
                    method: 'POST',
                    body: formData
                });

                const result = await response.json();

                if (result.status === 'success') {
                    // เพิ่มลงในรายการสั่งซื้อปัจจุบัน
                    currentOrder.push({
                        location: location,
                        shopName: shopName,
                        name: name,
                        category: category,
                        price: price,
                        description: description
                    });

                    // แจ้งเตือนสำเร็จ
                    alert('เพิ่มรายการสำเร็จ! ✅');
                    
                    // ล้างฟอร์ม
                    document.getElementById('shopName').value = '';
                    document.getElementById('productName').value = '';
                    document.getElementById('productCategory').value = '';
                    document.getElementById('productPrice').value = '';
                    document.getElementById('productDescription').value = '';
                    
                    hideError('errorMessage');
                } else {
                    throw new Error(result.message || 'เกิดข้อผิดพลาด');
                }
            } catch (error) {
                showError('errorMessage', 'ไม่สามารถบันทึกข้อมูลได้: ' + error.message);
            } finally {
                hideLoading('loading');
            }
        }

        // ฟังก์ชันชำระเงิน
        async function processPayment() {
            const customerName = document.getElementById('customerName').value.trim();
            const tableNumber = document.getElementById('tableNumber').value.trim();
            const paymentMethod = document.getElementById('paymentMethod').value;

            // ตรวจสอบข้อมูล
            if (!customerName || !tableNumber || !paymentMethod) {
                showError('paymentError', 'กรุณากรอกข้อมูลให้ครบถ้วน');
                return;
            }

            if (currentOrder.length === 0) {
                showError('paymentError', 'กรุณาเพิ่มรายการอาหารก่อนชำระเงิน');
                return;
            }

            // แสดง loading
            showLoading('paymentLoading');

            try {
                // ส่งข้อมูลไป Google Sheets
                const formData = new FormData();
                formData.append('action', 'processPayment');
                formData.append('customerName', customerName);
                formData.append('tableNumber', tableNumber);
                formData.append('paymentMethod', paymentMethod);
                formData.append('orderData', JSON.stringify(currentOrder));
                formData.append('totalAmount', calculateTotal());

                const response = await fetch(SCRIPT_URL, {
                    method: 'POST',
                    body: formData
                });

                const result = await response.json();

                if (result.status === 'success') {
                    // ไปหน้าสำเร็จ
                    goToPage('success');
                    hideError('paymentError');
                } else {
                    throw new Error(result.message || 'เกิดข้อผิดพลาด');
                }
            } catch (error) {
                showError('paymentError', 'ไม่สามารถดำเนินการชำระเงินได้: ' + error.message);
            } finally {
                hideLoading('paymentLoading');
            }
        }

        // ฟังก์ชันโหลดรายงานยอดขาย
        async function loadSalesReport() {
            const date = document.getElementById('reportDate').value;
            const category = document.getElementById('reportCategory').value;

            if (!date) {
                showError('reportError', 'กรุณาเลือกวันที่');
                return;
            }

            showLoading('reportLoading');

            try {
                const url = `${SCRIPT_URL}?action=getSalesReport&date=${date}&category=${category}`;
                const response = await fetch(url);
                const result = await response.json();

                if (result.status === 'success') {
                    // แสดงผลรายงาน
                    document.getElementById('reportCount').textContent = result.count;
                    document.getElementById('reportTotal').textContent = result.total.toFixed(2) + ' บาท';
                    document.getElementById('reportSummary').style.display = 'block';
                    hideError('reportError');
                } else {
                    throw new Error(result.message || 'เกิดข้อผิดพลาด');
                }
            } catch (error) {
                showError('reportError', 'ไม่สามารถโหลดรายงานได้: ' + error.message);
            } finally {
                hideLoading('reportLoading');
            }
        }

        // ฟังก์ชันคำนวณยอดรวม
        function calculateTotal() {
            return currentOrder.reduce((sum, item) => sum + item.price, 0);
        }

        // ฟังก์ชันอัพเดทสรุปรายการ
        function updateOrderSummary() {
            const summaryDiv = document.getElementById('summaryItems');
            summaryDiv.innerHTML = '';

            currentOrder.forEach((item, index) => {
                const itemDiv = document.createElement('div');
                itemDiv.className = 'summary-item';
                itemDiv.innerHTML = `
                    <span>${index + 1}. ${item.shopName} - ${item.name}</span>
                    <span>${item.price.toFixed(2)} บาท</span>
                `;
                summaryDiv.appendChild(itemDiv);
            });

            document.getElementById('totalAmount').textContent = calculateTotal().toFixed(2) + ' บาท';
        }

        // ฟังก์ชันรีเซ็ตคำสั่งซื้อ
        function resetOrder() {
            currentOrder = [];
            document.getElementById('canteenLocation').value = '';
            document.getElementById('customerName').value = '';
            document.getElementById('tableNumber').value = '';
            document.getElementById('paymentMethod').value = '';
            localStorage.removeItem('selectedLocation');
            goToPage('home');
        }

        // ฟังก์ชันแสดง/ซ่อน Error
        function showError(elementId, message) {
            const errorDiv = document.getElementById(elementId);
            errorDiv.textContent = message;
            errorDiv.style.display = 'block';
        }

        function hideError(elementId) {
            document.getElementById(elementId).style.display = 'none';
        }

        // ฟังก์ชันแสดง/ซ่อน Loading
        function showLoading(elementId) {
            document.getElementById(elementId).style.display = 'block';
        }

        function hideLoading(elementId) {
            document.getElementById(elementId).style.display = 'none';
        }

        // อัพเดทสรุปรายการเมื่อไปหน้าชำระเงิน
        document.addEventListener('DOMContentLoaded', function() {
            // ตั้งค่าวันที่เริ่มต้น
            const today = new Date().toISOString().split('T')[0];
            document.getElementById('reportDate').value = today;
        });

        // เพิ่ม event listener สำหรับการเปลี่ยนหน้า
        const originalGoToPage = goToPage;
        goToPage = function(pageName) {
            if (pageName === 'payment') {
                updateOrderSummary();
            }
            originalGoToPage(pageName);
        };
    </script>
</body>
</html>
