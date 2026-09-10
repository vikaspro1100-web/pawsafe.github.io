<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>PAWSAFE | Smart Pet Safety</title>

<script src="https://cdnjs.cloudflare.com/ajax/libs/qrcodejs/1.0.0/qrcode.min.js"></script>

<style>

/* =========================================================
   PAWSAFE
   SMART PET SAFETY PLATFORM
========================================================= */

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
}

body{
    font-family:
        Inter,
        -apple-system,
        BlinkMacSystemFont,
        "Segoe UI",
        sans-serif;

    background:#fafcfb;
    color:#14201b;
    overflow-x:hidden;
}

button,
input,
textarea,
select{
    font-family:inherit;
}

button{
    cursor:pointer;
}

a{
    text-decoration:none;
    color:inherit;
}

:root{
    --green:#13a66d;
    --green-dark:#087a4e;
    --mint:#e8fff4;
    --dark:#10211a;
    --cream:#fffaf3;
    --pink:#ff6574;
    --blue:#65aeea;
    --text:#14201b;
    --muted:#718078;
    --border:#e4ebe7;
    --white:#ffffff;
}


/* =========================================================
   SCROLLBAR
========================================================= */

::-webkit-scrollbar{
    width:8px;
}

::-webkit-scrollbar-thumb{
    background:#b9d9cc;
    border-radius:20px;
}


/* =========================================================
   NAVBAR
========================================================= */

.navbar{
    position:fixed;
    top:0;
    left:0;
    right:0;
    height:76px;

    padding:0 6%;

    display:flex;
    align-items:center;
    justify-content:space-between;

    background:rgba(255,255,255,.86);
    backdrop-filter:blur(18px);

    border-bottom:1px solid rgba(0,0,0,.05);

    z-index:999;
}

.logo{
    display:flex;
    align-items:center;
    gap:10px;

    font-size:23px;
    font-weight:900;
    letter-spacing:-1px;
}

.logo-paw{
    width:39px;
    height:39px;

    display:grid;
    place-items:center;

    background:var(--dark);
    color:white;

    border-radius:13px;

    font-size:21px;
}

.logo span{
    color:var(--green);
}

.nav-links{
    display:flex;
    gap:27px;
}

.nav-links a{
    color:#53615b;
    font-size:14px;
    font-weight:700;
    transition:.2s;
}

.nav-links a:hover{
    color:var(--green);
}

.nav-actions{
    display:flex;
    gap:8px;
}

.login-btn,
.register-btn{
    padding:10px 17px;
    border-radius:11px;
    font-weight:800;
    border:1px solid var(--green);
    background:white;
    color:var(--green-dark);
}

.register-btn{
    background:var(--green);
    color:white;
}


/* =========================================================
   HERO
========================================================= */

.hero{
    min-height:760px;

    padding:
        135px 7%
        80px;

    display:grid;
    grid-template-columns:1.08fr .92fr;

    align-items:center;

    gap:55px;

    position:relative;
    overflow:hidden;

    background:
        radial-gradient(
            circle at 80% 20%,
            #d8fff0,
            transparent 28%
        ),
        radial-gradient(
            circle at 15% 80%,
            #fff0e8,
            transparent 25%
        ),
        #fbfdfc;
}

.hero::before{
    content:"";

    position:absolute;

    width:520px;
    height:520px;

    right:-190px;
    top:-180px;

    border:1px solid rgba(19,166,109,.13);

    border-radius:50%;
}

.hero-content{
    position:relative;
    z-index:2;
}

.hero-badge{
    display:inline-flex;
    align-items:center;
    gap:8px;

    padding:9px 15px;

    border-radius:30px;

    background:var(--mint);

    color:var(--green-dark);

    font-size:11px;
    font-weight:900;

    letter-spacing:1px;

    margin-bottom:23px;
}

.green-dot{
    width:7px;
    height:7px;

    border-radius:50%;

    background:var(--green);

    box-shadow:
        0 0 0 5px
        rgba(19,166,109,.12);
}

.hero h1{
    max-width:680px;

    font-size:
        clamp(48px,6.3vw,78px);

    line-height:.96;

    letter-spacing:-4px;

    margin-bottom:25px;
}

.hero h1 span{
    color:var(--green);
}

.hero-description{
    max-width:570px;

    color:#65736c;

    font-size:17px;

    line-height:1.7;

    margin-bottom:30px;
}

.hero-buttons{
    display:flex;
    flex-wrap:wrap;
    gap:12px;
}

.primary{
    border:none;

    background:var(--green);

    color:white;

    padding:15px 23px;

    border-radius:13px;

    font-weight:900;

    box-shadow:
        0 12px 25px
        rgba(19,166,109,.18);

    transition:.25s;
}

.primary:hover{
    transform:translateY(-3px);
}

.secondary{
    border:1px solid var(--border);

    background:white;

    color:var(--dark);

    padding:15px 23px;

    border-radius:13px;

    font-weight:900;

    transition:.25s;
}

.secondary:hover{
    transform:translateY(-3px);
}


/* =========================================================
   HERO VISUAL
========================================================= */

.hero-visual{
    min-height:490px;

    display:flex;
    align-items:center;
    justify-content:center;

    position:relative;
}

.hero-ring{
    position:absolute;

    width:400px;
    height:400px;

    border:1px dashed
        rgba(19,166,109,.3);

    border-radius:50%;

    animation:spin 25s linear infinite;
}

.hero-ring::after{
    content:"";

    position:absolute;

    width:12px;
    height:12px;

    border-radius:50%;

    background:var(--green);

    left:40px;
    top:50px;
}

@keyframes spin{
    to{
        transform:rotate(360deg);
    }
}

.hero-pet-card{
    width:350px;

    padding:20px;

    background:rgba(255,255,255,.92);

    border-radius:29px;

    box-shadow:
        0 30px 70px
        rgba(27,56,44,.15);

    border:1px solid white;

    transform:rotate(2deg);

    position:relative;
    z-index:5;
}

.hero-pet-image{
    height:255px;

    display:grid;
    place-items:center;

    border-radius:22px;

    background:
        linear-gradient(
            145deg,
            #dcf9eb,
            #f7eee6
        );

    font-size:130px;

    margin-bottom:17px;
}

.hero-pet-name{
    display:flex;
    align-items:center;
    justify-content:space-between;
}

.hero-pet-name h3{
    font-size:26px;
}

.active-badge{
    padding:6px 9px;

    border-radius:20px;

    background:#e5fff2;

    color:var(--green-dark);

    font-size:9px;

    font-weight:900;
}

.hero-pet-card p{
    margin-top:6px;
    color:var(--muted);
}

.floating{
    position:absolute;

    background:white;

    padding:14px 16px;

    border-radius:16px;

    box-shadow:
        0 18px 40px
        rgba(20,50,39,.12);

    z-index:10;

    animation:float 3s ease-in-out infinite;
}

.floating-location{
    left:0;
    bottom:60px;
}

.floating-qr{
    right:0;
    top:50px;
    animation-delay:1s;
}

.floating small{
    display:block;

    color:#89958f;

    font-size:10px;

    margin-bottom:4px;
}

.floating strong{
    font-size:13px;
}

@keyframes float{
    0%,100%{
        transform:translateY(0);
    }

    50%{
        transform:translateY(-9px);
    }
}


/* =========================================================
   TRUST BAR
========================================================= */

.trust-bar{
    padding:25px 7%;

    background:white;

    border-top:1px solid var(--border);
    border-bottom:1px solid var(--border);

    display:grid;
    grid-template-columns:repeat(4,1fr);

    gap:15px;
}

.trust-item{
    display:flex;
    align-items:center;
    justify-content:center;

    gap:12px;

    padding:8px;

    border-right:1px solid var(--border);
}

.trust-item:last-child{
    border-right:none;
}

.trust-icon{
    width:42px;
    height:42px;

    display:grid;
    place-items:center;

    border-radius:13px;

    background:var(--mint);

    font-size:20px;
}

.trust-item strong{
    display:block;
    font-size:20px;
}

.trust-item span{
    color:var(--muted);
    font-size:11px;
}


/* =========================================================
   SECTION COMMON
========================================================= */

section{
    padding:100px 7%;
}

.section-head{
    max-width:670px;

    text-align:center;

    margin:
        0 auto
        50px;
}

.section-mini{
    color:var(--green);

    font-size:11px;

    letter-spacing:1.8px;

    font-weight:900;

    margin-bottom:10px;
}

.section-head h2{
    font-size:42px;

    letter-spacing:-2px;

    margin-bottom:12px;
}

.section-head p{
    color:var(--muted);

    line-height:1.65;
}


/* =========================================================
   HOW IT WORKS
========================================================= */

.steps{
    max-width:1080px;

    margin:auto;

    display:grid;
    grid-template-columns:repeat(3,1fr);

    gap:20px;
}

.step{
    background:white;

    padding:30px;

    border:1px solid var(--border);

    border-radius:24px;

    transition:.3s;
}

.step:hover{
    transform:translateY(-7px);

    box-shadow:
        0 20px 45px
        rgba(20,50,39,.08);
}

.step-number{
    width:43px;
    height:43px;

    display:grid;
    place-items:center;

    border-radius:13px;

    background:var(--mint);

    color:var(--green);

    font-weight:900;

    margin-bottom:20px;
}

.step-icon{
    font-size:38px;

    margin-bottom:15px;
}

.step h3{
    margin-bottom:9px;
}

.step p{
    color:var(--muted);

    line-height:1.6;

    font-size:14px;
}


/* =========================================================
   PET PROFILE
========================================================= */

.profile-section{
    background:#f0f8f4;
}

.profile{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:330px 1fr;

    gap:22px;
}

.profile-left{
    background:var(--dark);

    color:white;

    padding:22px;

    border-radius:27px;

    display:flex;

    flex-direction:column;

    justify-content:space-between;
}

.profile-image{
    height:270px;

    display:grid;

    place-items:center;

    background:
        linear-gradient(
            145deg,
            #dff9eb,
            #c2eedb
        );

    border-radius:21px;

    font-size:130px;
}

.profile-left h2{
    font-size:29px;

    margin-top:18px;
}

.profile-left p{
    color:#aebcb6;

    margin-top:5px;
}

.verified{
    display:inline-block;

    margin-top:12px;

    padding:7px 11px;

    border-radius:20px;

    background:
        rgba(19,166,109,.17);

    color:#65e4b1;

    font-size:10px;

    font-weight:900;
}

.profile-id{
    color:#9eada7 !important;

    font-size:12px;
}

.profile-right{
    background:white;

    border:1px solid var(--border);

    border-radius:27px;

    padding:30px;
}

.profile-right h3{
    font-size:23px;

    margin-bottom:20px;
}

.info-grid{
    display:grid;

    grid-template-columns:repeat(2,1fr);

    gap:13px;
}

.info{
    padding:17px;

    border:1px solid var(--border);

    border-radius:15px;
}

.info small{
    display:block;

    color:#8a958f;

    font-size:10px;

    text-transform:uppercase;

    letter-spacing:.6px;

    margin-bottom:6px;
}

.info strong{
    font-size:15px;
}

.owner{
    margin-top:17px;

    padding:19px;

    border-radius:16px;

    background:#f3faf7;
}

.owner h4{
    margin-bottom:7px;
}

.owner p{
    color:var(--muted);

    font-size:13px;

    line-height:1.6;
}


/* =========================================================
   LOST PET
========================================================= */

.lost-section{
    background:var(--cream);
}

.lost-grid{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:.9fr 1.1fr;

    gap:22px;
}

.lost-card{
    background:white;

    border:1px solid var(--border);

    border-radius:27px;

    padding:30px;
}

.lost-card h3{
    font-size:25px;

    margin-bottom:9px;
}

.lost-card>p{
    color:var(--muted);

    line-height:1.6;

    font-size:14px;
}

.lost-buttons{
    margin-top:25px;

    display:grid;

    gap:11px;
}

.lost-btn{
    padding:14px;

    border-radius:12px;

    border:1px solid #ffd5da;

    background:#fff6f7;

    color:#d94757;

    font-weight:900;
}

.found-btn{
    background:var(--mint);

    border-color:#ccefe0;

    color:var(--green-dark);
}

.lost-pet-visual{
    margin-top:25px;

    height:160px;

    border-radius:19px;

    display:grid;

    place-items:center;

    font-size:100px;

    background:
        linear-gradient(
            135deg,
            #ffe4e4,
            #fff6ec
        );
}

.alert-list{
    margin-top:20px;

    display:grid;

    gap:11px;
}

.alert{
    display:flex;

    align-items:center;

    gap:12px;

    padding:14px;

    border-radius:13px;

    background:#f8faf9;
}

.alert-icon{
    width:35px;
    height:35px;

    display:grid;
    place-items:center;

    background:white;

    border-radius:10px;
}

.alert strong{
    font-size:13px;
}

.alert span{
    display:block;

    color:var(--muted);

    font-size:11px;

    margin-top:3px;
}


/* =========================================================
   LOCATION
========================================================= */

.location-section{
    background:var(--dark);

    color:white;
}

.location-section .section-head p{
    color:#9eada7;
}

.location-grid{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:1fr 1fr;

    gap:22px;
}

.location-card{
    background:#182d25;

    border:1px solid rgba(255,255,255,.07);

    border-radius:27px;

    padding:30px;
}

.location-card h3{
    font-size:24px;

    margin-bottom:8px;
}

.location-card>p{
    color:#9eada7;

    line-height:1.6;

    font-size:13px;
}

.map{
    height:230px;

    margin-top:22px;

    border-radius:19px;

    display:grid;

    place-items:center;

    background:
        repeating-linear-gradient(
            45deg,
            #29483c,
            #29483c 2px,
            #223c33 2px,
            #223c33 28px
        );
}

.map-pin{
    width:66px;
    height:66px;

    display:grid;
    place-items:center;

    background:#dcfff0;

    color:var(--green);

    border-radius:50%;

    font-size:28px;

    box-shadow:
        0 0 0 15px
        rgba(220,255,240,.1);
}

.location-data{
    margin-top:15px;

    padding:15px;

    background:rgba(255,255,255,.06);

    border-radius:13px;

    color:#c3d0ca;

    font-size:12px;
}

.location-buttons{
    display:flex;

    gap:10px;

    flex-wrap:wrap;

    margin-top:17px;
}

.location-buttons button{
    padding:12px 15px;

    border:0;

    border-radius:11px;

    font-weight:900;
}

.gps-btn{
    background:var(--green);

    color:white;
}

.map-btn{
    background:white;

    color:var(--dark);
}


/* =========================================================
   VET HOSPITALS
========================================================= */

.hospitals{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:repeat(3,1fr);

    gap:17px;
}

.hospital{
    background:white;

    border:1px solid var(--border);

    border-radius:22px;

    padding:23px;

    transition:.3s;
}

.hospital:hover{
    transform:translateY(-6px);

    box-shadow:
        0 18px 40px
        rgba(20,50,39,.08);
}

.hospital-icon{
    width:48px;
    height:48px;

    display:grid;
    place-items:center;

    background:var(--mint);

    border-radius:13px;

    font-size:23px;

    margin-bottom:16px;
}

.hospital h3{
    font-size:17px;

    margin-bottom:7px;
}

.hospital p{
    color:var(--muted);

    font-size:12px;

    line-height:1.6;

    margin-bottom:16px;
}

.hospital button{
    width:100%;

    border:0;

    padding:11px;

    border-radius:10px;

    background:#edf9f4;

    color:var(--green-dark);

    font-weight:900;
}


/* =========================================================
   DIGITAL PET ID
========================================================= */

.digital-id{
    background:#eefaf5;
}

.id-card{
    max-width:1050px;

    margin:auto;

    display:grid;

    grid-template-columns:1fr 330px;

    gap:30px;

    align-items:center;
}

.id-text h2{
    font-size:43px;

    letter-spacing:-2px;

    margin-bottom:15px;
}

.id-text p{
    color:var(--muted);

    line-height:1.7;

    max-width:570px;
}

.check-list{
    list-style:none;

    margin-top:22px;
}

.check-list li{
    margin:12px 0;

    font-size:14px;

    font-weight:700;
}

.check-list span{
    color:var(--green);

    margin-right:7px;
}

.id-visual{
    background:white;

    border:1px solid var(--border);

    border-radius:25px;

    padding:25px;

    text-align:center;

    box-shadow:
        0 18px 40px
        rgba(20,50,39,.07);
}

.id-visual h3{
    margin-bottom:10px;
}

#qrcode{
    width:180px;
    height:180px;

    margin:20px auto;
}

.id-number{
    font-size:12px;

    color:var(--muted);
}


/* =========================================================
   HEALTH RECORD
========================================================= */

.health-grid{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:repeat(4,1fr);

    gap:15px;
}

.health{
    padding:24px;

    background:white;

    border:1px solid var(--border);

    border-radius:20px;
}

.health-icon{
    font-size:29px;

    margin-bottom:14px;
}

.health h3{
    font-size:15px;

    margin-bottom:7px;
}

.health p{
    color:var(--muted);

    font-size:12px;

    line-height:1.6;
}


/* =========================================================
   OWNER DASHBOARD
========================================================= */

.dashboard-section{
    background:#f6f8f7;
}

.dashboard{
    max-width:1080px;

    margin:auto;

    padding:30px;

    background:white;

    border:1px solid var(--border);

    border-radius:27px;
}

.dashboard-header{
    display:flex;

    align-items:center;

    justify-content:space-between;

    margin-bottom:25px;
}

.dashboard-header p{
    color:var(--muted);

    font-size:12px;

    margin-top:5px;
}

.active{
    background:#e4fff2;

    color:var(--green-dark);

    padding:8px 11px;

    border-radius:20px;

    font-size:10px;

    font-weight:900;
}

.form{
    display:grid;

    grid-template-columns:repeat(2,1fr);

    gap:16px;
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
    font-size:11px;

    font-weight:900;
}

.field input,
.field textarea,
.field select{
    width:100%;

    padding:13px;

    border:1px solid var(--border);

    border-radius:11px;

    background:#fafcfb;

    outline:none;

    font-size:13px;
}

.field textarea{
    min-height:85px;

    resize:vertical;
}

.field input:focus,
.field textarea:focus,
.field select:focus{
    border-color:var(--green);
}

.save-button{
    margin-top:20px;
}


/* =========================================================
   SHOP
========================================================= */

.shop-section{
    background:#fffaf5;
}

.shop-top{
    max-width:1080px;

    margin:
        0 auto
        35px;

    display:flex;

    align-items:end;

    justify-content:space-between;

    gap:20px;
}

.shop-top h2{
    font-size:42px;

    letter-spacing:-2px;
}

.shop-top p{
    color:var(--muted);

    margin-top:7px;
}

.shop-badge{
    display:inline-block;

    color:#b65c25;

    font-size:11px;

    font-weight:900;

    letter-spacing:1px;

    margin-bottom:6px;
}

.shop-button{
    padding:11px 17px;

    background:white;

    border:1px solid var(--green);

    color:var(--green-dark);

    border-radius:11px;

    font-weight:900;
}

.products{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:
        repeat(4,1fr);

    gap:17px;
}

.product{
    background:white;

    border:1px solid var(--border);

    border-radius:21px;

    padding:13px;

    transition:.3s;

    position:relative;
}

.product:hover{
    transform:translateY(-7px);

    box-shadow:
        0 20px 40px
        rgba(50,40,20,.09);
}

.product-image{
    height:180px;

    border-radius:16px;

    display:grid;

    place-items:center;

    font-size:83px;

    background:
        linear-gradient(
            135deg,
            #eef8f3,
            #fff0e7
        );

    margin-bottom:15px;
}

.product-tag{
    position:absolute;

    top:24px;
    left:24px;

    padding:5px 8px;

    border-radius:20px;

    background:#10211a;

    color:white;

    font-size:8px;

    font-weight:900;
}

.product h3{
    font-size:15px;

    margin-bottom:5px;
}

.product-description{
    color:var(--muted);

    font-size:11px;

    line-height:1.5;

    min-height:34px;
}

.product-bottom{
    display:flex;

    align-items:center;

    justify-content:space-between;

    gap:7px;

    margin-top:15px;
}

.price{
    font-size:17px;

    font-weight:900;
}

.buy{
    border:0;

    background:var(--green);

    color:white;

    padding:9px 12px;

    border-radius:9px;

    font-size:11px;

    font-weight:900;
}

.cart{
    position:fixed;

    right:25px;
    bottom:25px;

    width:55px;
    height:55px;

    display:grid;

    place-items:center;

    background:var(--dark);

    color:white;

    border-radius:18px;

    box-shadow:
        0 15px 35px
        rgba(0,0,0,.2);

    z-index:900;

    font-size:21px;
}

.cart-count{
    position:absolute;

    right:-5px;
    top:-5px;

    width:20px;
    height:20px;

    display:grid;
    place-items:center;

    background:var(--pink);

    border-radius:50%;

    font-size:10px;

    font-weight:900;
}


/* =========================================================
   COMMUNITY
========================================================= */

.community{
    background:white;
}

.community-grid{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:repeat(3,1fr);

    gap:18px;
}

.community-card{
    padding:27px;

    border-radius:22px;

    background:#f7faf8;

    border:1px solid var(--border);
}

.community-card-icon{
    font-size:34px;

    margin-bottom:15px;
}

.community-card h3{
    margin-bottom:8px;
}

.community-card p{
    color:var(--muted);

    font-size:13px;

    line-height:1.6;
}

.community-card button{
    margin-top:18px;

    border:0;

    background:var(--dark);

    color:white;

    padding:10px 15px;

    border-radius:10px;

    font-size:11px;

    font-weight:900;
}


/* =========================================================
   FINAL CTA
========================================================= */

.final-cta{
    padding:90px 7%;

    background:#f7faf8;
}

.cta-box{
    max-width:1080px;

    margin:auto;

    padding:65px 30px;

    border-radius:31px;

    background:var(--dark);

    color:white;

    text-align:center;

    position:relative;

    overflow:hidden;
}

.cta-box::before{
    content:"🐾";

    position:absolute;

    font-size:230px;

    right:-20px;

    bottom:-70px;

    opacity:.035;
}

.cta-box h2{
    font-size:43px;

    letter-spacing:-2px;

    margin-bottom:12px;

    position:relative;
}

.cta-box p{
    color:#aab8b2;

    margin-bottom:25px;

    position:relative;
}


/* =========================================================
   FOOTER
========================================================= */

footer{
    padding:45px 7% 25px;

    background:#0b1712;

    color:white;
}

.footer-grid{
    max-width:1080px;

    margin:auto;

    display:grid;

    grid-template-columns:1.5fr 1fr 1fr 1.5fr;

    gap:35px;
}

.footer-logo{
    font-size:23px;

    font-weight:900;

    margin-bottom:10px;
}

.footer-logo span{
    color:var(--green);
}

footer p{
    color:#82918a;

    font-size:12px;

    line-height:1.6;
}

.footer-column h4{
    margin-bottom:13px;

    font-size:13px;
}

.footer-column a{
    display:block;

    color:#82918a;

    font-size:12px;

    margin:8px 0;
}

.footer-column a:hover{
    color:white;
}

.copyright{
    max-width:1080px;

    margin:35px auto 0;

    padding-top:20px;

    border-top:1px solid rgba(255,255,255,.08);

    text-align:center;
}


/* =========================================================
   TOAST
========================================================= */

.toast{
    position:fixed;

    left:50%;
    bottom:25px;

    transform:
        translate(-50%,100px);

    opacity:0;

    padding:14px 20px;

    background:var(--dark);

    color:white;

    border-radius:13px;

    font-size:12px;

    font-weight:800;

    z-index:5000;

    transition:.35s;
}

.toast.show{
    transform:
        translate(-50%,0);

    opacity:1;
}


/* =========================================================
   MOBILE
========================================================= */

@media(max-width:900px){

    .nav-links{
        display:none;
    }

    .hero{
        grid-template-columns:1fr;

        text-align:center;
    }

    .hero-description{
        margin-left:auto;
        margin-right:auto;
    }

    .hero-buttons{
        justify-content:center;
    }

    .trust-bar{
        grid-template-columns:repeat(2,1fr);
    }

    .trust-item{
        border-right:none;
    }

    .steps,
    .hospitals,
    .community-grid{
        grid-template-columns:1fr;
    }

    .profile,
    .lost-grid,
    .location-grid,
    .id-card{
        grid-template-columns:1fr;
    }

    .products{
        grid-template-columns:repeat(2,1fr);
    }

    .health-grid{
        grid-template-columns:repeat(2,1fr);
    }

    .footer-grid{
        grid-template-columns:repeat(2,1fr);
    }

}


@media(max-width:550px){

    .navbar{
        padding:0 5%;
    }

    .login-btn{
        display:none;
    }

    .hero{
        padding-left:5%;
        padding-right:5%;
    }

    .hero h1{
        letter-spacing:-2.5px;
    }

    .hero-ring{
        width:330px;
        height:330px;
    }

    .hero-pet-card{
        width:285px;
    }

    .floating{
        display:none;
    }

    .trust-bar{
        grid-template-columns:1fr 1fr;
    }

    section{
        padding:70px 5%;
    }

    .section-head h2,
    .shop-top h2,
    .id-text h2{
        font-size:33px;
    }

    .info-grid,
    .form{
        grid-template-columns:1fr;
    }

    .field.full{
        grid-column:auto;
    }

    .products{
        grid-template-columns:1fr 1fr;
    }

    .product-image{
        height:135px;
        font-size:60px;
    }

    .shop-top{
        align-items:start;
        flex-direction:column;
    }

    .health-grid{
        grid-template-columns:1fr;
    }

    .footer-grid{
        grid-template-columns:1fr;
    }

}

</style>
</head>


<body>


<!-- =========================================================
     NAVIGATION
========================================================= -->

<nav class="navbar">

    <a href="#home" class="logo">

        <div class="logo-paw">
            🐾
        </div>

        PAW<span>SAFE</span>

    </a>


    <div class="nav-links">

        <a href="#home">Home</a>

        <a href="#find">Find Pet</a>

        <a href="#profile">Pet Care</a>

        <a href="#shop">Products</a>

        <a href="#about">About</a>

    </div>


    <div class="nav-actions">

        <button
            class="login-btn"
            onclick="showToast('Welcome to PAWSAFE!')">

            Login

        </button>

        <button
            class="register-btn"
            onclick="scrollToSection('dashboard')">

            Register

        </button>

    </div>

</nav>



<!-- =========================================================
     HERO
========================================================= -->

<header class="hero" id="home">

    <div class="hero-content">

        <div class="hero-badge">

            <span class="green-dot"></span>

            SMART PET SAFETY PLATFORM

        </div>


        <h1>

            Because they're
            <span>family.</span>

        </h1>


        <p class="hero-description">

            PAWSAFE connects lost pets with their owners
            through QR identification, location sharing,
            emergency veterinary support and smart pet care.

        </p>


        <div class="hero-buttons">

            <button
                class="primary"
                onclick="scrollToSection('find')">

                🔳 Find a Pet

            </button>


            <button
                class="secondary"
                onclick="scrollToSection('shop')">

                🛍️ Visit PAWSAFE Shop

            </button>

        </div>

    </div>



    <!-- HERO PET -->

    <div class="hero-visual">

        <div class="hero-ring"></div>


        <div class="floating floating-qr">

            <small>QR STATUS</small>

            <strong>✓ ACTIVE</strong>

        </div>


        <div class="floating floating-location">

            <small>LAST SEEN</small>

            <strong>📍 Bengaluru</strong>

        </div>


        <div class="hero-pet-card">

            <div class="hero-pet-image">
                🐕
            </div>

            <div class="hero-pet-name">

                <h3 id="heroName">
                    Buddy
                </h3>

                <span class="active-badge">
                    ● SAFE ID
                </span>

            </div>

            <p id="heroBreed">
                Golden Retriever · Male
            </p>

        </div>

    </div>

</header>



<!-- =========================================================
     TRUST BAR
========================================================= -->

<div class="trust-bar">

    <div class="trust-item">

        <div class="trust-icon">
            🐾
        </div>

        <div>
            <strong>500+</strong>
            <span>Pets Registered</span>
        </div>

    </div>


    <div class="trust-item">

        <div class="trust-icon">
            ❤️
        </div>

        <div>
            <strong>300+</strong>
            <span>Happy Reunions</span>
        </div>

    </div>


    <div class="trust-item">

        <div class="trust-icon">
            🏥
        </div>

        <div>
            <strong>150+</strong>
            <span>Vet Partners</span>
        </div>

    </div>


    <div class="trust-item">

        <div class="trust-icon">
            🛡️
        </div>

        <div>
            <strong>24/7</strong>
            <span>Pet Protection</span>
        </div>

    </div>

</div>



<!-- =========================================================
     HOW IT WORKS
========================================================= -->

<section id="about">

    <div class="section-head">

        <div class="section-mini">
            HOW IT WORKS
        </div>

        <h2>
            One scan. Three simple steps.
        </h2>

        <p>
            PAWSAFE makes it easier for a finder to identify
            a lost pet and help it get home safely.
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
                Scan the smart QR tag attached to the
                pet's collar using a smartphone.
            </p>

        </div>


        <div class="step">

            <div class="step-number">
                02
            </div>

            <div class="step-icon">
                🐶
            </div>

            <h3>
                View Pet Profile
            </h3>

            <p>
                See the pet's basic details, owner contact,
                health information and identification ID.
            </p>

        </div>


        <div class="step">

            <div class="step-number">
                03
            </div>

            <div class="step-icon">
                🏠
            </div>

            <h3>
                Bring Them Home
            </h3>

            <p>
                Share the location, contact the owner or
                find veterinary help nearby.
            </p>

        </div>

    </div>

</section>



<!-- =========================================================
     FIND PET
========================================================= -->

<section class="lost-section" id="find">

    <div class="section-head">

        <div class="section-mini">
            LOST & FOUND
        </div>

        <h2>
            Help a pet get home.
        </h2>

        <p>
            Quick actions for people who find or lose a pet.
        </p>

    </div>


    <div class="lost-grid">


        <!-- FINDER -->

        <div class="lost-card">

            <h3>
                🐾 I found a pet
            </h3>

            <p>
                Found a pet with a PAWSAFE tag?
                Use the QR code to identify the pet
                and contact the owner.
            </p>


            <div class="lost-buttons">

                <button
                    class="lost-btn found-btn"
                    onclick="scanDemo()">

                    🔳 Scan / Enter Pet ID

                </button>


                <button
                    class="lost-btn"
                    onclick="callOwner()">

                    📞 Contact Owner

                </button>

            </div>


            <div class="lost-pet-visual">
                🐕
            </div>

        </div>



        <!-- ALERTS -->

        <div class="lost-card">

            <h3>
                🚨 Pet safety center
            </h3>

            <p>
                Important information can be displayed
                to help coordinate a safe reunion.
            </p>


            <div class="alert-list">

                <div class="alert">

                    <div class="alert-icon">
                        📍
                    </div>

                    <div>

                        <strong>
                            Last location
                        </strong>

                        <span>
                            Bengaluru · Updated recently
                        </span>

                    </div>

                </div>


                <div class="alert">

                    <div class="alert-icon">
                        👤
                    </div>

                    <div>

                        <strong>
                            Owner available
                        </strong>

                        <span>
                            Contact information available
                        </span>

                    </div>

                </div>


                <div class="alert">

                    <div class="alert-icon">
                        🏥
                    </div>

                    <div>

                        <strong>
                            Veterinary support
                        </strong>

                        <span>
                            Nearby clinics can be searched
                        </span>

                    </div>

                </div>


                <div class="alert">

                    <div class="alert-icon">
                        🛡️
                    </div>

                    <div>

                        <strong>
                            Privacy protected
                        </strong>

                        <span>
                            Owner controls the information shown
                        </span>

                    </div>

                </div>

            </div>

        </div>

    </div>

</section>



<!-- =========================================================
     PET PROFILE
========================================================= -->

<section
    class="profile-section"
    id="profile">

    <div class="section-head">

        <div class="section-mini">
            DIGITAL PET PROFILE
        </div>

        <h2>
            Everything about your pet.
        </h2>

        <p>
            A clean digital identity that can be opened
            from the pet's QR tag.
        </p>

    </div>


    <div class="profile">


        <!-- PROFILE LEFT -->

        <div class="profile-left">

            <div>

                <div class="profile-image">
                    🐶
                </div>

                <h2 id="profileName">
                    Buddy
                </h2>

                <p id="profileBreed">
                    Golden Retriever
                </p>

                <span class="verified">
                    ✓ VERIFIED PET ID
                </span>

            </div>


            <p class="profile-id">

                Pet ID:
                <strong>
                    PV-2026-6767
                </strong>

            </p>

        </div>



        <!-- PROFILE RIGHT -->

        <div class="profile-right">

            <h3>
                Pet information
            </h3>


            <div class="info-grid">

                <div class="info">

                    <small>
                        Pet name
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


            <div class="owner">

                <h4>
                    👤 Owner information
                </h4>

                <p>

                    <strong id="infoOwner">
                        MAX 
                    </strong>

                    <br>

                    📞
                    <strong id="infoPhone">
                        +91 XXXXX XXXXX
                    </strong>

                </p>

            </div>


            <div class="owner">

                <h4>
                    📝 Important information
                </h4>

                <p id="infoNotes">

                    Friendly pet. Be safee
                    Please contact the owner if found.

                </p>

            </div>

        </div>

    </div>

</section>



<!-- =========================================================
     LOCATION
========================================================= -->

<section
    class="location-section"
    id="location">

    <div class="section-head">

        <div class="section-mini">
            SMART LOCATION
        </div>

        <h2>
            Find where the pet was seen.
        </h2>

        <p>
            Capture the current GPS location and open it
            directly in Google Maps.
        </p>

    </div>


    <div class="location-grid">


        <div class="location-card">

            <h3>
                📍 Location map
            </h3>

            <p>
                The demonstration starts with a sample
                location. Use GPS to replace it.
            </p>


            <div class="map">

                <div class="map-pin">
                    📍
                </div>

            </div>

        </div>



        <div class="location-card">

            <h3>
                Last-seen information
            </h3>

            <p>
                The owner can record the location where
                the pet was last seen.
            </p>


            <div class="location-data">

                <strong id="locationStatus">
                    Demo Location
                </strong>

                <br><br>

                <span id="coordinates">
                    12.9716, 77.5946
                </span>

            </div>


            <div class="location-buttons">

                <button
                    class="gps-btn"
                    onclick="getGPS()">

                    📍 Use My GPS

                </button>


                <button
                    class="map-btn"
                    onclick="openMaps()">

                    🗺️ Open Maps

                </button>

            </div>

        </div>

    </div>

</section>



<!-- =========================================================
     VETERINARY CARE
========================================================= -->

<section id="hospitals">

    <div class="section-head">

        <div class="section-mini">
            PET CARE
        </div>

        <h2>
            Veterinary help, when needed.
        </h2>

        <p>
            Search nearby veterinary services directly
            from the PAWSAFE platform.
        </p>

    </div>


    <div class="hospitals">


        <div class="hospital">

            <div class="hospital-icon">
                🏥
            </div>

            <h3>
                Veterinary Hospital
            </h3>

            <p>
                Find animal hospitals around your
                current location.
            </p>

            <button onclick="searchHospital()">
                Find Nearby →
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
                Search for veterinary clinics and
                animal healthcare services.
            </p>

            <button onclick="searchClinic()">
                Search Clinics →
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
                Quickly search for emergency veterinary
                services nearby.
            </p>

            <button onclick="searchEmergency()">
                Emergency Search →
            </button>

        </div>

    </div>

</section>



<!-- =========================================================
     DIGITAL ID
========================================================= -->

<section class="digital-id">

    <div class="id-card">


        <div class="id-text">

            <div class="section-mini">
                DIGITAL PET ID
            </div>

            <h2>
                One identity for every paw.
            </h2>

            <p>
                Every registered pet receives a unique
                PAWSAFE identity that can be connected
                to a QR tag.
            </p>


            <ul class="check-list">

                <li>
                    <span>✓</span>
                    Unique Pet ID
                </li>

                <li>
                    <span>✓</span>
                    Owner information
                </li>

                <li>
                    <span>✓</span>
                    Pet photo and profile
                </li>

                <li>
                    <span>✓</span>
                    Health information
                </li>

                <li>
                    <span>✓</span>
                    Location sharing
                </li>

            </ul>

        </div>



        <div class="id-visual">

            <h3>
                🐾 PAWSAFE ID
            </h3>

            <div id="qrcode"></div>

            <div class="id-number">
                PV-2026-6767
            </div>

            <p style="margin-top:8px;color:#718078;font-size:11px;">
                Scan to view pet profile
            </p>

        </div>

    </div>

</section>



<!-- =========================================================
     HEALTH RECORDS
========================================================= -->

<section>

    <div class="section-head">

        <div class="section-mini">
            PET HEALTH
        </div>

        <h2>
            Important health information.
        </h2>

        <p>
            Keep essential information available when
            a pet needs help.
        </p>

    </div>


    <div class="health-grid">


        <div class="health">

            <div class="health-icon">
                💉
            </div>

            <h3>
                Vaccination
            </h3>

            <p>
                Store vaccination information
                for easier veterinary access.
            </p>

        </div>


        <div class="health">

            <div class="health-icon">
                🩹
            </div>

            <h3>
                Medical Notes
            </h3>

            <p>
                Keep useful medical notes
                available for authorized help.
            </p>

        </div>


        <div class="health">

            <div class="health-icon">
                ⚠️
            </div>

            <h3>
                Allergies
            </h3>

            <p>
                Important allergy information
                can be displayed when necessary.
            </p>

        </div>


        <div class="health">

            <div class="health-icon">
                ❤️
            </div>

            <h3>
                Emergency Contact
            </h3>

            <p>
                Quick access to the owner's
                emergency contact information.
            </p>

        </div>

    </div>

</section>



<!-- =========================================================
     OWNER DASHBOARD
========================================================= -->

<section
    class="dashboard-section"
    id="dashboard">

    <div class="section-head">

        <div class="section-mini">
            OWNER DASHBOARD
        </div>

        <h2>
            Manage your pet's profile.
        </h2>

        <p>
            Change the demo information and instantly
            update the digital profile.
        </p>

    </div>


    <div class="dashboard">

        <div class="dashboard-header">

            <div>

                <h3>
                    PAWSAFE Owner Dashboard
                </h3>

                <p>
                    Manage your public pet information
                </p>

            </div>

            <span class="active">
                ● ACTIVE
            </span>

        </div>


        <div class="form">


            <div class="field">

                <label>
                    PET NAME
                </label>

                <input
                    id="petInput"
                    value="OREO">

            </div>


            <div class="field">

                <label>
                    BREED
                </label>

                <input
                    id="breedInput"
                    value="Golden Retriever">

            </div>


            <div class="field">

                <label>
                    AGE
                </label>

                <input
                    id="ageInput"
                    value="3 Years">

            </div>


            <div class="field">

                <label>
                    GENDER
                </label>

                <select id="genderInput">

                    <option>Male</option>

                    <option>Female</option>

                </select>

            </div>


            <div class="field">

                <label>
                    OWNER NAME
                </label>

                <input
                    id="ownerInput"
                    value="Vikas">

            </div>


            <div class="field">

                <label>
                    CONTACT NUMBER
                </label>

                <input
                    id="phoneInput"
                    value="+91 XXXXX XXXXX">

            </div>


            <div class="field full">

                <label>
                    IMPORTANT INFORMATION
                </label>

                <textarea id="notesInput">Friendly pet. Please contact the owner if found.</textarea>

            </div>

        </div>


        <button
            class="primary save-button"
            onclick="saveProfile()">

            💾 Save Pet Profile

        </button>

    </div>

</section>



<!-- =========================================================
     🛍️ PAWSAFE SHOP
========================================================= -->

<section
    class="shop-section"
    id="shop">


    <div class="shop-top">

        <div>

            <div class="shop-badge">
                PAWSAFE SHOP
            </div>

            <h2>
                Smart products for safer pets.
            </h2>

            <p>
                Explore PAWSAFE accessories and pet-care products.
            </p>

        </div>


        <button
            class="shop-button"
            onclick="showAllProducts()">

            View All Products

        </button>

    </div>


    <div class="products">


        <!-- PRODUCT 1 -->

        <div class="product">

            <span class="product-tag">
                POPULAR
            </span>

            <div class="product-image">
                🏷️
            </div>

            <h3>
                QR Pet Tag
            </h3>

            <p class="product-description">
                Durable QR identity tag for pet collars.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹499
                </span>

                <button
                    class="buy"
                    onclick="addToCart('QR Pet Tag',499)">

                    Buy Now

                </button>

            </div>

        </div>



        <!-- PRODUCT 2 -->

        <div class="product">

            <span class="product-tag">
                SMART
            </span>

            <div class="product-image">
                📡
            </div>

            <h3>
                GPS Tracker Collar
            </h3>

            <p class="product-description">
                Smart location tracking collar concept.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹1,999
                </span>

                <button
                    class="buy"
                    onclick="addToCart('GPS Tracker Collar',1999)">

                    Buy Now

                </button>

            </div>

        </div>



        <!-- PRODUCT 3 -->

        <div class="product">

            <div class="product-image">
                🦴
            </div>

            <h3>
                Custom Name Tag
            </h3>

            <p class="product-description">
                Personalized pet name and ID tag.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹399
                </span>

                <button
                    class="buy"
                    onclick="addToCart('Custom Name Tag',399)">

                    Buy Now

                </button>

            </div>

        </div>



        <!-- PRODUCT 4 -->

        <div class="product">

            <div class="product-image">
                🟢
            </div>

            <h3>
                Reflective Collar
            </h3>

            <p class="product-description">
                High-visibility collar for safer walks.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹699
                </span>

                <button
                    class="buy"
                    onclick="addToCart('Reflective Collar',699)">

                    Buy Now

                </button>

            </div>

        </div>



        <!-- PRODUCT 5 -->

        <div class="product">

            <span class="product-tag">
                KIT
            </span>

            <div class="product-image">
                🧰
            </div>

            <h3>
                Pet Care Kit
            </h3>

            <p class="product-description">
                Everyday essentials packed together.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹1,299
                </span>

                <button
                    class="buy"
                    onclick="addToCart('Pet Care Kit',1299)">

                    Buy Now

                </button>

            </div>

        </div>



        <!-- PRODUCT 6 -->

        <div class="product">

            <div class="product-image">
                🥤
            </div>

            <h3>
                Travel Water Bottle
            </h3>

            <p class="product-description">
                Portable water bottle for pet travel.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹599
                </span>

                <button
                    class="buy"
                    onclick="addToCart('Travel Water Bottle',599)">

                    Buy Now

                </button>

            </div>

        </div>



        <!-- PRODUCT 7 -->

        <div class="product">

            <div class="product-image">
                🎀
            </div>

            <h3>
                Personalised Collar
            </h3>

            <p class="product-description">
                Stylish collar with your pet's details.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹799
                </span>

                <button
                    class="buy"
                    onclick="addToCart('Personalised Collar',799)">

                    Buy Now

                </button>

            </div>

        </div>



        <!-- PRODUCT 8 -->

        <div class="product">

            <span class="product-tag">
                NEW
            </span>

            <div class="product-image">
                🧸
            </div>

            <h3>
                Pet Comfort Toy
            </h3>

            <p class="product-description">
                Soft enrichment toy for happy pets.
            </p>

            <div class="product-bottom">

                <span class="price">
                    ₹349
                </span>

                <button
                    class="buy"
                    onclick="addToCart('Pet Comfort Toy',349)">

                    Buy Now

                </button>

            </div>

        </div>

    </div>

</section>



<!-- =========================================================
     COMMUNITY
========================================================= -->

<section class="community">

    <div class="section-head">

        <div class="section-mini">
            OUR COMMUNITY
        </div>

        <h2>
            Together, we can protect more pets.
        </h2>

        <p>
            PAWSAFE is more than technology — it is
            a community built around responsible pet care.
        </p>

    </div>


    <div class="community-grid">


        <div class="community-card">

            <div class="community-card-icon">
                🚨
            </div>

            <h3>
                Report Lost Pet
            </h3>

            <p>
                Help spread awareness when a pet goes missing.
            </p>

            <button
                onclick="reportLost()">

                Report Now

            </button>

        </div>


        <div class="community-card">

            <div class="community-card-icon">
                📢
            </div>

            <h3>
                Spread Awareness
            </h3>

            <p>
                Share the PAWSAFE concept with your
                community and fellow pet owners.
            </p>

            <button
                onclick="shareWebsite()">

                Share PAWSAFE

            </button>

        </div>


        <div class="community-card">

            <div class="community-card-icon">
                ❤️
            </div>

            <h3>
                Adopt & Care
            </h3>

            <p>
                Encourage responsible pet ownership,
                adoption and animal welfare.
            </p>

            <button
                onclick="showToast('Thank you for supporting pets ❤️')">

                Learn More

            </button>

        </div>

    </div>

</section>



<!-- =========================================================
     FINAL CTA
========================================================= -->

<section class="final-cta">

    <div class="cta-box">

        <h2>
            A safer tomorrow for every paw.
        </h2>

        <p>
            Smart identification. Better protection.
            Faster reunions.
        </p>

        <button
            class="primary"
            onclick="scrollToSection('shop')">

            🛍️ Explore PAWSAFE Shop

        </button>

    </div>

</section>



<!-- =========================================================
     FOOTER
========================================================= -->

<footer id="contact">

    <div class="footer-grid">


        <div>

            <div class="footer-logo">
                PAW<span>SAFE</span>
            </div>

            <p>
                A student-led smart pet safety concept
                designed to help lost pets reconnect
                with their families.
            </p>

        </div>


        <div class="footer-column">

            <h4>
                Quick Links
            </h4>

            <a href="#home">
                Home
            </a>

            <a href="#find">
                Find Pet
            </a>

            <a href="#profile">
                Pet Profile
            </a>

            <a href="#shop">
                Products
            </a>

        </div>


        <div class="footer-column">

            <h4>
                Pet Care
            </h4>

            <a href="#location">
                Location
            </a>

            <a href="#hospitals">
                Veterinary Help
            </a>

            <a href="#profile">
                Health Records
            </a>

            <a href="#about">
                How It Works
            </a>

        </div>


        <div class="footer-column">

            <h4>
                PAWSAFE
            </h4>

            <p>
                Scan. Connect. Reunite.
            </p>

            <p style="margin-top:10px;">
                Made with ❤️ for a better tomorrow.
            </p>

        </div>

    </div>


    <div class="copyright">

        <p>
            © 2026 PAWSAFE · Smart Pet Identification System
        </p>

    </div>

</footer>



<!-- =========================================================
     CART BUTTON
========================================================= -->

<div
    class="cart"
    onclick="openCart()">

    🛒

    <span
        class="cart-count"
        id="cartCount">

        0

    </span>

</div>



<!-- =========================================================
     TOAST
========================================================= -->

<div
    class="toast"
    id="toast">

    Done ✓

</div>



<script>

/* =========================================================
   VARIABLES
========================================================= */

let latitude = 12.9716;
let longitude = 77.5946;

let cart = [];


/* =========================================================
   TOAST
========================================================= */

function showToast(message){

    const toast =
        document.getElementById("toast");

    toast.textContent = message;

    toast.classList.add("show");

    setTimeout(() => {

        toast.classList.remove("show");

    },2500);

}


/* =========================================================
   SCROLL
========================================================= */

function scrollToSection(id){

    document
        .getElementById(id)
        .scrollIntoView({
            behavior:"smooth"
        });

}


/* =========================================================
   PROFILE SAVE
========================================================= */

function saveProfile(){

    const pet =
        document.getElementById("petInput").value;

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


    document.getElementById("heroName")
        .textContent = pet;

    document.getElementById("heroBreed")
        .textContent =
        breed + " · " + gender;


    document.getElementById("profileName")
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


    showToast(
        "Pet profile updated successfully ✓"
    );

}


/* =========================================================
   LOAD PROFILE
========================================================= */

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


    document.getElementById("petInput")
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


    document.getElementById("heroName")
        .textContent = pet;

    document.getElementById("heroBreed")
        .textContent =
        breed + " · " + gender;

    document.getElementById("profileName")
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


/* =========================================================
   GPS LOCATION
========================================================= */

function getGPS(){

    if(!navigator.geolocation){

        showToast(
            "GPS is not supported."
        );

        return;
    }


    document.getElementById("locationStatus")
        .textContent =
        "Getting GPS location...";


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
                "pawsafe_lat",
                latitude
            );

            localStorage.setItem(
                "pawsafe_lng",
                longitude
            );


            showToast(
                "Location updated ✓"
            );

        },

        function(){

            document.getElementById("locationStatus")
                .textContent =
                "Location permission denied";

            showToast(
                "Please allow location permission."
            );

        }

    );

}


/* =========================================================
   OPEN GOOGLE MAPS
========================================================= */

function openMaps(){

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


/* =========================================================
   VETERINARY SEARCH
========================================================= */

function searchHospital(){

    window.open(
        "https://www.google.com/maps/search/veterinary+hospital+near+me",
        "_blank"
    );

}


function searchClinic(){

    window.open(
        "https://www.google.com/maps/search/pet+clinic+near+me",
        "_blank"
    );

}


function searchEmergency(){

    window.open(
        "https://www.google.com/maps/search/emergency+veterinary+hospital+near+me",
        "_blank"
    );

}


/* =========================================================
   PET QR
========================================================= */

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

            colorDark:"#10211a",

            colorLight:"#ffffff",

            correctLevel:
                QRCode.CorrectLevel.H
        }

    );

}


/* =========================================================
   DEMO SCANNER
========================================================= */

function scanDemo(){

    const petID =
        prompt(
            "Enter Pet ID",
            "PS-2026-001"
        );


    if(petID){

        if(
            petID.toUpperCase()
            === "PS-2026-001"
        ){

            scrollToSection("profile");

            showToast(
                "Pet profile found ✓"
            );

        }else{

            showToast(
                "Demo Pet ID not found."
            );

        }

    }

}


/* =========================================================
   CALL OWNER
========================================================= */

function callOwner(){

    const phone =
        document.getElementById("phoneInput").value;

    if(
        phone.includes("676767")
    ){

        showToast(
            "Demo: Owner contact would open here."
        );

        return;
    }


    window.location.href =
        "tel:" + phone;

}


/* =========================================================
   SHOP CART
========================================================= */

function addToCart(
    productName,
    price
){

    cart.push({
        name:productName,
        price:price
    });


    document.getElementById("cartCount")
        .textContent = cart.length;


    showToast(
        productName +
        " added to cart 🛒"
    );

}


/* =========================================================
   OPEN CART
========================================================= */

function openCart(){

    if(cart.length === 0){

        showToast(
            "Your cart is empty."
        );

        scrollToSection("shop");

        return;
    }


    let total = 0;

    let message =
        "PAWSAFE CART\n\n";


    cart.forEach(
        function(item,index){

            message +=
                (index+1)
                + ". "
                + item.name
                + " — ₹"
                + item.price
                + "\n";

            total += item.price;

        }
    );


    message +=
        "\nTOTAL: ₹"
        + total;


    alert(message);

}


/* =========================================================
   SHOP
========================================================= */

function showAllProducts(){

    showToast(
        "Showing all PAWSAFE products ✓"
    );

}


/* =========================================================
   COMMUNITY
========================================================= */

function reportLost(){

    const pet =
        prompt(
            "Enter Pet ID to report:",
            "PS-2026-001"
        );


    if(pet){

        showToast(
            "Lost pet report created for "
            + pet
        );

    }

}


/* =========================================================
   SHARE
========================================================= */

function shareWebsite(){

    if(
        navigator.share
    ){

        navigator.share({

            title:"PAWSAFE",

            text:
                "Check out PAWSAFE — Smart Pet Safety Platform!",

            url:
                window.location.href

        });

    }else{

        navigator.clipboard.writeText(
            window.location.href
        );

        showToast(
            "Website link copied ✓"
        );

    }

}


/* =========================================================
   LOAD LOCATION
========================================================= */

function loadLocation(){

    const lat =
        localStorage.getItem(
            "pawsafe_lat"
        );

    const lng =
        localStorage.getItem(
            "pawsafe_lng"
        );


    if(lat && lng){

        latitude =
            parseFloat(lat);

        longitude =
            parseFloat(lng);


        document.getElementById(
            "locationStatus"
        ).textContent =
            "✓ Saved Last-Seen Location";


        document.getElementById(
            "coordinates"
        ).textContent =
            latitude.toFixed(6)
            + ", "
            + longitude.toFixed(6);

    }

}


/* =========================================================
   START
========================================================= */

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
