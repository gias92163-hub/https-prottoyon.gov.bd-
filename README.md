<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>জন্ম নিবন্ধন সংশোধন আবেদন ফরম</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
    <style>
        body {
            font-family: 'Kalpurush', 'Siyam Rupali', Arial, sans-serif;
            background-color: #f4f4f9;
            margin: 0;
            padding: 20px;
            color: #333;
        }
        .container {
            max-width: 900px;
            margin: 0 auto;
            background: #fff;
            padding: 30px;
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
        }
        h2, h3 {
            text-align: center;
            color: #000;
            margin-bottom: 20px;
        }
        .form-section {
            margin-bottom: 25px;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 6px;
            background-color: #fdfdfd;
        }
        .form-section h4 {
            margin-top: 0;
            border-bottom: 2px solid #0056b3;
            padding-bottom: 5px;
            color: #0056b3;
        }
        .grid-2 {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
        }
        .form-group {
            display: flex;
            flex-direction: column;
            margin-bottom: 12px;
        }
        label {
            font-weight: bold;
            margin-bottom: 5px;
            font-size: 14px;
        }
        input, select, textarea {
            padding: 8px 12px;
            border: 1px solid #ccc;
            border-radius: 4px;
            font-size: 14px;
        }
        button {
            display: block;
            width: 100%;
            padding: 12px;
            background-color: #28a745;
            color: #fff;
            border: none;
            border-radius: 5px;
            font-size: 16px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s;
            margin-top: 20px;
        }
        button:hover {
            background-color: #218838;
        }
        #pdf-template {
            display: none;
            width: 100%;
            padding: 40px;
            box-sizing: border-box;
            background: #fff;
            color: #000;
            font-size: 13px;
            line-height: 1.5;
        }
        .pdf-header {
            text-align: center;
            margin-bottom: 15px;
        }
        .pdf-header h3 { margin: 5px 0; font-size: 18px; }
        .pdf-header p { margin: 3px 0; font-size: 13px; }
        .meta-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 15px;
            font-size: 13px;
        }
        .pdf-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
            margin-bottom: 15px;
        }
        .pdf-table th, .pdf-table td {
            border: 1px solid #000;
            padding: 6px 8px;
            text-align: left;
            font-size: 12px;
            vertical-align: top;
        }
        .pdf-table th {
            background-color: #f2f2f2;
        }
        .footer-section {
            margin-top: 30px;
            display: flex;
            justify-content: space-between;
        }
        .footer-box {
            width: 45%;
            border: 1px solid #000;
            padding: 10px;
            border-radius: 4px;
        }
        .signature-area {
            margin-top: 40px;
            border-top: 1px dashed #000;
            text-align: center;
            font-size: 12px;
            padding-top: 5px;
        }
    </style>
</head>
<body>
<div class="container">
    <h2>জন্ম নিবন্ধন সংশোধন আবেদন ফরম</h2>
    <p style="text-align: center; color: #666;">নিচের তথ্যগুলো পূরণ করে "পিডিএফ ডাউনলোড করুন" বাটনে ক্লিক করুন।</p>
   
    <form id="regForm">
        <!-- প্রাথমিক তথ্য -->
        <div class="form-section">
            <h4>প্রাথমিক তথ্য</h4>
            <div class="grid-2">
                <div class="form-group">
                    <label>আবেদনপত্রের আইডি:</label>
                    <input type="text" id="app_id" value="৫৮১২৫১২৪">
                </div>
                <div class="form-group">
                    <label>আবেদনের তারিখ:</label>
                    <input type="text" id="app_date" value="২৩/০১/২০২৬">
                </div>
                <div class="form-group">
                    <label>জন্ম নিবন্ধন নম্বর:</label>
                    <input type="text" id="br_num" value="১৯৯৪২২১২৪৪২০২১৫২৩">
                </div>
                <div class="form-group">
                    <label>জন্ম নিবন্ধনের তারিখ:</label>
                    <input type="text" id="br_date" value="০১/১০/২০০৮">
                </div>
            </div>
            <div class="form-group" style="margin-top:10px;">
                <label>কার্যালয়ের নাম ও ঠিকানা:</label>
                <input type="text" id="office_address" value="ইসলামাবাদ ইউনিয়ন পরিষদ, ঈদগাঁও, কক্সবাজার, চট্টগ্রাম বিভাগ, বাংলাদেশ">
            </div>
        </div>

        <!-- নিবন্ধিত ব্যক্তির তথ্য -->
        <div class="form-section">
            <h4>নিবন্ধিত ব্যক্তির তথ্য</h4>
            <div class="grid-2">
                <div class="form-group">
                    <label>১। নিবন্ধিত ব্যক্তির নাম (বাংলা):</label>
                    <input type="text" id="person_name" value="শফি আলম">
                </div>
                <div class="form-group">
                    <label>২। জন্ম তারিখ:</label>
                    <input type="text" id="birth_date" value="০২/০৫/১৯৯৪">
                </div>
            </div>
        </div>

        <!-- সংশোধনীর বিবরণ -->
        <div class="form-section">
            <h4>৩। ভুল তথ্যের বিবরণ ও উহার কারণ</h4>
            
            <div style="background:#eee; padding:10px; margin-bottom:10px; border-radius:4px;">
                <strong>নামের প্রথম অংশ (ইংরেজি):</strong>
                <div class="grid-2" style="margin-top:5px;">
                    <input type="text" id="corr_name_en" value="SAFI ALAM">
                    <input type="text" id="cause_name_en" value="ভুল লিপিবদ্ধ করা হয়েছিল">
                </div>
            </div>

            <div style="background:#eee; padding:10px; margin-bottom:10px; border-radius:4px;">
                <strong>পিতার নাম (বাংলা & ইংরেজি):</strong>
                <div class="grid-2" style="margin-top:5px;">
                    <input type="text" id="corr_fat_bn" value="মৃত আবুল হোছন">
                    <input type="text" id="corr_fat_en" value="LATE ABUL HOSAN">
                    <input type="text" id="cause_fat" value="ভুল লিপিবদ্ধ করা হয়েছিল">
                </div>
            </div>

            <div style="background:#eee; padding:10px; margin-bottom:10px; border-radius:4px;">
                <strong>মাতার নাম (বাংলা & ইংরেজি):</strong>
                <div class="grid-2" style="margin-top:5px;">
                    <input type="text" id="corr_mot_bn" value="গোল বাহার">
                    <input type="text" id="corr_mot_en" value="GOAL BAHAR">
                    <input type="text" id="cause_mot" value="ভুল লিপিবদ্ধ করা হয়েছিল">
                </div>
            </div>

            <div style="background:#eee; padding:10px; margin-bottom:10px; border-radius:4px;">
                <strong>ঠিকানা সংশোধন</strong>
                <div class="form-group">
                    <label>জন্মস্থান বাংলায়:</label>
                    <input type="text" id="p_birth_bn" value="হোল্ডিং নং-৮২৫ সিকদার পাড়া, ইসলামাবাদ- ৪৭০২">
                </div>
                <div class="form-group">
                    <label>স্থায়ী ঠিকানা বাংলায়:</label>
                    <input type="text" id="p_perm_bn" value="হোল্ডিং নং-৮২৫ আউলিয়াবাদ, ইসলামাবাদ-৪৭০২">
                </div>
                <div class="form-group">
                    <label>বর্তমান ঠিকানা বাংলায়:</label>
                    <input type="text" id="p_curr_bn" value="হোল্ডিং নং-৮২৫ আউলিয়াবাদ, ইসলামাবাদ-৪৭০২">
                </div>
            </div>
        </div>

        <button type="button" onclick="generatePDF()">পিডিএফ ডাউনলোড করুন</button>
    </form>
</div>

<!-- PDF Template -->
<div id="pdf-template">
    <div style="text-align: right; font-size: 11px;">(জমনি ফরম-৮)</div>
    <div class="meta-info">
        <div><strong>আবেদনপত্রের আইডি-</strong> <span id="pdf_app_id"></span></div>
        <div><strong>আবেদনের তারিখ -</strong> <span id="pdf_app_date"></span></div>
    </div>
    <div class="pdf-header">
        <p><strong>জন্ম নিবন্ধন নম্বর:</strong> <span id="pdf_br_num"></span></p>
        <p><strong>জন্ম নিবন্ধনের তারিখ:</strong> <span id="pdf_br_date"></span></p>
        <h3 id="pdf_office_address"></h3>
        <h3>জন্ম সনদ সংশোধনের জন্য আবেদনপত্র</h3>
        <p>[বিধি ১৫ দ্রষ্টব্য]</p>
    </div>

    <div>
        <p><strong>১। নিবন্ধিত ব্যক্তির নাম:</strong> <span id="pdf_person_name"></span></p>
        <p><strong>২। জন্ম তারিখ:</strong> <span id="pdf_birth_date"></span></p>
        <p><strong>৩। ভুল তথ্যের বিবরণ ও উহার কারণ:</strong></p>
    </div>

    <table class="pdf-table">
        <thead>
            <tr>
                <th style="width: 30%;">সংশোধনের বিষয়</th>
                <th style="width: 45%;">সংশোধনীয় তথ্য</th>
                <th style="width: 25%;">সংশোধনের কারণ</th>
            </tr>
        </thead>
        <tbody id="pdf_table_body"></tbody>
    </table>

    <p><strong>৪। ঘোষণাঃ</strong> আমি সজ্ঞানে ঘোষণা করিতেছি যে উপরোক্ত তথ্য সত্য।</p>
    <p><strong>৫। সংযুক্তি:</strong> মাতার জাতীয় পরিচয়পত্র, ইস্যু সম্পর্কিত ফাইল, পিতার মৃত্যুর প্রমাণ, নিবন্ধকের প্রত্যয়নপত্র ইত্যাদি।</p>

    <div style="text-align: right; margin-top: 30px;">
        <p><strong>আবেদনকারীর স্বাক্ষর</strong></p>
    </div>

    <hr style="border: 1px dashed #000; margin: 30px 0;">
    
    <div class="footer-section">
        <div class="footer-box">
            <p style="margin:0; font-size:11px;">সংশোধিত সনদের কপি বিতরণের সম্ভাব্য তারিখ (নিবন্ধক কর্তৃক পূরণীয়)</p>
        </div>
        <div style="width: 45%; text-align: center; margin-top: 20px;">
            <p class="signature-area">নিবন্ধকের স্বাক্ষর ও সিল</p>
        </div>
    </div>
</div>

<script>
function generatePDF() {
    const appId = document.getElementById('app_id').value;
    const appDate = document.getElementById('app_date').value;
    const brNum = document.getElementById('br_num').value;
    const brDate = document.getElementById('br_date').value;
    const officeAddress = document.getElementById('office_address').value;
    const personName = document.getElementById('person_name').value;
    const birthDate = document.getElementById('birth_date').value;

    // টেবিল ডেটা
    const rows = [
        { subject: "নামের প্রথম অংশ (ইংরেজি)", info: document.getElementById('corr_name_en').value, cause: document.getElementById('cause_name_en').value },
        { subject: "পিতার নাম (বাংলা)", info: document.getElementById('corr_fat_bn').value, cause: document.getElementById('cause_fat').value },
        { subject: "পিতার নাম (ইংরেজি)", info: document.getElementById('corr_fat_en').value, cause: document.getElementById('cause_fat').value },
        { subject: "মাতার নাম (বাংলা)", info: document.getElementById('corr_mot_bn').value, cause: document.getElementById('cause_mot').value },
        { subject: "মাতার নাম (ইংরেজি)", info: document.getElementById('corr_mot_en').value, cause: document.getElementById('cause_mot').value },
        { subject: "জন্মস্থান বাংলায়", info: document.getElementById('p_birth_bn').value, cause: "" },
        { subject: "স্থায়ী ঠিকানা বাংলায়", info: document.getElementById('p_perm_bn').value, cause: "" },
        { subject: "বর্তমান ঠিকানা বাংলায়", info: document.getElementById('p_curr_bn').value, cause: "" }
    ];

    // PDF টেমপ্লেটে ডেটা সেট করা
    document.getElementById('pdf_app_id').innerText = appId;
    document.getElementById('pdf_app_date').innerText = appDate;
    document.getElementById('pdf_br_num').innerText = brNum;
    document.getElementById('pdf_br_date').innerText = brDate;
    document.getElementById('pdf_office_address').innerText = officeAddress;
    document.getElementById('pdf_person_name').innerText = personName;
    document.getElementById('pdf_birth_date').innerText = birthDate;

    // টেবিল তৈরি
    let tableHtml = "";
    rows.forEach(row => {
        tableHtml += `<tr>
            <td>${row.subject}</td>
            <td>${row.info}</td>
            <td>${row.cause}</td>
        </tr>`;
    });
    document.getElementById('pdf_table_body').innerHTML = tableHtml;

    const element = document.getElementById('pdf-template');
    element.style.display = 'block';

    const opt = {
        margin: [12, 15, 12, 15],
        filename: `জন্ম_সনদ_সংশোধন_${appId}.pdf`,
        image: { type: 'jpeg', quality: 0.98 },
        html2canvas: { scale: 2, useCORS: true },
        jsPDF: { unit: 'mm', format: 'a4', orientation: 'portrait' }
    };

    html2pdf().set(opt).from(element).save().then(() => {
        element.style.display = 'none';
    });
}
</script>
</body>
</html>
