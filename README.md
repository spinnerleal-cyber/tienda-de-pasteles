<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#fff9f2">
  <meta name="description" content="Doce Pote: bolos de pote artesanais, super recheados e cheios de carinho. Monte seu carrinho e peça pelo WhatsApp.">
  <title>Doce Pote — Felicidade em camadas</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700;800&family=Fraunces:opsz,wght,SOFT,WONK@9..144,600,30,1;9..144,700,30,1;9..144,800,30,1&display=swap" rel="stylesheet">
  <style>
    :root{--paper:#fff9f2;--white:#fff;--ink:#38232b;--muted:#806b70;--berry:#b43d68;--berry-deep:#842b50;--blush:#fce6e9;--peach:#ffead6;--brown:#54333a;--line:#efdfd9;--green:#1e965f;--shadow:0 18px 52px rgba(82,37,49,.11);--display:'Fraunces',Georgia,serif;--body:'DM Sans',Arial,sans-serif}
    *,*::before,*::after{box-sizing:border-box}
    html{scroll-behavior:smooth;scroll-padding-top:100px}
    body{margin:0;background:var(--paper);font-family:var(--body);color:var(--ink);overflow-x:hidden}
    body.cart-open{overflow:hidden}
    button,input,select,textarea{font:inherit}
    button{cursor:pointer}
    a{color:inherit;text-decoration:none}
    button:focus-visible,a:focus-visible,input:focus-visible,select:focus-visible,textarea:focus-visible{outline:3px solid #f1a64d;outline-offset:3px}
    ::selection{background:#f6bfd0;color:#3c2130}
    .container{width:min(1190px,calc(100% - 48px));margin-inline:auto}
    .topline{height:35px;background:var(--berry-deep);color:#fff2e9;overflow:hidden;display:flex;align-items:center}
    .topline-track{display:flex;gap:42px;white-space:nowrap;width:max-content;animation:marquee 38s linear infinite;font-size:10px;letter-spacing:.16em;text-transform:uppercase;font-weight:800}
    .topline-track span{display:inline-flex;gap:42px;align-items:center}.topline-track i{color:#ffb58e;font-size:16px;font-style:normal}
    .header{position:sticky;top:0;z-index:30;background:rgba(255,249,242,.93);-webkit-backdrop-filter:blur(18px);backdrop-filter:blur(18px);border-bottom:1px solid rgba(90,46,60,.09);transition:box-shadow .2s}
    .header.scrolled{box-shadow:0 9px 24px rgba(88,39,48,.06)}
    .nav{height:77px;display:flex;align-items:center;justify-content:space-between;gap:20px}
    .brand{display:inline-flex;align-items:center;gap:10px;flex-shrink:0}
    .brand-icon{background:#f6d2db;border-radius:16px;width:45px;height:45px;display:grid;place-items:center;font-size:24px;transform:rotate(-7deg);box-shadow:inset 0 -3px 0 rgba(150,37,82,.08)}
    .brand-text{font-family:var(--display);font-weight:800;letter-spacing:-1px;font-size:26px;color:var(--berry-deep);line-height:1}
    .brand-text span{color:var(--ink)}
    .nav-links{display:flex;gap:37px;font-size:13px;font-weight:800;color:#705963}
    .nav-links a{transition:color .2s;position:relative}
    .nav-links a::after{content:"";position:absolute;bottom:-7px;left:0;width:0;height:2px;background:var(--berry);transition:width .25s}
    .nav-links a:hover{color:var(--berry)}.nav-links a:hover::after{width:100%}
    .nav-cart{display:flex;align-items:center;gap:11px;background:var(--ink);border:0;border-radius:99px;color:#fff;padding:11px 12px 11px 18px;font-weight:800;font-size:12px;transition:transform .2s,background .2s;box-shadow:0 8px 18px rgba(58,28,39,.13)}
    .nav-cart:hover{transform:translateY(-2px);background:var(--berry-deep)}
    .cart-badge{width:27px;height:27px;border-radius:50%;background:#fce9e3;color:var(--berry-deep);display:grid;place-items:center;font-size:12px;font-weight:800}
    .cart-badge.bump{animation:bump .35s ease}
    .hero{position:relative;display:grid;grid-template-columns:1.05fr .95fr;align-items:center;min-height:572px;margin-top:23px;border-radius:34px;overflow:hidden;background:#fbe9e4;isolation:isolate}
    .hero::before{content:"";position:absolute;inset:0;background:radial-gradient(circle at 16% 12%,#fff9ed 0,transparent 47%),linear-gradient(110deg,#fff3e7,#f9d7da);z-index:-2}
    .hero::after{content:"";position:absolute;left:-78px;bottom:-118px;width:320px;height:320px;border:1px solid rgba(180,61,104,.1);border-radius:50%;box-shadow:0 0 0 35px rgba(255,255,255,.1),0 0 0 75px rgba(255,255,255,.08);z-index:-1}
    .hero-copy{padding:62px 12px 60px clamp(32px,5.1vw,76px);position:relative;z-index:3;animation:slideUp .75s both}
    .eyebrow{display:inline-flex;gap:9px;align-items:center;color:var(--berry-deep);font-size:11px;font-weight:800;letter-spacing:.12em;text-transform:uppercase}
    .eyebrow::before{content:'✦';font-size:20px;color:#d78859}
    h1,h2,h3,h4,p{margin-top:0}
    .hero h1{font:800 clamp(47px,5.5vw,75px)/1.04 var(--display);letter-spacing:-3px;margin:21px 0 22px;max-width:590px}
    .hero h1 em{font-style:normal;color:var(--berry);position:relative;white-space:nowrap}
    .hero h1 em::after{content:"";position:absolute;left:2%;bottom:-12px;width:94%;height:14px;border:solid var(--berry);border-width:3px 0 0;border-radius:50%;transform:rotate(-3deg);opacity:.65}
    .hero p{font-size:15px;color:#7d6166;line-height:1.85;max-width:410px;margin-bottom:31px}
    .hero-actions{display:flex;align-items:center;gap:20px;flex-wrap:wrap}
    .btn-primary{border:0;border-radius:99px;padding:16px 25px;color:white;background:var(--berry);display:inline-flex;align-items:center;gap:12px;font-size:13px;font-weight:800;box-shadow:0 12px 23px rgba(166,53,92,.24);transition:transform .25s,background .25s,box-shadow .25s}
    .btn-primary:hover{transform:translateY(-4px);background:var(--berry-deep);box-shadow:0 17px 29px rgba(166,53,92,.32)}
    .btn-link{font-size:13px;font-weight:800;color:var(--brown);border-bottom:1px solid #bb8c95;padding:7px 0;transition:color .25s}.btn-link:hover{color:var(--berry)}
    .hero-foot{display:flex;align-items:center;gap:9px;margin-top:38px;font-size:12px;color:#75575e;font-weight:700}
    .hero-foot .heart{width:30px;height:30px;display:grid;place-items:center;border-radius:50%;background:#fff7ef;color:var(--berry);font-size:16px}
    .hero-visual{align-self:stretch;min-height:500px;position:relative;display:grid;place-items:center;overflow:hidden;isolation:isolate}
    .hero-visual::before{content:"";position:absolute;width:550px;height:550px;border-radius:50%;background:#f1b9c6;right:-115px;top:40px;z-index:-2}
    .hero-visual::after{content:"";position:absolute;width:410px;height:410px;border-radius:50%;border:1px dashed rgba(255,255,255,.52);right:-42px;top:114px;z-index:-1}
    .hero-jar{width:min(465px,97%);z-index:2;position:relative;filter:drop-shadow(0 25px 13px rgba(106,43,65,.15));animation:heroFloat 6s ease-in-out infinite}
    .hero-jar svg{width:100%;height:auto;display:block}
    .hero-mini{position:absolute;right:8%;top:9%;width:104px;height:104px;border-radius:50%;background:#fff7eb;border:1px solid #fff;display:grid;place-items:center;text-align:center;transform:rotate(11deg);box-shadow:0 14px 29px rgba(92,41,56,.12);z-index:4;color:var(--berry-deep);font:700 17px/1.2 var(--display)}
    .hero-spark{position:absolute;font-size:27px;color:#fff8e9;z-index:4;animation:sparkle 3.2s ease-in-out infinite}.hero-spark.one{left:15%;top:14%}.hero-spark.two{right:10%;bottom:17%;font-size:39px;animation-delay:1s}.hero-spark.three{left:9%;bottom:28%;font-size:17px;animation-delay:1.8s}
    .floating-chip{position:absolute;left:3%;bottom:12%;background:rgba(255,255,255,.94);border-radius:14px;padding:12px 15px;box-shadow:0 12px 32px rgba(82,37,49,.13);z-index:4;display:flex;gap:9px;align-items:center;transform:rotate(-6deg);animation:chipFloat 5s ease-in-out infinite}
    .floating-chip span{font-size:25px}.floating-chip strong{font-size:12px;line-height:1.4}.floating-chip small{display:block;color:var(--muted);font-size:10px;margin-top:2px}
    .benefits{display:grid;grid-template-columns:repeat(3,1fr);gap:18px;margin-top:27px}
    .benefit{padding:21px 19px;display:flex;align-items:center;gap:14px;border-radius:19px;background:white;border:1px solid #f2e8e1;box-shadow:0 5px 18px rgba(96,51,52,.025)}
    .benefit-emoji{height:48px;width:48px;display:grid;place-items:center;background:#fff0e9;border-radius:15px;font-size:24px;flex-shrink:0}
    .benefit strong{display:block;font-size:13px;margin-bottom:5px}.benefit p{font-size:11px;color:var(--muted);margin:0;line-height:1.6}
    .menu{padding-top:106px;padding-bottom:92px}
    .section-top{display:flex;align-items:end;justify-content:space-between;gap:24px;margin-bottom:30px}
    .kicker{display:block;color:var(--berry);font-size:11px;font-weight:800;letter-spacing:.19em;text-transform:uppercase;margin-bottom:11px}
    .section-title{font:800 clamp(35px,4vw,51px)/1.15 var(--display);letter-spacing:-1.6px;margin:0}
    .section-title em{font-style:normal;color:var(--berry)}
    .section-desc{max-width:330px;color:var(--muted);font-size:13px;line-height:1.7;margin:0 0 4px}
    .filters{display:flex;gap:9px;flex-wrap:wrap;margin-bottom:30px}
    .filter-btn{border:1px solid #ead9d2;border-radius:99px;color:#78646c;background:#fffaf6;font-size:12px;font-weight:800;padding:11px 19px;transition:background .2s,border-color .2s,transform .2s,color .2s}
    .filter-btn:hover{transform:translateY(-2px);border-color:#d98ea7}.filter-btn.active{background:var(--ink);border-color:var(--ink);color:white}
    .products-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:24px;min-height:360px}
    .product-card{background:white;border:1px solid #f0e3dc;border-radius:23px;overflow:hidden;box-shadow:0 7px 25px rgba(91,45,59,.04);transition:transform .35s cubic-bezier(.18,.7,.25,1),box-shadow .35s}
    .product-card:hover{transform:translateY(-9px);box-shadow:0 21px 42px rgba(91,45,59,.13)}
    .product-art{height:248px;position:relative;display:grid;place-items:center;isolation:isolate;overflow:hidden;background:var(--bg)}
    .product-art::before{content:"";position:absolute;width:260px;height:260px;border-radius:50%;background:rgba(255,255,255,.24);right:-52px;top:-100px;z-index:-1}
    .product-art::after{content:"";position:absolute;width:200px;height:200px;border:1px dashed rgba(255,255,255,.65);border-radius:50%;bottom:-125px;left:-68px;z-index:-1}
    .product-art svg{height:260px;width:260px;max-width:90%;filter:drop-shadow(0 15px 8px rgba(65,28,36,.12));transition:transform .45s cubic-bezier(.18,.7,.25,1)}
    .product-card:hover .product-art svg{transform:scale(1.085) rotate(-3deg) translateY(-4px)}
    .product-tag{position:absolute;top:15px;left:15px;background:white;color:var(--berry-deep);font-size:10px;font-weight:800;border-radius:999px;padding:8px 12px;z-index:3;box-shadow:0 5px 14px rgba(40,26,26,.06)}
    .tiny-heart{position:absolute;right:18px;bottom:15px;color:rgba(255,255,255,.83);font-size:24px;transform:rotate(15deg)}
    .product-info{padding:23px 23px 22px}
    .product-info h3{font:800 22px/1.15 var(--display);letter-spacing:-.55px;margin:0 0 10px}
    .product-info p{font-size:12px;line-height:1.7;color:var(--muted);min-height:41px;margin-bottom:22px}
    .product-bottom{display:flex;align-items:end;justify-content:space-between;gap:8px}
    .price-label{display:block;color:#9a8586;font-size:10px;margin-bottom:5px}
    .price{font-weight:800;font-size:23px;letter-spacing:-.7px;color:var(--berry-deep)}
    .add-btn{border:0;border-radius:13px;padding:12px 15px;background:#f9e7ed;color:var(--berry-deep);display:inline-flex;gap:8px;align-items:center;font-weight:800;font-size:12px;transition:transform .2s,background .2s,color .2s}
    .add-btn:hover{background:var(--berry);color:white;transform:translateY(-2px)}.add-btn.added{background:#e0f6e9;color:#1d7950}
    .steps-wrap{background:#f8ecdf;padding:78px 0 89px;overflow:hidden}
    .steps-head{text-align:center;margin-bottom:40px}.steps-head .section-title{font-size:clamp(31px,4vw,46px)}
    .steps{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
    .step{position:relative;background:#fffaf5;border:1px solid rgba(128,75,67,.08);padding:31px 26px;border-radius:23px;text-align:center;box-shadow:0 8px 22px rgba(93,48,50,.035)}
    .step-icon{margin:0 auto 19px;height:64px;width:64px;border-radius:22px;display:grid;place-items:center;font-size:31px;background:#f9e5e5}
    .step-num{position:absolute;top:17px;right:18px;color:#d5bfc0;font:800 22px var(--display)}
    .step h3{font:800 21px var(--display);margin-bottom:8px}.step p{font-size:12px;line-height:1.75;color:var(--muted);margin:0}
    .bottom-banner{margin-top:94px;margin-bottom:93px;border-radius:28px;background:var(--berry-deep);color:white;display:flex;align-items:center;justify-content:space-between;gap:30px;padding:46px 63px;position:relative;overflow:hidden}
    .bottom-banner::after{content:'✳';position:absolute;right:24%;bottom:-95px;color:rgba(255,255,255,.07);font-size:270px;line-height:1;pointer-events:none}
    .bottom-banner h2{font:800 clamp(29px,3.7vw,43px)/1.16 var(--display);letter-spacing:-1px;margin-bottom:10px}.bottom-banner p{font-size:12px;line-height:1.8;opacity:.8;margin:0;max-width:470px}
    .btn-light{border:0;border-radius:99px;background:#fff9f2;color:var(--berry-deep);padding:15px 23px;font-weight:800;font-size:12px;display:inline-flex;align-items:center;gap:10px;position:relative;white-space:nowrap;transition:transform .25s,box-shadow .25s}
    .btn-light:hover{transform:translateY(-4px);box-shadow:0 12px 23px rgba(25,7,17,.17)}
    .footer{background:#35212c;color:#fff6f1;padding:50px 0 22px}
    .footer-grid{display:flex;justify-content:space-between;gap:30px;align-items:start}
    .footer .brand-text,.footer .brand-text span{color:#fff7f1}
    .footer .brand-icon{background:#a75070}
    .footer p{color:#c9b3b8;max-width:370px;font-size:12px;line-height:1.9;margin:17px 0 0}
    .footer-links{text-align:right;font-size:12px;line-height:2;color:#f5cdd8}.footer-links strong{color:#fff}
    .footer-bottom{margin-top:43px;border-top:1px solid rgba(255,255,255,.13);padding-top:20px;color:#a89199;text-align:center;font-size:11px}
    .overlay{position:fixed;inset:0;z-index:50;background:rgba(35,18,29,.55);-webkit-backdrop-filter:blur(2px);backdrop-filter:blur(2px);opacity:0;visibility:hidden;transition:opacity .3s,visibility .3s}
    .overlay.show{opacity:1;visibility:visible}
    .cart-panel{position:fixed;z-index:51;right:0;top:0;height:100dvh;width:min(466px,100%);display:flex;flex-direction:column;transform:translateX(105%);transition:transform .42s cubic-bezier(.2,.75,.15,1);background:#fffbf7;box-shadow:-20px 0 70px rgba(40,12,22,.2);visibility:hidden}
    .cart-panel.open{transform:translateX(0);visibility:visible}
    .cart-header{flex:0 0 auto;display:flex;align-items:center;justify-content:space-between;padding:25px 24px 20px;border-bottom:1px solid var(--line)}
    .cart-header h2{font:800 28px var(--display);margin-bottom:5px}.cart-header p{font-size:11px;color:var(--muted);margin:0}
    .close-cart{height:41px;width:41px;flex-shrink:0;border:0;background:#f9e9e8;color:var(--berry-deep);border-radius:50%;font-size:25px;line-height:1;transition:transform .2s}.close-cart:hover{transform:rotate(90deg)}
    .cart-items{flex:1;min-height:50px;overflow-y:auto;overscroll-behavior:contain;padding:8px 23px}
    .empty-cart{min-height:100%;display:flex;flex-direction:column;align-items:center;justify-content:center;text-align:center;padding:40px 12px;color:var(--muted)}
    .empty-cart .empty-icon{font-size:61px;filter:drop-shadow(0 7px 8px rgba(140,50,90,.15));margin-bottom:21px}.empty-cart strong{font:800 24px var(--display);color:var(--ink);margin-bottom:9px}.empty-cart p{font-size:12px;line-height:1.7;max-width:255px;margin-bottom:18px}.empty-cart a{font-size:12px;font-weight:800;color:var(--berry);border-bottom:1px solid var(--berry);padding-bottom:3px}
    .cart-item{display:grid;grid-template-columns:79px 1fr auto;gap:12px;border-bottom:1px solid var(--line);padding:15px 0;align-items:start}
    .cart-thumb{width:79px;height:83px;border-radius:13px;background:var(--bg);display:grid;place-items:center;overflow:hidden}
    .cart-thumb svg{width:100px;height:100px;transform:scale(.94)}
    .cart-item h4{font-size:13px;margin:4px 0 5px}.cart-item-price{font-size:12px;font-weight:800;color:var(--berry-deep)}
    .quantity{display:inline-flex;align-items:center;gap:10px;margin-top:10px;border:1px solid #eeddd8;border-radius:9px;padding:3px}
    .quantity button{border:0;height:23px;width:24px;border-radius:6px;background:#f9e9e8;color:var(--berry-deep);font-weight:800;transition:background .2s}.quantity button:hover{background:#edc5d1}
    .quantity span{font-size:11px;min-width:13px;text-align:center;font-weight:800}
    .remove-item{border:0;background:none;color:#bda7ab;font-size:21px;padding:0 3px}.remove-item:hover{color:var(--berry)}
    .cart-bottom{background:white;border-top:1px solid var(--line);padding:20px 23px max(22px,env(safe-area-inset-bottom));flex-shrink:0;max-height:66dvh;overflow-y:auto}
    .cart-total{display:flex;justify-content:space-between;align-items:baseline;margin-bottom:17px}.cart-total span{color:var(--muted);font-size:12px}.cart-total strong{color:var(--berry-deep);font-size:26px}
    .checkout-fields{display:grid;gap:9px;margin-bottom:15px}
    .checkout-fields input,.checkout-fields select,.checkout-fields textarea{border:1px solid #eadbd4;border-radius:11px;background:#fffbf8;color:var(--ink);padding:12px 13px;font-size:12px;width:100%;outline:0;resize:vertical}
    .checkout-fields input:focus,.checkout-fields select:focus,.checkout-fields textarea:focus{border-color:#c76383;box-shadow:0 0 0 3px #fae7ed}
    .checkout-fields label{font-size:11px;font-weight:800;color:#775d65}
    .address-field[hidden]{display:none}
    .checkout-btn{width:100%;display:flex;justify-content:center;align-items:center;gap:10px;background:var(--green);color:#fff;border:0;border-radius:13px;font-size:13px;font-weight:800;padding:15px 12px;transition:transform .2s,background .2s;text-align:center;text-decoration:none;cursor:pointer}
    .checkout-btn:hover{background:#15764a;transform:translateY(-2px)}
    .checkout-btn:focus-visible,.copy-order:focus-visible{outline:3px solid #d9799b;outline-offset:3px}
    .backup-checkout{display:flex;flex-wrap:wrap;justify-content:center;align-items:center;gap:7px 12px;margin-top:12px}
    .copy-order{padding:9px 12px;border-radius:10px;border:1px solid #e3d1cf;background:#fff8f7;color:#7e4059;font-size:11px;font-weight:800;cursor:pointer}
    .copy-order:hover{border-color:#cf8da3;background:#fcecf2}
    .backup-checkout a{color:#7e4059;text-decoration:underline;text-underline-offset:3px;font-size:11px;font-weight:700}
    .secure-note{text-align:center;color:#9e888a;margin:10px 0 0;font-size:10px;line-height:1.6}
    .toast{position:fixed;left:50%;bottom:28px;z-index:65;max-width:calc(100% - 32px);transform:translate(-50%,30px) scale(.95);opacity:0;pointer-events:none;border-radius:99px;padding:14px 20px;background:#38232b;color:#fff;font-size:12px;font-weight:800;box-shadow:var(--shadow);transition:opacity .28s,transform .28s;text-align:center}
    .toast.show{opacity:1;transform:translate(-50%,0) scale(1)}
    .mobile-cart{position:fixed;z-index:29;bottom:17px;left:50%;transform:translate(-50%,130px);opacity:0;pointer-events:none;display:none;align-items:center;justify-content:space-between;gap:20px;min-width:230px;padding:14px 21px;border:0;border-radius:99px;background:var(--ink);color:#fff;box-shadow:0 12px 35px rgba(50,19,30,.27);font-size:12px;font-weight:800;transition:transform .35s,opacity .35s}.mobile-cart.show{transform:translate(-50%,0);opacity:1;pointer-events:auto}
    [data-reveal]{opacity:0;transform:translateY(30px);transition:opacity .7s ease,transform .7s cubic-bezier(.2,.75,.2,1)}
    [data-reveal].visible{opacity:1;transform:translateY(0)}
    @keyframes marquee{to{transform:translateX(-50%)}}
    @keyframes heroFloat{0%,100%{transform:translateY(0) rotate(-2deg)}50%{transform:translateY(-14px) rotate(1deg)}}
    @keyframes chipFloat{0%,100%{transform:translateY(0) rotate(-6deg)}50%{transform:translateY(-12px) rotate(-3deg)}}
    @keyframes sparkle{0%,100%{opacity:.55;transform:scale(.86) rotate(-9deg)}50%{opacity:1;transform:scale(1.2) rotate(18deg)}}
    @keyframes slideUp{from{transform:translateY(20px);opacity:0}to{transform:translateY(0);opacity:1}}
    @keyframes bump{0%,100%{transform:scale(1)}45%{transform:scale(1.3)}}
    @keyframes cardAppear{from{opacity:0;transform:translateY(18px) scale(.97)}to{opacity:1;transform:translateY(0) scale(1)}}
    .product-card{animation:cardAppear .5s both;animation-delay:var(--delay,0ms)}
    @media(max-width:960px){.nav-links{gap:20px}.hero{grid-template-columns:1.1fr .9fr;min-height:510px}.hero-copy{padding-left:37px}.hero h1{font-size:56px}.hero-visual{min-height:510px}.hero-mini{right:3%;width:88px;height:88px;font-size:14px}.floating-chip{left:0}.product-info{padding:18px}.product-info h3{font-size:19px}.products-grid{gap:16px}}
    @media(max-width:720px){.container{width:calc(100% - 28px)}.topline{height:29px}.topline-track{font-size:9px}.nav{height:67px}.nav-links{display:none}.brand-icon{width:40px;height:40px;font-size:21px}.brand-text{font-size:23px}.nav-cart{font-size:11px;padding:9px 10px 9px 14px}.hero{display:flex;flex-direction:column;margin-top:12px;border-radius:25px;min-height:0}.hero-copy{text-align:center;display:flex;align-items:center;flex-direction:column;padding:43px 21px 5px}.hero h1{font-size:clamp(43px,9.8vw,61px);letter-spacing:-2.4px;margin:16px 0 24px}.hero p{font-size:13px;line-height:1.8;max-width:420px;margin-bottom:25px}.hero-actions{justify-content:center;gap:14px}.btn-primary{padding:14px 20px}.hero-foot{margin-top:22px}.hero-visual{width:100%;min-height:345px}.hero-visual::before{width:440px;height:440px;right:50%;transform:translateX(50%);top:25px}.hero-visual::after{right:50%;transform:translateX(50%);top:75px;width:320px;height:320px}.hero-jar{width:320px;max-width:100%}.floating-chip{left:5%;bottom:9%;padding:9px;font-size:10px}.floating-chip span{font-size:19px}.floating-chip strong{font-size:10px}.floating-chip small{font-size:9px}.hero-mini{right:6%;top:3%;height:82px;width:82px;font-size:13px}.benefits{grid-template-columns:1fr;gap:9px;margin-top:14px}.benefit{padding:12px 15px}.benefit-emoji{width:40px;height:40px;font-size:21px}.menu{padding-top:72px;padding-bottom:71px}.section-top{display:block;margin-bottom:22px}.section-desc{margin-top:12px}.filters{gap:7px;margin-bottom:22px}.filter-btn{font-size:10px;padding:10px 13px}.products-grid{grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}.product-art{height:169px}.product-art svg{height:200px;width:200px;max-width:100%}.product-tag{top:10px;left:10px;padding:6px 9px;font-size:9px}.product-info{padding:14px 12px 15px}.product-info h3{font-size:16px;margin-bottom:8px}.product-info p{font-size:10px;min-height:50px;line-height:1.5;margin-bottom:14px}.price{font-size:18px}.price-label{font-size:9px}.product-bottom{align-items:center;gap:5px}.add-btn{font-size:0;padding:10px 12px;border-radius:10px}.add-btn span{font-size:20px;line-height:1}.steps-wrap{padding:61px 0}.steps{grid-template-columns:1fr;gap:12px}.step{padding:24px 25px}.step-icon{height:55px;width:55px;font-size:25px;margin-bottom:12px}.bottom-banner{margin-block:61px;padding:34px 25px;display:block;text-align:center}.bottom-banner p{margin:0 auto 24px}.footer{padding-top:40px}.footer-grid{display:block;text-align:center}.footer .brand{justify-content:center}.footer p{margin:14px auto}.footer-links{text-align:center;margin-top:22px}.footer-bottom{margin-top:28px}.mobile-cart{display:flex}.toast{bottom:90px}}
    @media(max-width:390px){.brand-text{font-size:20px}.nav-cart .cart-label{display:none}.nav-cart{padding:9px 10px 9px 13px}.hero h1{font-size:41px}.hero-mini{right:2%}.product-info h3{font-size:15px}.product-art{height:151px}.product-art svg{height:187px}.product-info{padding:13px 10px}.add-btn{padding:9px}.price{font-size:16px}}
    @media(prefers-reduced-motion:reduce){html{scroll-behavior:auto}*,*::before,*::after{animation-duration:.01ms!important;animation-iteration-count:1!important;transition-duration:.01ms!important} [data-reveal]{opacity:1;transform:none}.hero-jar{transform:none}}
  </style>
</head>
<body>
  <div class="topline" aria-label="Bolos de pote artesanais feitos com carinho"><div class="topline-track" aria-hidden="true">
    <span>FEITO COM CARINHO <i>✳</i> CREMOSIDADE EM CAMADAS <i>✳</i> SEU DOCE FAVORITO <i>✳</i> PEÇA PELO WHATSAPP <i>✳</i></span>
    <span>FEITO COM CARINHO <i>✳</i> CREMOSIDADE EM CAMADAS <i>✳</i> SEU DOCE FAVORITO <i>✳</i> PEÇA PELO WHATSAPP <i>✳</i></span>
  </div></div>
  <header class="header" id="header">
    <nav class="nav container" aria-label="Navegação principal">
      <a class="brand" href="#inicio" aria-label="Doce Pote, ir para início"><span class="brand-icon" aria-hidden="true">🍰</span><span class="brand-text">doce<span>pote.</span></span></a>
      <div class="nav-links"><a href="#inicio">Início</a><a href="#cardapio">Cardápio</a><a href="#como-pedir">Como pedir</a><a href="#contato">Contato</a></div>
      <button class="nav-cart" id="openCart" type="button" aria-label="Abrir carrinho de compras">🛍️ <span class="cart-label">Meu carrinho</span> <span class="cart-badge" id="cartCount">0</span></button>
    </nav>
  </header>
  <main>
    <section class="hero container" id="inicio" aria-labelledby="heroTitle">
      <div class="hero-copy">
        <span class="eyebrow">Um docinho muda tudo</span>
        <h1 id="heroTitle">Felicidade em <em>cada camada.</em></h1>
        <p>Massa fofinha, recheio generoso e aquele sabor que faz você fechar os olhos na primeira colherada. Escolha seu potinho favorito!</p>
        <div class="hero-actions"><a href="#cardapio" class="btn-primary">Quero meu bolo de pote <span aria-hidden="true">↗</span></a><a href="#como-pedir" class="btn-link">Como funciona?</a></div>
        <div class="hero-foot"><span class="heart" aria-hidden="true">♥</span> Produzidos com amor, um por um.</div>
      </div>
      <div class="hero-visual" aria-label="Ilustração de um bolo de pote recheado">
        <span class="hero-spark one" aria-hidden="true">✦</span><span class="hero-spark two" aria-hidden="true">✳</span><span class="hero-spark three" aria-hidden="true">✧</span>
        <div class="hero-mini">amor em<br>cada<br>colherada ♡</div>
        <div class="hero-jar" id="heroJar" aria-hidden="true"></div>
        <div class="floating-chip"><span aria-hidden="true">🍫</span><strong>Caprichado de verdade<small>Camadas irresistíveis</small></strong></div>
      </div>
    </section>
    <section class="benefits container" aria-label="Por que escolher o Doce Pote">
      <div class="benefit" data-reveal><span class="benefit-emoji" aria-hidden="true">🍓</span><div><strong>Ingredientes selecionados</strong><p>Carinho e qualidade em cada potinho.</p></div></div>
      <div class="benefit" data-reveal><span class="benefit-emoji" aria-hidden="true">🥄</span><div><strong>Recheio de verdade</strong><p>Camadas generosas de cremosidade.</p></div></div>
      <div class="benefit" data-reveal><span class="benefit-emoji" aria-hidden="true">💌</span><div><strong>É muito fácil pedir</strong><p>Monte seu pedido e envie no WhatsApp.</p></div></div>
    </section>
    <section class="menu container" id="cardapio" aria-labelledby="menuTitle">
      <div class="section-top" data-reveal><div><span class="kicker">Qual vai ser o seu?</span><h2 class="section-title" id="menuTitle">Nossos <em>queridinhos.</em></h2></div><p class="section-desc">Sabores que abraçam a alma. Escolha um, dois... ou quantos der vontade!</p></div>
      <div class="filters" id="filters" aria-label="Filtrar sabores">
        <button type="button" class="filter-btn active" data-filter="todos" aria-pressed="true">Todos os sabores ✦</button>
        <button type="button" class="filter-btn" data-filter="chocolate" aria-pressed="false">🍫 Chocolate</button>
        <button type="button" class="filter-btn" data-filter="especiais" aria-pressed="false">✨ Especiais</button>
        <button type="button" class="filter-btn" data-filter="frutas" aria-pressed="false">🍓 Frutas</button>
      </div>
      <div class="products-grid" id="productsGrid" aria-live="polite"></div>
    </section>
    <section class="steps-wrap" id="como-pedir" aria-labelledby="stepsTitle"><div class="container">
      <div class="steps-head" data-reveal><span class="kicker">Sem complicação</span><h2 class="section-title" id="stepsTitle">Seu docinho em <em>3 passos</em></h2></div>
      <div class="steps">
        <article class="step" data-reveal><span class="step-num">01</span><div class="step-icon" aria-hidden="true">🍰</div><h3>Escolha os sabores</h3><p>Explore nosso cardápio e adicione seus bolos preferidos ao carrinho.</p></article>
        <article class="step" data-reveal><span class="step-num">02</span><div class="step-icon" aria-hidden="true">🛍️</div><h3>Monte o seu pedido</h3><p>Ajuste as quantidades e confira o valor total antes de finalizar.</p></article>
        <article class="step" data-reveal><span class="step-num">03</span><div class="step-icon" aria-hidden="true">💬</div><h3>Envie pelo WhatsApp</h3><p>Seu pedido vai prontinho na mensagem para combinar os próximos detalhes.</p></article>
      </div>
    </div></section>
    <section class="bottom-banner container" data-reveal><div><h2>Um potinho de alegria<br>tá te esperando! ✨</h2><p>Escolha seus sabores, monte seu carrinho e mande o pedido. É simples assim.</p></div><a href="#cardapio" class="btn-light">Escolher meus docinhos <span aria-hidden="true">↗</span></a></section>
  </main>
  <footer class="footer" id="contato"><div class="container">
    <div class="footer-grid"><div><a class="brand" href="#inicio"><span class="brand-icon" aria-hidden="true">🍰</span><span class="brand-text">doce<span>pote.</span></span></a><p>Pequenos potinhos, grandes momentos. Obrigado por fazer parte da nossa história mais doce!</p></div>
      <div class="footer-links"><strong>Quer tirar uma dúvida?</strong><br>Fale com a gente no WhatsApp<br><a href="https://wa.me/5513981852816" target="_blank" rel="noopener noreferrer">(13) 98185-2816 ↗</a></div></div>
    <div class="footer-bottom">© <span id="year"></span> Doce Pote. Feito com carinho. ♡</div>
  </div></footer>
  <div class="overlay" id="overlay"></div>
  <aside class="cart-panel" id="cartPanel" role="dialog" aria-modal="true" aria-label="Carrinho de compras" aria-hidden="true" inert>
    <div class="cart-header"><div><h2>Seu carrinho 🛍️</h2><p id="cartSubtitle">Seus docinhos estão aqui!</p></div><button type="button" id="closeCart" class="close-cart" aria-label="Fechar carrinho">×</button></div>
    <div class="cart-items" id="cartItems"></div>
    <div class="cart-bottom">
      <div class="cart-total"><span>Subtotal do pedido</span><strong id="cartTotal">R$ 0,00</strong></div>
      <div class="checkout-fields">
        <label for="customerName">Seu nome (opcional)</label><input id="customerName" type="text" maxlength="60" placeholder="Como podemos te chamar?" autocomplete="name">
        <label for="orderType">Como deseja receber?</label><select id="orderType"><option value="A combinar">Entrega ou retirada: a combinar</option><option value="Entrega">Entrega</option><option value="Retirada">Retirada</option></select>
        <div id="addressField" class="address-field" hidden><label for="customerAddress">Endereço para entrega</label><input id="customerAddress" maxlength="180" placeholder="Rua, número, bairro e cidade" autocomplete="street-address"></div>
        <label for="orderNotes">Alguma observação? (opcional)</label><textarea rows="2" id="orderNotes" maxlength="350" placeholder="Ex.: sem cobertura, horário desejado..."></textarea>
      </div>
      <a class="checkout-btn" id="checkoutBtn" href="https://wa.me/5513981852816" target="_blank" rel="noopener noreferrer" aria-describedby="checkoutHelp">💬 Enviar pedido pelo WhatsApp <span aria-hidden="true">↗</span></a>
      <p class="secure-note" id="checkoutHelp">Ao tocar, o WhatsApp abrirá com todos os itens, quantidades e total. Entrega e pagamento são combinados na conversa.</p>
      <div class="backup-checkout">
        <button class="copy-order" id="copyOrderBtn" type="button">📋 Copiar pedido</button>
        <a href="https://wa.me/5513981852816" target="_blank" rel="noopener noreferrer">Abrir WhatsApp manualmente ↗</a>
      </div>
    </div>
  </aside>
  <button type="button" class="mobile-cart" id="mobileCart" aria-label="Abrir carrinho"><span>🛍️ Ver carrinho</span><span id="mobileTotal">R$ 0,00</span></button>
  <div class="toast" id="toast" role="status" aria-live="polite"></div>
<script>
  // PERSONALIZE AQUI: nomes, categorias, preços e cores dos sabores.
  // Todos os valores são de exemplo. Ajuste antes de publicar sua loja.
  const products = [
    {id:1,name:'Brigadeiro Clássico',category:'chocolate',price:12.90,description:'Bolo de chocolate fofinho com brigadeiro bem cremoso.',tag:'Mais pedido ♡',emoji:'🍫',bg:'#f5dfd6',cream:'#f5dbba',cake:'#8b4b3f',filling:'#5b2b30',topping:'#60302d',accent:'#ba6f5a'},
    {id:2,name:'Ninho com Nutella',category:'especiais',price:16.90,description:'Leite Ninho irresistível com muito creme de avelã.',tag:'O favorito ✨',emoji:'🥛',bg:'#f9e8cd',cream:'#fff0c9',cake:'#c88c65',filling:'#6b3632',topping:'#fff7e0',accent:'#c28b5d'},
    {id:3,name:'Morango & Chocolate',category:'frutas',price:14.90,description:'Chocolate, creme delicado e pedacinhos de morango.',tag:'Frutado 🍓',emoji:'🍓',bg:'#f8dfe5',cream:'#ffe8ea',cake:'#8e4a48',filling:'#c84e67',topping:'#ffebdb',accent:'#e06b7a'},
    {id:4,name:'Dois Amores',category:'chocolate',price:14.50,description:'Brigadeiro preto e branco: combinação apaixonante.',tag:'Dois em um 💕',emoji:'💗',bg:'#e9ddec',cream:'#fff2d8',cake:'#8c5c4a',filling:'#e8bf9d',topping:'#6b383a',accent:'#c9909c'},
    {id:5,name:'Oreo Cremoso',category:'especiais',price:15.90,description:'Creme branco aveludado com biscoito crocante.',tag:'Crocante 🍪',emoji:'🍪',bg:'#e4e5f0',cream:'#fdf2e6',cake:'#494047',filling:'#f1e1c7',topping:'#fff8ea',accent:'#91818a'},
    {id:6,name:'Prestígio',category:'chocolate',price:13.90,description:'Beijinho de coco com uma cobertura de chocolate.',tag:'Clássico 🥥',emoji:'🥥',bg:'#dfeee8',cream:'#fff3dd',cake:'#895a48',filling:'#f8e5c9',topping:'#70423b',accent:'#8ab6a4'}
  ];
  const WHATSAPP_NUMBER='5513981852816';
  const STORAGE_KEY='docePoteCartV1'; // Mantém o carrinho da versão anterior.
  const $=selector=>document.querySelector(selector);
  const grid=$('#productsGrid'),cartPanel=$('#cartPanel'),overlay=$('#overlay'),cartItems=$('#cartItems'),toast=$('#toast');
  const money=n=>n.toLocaleString('pt-BR',{style:'currency',currency:'BRL'});
  const productById=id=>products.find(p=>p.id===id);
  let activeFilter='todos';
  let toastTimeout;
  let previousFocus=null;
  let cart=loadCart();

  function loadCart(){
    try{
      const stored=JSON.parse(localStorage.getItem(STORAGE_KEY)||'[]');
      if(!Array.isArray(stored)) return [];
      const out=[];
      for(const entry of stored){
        const id=Number(entry.id),q=Number(entry.quantity);
        if(productById(id)&&Number.isInteger(q)&&q>0&&q<=999){
          const existing=out.find(x=>x.id===id);
          if(existing) existing.quantity=Math.min(999,existing.quantity+q);else out.push({id,quantity:q});
        }
      }
      return out;
    }catch(e){return []}
  }
  function saveCart(){try{localStorage.setItem(STORAGE_KEY,JSON.stringify(cart))}catch(e){/* Navegação privada. */}}
  const getCount=()=>cart.reduce((n,item)=>n+item.quantity,0);
  const getTotal=()=>cart.reduce((n,item)=>n+(productById(item.id)?.price||0)*item.quantity,0);

  // Ilustração SVG original: bolo servido em um potinho transparente.
  // É gerada dentro do HTML, então o site funciona sem carregar fotos externas.
  function jarSVG(p){
    const key='flavor'+p.id;
    return `<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 360 360" aria-hidden="true" focusable="false">
      <defs>
        <linearGradient id="glass-${key}" x1="0" y1="0" x2="1" y2=".2"><stop stop-color="#fff" stop-opacity=".66"/><stop offset=".2" stop-color="#fff" stop-opacity=".07"/><stop offset=".8" stop-color="#fff" stop-opacity=".08"/><stop offset="1" stop-color="#fff" stop-opacity=".45"/></linearGradient>
        <linearGradient id="layer-${key}" x1="0" y1="0" x2="0" y2="1"><stop stop-color="${p.cake}"/><stop offset="1" stop-color="${p.filling}"/></linearGradient>
        <clipPath id="clip-${key}"><path d="M99 125 Q98 116 112 116 L248 116 Q261 116 261 126 L247 289 Q246 305 228 307 L131 307 Q114 305 113 288 Z"/></clipPath>
      </defs>
      <ellipse cx="182" cy="319" rx="107" ry="15" fill="#47252c" opacity=".12"/>
      <g transform="rotate(-3 180 210)">
        <g clip-path="url(#clip-${key})">
          <rect x="89" y="116" width="182" height="203" fill="${p.cake}"/>
          <path d="M84 144 Q125 153 177 145 T277 146 L277 171 Q240 177 182 170 T83 172 Z" fill="${p.cream}"/>
          <path d="M85 172 Q128 163 181 171 T275 170 L275 200 Q234 206 180 199 T84 202 Z" fill="${p.filling}"/>
          <path d="M83 202 Q129 194 183 203 T276 201 L276 226 Q224 234 181 226 T84 228 Z" fill="${p.cake}"/>
          <path d="M82 230 Q127 221 179 230 T277 229 L277 256 Q230 264 181 255 T82 258 Z" fill="${p.cream}"/>
          <path d="M84 260 Q125 248 185 258 T276 259 L276 284 Q229 294 181 288 T86 291 Z" fill="${p.filling}"/>
          <path d="M84 287 Q136 281 181 286 T276 286 L276 326 H84Z" fill="url(#layer-${key})"/>
          <g fill="${p.accent}" opacity=".56"><circle cx="129" cy="186" r="3"/><circle cx="218" cy="220" r="4"/><circle cx="168" cy="270" r="3"/><circle cx="231" cy="161" r="2.6"/><circle cx="141" cy="244" r="2.5"/><circle cx="217" cy="298" r="2.4"/></g>
        </g>
        <path d="M99 125 Q98 116 112 116 L248 116 Q261 116 261 126 L247 289 Q246 305 228 307 L131 307 Q114 305 113 288 Z" fill="url(#glass-${key})" stroke="#fff" stroke-opacity=".78" stroke-width="3.6"/>
        <path d="M117 135 L128 281" fill="none" stroke="#fff" stroke-opacity=".4" stroke-width="7" stroke-linecap="round"/>
        <path d="M247 135 L235 284" fill="none" stroke="#fff" stroke-opacity=".25" stroke-width="4" stroke-linecap="round"/>
        <rect x="132" y="212" width="96" height="49" rx="12" fill="#fff9f2" opacity=".93"/>
        <text x="180" y="230" text-anchor="middle" fill="#9c5270" font-family="Georgia,serif" font-size="13" font-weight="bold">docepote.</text>
        <path d="M160 237 H200" stroke="#d0abb4" stroke-width=".8"/>
        <text x="180" y="249" text-anchor="middle" fill="#9c6c78" font-family="Arial,sans-serif" font-size="7" letter-spacing="1.5">FEITO COM AMOR</text>
        <ellipse cx="180" cy="117" rx="82" ry="16" fill="${p.filling}" stroke="#fff" stroke-opacity=".75" stroke-width="4"/>
        <ellipse cx="180" cy="113" rx="69" ry="12" fill="${p.cream}"/>
        <path d="M120 112 Q117 95 139 92 Q132 75 156 71 Q157 58 177 58 Q185 44 202 58 Q220 56 224 77 Q248 78 244 96 Q252 107 241 116 Q215 109 199 115 Q182 106 163 114 Q142 106 120 112Z" fill="${p.topping}" stroke="#fff" stroke-opacity=".44" stroke-width="2"/>
        <path d="M138 105 Q154 88 175 102 M160 79 Q171 69 184 78 M200 83 Q220 87 226 103" fill="none" stroke="${p.cream}" stroke-width="7" stroke-linecap="round" opacity=".72"/>
        <path d="M171 62 Q174 50 184 51 M201 68 Q209 66 213 73" fill="none" stroke="#fff" stroke-opacity=".55" stroke-width="4" stroke-linecap="round"/>
        <g fill="${p.accent}"><circle cx="143" cy="92" r="5"/><circle cx="222" cy="98" r="4"/><circle cx="196" cy="65" r="3"/></g>
        <g fill="#fff9e8" opacity=".92"><circle cx="168" cy="99" r="3"/><circle cx="207" cy="102" r="2"/><circle cx="188" cy="77" r="2.5"/><circle cx="151" cy="106" r="1.8"/></g>
        <ellipse cx="180" cy="118" rx="84" ry="16" fill="none" stroke="#fff" stroke-opacity=".84" stroke-width="5"/>
      </g>
      <g fill="none" stroke="#fff" stroke-width="2" stroke-linecap="round" opacity=".8"><path d="M74 116 l0 -11 M68 110 l12 0"/><path d="M283 189 l0 -12 M277 183 l12 0"/></g>
    </svg>`;
  }

  function renderProducts(){
    const visible=activeFilter==='todos'?products:products.filter(p=>p.category===activeFilter);
    grid.innerHTML=visible.map((p,i)=>`<article class="product-card" style="--delay:${i*65}ms">
      <div class="product-art" style="--bg:${p.bg}">${jarSVG(p)}<span class="product-tag">${p.tag}</span><span class="tiny-heart" aria-hidden="true">✳</span></div>
      <div class="product-info"><h3>${p.name}</h3><p>${p.description}</p><div class="product-bottom"><div><span class="price-label">Cada potinho</span><strong class="price">${money(p.price)}</strong></div><button type="button" class="add-btn" data-add="${p.id}" aria-label="Adicionar ${p.name} ao carrinho"><span aria-hidden="true">＋</span> Adicionar</button></div></div>
    </article>`).join('');
  }

  function renderCart(){
    const count=getCount();
    const badge=$('#cartCount');
    badge.textContent=count;
    badge.classList.remove('bump');void badge.offsetWidth;badge.classList.add('bump');
    $('#cartTotal').textContent=money(getTotal());
    $('#mobileTotal').textContent=money(getTotal());
    $('#mobileCart').classList.toggle('show',count>0&&!cartPanel.classList.contains('open'));
    $('#cartSubtitle').textContent=count===0?'Que tal começar a adoçar seu dia?':`${count} ${count===1?'potinho escolhido':'potinhos escolhidos'} com carinho`;
    if(!count){
      cartItems.innerHTML=`<div class="empty-cart"><span class="empty-icon" aria-hidden="true">🧁</span><strong>Seu carrinho tá vazio!</strong><p>Escolha seus sabores favoritos e deixe o resto com a gente.</p><a href="#cardapio" id="goToMenu">Explorar cardápio ↗</a></div>`;
      return;
    }
    cartItems.innerHTML=cart.map(item=>{
      const p=productById(item.id);
      return `<div class="cart-item"><div class="cart-thumb" style="--bg:${p.bg}">${jarSVG(p)}</div><div><h4>${p.name}</h4><div class="cart-item-price">${money(p.price*item.quantity)}</div><div class="quantity"><button type="button" data-minus="${p.id}" aria-label="Diminuir quantidade de ${p.name}">−</button><span>${item.quantity}</span><button type="button" data-plus="${p.id}" aria-label="Aumentar quantidade de ${p.name}">＋</button></div></div><button class="remove-item" type="button" data-remove="${p.id}" aria-label="Remover ${p.name}">×</button></div>`;
    }).join('');
  }
  function showToast(message){toast.textContent=message;toast.classList.add('show');clearTimeout(toastTimeout);toastTimeout=setTimeout(()=>toast.classList.remove('show'),2500)}
  function addToCart(id,button){
    const p=productById(id);if(!p)return;
    const existing=cart.find(item=>item.id===id);
    if(existing){if(existing.quantity>=999){showToast('Quantidade máxima atingida.');return}existing.quantity++}else cart.push({id,quantity:1});
    saveCart();renderCart();showToast(`${p.name} adicionado! ♡`);
    if(button){button.classList.add('added');const old=button.innerHTML;button.innerHTML='<span aria-hidden="true">✓</span> Adicionado';setTimeout(()=>{if(button.isConnected){button.classList.remove('added');button.innerHTML=old}},950)}
  }
  function changeQuantity(id,diff){const item=cart.find(x=>x.id===id);if(!item)return;item.quantity+=diff;if(item.quantity<=0)cart=cart.filter(x=>x.id!==id);else item.quantity=Math.min(item.quantity,999);saveCart();renderCart()}
  function removeFromCart(id){cart=cart.filter(x=>x.id!==id);saveCart();renderCart();showToast('Item removido do carrinho')}
  function openCart(){previousFocus=document.activeElement;cartPanel.inert=false;cartPanel.classList.add('open');overlay.classList.add('show');document.body.classList.add('cart-open');cartPanel.setAttribute('aria-hidden','false');$('#mobileCart').classList.remove('show');$('#closeCart').focus()}
  function closeCart(){cartPanel.classList.remove('open');overlay.classList.remove('show');document.body.classList.remove('cart-open');cartPanel.setAttribute('aria-hidden','true');cartPanel.inert=true;$('#mobileCart').classList.toggle('show',getCount()>0);if(previousFocus?.isConnected)previousFocus.focus();else $('#openCart').focus()}
  function getOrderMessage(){
    if(!cart.length){showToast('Adicione um potinho ao carrinho primeiro ♡');return null}
    const name=$('#customerName').value.trim();
    const type=$('#orderType').value;
    const address=$('#customerAddress').value.trim();
    const notes=$('#orderNotes').value.trim();
    if(type==='Entrega'&&!address){showToast('Informe o endereço para a entrega');$('#customerAddress').focus();return null}
    const lines=cart.map(item=>{
      const p=productById(item.id);
      return `• ${item.quantity}x ${p.name} — ${money(p.price*item.quantity)} (${money(p.price)} cada)`;
    });
    return ['Olá! Gostaria de fazer um pedido na Doce Pote 🍰','', '*MEU PEDIDO:*',...lines,'',`*TOTAL: ${money(getTotal())}*`,'',...(name?[`*Nome:* ${name}`]:[]),`*Entrega/retirada:* ${type}`,...(address?[`*Endereço:* ${address}`]:[]),...(notes?[`*Observações:* ${notes}`]:[]),'','Podemos combinar os detalhes? ♡'].join('\n');
  }
  // A URL é atribuída a um <a> real durante o clique. O navegador segue o link
  // como um clique do cliente, sem abrir janelas artificialmente por JS.
  function checkout(event){
    const message=getOrderMessage();
    if(!message){event.preventDefault();return}
    event.currentTarget.href=`https://wa.me/${WHATSAPP_NUMBER}?text=${encodeURIComponent(message)}`;
  }
  async function copyOrder(){
    const message=getOrderMessage();
    if(!message)return;
    let success=false;
    try{
      if(navigator.clipboard&&window.isSecureContext){await navigator.clipboard.writeText(message);success=true}
    }catch(e){/* Alguns visualizadores bloqueiam a área de transferência. */}
    if(!success){
      const temp=document.createElement('textarea');
      temp.value=message;temp.setAttribute('readonly','');
      temp.style.cssText='position:fixed;top:0;left:-9999px;opacity:0';
      document.body.appendChild(temp);temp.select();
      try{success=document.execCommand('copy')}catch(e){};
      temp.remove();
    }
    if(success){showToast('Pedido copiado! Abra o WhatsApp e cole a mensagem. ♡')}
    else{showToast('Cópia bloqueada. Abra o site diretamente no navegador.')}
  }
  grid.addEventListener('click',event=>{const b=event.target.closest('[data-add]');if(b)addToCart(Number(b.dataset.add),b)});
  cartItems.addEventListener('click',event=>{
    const plus=event.target.closest('[data-plus]'),minus=event.target.closest('[data-minus]'),remove=event.target.closest('[data-remove]');
    if(plus)changeQuantity(Number(plus.dataset.plus),1);
    else if(minus)changeQuantity(Number(minus.dataset.minus),-1);
    else if(remove)removeFromCart(Number(remove.dataset.remove));
    else if(event.target.closest('#goToMenu'))closeCart();
  });
  $('#filters').addEventListener('click',event=>{const b=event.target.closest('[data-filter]');if(!b)return;activeFilter=b.dataset.filter;document.querySelectorAll('.filter-btn').forEach(el=>{const active=el===b;el.classList.toggle('active',active);el.setAttribute('aria-pressed',active)});renderProducts()});
  $('#openCart').addEventListener('click',openCart);$('#mobileCart').addEventListener('click',openCart);$('#closeCart').addEventListener('click',closeCart);overlay.addEventListener('click',closeCart);
  $('#checkoutBtn').addEventListener('click',checkout);
  $('#copyOrderBtn').addEventListener('click',copyOrder);
  $('#orderType').addEventListener('change',()=>{$('#addressField').hidden=$('#orderType').value!=='Entrega'});
  document.addEventListener('keydown',event=>{
    if(!cartPanel.classList.contains('open'))return;
    if(event.key==='Escape'){closeCart();return}
    if(event.key==='Tab'){
      const focusable=[...cartPanel.querySelectorAll('button:not([disabled]),a[href],input:not([disabled]),select:not([disabled]),textarea:not([disabled])')].filter(el=>el.getClientRects().length);
      if(!focusable.length)return;
      const first=focusable[0],last=focusable[focusable.length-1];
      if(event.shiftKey&&document.activeElement===first){event.preventDefault();last.focus()}
      else if(!event.shiftKey&&document.activeElement===last){event.preventDefault();first.focus()}
    }
  });
  $('#header').classList.toggle('scrolled',scrollY>10);
  addEventListener('scroll',()=>$('#header').classList.toggle('scrolled',scrollY>10),{passive:true});
  $('#year').textContent=new Date().getFullYear();
  $('#heroJar').innerHTML=jarSVG(products[2]);
  if('IntersectionObserver' in window){const obs=new IntersectionObserver(entries=>{for(const e of entries){if(e.isIntersecting){e.target.classList.add('visible');obs.unobserve(e.target)}}},{threshold:.08});document.querySelectorAll('[data-reveal]').forEach(el=>obs.observe(el))}else document.querySelectorAll('[data-reveal]').forEach(el=>el.classList.add('visible'));
  renderProducts();renderCart();
</script>
</body>
</html>
