# antioquia-esencia
Sitio web demostrativo de turismo generado con IA
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#102A43">

<title>Antioquia Esencia | Antioquia no se visita. Se vive.</title>

<meta name="description" content="Experiencias de turismo en Antioquia inspiradas en naturaleza, cultura, gastronomía, pueblos y momentos para recordar. Sitio demostrativo.">

<style>

/* ==========================================================
   ANTIOQUIA ESENCIA
   SITIO DEMOSTRATIVO — HTML + CSS + JAVASCRIPT

   GUÍA RÁPIDA PARA ESTUDIANTES
   1. NOMBRE: buscar "Antioquia Esencia"
   2. COLORES: modificar las variables :root
   3. TEXTOS: editar directamente el contenido HTML
   4. DESTINOS: sección #destinos
   5. EXPERIENCIAS: sección #experiencias
   6. FOTOGRAFÍAS: sustituir los background-image
   7. WHATSAPP: modificar WHATSAPP_NUMBER al final
   8. CONTACTO: sección #contacto y constantes JS
   ========================================================== */

:root{
    --azul:#102A43;
    --azul-medio:#176B87;
    --cafe:#704214;
    --dorado:#C89B3C;
    --terracota:#A63D40;
    --crema:#F7F1E5;
    --blanco:#FFFFFF;
    --texto:#243746;
    --texto-suave:#647583;
    --linea:#E7E0D4;
    --sombra:0 18px 50px rgba(16,42,67,.12);
    --radio:20px;
    --max:1200px;
}

*{
    box-sizing:border-box;
}

html{
    scroll-behavior:smooth;
    scroll-padding-top:90px;
}

body{
    margin:0;
    font-family:Inter,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;
    color:var(--texto);
    background:var(--blanco);
    line-height:1.6;
}

body.menu-open{
    overflow:hidden;
}

img{
    max-width:100%;
    display:block;
}

a{
    color:inherit;
}

button,
input,
select,
textarea{
    font:inherit;
}

button{
    cursor:pointer;
}

:focus-visible{
    outline:3px solid var(--dorado);
    outline-offset:4px;
}

.container{
    width:min(var(--max),calc(100% - 40px));
    margin:auto;
}

.section{
    padding:100px 0;
}

.section-small{
    padding:70px 0;
}

.eyebrow{
    display:inline-flex;
    align-items:center;
    gap:10px;
    margin-bottom:16px;
    color:var(--terracota);
    font-size:.78rem;
    font-weight:800;
    letter-spacing:.15em;
    text-transform:uppercase;
}

.eyebrow::before{
    content:"";
    width:30px;
    height:2px;
    background:var(--dorado);
}

h1,h2,h3,p{
    margin-top:0;
}

h1,h2,h3{
    line-height:1.08;
}

h1{
    font-family:Georgia,"Times New Roman",serif;
    font-size:clamp(3.4rem,8vw,7.4rem);
    letter-spacing:-.055em;
}

h2{
    font-family:Georgia,"Times New Roman",serif;
    font-size:clamp(2.2rem,5vw,4.2rem);
    letter-spacing:-.035em;
}

h3{
    font-size:1.35rem;
}

.section-head{
    max-width:720px;
    margin-bottom:45px;
}

.section-head p{
    color:var(--texto-suave);
    font-size:1.08rem;
}

.btn{
    display:inline-flex;
    justify-content:center;
    align-items:center;
    gap:10px;
    min-height:50px;
    padding:14px 24px;
    border:1px solid transparent;
    border-radius:50px;
    background:var(--terracota);
    color:white;
    font-size:.86rem;
    font-weight:800;
    letter-spacing:.04em;
    text-decoration:none;
    transition:.25s ease;
}

.btn:hover{
    transform:translateY(-3px);
    box-shadow:0 12px 30px rgba(166,61,64,.25);
}

.btn-gold{
    background:var(--dorado);
    color:var(--azul);
}

.btn-outline{
    background:transparent;
    border-color:rgba(255,255,255,.55);
    color:white;
}

.btn-outline:hover{
    background:white;
    color:var(--azul);
}

.btn-blue{
    background:var(--azul);
}

.actions{
    display:flex;
    flex-wrap:wrap;
    gap:12px;
}

.skip-link{
    position:fixed;
    top:-100px;
    left:20px;
    z-index:999;
    background:white;
    color:black;
    padding:12px 18px;
}

.skip-link:focus{
    top:10px;
}

/* ===================== HEADER ===================== */

.header{
    position:sticky;
    top:0;
    z-index:100;
    background:rgba(16,42,67,.97);
    color:white;
    backdrop-filter:blur(12px);
    border-bottom:1px solid rgba(255,255,255,.1);
}

.nav{
    min-height:82px;
    display:flex;
    align-items:center;
    justify-content:space-between;
    gap:30px;
}

.logo{
    display:flex;
    align-items:center;
    gap:12px;
    text-decoration:none;
}

.logo-mark{
    width:40px;
    height:40px;
    border:1px solid var(--dorado);
    border-radius:50% 50% 50% 8px;
    transform:rotate(-12deg);
    display:grid;
    place-items:center;
}

.logo-mark::after{
    content:"A";
    color:var(--dorado);
    font-family:Georgia,serif;
    font-size:1.25rem;
    transform:rotate(12deg);
}

.logo-text{
    line-height:.92;
}

.logo-text strong{
    display:block;
    font-family:Georgia,serif;
    font-size:1.08rem;
    letter-spacing:.08em;
}

.logo-text small{
    display:block;
    margin-top:6px;
    color:var(--dorado);
    font-size:.62rem;
    letter-spacing:.28em;
}

.nav-links{
    display:flex;
    align-items:center;
    gap:25px;
}

.nav-links>a:not(.btn){
    position:relative;
    color:#E5EDF3;
    font-size:.88rem;
    text-decoration:none;
}

.nav-links>a:not(.btn)::after{
    content:"";
    position:absolute;
    left:0;
    bottom:-7px;
    width:0;
    height:2px;
    background:var(--dorado);
    transition:.25s;
}

.nav-links>a:not(.btn):hover::after{
    width:100%;
}

.menu-btn{
    display:none;
    min-width:48px;
    min-height:48px;
    border:1px solid rgba(255,255,255,.3);
    border-radius:50%;
    background:transparent;
    color:white;
    font-size:1.3rem;
}

/* ===================== HERO ===================== */

.hero{
    position:relative;
    min-height:calc(100vh - 82px);
    display:flex;
    align-items:center;
    overflow:hidden;
    color:white;
    background:
        linear-gradient(90deg,
            rgba(9,28,43,.96) 0%,
            rgba(16,42,67,.84) 45%,
            rgba(16,42,67,.28) 100%),
        linear-gradient(135deg,#102A43 0%,#176B87 55%,#704214 100%);
}

/*
   6. FOTOGRAFÍAS:
   Puedes reemplazar el background anterior por:
   background:
   linear-gradient(...),
   url("TU-FOTO.jpg") center/cover;
*/

.hero::before{
    content:"";
    position:absolute;
    width:600px;
    height:600px;
    right:-100px;
    top:-180px;
    border:1px solid rgba(200,155,60,.25);
    border-radius:50%;
}

.hero::after{
    content:"";
    position:absolute;
    width:420px;
    height:420px;
    right:80px;
    bottom:-230px;
    border:1px solid rgba(255,255,255,.14);
    border-radius:50%;
}

.hero-content{
    position:relative;
    z-index:2;
    padding:110px 0 80px;
    max-width:850px;
}

.hero .eyebrow{
    color:#E8D19B;
}

.hero h1{
    max-width:830px;
    margin-bottom:25px;
}

.hero h1 em{
    color:var(--dorado);
    font-style:italic;
}

.hero-subtitle{
    max-width:630px;
    margin-bottom:32px;
    color:#D9E3EA;
    font-size:clamp(1.05rem,2vw,1.25rem);
}

.hero-tags{
    display:flex;
    flex-wrap:wrap;
    gap:10px;
    margin-top:55px;
}

.hero-tag{
    padding:8px 15px;
    border:1px solid rgba(255,255,255,.22);
    border-radius:30px;
    color:#E5EDF3;
    font-size:.78rem;
    letter-spacing:.06em;
}

.scroll-hint{
    position:absolute;
    z-index:3;
    right:40px;
    bottom:35px;
    color:#D9E3EA;
    font-size:.7rem;
    letter-spacing:.15em;
    writing-mode:vertical-rl;
}

/* ===================== INTRO ===================== */

.intro{
    background:var(--crema);
}

.intro-grid{
    display:grid;
    grid-template-columns:.8fr 1.2fr;
    gap:80px;
    align-items:start;
}

.intro-number{
    color:var(--dorado);
    font-family:Georgia,serif;
    font-size:6rem;
    line-height:1;
}

.intro-copy{
    max-width:700px;
}

.intro-copy p{
    color:var(--texto-suave);
    font-size:1.15rem;
}

/* ===================== DESTINOS ===================== */

.destinations-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:22px;
}

.destination{
    position:relative;
    min-height:390px;
    overflow:hidden;
    border-radius:var(--radio);
    background:
        linear-gradient(to top,rgba(8,27,42,.95),rgba(16,42,67,.05)),
        linear-gradient(135deg,var(--azul-medio),var(--cafe));
    color:white;
    box-shadow:var(--sombra);
}

.destination:nth-child(2){
    background:
        linear-gradient(to top,rgba(8,27,42,.95),rgba(16,42,67,.08)),
        linear-gradient(135deg,#426B55,#704214);
}

.destination:nth-child(3){
    background:
        linear-gradient(to top,rgba(8,27,42,.95),rgba(16,42,67,.08)),
        linear-gradient(135deg,#8B6445,#A63D40);
}

.destination:nth-child(4){
    background:
        linear-gradient(to top,rgba(8,27,42,.95),rgba(16,42,67,.08)),
        linear-gradient(135deg,#C89B3C,#704214);
}

.destination:nth-child(5){
    background:
        linear-gradient(to top,rgba(8,27,42,.95),rgba(16,42,67,.08)),
        linear-gradient(135deg,#176B87,#102A43);
}

.destination:nth-child(6){
    background:
        linear-gradient(to top,rgba(8,27,42,.95),rgba(16,42,67,.08)),
        linear-gradient(135deg,#315F45,#9B7653);
}

.destination-visual{
    position:absolute;
    inset:0;
    opacity:.32;
}

.destination-visual::before,
.destination-visual::after{
    content:"";
    position:absolute;
    border-radius:50% 50% 0 0;
    background:rgba(255,255,255,.15);
    transform:rotate(-8deg);
}

.destination-visual::before{
    width:130%;
    height:55%;
    left:-30%;
    bottom:0;
}

.destination-visual::after{
    width:110%;
    height:42%;
    right:-35%;
    bottom:0;
}

.destination-content{
    position:absolute;
    z-index:2;
    left:0;
    right:0;
    bottom:0;
    padding:28px;
}

.destination-type{
    display:block;
    margin-bottom:10px;
    color:#E7C978;
    font-size:.72rem;
    font-weight:800;
    letter-spacing:.14em;
    text-transform:uppercase;
}

.destination h3{
    margin-bottom:10px;
    font-family:Georgia,serif;
    font-size:2rem;
}

.destination p{
    margin-bottom:18px;
    color:#E0E8ED;
    font-size:.92rem;
}

.discover{
    display:inline-flex;
    align-items:center;
    gap:8px;
    color:white;
    border:0;
    padding:0;
    background:transparent;
    font-weight:700;
}

.discover span{
    transition:.2s;
}

.discover:hover span{
    transform:translateX(5px);
}

/* ===================== EXPERIENCIAS ===================== */

.experiences{
    background:#F5F7F8;
}

.filters{
    display:flex;
    flex-wrap:wrap;
    gap:10px;
    margin-bottom:35px;
}

.filter{
    min-height:44px;
    padding:9px 18px;
    border:1px solid #CBD5DC;
    border-radius:30px;
    background:white;
    color:var(--azul);
    font-weight:700;
}

.filter[aria-pressed="true"]{
    border-color:var(--azul);
    background:var(--azul);
    color:white;
}

.experience-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:24px;
}

.experience-card{
    position:relative;
    display:flex;
    flex-direction:column;
    overflow:hidden;
    border:1px solid #E2E8EC;
    border-radius:var(--radio);
    background:white;
    transition:.3s;
}

.experience-card:hover{
    transform:translateY(-6px);
    box-shadow:var(--sombra);
}

.experience-card.recommended{
    border:2px solid var(--dorado);
}

.recommended-label{
    position:absolute;
    z-index:3;
    top:16px;
    right:16px;
    padding:6px 11px;
    border-radius:30px;
    background:var(--dorado);
    color:var(--azul);
    font-size:.7rem;
    font-weight:900;
}

.experience-image{
    height:180px;
    position:relative;
    overflow:hidden;
    background:linear-gradient(135deg,var(--azul-medio),var(--cafe));
}

.experience-image::before{
    content:"";
    position:absolute;
    width:120%;
    height:100%;
    left:-30%;
    bottom:-50%;
    border-radius:50% 50% 0 0;
    background:rgba(255,255,255,.18);
    transform:rotate(8deg);
}

.experience-card:nth-child(2) .experience-image{
    background:linear-gradient(135deg,#176B87,#3E7657);
}

.experience-card:nth-child(3) .experience-image{
    background:linear-gradient(135deg,#A63D40,#704214);
}

.experience-card:nth-child(4) .experience-image{
    background:linear-gradient(135deg,#102A43,#176B87);
}

.experience-card:nth-child(5) .experience-image{
    background:linear-gradient(135deg,#315F45,#102A43);
}

.experience-card:nth-child(6) .experience-image{
    background:linear-gradient(135deg,#A63D40,#C89B3C);
}

.experience-body{
    display:flex;
    flex-direction:column;
    flex:1;
    padding:26px;
}

.category{
    color:var(--terracota);
    font-size:.72rem;
    font-weight:800;
    letter-spacing:.1em;
    text-transform:uppercase;
}

.experience-body h3{
    margin:9px 0;
    font-family:Georgia,serif;
    font-size:1.55rem;
}

.experience-body>p{
    color:var(--texto-suave);
}

.meta{
    display:flex;
    flex-wrap:wrap;
    gap:8px;
    margin:5px 0 18px;
}

.meta span{
    padding:5px 9px;
    border-radius:5px;
    background:var(--crema);
    font-size:.76rem;
}

.includes{
    margin:0 0 24px;
    padding-left:18px;
    color:var(--texto-suave);
    font-size:.88rem;
}

.experience-body .btn{
    margin-top:auto;
    align-self:flex-start;
}

/* ===================== EXPERIENCIA DESTACADA ===================== */

.featured{
    position:relative;
    overflow:hidden;
    background:var(--azul);
    color:white;
}

.featured::before{
    content:"";
    position:absolute;
    width:500px;
    height:500px;
    right:-180px;
    top:-180px;
    border:1px solid rgba(200,155,60,.25);
    border-radius:50%;
}

.featured-layout{
    position:relative;
    display:grid;
    grid-template-columns:.9fr 1.1fr;
    gap:80px;
    align-items:center;
}

.featured .eyebrow{
    color:var(--dorado);
}

.featured p{
    color:#C7D3DC;
}

.timeline{
    position:relative;
    padding-left:35px;
}

.timeline::before{
    content:"";
    position:absolute;
    left:7px;
    top:12px;
    bottom:12px;
    width:1px;
    background:rgba(200,155,60,.5);
}

.day{
    position:relative;
    padding:0 0 35px;
}

.day:last-child{
    padding-bottom:0;
}

.day::before{
    content:"";
    position:absolute;
    left:-35px;
    top:6px;
    width:15px;
    height:15px;
    border-radius:50%;
    background:var(--dorado);
    box-shadow:0 0 0 7px rgba(200,155,60,.12);
}

.day small{
    color:var(--dorado);
    font-weight:800;
    letter-spacing:.12em;
}

.day h3{
    margin:7px 0;
    font-family:Georgia,serif;
    font-size:1.6rem;
}

.demo-note{
    margin-top:25px;
    padding:12px 15px;
    border-left:2px solid var(--dorado);
    background:rgba(255,255,255,.06);
    font-size:.82rem;
}

/* ===================== POR QUÉ ===================== */

.why-grid{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:30px;
}

.why-item{
    padding-top:25px;
    border-top:2px solid var(--dorado);
}

.why-number{
    color:var(--dorado);
    font-family:Georgia,serif;
    font-size:2.8rem;
}

.why-item p{
    color:var(--texto-suave);
}

/* ===================== EMOCIONAL ===================== */

.emotional{
    padding:120px 0;
    background:var(--crema);
    text-align:center;
}

.emotional blockquote{
    max-width:930px;
    margin:0 auto;
    color:var(--azul);
    font-family:Georgia,serif;
    font-size:clamp(2rem,5vw,4rem);
    line-height:1.18;
    letter-spacing:-.03em;
}

.emotional blockquote em{
    color:var(--terracota);
}

/* ===================== GALERÍA ===================== */

.gallery{
    display:grid;
    grid-template-columns:2fr 1fr 1fr;
    grid-template-rows:250px 250px;
    gap:12px;
}

.gallery-item{
    position:relative;
    overflow:hidden;
    border-radius:14px;
    background:linear-gradient(135deg,var(--azul-medio),var(--cafe));
}

.gallery-item:first-child{
    grid-row:1/3;
}

.gallery-item:nth-child(2){
    background:linear-gradient(135deg,#704214,#C89B3C);
}

.gallery-item:nth-child(3){
    background:linear-gradient(135deg,#176B87,#315F45);
}

.gallery-item:nth-child(4){
    background:linear-gradient(135deg,#A63D40,#704214);
}

.gallery-item:nth-child(5){
    background:linear-gradient(135deg,#102A43,#176B87);
}

.gallery-item::before{
    content:"";
    position:absolute;
    width:130%;
    height:90%;
    left:-20%;
    bottom:-55%;
    background:rgba(255,255,255,.14);
    border-radius:50% 50% 0 0;
    transition:.5s;
}

.gallery-item:hover::before{
    transform:translateY(-20px) scale(1.05);
}

.gallery-label{
    position:absolute;
    left:20px;
    bottom:18px;
    color:white;
    font-weight:800;
    text-shadow:0 2px 10px rgba(0,0,0,.3);
}

/* ===================== STATS ===================== */

.stats{
    background:var(--azul);
    color:white;
}

.stats-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
}

.stat{
    padding:35px;
    text-align:center;
    border-right:1px solid rgba(255,255,255,.15);
}

.stat:last-child{
    border-right:0;
}

.stat strong{
    display:block;
    color:var(--dorado);
    font-family:Georgia,serif;
    font-size:clamp(3rem,6vw,5.5rem);
    line-height:1;
}

.stat span{
    display:block;
    margin-top:12px;
    color:#D9E3EA;
}

/* ===================== TESTIMONIOS ===================== */

.testimonials-grid{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:22px;
}

.testimonial{
    padding:30px;
    border:1px dashed #B9C4CB;
    border-radius:var(--radio);
    background:#FAFBFB;
}

.testimonial-mark{
    color:var(--dorado);
    font-family:Georgia,serif;
    font-size:4rem;
    line-height:.7;
}

.testimonial h3{
    margin-top:20px;
}

.testimonial p{
    color:var(--texto-suave);
}

.placeholder-badge{
    display:inline-block;
    padding:5px 10px;
    border-radius:30px;
    background:var(--crema);
    color:var(--cafe);
    font-size:.7rem;
    font-weight:800;
}

/* ===================== FAQ ===================== */

.faq{
    background:#F5F7F8;
}

.faq-layout{
    display:grid;
    grid-template-columns:.75fr 1.25fr;
    gap:70px;
}

.faq-item{
    border-bottom:1px solid #D9E1E6;
}

.faq-question{
    width:100%;
    min-height:70px;
    display:flex;
    justify-content:space-between;
    align-items:center;
    gap:20px;
    padding:18px 0;
    border:0;
    background:transparent;
    color:var(--azul);
    text-align:left;
    font-weight:800;
}

.faq-icon{
    flex:none;
    width:32px;
    height:32px;
    display:grid;
    place-items:center;
    border:1px solid #CBD5DC;
    border-radius:50%;
    transition:.25s;
}

.faq-question[aria-expanded="true"] .faq-icon{
    transform:rotate(45deg);
    background:var(--azul);
    color:white;
}

.faq-answer{
    max-height:0;
    overflow:hidden;
    transition:max-height .35s ease;
}

.faq-answer p{
    padding:0 45px 22px 0;
    color:var(--texto-suave);
}

/* ===================== CONTACTO ===================== */

.contact{
    background:var(--crema);
}

.contact-layout{
    display:grid;
    grid-template-columns:.75fr 1.25fr;
    gap:70px;
}

.contact-info p{
    color:var(--texto-suave);
}

.contact-points{
    margin-top:30px;
    padding:0;
    list-style:none;
}

.contact-points li{
    display:flex;
    gap:12px;
    padding:12px 0;
    border-bottom:1px solid #DDD3C2;
}

.contact-points li::before{
    content:"✓";
    color:var(--terracota);
    font-weight:900;
}

.form-panel{
    padding:35px;
    border-radius:var(--radio);
    background:white;
    box-shadow:var(--sombra);
}

.form-grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:18px;
}

.field{
    display:flex;
    flex-direction:column;
    gap:7px;
}

.full{
    grid-column:1/-1;
}

label{
    color:var(--azul);
    font-size:.83rem;
    font-weight:800;
}

input,
select,
textarea{
    width:100%;
    min-height:49px;
    padding:12px 13px;
    border:1px solid #C9D2D8;
    border-radius:9px;
    background:white;
    color:var(--texto);
}

textarea{
    min-height:120px;
    resize:vertical;
}

input:focus,
select:focus,
textarea:focus{
    border-color:var(--azul-medio);
}

.form-note{
    margin:15px 0;
    color:var(--texto-suave);
    font-size:.78rem;
}

.summary-box{
    margin-top:25px;
    padding-top:25px;
    border-top:1px solid var(--linea);
}

.summary-box textarea{
    min-height:280px;
    background:#F8FAFB;
}

.status{
    margin-top:12px;
    color:var(--azul-medio);
    font-weight:700;
    font-size:.86rem;
}

/* ===================== FOOTER ===================== */

.footer{
    padding:70px 0 25px;
    background:#091D2D;
    color:#C9D6DF;
}

.footer-grid{
    display:grid;
    grid-template-columns:1.4fr .7fr .7fr .8fr;
    gap:50px;
}

.footer .logo{
    width:max-content;
    color:white;
}

.footer-tagline{
    margin-top:25px;
    color:#9FB0BC;
    font-family:Georgia,serif;
    font-size:1.5rem;
}

.footer h3{
    color:white;
    font-size:.9rem;
    text-transform:uppercase;
    letter-spacing:.1em;
}

.footer-links{
    display:flex;
    flex-direction:column;
    gap:9px;
}

.footer-links a,
.footer-links button{
    width:max-content;
    padding:0;
    border:0;
    background:none;
    color:#B6C5CF;
    text-decoration:none;
    text-align:left;
}

.footer-links a:hover,
.footer-links button:hover{
    color:var(--dorado);
}

.footer-bottom{
    display:flex;
    justify-content:space-between;
    gap:20px;
    margin-top:55px;
    padding-top:20px;
    border-top:1px solid rgba(255,255,255,.12);
    font-size:.76rem;
}

/* ===================== WHATSAPP + TOP ===================== */

.floating-actions{
    position:fixed;
    z-index:90;
    right:22px;
    bottom:22px;
    display:flex;
    flex-direction:column;
    gap:10px;
}

.float-btn{
    width:54px;
    height:54px;
    display:grid;
    place-items:center;
    border:0;
    border-radius:50%;
    box-shadow:0 10px 30px rgba(0,0,0,.22);
    transition:.2s;
}

.float-btn:hover{
    transform:translateY(-3px);
}

.whatsapp{
    background:#25D366;
    color:#08351A;
    font-size:1.35rem;
}

.to-top{
    background:var(--azul);
    color:white;
    opacity:0;
    pointer-events:none;
}

.to-top.visible{
    opacity:1;
    pointer-events:auto;
}

/* ===================== MODAL ===================== */

.modal{
    position:fixed;
    z-index:300;
    inset:0;
    display:none;
    place-items:center;
    padding:20px;
    background:rgba(4,17,27,.75);
}

.modal.open{
    display:grid;
}

.modal-card{
    position:relative;
    width:min(560px,100%);
    max-height:90vh;
    overflow:auto;
    padding:35px;
    border-radius:var(--radio);
    background:white;
    box-shadow:0 30px 100px rgba(0,0,0,.35);
}

.modal-close{
    position:absolute;
    top:15px;
    right:15px;
    width:42px;
    height:42px;
    border:0;
    border-radius:50%;
    background:#EEF2F4;
    font-size:1.2rem;
}

.modal-card h2{
    margin-top:15px;
    font-size:2.4rem;
}

.modal-card p{
    color:var(--texto-suave);
}

/* ===================== ANIMACIONES ===================== */

.reveal{
    opacity:0;
    transform:translateY(25px);
    transition:opacity .7s ease,transform .7s ease;
}

.reveal.visible{
    opacity:1;
    transform:none;
}

/* ===================== RESPONSIVE ===================== */

@media(max-width:1000px){

    .nav-links{
        gap:15px;
    }

    .destinations-grid,
    .experience-grid{
        grid-template-columns:repeat(2,1fr);
    }

    .why-grid{
        grid-template-columns:repeat(2,1fr);
    }

    .featured-layout,
    .intro-grid,
    .faq-layout,
    .contact-layout{
        gap:45px;
    }

    .footer-grid{
        grid-template-columns:1fr 1fr;
    }
}

@media(max-width:780px){

    .section{
        padding:75px 0;
    }

    .menu-btn{
        display:grid;
        place-items:center;
    }

    .nav{
        min-height:72px;
    }

    .nav-links{
        position:fixed;
        top:72px;
        left:0;
        right:0;
        bottom:0;
        display:none;
        flex-direction:column;
        align-items:stretch;
        padding:25px;
        background:var(--azul);
    }

    .nav-links.open{
        display:flex;
    }

    .nav-links>a{
        padding:13px;
    }

    .nav-links .btn{
        margin-top:10px;
    }

    .hero{
        min-height:calc(100vh - 72px);
    }

    .hero-content{
        padding:80px 0 65px;
    }

    .scroll-hint{
        display:none;
    }

    .intro-grid,
    .featured-layout,
    .faq-layout,
    .contact-layout{
        grid-template-columns:1fr;
    }

    .intro-number{
        font-size:4rem;
    }

    .gallery{
        grid-template-columns:1fr 1fr;
        grid-template-rows:300px 200px 200px;
    }

    .gallery-item:first-child{
        grid-column:1/3;
        grid-row:auto;
    }

    .stats-grid{
        grid-template-columns:1fr 1fr 1fr;
    }

    .stat{
        padding:20px 10px;
    }

    .testimonials-grid{
        grid-template-columns:1fr;
    }
}

@media(max-width:600px){

    .container{
        width:calc(100% - 28px);
    }

    h1{
        font-size:clamp(3rem,15vw,5rem);
    }

    .destinations-grid,
    .experience-grid,
    .why-grid{
        grid-template-columns:1fr;
    }

    .destination{
        min-height:330px;
    }

    .form-grid{
        grid-template-columns:1fr;
    }

    .full{
        grid-column:auto;
    }

    .form-panel{
        padding:22px;
    }

    .gallery{
        grid-template-columns:1fr;
        grid-template-rows:none;
    }

    .gallery-item,
    .gallery-item:first-child{
        grid-column:auto;
        min-height:230px;
    }

    .stats-grid{
        grid-template-columns:1fr;
    }

    .stat{
        border-right:0;
        border-bottom:1px solid rgba(255,255,255,.15);
    }

    .actions .btn{
        width:100%;
    }

    .footer-grid{
        grid-template-columns:1fr;
    }

    .footer-bottom{
        flex-direction:column;
    }
}

@media(prefers-reduced-motion:reduce){

    html{
        scroll-behavior:auto;
    }

    *,
    *::before,
    *::after{
        animation:none!important;
        transition:none!important;
    }

    .reveal{
        opacity:1;
        transform:none;
    }
}

</style>
</head>

<body id="inicio">

<a href="#contenido" class="skip-link">Saltar al contenido</a>

<!-- =========================================================
     1. NOMBRE DE EMPRESA:
     Cambia "ANTIOQUIA ESENCIA" en logo, títulos y footer.
     ========================================================= -->

<header class="header">
<div class="container nav">

<a href="#inicio" class="logo" aria-label="Antioquia Esencia, inicio">
    <span class="logo-mark" aria-hidden="true"></span>
    <span class="logo-text">
        <strong>ANTIOQUIA</strong>
        <small>ESENCIA</small>
    </span>
</a>

<button
    class="menu-btn"
    id="menuBtn"
    type="button"
    aria-label="Abrir menú"
    aria-expanded="false"
    aria-controls="mainNav">
    ☰
</button>

<nav class="nav-links" id="mainNav" aria-label="Navegación principal">
    <a href="#inicio">Inicio</a>
    <a href="#experiencias">Experiencias</a>
    <a href="#destinos">Destinos</a>
    <a href="#nosotros">Nosotros</a>
    <a href="#preguntas">Preguntas</a>
    <a href="#contacto">Contacto</a>
    <a href="#contacto" class="btn">PLANEAR MI VIAJE</a>
</nav>

</div>
</header>

<main id="contenido">

<!-- ===================== HERO ===================== -->

<section class="hero" aria-labelledby="heroTitle">

<div class="container">
<div class="hero-content reveal">

<span class="eyebrow">Descubre otra forma de viajar</span>

<h1 id="heroTitle">
Antioquia no se visita.<br>
<em>Se vive.</em>
</h1>

<p class="hero-subtitle">
Montañas, pueblos, sabores y experiencias que convierten
un viaje en una historia para recordar.
</p>

<div class="actions">
<a href="#experiencias" class="btn btn-gold">
EXPLORAR EXPERIENCIAS
</a>

<a href="#contacto" class="btn btn-outline">
PLANEAR MI VIAJE
</a>
</div>

<div class="hero-tags" aria-label="Tipos de experiencias">
<span class="hero-tag">△ NATURALEZA</span>
<span class="hero-tag">◉ CULTURA</span>
<span class="hero-tag">◇ GASTRONOMÍA</span>
<span class="hero-tag">↗ AVENTURA</span>
</div>

</div>
</div>

<div class="scroll-hint" aria-hidden="true">
DESCUBRE ANTIOQUIA ↓
</div>

</section>

<!-- ===================== INTRO ===================== -->

<section class="section intro" id="nosotros">
<div class="container intro-grid reveal">

<div>
<span class="eyebrow">Nuestra esencia</span>
<div class="intro-number">∞</div>
</div>

<div class="intro-copy">
<h2>Viajar es descubrir lo que un mapa no puede mostrarte.</h2>

<p>
Antioquia Esencia es una marca demostrativa de turismo experiencial
pensada para conectar al viajero con paisajes, sabores, historias,
tradiciones y personas.
</p>

<p>
Aquí no comienzas eligiendo simplemente un destino.
Comienzas preguntándote <strong>qué quieres sentir, descubrir
y recordar de tu viaje.</strong>
</p>

<a href="#destinos" class="btn btn-blue">VER DESTINOS</a>
</div>

</div>
</section>

<!-- ===================== DESTINOS ===================== -->

<section class="section" id="destinos">

<div class="container">

<div class="section-head reveal">
<span class="eyebrow">Destinos destacados</span>
<h2>Seis maneras de descubrir Antioquia.</h2>
<p>
Pueblos, montañas y ciudades que pueden convertirse en el punto
de partida de una experiencia diferente.
</p>
</div>

<!-- 4. DESTINOS: Duplica o modifica estas tarjetas -->

<div class="destinations-grid">

<article class="destination reveal">
<div class="destination-visual"></div>
<div class="destination-content">
<span class="destination-type">Naturaleza · Paisaje</span>
<h3>Guatapé</h3>
<p>Colores, embalse y montañas para mirar Antioquia desde otra perspectiva.</p>
<button class="discover destination-btn"
data-destination="Guatapé"
data-description="Paisajes, embalse, cultura local y experiencias alrededor de uno de los destinos más reconocibles de Antioquia.">
Descubrir <span>→</span>
</button>
</div>
</article>

<article class="destination reveal">
<div class="destination-visual"></div>
<div class="destination-content">
<span class="destination-type">Naturaleza · Pueblo</span>
<h3>Jardín</h3>
<p>Café, balcones y montañas donde el ritmo del viaje cambia.</p>
<button class="discover destination-btn"
data-destination="Jardín"
data-description="Una propuesta para explorar paisaje, tradición cafetera y arquitectura en un entorno de montaña.">
Descubrir <span>→</span>
</button>
</div>
</article>

<article class="destination reveal">
<div class="destination-visual"></div>
<div class="destination-content">
<span class="destination-type">Patrimonio · Café</span>
<h3>Jericó</h3>
<p>Calles con historia, tradición y una identidad que invita a caminar sin prisa.</p>
<button class="discover destination-btn"
data-destination="Jericó"
data-description="Una experiencia conceptual alrededor de patrimonio, cultura, montaña y tradición antioqueña.">
Descubrir <span>→</span>
</button>
</div>
</article>

<article class="destination reveal">
<div class="destination-visual"></div>
<div class="destination-content">
<span class="destination-type">Historia · Arquitectura</span>
<h3>Santa Fe de Antioquia</h3>
<p>Arquitectura, clima cálido e historias que conectan con otro tiempo.</p>
<button class="discover destination-btn"
data-destination="Santa Fe de Antioquia"
data-description="Patrimonio arquitectónico, recorridos históricos y experiencias en uno de los destinos tradicionales del departamento.">
Descubrir <span>→</span>
</button>
</div>
</article>

<article class="destination reveal">
<div class="destination-visual"></div>
<div class="destination-content">
<span class="destination-type">Ciudad · Cultura</span>
<h3>Medellín</h3>
<p>Una ciudad para descubrir innovación, transformación, gastronomía y cultura.</p>
<button class="discover destination-btn"
data-destination="Medellín"
data-description="Una mirada urbana y cultural para descubrir diferentes facetas de Medellín más allá de los recorridos convencionales.">
Descubrir <span>→</span>
</button>
</div>
</article>

<article class="destination reveal">
<div class="destination-visual"></div>
<div class="destination-content">
<span class="destination-type">Naturaleza · Tradición</span>
<h3>Santa Elena</h3>
<p>Flores, montaña y tradición a pocos kilómetros de la ciudad.</p>
<button class="discover destination-btn"
data-destination="Santa Elena"
data-description="Naturaleza de montaña y aproximación a tradiciones rurales y culturales del territorio.">
Descubrir <span>→</span>
</button>
</div>
</article>

</div>
</div>
</section>

<!-- ===================== EXPERIENCIAS ===================== -->

<section class="section experiences" id="experiencias">

<div class="container">

<div class="section-head reveal">
<span class="eyebrow">Elige cómo quieres sentir Antioquia</span>
<h2>No todos viajamos buscando lo mismo.</h2>
<p>
Filtra las experiencias y encuentra una idea que se acerque
a la forma en que quieres viajar.
</p>
</div>

<div class="filters reveal" role="group" aria-label="Filtrar experiencias">

<button class="filter" data-filter="all" aria-pressed="true">
Todas
</button>

<button class="filter" data-filter="naturaleza" aria-pressed="false">
Naturaleza
</button>

<button class="filter" data-filter="cultura" aria-pressed="false">
Cultura
</button>

<button class="filter" data-filter="gastronomia" aria-pressed="false">
Gastronomía
</button>

<button class="filter" data-filter="parejas" aria-pressed="false">
Parejas
</button>

</div>

<p id="filterStatus" role="status" class="form-note">
6 experiencias disponibles.
</p>

<!-- 5. EXPERIENCIAS: Edita, elimina o duplica tarjetas -->

<div class="experience-grid">

<article class="experience-card reveal"
data-category="gastronomia naturaleza">

<div class="experience-image"
role="img"
aria-label="Espacio visual para fotografía de una experiencia cafetera"></div>

<div class="experience-body">

<span class="category">Café · Gastronomía</span>

<h3>Ruta del café</h3>

<p>
Del grano a la taza: una aproximación al paisaje y a la cultura
que rodea al café antioqueño.
</p>

<div class="meta">
<span>◷ Día completo</span>
<span>♧ Rural</span>
</div>

<ul class="includes">
<li>Recorrido conceptual por entorno cafetero</li>
<li>Experiencia gastronómica propuesta</li>
<li>Espacios para interpretación cultural</li>
</ul>

<button class="btn btn-blue select-experience"
data-experience="Ruta del café">
Explorar experiencia
</button>

</div>
</article>

<article class="experience-card recommended reveal"
data-category="naturaleza cultura">

<span class="recommended-label">
EXPERIENCIA DESTACADA
</span>

<div class="experience-image"
role="img"
aria-label="Espacio visual para fotografía de Guatapé"></div>

<div class="experience-body">

<span class="category">Paisaje · Cultura</span>

<h3>Guatapé y Piedra del Peñol</h3>

<p>
Un día entre colores, agua y algunas de las panorámicas más reconocibles
del oriente antioqueño.
</p>

<div class="meta">
<span>◷ Día completo</span>
<span>△ Paisaje</span>
</div>

<ul class="includes">
<li>Recorrido conceptual por Guatapé</li>
<li>Tiempo para explorar el entorno</li>
<li>Propuesta gastronómica local</li>
</ul>

<button class="btn select-experience"
data-experience="Guatapé y Piedra del Peñol">
Explorar experiencia
</button>

</div>
</article>

<article class="experience-card reveal"
data-category="cultura">

<div class="experience-image"
role="img"
aria-label="Espacio visual para fotografía de pueblos patrimoniales"></div>

<div class="experience-body">

<span class="category">Historia · Cultura</span>

<h3>Pueblos patrimoniales</h3>

<p>
Calles, balcones y relatos que permiten mirar Antioquia
desde su memoria y sus tradiciones.
</p>

<div class="meta">
<span>◷ 1–2 días</span>
<span>⌂ Patrimonio</span>
</div>

<ul class="includes">
<li>Selección conceptual de pueblos</li>
<li>Recorridos culturales</li>
<li>Tiempo de exploración personal</li>
</ul>

<button class="btn btn-blue select-experience"
data-experience="Pueblos patrimoniales">
Explorar experiencia
</button>

</div>
</article>

<article class="experience-card reveal"
data-category="cultura gastronomia">

<div class="experience-image"
role="img"
aria-label="Espacio visual para fotografía urbana de Medellín"></div>

<div class="experience-body">

<span class="category">Ciudad · Cultura</span>

<h3>Medellín urbana y cultural</h3>

<p>
Una mirada a los contrastes, historias, espacios urbanos
y sabores de Medellín.
</p>

<div class="meta">
<span>◷ 6–8 horas</span>
<span>◎ Urbano</span>
</div>

<ul class="includes">
<li>Recorrido urbano conceptual</li>
<li>Paradas culturales</li>
<li>Selección gastronómica propuesta</li>
</ul>

<button class="btn btn-blue select-experience"
data-experience="Medellín urbana y cultural">
Explorar experiencia
</button>

</div>
</article>

<article class="experience-card reveal"
data-category="naturaleza">

<div class="experience-image"
role="img"
aria-label="Espacio visual para fotografía de naturaleza y aventura"></div>

<div class="experience-body">

<span class="category">Naturaleza · Aventura</span>

<h3>Naturaleza y aventura</h3>

<p>
Salir del ruido para reencontrarse con montaña, caminos
y escenarios naturales.
</p>

<div class="meta">
<span>◷ Flexible</span>
<span>△ Exterior</span>
</div>

<ul class="includes">
<li>Actividad ajustable al perfil del viajero</li>
<li>Entornos naturales</li>
<li>Planeación según condiciones aplicables</li>
</ul>

<button class="btn btn-blue select-experience"
data-experience="Naturaleza y aventura">
Explorar experiencia
</button>

</div>
</article>

<article class="experience-card reveal"
data-category="parejas gastronomia">

<div class="experience-image"
role="img"
aria-label="Espacio visual para una escapada romántica"></div>

<div class="experience-body">

<span class="category">Parejas · Experiencia</span>

<h3>Escapada romántica</h3>

<p>
Una propuesta para cambiar la rutina por paisajes,
sabores y tiempo compartido.
</p>

<div class="meta">
<span>◷ 2 días</span>
<span>♡ Parejas</span>
</div>

<ul class="includes">
<li>Itinerario conceptual personalizable</li>
<li>Momentos gastronómicos</li>
<li>Selección de experiencias según preferencias</li>
</ul>

<button class="btn btn-blue select-experience"
data-experience="Escapada romántica">
Explorar experiencia
</button>

</div>
</article>

</div>
</div>
</section>

<!-- ===================== PLAN DESTACADO ===================== -->

<section class="section featured">

<div class="container featured-layout">

<div class="reveal">

<span class="eyebrow">Itinerario inspiración</span>

<h2>
48 horas para enamorarte de Antioquia.
</h2>

<p>
Una propuesta demostrativa para visualizar cómo distintas experiencias
pueden convertirse en una sola historia.
</p>

<div class="demo-note">
Este itinerario es ilustrativo. No representa disponibilidad,
precio ni reserva confirmada.
</div>

</div>

<div class="timeline reveal">

<div class="day">
<small>DÍA 01</small>
<h3>Medellín → Guatapé → sabores</h3>
<p>
Comenzar entre ciudad y montaña, explorar Guatapé y terminar
el día alrededor de una experiencia gastronómica.
</p>
</div>

<div class="day">
<small>DÍA 02</small>
<h3>Naturaleza → café → atardecer</h3>
<p>
Cambiar el ritmo, acercarse al paisaje cafetero y cerrar
el viaje contemplando Antioquia al final de la tarde.
</p>
</div>

<a href="#contacto"
class="btn btn-gold select-plan"
data-experience="48 horas para enamorarte de Antioquia">
QUIERO CONOCER ESTE PLAN
</a>

</div>
</div>
</section>

<!-- ===================== POR QUÉ ===================== -->

<section class="section">

<div class="container">

<div class="section-head reveal">
<span class="eyebrow">Viajar con intención</span>
<h2>Menos incertidumbre. Más viaje.</h2>
<p>
Una experiencia bien diseñada comienza mucho antes de llegar al destino.
</p>
</div>

<div class="why-grid">

<div class="why-item reveal">
<div class="why-number">01</div>
<h3>Experiencias seleccionadas</h3>
<p>Propuestas organizadas alrededor de diferentes formas de descubrir el territorio.</p>
</div>

<div class="why-item reveal">
<div class="why-number">02</div>
<h3>Acompañamiento</h3>
<p>Un punto de contacto para conversar sobre preferencias y necesidades del viaje.</p>
</div>

<div class="why-item reveal">
<div class="why-number">03</div>
<h3>Conocimiento local</h3>
<p>El territorio como punto de partida para diseñar experiencias con contexto.</p>
</div>

<div class="why-item reveal">
<div class="why-number">04</div>
<h3>Viajes personalizados</h3>
<p>La propuesta puede adaptarse al tipo de viajero, grupo e intereses.</p>
</div>

</div>
</div>
</section>

<!-- ===================== FRASE EMOCIONAL ===================== -->

<section class="emotional">

<div class="container reveal">

<blockquote>
“Quizás dentro de unos años no recuerdes todos los lugares que visitaste.
Pero sí recordarás <em>cómo te hicieron sentir.</em>”
</blockquote>

</div>
</section>

<!-- ===================== GALERÍA ===================== -->

<section class="section">

<div class="container">

<div class="section-head reveal">
<span class="eyebrow">Imagina el viaje</span>
<h2>Antioquia cambia con cada mirada.</h2>
<p>
Estos bloques están preparados para reemplazarse por fotografías propias
o imágenes con licencia adecuada.
</p>
</div>

<!-- 6. FOTOGRAFÍAS:
     Sustituye estos fondos por imágenes reales/licenciadas. -->

<div class="gallery reveal">

<div class="gallery-item" role="img" aria-label="Placeholder para fotografía de montañas">
<span class="gallery-label">Montañas</span>
</div>

<div class="gallery-item" role="img" aria-label="Placeholder para fotografía de café">
<span class="gallery-label">Café</span>
</div>

<div class="gallery-item" role="img" aria-label="Placeholder para fotografía de Guatapé">
<span class="gallery-label">Guatapé</span>
</div>

<div class="gallery-item" role="img" aria-label="Placeholder para fotografía de pueblos">
<span class="gallery-label">Pueblos</span>
</div>

<div class="gallery-item" role="img" aria-label="Placeholder para fotografía de gastronomía">
<span class="gallery-label">Sabores</span>
</div>

</div>
</div>
</section>

<!-- ===================== ESTADÍSTICAS REALES DEL CONTENIDO ===================== -->

<section class="section-small stats">

<div class="container">

<div class="stats-grid">

<div class="stat">
<strong class="counter" data-target="6">0</strong>
<span>Destinos presentados</span>
</div>

<div class="stat">
<strong class="counter" data-target="6">0</strong>
<span>Experiencias propuestas</span>
</div>

<div class="stat">
<strong class="counter" data-target="4">0</strong>
<span>Tipos de viaje destacados</span>
</div>

</div>

</div>
</section>

<!-- ===================== TESTIMONIOS ===================== -->

<section class="section">

<div class="container">

<div class="section-head reveal">
<span class="eyebrow">Historias que algún día podrán contarse</span>
<h2>La confianza no se inventa.</h2>
<p>
Por tratarse de una empresa ficticia, estos componentes se reservan
para futuras opiniones auténticas y verificables.
</p>
</div>

<div class="testimonials-grid">

<article class="testimonial reveal">
<div class="testimonial-mark">“</div>
<span class="placeholder-badge">DEMOSTRACIÓN</span>
<h3>Espacio para testimonio verificado</h3>
<p>Aquí podría mostrarse una opinión real únicamente después de contar con autorización y evidencia.</p>
</article>

<article class="testimonial reveal">
<div class="testimonial-mark">“</div>
<span class="placeholder-badge">DEMOSTRACIÓN</span>
<h3>Espacio para testimonio verificado</h3>
<p>El diseño está preparado para incorporar nombre, experiencia y valoración auténtica.</p>
</article>

<article class="testimonial reveal">
<div class="testimonial-mark">“</div>
<span class="placeholder-badge">DEMOSTRACIÓN</span>
<h3>Espacio para testimonio verificado</h3>
<p>No se utilizan viajeros ficticios para simular confianza o prueba social.</p>
</article>

</div>
</div>
</section>

<!-- ===================== FAQ ===================== -->

<section class="section faq" id="preguntas">

<div class="container faq-layout">

<div class="reveal">

<span class="eyebrow">Preguntas frecuentes</span>

<h2>
Viajar con menos preguntas también se disfruta más.
</h2>

<p>
Estas respuestas son orientativas para el sitio demostrativo.
Las condiciones concretas dependerían de cada experiencia.
</p>

<a href="#contacto" class="btn btn-blue">
HABLAR CON UN ASESOR
</a>

</div>

<div class="faq-list reveal">

<div class="faq-item">
<button class="faq-question" aria-expanded="false">
¿Puedo personalizar mi viaje?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>Sí. El concepto del sitio contempla recopilar intereses, destinos y tipo de viaje para preparar una propuesta ajustada al viajero.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" aria-expanded="false">
¿Qué incluyen las experiencias?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>Cada experiencia muestra una orientación general de sus componentes. Una propuesta comercial real debería especificar claramente inclusiones, exclusiones y condiciones antes de reservar.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" aria-expanded="false">
¿Realizan viajes para grupos?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>El sitio permite solicitar propuestas para varios viajeros. La capacidad y condiciones concretas tendrían que confirmarse antes de cualquier reserva.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" aria-expanded="false">
¿Puedo viajar con niños?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>La selección debería considerar edad, actividad y características del destino. La idoneidad de cada experiencia tendría que verificarse específicamente.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" aria-expanded="false">
¿Cómo solicito disponibilidad?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>Completa el formulario para generar el resumen de tu viaje. Esta demostración no consulta disponibilidad real ni realiza reservas.</p>
</div>
</div>

<div class="faq-item">
<button class="faq-question" aria-expanded="false">
¿Las experiencias incluyen transporte?
<span class="faq-icon">+</span>
</button>
<div class="faq-answer">
<p>Dependería del plan contratado. En una versión comercial, cada experiencia debe especificar claramente si el transporte está incluido.</p>
</div>
</div>

</div>
</div>
</section>

<!-- ===================== CONTACTO ===================== -->

<section class="section contact" id="contacto">

<div class="container contact-layout">

<div class="contact-info reveal">

<span class="eyebrow">Comienza tu historia</span>

<h2>¿Qué Antioquia quieres vivir?</h2>

<p>
Cuéntanos cómo imaginas tu viaje. La página preparará un resumen
que podrás copiar o llevar a WhatsApp.
</p>

<ul class="contact-points">
<li>Selecciona tu destino.</li>
<li>Cuéntanos con quién viajas.</li>
<li>Indica aproximadamente cuándo.</li>
<li>Genera tu solicitud.</li>
</ul>

<p class="form-note">
Sitio demostrativo. Este formulario no envía ni almacena información
en un servidor.
</p>

</div>

<div class="form-panel reveal">

<form id="travelForm">

<div class="form-grid">

<div class="field">
<label for="name">Nombre *</label>
<input
id="name"
name="name"
autocomplete="name"
required
maxlength="100"
placeholder="Tu nombre">
</div>

<div class="field">
<label for="email">Correo *</label>
<input
id="email"
name="email"
type="email"
autocomplete="email"
required
maxlength="150"
placeholder="nombre@correo.com">
</div>

<div class="field">
<label for="phone">Teléfono</label>
<input
id="phone"
name="phone"
type="tel"
autocomplete="tel"
maxlength="30"
placeholder="+57 ...">
</div>

<div class="field">
<label for="travelers">Número de viajeros *</label>
<input
id="travelers"
name="travelers"
type="number"
min="1"
max="99"
value="2"
required>
</div>

<div class="field">
<label for="destination">Destino de interés *</label>
<select id="destination" name="destination" required>
<option value="">Selecciona</option>
<option>Guatapé</option>
<option>Jardín</option>
<option>Jericó</option>
<option>Santa Fe de Antioquia</option>
<option>Medellín</option>
<option>Santa Elena</option>
<option>Quiero orientación</option>
</select>
</div>

<div class="field">
<label for="date">Fecha aproximada</label>
<input id="date" name="date" type="date">
</div>

<div class="field full">
<label for="experience">Tipo de experiencia *</label>
<select id="experience" name="experience" required>
<option value="">Selecciona</option>
<option>Ruta del café</option>
<option>Guatapé y Piedra del Peñol</option>
<option>Pueblos patrimoniales</option>
<option>Medellín urbana y cultural</option>
<option>Naturaleza y aventura</option>
<option>Escapada romántica</option>
<option>48 horas para enamorarte de Antioquia</option>
<option>Quiero una propuesta personalizada</option>
</select>
</div>

<div class="field full">
<label for="message">Cuéntanos cómo imaginas el viaje</label>
<textarea
id="message"
name="message"
maxlength="1000"
placeholder="Por ejemplo: viajamos en pareja, nos gusta la naturaleza y queremos conocer algo relacionado con café..."></textarea>
</div>

</div>

<button type="submit" class="btn">
QUIERO PLANEAR MI VIAJE
</button>

<p class="form-note">
Preparar la solicitud no significa que haya sido enviada ni reservada.
</p>

</form>

<div id="summaryBox" class="summary-box" hidden>

<label for="travelSummary">
Tu solicitud está lista para revisar:
</label>

<textarea id="travelSummary" readonly></textarea>

<div class="actions">

<button type="button" id="copyBtn" class="btn btn-blue">
COPIAR SOLICITUD
</button>

<button type="button" id="summaryWhatsapp" class="btn">
ABRIR EN WHATSAPP
</button>

</div>

<p id="formStatus" class="status" role="status" aria-live="polite"></p>

</div>

</div>
</div>
</section>

</main>

<!-- ===================== FOOTER ===================== -->

<footer class="footer">

<div class="container">

<div class="footer-grid">

<div>

<a href="#inicio" class="logo" aria-label="Antioquia Esencia">
<span class="logo-mark" aria-hidden="true"></span>
<span class="logo-text">
<strong>ANTIOQUIA</strong>
<small>ESENCIA</small>
</span>
</a>

<div class="footer-tagline">
Explora.<br>
Descubre.<br>
Recuerda.
</div>

</div>

<div>
<h3>Navegación</h3>
<div class="footer-links">
<a href="#inicio">Inicio</a>
<a href="#destinos">Destinos</a>
<a href="#experiencias">Experiencias</a>
<a href="#preguntas">Preguntas</a>
</div>
</div>

<div>
<h3>Contacto</h3>
<div class="footer-links">
<a href="#contacto">Planear viaje</a>
<button type="button" class="open-whatsapp">
WhatsApp
</button>
</div>
</div>

<div>
<h3>Redes</h3>
<div class="footer-links">
<button type="button" class="social-placeholder">Instagram</button>
<button type="button" class="social-placeholder">Facebook</button>
<button type="button" class="social-placeholder">YouTube</button>
</div>
</div>

</div>

<div class="footer-bottom">

<span>
© <span id="year"></span> Antioquia Esencia
</span>

<span>
Proyecto académico demostrativo · Marca ficticia · Sin reservas reales
</span>

</div>

</div>
</footer>

<!-- ===================== BOTONES FLOTANTES ===================== -->

<div class="floating-actions">

<button
type="button"
class="float-btn whatsapp open-whatsapp"
aria-label="Preparar conversación por WhatsApp"
title="WhatsApp">
✆
</button>

<button
type="button"
class="float-btn to-top"
id="toTop"
aria-label="Volver arriba"
title="Volver arriba">
↑
</button>

</div>

<!-- ===================== MODAL DESTINOS ===================== -->

<div
class="modal"
id="destinationModal"
role="dialog"
aria-modal="true"
aria-labelledby="modalTitle">

<div class="modal-card">

<button
class="modal-close"
id="modalClose"
type="button"
aria-label="Cerrar">
×
</button>

<span class="eyebrow">Descubre el destino</span>

<h2 id="modalTitle"></h2>

<p id="modalDescription"></p>

<div class="actions">

<button
type="button"
class="btn modal-plan">
QUIERO EXPLORARLO
</button>

<button
type="button"
class="btn btn-blue"
id="modalCloseSecondary">
SEGUIR EXPLORANDO
</button>

</div>

</div>
</div>

<script>
"use strict";

/* ==========================================================
   CONFIGURACIÓN PARA ESTUDIANTES

   7. WHATSAPP
   Sustituye el siguiente número por el número comercial real.
   Formato internacional SIN +, espacios ni guiones.
   Este número es deliberadamente ficticio/no operativo.

   8. DATOS DE CONTACTO
   En una implementación real pueden añadirse correo, dirección,
   horario y canales oficiales.
   ========================================================== */

const WHATSAPP_NUMBER = "573000000000";
const WHATSAPP_IS_DEMO = true;

/* ===================== AÑO ===================== */

document.getElementById("year").textContent =
    new Date().getFullYear();

/* ===================== MENÚ MÓVIL ===================== */

const menuBtn = document.getElementById("menuBtn");
const mainNav = document.getElementById("mainNav");

function setMenu(open){

    mainNav.classList.toggle("open",open);

    menuBtn.setAttribute(
        "aria-expanded",
        String(open)
    );

    menuBtn.setAttribute(
        "aria-label",
        open ? "Cerrar menú" : "Abrir menú"
    );

    menuBtn.textContent =
        open ? "×" : "☰";

    document.body.classList.toggle(
        "menu-open",
        open
    );
}

menuBtn.addEventListener("click",()=>{

    const open =
        menuBtn.getAttribute("aria-expanded") !== "true";

    setMenu(open);
});

mainNav.addEventListener("click",event=>{

    if(event.target.closest("a")){
        setMenu(false);
    }
});

document.addEventListener("keydown",event=>{

    if(event.key === "Escape"){
        setMenu(false);
        closeModal();
    }
});

/* ===================== FILTROS ===================== */

const filterButtons =
    document.querySelectorAll(".filter");

const experienceCards =
    document.querySelectorAll(".experience-card");

const filterStatus =
    document.getElementById("filterStatus");

filterButtons.forEach(button=>{

    button.addEventListener("click",()=>{

        const filter =
            button.dataset.filter;

        let visible = 0;

        filterButtons.forEach(item=>{
            item.setAttribute(
                "aria-pressed",
                String(item === button)
            );
        });

        experienceCards.forEach(card=>{

            const categories =
                card.dataset.category.split(" ");

            const show =
                filter === "all" ||
                categories.includes(filter);

            card.hidden = !show;

            if(show) visible++;
        });

        filterStatus.textContent =
            `${visible} ${
                visible === 1
                ? "experiencia disponible"
                : "experiencias disponibles"
            }.`;
    });
});

/* ===================== FAQ ===================== */

document.querySelectorAll(".faq-question")
.forEach(button=>{

    button.addEventListener("click",()=>{

        const expanded =
            button.getAttribute("aria-expanded") === "true";

        const answer =
            button.nextElementSibling;

        button.setAttribute(
            "aria-expanded",
            String(!expanded)
        );

        answer.style.maxHeight =
            expanded
            ? null
            : answer.scrollHeight + "px";
    });
});

/* ===================== EXPERIENCIAS → FORMULARIO ===================== */

const experienceSelect =
    document.getElementById("experience");

document.querySelectorAll(
    ".select-experience,.select-plan"
).forEach(button=>{

    button.addEventListener("click",()=>{

        experienceSelect.value =
            button.dataset.experience;

        document
            .getElementById("contacto")
            .scrollIntoView({
                behavior:"smooth"
            });

        setTimeout(()=>{
            experienceSelect.focus();
        },500);
    });
});

/* ===================== DESTINOS MODAL ===================== */

const modal =
    document.getElementById("destinationModal");

const modalTitle =
    document.getElementById("modalTitle");

const modalDescription =
    document.getElementById("modalDescription");

const modalClose =
    document.getElementById("modalClose");

const modalCloseSecondary =
    document.getElementById("modalCloseSecondary");

const modalPlan =
    document.querySelector(".modal-plan");

let selectedDestination = "";

function openModal(button){

    selectedDestination =
        button.dataset.destination;

    modalTitle.textContent =
        selectedDestination;

    modalDescription.textContent =
        button.dataset.description;

    modal.classList.add("open");

    modalClose.focus();
}

function closeModal(){

    modal.classList.remove("open");
}

document.querySelectorAll(".destination-btn")
.forEach(button=>{

    button.addEventListener("click",()=>{
        openModal(button);
    });
});

modalClose.addEventListener(
    "click",
    closeModal
);

modalCloseSecondary.addEventListener(
    "click",
    closeModal
);

modal.addEventListener("click",event=>{

    if(event.target === modal){
        closeModal();
    }
});

modalPlan.addEventListener("click",()=>{

    const destinationSelect =
        document.getElementById("destination");

    destinationSelect.value =
        selectedDestination;

    closeModal();

    document
        .getElementById("contacto")
        .scrollIntoView({
            behavior:"smooth"
        });

    setTimeout(()=>{
        destinationSelect.focus();
    },500);
});

/* ===================== FORMULARIO ===================== */

const travelForm =
    document.getElementById("travelForm");

const summaryBox =
    document.getElementById("summaryBox");

const travelSummary =
    document.getElementById("travelSummary");

const formStatus =
    document.getElementById("formStatus");

travelForm.addEventListener(
    "submit",
    event=>{

        event.preventDefault();

        if(!travelForm.reportValidity()){
            return;
        }

        const data =
            new FormData(travelForm);

        const name =
            String(data.get("name")).trim();

        const email =
            String(data.get("email")).trim();

        const phone =
            String(data.get("phone")).trim();

        const travelers =
            String(data.get("travelers"));

        const destination =
            String(data.get("destination"));

        const date =
            String(data.get("date")).trim();

        const experience =
            String(data.get("experience"));

        const message =
            String(data.get("message")).trim();

        const summary = [
            "SOLICITUD DE VIAJE — ANTIOQUIA ESENCIA",
            "",
            `Nombre: ${name}`,
            `Correo: ${email}`,
            `Teléfono: ${phone || "No indicado"}`,
            `Viajeros: ${travelers}`,
            `Destino: ${destination}`,
            `Fecha aproximada: ${date || "Por definir"}`,
            `Experiencia: ${experience}`,
            "",
            "Preferencias / mensaje:",
            message || "No se añadieron comentarios.",
            "",
            "Nota: esta solicitud fue generada desde un sitio demostrativo y no constituye una reserva."
        ].join("\n");

        travelSummary.value =
            summary;

        summaryBox.hidden =
            false;

        formStatus.textContent =
            "Solicitud preparada. Todavía no se ha enviado ni reservado nada.";

        summaryBox.scrollIntoView({
            behavior:"smooth",
            block:"nearest"
        });
    }
);

/* ===================== COPIAR ===================== */

const copyBtn =
    document.getElementById("copyBtn");

copyBtn.addEventListener(
    "click",
    async()=>{

        try{

            await navigator.clipboard.writeText(
                travelSummary.value
            );

            formStatus.textContent =
                "Solicitud copiada. Puedes compartirla por el canal que prefieras.";

        }catch(error){

            travelSummary.focus();
            travelSummary.select();

            formStatus.textContent =
                "La solicitud quedó seleccionada. Usa Ctrl+C o la opción Copiar de tu dispositivo.";
        }
    }
);

/* ===================== WHATSAPP ===================== */

function openWhatsApp(message){

    if(WHATSAPP_IS_DEMO){

        alert(
            "WhatsApp está configurado con un número demostrativo. " +
            "Para activarlo, cambia WHATSAPP_NUMBER y WHATSAPP_IS_DEMO en el JavaScript."
        );

        return;
    }

    const url =
        "https://wa.me/" +
        WHATSAPP_NUMBER +
        "?text=" +
        encodeURIComponent(message);

    window.open(
        url,
        "_blank",
        "noopener,noreferrer"
    );
}

document
.querySelectorAll(".open-whatsapp")
.forEach(button=>{

    button.addEventListener("click",()=>{

        openWhatsApp(
            "Hola, quiero conocer las experiencias de Antioquia Esencia."
        );
    });
});

document
.getElementById("summaryWhatsapp")
.addEventListener("click",()=>{

    openWhatsApp(
        travelSummary.value ||
        "Hola, quiero planear un viaje por Antioquia."
    );
});

/* ===================== REDES PLACEHOLDER ===================== */

document
.querySelectorAll(".social-placeholder")
.forEach(button=>{

    button.addEventListener("click",()=>{

        alert(
            "En una implementación real, este botón se enlazaría al perfil oficial de " +
            button.textContent.trim() +
            "."
        );
    });
});

/* ===================== ANIMACIONES SCROLL ===================== */

const prefersReducedMotion =
    window.matchMedia(
        "(prefers-reduced-motion: reduce)"
    ).matches;

const revealElements =
    document.querySelectorAll(".reveal");

if(prefersReducedMotion){

    revealElements.forEach(element=>{
        element.classList.add("visible");
    });

}else{

    const observer =
        new IntersectionObserver(
            entries=>{

                entries.forEach(entry=>{

                    if(entry.isIntersecting){

                        entry.target
                            .classList
                            .add("visible");

                        observer.unobserve(
                            entry.target
                        );
                    }
                });

            },
            {
                threshold:.12
            }
        );

    revealElements.forEach(element=>{
        observer.observe(element);
    });
}

/* ===================== CONTADORES ===================== */

const counters =
    document.querySelectorAll(".counter");

let countersStarted = false;

const statsObserver =
    new IntersectionObserver(
        entries=>{

            if(
                entries.some(
                    entry=>entry.isIntersecting
                ) &&
                !countersStarted
            ){

                countersStarted = true;

                counters.forEach(counter=>{

                    const target =
                        Number(counter.dataset.target);

                    if(prefersReducedMotion){

                        counter.textContent =
                            String(target).padStart(2,"0");

                        return;
                    }

                    let current = 0;

                    const interval =
                        setInterval(()=>{

                            current++;

                            counter.textContent =
                                String(current)
                                .padStart(2,"0");

                            if(current >= target){

                                clearInterval(
                                    interval
                                );
                            }

                        },120);
                });
            }
        },
        {
            threshold:.4
        }
    );

if(counters.length){

    statsObserver.observe(
        counters[0].closest(".stats")
    );
}

/* ===================== VOLVER ARRIBA ===================== */

const toTop =
    document.getElementById("toTop");

window.addEventListener(
    "scroll",
    ()=>{

        toTop.classList.toggle(
            "visible",
            window.scrollY > 600
        );

    },
    {
        passive:true
    }
);

toTop.addEventListener(
    "click",
    ()=>{

        window.scrollTo({
            top:0,
            behavior:
                prefersReducedMotion
                ? "auto"
                : "smooth"
        });
    }
);

/* ===================== EVITAR FECHAS PASADAS ===================== */

const dateInput =
    document.getElementById("date");

const today =
    new Date();

const localDate =
    new Date(
        today.getTime() -
        today.getTimezoneOffset()*60000
    )
    .toISOString()
    .split("T")[0];

dateInput.min =
    localDate;

</script>

</body>
</html>
