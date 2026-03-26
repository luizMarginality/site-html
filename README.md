<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Aniversário One Piece</title>

  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;800&family=Pacifico&display=swap" rel="stylesheet" />

  <style>
    *{
      margin:0;
      padding:0;
      box-sizing:border-box;
      font-family:'Poppins',sans-serif;
    }

    html{
      scroll-behavior:smooth;
    }

    body{
  min-height:100vh;
  color:white;
  overflow-x:hidden;
  position:relative;
  background-color:#000;
}

body::before{
  content:"";
  position:fixed;
  inset:0;
  z-index:-1;

  background-image:
    linear-gradient(rgba(0,0,0,0.25), rgba(0,0,0,0.45)),
    url('fundo.jpg');
  background-repeat:no-repeat;
  background-position:center center;
  background-size:cover;
  background-color:#000;
}

    @keyframes bgPulse{
      0%,100%{opacity:0.8; transform:scale(1);}
      50%{opacity:1; transform:scale(1.03);}
    }

    .opening{
      position:fixed;
      inset:0;
      background:linear-gradient(180deg, rgba(0,0,0,0.95), rgba(15,8,0,0.95));
      z-index:9999;
      display:flex;
      align-items:center;
      justify-content:center;
      flex-direction:column;
      text-align:center;
      padding:20px;
      animation:openingOut 1.2s ease 5.8s forwards;
    }

    .opening::before,
    .opening::after{
      content:"";
      position:absolute;
      left:0;
      width:100%;
      height:16vh;
      background:#000;
      z-index:2;
    }

    .opening::before{top:0;}
    .opening::after{bottom:0;}

    .opening-small{
      letter-spacing:4px;
      text-transform:uppercase;
      font-size:0.9rem;
      color:#ffd56b;
      margin-bottom:16px;
      opacity:0;
      animation:fadeRise 1s ease .2s forwards;
    }

    .opening-title{
      font-size:clamp(2rem,6vw,4.8rem);
      font-weight:800;
      color:#fff3c4;
      text-shadow:0 0 18px rgba(255,215,0,0.20);
      opacity:0;
      transform:scale(0.9);
      animation:titlePop 1.3s ease 1s forwards;
      max-width:900px;
    }

    .opening-sub{
      margin-top:18px;
      max-width:720px;
      line-height:1.8;
      color:#f7e7bf;
      opacity:0;
      animation:fadeRise 1s ease 2.1s forwards;
    }

    .opening-flash{
      position:absolute;
      inset:0;
      background:white;
      opacity:0;
      pointer-events:none;
      animation:flashAnime .7s ease 4.6s forwards;
    }

    @keyframes fadeRise{
      from{opacity:0; transform:translateY(22px);}
      to{opacity:1; transform:translateY(0);}
    }

    @keyframes titlePop{
      0%{opacity:0; transform:scale(0.8);}
      70%{opacity:1; transform:scale(1.04);}
      100%{opacity:1; transform:scale(1);}
    }

    @keyframes flashAnime{
      0%{opacity:0;}
      35%{opacity:.95;}
      100%{opacity:0;}
    }

    @keyframes openingOut{
      to{
        opacity:0;
        visibility:hidden;
      }
    }

    .energy{
      position:fixed;
      inset:0;
      pointer-events:none;
      z-index:1;
      overflow:hidden;
    }

    .spark{
      position:absolute;
      width:6px;
      height:6px;
      border-radius:50%;
      background:#ffd700;
      box-shadow:0 0 12px rgba(255,215,0,0.9);
      animation:floatUp linear infinite;
      opacity:.65;
    }

    .spark.red{
      background:#ff7a00;
      box-shadow:0 0 12px rgba(255,122,0,0.9);
    }

    @keyframes floatUp{
      0%{
        transform:translateY(110vh) scale(.6);
        opacity:0;
      }
      10%{opacity:1;}
      100%{
        transform:translateY(-10vh) scale(1.15);
        opacity:0;
      }
    }

    .sea-decor{
      position:fixed;
      inset:0;
      pointer-events:none;
      z-index:1;
      overflow:hidden;
    }

    .ship,.map,.hat,.skull{
      position:absolute;
      opacity:.12;
      filter:drop-shadow(0 8px 20px rgba(0,0,0,.3));
      user-select:none;
    }

    .ship{
      left:4%;
      bottom:8%;
      font-size:72px;
      animation:sail 8s ease-in-out infinite;
    }

    .map{
      right:4%;
      top:14%;
      font-size:78px;
      animation:floatMap 7s ease-in-out infinite;
    }

    .hat{
      right:15%;
      bottom:10%;
      font-size:56px;
      animation:hatBounce 5s ease-in-out infinite;
    }

    .skull{
      left:10%;
      top:18%;
      font-size:46px;
      animation:skullFloat 6s ease-in-out infinite;
    }

    @keyframes sail{
      0%,100%{transform:translateX(0) translateY(0) rotate(0deg);}
      50%{transform:translateX(14px) translateY(-8px) rotate(-2deg);}
    }

    @keyframes floatMap{
      0%,100%{transform:translateY(0) rotate(0deg);}
      50%{transform:translateY(-12px) rotate(4deg);}
    }

    @keyframes hatBounce{
      0%,100%{transform:translateY(0) rotate(0deg);}
      50%{transform:translateY(-10px) rotate(-6deg);}
    }

    @keyframes skullFloat{
      0%,100%{transform:translateY(0);}
      50%{transform:translateY(-9px);}
    }

    .container{
      width:min(1100px, 92%);
      margin:0 auto;
      padding:24px 0 60px;
      position:relative;
      z-index:2;
    }

    header{
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:14px;
      flex-wrap:wrap;
      padding:8px 0 26px;
    }

    .logo{
      color:#ffd54f;
      font-weight:800;
      letter-spacing:1px;
      text-transform:uppercase;
      font-size:1rem;
      text-shadow:0 0 14px rgba(255,213,79,.25);
    }

    .badge{
      background:rgba(255,255,255,.10);
      border:1px solid rgba(255,255,255,.14);
      color:#fff0c2;
      padding:10px 16px;
      border-radius:999px;
      backdrop-filter:blur(10px);
      font-size:.92rem;
      font-weight:700;
      text-align:center;
    }

    .hero{
      min-height:88vh;
      display:flex;
      flex-direction:column;
      align-items:center;
      justify-content:center;
      text-align:center;
      gap:18px;
      padding:14px 0 34px;
    }

    .typing-wrap{
      min-height:88px;
      display:flex;
      justify-content:center;
      align-items:center;
      width:100%;
    }

    .typing{
      font-family:'Pacifico',cursive;
      font-size:clamp(2rem,7vw,5rem);
      color:#ffd54f;
      text-shadow:0 0 20px rgba(255,213,79,.35);
      border-right:4px solid #ffd54f;
      white-space:nowrap;
      overflow:hidden;
      width:0;
      animation:
        typing 3.2s steps(20,end) 5.9s forwards,
        blink .8s step-end infinite 5.9s;
      max-width:100%;
    }

    @keyframes typing{
      from{width:0;}
      to{width:12ch;}
    }

    @keyframes blink{
      50%{border-color:transparent;}
    }

    .subtitle{
      font-size:clamp(1.1rem,3vw,1.8rem);
      color:#fff3d1;
      font-weight:700;
      padding:0 10px;
    }

    .hero-line{
      color:#f5deb0;
      opacity:.95;
      letter-spacing:1px;
      font-size:1rem;
      padding:0 10px;
    }

    .hero p{
      max-width:760px;
      line-height:1.9;
      color:#f2e7cf;
      font-size:1.03rem;
      padding:0 10px;
    }

    .photo{
      margin:18px auto 8px;
      width:min(320px, 78vw);
      aspect-ratio:1/1;
      border-radius:50%;
      overflow:hidden;
      border:4px solid #ffd700;
      box-shadow:
        0 0 25px rgba(255,215,0,.55),
        0 0 60px rgba(255,122,0,.25);
      background:rgba(255,255,255,.08);
      position:relative;
      animation:photoAura 3s ease-in-out infinite;
    }

    .photo::before{
      content:"";
      position:absolute;
      inset:-10px;
      border-radius:50%;
      border:2px solid rgba(255,215,0,.25);
      animation:ringSpin 8s linear infinite;
    }

    @keyframes ringSpin{
      from{transform:rotate(0deg);}
      to{transform:rotate(360deg);}
    }

    @keyframes photoAura{
      0%,100%{transform:scale(1); box-shadow:0 0 25px rgba(255,215,0,.55), 0 0 60px rgba(255,122,0,.25);}
      50%{transform:scale(1.02); box-shadow:0 0 30px rgba(255,215,0,.75), 0 0 70px rgba(255,122,0,.35);}
    }

    .photo img{
      width:100%;
      height:100%;
      object-fit:cover;
      display:block;
    }

    .buttons{
      display:flex;
      justify-content:center;
      flex-wrap:wrap;
      gap:14px;
      margin-top:6px;
      width:100%;
    }

    .btn{
      border:none;
      padding:14px 22px;
      border-radius:14px;
      font-weight:700;
      cursor:pointer;
      transition:.3s ease;
      box-shadow:0 10px 25px rgba(0,0,0,.18);
      font-size:.97rem;
    }

    .btn-primary{
      background:linear-gradient(135deg,#ffd700,#ff7a00);
      color:#1b1200;
    }

    .btn-secondary{
      background:rgba(255,255,255,.10);
      color:white;
      border:1px solid rgba(255,255,255,.15);
      backdrop-filter:blur(10px);
    }

    .btn:hover{
      transform:translateY(-3px) scale(1.02);
    }

    .music-note{
      font-size:.92rem;
      color:#f3e6c0;
      margin-top:2px;
      text-align:center;
      padding:0 10px;
    }

    audio{
      width:min(100%, 340px);
    }

    section{
      padding:28px 0 36px;
    }

    .section-title{
      text-align:center;
      font-size:clamp(1.6rem, 4vw, 2rem);
      margin-bottom:10px;
      color:#ffd54f;
      text-shadow:0 4px 16px rgba(0,0,0,.25);
      padding:0 10px;
    }

    .section-subtitle{
      text-align:center;
      max-width:740px;
      margin:0 auto 28px;
      line-height:1.8;
      color:#f2e7cf;
      padding:0 10px;
    }

    .gallery{
      display:grid;
      grid-template-columns:repeat(4, minmax(0,1fr));
      gap:22px;
      justify-items:center;
      align-items:start;
    }

    .gallery-item{
      display:flex;
      flex-direction:column;
      align-items:center;
      gap:12px;
      position:relative;
      width:100%;
    }

    .gallery-photo{
      width:min(180px, 100%);
      aspect-ratio:1/1;
      border-radius:50%;
      overflow:hidden;
      border:3px solid rgba(255,255,255,0.3);
      box-shadow:0 10px 30px rgba(0,0,0,.5);
      flex-shrink:0;
      background:rgba(255,255,255,.06);
    }

    .gallery-photo img{
      width:100%;
      height:100%;
      object-fit:cover;
      object-position:center;
      display:block;
    }

    .gallery-caption{
      background:rgba(0,0,0,.6);
      padding:8px 14px;
      border-radius:999px;
      font-size:0.9rem;
      text-align:center;
      color:#fff;
      max-width:180px;
      width:100%;
    }

    .gallery-item::after{
      content:"⚓";
      position:absolute;
      bottom:42px;
      right:10px;
      font-size:24px;
      opacity:.14;
    }

    .message-box{
      max-width:860px;
      margin:0 auto;
      background:rgba(255,255,255,.08);
      border-radius:28px;
      padding:30px;
      border:1px solid rgba(255,255,255,.12);
      box-shadow:0 20px 50px rgba(0,0,0,.28);
      line-height:2;
      font-size:1.03rem;
      text-align:center;
      color:white;
      backdrop-filter:blur(8px);
    }

    .surprise-wrap{
      margin-top:24px;
    }

    .surprise{
      display:none;
      margin-top:20px;
      background:linear-gradient(135deg, rgba(255,255,255,.12), rgba(255,255,255,.08));
      border:2px solid rgba(255,255,255,.18);
      padding:22px;
      border-radius:22px;
      box-shadow:0 20px 50px rgba(0,0,0,.25);
      animation:appear .6s ease;
      color:#fff;
    }

    @keyframes appear{
      from{opacity:0; transform:translateY(15px);}
      to{opacity:1; transform:translateY(0);}
    }

    .gift-screen{
      position:fixed;
      inset:0;
      background:linear-gradient(135deg, rgba(11,22,48,.96), rgba(178,34,34,.92));
      display:none;
      align-items:center;
      justify-content:center;
      z-index:60;
      padding:20px;
    }

    .gift-box-wrap{
      text-align:center;
      color:white;
      width:min(900px,95%);
    }

    .gift-box{
      width:min(180px, 45vw);
      aspect-ratio:1/1;
      margin:0 auto 20px;
      background:linear-gradient(135deg,#d9a441,#b22222);
      border-radius:24px;
      position:relative;
      cursor:pointer;
      box-shadow:0 20px 50px rgba(0,0,0,.25);
      transition:transform .3s ease;
      animation:pulse 1.5s infinite;
    }

    .gift-box:hover{
      transform:scale(1.04) rotate(-2deg);
    }

    .gift-box::before{
      content:"";
      position:absolute;
      width:28px;
      height:100%;
      background:#fff3d1;
      left:50%;
      top:0;
      transform:translateX(-50%);
    }

    .gift-box::after{
      content:"🏴‍☠️";
      position:absolute;
      top:-24px;
      left:50%;
      transform:translateX(-50%);
      font-size:52px;
    }

    @keyframes pulse{
      0%{transform:scale(1);}
      50%{transform:scale(1.07);}
      100%{transform:scale(1);}
    }

    .gift-reveal{
      display:none;
      max-width:760px;
      background:rgba(0,0,0,.78);
      border:2px solid rgba(255,255,255,.25);
      padding:28px;
      border-radius:28px;
      backdrop-filter:blur(10px);
      box-shadow:0 20px 60px rgba(0,0,0,.4);
      animation:popReveal .8s ease;
      color:#fff;
      margin:0 auto;
    }

    .gift-reveal h2{
      font-size:clamp(2rem,5vw,4rem);
      margin-bottom:12px;
      color:#ffd54f;
      font-family:'Pacifico',cursive;
    }

    .gift-reveal p{
      font-size:1.08rem;
      line-height:1.9;
      font-weight:500;
    }

    .close-gift{
      margin-top:20px;
      border:none;
      background:white;
      color:#b22222;
      padding:12px 18px;
      border-radius:14px;
      font-weight:700;
      cursor:pointer;
    }

    @keyframes popReveal{
      from{opacity:0; transform:scale(.8) translateY(20px);}
      to{opacity:1; transform:scale(1) translateY(0);}
    }

    footer{
      text-align:center;
      padding:30px 0 42px;
      color:#f0e3bf;
      font-size:.95rem;
    }

    @media (max-width: 1024px){
      .gallery{
        grid-template-columns:repeat(2, minmax(0,1fr));
      }
    }

    @media (max-width: 768px){
      body{
        background-attachment:scroll;
      }

      .container{
        width:min(94%, 900px);
      }

      header{
        justify-content:center;
        text-align:center;
      }

      .hero{
        min-height:auto;
        padding-top:20px;
      }

      .typing{
        font-size:2.4rem;
      }

      .subtitle{
        font-size:1rem;
      }

      .hero-line{
        font-size:.92rem;
        line-height:1.7;
      }

      .hero p{
        font-size:.98rem;
      }

      .message-box{
        padding:22px 18px;
        font-size:.98rem;
      }

      .gift-reveal{
        padding:22px 18px;
      }

      .gift-reveal p{
        font-size:.98rem;
      }

      .ship{font-size:48px;}
      .map{font-size:52px;}
      .hat{font-size:40px;}
      .skull{font-size:34px;}
    }

    @media (max-width: 600px){
      .opening-small{
        font-size:.72rem;
        letter-spacing:2px;
      }

      .opening-title{
        font-size:1.8rem;
      }

      .opening-sub{
        font-size:.92rem;
        line-height:1.7;
      }

      .typing{
        font-size:2rem;
      }

      @keyframes typing{
        from{width:0;}
        to{width:10ch;}
      }

      .photo{
        width:min(230px, 72vw);
      }

      .buttons{
        flex-direction:column;
        align-items:center;
      }

      .btn{
        width:100%;
        max-width:320px;
      }

      .gallery{
        grid-template-columns:1fr;
        gap:20px;
      }

      .gallery-photo{
        width:140px;
      }

      .gallery-caption{
        font-size:0.82rem;
        max-width:160px;
      }

      .gift-reveal h2{
        font-size:1.8rem;
      }

      .gift-box{
        width:140px;
      }

      .ship{font-size:40px;}
      .map{font-size:45px;}
      .hat{font-size:38px;}
      .skull{font-size:32px;}
    }

    @media (max-width: 380px){
      .typing{
        font-size:1.7rem;
      }

      .subtitle{
        font-size:.95rem;
      }

      .hero-line{
        font-size:.84rem;
      }

      .section-title{
        font-size:1.4rem;
      }

      .message-box{
        border-radius:22px;
      }
    }
  </style>
</head>
<body>
  <div class="opening">
    <div class="opening-small">especial de aniversário</div>
    <div class="opening-title">Uma aventura está prestes a começar...</div>
    <div class="opening-sub">
      Em um mar cheio de sonhos, existe um tesouro raro e especial.<br>
      Hoje, essa aventura é toda para <strong>CLARINHA</strong>.
    </div>
    <div class="opening-flash"></div>
  </div>

  <div class="sea-decor">
    <div class="ship">⛵</div>
    <div class="map">🗺️</div>
    <div class="hat">👒</div>
    <div class="skull">☠️</div>
  </div>

  <div class="energy" id="energy"></div>

  <div class="gift-screen" id="giftScreen">
    <div class="gift-box-wrap">
      <div class="gift-box" onclick="abrirPresente()"></div>
      <h2 style="font-size:2rem; margin-bottom:10px;">Clique para abrir seu presente 🎁</h2>
      <p style="font-size:1.05rem; opacity:0.95;">Tem uma surpresa especial esperando por você.</p>

      <div class="gift-reveal" id="giftReveal">
        <h2>Maria Clara ✨</h2>
        <p>
          Você é meu tesouro. Em meio a tantas aventuras da vida, sua presença faz tudo ficar mais bonito,
          mais leve e mais especial. Que seu aniversário seja cheio de emoção, alegria, sonhos e momentos
          inesquecíveis, como uma verdadeira jornada de One Piece. ☠️⚓🌸
          <br><br>
          Que nunca faltem mapas para novos sonhos, um navio para seguir em frente e coragem para conquistar
          tudo o que seu coração deseja.
        </p>
        <button class="close-gift" onclick="fecharPresente()">Fechar presente</button>
      </div>
    </div>
  </div>

  <div class="container">
    <header>
      <div class="logo">☠️ One Piece Birthday</div>
      <div class="badge">⚓ Uma aventura especial</div>
    </header>

    <section class="hero">
      <div class="typing-wrap">
        <div class="typing">Clarinha</div>
      </div>

      <div class="subtitle">você é meu tesouro ☠️</div>
      <div class="hero-line">🗺️ Mapa do tesouro aberto • ⚓ Tripulação reunida • 👒 Chapéu de palha no visual</div>

      <div class="photo">
        <img src="foto-dela.jpg" alt="Foto dela">
      </div>

      <p>
        Hoje é o seu dia... e essa é uma pequena aventura feita especialmente pra você.
        Que sua vida seja cheia de conquistas, felicidade e momentos inesquecíveis.
      </p>

      <div class="buttons">
        <button class="btn btn-primary" onclick="mostrarTelaPresente()">Abrir presente 🎁</button>
        <button class="btn btn-secondary" onclick="tocarMusicaAnime()">Tocar música 🎵</button>
      </div>

      <div class="music-note">Música do seu cantor favorito.</div>

      <audio id="animeMusic" controls style="margin-top:10px;">
        <source src="musica-anime.mp3" type="audio/mpeg">
        Seu navegador não suporta áudio.
      </audio>
    </section>

    <section>
      <h2 class="section-title">Coisas favoritas da Clarinha</h2>
      <p class="section-subtitle">
        Luan Santana | Capivara | São Paulo | Lírios
      </p>

      <div class="gallery">
        <div class="gallery-item">
          <div class="gallery-photo">
            <img src="luan.jpg"> alt="Cantor favorito">
          </div>
          <div class="gallery-caption">Cantor favorito</div>
        </div>

        <div class="gallery-item">
          <div class="gallery-photo">
            <img src="animal.jpg"> alt="Animal favorito">
          </div>
          <div class="gallery-caption">Animal preferido</div>
        </div>

        <div class="gallery-item">
          <div class="gallery-photo">
            <img src="saopaulo.jpg" alt="Time do coração">
          </div>
          <div class="gallery-caption">Time do coração</div>
        </div>

        <div class="gallery-item">
          <div class="gallery-photo">
            <img src="lirios1.jpg" alt="Flor favorita">
          </div>
          <div class="gallery-caption">Flor favorita</div>
        </div>
      </div>
    </section>

    <section>
      <h2 class="section-title">Mensagem especial do Luizinho para você</h2>
      <p class="section-subtitle">Clarinha...</p>

      <div class="message-box">
        Feliz aniversário! Hoje é o seu dia, e eu queria te lembrar que você é um verdadeiro tesouro.
        Sua presença deixa tudo mais especial, mais bonito e muito mais inesquecível.
        <br><br>
        Que seu novo ciclo seja como uma grande aventura: cheio de conquistas, felicidade, coragem,
        pessoas especiais e sonhos se realizando a cada novo horizonte.

        <div class="surprise-wrap">
          <button class="btn btn-primary" onclick="mostrarSurpresa()">Clique para ver uma surpresa</button>
          <div class="surprise" id="surpresaBox">
            🎁 Surpresa! Você é meu tesouro, minha capitã especial dessa aventura.
            Que nunca faltem sonhos, sorrisos, conquistas e momentos inesquecíveis no seu caminho! ☠️⚓✨
          </div>
        </div>
      </div>
    </section>

    <footer>
      Feito com carinho por <strong>Luiz Fernando</strong> em uma aventura de aniversário digna de One Piece ☠️
    </footer>
  </div>

  <script>
    const energy = document.getElementById('energy');

    for (let i = 0; i < 55; i++) {
      const s = document.createElement('div');
      s.className = Math.random() > 0.5 ? 'spark' : 'spark red';
      s.style.left = Math.random() * 100 + 'vw';
      s.style.animationDuration = (2 + Math.random() * 4) + 's';
      s.style.animationDelay = Math.random() * 4 + 's';
      s.style.opacity = 0.4 + Math.random() * 0.5;
      energy.appendChild(s);
    }

    function mostrarSurpresa() {
      const box = document.getElementById('surpresaBox');
      box.style.display = box.style.display === 'block' ? 'none' : 'block';
    }

    function tocarMusicaAnime() {
      const audio = document.getElementById('animeMusic');
      audio.play();
    }

    function mostrarTelaPresente() {
      const screen = document.getElementById('giftScreen');
      const reveal = document.getElementById('giftReveal');
      reveal.style.display = 'none';
      screen.style.display = 'flex';
    }

    function abrirPresente() {
      const reveal = document.getElementById('giftReveal');
      reveal.style.display = 'block';
    }

    function fecharPresente() {
      const screen = document.getElementById('giftScreen');
      screen.style.display = 'none';
    }
  </script>
</body>
</html>
<script>
const telaCoracao = document.getElementById("telaCoracao");
const canvas = document.getElementById("heartCanvas");
const ctx = canvas.getContext("2d");

let particles = [];
let animationId;

function resizeCanvas() {
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;
}

window.addEventListener("resize", resizeCanvas);
resizeCanvas();

function heartPoint(t) {
  const x = 16 * Math.pow(Math.sin(t), 3);
  const y = -(13 * Math.cos(t) - 5 * Math.cos(2 * t) - 2 * Math.cos(3 * t) - Math.cos(4 * t));
  return { x, y };
}

function createParticles() {
  particles = [];
  const centerX = canvas.width / 2;
  const centerY = canvas.height / 2;

  for (let i = 0; i < 700; i++) {
    const t = Math.random() * Math.PI * 2;
    const p = heartPoint(t);

    particles.push({
      x: Math.random() * canvas.width,
      y: Math.random() * canvas.height,
      tx: centerX + p.x * 15,
      ty: centerY + p.y * 15,
      speed: 0.02 + Math.random() * 0.03
    });
  }
}

function animate() {
  ctx.clearRect(0,0,canvas.width,canvas.height);

  particles.forEach(p => {
    p.x += (p.tx - p.x) * p.speed;
    p.y += (p.ty - p.y) * p.speed;

    ctx.beginPath();
    ctx.arc(p.x, p.y, 2, 0, Math.PI*2);
    ctx.fillStyle = "white";
    ctx.fill();
  });

  animationId = requestAnimationFrame(animate);
}

function abrirTelaCoracao(){
  telaCoracao.style.display = "flex";
  createParticles();
  animate();
}

function fecharTelaCoracao(){
  telaCoracao.style.display = "none";
  cancelAnimationFrame(animationId);
}
</script>
