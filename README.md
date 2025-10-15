<!doctype html>
<html lang="vi">
<head>
<meta charset="utf-8" />
<meta name="viewport" content="width=device-width,initial-scale=1" />
<title>hello mọi người - Trang bí mật</title>
<style>
  :root{--bg:#fff9fb;--card:#ffffff;--accent:#ff4d7a;--muted:#666;}
  html,body{height:100%;margin:0;font-family:Inter, "Segoe UI", Roboto, Arial, sans-serif;background:linear-gradient(135deg,#fff2f8 0%,#fffef9 100%);color:#222;}
  .wrap{min-height:100vh;display:flex;align-items:center;justify-content:center;padding:24px;box-sizing:border-box;}
  .card{width:100%;max-width:980px;background:var(--card);border-radius:16px;padding:26px;box-shadow:0 18px 50px rgba(17,24,39,0.08);display:grid;grid-template-columns:1fr 360px;gap:20px;align-items:center;}
  @media(max-width:880px){.card{grid-template-columns:1fr;}.right{order:-1}}
  h1{margin:0;font-size:30px;color:var(--accent);}
  p.lead{margin:12px 0 18px;font-size:15px;color:#333;line-height:1.6;}
  .btn{display:inline-block;padding:10px 16px;border-radius:10px;background:linear-gradient(90deg,var(--accent),#ff7aa6);color:white;text-decoration:none;font-weight:700;}
  .mini{font-size:13px;color:var(--muted)}
  .cake{display:flex;align-items:center;justify-content:center;margin-top:12px}
  .cake .plate{width:220px;height:120px;background:linear-gradient(180deg,#fff0f6,#ffe6ef);border-radius:120px 120px 28px 28px;position:relative;box-shadow:inset 0 -6px 12px rgba(0,0,0,0.04);}
  .cake .layer{position:absolute;left:50%;transform:translateX(-50%);width:160px;height:64px;background:#fff;border-radius:14px;top:10px;box-shadow:0 6px 16px rgba(0,0,0,0.06);display:flex;align-items:center;justify-content:center;}
  .candle{position:absolute;top:-18px;left:50%;transform:translateX(-50%);width:8px;height:34px;background:#ffb3c7;border-radius:4px;}
  .flame{position:absolute;width:12px;height:18px;top:-26px;left:50%;transform:translateX(-50%);background:radial-gradient(circle at 50% 30%,#fff1a8 0%, #ffd166 30%, #ff8aa6 70%);border-radius:60%;filter:drop-shadow(0 4px 6px rgba(255,130,150,0.18));animation:flicker 1s infinite;}
  @keyframes flicker{0%{transform:translateX(-50%) scale(1);}50%{transform:translateX(-50%) scale(1.08);}100%{transform:translateX(-50%) scale(1);}}
  .right{display:flex;flex-direction:column;align-items:center;justify-content:center;padding:8px;}
  .balloon{width:72px;height:96px;border-radius:50% 50% 45% 45%;display:inline-block;margin:6px;box-shadow:inset -6px -10px 18px rgba(0,0,0,0.06);}
  .message{font-size:15px;line-height:1.6;color:#333;margin-top:10px;background:linear-gradient(180deg,#fff,#fff0f6);padding:12px;border-radius:12px;}
  .signature{margin-top:14px;font-weight:800;color:var(--accent);}
  .overlay{position:fixed;inset:0;background:linear-gradient(180deg,rgba(0,0,0,0.45),rgba(0,0,0,0.55));display:flex;align-items:center;justify-content:center;z-index:9999;backdrop-filter:blur(3px);}
  .pwbox{background:white;padding:22px;border-radius:12px;min-width:320px;text-align:center;box-shadow:0 20px 60px rgba(2,6,23,0.4);}
  .pwbox h2{margin:0 0 10px;font-size:18px;color:#222}
  .pwbox input{width:100%;padding:12px;border:1px solid #eee;border-radius:10px;margin-bottom:12px;font-size:15px;box-sizing:border-box;}
  .hint{font-size:13px;color:#777;margin-top:6px;}
  footer.note{margin-top:18px;text-align:center;font-size:13px;color:#666;}
  .confetti-piece{position:absolute;width:10px;height:20px;opacity:0.95;transform-origin:center;animation:fall 6s linear infinite;}
  @keyframes fall{0%{transform:translateY(-20vh) rotate(0deg);opacity:1;}100%{transform:translateY(120vh) rotate(540deg);opacity:0.9;}}
</style>
</head>
<body>
<div class="wrap">
  <div class="card" id="card">
    <div class="left">
      <h1>❤ Hello, <span id="recipientNameDisplay">Em yêu</span>!</h1>
      <p class="lead">hi vọng mọi người zui zui.</p>
      <p><a class="btn" id="toggleMsg">Mở lời chúc </a></p>

      <div class="cake" aria-hidden="true">
        <div class="plate" role="img" aria-label="8==D----">
          <div class="layer"></div>
          <div class="candle"></div>
          <div class="flame"></div>
        </div>
      </div>

      <div class="message" id="message" style="display:none;">
        <p>địt mẹ chúng mày,</p>
        
        <p class="signature">Nhất Nhất — <span id="senderNameDisplay">[Tên anh]</span> ♥</p>
      </div>
    </div>

    <div class="right" aria-hidden="true">
      <div style="display:flex;align-items:center;justify-content:center;flex-wrap:wrap;">
        <div class="balloon" style="background:linear-gradient(180deg,#ff9db5,#ff7598);"></div>
        <div class="balloon" style="background:linear-gradient(180deg,#ffd1a9,#ffb86b);"></div>
        <div class="balloon" style="background:linear-gradient(180deg,#c7f5ff,#8bd6ff);"></div>
      </div>
      <div style="text-align:center;margin-top:10px;">
        <div style="font-weight:700;color:var(--accent);font-size:18px;">8==D----</div>
        <div class="mini">haha, mấy thàng lon</div>
      </div>
    </div>
  </div>
</div>


<div class="overlay" id="overlay">
  <div class="pwbox" role="dialog" aria-modal="true" aria-labelledby="pwtitle">
    <h2 id="pwtitle">Mở trang bằng mật khẩu</h2>
    <input id="pw" type="password" placeholder="Nhập mật khẩu..." aria-label="password input" />
    <button class="btn" id="btnOpen" style="width:100%;">Mở</button>
    <div class="hint">Trang này đã được thiết kế bởi người rất yêu quí bạn. Nếu đây là bạn, nhập mật khẩu được gửi cho bạn để xem lời chúc nhé.</div>
    <footer class="note">Bạn có thể sửa mật khẩu và tên hiển thị bằng cách mở file trong trình soạn thảo.</footer>
  </div>
</div>

<script>

const PASSWORD = '151006';

const RECIPIENT_NAME = 'mọi người';
const SENDER_NAME = 'đẹp trai vcl';


document.getElementById('recipientNameDisplay').textContent = RECIPIENT_NAME;
document.getElementById('senderNameDisplay').textContent = SENDER_NAME;

(function makeConfetti(){
  const colors = ['#ff7aa6','#ffd166','#8bd6ff','#b6ffb3','#ffd6e4'];
  for(let i=0;i<22;i++){
    const d = document.createElement('div');
    d.className = 'confetti-piece';
    d.style.left = Math.random()*100 + '%';
    d.style.background = colors[i % colors.length];
    d.style.top = (-Math.random()*20)+'vh';
    d.style.width = (6+Math.random()*12)+'px';
    d.style.height = (10+Math.random()*22)+'px';
    d.style.transform = 'rotate('+(Math.random()*360)+'deg)';
    d.style.animationDelay = (Math.random()*3)+'s';
    d.style.opacity = 0.95;
    document.body.appendChild(d);
  }
})();

const overlay = document.getElementById('overlay');
const input = document.getElementById('pw');
const btn = document.getElementById('btnOpen');
const msg = document.getElementById('message');
const toggle = document.getElementById('toggleMsg');
const card = document.getElementById('card');

function unlock(){
  const v = input.value || '';
  if(v === PASSWORD){
    overlay.style.display = 'none';
    msg.style.display = 'none';
    card.style.transform = 'scale(0.99)';
    setTimeout(()=>{ card.style.transform = 'scale(1)'; },80);
  } else {
    overlay.querySelector('.pwbox').animate([
      { transform: 'translateX(-6px)'},
      { transform: 'translateX(6px)'},
      { transform: 'translateX(-4px)'},
      { transform: 'translateX(0)'},
    ],{duration:300});
    input.value = '';
    input.placeholder = 'Mật khẩu không đúng — thử lại';
  }
}

btn.addEventListener('click', unlock);
input.addEventListener('keydown', function(e){ if(e.key === 'Enter') unlock(); });
toggle.addEventListener('click', function(){
  if(msg.style.display === 'block'){ msg.style.display = 'none'; toggle.textContent = 'Đóng lời chúc'; }
  else { msg.style.display = 'block'; toggle.textContent = 'Đóng lời chúc'; }
});


input.focus();
</script>
</body>
</html>
