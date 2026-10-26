<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>RED ROOM.EXE — Audio Product</title>
<style>
:root{--red:#f12d36;--darkred:#780d18;--cream:#fff2d6;--blue:#173fb5;--black:#090909;--gray:#c7c7c7}
*{box-sizing:border-box}
body{margin:0;background:var(--black);color:#111;font-family:Tahoma,Verdana,sans-serif;font-size:13px;min-height:100vh;overflow-x:hidden}
.desktop{min-height:100vh;padding:24px 18px 52px;position:relative;background:
 repeating-linear-gradient(0deg,rgba(255,255,255,.025) 0px,rgba(255,255,255,.025) 1px,transparent 1px,transparent 4px),
 radial-gradient(ellipse at 50% 38%,#421015 0%,#18080a 43%,#050505 78%)}
.desktop:before{content:"";position:absolute;inset:0;pointer-events:none;opacity:.35;background:linear-gradient(135deg,transparent 40%,rgba(241,45,54,.25) 40.2%,transparent 41%),linear-gradient(25deg,transparent 68%,rgba(241,45,54,.17) 68.2%,transparent 69%)}
.icons{display:flex;gap:22px;margin:0 0 22px;position:relative;z-index:1}
.desktop-icon{width:70px;text-align:center;color:white;text-shadow:1px 1px #000;cursor:default}
.icon-art{height:44px;width:48px;margin:0 auto 5px;border:2px solid #ddd;background:#bdbdbd;box-shadow:inset -3px -3px #777,inset 3px 3px #fff;display:grid;place-items:center;font-size:25px}
.icon-label{font-size:11px}
.window{position:relative;z-index:1;width:min(850px,100%);margin:0 auto;background:var(--gray);border:2px solid #eee;box-shadow:3px 3px 0 #555,6px 6px 0 rgba(0,0,0,.65);padding:3px}
.titlebar{height:29px;background:linear-gradient(90deg,#102f98,#2865d9 70%,#15338e);color:white;font-weight:bold;display:flex;align-items:center;justify-content:space-between;padding:3px 5px 3px 9px;letter-spacing:.2px}
.window-buttons{display:flex;gap:3px}
.winbtn{width:19px;height:18px;background:#c7c7c7;border:2px outset white;color:#111;text-align:center;line-height:13px;font-weight:bold}
.content{padding:18px;background:#f5f3ec;border:2px inset #eee}
.topline{display:flex;align-items:flex-start;justify-content:space-between;gap:18px;border-bottom:2px solid #111;padding-bottom:15px}
.kicker{font-family:monospace;text-transform:uppercase;letter-spacing:2px;color:var(--darkred);font-weight:bold}
h1{font-size:clamp(28px,5vw,54px);line-height:.95;margin:8px 0;color:#b30d20;letter-spacing:-2px;text-shadow:2px 2px 0 #111}
.subtitle{font-size:12px;line-height:1.5;max-width:430px}
.sticker{background:var(--red);color:#fff;transform:rotate(4deg);padding:13px 11px;text-align:center;font-family:monospace;font-weight:bold;box-shadow:3px 3px 0 #111;min-width:95px}
.sticker span{display:block;font-size:24px}
.product{display:grid;grid-template-columns:minmax(180px, .85fr) minmax(0,1.4fr);gap:20px;padding:20px 0}
.cover{aspect-ratio:1/1;background:#b90e20;border:3px solid #111;box-shadow:5px 5px 0 #111;position:relative;overflow:hidden;display:flex;align-items:center;justify-content:center;color:#fff;text-align:center}
.cover:before{content:"";position:absolute;width:130%;height:38%;background:#111;transform:rotate(-42deg);top:28%;left:-15%;border-top:7px solid #f65a60;border-bottom:7px solid #f65a60}
.cover:after{content:"";position:absolute;inset:12px;border:1px solid rgba(255,255,255,.6)}
.covertext{z-index:1;font-family:monospace;font-size:clamp(26px,4vw,40px);font-weight:900;line-height:.85;transform:rotate(-7deg);text-shadow:3px 3px #111}
.covertext small{font-size:11px;display:block;letter-spacing:3px;margin-top:15px}
.details{display:flex;flex-direction:column;gap:10px}
.tag{display:inline-block;background:#111;color:#fff;padding:5px 8px;font-family:monospace;width:max-content}
.description{line-height:1.6;margin:2px 0 5px}
.price-row{display:flex;align-items:center;gap:12px;flex-wrap:wrap;margin-top:auto}
.price{font-size:25px;font-weight:bold;color:#b30d20}
.buy{background:var(--red);color:white;border:2px outset #ff777d;padding:10px 15px;font-weight:bold;cursor:pointer;box-shadow:2px 2px #111}
.buy:active{border-style:inset;transform:translate(1px,1px)}
.track-area{border-top:2px solid #111;padding-top:15px}
.section-title{font-size:17px;margin:0 0 10px;font-weight:bold}
.track-head{display:flex;justify-content:space-between;align-items:center;gap:12px;flex-wrap:wrap}
.upload{font-size:11px;border:1px solid #777;background:#ddd;padding:7px;max-width:100%}
.hint{font-size:11px;color:#555;line-height:1.45;margin:8px 0 12px}
.tracklist{display:grid;grid-template-columns:1fr 1fr;gap:5px 8px}
.track{display:flex;align-items:center;gap:8px;padding:7px;background:#e0dfd8;border:1px solid #aaa;min-width:0;cursor:pointer}
.track:hover,.track.active{background:#f6c7c9;border-color:#b30d20}
.num{font-family:monospace;font-weight:bold;color:#b30d20;min-width:19px}
.track-name{overflow:hidden;text-overflow:ellipsis;white-space:nowrap;flex:1}
.track-status{font-family:monospace;font-size:10px;color:#555}
.player{margin-top:12px;background:#111;color:#fff;padding:12px;display:grid;grid-template-columns:1fr auto;gap:10px;align-items:center}
.nowplaying{font-family:monospace;min-width:0}
.nowplaying small{display:block;color:#ff6c73;margin-bottom:4px}
.now-title{overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
.controls{display:flex;gap:5px}
.controls button{background:#d6d6d6;border:2px outset #fff;padding:7px 10px;cursor:pointer;font-weight:bold}
audio{width:100%;height:30px;grid-column:1/-1}
.footer{display:flex;justify-content:space-between;gap:12px;flex-wrap:wrap;border-top:1px solid #aaa;padding-top:12px;margin-top:15px;font-family:monospace;font-size:10px;color:#555}
.taskbar{position:fixed;z-index:5;bottom:0;left:0;right:0;height:40px;background:#aaa;border-top:2px solid white;display:flex;align-items:center;padding:4px 8px;gap:7px;box-shadow:0 -2px 0 #555}
.start{border:2px outset #eee;background:#c7c7c7;font-weight:bold;padding:6px 12px}
.task-item{background:#c7c7c7;border:2px inset #eee;padding:6px 12px;min-width:110px}
.clock{margin-left:auto;background:#c7c7c7;border:2px inset #eee;padding:6px 10px;font-family:monospace}
@media(max-width:600px){.desktop{padding:15px 9px 55px}.content{padding:12px}.topline{gap:8px}.sticker{min-width:70px;padding:9px 6px}.product{grid-template-columns:1fr;gap:15px}.cover{max-width:310px;width:100%;margin:auto}.tracklist{grid-template-columns:1fr}.player{grid-template-columns:1fr}.controls{grid-row:2}.task-item:nth-of-type(3){display:none}.window{width:100%}}
</style>
</head>
<body>
<div class="desktop">
  <div class="icons">
    <div class="desktop-icon"><div class="icon-art">▰</div><div class="icon-label">RED ROOM</div></div>
    <div class="desktop-icon"><div class="icon-art">♬</div><div class="icon-label">Audio Disc</div></div>
    <div class="desktop-icon"><div class="icon-art">▤</div><div class="icon-label">Read_Me.txt</div></div>
  </div>
  <main class="window">
    <div class="titlebar"><span>RED_ROOM.EXE — PRODUCT_PAGE</span><div class="window-buttons"><div class="winbtn">_</div><div class="winbtn">□</div><div class="winbtn">×</div></div></div>
    <div class="content">
      <div class="topline">
        <div><div class="kicker">Independent audio object / No. 001</div><h1>RED<br>ROOM.EXE</h1><div class="subtitle">Diez piezas para entrar, perder la señal y no salir siendo exactamente la misma persona.</div></div>
        <div class="sticker">LIMITED<br>EDITION<span>10</span>TRACKS</div>
      </div>
      <section class="product">
        <div class="cover" aria-label="Portada gráfica roja del álbum"><div class="covertext">RED<br>ROOM<small>PLEASE STAY OFFLINE</small></div></div>
        <div class="details">
          <span class="tag">PRODUCT_001 / DIGITAL ALBUM</span>
          <h2 style="margin:0;font-size:22px">The Red Room Sessions</h2>
          <p class="description">Un pequeño objeto digital con diez cortes, tensión analógica y una interfaz que parece rescatada de un ordenador olvidado. Hecho para escucharse de principio a fin, con las luces bajas.</p>
          <div><strong>Formato:</strong> descarga digital · 10 tracks</div>
          <div><strong>Género:</strong> electronic / alternative / dark pop</div>
          <div class="price-row"><div class="price">€10.00</div><button class="buy" id="buyBtn">GET THE ALBUM ↗</button></div>
        </div>
      </section>
      <section class="track-area">
        <div class="track-head"><h2 class="section-title">AUDIO PLAYER // TRACKLIST</h2><input class="upload" type="file" id="audioFiles" accept="audio/*" multiple aria-label="Cargar archivos de audio"></div>
        <p class="hint">Carga hasta 10 archivos de audio desde tu dispositivo. Se asignarán por orden a las pistas; no se suben a ningún servidor. Puedes usar tus propios títulos y archivos.</p>
        <div class="tracklist" id="tracklist"></div>
        <div class="player">
          <div class="nowplaying"><small>NOW PLAYING:</small><div class="now-title" id="nowTitle">01 — Boot Sequence</div></div>
          <div class="controls"><button id="prev" aria-label="Pista anterior">◀◀</button><button id="play" aria-label="Reproducir o pausar">▶ / II</button><button id="next" aria-label="Pista siguiente">▶▶</button></div>
          <audio id="audio" controls preload="metadata"></audio>
        </div>
      </section>
      <div class="footer"><span>© RED ROOM AUDIO LAB — 2026</span><span>BEST VIEWED AFTER MIDNIGHT</span><span>STATUS: <b style="color:#b30d20">ONLINE</b></span></div>
    </div>
  </main>
</div>
<div class="taskbar"><div class="start">▣ Start</div><div class="task-item">RED_ROOM.EXE</div><div class="task-item">Audio Player</div><div class="clock" id="clock">00:00 AM</div></div>
<script>
const titles = ["Boot Sequence","Velvet Static","Red Signal","Plastic Flowers","Room Tone","Dead Pixel Heart","Afterimage","No Exit Music","Soft Crash","Shutdown / Dawn"];
const files = Array(10).fill(null);
let current = 0;
const list = document.getElementById('tracklist');
const audio = document.getElementById('audio');
const nowTitle = document.getElementById('nowTitle');
function render(){
  list.innerHTML = '';
  titles.forEach((title,i)=>{
    const row=document.createElement('div');
    row.className='track'+(i===current?' active':'');
    row.innerHTML=`<span class="num">${String(i+1).padStart(2,'0')}</span><span class="track-name"></span><span class="track-status">${files[i]?'READY':'EMPTY'}</span>`;
    row.querySelector('.track-name').textContent=title;
    row.addEventListener('click',()=>selectTrack(i,true));
    list.appendChild(row);
  });
  nowTitle.textContent=String(current+1).padStart(2,'0')+' — '+titles[current];
}
function selectTrack(i,autoplay=false){
  current=(i+10)%10;
  if(files[current]){audio.src=files[current].url;if(autoplay) audio.play().catch(()=>{});}
  else {audio.removeAttribute('src');audio.load();}
  render();
}
document.getElementById('audioFiles').addEventListener('change',e=>{
  files.forEach(f=>{if(f&&f.url)URL.revokeObjectURL(f.url)});
  files.fill(null);
  [...e.target.files].slice(0,10).forEach((file,i)=>{files[i]={file,url:URL.createObjectURL(file)};titles[i]=file.name.replace(/\.[^.]+$/,'');});
  selectTrack(0,false);
});
document.getElementById('prev').addEventListener('click',()=>selectTrack(current-1,true));
document.getElementById('next').addEventListener('click',()=>selectTrack(current+1,true));
document.getElementById('play').addEventListener('click',()=>{if(!audio.src){alert('Primero carga tus archivos de audio con el botón de arriba.');return;}if(audio.paused)audio.play();else audio.pause();});
audio.addEventListener('ended',()=>{if(current<9&&files[current+1])selectTrack(current+1,true);});
document.getElementById('buyBtn').addEventListener('click',()=>alert('Botón de muestra: conecta aquí tu tienda o enlace de compra.'));
function tick(){const d=new Date();let h=d.getHours(),m=String(d.getMinutes()).padStart(2,'0');const ap=h>=12?'PM':'AM';h=h%12||12;document.getElementById('clock').textContent=`${h}:${m} ${ap}`;}
tick();setInterval(tick,30000);render();
</script>
</body>
</html>
