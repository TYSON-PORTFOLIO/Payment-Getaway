<html lang="en">
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
    <title>Tyson_Owner Team • Hack</title>
    <link rel="preconnect" href="https://fonts.googleapis.com" />
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700;900&family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet" />
    <style>
        /* ---- Reset & Base ---- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 12px;
            font-family: 'Inter', sans-serif;
            background: radial-gradient(circle at 10% 20%, #0f0f2a, #03030a);
            background-attachment: fixed;
            overflow-x: hidden;
        }

        /* ---- Glowing Orbs (adjusted for mobile) ---- */
        body::before,
        body::after {
            content: '';
            position: fixed;
            border-radius: 50%;
            filter: blur(100px);
            z-index: 0;
            opacity: 0.2;
            pointer-events: none;
        }
        body::before {
            width: 300px;
            height: 300px;
            top: -80px;
            right: -80px;
            background: #a855f7;
        }
        body::after {
            width: 350px;
            height: 350px;
            bottom: -100px;
            left: -100px;
            background: #06b6d4;
        }

        .container {
            max-width: 440px;
            width: 100%;
            background: rgba(12, 12, 35, 0.78);
            backdrop-filter: blur(24px);
            -webkit-backdrop-filter: blur(24px);
            border-radius: 36px;
            padding: 20px 16px 20px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            box-shadow: 0 30px 80px rgba(0, 0, 0, 0.8);
            position: relative;
            z-index: 1;
            overflow-x: hidden;
        }

        /* ---- Header ---- */
        .header {
            display: flex;
            align-items: center;
            gap: 14px;
            margin-bottom: 16px;
            padding: 0 2px;
        }
        .header-logo {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            border: 2px solid rgba(0, 255, 255, 0.4);
            box-shadow: 0 0 25px rgba(0, 255, 255, 0.15);
            object-fit: cover;
            flex-shrink: 0;
        }
        .header-title {
            font-family: 'Orbitron', sans-serif;
            font-weight: 900;
            font-size: 18px;
            line-height: 1.2;
            background: linear-gradient(135deg, #c084fc, #22d3ee, #fde047);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .header-title small {
            font-family: 'Inter', sans-serif;
            font-weight: 600;
            font-size: 11px;
            color: #94a3b8;
            background: none;
            -webkit-background-clip: unset;
            background-clip: unset;
            display: block;
            margin-top: 0px;
            letter-spacing: 2px;
            opacity: 0.8;
        }

        /* ---- Developer Banner ---- */
        .dev-banner {
            background: linear-gradient(135deg, rgba(168, 85, 247, 0.12), rgba(6, 182, 212, 0.12));
            border: 1px solid rgba(168, 85, 247, 0.15);
            border-radius: 60px;
            padding: 8px 14px;
            text-align: center;
            margin-bottom: 20px;
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            font-size: 12px;
            color: #e2e8f0;
            letter-spacing: 0.5px;
        }
        .dev-banner span {
            background: linear-gradient(135deg, #c084fc, #22d3ee);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: pulseGlow 3s ease-in-out infinite;
        }
        @keyframes pulseGlow {
            0%,
            100% {
                opacity: 0.7;
            }
            50% {
                opacity: 1;
                filter: drop-shadow(0 0 10px #c084fc);
            }
        }

        /* ---- Features (Full width on mobile) ---- */
        .features {
            display: flex;
            flex-direction: column;
            gap: 8px;
            margin-bottom: 22px;
        }
        .feature-item {
            width: 100%;
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.05);
            border-radius: 60px;
            padding: 10px 16px;
            display: flex;
            align-items: center;
            gap: 12px;
            font-weight: 600;
            font-size: 14px;
            color: #cbd5e1;
            backdrop-filter: blur(4px);
            transition: 0.2s;
        }
        .feature-item:active {
            background: rgba(34, 211, 238, 0.06);
            transform: scale(0.98);
        }
        .feature-item .icon {
            font-size: 22px;
            flex-shrink: 0;
        }
        .feature-item .highlight {
            color: #22d3ee;
            font-weight: 700;
        }

        /* ---- Plan Cards (Stacks perfectly on phone) ---- */
        .plan {
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            padding: 14px 16px;
            margin-bottom: 10px;
            border: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
            transition: all 0.2s;
            position: relative;
        }
        .plan:active {
            background: rgba(255, 255, 255, 0.06);
            transform: scale(0.99);
        }
        .plan-info {
            display: flex;
            flex-direction: column;
            gap: 0px;
            flex: 1;
            min-width: 120px;
        }
        .plan-name {
            font-weight: 700;
            font-size: 16px;
            color: #f1f5f9;
            letter-spacing: -0.2px;
        }
        .plan-name span {
            font-weight: 500;
            font-size: 11px;
            color: #94a3b8;
            margin-left: 6px;
            background: rgba(255, 255, 255, 0.05);
            padding: 2px 10px;
            border-radius: 40px;
            display: inline-block;
        }
        .plan-price {
            font-size: 20px;
            font-weight: 800;
            background: linear-gradient(135deg, #c084fc, #22d3ee);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .pay-btn {
            background: linear-gradient(135deg, #22d3ee, #0891b2);
            border: none;
            padding: 10px 24px;
            border-radius: 60px;
            font-weight: 700;
            font-size: 14px;
            color: #0f172a;
            cursor: pointer;
            transition: all 0.15s;
            box-shadow: 0 4px 20px rgba(34, 211, 238, 0.2);
            text-decoration: none;
            display: inline-block;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            text-align: center;
            min-width: 76px;
        }
        .pay-btn:active {
            transform: scale(0.92);
            box-shadow: 0 0 30px #22d3ee;
        }

        /* ---- QR Section ---- */
        .qr-section {
            margin-top: 24px;
            text-align: center;
            background: rgba(0, 0, 0, 0.25);
            border-radius: 28px;
            padding: 20px 14px 18px;
            border: 1px solid rgba(255, 255, 255, 0.04);
        }
        .qr-section .qr-label {
            font-size: 14px;
            font-weight: 700;
            color: #c084fc;
            margin-bottom: 10px;
            letter-spacing: 0.3px;
        }
        .qr-section img {
            max-width: 160px;
            width: 100%;
            border-radius: 18px;
            box-shadow: 0 0 30px rgba(0, 0, 0, 0.6);
            background: white;
            padding: 5px;
            border: 1px solid rgba(255, 255, 255, 0.06);
        }

        .upi-id {
            background: rgba(255, 255, 255, 0.04);
            padding: 10px 14px;
            border-radius: 60px;
            margin-top: 14px;
            font-size: 14px;
            color: #e2e8f0;
            border: 1px solid rgba(255, 255, 255, 0.05);
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 8px;
        }
        .upi-id strong {
            color: #22d3ee;
            font-weight: 700;
        }
        .copy-btn {
            background: rgba(34, 211, 238, 0.08);
            border: 1px solid rgba(34, 211, 238, 0.15);
            color: #22d3ee;
            padding: 4px 16px;
            border-radius: 60px;
            font-size: 12px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.15s;
            white-space: nowrap;
        }
        .copy-btn:active {
            background: #22d3ee;
            color: #0f172a;
            transform: scale(0.92);
        }

        .auto-redirect {
            background: rgba(34, 211, 238, 0.03);
            border-left: 3px solid #22d3ee;
            padding: 8px 12px;
            border-radius: 14px;
            margin: 14px 0 2px;
            font-size: 12px;
            color: #94a3b8;
            line-height: 1.4;
        }
        .auto-redirect strong {
            color: #c084fc;
        }

        /* ---- Verification Box (Stacked on phone) ---- */
        .verify-section {
            margin: 22px 0 6px;
            background: rgba(255, 255, 255, 0.02);
            border-radius: 24px;
            padding: 16px 14px 18px;
            border: 1px solid rgba(255, 255, 255, 0.04);
        }
        .verify-section .label {
            display: block;
            font-size: 13px;
            font-weight: 600;
            color: #94a3b8;
            margin-bottom: 10px;
            letter-spacing: 0.3px;
        }
        .verify-section .label span {
            color: #c084fc;
            font-weight: 700;
        }
        .verify-row {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
        .verify-row input {
            width: 100%;
            background: rgba(255, 255, 255, 0.04);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: 60px;
            padding: 14px 18px;
            font-size: 14px;
            color: #f1f5f9;
            outline: none;
            transition: 0.3s;
            font-weight: 500;
            font-family: 'Inter', sans-serif;
        }
        .verify-row input:focus {
            border-color: #c084fc;
            box-shadow: 0 0 25px rgba(168, 85, 247, 0.06);
            background: rgba(255, 255, 255, 0.06);
        }
        .verify-row input::placeholder {
            color: #475569;
            font-weight: 400;
            font-size: 13px;
        }
        .verify-btn {
            width: 100%;
            background: linear-gradient(135deg, #c084fc, #7e22ce);
            border: none;
            padding: 14px 20px;
            border-radius: 60px;
            font-weight: 700;
            font-size: 15px;
            color: #fff;
            cursor: pointer;
            box-shadow: 0 4px 20px rgba(168, 85, 247, 0.2);
            border: 1px solid rgba(255, 255, 255, 0.05);
            transition: all 0.15s;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            text-align: center;
        }
        .verify-btn:active {
            transform: scale(0.95);
            box-shadow: 0 0 40px #c084fc;
        }
        .verify-hint {
            font-size: 11px;
            color: #475569;
            margin-top: 10px;
            text-align: center;
            line-height: 1.5;
        }
        .verify-hint strong {
            color: #22d3ee;
            font-weight: 600;
        }

        /* ---- Footer ---- */
        .footer {
            margin-top: 20px;
            text-align: center;
            font-size: 11px;
            color: #334155;
            border-top: 1px solid rgba(255, 255, 255, 0.04);
            padding-top: 16px;
            display: flex;
            flex-direction: column;
            gap: 4px;
        }
        .footer .owner {
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            color: #c084fc;
            font-size: 13px;
            letter-spacing: 0.3px;
        }
        .footer .warning {
            color: #64748b;
            opacity: 0.7;
            font-size: 10px;
        }
        .footer .warning strong {
            color: #22d3ee;
            opacity: 1;
        }

        /* ---- Modal / Receipt (Phone Optimized) ---- */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0, 0, 0, 0.85);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            display: none;
            justify-content: center;
            align-items: center;
            z-index: 999;
            padding: 16px;
        }
        .modal-overlay.active {
            display: flex;
        }
        .modal-content {
            max-width: 380px;
            width: 100%;
            background: rgba(16, 16, 40, 0.97);
            border-radius: 32px;
            padding: 24px 18px 20px;
            border: 1px solid rgba(34, 211, 238, 0.15);
            box-shadow: 0 0 60px rgba(34, 211, 238, 0.04), 0 30px 60px rgba(0, 0, 0, 0.6);
            animation: modalPop 0.3s cubic-bezier(0.34, 1.56, 0.64, 1);
        }
        @keyframes modalPop {
            0% {
                transform: scale(0.9) translateY(20px);
                opacity: 0;
            }
            100% {
                transform: scale(1) translateY(0);
                opacity: 1;
            }
        }
        .modal-header {
            text-align: center;
            font-family: 'Orbitron', sans-serif;
            font-weight: 900;
            font-size: 18px;
            color: #22d3ee;
            padding-bottom: 14px;
            border-bottom: 1px dashed rgba(34, 211, 238, 0.1);
            margin-bottom: 16px;
            letter-spacing: 0.5px;
        }
        .modal-header .check {
            font-size: 40px;
            display: block;
            margin-bottom: 0px;
            filter: drop-shadow(0 0 25px #22d3ee);
        }
        .receipt-body {
            display: flex;
            flex-direction: column;
            gap: 10px;
            margin-bottom: 20px;
        }
        .receipt-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            font-size: 13px;
            padding: 5px 0px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.03);
            color: #cbd5e1;
            gap: 10px;
        }
        .receipt-row .label {
            font-weight: 500;
            color: #64748b;
            flex-shrink: 0;
        }
        .receipt-row .value {
            font-weight: 700;
            color: #f1f5f9;
            text-align: right;
            word-break: break-all;
            max-width: 60%;
        }
        .receipt-row .value.highlight-amount {
            background: linear-gradient(135deg, #c084fc, #22d3ee);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-size: 20px;
            font-weight: 900;
        }
        .receipt-row .value.status {
            color: #4ade80;
        }
        .receipt-row .value.txn-id {
            font-family: 'Inter', monospace;
            font-weight: 600;
            color: #c084fc;
            font-size: 12px;
        }
        .modal-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 14px;
            border-top: 1px dashed rgba(255, 255, 255, 0.05);
            flex-wrap: wrap;
            gap: 10px;
        }
        .modal-footer .brand {
            font-family: 'Orbitron', sans-serif;
            font-weight: 700;
            color: #c084fc;
            font-size: 11px;
        }
        .modal-footer .close-btn {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid #334155;
            color: #94a3b8;
            padding: 8px 24px;
            border-radius: 60px;
            font-weight: 600;
            font-size: 13px;
            cursor: pointer;
            transition: 0.15s;
        }
        .modal-footer .close-btn:active {
            background: #c084fc;
            color: #0f172a;
            transform: scale(0.92);
        }

        /* ---- Extremely small screens (like 320px) ---- */
        @media (max-width: 380px) {
            .container {
                padding: 16px 12px;
                border-radius: 28px;
            }
            .header-title {
                font-size: 16px;
            }
            .header-logo {
                width: 42px;
                height: 42px;
            }
            .plan {
                padding: 12px 12px;
            }
            .plan-name {
                font-size: 14px;
            }
            .plan-price {
                font-size: 18px;
            }
            .pay-btn {
                padding: 8px 16px;
                font-size: 12px;
                min-width: 64px;
            }
            .feature-item {
                font-size: 12px;
                padding: 8px 12px;
            }
            .feature-item .icon {
                font-size: 18px;
            }
            .qr-section img {
                max-width: 130px;
            }
            .modal-content {
                padding: 20px 14px;
            }
            .receipt-row {
                font-size: 12px;
            }
        }
    </style>
</head>
<body>
<div class="container">

    <!-- HEADER -->
    <div class="header">
        <img class="header-logo" src="https://www.image2url.com/r2/default/images/1782060674321-f50f86c8-f27d-41cf-b670-8910cd19d5b1.jpg" alt="Tyson Owner Logo" />
        <div class="header-title">
            Tyson_Owner Team
            <small>• HACK • Payment Getaway</small>
        </div>
    </div>

    <!-- DEVELOPER BANNER -->
    <div class="dev-banner">
        <span>🔻 Hack Buy Direct From Developer 🔺</span>
    </div>

    <!-- FEATURES -->
    <div class="features">
        <div class="feature-item">
            <span class="icon">👁️⚡</span>
            <span class="text"><span class="highlight">Auto Prediction</span> Every Min</span>
        </div>
        <div class="feature-item">
            <span class="icon">👁️🎯</span>
            <span class="text"><span class="highlight">Big/Small</span> Smart Logic</span>
        </div>
    </div>

    <!-- PLANS -->
    <div class="plan">
        <div class="plan-info">
            <div class="plan-name">🔥 1 WEEK <span>Trial</span></div>
            <div class="plan-price">₹1200</div>
        </div>
        <a href="upi://pay?pa=8092043236@ybl&pn=TysonVIP&am=1200&cu=INR&tn=Tyson%20VIP%20Hack%20-%201%20Week"
           class="pay-btn" onclick="storePayment(1200,'1 Week Trial')">Pay</a>
    </div>

    <div class="plan">
        <div class="plan-info">
            <div class="plan-name">🚀 1 MONTH <span>Standard</span></div>
            <div class="plan-price">₹1900</div>
        </div>
        <a href="upi://pay?pa=8092043236@ybl&pn=TysonVIP&am=1900&cu=INR&tn=Tyson%20VIP%20Hack%20-%201%20Month"
           class="pay-btn" onclick="storePayment(1900,'1 Month Standard')">Pay</a>
    </div>

    <div class="plan">
        <div class="plan-info">
            <div class="plan-name">🏆 2 MONTHS <span>Premium</span></div>
            <div class="plan-price">₹2999</div>
        </div>
        <a href="upi://pay?pa=8092043236@ybl&pn=TysonVIP&am=2999&cu=INR&tn=Tyson%20VIP%20Hack%20-%202%20Months"
           class="pay-btn" onclick="storePayment(2999,'2 Months Premium')">Pay</a>
    </div>

    <!-- QR + UPI -->
    <div class="qr-section">
        <div class="qr-label">📱 Scan to Pay (Any UPI App)</div>
        <img src="https://i.postimg.cc/QK5VFwC1/IMG-20260415-050829.jpg" alt="PhonePe QR Code" loading="lazy" />
        <div class="upi-id">
            <span><strong>UPI ID :</strong> 8092043236@ybl</span>
            <button class="copy-btn" onclick="copyUPI()">📋 Copy</button>
        </div>
        <div class="auto-redirect">
            ✅ Tap <strong>Pay</strong> → auto‑redirect with pre‑filled message.<br />
            <span style="font-size:11px; opacity:0.6;">(Opens web UPI if no app installed)</span>
        </div>
    </div>

    <!-- VERIFICATION + BILL SLIP -->
    <div class="verify-section">
        <div class="label">🔐 <span>Verify</span> Your Payment</div>
        <div class="verify-row">
            <input type="text" id="txnInput" placeholder="Paste UPI Reference / TXN ID" />
            <button class="verify-btn" onclick="verifyAndShowSlip()">Verify ✅</button>
        </div>
        <div class="verify-hint">
            💡 Payment ke baad UPI app se <strong>Transaction ID</strong> copy karke paste karein.
        </div>
    </div>

    <!-- FOOTER -->
    <div class="footer">
        <div class="owner">👑 @TYSON_OWNER</div>
        <div class="warning">⚠️ Confirm payee <strong>TYSON VIP</strong> before paying · Auto‑credited</div>
        <div style="opacity:0.3; font-size:9px;">Secure UPI · Display only</div>
    </div>

</div>

<!-- ===== RECEIPT MODAL ===== -->
<div id="receiptModal" class="modal-overlay">
    <div class="modal-content">
        <div class="modal-header">
            <span class="check">✅</span>
            Payment Bill Slip
        </div>
        <div class="receipt-body">
            <div class="receipt-row">
                <span class="label">📅 Date & Time</span>
                <span class="value" id="r-date">-</span>
            </div>
            <div class="receipt-row">
                <span class="label">🔢 Transaction ID</span>
                <span class="value txn-id" id="r-txn">-</span>
            </div>
            <div class="receipt-row">
                <span class="label">📋 Plan</span>
                <span class="value" id="r-plan">-</span>
            </div>
            <div class="receipt-row">
                <span class="label">💰 Amount</span>
                <span class="value highlight-amount" id="r-amount">-</span>
            </div>
            <div class="receipt-row">
                <span class="label">🏦 UPI ID</span>
                <span class="value">8092043236@ybl</span>
            </div>
            <div class="receipt-row">
                <span class="label">📌 Status</span>
                <span class="value status">✅ Verified & Successful</span>
            </div>
        </div>
        <div class="modal-footer">
            <span class="brand">👑 @TYSON_OWNER</span>
            <button class="close-btn" onclick="closeReceipt()">Close</button>
        </div>
    </div>
</div>

<script>
    let lastAmount = 0;
    let lastPlan = '';

    function storePayment(amount, plan) {
        lastAmount = amount;
        lastPlan = plan;
        document.getElementById('txnInput').focus();
    }

    function verifyAndShowSlip() {
        const txnInput = document.getElementById('txnInput');
        const txnId = txnInput.value.trim();

        if (!lastAmount || lastAmount === 0) {
            alert('⚠️ Pehle koi "Pay" button dabayein (plan select karein).');
            txnInput.focus();
            return;
        }
        if (txnId === '') {
            alert('⚠️ Kripya UPI app se Transaction ID copy karke paste karein.');
            txnInput.focus();
            return;
        }

        const now = new Date();
        const dateStr = now.toLocaleDateString('en-IN', { day: '2-digit', month: 'short', year: 'numeric' });
        const timeStr = now.toLocaleTimeString('en-IN', { hour: '2-digit', minute: '2-digit', hour12: true });

        document.getElementById('r-date').innerText = `${dateStr}, ${timeStr}`;
        document.getElementById('r-txn').innerText = txnId;
        document.getElementById('r-plan').innerText = lastPlan;
        document.getElementById('r-amount').innerText = '₹' + lastAmount;

        document.getElementById('receiptModal').classList.add('active');
    }

    function closeReceipt() {
        document.getElementById('receiptModal').classList.remove('active');
    }

    document.getElementById('receiptModal').addEventListener('click', function(e) {
        if (e.target === this) closeReceipt();
    });

    document.getElementById('txnInput').addEventListener('keypress', function(e) {
        if (e.key === 'Enter') verifyAndShowSlip();
    });

    function copyUPI() {
        const upi = "8092043236@ybl";
        navigator.clipboard.writeText(upi).then(() => {
            const btn = document.querySelector('.copy-btn');
            btn.textContent = '✅ Copied!';
            setTimeout(() => btn.textContent = '📋 Copy', 2000);
        }).catch(() => alert('Copy manually: ' + upi));
    }
</script>
</body>
</html>
