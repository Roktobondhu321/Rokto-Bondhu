# Rokto-Bondhu<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Rokto Bondhu</title>

<style>
*{
    box-sizing:border-box;
    margin:0;
    padding:0;
    font-family:Arial,"Noto Sans Bengali",sans-serif;
}

body{
    background:#f5f6fa;
    color:#222;
    padding-bottom:80px;
}

header{
    background:linear-gradient(135deg,#d90429,#ef233c);
    color:white;
    padding:24px 18px;
    border-radius:0 0 25px 25px;
}

.logo{
    display:flex;
    align-items:center;
    gap:12px;
}

.logo-icon{
    width:52px;
    height:52px;
    background:white;
    color:#d90429;
    border-radius:50%;
    display:flex;
    justify-content:center;
    align-items:center;
    font-size:27px;
}

.logo h1{
    font-size:25px;
}

.logo p{
    font-size:13px;
    opacity:.9;
}

.container{
    max-width:600px;
    margin:auto;
    padding:18px;
}

.page{
    display:none;
}

.page.active{
    display:block;
}

.card{
    background:white;
    border-radius:18px;
    padding:18px;
    margin-bottom:16px;
    box-shadow:0 5px 18px rgba(0,0,0,.07);
}

.card h2{
    margin-bottom:15px;
}

button{
    border:none;
    border-radius:12px;
    padding:13px 16px;
    font-size:15px;
    font-weight:bold;
    cursor:pointer;
}

button:disabled{
    opacity:.6;
}

.primary{
    background:#d90429;
    color:white;
}

.secondary{
    background:#ffe5e9;
    color:#d90429;
}

.green{
    background:#16a34a;
    color:white;
}

.gray{
    background:#e5e7eb;
    color:#374151;
}

.danger{
    background:#fee2e2;
    color:#b91c1c;
}

.full{
    width:100%;
    margin-top:10px;
}

input,
select{
    width:100%;
    padding:13px;
    margin:7px 0 14px;
    border:1px solid #ddd;
    border-radius:10px;
    font-size:15px;
    background:white;
}

select:disabled{
    background:#f1f1f1;
    color:#999;
}

label{
    font-size:14px;
    font-weight:bold;
}

.address-title,
.health-title{
    color:#d90429;
    margin-bottom:10px;
}

.address-info,
.health-info{
    background:#fff7ed;
    color:#9a3412;
    padding:12px;
    border-radius:10px;
    font-size:13px;
    line-height:1.6;
    margin-bottom:15px;
}

.health-item{
    display:flex;
    align-items:flex-start;
    gap:10px;
    padding:12px 8px;
    border-bottom:1px solid #eee;
}

.health-item input{
    width:20px;
    height:20px;
    margin:0;
    accent-color:#d90429;
}

.warning{
    display:none;
    background:#fee2e2;
    color:#991b1b;
    padding:14px;
    border-radius:12px;
    margin-top:15px;
    line-height:1.6;
}

.success{
    display:none;
    background:#dcfce7;
    color:#166534;
    padding:14px;
    border-radius:12px;
    margin-bottom:15px;
}

.badge{
    display:inline-block;
    padding:6px 10px;
    border-radius:20px;
    font-size:12px;
    font-weight:bold;
}

.available{
    background:#dcfce7;
    color:#15803d;
}

.unavailable{
    background:#fee2e2;
    color:#b91c1c;
}

.review{
    background:#fef3c7;
    color:#92400e;
}

.donor{
    border-left:5px solid #d90429;
}

.bottom-nav{
    position:fixed;
    bottom:0;
    left:0;
    right:0;
    height:70px;
    background:white;
    box-shadow:0 -3px 15px rgba(0,0,0,.1);
    display:flex;
    justify-content:space-around;
    align-items:center;
    z-index:100;
}

.nav-btn{
    background:none;
    color:#777;
    font-size:12px;
    padding:5px;
}

.nav-btn span{
    display:block;
    font-size:22px;
}

.nav-btn.active{
    color:#d90429;
}

.empty,
.loading{
    text-align:center;
    padding:25px;
    color:#777;
}

.stat-box{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:10px;
}

.stat{
    background:white;
    padding:15px 5px;
    text-align:center;
    border-radius:15px;
    box-shadow:0 4px 12px rgba(0,0,0,.06);
}

.stat strong{
    display:block;
    color:#d90429;
    font-size:22px;
}

/* PROFILE */

.profile-top{
    text-align:center;
    margin-bottom:18px;
}

.profile-photo{
    width:120px;
    height:120px;
    border-radius:50%;
    object-fit:cover;
    border:5px solid #ffe5e9;
    display:block;
    margin:0 auto 12px;
    background:#f3f4f6;
}

.profile-placeholder{
    width:120px;
    height:120px;
    border-radius:50%;
    background:#ffe5e9;
    color:#d90429;
    display:flex;
    justify-content:center;
    align-items:center;
    font-size:48px;
    margin:0 auto 12px;
}

.profile-address{
    background:#f8f9fa;
    padding:14px;
    border-radius:12px;
    line-height:1.8;
    margin-top:12px;
}

.profile-line{
    padding:10px 0;
    border-bottom:1px solid #eee;
}

.donation-box{
    background:#fff7ed;
    padding:15px;
    border-radius:14px;
    margin-top:18px;
    border:1px solid #fed7aa;
}

.donation-box h3{
    color:#9a3412;
    margin-bottom:8px;
}

.hold-box{
    background:#fef3c7;
    color:#92400e;
    padding:14px;
    border-radius:12px;
    margin-top:15px;
    line-height:1.7;
}

.available-box{
    background:#dcfce7;
    color:#166534;
    padding:14px;
    border-radius:12px;
    margin-top:15px;
    line-height:1.7;
}

.photo-input{
    background:#f8f9fa;
    padding:12px;
    border-radius:12px;
    margin-top:10px;
}

.photo-input input{
    margin-bottom:0;
}

</style>


<!-- ================= FIREBASE ================= -->

<script type="module">

import {
    initializeApp
}
from
"https://www.gstatic.com/firebasejs/12.1.0/firebase-app.js";


import {
    getFirestore,
    collection,
    addDoc,
    getDocs,
    doc,
    updateDoc,
    deleteField
}
from
"https://www.gstatic.com/firebasejs/12.1.0/firebase-firestore.js";


import {
    getStorage,
    ref,
    uploadBytes,
    getDownloadURL,
    deleteObject
}
from
"https://www.gstatic.com/firebasejs/12.1.0/firebase-storage.js";


/* =================================================
   🔥 FIREBASE CONFIG
   এখানে তোমার Firebase Config বসাবে
================================================= */

const firebaseConfig = {

    apiKey:
    "YOUR_API_KEY",

    authDomain:
    "YOUR_PROJECT.firebaseapp.com",

    projectId:
    "YOUR_PROJECT_ID",

    storageBucket:
    "YOUR_PROJECT.firebasestorage.app",

    messagingSenderId:
    "YOUR_MESSAGING_SENDER_ID",

    appId:
    "YOUR_APP_ID"

};


/* ================= FIREBASE START ================= */

const app =
initializeApp(firebaseConfig);

const db =
getFirestore(app);

const storage =
getStorage(app);


window.db = db;

window.storage = storage;

window.donorCollection =
collection(db,"donors");

window.firebaseAddDonor =
addDoc;

window.firebaseGetDocs =
getDocs;

window.firebaseDoc =
doc;

window.firebaseUpdateDoc =
updateDoc;

window.firebaseDeleteField =
deleteField;

window.firebaseStorageRef =
ref;

window.firebaseUploadBytes =
uploadBytes;

window.firebaseGetDownloadURL =
getDownloadURL;

window.firebaseDeleteObject =
deleteObject;

</script>

</head>


<body>


<!-- =================================================
HEADER
================================================= -->

<header>

<div class="logo">

<div class="logo-icon">
🩸
</div>

<div>

<h1>Rokto Bondhu</h1>

<p>
রক্ত দিন, জীবন বাঁচান ❤️
</p>

</div>

</div>

</header>


<!-- =================================================
HOME
================================================= -->

<section
id="home"
class="page active">

<div class="container">

<div class="card">

<h2>
🩸 আপনাকে কীভাবে সাহায্য করতে পারি?
</h2>

<button
class="primary full"
onclick="showPage('search')">

🔎 রক্ত খুঁজুন

</button>

<button
class="secondary full"
onclick="showPage('register')">

❤️ Donor হিসেবে নিবন্ধন করুন

</button>

</div>


<div class="card">

<h2>
❤️ Rokto Bondhu
</h2>

<p>

একজন মানুষের এক ব্যাগ রক্ত
আরেকজন মানুষের জীবন বাঁচাতে পারে।

</p>

</div>


<div class="stat-box">

<div class="stat">

<strong id="totalDonor">
0
</strong>

Donor

</div>


<div class="stat">

<strong id="availableDonor">
0
</strong>

Available

</div>


<div class="stat">

<strong>
8
</strong>

Blood Group

</div>

</div>

</div>

</section>


<!-- =================================================
SEARCH
================================================= -->

<section
id="search"
class="page">

<div class="container">

<div class="card">

<h2>
🔎 রক্ত খুঁজুন
</h2>

<label>
Blood Group
</label>

<select id="searchBlood">

<option value="">
সব গ্রুপ
</option>

<option value="A+">A+</option>
<option value="A-">A-</option>
<option value="B+">B+</option>
<option value="B-">B-</option>
<option value="AB+">AB+</option>
<option value="AB-">AB-</option>
<option value="O+">O+</option>
<option value="O-">O-</option>

</select>


<label>
এলাকা
</label>

<input
id="searchLocation"
placeholder="জেলা / উপজেলা / ইউনিয়ন / গ্রামের নাম লিখুন"
>


<button
class="primary full"
onclick="searchDonors()">

🔎 Donor খুঁজুন

</button>

</div>


<div id="searchResults">

<div class="empty">

Blood Group এবং এলাকা দিয়ে
Donor খুঁজুন।

</div>

</div>

</div>

</section>


<!-- =================================================
REGISTER
================================================= -->

<section
id="register"
class="page">

<div class="container">

<div class="card">

<h2>
❤️ Donor Registration
</h2>


<div
id="registerSuccess"
class="success">

✅ Registration সফল হয়েছে!

</div>


<form
id="donorForm">


<label>
পূর্ণ নাম
</label>

<input
id="name"
required
placeholder="আপনার নাম"
>


<label>
বয়স
</label>

<input
id="age"
type="number"
min="18"
required
placeholder="বয়স"
>


<label>
ফোন নম্বর
</label>

<input
id="phone"
type="tel"
required
placeholder="01XXXXXXXXX"
>


<!-- ADDRESS -->

<div
class="card"
style="margin-top:15px;background:#fafafa;box-shadow:none;">

<h3 class="address-title">
📍 Donor-এর ঠিকানা
</h3>


<div class="address-info">

আপনার ঠিকানা ধাপে ধাপে নির্বাচন করুন:

<br>

<strong>
বিভাগ → জেলা → উপজেলা → ইউনিয়ন → গ্রাম
</strong>

</div>


<label>
বিভাগ
</label>

<select
id="division"
required>

<option value="">
বিভাগ নির্বাচন করুন
</option>

</select>


<label>
জেলা
</label>

<select
id="district"
required
disabled>

<option value="">
আগে বিভাগ নির্বাচন করুন
</option>

</select>


<label>
উপজেলা
</label>

<select
id="upazila"
required
disabled>

<option value="">
আগে জেলা নির্বাচন করুন
</option>

</select>


<label>
ইউনিয়ন
</label>

<select
id="union"
required
disabled>

<option value="">
আগে উপজেলা নির্বাচন করুন
</option>

</select>


<label>
গ্রাম
</label>

<input
id="village"
required
placeholder="আপনার গ্রামের নাম লিখুন"
>

</div>


<!-- BLOOD -->

<label>
Blood Group
</label>

<select
id="blood"
required>

<option value="">
Blood Group নির্বাচন করুন
</option>

<option value="A+">A+</option>
<option value="A-">A-</option>
<option value="B+">B+</option>
<option value="B-">B-</option>
<option value="AB+">AB+</option>
<option value="AB-">AB-</option>
<option value="O+">O+</option>
<option value="O-">O-</option>

</select>


<label>
সর্বশেষ কবে রক্ত দিয়েছেন?
</label>

<input
id="lastDonation"
type="date"
>


<!-- HEALTH -->

<div
class="card"
style="margin-top:20px;">

<h2 class="health-title">
🩺 স্বাস্থ্য সম্পর্কিত তথ্য
</h2>


<div class="health-info">

নিচের কোনো সমস্যা থাকলে টিক দিন।

<br><br>

এই তথ্য শুধুমাত্র প্রাথমিক screening-এর জন্য।
চূড়ান্তভাবে রক্ত দেওয়া যাবে কি না তা
রক্তদান কেন্দ্র/চিকিৎসকের screening-এর মাধ্যমে
নির্ধারণ করতে হবে।

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="hepatitis">

<span>
Hepatitis B / Hepatitis C অথবা গুরুতর লিভারের সংক্রমণ
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="hiv">

<span>
HIV/AIDS অথবা HIV positive
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="diabetes">

<span>
Diabetes
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="hypertension">

<span>
উচ্চ রক্তচাপ / High Blood Pressure
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="heart">

<span>
গুরুতর হৃদরোগ
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="kidney">

<span>
গুরুতর কিডনি রোগ
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="blood_disorder">

<span>
রক্ত জমাট বাঁধার সমস্যা / Bleeding Disorder
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="anemia">

<span>
রক্তস্বল্পতা / Anaemia
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="cancer">

<span>
ক্যান্সার
</span>

</div>


<div class="health-item">

<input
type="checkbox"
name="healthProblem"
value="infection">

<span>
বর্তমানে জ্বর, ফ্লু বা অন্য কোনো সংক্রমণ আছে
</span>

</div>


<div
id="healthWarning"
class="warning">

⚠️
<strong>
Medical Review Required
</strong>

<br><br>

আপনার স্বাস্থ্য তথ্যের কারণে
রক্ত দেওয়ার আগে চিকিৎসক বা অনুমোদিত
রক্তদান কেন্দ্রের মাধ্যমে eligibility
যাচাই করা প্রয়োজন।

</div>

</div>


<div
class="health-item"
style="margin-top:10px;">

<input
type="checkbox"
id="healthConfirm"
required>

<span>

আমি আমার স্বাস্থ্য সম্পর্কিত তথ্য
সঠিকভাবে দিয়েছি এবং প্রয়োজনে
চিকিৎসকের screening গ্রহণ করব।

</span>

</div>


<button
class="primary full"
type="submit">

❤️ Donor হিসেবে নিবন্ধন করুন

</button>


</form>

</div>

</div>

</section>


<!-- =================================================
PROFILE
================================================= -->

<section
id="profile"
class="page">

<div class="container">

<div class="card">

<h2>
👤 My Profile
</h2>


<div id="profileContent">

<div class="empty">

এখনো কোনো Donor Registration
করা হয়নি।

</div>

</div>

</div>

</div>

</section>


<!-- =================================================
BOTTOM NAV
================================================= -->

<nav class="bottom-nav">

<button
class="nav-btn active"
onclick="showPage('home',this)">

<span>🏠</span>

Home

</button>


<button
class="nav-btn"
onclick="showPage('search',this)">

<span>🔎</span>

Search

</button>


<button
class="nav-btn"
onclick="showPage('register',this)">

<span>❤️</span>

Donor

</button>


<button
class="nav-btn"
onclick="showPage('profile',this)">

<span>👤</span>

Profile

</button>

</nav>


<!-- =================================================
JAVASCRIPT
================================================= -->

<script>

let donors = [];

let currentDonor = null;

let bdData = [];


/* =================================================
PAGE NAVIGATION
================================================= */

function showPage(pageId,button){

    document
    .querySelectorAll(".page")
    .forEach(page=>{
        page.classList.remove("active");
    });


    document
    .getElementById(pageId)
    .classList.add("active");


    document
    .querySelectorAll(".nav-btn")
    .forEach(btn=>{
        btn.classList.remove("active");
    });


    if(button){
        button.classList.add("active");
    }


    if(pageId==="profile"){
        loadProfile();
    }


    window.scrollTo(0,0);

}


/* =================================================
HEALTH
================================================= */

function checkHealth(donor){

    return donor.healthProblems &&
           donor.healthProblems.length>0;

}


/* =================================================
DONOR STATUS
================================================= */

function getStatus(donor){

    if(checkHealth(donor)){

        return {
            available:false,
            medicalReview:true,
            date:null
        };

    }


    if(!donor.lastDonation){

        return {
            available:true,
            medicalReview:false,
            date:null
        };

    }


    let donationDate =
        new Date(
            donor.lastDonation+"T00:00:00"
        );


    let availableDate =
        new Date(donationDate);


    availableDate.setMonth(
        availableDate.getMonth()+4
    );


    let today =
        new Date();

    today.setHours(0,0,0,0);


    if(today>=availableDate){

        return {
            available:true,
            medicalReview:false,
            date:availableDate
        };

    }


    return {
        available:false,
        medicalReview:false,
        date:availableDate
    };

}


/* =================================================
DATE
================================================= */

function formatDate(date){

    if(!date){
        return "-";
    }

    return new Date(date)
    .toLocaleDateString(
        "bn-BD",
        {
            year:"numeric",
            month:"long",
            day:"numeric"
        }
    );

}


function getTodayDate(){

    const d=new Date();

    return d.getFullYear()+"-"+
    String(d.getMonth()+1).padStart(2,"0")+"-"+
    String(d.getDate()).padStart(2,"0");

}


/* =================================================
BANGLADESH ADDRESS
================================================= */

const BD_GEO_URL =
"https://iqbalhasandev.github.io/bangladesh-geo-json/bangladesh-geo.json";


async function loadBangladeshAddress(){

    try{

        const response =
            await fetch(BD_GEO_URL);

        if(!response.ok){
            throw new Error("Address failed");
        }

        bdData =
            await response.json();


        const division =
            document.getElementById("division");


        division.innerHTML =
        `
        <option value="">
            বিভাগ নির্বাচন করুন
        </option>
        `;


        bdData.forEach(div=>{

            division.innerHTML+=
            `
            <option value="${escapeHTML(div.bn_name)}">
                ${escapeHTML(div.bn_name)}
            </option>
            `;

        });

    }

    catch(error){

        console.error(error);

        alert(
            "বাংলাদেশের ঠিকানা লোড করা যায়নি।"
        );

    }

}


/* =================================================
DIVISION
================================================= */

document
.getElementById("division")
.addEventListener("change",function(){

    const selectedDivision =
        bdData.find(
            d=>d.bn_name===this.value
        );


    const district =
        document.getElementById("district");

    const upazila =
        document.getElementById("upazila");

    const union =
        document.getElementById("union");


    district.innerHTML =
    `<option value="">
    জেলা নির্বাচন করুন
    </option>`;

    upazila.innerHTML =
    `<option value="">
    আগে জেলা নির্বাচন করুন
    </option>`;

    union.innerHTML =
    `<option value="">
    আগে উপজেলা নির্বাচন করুন
    </option>`;


    district.disabled=true;
    upazila.disabled=true;
    union.disabled=true;


    if(!selectedDivision){
        return;
    }


    district.disabled=false;


    selectedDivision.districts
    .forEach(d=>{

        district.innerHTML+=
        `
        <option value="${escapeHTML(d.bn_name)}">
            ${escapeHTML(d.bn_name)}
        </option>
        `;

    });

});


/* =================================================
DISTRICT
================================================= */

document
.getElementById("district")
.addEventListener("change",function(){

    const selectedDivision =
        bdData.find(
            d =>
            d.bn_name ===
            document.getElementById("division").value
        );


    const selectedDistrict =
        selectedDivision?.districts.find(
            d=>d.bn_name===this.value
        );


    const upazila =
        document.getElementById("upazila");

    const union =
        document.getElementById("union");


    upazila.innerHTML =
    `<option value="">
    উপজেলা নির্বাচন করুন
    </option>`;

    union.innerHTML =
    `<option value="">
    আগে উপজেলা নির্বাচন করুন
    </option>`;


    upazila.disabled=true;
    union.disabled=true;


    if(!selectedDistrict){
        return;
    }


    upazila.disabled=false;


    selectedDistrict.upazilas
    .forEach(u=>{

        upazila.innerHTML+=
        `
        <option value="${escapeHTML(u.bn_name)}">
            ${escapeHTML(u.bn_name)}
        </option>
        `;

    });

});


/* =================================================
UPAZILA
================================================= */

document
.getElementById("upazila")
.addEventListener("change",function(){

    const selectedDivision =
        bdData.find(
            d =>
            d.bn_name ===
            document.getElementById("division").value
        );


    const selectedDistrict =
        selectedDivision?.districts.find(
            d =>
            d.bn_name ===
            document.getElementById("district").value
        );


    const selectedUpazila =
        selectedDistrict?.upazilas.find(
            u=>u.bn_name===this.value
        );


    const union =
        document.getElementById("union");


    union.innerHTML =
    `<option value="">
    ইউনিয়ন নির্বাচন করুন
    </option>`;

    union.disabled=true;


    if(!selectedUpazila){
        return;
    }


    if(
        selectedUpazila.unions &&
        selectedUpazila.unions.length
    ){

        union.disabled=false;


        selectedUpazila.unions
        .forEach(u=>{

            union.innerHTML+=
            `
            <option value="${escapeHTML(u.bn_name)}">
                ${escapeHTML(u.bn_name)}
            </option>
            `;

        });

    }

});


/* =================================================
LOAD DONORS
================================================= */

async function loadDonors(){

    try{

        const snapshot =
            await window.firebaseGetDocs(
                window.donorCollection
            );


        donors=[];


        snapshot.forEach(docItem=>{

            donors.push({
                id:docItem.id,
                ...docItem.data()
            });

        });


        const savedId =
            localStorage.getItem(
                "roktoBondhuDonorId"
            );


        if(savedId){

            currentDonor =
                donors.find(
                    d=>d.id===savedId
                ) || null;

        }


        updateStats();

    }

    catch(error){

        console.error(error);

    }

}


/* =================================================
REGISTRATION
================================================= */

document
.getElementById("donorForm")
.addEventListener(
"submit",
async function(e){

    e.preventDefault();


    let healthProblems=[];


    document
    .querySelectorAll(
        'input[name="healthProblem"]:checked'
    )
    .forEach(item=>{
        healthProblems.push(item.value);
    });


    const division =
        document.getElementById("division").value;

    const district =
        document.getElementById("district").value;

    const upazila =
        document.getElementById("upazila").value;

    const union =
        document.getElementById("union").value;

    const village =
        document.getElementById("village").value.trim();


    const location=[
        division,
        district,
        upazila,
        union,
        village
    ]
    .filter(Boolean)
    .join(", ");


    const donor={

        name:
        document.getElementById("name").value.trim(),

        age:
        document.getElementById("age").value,

        phone:
        document.getElementById("phone").value.trim(),

        division:division,

        district:district,

        upazila:upazila,

        union:union,

        village:village,

        location:location,

        blood:
        document.getElementById("blood").value,

        lastDonation:
        document.getElementById("lastDonation").value,

        healthProblems:healthProblems,

        photoURL:"",

        createdAt:
        new Date().toISOString()

    };


    try{

        const docRef =
            await window.firebaseAddDonor(
                window.donorCollection,
                donor
            );


        donor.id=docRef.id;

        currentDonor=donor;


        localStorage.setItem(
            "roktoBondhuDonorId",
            docRef.id
        );


        await loadDonors();


        document
        .getElementById("registerSuccess")
        .style.display="block";


        this.reset();


        resetAddress();


        document
        .getElementById("healthWarning")
        .style.display="none";


        alert(
            "❤️ Donor Registration সফল হয়েছে!"
        );


        showPage("profile");

        loadProfile();


    }

    catch(error){

        console.error(error);

        alert(
            "❌ Registration করা যায়নি। Firebase Config পরীক্ষা করুন।"
        );

    }

});


/* =================================================
HEALTH WARNING
================================================= */

document
.querySelectorAll(
    'input[name="healthProblem"]'
)
.forEach(box=>{

    box.addEventListener(
        "change",
        function(){

            const count =
                document
                .querySelectorAll(
                    'input[name="healthProblem"]:checked'
                ).length;


            document
            .getElementById("healthWarning")
            .style.display =
                count>0
                ?"block"
                :"none";

        }
    );

});


/* =================================================
RESET ADDRESS
================================================= */

function resetAddress(){

    document.getElementById("district").innerHTML=
    `<option value="">
    আগে বিভাগ নির্বাচন করুন
    </option>`;

    document.getElementById("upazila").innerHTML=
    `<option value="">
    আগে জেলা নির্বাচন করুন
    </option>`;

    document.getElementById("union").innerHTML=
    `<option value="">
    আগে উপজেলা নির্বাচন করুন
    </option>`;


    document.getElementById("district").disabled=true;
    document.getElementById("upazila").disabled=true;
    document.getElementById("union").disabled=true;

}


/* =================================================
SEARCH
================================================= */

async function searchDonors(){

    const blood =
        document.getElementById("searchBlood").value;


    const location =
        document
        .getElementById("searchLocation")
        .value
        .trim()
        .toLowerCase();


    document
    .getElementById("searchResults")
    .innerHTML=
    `
    <div class="card loading">
        🔄 Donor খোঁজা হচ্ছে...
    </div>
    `;


    await loadDonors();


    const results =
        donors.filter(donor=>{

            const status =
                getStatus(donor);


            const bloodMatch =
                !blood ||
                donor.blood===blood;


            const address=[
                donor.division,
                donor.district,
                donor.upazila,
                donor.union,
                donor.village
            ]
            .filter(Boolean)
            .join(" ")
            .toLowerCase();


            const oldLocation =
                String(
                    donor.location||""
                )
                .toLowerCase();


            const locationMatch =
                !location ||
                address.includes(location) ||
                oldLocation.includes(location);


            return(
                bloodMatch &&
                locationMatch &&
                status.available &&
                !status.medicalReview
            );

        });


    let html="";


    if(results.length===0){

        html=
        `
        <div class="card empty">

            😔

            <br><br>

            এই মুহূর্তে কোনো
            Available Donor পাওয়া যায়নি।

        </div>
        `;

    }

    else{

        results.forEach(donor=>{

            let address=[
                donor.division,
                donor.district,
                donor.upazila,
                donor.union,
                donor.village
            ]
            .filter(Boolean)
            .join(" → ");


            if(!address){
                address=donor.location||"-";
            }


            let photo="";


            if(donor.photoURL){

                photo=
                `
                <img
                src="${escapeHTML(donor.photoURL)}"
                style="
                width:70px;
                height:70px;
                border-radius:50%;
                object-fit:cover;
                float:right;
                border:3px solid #ffe5e9;
                ">
                `;

            }


            html+=
            `
            <div class="card donor">

                ${photo}

                <h3>
                    ${escapeHTML(donor.name)}
                </h3>

                <br>

                <span class="badge available">
                    ✓ Available
                </span>


                <p style="margin-top:12px">

                    🩸
                    <strong>
                    ${escapeHTML(donor.blood)}
                    </strong>

                </p>


                <p>
                    📍
                    ${escapeHTML(address)}
                </p>


                <p>
                    📞
                    ${escapeHTML(donor.phone)}
                </p>


                <button
                class="primary full"
                onclick="callDonor('${escapeHTML(donor.phone)}')">

                    📞 Call Donor

                </button>

            </div>
            `;

        });

    }


    document
    .getElementById("searchResults")
    .innerHTML=html;

}


/* =================================================
CALL DONOR
================================================= */

function callDonor(phone){

    window.location.href=
        "tel:"+phone;

}


/* =================================================
PROFILE
================================================= */

function loadProfile(){

    const box =
        document.getElementById(
            "profileContent"
        );


    if(!currentDonor){

        box.innerHTML=
        `
        <div class="empty">

            এখনো কোনো Donor Registration
            করা হয়নি।

        </div>
        `;

        return;

    }


    const donor=currentDonor;


    const status =
        getStatus(donor);


    let address=[
        donor.division,
        donor.district,
        donor.upazila,
        donor.union,
        donor.village
    ]
    .filter(Boolean)
    .join(" → ");


    if(!address){
        address=donor.location||"-";
    }


    let photoHTML;


    if(donor.photoURL){

        photoHTML=
        `
        <img
        src="${escapeHTML(donor.photoURL)}"
        class="profile-photo">
        `;

    }

    else{

        photoHTML=
        `
        <div class="profile-placeholder">
            👤
        </div>
        `;

    }


    let statusHTML;


    if(status.medicalReview){

        statusHTML=
        `
        <div class="hold-box">

            ⚠️
            <strong>
            Medical Review Required
            </strong>

            <br><br>

            আপনার স্বাস্থ্য তথ্যের কারণে
            রক্ত দেওয়ার আগে চিকিৎসক/
            অনুমোদিত রক্তদান কেন্দ্রের
            screening প্রয়োজন।

        </div>
        `;

    }

    else if(status.available){

        statusHTML=
        `
        <div class="available-box">

            ✅
            <strong>
            আপনি বর্তমানে Available Donor
            </strong>

            <br><br>

            প্রয়োজন হলে রক্তদানের জন্য
            যোগাযোগ করা যেতে পারে।

        </div>
        `;

    }

    else{

        statusHTML=
        `
        <div class="hold-box">

            ⏳
            <strong>
            আপনি বর্তমানে ৪ মাসের Hold-এ আছেন
            </strong>

            <br><br>

            আবার রক্ত দেওয়ার সম্ভাব্য তারিখ:

            <br>

            <strong>
            ${formatDate(status.date)}
            </strong>

        </div>
        `;

    }


    box.innerHTML=
    `

    <div class="profile-top">

        ${photoHTML}

        <h2>
            ${escapeHTML(donor.name)}
        </h2>

        <p style="color:#777;margin-top:5px">

            🩸
            ${escapeHTML(donor.blood)}

        </p>

    </div>


    <div class="profile-line">

        <b>👤 বয়স:</b>

        ${escapeHTML(donor.age)}

    </div>


    <div class="profile-line">

        <b>📞 ফোন:</b>

        ${escapeHTML(donor.phone)}

    </div>


    <div class="profile-address">

        <b>
        📍 ঠিকানা
        </b>

        <br>

        ${escapeHTML(address)}

    </div>


    <div class="profile-line">

        <b>
        🩸 Blood Group:
        </b>

        ${escapeHTML(donor.blood)}

    </div>


    <div class="profile-line">

        <b>
        🩸 সর্বশেষ রক্তদান:
        </b>

        ${formatDate(donor.lastDonation)}

    </div>


    ${statusHTML}


    <!-- PHOTO -->

    <div class="donation-box">

        <h3>
        📷 Profile Photo
        </h3>

        <p
        style="font-size:13px;color:#777;line-height:1.6">

            ছবি দেওয়া Optional।
            চাইলে দিতে পারেন,
            আবার না দিলেও Profile ব্যবহার করতে পারবেন।

        </p>


        <div class="photo-input">

            <input
            type="file"
            id="profilePhotoInput"
            accept="image/*">

        </div>


        <button
        class="primary full"
        onclick="uploadProfilePhoto()">

            📷 ছবি আপলোড / পরিবর্তন করুন

        </button>


        ${
            donor.photoURL
            ?
            `
            <button
            class="danger full"
            onclick="removeProfilePhoto()">

                🗑️ ছবি মুছে ফেলুন

            </button>
            `
            :
            ""
        }

    </div>


    <!-- DONATION -->

    <div class="donation-box">

        <h3>
        🩸 রক্তদান আপডেট
        </h3>


        <p
        style="font-size:13px;color:#777;line-height:1.6">

            রক্তদান করার পর এখানে
            রক্তদানের তারিখ দিয়ে Update করুন।
            সেই তারিখ থেকে ৪ মাস Hold শুরু হবে।

        </p>


        <label>
        রক্তদানের তারিখ
        </label>


        <input
        type="date"
        id="donationDate"
        value="${getTodayDate()}">


        <button
        class="green full"
        onclick="updateDonationDate()">

            🩸 আজ রক্ত দিয়েছি — Update করুন

        </button>


        ${
            donor.lastDonation
            ?
            `
            <button
            class="gray full"
            onclick="changeDonationDate()">

                ✏️ রক্তদানের তারিখ পরিবর্তন করুন

            </button>
            `
            :
            ""
        }

    </div>


    <button
    class="secondary full"
    onclick="refreshMyProfile()">

        🔄 Profile Refresh

    </button>

    `;

}


/* =================================================
UPDATE DONATION
================================================= */

async function updateDonationDate(){

    if(!currentDonor){

        alert(
            "❌ Donor Profile পাওয়া যায়নি।"
        );

        return;

    }


    const date =
        document
        .getElementById("donationDate")
        .value;


    if(!date){

        alert(
            "⚠️ রক্তদানের তারিখ নির্বাচন করুন।"
        );

        return;

    }


    const selected =
        new Date(
            date+"T00:00:00"
        );


    const today =
        new Date();


    today.setHours(0,0,0,0);


    if(selected>today){

        alert(
            "⚠️ ভবিষ্যতের তারিখ দেওয়া যাবে না।"
        );

        return;

    }


    if(
        !confirm(
            "আপনি কি নিশ্চিত যে এই তারিখে রক্তদান করেছেন?"
        )
    ){
        return;
    }


    try{

        const donorRef =
            window.firebaseDoc(
                window.db,
                "donors",
                currentDonor.id
            );


        await window.firebaseUpdateDoc(
            donorRef,
            {
                lastDonation:date,

                lastDonationUpdatedAt:
                new Date().toISOString()
            }
        );


        currentDonor.lastDonation=date;


        const index =
            donors.findIndex(
                d=>d.id===currentDonor.id
            );


        if(index!==-1){

            donors[index].lastDonation=date;

        }


        updateStats();

        loadProfile();


        alert(
            "🩸 রক্তদানের তথ্য Update হয়েছে।\n\nএখন থেকে ৪ মাসের Hold শুরু হয়েছে।"
        );

    }

    catch(error){

        console.error(error);

        alert(
            "❌ তথ্য Update করা যায়নি।"
        );

    }

}


/* =================================================
CHANGE DATE
================================================= */

function changeDonationDate(){

    updateDonationDate();

}


/* =================================================
UPLOAD PHOTO
================================================= */

async function uploadProfilePhoto(){

    if(!currentDonor){

        alert(
            "❌ Donor Profile পাওয়া যায়নি।"
        );

        return;

    }


    const input =
        document.getElementById(
            "profilePhotoInput"
        );


    if(
        !input ||
        !input.files ||
        !input.files[0]
    ){

        alert(
            "📷 আগে একটি ছবি নির্বাচন করুন।"
        );

        return;

    }


    const file=input.files[0];


    if(!file.type.startsWith("image/")){

        alert(
            "❌ শুধুমাত্র Image দেওয়া যাবে।"
        );

        return;

    }


    if(file.size>5*1024*1024){

        alert(
            "❌ ছবির সাইজ সর্বোচ্চ 5 MB হতে পারবে।"
        );

        return;

    }


    try{

        const extension =
            file.name.split(".").pop();


        const path =
            "donorPhotos/"+
            currentDonor.id+
            "."+
            extension;


        const storageRef =
            window.firebaseStorageRef(
                window.storage,
                path
            );


        await window.firebaseUploadBytes(
            storageRef,
            file
        );


        const url =
            await window.firebaseGetDownloadURL(
                storageRef
            );


        const donorRef =
            window.firebaseDoc(
                window.db,
                "donors",
                currentDonor.id
            );


        await window.firebaseUpdateDoc(
            donorRef,
            {
                photoURL:url,
                photoPath:path
            }
        );


        currentDonor.photoURL=url;
        currentDonor.photoPath=path;


        const index =
            donors.findIndex(
                d=>d.id===currentDonor.id
            );


        if(index!==-1){

            donors[index].photoURL=url;
            donors[index].photoPath=path;

        }


        loadProfile();


        alert(
            "📷 Profile Photo সফলভাবে আপলোড হয়েছে!"
        );

    }

    catch(error){

        console.error(error);

        alert(
            "❌ ছবি আপলোড করা যায়নি। Firebase Storage চালু আছে কিনা দেখুন।"
        );

    }

}


/* =================================================
REMOVE PHOTO
================================================= */

async function removeProfilePhoto(){

    if(!currentDonor){
        return;
    }


    if(
        !confirm(
            "আপনি কি Profile Photo মুছে ফেলতে চান?"
        )
    ){
        return;
    }


    try{

        if(currentDonor.photoPath){

            try{

                const photoRef =
                    window.firebaseStorageRef(
                        window.storage,
                        currentDonor.photoPath
                    );


                await window.firebaseDeleteObject(
                    photoRef
                );

            }

            catch(e){

                console.log(
                    "Photo already deleted."
                );

            }

        }


        const donorRef =
            window.firebaseDoc(
                window.db,
                "donors",
                currentDonor.id
            );


        await window.firebaseUpdateDoc(
            donorRef,
            {
                photoURL:
                window.firebaseDeleteField(),

                photoPath:
                window.firebaseDeleteField()
            }
        );


        delete currentDonor.photoURL;

        delete currentDonor.photoPath;


        const index =
            donors.findIndex(
                d=>d.id===currentDonor.id
            );


        if(index!==-1){

            delete donors[index].photoURL;
            delete donors[index].photoPath;

        }


        loadProfile();


        alert(
            "🗑️ Profile Photo মুছে ফেলা হয়েছে।"
        );

    }

    catch(error){

        console.error(error);

        alert(
            "❌ ছবি মুছে ফেলা যায়নি।"
        );

    }

}


/* =================================================
REFRESH PROFILE
================================================= */

async function refreshMyProfile(){

    await loadDonors();

    loadProfile();

}


/* =================================================
STATISTICS
================================================= */

function updateStats(){

    let available=0;


    donors.forEach(donor=>{

        const status =
            getStatus(donor);


        if(
            status.available &&
            !status.medicalReview
        ){

            available++;

        }

    });


    document
    .getElementById("totalDonor")
    .innerText=donors.length;


    document
    .getElementById("availableDonor")
    .innerText=available;

}


/* =================================================
SECURITY
================================================= */

function escapeHTML(text){

    return String(text??"")
    .replace(/&/g,"&amp;")
    .replace(/</g,"&lt;")
    .replace(/>/g,"&gt;")
    .replace(/"/g,"&quot;")
    .replace(/'/g,"&#039;");

}


/* =================================================
START
================================================= */

setTimeout(
async()=>{
    
    await loadDonors();

    await loadBangladeshAddress();

    if(currentDonor){
        loadProfile();
    }

},
500
);

</script>

</body>
</html>
