<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>PAWSAFE — Smart Pet Recovery</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

<style>

/* =========================
   RESET
========================= */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:Inter,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;
    background:#f7f9f8;
    color:#15201c;
    overflow-x:hidden;
}

a{
    text-decoration:none;
    color:inherit;
}

button{
    font-family:inherit;
}


/* =========================
   VARIABLES
========================= */

:root{
    --green:#19a974;
    --dark:#10201a;
    --light:#e9fff5;
    --text:#15201c;
    --muted:#718079;
    --white:#ffffff;
    --border:#e5ebe8;
}


/* =========================
   NAVBAR
========================= */

.navbar{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    height:76px;
    padding:0 7%;
    display:flex;
    align-items:center;
    justify-content:space-between;
    background:rgba(255,255,255,.82);
    backdrop-filter:blur(18px);
    border-bottom:1px solid rgba(0,0,0,.05);
    z-index:1000;
}

.logo{
    display:flex;
    align-items:center;
    gap:10px;
    font-size:22px;
    font-weight:900;
    letter-spacing:-1px;
}

.logo-icon{
    width:38px;
    height:38px;
    border-radius:12px;
    background:var(--dark);
    display:grid;
    place-items:center;
    color:white;
    font-size:20px;
}

.logo span{
    color:var(--green);
}

.nav-links{
    display:flex;
    align-items:center;
    gap:30px;
}

.nav-links a{
    font-size:14px;
    font-weight:600;
    color:#56645e;
    transition:.25s;
}

.nav-links a:hover{
    color:var(--green);
}

.nav-button{
    border:0;
    background:var(--dark);
    color:white;
    padding:11px 19px;
    border-radius:12px;
    cursor:pointer;
    font-weight:700;
    transition:.25s;
}

.nav-button:hover{
    transform:translateY(-2px);
}


/* =========================
   HERO
========================= */

.hero{
    min-height:760px;
    padding:150px 7% 90px;
    display:grid;
    grid-template-columns:1.05fr .95fr;
    align-items:center;
    gap:60px;
    position:relative;
    overflow:hidden;
    background:
        radial-gradient(circle at 85% 25%,#caffea 0,transparent 28%),
        radial-gradient(circle at 10% 70%,#e4fff4 0,transparent 30%),
        #f8fbfa;
}

.hero::before{
    content:"";
    position:absolute;
    width:450px;
    height:450px;
    border:1px solid rgba(25,169,116,.12);
    border-radius:50%;
    right:-130px;
    top:-100px;
}

.hero-content{
    position:relative;
    z-index:2;
}

.pill{
    display:inline-flex;
    align-items:center;
    gap:8px;
    padding:8px 14px;
    border-radius:30px;
    background:#e1fff1;
    color:#08734e;
    font-size:12px;
    font-weight:800;
    letter-spacing:.5px;
    margin-bottom:24px;
}

.pill-dot{
    width:7px;
    height:7px;
    border-radius:50%;
    background:var(--green);
    box-shadow:0 0 0 5px rgba(25,169,116,.1);
}

.hero h1{
    font-size:clamp(48px,6vw,78px);
    line-height:.98;
    letter-spacing:-4px;
    max-width:700px;
    margin-bottom:26px;
}

.hero h1 span{
    color:var(--green);
}

.hero-description{
    max-width:580px;
    color:#63716b;
    font-size:17px;
    line-height:1.7;
    margin-bottom:34px;
}

.hero-actions{
    display:flex;
    gap:12px;
    flex-wrap:wrap;
}

.primary-btn{
    border:0;
    background:var(--green);
    color:white;
    padding:15px 23px;
    border-radius:14px;
    font-weight:800;
    cursor:pointer;
    box-shadow:0 12px 25px rgba(25,169,116,.2);
    transition:.25s;
}

.primary-btn:hover{
    transform:translateY(-3px);
    box-shadow:0 16px 30px rgba(25,169,116,.27);
}

.secondary-btn{
    border:1px solid var(--border);
    background:white;
    color:var(--dark);
    padding:15px 23px;
    border-radius:14px;
    font-weight:800;
    cursor:pointer;
    transition:.25s;
}

.secondary-btn:hover{
    transform:translateY(-3px);
}


/* =========================
   HERO VISUAL
========================= */

.hero-visual{
    position:relative;
    min-height:470px;
    display:flex;
    justify-content:center;
    align-items:center;
}

.orbit{
    position:absolute;
    width:390px;
    height:390px;
    border:1px dashed rgba(25,169,116,.3);
    border-radius:50%;
    animation:rotate 25s linear infinite;
}

.orbit::after{
    content:"";
    position:absolute;
    width:12px;
    height:12px;
    background:var(--green);
    border-radius:50%;
    top:35px;
    left:40px;
    box-shadow:0 0 0 8px rgba(25,169,116,.12);
}

@keyframes rotate{
    to{transform:rotate(360deg);}
}

.pet-card-hero{
    width:340px;
    padding:25px;
    border-radius:30px;
    background:rgba(255,255,255,.88);
    backdrop-filter:blur(20px);
    border:1px solid rgba(255,255,255,.9);
    box-shadow:0 30px 70px rgba(26,50,42,.14);
    position:relative;
    z-index:3;
    transform:rotate(2deg);
}

.pet-picture{
    height:235px;
    border-radius:22px;
    background:
        linear-gradient(135deg,#dff9ed,#f3fffa);
    display:grid;
    place-items:center;
    font-size:125px;
    margin-bottom:18px;
    overflow:hidden;
}

.pet-name-row{
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.pet-name-row h3{
    font-size:25px;
}

.online{
    font-size:10px;
    font-weight:800;
    color:#08734e;
    background:#e2fff1;
    padding:6px 9px;
    border-radius:20px;
}

.pet-card-hero p{
    color:var(--muted);
    margin-top:6px;
}

.floating-card{
    position:absolute;
    background:white;
    border:1px solid #edf1ef;
    box-shadow:0 18px 40px rgba(20,45,36,.12);
    border-radius:17px;
    padding:14px 17px;
    z-index:5;
}

.location-float{
    left:0;
    bottom:65px;
}

.qr-float{
    right:0;
    top:55px;
}

.float-title{
    font-size:11px;
    color:var(--muted);
    margin-bottom:4px;
}

.float-value{
    font-size:14px;
    font-weight:800;
}


/* =========================
   GENERAL SECTION
========================= */

section{
    padding:100px 7%;
}

.section-heading{
    text-align:center;
    max-width:650px;
    margin:0 auto 55px;
}

.section-heading .mini{
    color:var(--green);
    font-size:12px;
    font-weight:900;
    letter-spacing:1.5px;
    text-transform:uppercase;
    margin-bottom:10px;
}

.section-heading h2{
    font-size:42px;
    letter-spacing:-2px;
    margin-bottom:12px;
}

.section-heading p{
    color:var(--muted);
    line-height:1.6;
}


/* =========================
   HOW IT WORKS
========================= */

.steps{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:20px;
    max-width:1050px;
    margin:auto;
}

.step{
    background:white;
    border:1px solid var(--border);
    border-radius:23px;
    padding:30px;
    transition:.3s;
}

.step:hover{
    transform:translateY(-7px);
    box-shadow:0 20px 45px rgba(20,45,36,.08);
}

.step-number{
    width:45px;
    height:45px;
    border-radius:13px;
    background:#e5fff3;
    color:var(--green);
    display:grid;
    place-items:center;
    font-weight:900;
    margin-bottom:22px;
}

.step-icon{
    font-size:38px;
    margin-bottom:18px;
}

.step h3{
    margin-bottom:9px;
}

.step p{
    color:var(--muted);
    font-size:14px;
    line-height:1.6;
}


/* =========================
   PET PROFILE
========================= */

.profile-section{
    background:#f0f8f4;
}

.profile{
    max-width:1050px;
    margin:auto;
    display:grid;
    grid-template-columns:330px 1fr;
    gap:25px;
}

.profile-left{
    background:var(--dark);
    color:white;
    border-radius:28px;
    padding:25px;
    min-height:430px;
    display:flex;
    flex-direction:column;
    justify-content:space-between;
}

.profile-photo{
    height:250px;
    border-radius:21px;
    background:linear-gradient(145deg,#d9f7e9,#aeeed1);
    display:grid;
    place-items:center;
    font-size:125px;
}

.profile-left h2{
    font-size:30px;
    margin-top:20px;
}

.profile-left p{
    color:#aebdb7;
    margin-top:5px;
}

.verified-badge{
    display:inline-flex;
    margin-top:14px;
    background:rgba(25,169,116,.18);
    color:#61e4af;
    padding:7px 11px;
    border-radius:20px;
    font-size:11px;
    font-weight:800;
}

.profile-right{
    background:white;
    border:1px solid var(--border);
    border-radius:28px;
    padding:32px;
}

.profile-right h3{
    font-size:23px;
    margin-bottom:22px;
}

.info-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:13px;
}

.info{
    padding:18px;
    border:1px solid var(--border);
    border-radius:16px;
}

.info small{
    color:#89948f;
    display:block;
    font-size:11px;
    margin-bottom:6px;
    text-transform:uppercase;
    letter-spacing:.5px;
}

.info strong{
    font-size:15px;
}

.owner-box{
    margin-top:20px;
    padding:20px;
    background:#f4faf7;
    border-radius:17px;
}

.owner-box h4{
    margin-bottom:7px;
}

.owner-box p{
    color:var(--muted);
    line-height:1.5;
    font-size:14px;
}


/* =========================
   LOCATION
========================= */

.location-section{
    background:var(--dark);
    color:white;
}

.location-wrap{
    max-width:1050px;
    margin:auto;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:25px;
}

.location-panel{
    padding:32px;
    border-radius:27px;
    background:#182c25;
    border:1px solid rgba(255,255,255,.08);
}

.location-panel h3{
    font-size:25px;
    margin-bottom:10px;
}

.location-panel>p{
    color:#aebcb6;
    line-height:1.6;
    font-size:14px;
}

.map-box{
    margin-top:25px;
    min-height:220px;
    border-radius:20px;
    background:
        linear-gradient(rgba(16,32,26,.7),rgba(16,32,26,.7)),
        repeating-linear-gradient(
            45deg,
            #274239,
            #274239 2px,
            #213a31 2px,
            #213a31 25px
        );
    display:grid;
    place-items:center;
    position:relative;
    overflow:hidden;
}

.map-pin{
    width:65px;
    height:65px;
    border-radius:50%;
    background:#dffff0;
    color:var(--green);
    display:grid;
    place-items:center;
    font-size:28px;
    box-shadow:0 0 0 14px rgba(223,255,240,.12);
}

.coordinates{
    margin-top:15px;
    padding:14px;
    background:rgba(255,255,255,.06);
    border-radius:12px;
    font-size:13px;
    color:#bdcbc5;
}

.location-actions{
    display:flex;
    gap:10px;
    margin-top:18px;
    flex-wrap:wrap;
}

.location-actions button{
    padding:12px 15px;
    border-radius:11px;
    border:0;
    cursor:pointer;
    font-weight:800;
}

.location-primary{
    background:var(--green);
    color:white;
}

.location-light{
    background:white;
    color:var(--dark);
}


/* =========================
   HOSPITALS
========================= */

.hospital-grid{
    max-width:1050px;
    margin:auto;
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:18px;
}

.hospital{
    background:white;
    border:1px solid var(--border);
    border-radius:23px;
    padding:25px;
    transition:.3s;
}

.hospital:hover{
    transform:translateY(-6px);
    box-shadow:0 18px 40px rgba(20,45,36,.08);
}

.hospital-icon{
    width:50px;
    height:50px;
    border-radius:14px;
    background:#e9fff5;
    display:grid;
    place-items:center;
    font-size:24px;
    margin-bottom:18px;
}

.hospital h3{
    margin-bottom:8px;
}

.hospital p{
    color:var(--muted);
    font-size:13px;
    line-height:1.6;
    margin-bottom:18px;
}

.hospital button{
    width:100%;
    padding:12px;
    border:0;
    border-radius:11px;
    background:#edf9f4;
    color:#08734e;
    font-weight:800;
    cursor:pointer;
}


/* =========================
   QR SECTION
========================= */

.qr-section{
    background:#eafff4;
}

.qr-layout{
    max-width:950px;
    margin:auto;
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:35px;
    align-items:center;
}

.qr-card{
    background:white;
    padding:35px;
    border-radius:28px;
    text-align:center;
    box-shadow:0 20px 50px rgba(20,60,45,.09);
}

.qr-card h3{
    font-size:24px;
}

.qr-card p{
    color:var(--muted);
    font-size:13px;
    margin-top:7px;
}

#qrcode{
    margin:25px auto;
    width:180px;
    height:180px;
}

.qr-card button{
    border:0;
    padding:13px 22px;
    border-radius:12px;
    background:var(--dark);
    color:white;
    font-weight:800;
    cursor:pointer;
}

.qr-info h2{
    font-size:40px;
    letter-spacing:-1.5px;
    margin-bottom:18px;
}

.qr-info p{
    color:#64726c;
    line-height:1.7;
}

.feature-list{
    list-style:none;
    margin-top:22px;
}

.feature-list li{
    margin:12px 0;
    font-size:14px;
    font-weight:700;
}

.feature-list li span{
    color:var(--green);
    margin-right:8px;
}


/* =========================
   OWNER DASHBOARD
========================= */

.dashboard{
    max-width:1050px;
    margin:auto;
    background:white;
    border:1px solid var(--border);
    border-radius:28px;
    padding:35px;
}

.dashboard-head{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:25px;
}

.dashboard-head p{
    color:var(--muted);
    font-size:13px;
    margin-top:4px;
}

.status{
    background:#e2fff1;
    color:#08734e;
    padding:8px 12px;
    border-radius:20px;
    font-size:11px;
    font-weight:800;
}

.form-grid{
    display:grid;
    grid-template-columns:repeat(2,1fr);
    gap:17px;
}

.field{
    display:flex;
    flex-direction:column;
    gap:7px;
}

.field.full{
    grid-column:1/-1;
}

.field label{
    font-size:12px;
    font-weight:800;
}

.field input,
.field textarea,
.field select{
    border:1px solid var(--border);
    background:#fafcfb;
    padding:13px;
    border-radius:11px;
    outline:none;
    font-size:14px;
}

.field textarea{
    min-height:90px;
    resize:vertical;
}

.field input:focus,
.field textarea:focus{
    border-color:var(--green);
}

.save{
    margin-top:22px;
}


/* =========================
   CTA
========================= */

.cta{
    padding:90px 7%;
    text-align:center;
}

.cta-box{
    max-width:950px;
    margin:auto;
    padding:60px 30px;
    border-radius:32px;
    background:var(--dark);
    color:white;
    position:relative;
    overflow:hidden;
}

.cta-box::before{
    content:"🐾";
    position:absolute;
    font-size:220px;
    opacity:.035;
    right:-20px;
    bottom:-65px;
}

.cta-box h2{
    font-size:42px;
    letter-spacing:-2px;
    margin-bottom:13px;
}

.cta-box p{
    color:#afbbb6;
    margin-bottom:25px;
}


/* =========================
   FOOTER
========================= */

footer{
    background:#0c1713;
    color:white;
    text-align:center;
    padding:30px 7%;
}

footer .footer-logo{
    font-weight:900;
    font-size:19px;
}

footer span{
    color:var(--green);
}

footer p{
    color:#7d8d86;
    font-size:12px;
    margin-top:7px;
}


/* =========================
   TOAST
========================= */

.toast{
    position:fixed;
    bottom:25px;
    left:50%;
    transform:translate(-50%,100px);
    background:var(--dark);
    color:white;
    padding:14px 20px;
    border-radius:13px;
    font-size:13px;
    font-weight:700;
    z-index:5000;
    opacity:0;
    transition:.35s;
}

.toast.show{
    transform:translate(-50%,0);
    opacity:1;
}


/* =========================
   MOBILE
========================= */

@media(max-width:850px){

    .nav-links{
        display:none;
    }

    .hero{
        grid-template-columns:1fr;
        text-align:center;
        padding-top:125px;
    }

    .hero-description{
        margin-left:auto;
        margin-right:auto;
    }

    .hero-actions{
        justify-content:center;
    }

    .hero-visual{
        min-height:420px;
    }

    .profile,
    .location-wrap,
    .qr-layout{
        grid-template-columns:1fr;
    }

    .steps,
    .hospital-grid{
        grid-template-columns:1fr;
    }

}

@media(max-width:550px){

    section{
        padding:70px 5%;
    }

    .hero{
        padding-left:5%;
        padding-right:5%;
    }

    .hero h1{
        letter-spacing:-2.5px;
    }

    .pet-card-hero{
        width:290px;
    }

    .orbit{
        width:330px;
        height:330px;
    }

    .floating-card{
        display:none;
    }

    .info-grid,
    .form-grid{
        grid-template-columns:1fr;
    }

    .field.full{
        grid-column:auto;
    }

    .section-heading h2{
        font-size:33px;
    }

    .qr-info h2,
    .cta-box h2{
        font-size:32px;
    }

    .dashboard{
        padding:22px;
    }
}

</style>
</head>


<body>


<!-- =========================
     NAVIGATION
========================= -->

<nav class="navbar">

    <div class="logo">
        <div class="logo-icon">🐾</div>
        PAW<span>SAFE</span>
    </div>

    <div class="nav-links">

        <a href="#home">Home</a>
        <a href="#how">How it works</a>
        <a href="#profile">Pet Profile</a>
        <a href="#location">Location</a>
        <a href="#hospitals">Veterinary Care</a>

    </div>

    <button
        class="nav-button"
        onclick="scrollToQR()">

        Scan / QR

    </button>

</nav>


<!-- =========================
     HERO
========================= -->

<header class="hero" id="home">

    <div class="hero-content">

        <div class="pill">
            <span class="pill-dot"></span>
            SMART PET RECOVERY SYSTEM
        </div>

        <h1>
            Helping lost pets
            <span>find their way home.</span>
        </h1>

        <p class="hero-description">

            PAWSAFE uses a simple QR-based identity system
            to connect a lost pet with its owner.
            Scan the tag, view the pet profile, check
            the last-known location and find veterinary
            care nearby.

        </p>

        <div class="hero-actions">

            <button
                class="primary-btn"
                onclick="scrollToQR()">

                🔳 View Pet QR

            </button>

            <button
                class="secondary-btn"
                onclick="scrollToProfile()">

                🐶 Explore Profile

            </button>

        </div>

    </div>


    <!-- HERO CARD -->

    <div class="hero-visual">

        <div class="orbit"></div>

        <div class="floating-card qr-float">

            <div class="float-title">
                QR STATUS
            </div>

            <div class="float-value">
                ✓ ACTIVE
            </div>

        </div>


        <div class="floating-card location-float">

            <div class="float-title">
                LAST SEEN
            </div>

            <div class="float-value">
                📍 Bengaluru
            </div>

        </div>


        <div class="pet-card-hero">

            <div class="pet-picture">
                🐕
            </div>

            <div class="pet-name-row">

                <h3 id="heroPetName">
                    Buddy
                </h3>

                <span class="online">
                    ● SAFE ID
                </span>

            </div>

            <p id="heroBreed">
                Golden Retriever · Male
            </p>

        </div>

    </div>

</header>


<!-- =========================
     HOW IT WORKS
========================= -->

<section id="how">

    <div class="section-heading">

        <div class="mini">
            SIMPLE • FAST • SMART
        </div>

        <h2>
            How PAWSAFE works
        </h2>

        <p>
            A simple system designed to help people
            identify and return lost pets faster.
        </p>

    </div>


    <div class="steps">

        <div class="step">

            <div class="step-number">
                01
            </div>

            <div class="step-icon">
                🔳
            </div>

            <h3>
                Scan the QR
            </h3>

            <p>
                A person who finds the pet scans
                the QR code attached to its collar.
            </p>

        </div>


        <div class="step">

            <div class="step-number">
                02
            </div>

            <div class="step-icon">
                👤
            </div>

            <h3>
                Identify the Pet
            </h3>

            <p>
                The QR page displays the pet's
                basic profile and owner contact information.
            </p>

        </div>


        <div class="step">

            <div class="step-number">
                03
            </div>

            <div class="step-icon">
                📍
            </div>

            <h3>
                Help Bring It Home
            </h3>

            <p>
                The owner can update the location
                and the finder can locate nearby veterinary care.
            </p>

        </div>

    </div>

</section>


<!-- =========================
     PET PROFILE
========================= -->

<section class="profile-section" id="profile">

    <div class="section-heading">

        <div class="mini">
            PET IDENTITY
        </div>

        <h2>
            Meet your pet's profile
        </h2>

        <p>
            Everything important in one simple,
            easy-to-read profile.
        </p>

    </div>


    <div class="profile">

        <!-- LEFT -->

        <div class="profile-left">

            <div>

                <div class="profile-photo">
                    🐶
                </div>

                <h2 id="profilePetName">
                    Buddy
                </h2>

                <p id="profileBreed">
                    Golden Retriever
                </p>

                <div class="verified-badge">
                    ✓ VERIFIED PET ID
                </div>

            </div>

            <div>

                <p>
                    Pet ID:
                    <strong id="petId">
                        PS-2026-001
                    </strong>
                </p>

            </div>

        </div>


        <!-- RIGHT -->

        <div class="profile-right">

            <h3>
                Pet information
            </h3>

            <div class="info-grid">

                <div class="info">

                    <small>
                        Name
                    </small>

                    <strong id="infoName">
                        Buddy
                    </strong>

                </div>


                <div class="info">

                    <small>
                        Breed
                    </small>

                    <strong id="infoBreed">
                        Golden Retriever
                    </strong>

                </div>


                <div class="info">

                    <small>
                        Age
                    </small>

                    <strong id="infoAge">
                        3 Years
                    </strong>

                </div>


                <div class="info">

                    <small>
                        Gender
                    </small>

                    <strong id="infoGender">
                        Male
                    </strong>

                </div>

            </div>


            <div class="owner-box">

                <h4>
                    👤 Owner
                </h4>

                <p>
                    <strong id="infoOwner">
                        Vikas
                    </strong>
                    <br>

                    Contact:
                    <strong id="infoPhone">
                        +91 XXXXX XXXXX
                    </strong>
                </p>

            </div>


            <div class="owner-box">

                <h4>
                    📝 Important information
                </h4>

                <p id="infoNotes">
                    Friendly dog. Please contact the owner
                    if found.
                </p>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     LOCATION
========================= -->

<section class="location-section" id="location">

    <div class="section-heading">

        <div class="mini">
            SMART LOCATION
        </div>

        <h2>
            Know where your pet was last seen.
        </h2>

        <p>
            Use the phone's GPS to capture a location
            and open it directly in Google Maps.
        </p>

    </div>


    <div class="location-wrap">

        <div class="location-panel">

            <h3>
                📍 Last Known Location
            </h3>

            <p>
                Location can be updated when the pet
                is found or when the owner wants to
                record its current position.
            </p>


            <div class="map-box">

                <div class="map-pin">
                    📍
                </div>

            </div>

        </div>


        <div class="location-panel">

            <h3>
                Location Details
            </h3>

            <p>
                Current demo location is set to Bengaluru.
                You can use GPS during your exhibition demo.
            </p>


            <div class="coordinates">

                <div>
                    <strong id="locationStatus">
                        Demo Location
                    </strong>
                </div>

                <br>

                <span id="coordinates">
                    12.9716, 77.5946
                </span>

            </div>


            <div class="location-actions">

                <button
                    class="location-primary"
                    onclick="getLocation()">

                    📍 Use My GPS

                </button>

                <button
                    class="location-light"
                    onclick="openMap()">

                    🗺️ Open Maps

                </button>

            </div>

        </div>

    </div>

</section>


<!-- =========================
     VETERINARY HOSPITALS
========================= -->

<section id="hospitals">

    <div class="section-heading">

        <div class="mini">
            EMERGENCY SUPPORT
        </div>

        <h2>
            Veterinary care nearby.
        </h2>

        <p>
            Quickly search for veterinary hospitals
            and pet clinics around your current location.
        </p>

    </div>


    <div class="hospital-grid">

        <div class="hospital">

            <div class="hospital-icon">
                🏥
            </div>

            <h3>
                Veterinary Hospital
            </h3>

            <p>
                Search for veterinary hospitals
                near your current location.
            </p>

            <button onclick="findHospital()">
                Find Hospital →
            </button>

        </div>


        <div class="hospital">

            <div class="hospital-icon">
                🩺
            </div>

            <h3>
                Pet Clinic
            </h3>

            <p>
                Find nearby animal clinics for
                basic medical support.
            </p>

            <button onclick="findClinic()">
                Find Pet Clinic →
            </button>

        </div>


        <div class="hospital">

            <div class="hospital-icon">
                🚨
            </div>

            <h3>
                Emergency Vet
            </h3>

            <p>
                Search for emergency veterinary
                services near your location.
            </p>

            <button onclick="findEmergency()">
                Emergency Search →
            </button>

        </div>

    </div>

</section>


<!-- =========================
     QR CODE
========================= -->

<section class="qr-section" id="qr">

    <div class="qr-layout">

        <div class="qr-card">

            <h3>
                🔳 Buddy's Smart ID
            </h3>

            <p>
                Scan this code to open this website.
            </p>

            <div id="qrcode"></div>

            <button onclick="generateQR()">
                Generate QR
            </button>

        </div>


        <div class="qr-info">

            <div class="mini">
                SMART COLLAR
            </div>

            <h2>
                One small QR.
                One big difference.
            </h2>

            <p>
                Attach the QR code to a pet's collar.
                If someone finds the pet, they can scan
                the code and access the information provided
                by the owner.
            </p>


            <ul class="feature-list">

                <li>
                    <span>✓</span>
                    Instant pet identification
                </li>

                <li>
                    <span>✓</span>
                    Owner contact information
                </li>

                <li>
                    <span>✓</span>
                    Last-known location
                </li>

                <li>
                    <span>✓</span>
                    Nearby veterinary support
                </li>

            </ul>

        </div>

    </div>

</section>


<!-- =========================
     OWNER DASHBOARD
========================= -->

<section id="register">

    <div class="section-heading">

        <div class="mini">
            PET REGISTRATION
        </div>

        <h2>
            Manage your pet profile.
        </h2>

        <p>
            Enter demo information here and instantly
            update the profile displayed above.
        </p>

    </div>


    <div class="dashboard">

        <div class="dashboard-head">

            <div>

                <h3>
                    PetSafe Owner Dashboard
                </h3>

                <p>
                    Update your pet's public information
                </p>

            </div>

            <div class="status">
                ● ACTIVE
            </div>

        </div>


        <div class="form-grid">

            <div class="field">

                <label>
                    Pet Name
                </label>

                <input
                    id="petNameInput"
                    value="Buddy">

            </div>


            <div class="field">

                <label>
                    Breed
                </label>

                <input
                    id="breedInput"
                    value="Golden Retriever">

            </div>


            <div class="field">

                <label>
                    Age
                </label>

                <input
                    id="ageInput"
                    value="3 Years">

            </div>


            <div class="field">

                <label>
                    Gender
                </label>

                <select id="genderInput">

                    <option>Male</option>
                    <option>Female</option>

                </select>

            </div>


            <div class="field">

                <label>
                    Owner Name
                </label>

                <input
                    id="ownerInput"
                    value="Vikas">

            </div>


            <div class="field">

                <label>
                    Contact Number
                </label>

                <input
                    id="phoneInput"
                    value="+91 XXXXX XXXXX">

            </div>


            <div class="field full">

                <label>
                    Important Information
                </label>

                <textarea id="notesInput">Friendly dog. Please contact the owner if found.</textarea>

            </div>

        </div>


        <button
            class="primary-btn save"
            onclick="saveProfile()">

            💾 Save Profile

        </button>

    </div>

</section>


<!-- =========================
     CTA
========================= -->

<section class="cta">

    <div class="cta-box">

        <h2>
            Technology that brings pets home.
        </h2>

        <p>
            PAWSAFE — Smart identification for a safer
            and more connected pet community.
        </p>

        <button
            class="primary-btn"
            onclick="scrollToQR()">

            🔳 View QR System

        </button>

    </div>

</section>


<!-- =========================
     FOOTER
========================= -->

<footer>

    <div class="footer-logo">
        PAW<span>SAFE</span>
    </div>

    <p>
        Smart Pet Identification & Recovery System
    </p>

    <p>
        © 2026 PAWSAFE Exhibition Project
    </p>

</footer>


<!-- =========================
     TOAST
========================= -->

<div
    class="toast"
    id="toast">

    Saved successfully ✓

</div>


<script>

/* =========================
   GLOBAL LOCATION
========================= */

let latitude = 12.9716;
let longitude = 77.5946;


/* =========================
   TOAST MESSAGE
========================= */

function showToast(message){

    const toast =
        document.getElementById("toast");

    toast.textContent = message;

    toast.classList.add("show");

    setTimeout(function(){

        toast.classList.remove("show");

    },2500);
}


/* =========================
   SCROLL FUNCTIONS
========================= */

function scrollToQR(){

    document
        .getElementById("qr")
        .scrollIntoView({
            behavior:"smooth"
        });

}


function scrollToProfile(){

    document
        .getElementById("profile")
        .scrollIntoView({
            behavior:"smooth"
        });

}


/* =========================
   SAVE PROFILE
========================= */

function saveProfile(){

    const pet =
        document.getElementById("petNameInput").value;

    const breed =
        document.getElementById("breedInput").value;

    const age =
        document.getElementById("ageInput").value;

    const gender =
        document.getElementById("genderInput").value;

    const owner =
        document.getElementById("ownerInput").value;

    const phone =
        document.getElementById("phoneInput").value;

    const notes =
        document.getElementById("notesInput").value;


    /* Update Hero */

    document.getElementById("heroPetName")
        .textContent = pet;

    document.getElementById("heroBreed")
        .textContent = breed + " · " + gender;


    /* Update Profile */

    document.getElementById("profilePetName")
        .textContent = pet;

    document.getElementById("profileBreed")
        .textContent = breed;


    document.getElementById("infoName")
        .textContent = pet;

    document.getElementById("infoBreed")
        .textContent = breed;

    document.getElementById("infoAge")
        .textContent = age;

    document.getElementById("infoGender")
        .textContent = gender;

    document.getElementById("infoOwner")
        .textContent = owner;

    document.getElementById("infoPhone")
        .textContent = phone;

    document.getElementById("infoNotes")
        .textContent = notes;


    /* Save locally */

    localStorage.setItem(
        "pawsafe_pet",
        pet
    );

    localStorage.setItem(
        "pawsafe_breed",
        breed
    );

    localStorage.setItem(
        "pawsafe_age",
        age
    );

    localStorage.setItem(
        "pawsafe_gender",
        gender
    );

    localStorage.setItem(
        "pawsafe_owner",
        owner
    );

    localStorage.setItem(
        "pawsafe_phone",
        phone
    );

    localStorage.setItem(
        "pawsafe_notes",
        notes
    );


    showToast("Pet profile updated ✓");

}


/* =========================
   LOAD PROFILE
========================= */

function loadProfile(){

    const pet =
        localStorage.getItem("pawsafe_pet");

    const breed =
        localStorage.getItem("pawsafe_breed");

    const age =
        localStorage.getItem("pawsafe_age");

    const gender =
        localStorage.getItem("pawsafe_gender");

    const owner =
        localStorage.getItem("pawsafe_owner");

    const phone =
        localStorage.getItem("pawsafe_phone");

    const notes =
        localStorage.getItem("pawsafe_notes");


    if(!pet) return;


    document.getElementById("petNameInput")
        .value = pet;

    document.getElementById("breedInput")
        .value = breed;

    document.getElementById("ageInput")
        .value = age;

    document.getElementById("genderInput")
        .value = gender;

    document.getElementById("ownerInput")
        .value = owner;

    document.getElementById("phoneInput")
        .value = phone;

    document.getElementById("notesInput")
        .value = notes;


    document.getElementById("heroPetName")
        .textContent = pet;

    document.getElementById("heroBreed")
        .textContent = breed + " · " + gender;

    document.getElementById("profilePetName")
        .textContent = pet;

    document.getElementById("profileBreed")
        .textContent = breed;

    document.getElementById("infoName")
        .textContent = pet;

    document.getElementById("infoBreed")
        .textContent = breed;

    document.getElementById("infoAge")
        .textContent = age;

    document.getElementById("infoGender")
        .textContent = gender;

    document.getElementById("infoOwner")
        .textContent = owner;

    document.getElementById("infoPhone")
        .textContent = phone;

    document.getElementById("infoNotes")
        .textContent = notes;

}


/* =========================
   GPS
========================= */

function getLocation(){

    if(!navigator.geolocation){

        showToast(
            "GPS is not supported by this browser."
        );

        return;
    }


    document.getElementById("locationStatus")
        .textContent =
        "Requesting GPS location...";


    navigator.geolocation.getCurrentPosition(

        function(position){

            latitude =
                position.coords.latitude;

            longitude =
                position.coords.longitude;


            document.getElementById("locationStatus")
                .textContent =
                "✓ Current GPS Location";


            document.getElementById("coordinates")
                .textContent =
                latitude.toFixed(6)
                + ", "
                + longitude.toFixed(6);


            localStorage.setItem(
                "pawsafe_latitude",
                latitude
            );

            localStorage.setItem(
                "pawsafe_longitude",
                longitude
            );


            showToast(
                "Location captured successfully ✓"
            );

        },

        function(){

            document.getElementById("locationStatus")
                .textContent =
                "Location permission denied";


            showToast(
                "Please allow location access."
            );

        }

    );

}


/* =========================
   OPEN GOOGLE MAPS
========================= */

function openMap(){

    const url =
        "https://www.google.com/maps/search/?api=1&query="
        + latitude
        + ","
        + longitude;

    window.open(
        url,
        "_blank"
    );

}


/* =========================
   VETERINARY SEARCH
========================= */

function findHospital(){

    window.open(
        "https://www.google.com/maps/search/veterinary+hospital+near+me",
        "_blank"
    );

}


function findClinic(){

    window.open(
        "https://www.google.com/maps/search/pet+clinic+near+me",
        "_blank"
    );

}


function findEmergency(){

    window.open(
        "https://www.google.com/maps/search/emergency+veterinary+hospital+near+me",
        "_blank"
    );

}


/* =========================
   QR CODE
========================= */

function generateQR(){

    const container =
        document.getElementById("qrcode");

    container.innerHTML = "";


    new QRCode(

        container,

        {
            text:window.location.href,

            width:180,

            height:180,

            colorDark:"#10201a",

            colorLight:"#ffffff",

            correctLevel:QRCode.CorrectLevel.H

        }

    );

}


/* =========================
   LOAD SAVED LOCATION
========================= */

function loadLocation(){

    const savedLat =
        localStorage.getItem(
            "pawsafe_latitude"
        );

    const savedLng =
        localStorage.getItem(
            "pawsafe_longitude"
        );


    if(savedLat && savedLng){

        latitude =
            parseFloat(savedLat);

        longitude =
            parseFloat(savedLng);


        document.getElementById("locationStatus")
            .textContent =
            "✓ Saved Last-Seen Location";


        document.getElementById("coordinates")
            .textContent =
            latitude.toFixed(6)
            + ", "
            + longitude.toFixed(6);

    }

}


/* =========================
   INITIALIZE
========================= */

window.addEventListener(
    "load",
    function(){

        loadProfile();

        loadLocation();

        generateQR();

    }
);

</script>

</body>
</html>
