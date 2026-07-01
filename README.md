<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জন্ম নিবন্ধনের জন্য আবেদন</title>
    <style>
        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: #f4f7f6;
            margin: 0;
            padding: 20px;
            direction: ltr;
        }
        .form-container {
            max-width: 800px;
            background: #ffffff;
            margin: 0 auto;
            padding: 30px;
            border-top: 5px solid #006a4e; /* সবুজ বর্ডার */
            box-shadow: 0 4px 8px rgba(0,0,0,0.05);
            border-radius: 4px;
        }
        h2 {
            color: #006a4e;
            border-bottom: 2px solid #f0f0f0;
            padding-bottom: 10px;
            margin-top: 0;
        }
        h3 {
            color: #333;
            font-size: 18px;
            margin-top: 25px;
            background: #e8f5e9;
            padding: 8px;
            border-left: 4px solid #006a4e;
        }
        .form-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        @media (max-width: 600px) {
            .form-grid {
                grid-template-columns: 1fr;
            }
        }
        .form-group {
            display: flex;
            flex-direction: column;
        }
        .form-group label {
            margin-bottom: 8px;
            font-weight: bold;
            color: #444;
            font-size: 14px;
        }
        .form-group label span {
            color: red;
        }
        .form-group input, .form-group select {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
        }
        .form-group input:focus, .form-group select:focus {
            border-color: #006a4e;
            outline: none;
        }
        .btn-container {
            margin-top: 30px;
            display: flex;
            justify-content: space-between;
        }
        .btn {
            padding: 10px 25px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            font-weight: bold;
        }
        .btn-next {
            background-color: #006a4e;
            color: white;
        }
        .btn-prev {
            background-color: #ccc;
            color: #333;
        }
    </style>
</head>
<body>

<div class="form-container">
    <h2>জন্ম নিবন্ধনের জন্য আবেদন</h2>
    
    <form>
        <!-- নিবন্ধনাধীন ব্যক্তির পরিচিতি -->
        <h3>নিবন্ধনাধীন ব্যক্তির পরিচিতি</h3>
        <div class="form-grid">
            <div class="form-group">
                <label>নামের প্রথম অংশ বাংলায় <span>*</span></label>
                <input type="text" placeholder="নামের প্রথম অংশ বাংলায়" required>
            </div>
            <div class="form-group">
                <label>নামের শেষ অংশ বাংলায় <span>*</span></label>
                <input type="text" placeholder="নামের শেষ অংশ বাংলায়" required>
            </div>
            <div class="form-group">
                <label>নামের প্রথম অংশ ইংরেজিতে <span>*</span></label>
                <input type="text" placeholder="First Name in English" required>
            </div>
            <div class="form-group">
                <label>নামের শেষ অংশ ইংরেজিতে <span>*</span></label>
                <input type="text" placeholder="Last Name in English" required>
            </div>
            <div class="form-group">
                <label>জন্ম তারিখ (খ্রিঃ) <span>*</span></label>
                <input type="date" required>
            </div>
            <div class="form-group">
                <label>পিতা ও মাতার কততম সন্তান <span>*</span></label>
                <select required>
                    <option value="">---নির্বাচন করুন---</option>
                    <option value="1">১</option>
                    <option value="2">২</option>
                    <option value="3">৩</option>
                </select>
            </div>
            <div class="form-group">
                <label>লিঙ্গ <span>*</span></label>
                <select required>
                    <option value="">---নির্বাচন করুন---</option>
                    <option value="male">পুরুষ</option>
                    <option value="female">মহিলা</option>
                    <option value="other">তৃতীয় লিঙ্গ</option>
                </select>
            </div>
        </div>

        <!-- জন্মস্থানের ঠিকানা -->
        <h3>জন্মস্থানের ঠিকানা</h3>
        <div class="form-grid">
            <div class="form-group">
                <label>দেশ <span>*</span></label>
                <select required>
                    <option value="">দেশ নির্বাচন করুন</option>
                    <option value="BD">বাংলাদেশ</option>
                </select>
            </div>
            <div class="form-group">
                <label>বিভাগ <span>*</span></label>
                <select required>
                    <option value="">বিভাগ নির্বাচন করুন</option>
                    <option value="dhaka">ঢাকা বিভাগ</option>
                    <option value="chittagong">চট্টগ্রাম বিভাগ</option>
                </select>
            </div>
            <div class="form-group">
                <label>ডাকঘর (বাংলায়) <span>*</span></label>
                <input type="text" required>
            </div>
            <div class="form-group">
                <label>ডাকঘর (ইংরেজিতে) <span>*</span></label>
                <input type="text" required>
            </div>
        </div>

        <!-- বোতাম বা বাটন সমূহ -->
        <div class="btn-container">
            <button type="button" class="btn btn-prev">পূর্ববর্তী</button>
            <button type="submit" class="btn btn-next">পরবর্তী</button>
        </div>
    </form>
</div>

</body>
</html>
