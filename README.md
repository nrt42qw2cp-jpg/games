<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, user-scalable=no">
<title>ألعاب دحوم</title>
<style>
:root{--bg:#10303a;--card:#16424f;--line:#1d4a57;--mint:#7fe0b0;--text:#e6f4ef;--dim:#9dc3bb;--gold:#f5c04a;--coral:#ff7a59}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{margin:0;min-height:100%;background:var(--bg);color:var(--text);font-family:system-ui,"Segoe UI",Tahoma,sans-serif}
button{font:inherit;color:inherit;cursor:pointer;border:0}
button:focus-visible{outline:3px solid #fff}
.wrap{max-width:560px;margin:0 auto;padding:16px}
.hidden{display:none!important}
.acct{display:flex;align-items:center;gap:12px;background:var(--card);border:1px solid var(--line);border-radius:18px;padding:14px 16px}
.av{width:46px;height:46px;flex:none;border-radius:50%;background:var(--mint);color:var(--bg);display:grid;place-items:center;font-weight:800;font-size:22px}
button.av:active{transform:scale(.92)}
.acct h1{margin:0;font-size:20px}
.prime{margin-inline-start:auto;background:var(--gold);color:#3a2a00;font-weight:800;font-size:15px;padding:6px 14px;border-radius:99px}
h2{font-size:17px;margin:22px 4px 10px;color:var(--dim);font-weight:600}
.grid{display:grid;grid-template-columns:1fr 1fr;gap:12px}
.game{background:var(--card);border:1px solid var(--line);border-radius:18px;padding:18px 10px;text-align:center;font-size:17px;font-weight:700;display:flex;flex-direction:column;gap:8px;align-items:center}
.game i{font-style:normal;font-size:40px}
.game small{font-weight:400;color:var(--dim);font-size:13px}
.game:active{transform:scale(.97)}
.top{display:flex;align-items:center;gap:12px;margin-bottom:14px}
.back{width:46px;height:46px;border-radius:14px;background:var(--card);border:1px solid var(--line);font-size:24px}
.top h1{margin:0;font-size:20px}
.stage{display:flex;flex-direction:column;align-items:center;gap:12px;touch-action:none;user-select:none}
.info{font-size:18px;min-height:26px;text-align:center}
.btn{background:var(--mint);color:var(--bg);font-weight:800;border-radius:12px;padding:10px 26px}
.btn.red{background:var(--coral);color:#fff}
.btn.ghost{background:var(--line);color:var(--text)}
canvas{width:min(92vw,52vh,420px);aspect-ratio:1;background:#0b2229;border-radius:14px;border:2px solid var(--line)}
.pad{display:grid;grid-template-columns:repeat(3,64px);grid-template-rows:repeat(2,54px);gap:8px;direction:ltr}
.pad button{background:var(--line);border-radius:12px;font-size:22px}
.pad .u{grid-column:2}.pad .l{grid-row:2;grid-column:1}.pad .d{grid-row:2;grid-column:2}.pad .r{grid-row:2;grid-column:3}
.row{display:flex;gap:10px;direction:ltr}.row button{width:90px;height:54px;background:var(--line);border-radius:12px;font-size:22px}
.xo{display:grid;grid-template-columns:repeat(3,1fr);gap:8px;width:min(86vw,320px)}
.xo button{aspect-ratio:1;background:var(--card);border:1px solid var(--line);border-radius:14px;font-size:44px;font-weight:800}
.mem{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;width:min(92vw,360px)}
.mem button{aspect-ratio:1;background:var(--line);border-radius:14px;font-size:34px}
.mem button.on{background:var(--card)}.mem button.ok{background:#1f6a52}
.holes{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;width:min(86vw,320px)}
.holes button{aspect-ratio:1;background:var(--line);border-radius:50%;font-size:40px}
.opts{display:grid;grid-template-columns:1fr 1fr;gap:10px;width:min(90vw,340px)}
.opts button{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:16px;font-size:24px;font-weight:700}
.big{font-size:34px;font-weight:800;min-height:46px}
.rps{display:flex;gap:12px}.rps button{width:92px;height:92px;font-size:46px;background:var(--card);border:1px solid var(--line);border-radius:18px}
.rbox{width:min(86vw,320px);height:240px;border-radius:18px;font-size:22px;font-weight:800;background:var(--line)}
.tap{width:190px;height:190px;border-radius:50%;font-size:60px;background:var(--card);border:3px solid var(--mint)}
.tap:active{transform:scale(.94)}
.dice{font-size:96px;line-height:1;min-height:100px}
.g2048{display:grid;grid-template-columns:repeat(4,1fr);gap:8px;width:min(88vw,340px);background:#0b2229;padding:8px;border-radius:14px}
.g2048 div{aspect-ratio:1;border-radius:10px;display:grid;place-items:center;font-weight:800;font-size:24px;background:var(--line)}
input{font:inherit;font-size:22px;width:140px;text-align:center;padding:10px;border-radius:12px;border:2px solid var(--line);background:#0b2229;color:var(--text)}
.panel{background:var(--card);border:1px solid var(--line);border-radius:18px;padding:16px;margin-bottom:14px}
.panel h3{margin:0 0 10px;font-size:17px}
.kv{display:flex;justify-content:space-between;padding:6px 0;color:var(--dim)}.kv b{color:var(--text)}
.dev{display:flex;align-items:center;gap:12px}
.dev .ic{font-size:30px}.dev .nm{font-weight:700}.dev small{display:block;color:var(--dim)}
.dot{margin-inline-start:auto;display:flex;align-items:center;gap:8px;color:#7ff0a0;font-size:14px}
.dot::before{content:"";width:12px;height:12px;border-radius:50%;background:#2fd36b;box-shadow:0 0 8px #2fd36b}
.msg{color:var(--mint);min-height:22px;margin-top:8px;text-align:center}
.center{text-align:center;padding-top:20vh}
.center h1{margin:0 0 20px}
.plans{display:flex;flex-direction:column;gap:12px}
.plan{text-align:start;background:var(--card);border:2px solid var(--line);border-radius:18px;padding:14px 16px;width:100%}
.plan.sel{border-color:var(--mint)}
.plan .hd{display:flex;align-items:center;gap:10px;font-weight:800;font-size:18px}
.plan .pr{margin-inline-start:auto;font-size:16px}
.plan .cur{font-size:12px;font-weight:600;background:var(--line);padding:2px 10px;border-radius:99px;color:var(--dim)}
.plan ul{margin:10px 0 0;padding:0;list-style:none;color:var(--dim);font-size:14px;line-height:1.9}
.plan li::before{content:"✓ ";color:var(--mint)}
.plan.pc .hd{color:var(--gold)}
.methods{display:flex;gap:8px}
.methods button{flex:1;background:var(--line);border-radius:12px;padding:12px 4px;font-weight:700;border:2px solid transparent}
.methods button.sel{border-color:var(--mint)}
.lock{opacity:.55}
.note{color:var(--dim);font-size:13px;text-align:center;margin-top:10px}
</style>
</head>
<body>
<div class="wrap">

<section id="home">
  <div class="acct">
    <button class="av" id="avatar" aria-label="حسابي">د</button>
    <h1>مرحباً دحوم</h1>
    <span class="prime" id="badge">برايم</span>
  </div>
  <h2>اختر لعبتك</h2>
  <div class="grid" id="list"></div>
</section>

<section id="play" class="hidden">
  <div class="top"><button class="back" id="back" aria-label="رجوع">→</button><h1 id="title"></h1></div>
  <div class="stage" id="stage"></div>
</section>

<section id="acct" class="hidden">
  <div class="top"><button class="back" id="back2" aria-label="رجوع">→</button><h1>حسابي</h1></div>
  <div class="panel">
    <div class="dev"><div class="av">د</div><div><div class="nm">دحوم</div><small id="mbr">عضو برايم</small></div><span class="prime" id="badge2">برايم</span></div>
  </div>
  <div class="panel">
    <h3>الاشتراك</h3>
    <div class="kv"><span>الباقة</span><b id="pn">برايم</b></div>
    <div class="kv"><span>الحالة</span><b id="st">فعّال</b></div>
    <div class="kv"><span>ينتهي في</span><b id="ex"></b></div>
    <div class="kv"><span>المتبقي</span><b id="left"></b></div>
    <div style="text-align:center;margin-top:10px"><button class="btn" id="renew">تجديد الاشتراك</button></div>
    <div class="msg" id="rmsg"></div>
  </div>
  <div class="panel">
    <h3>الأجهزة المسجلة بحسابك</h3>
    <div class="dev"><div class="ic">📱</div><div><div class="nm">iPhone 12</div><small>هذا الجهاز</small></div><span class="dot">متصل</span></div>
  </div>
  <button class="btn red" id="logout" style="width:100%">تسجيل خروج</button>
</section>

<section id="pay" class="hidden">
  <div class="top"><button class="back" id="back3" aria-label="رجوع">→</button><h1>الدفع</h1></div>
  <div class="plans" id="plans"></div>
  <div id="paybox"><h2>طريقة الدفع</h2><div class="methods" id="methods"></div></div>
  <button class="btn" id="payBtn" style="width:100%;margin-top:16px"></button>
  <div class="msg" id="pmsg"></div>
  <div class="note">صفحة تجريبية: لا يتم سحب أي مبلغ.</div>
</section>

<section id="out" class="hidden center">
  <h1>تم تسجيل الخروج</h1>
  <button class="btn" id="login">تسجيل الدخول</button>
</section>

</div>
<script>
const $=s=>document.querySelector(s),stage=$('#stage');
let cleanup=null;
const el=h=>{const d=document.createElement('div');d.innerHTML=h.trim();return d.firstChild};
const ld=(k,d)=>{try{return +localStorage.getItem(k)||d}catch(e){return d}};
const sv=(k,v)=>{try{localStorage.setItem(k,v)}catch(e){}};
function view(id){['home','play','acct','pay','out'].forEach(x=>$('#'+x).classList.toggle('hidden',x!=id));scrollTo(0,0)}

const games=[
 {name:'الثعبان',icon:'🐍',desc:'كُل وكبّر',run:snake},
 {name:'إكس أو',icon:'❌',desc:'ضد الكمبيوتر',run:xo},
 {name:'الذاكرة',icon:'🧠',desc:'اقلب وطابق',run:mem},
 {name:'خمّن الرقم',icon:'🔢',desc:'من 1 إلى 100',run:guess},
 {name:'حجر ورقة مقص',icon:'✌️',desc:'ضد الكمبيوتر',run:rps},
 {name:'اضرب الخلد',icon:'🐹',desc:'٣٠ ثانية',run:whack},
 {name:'حساب سريع',icon:'➕',desc:'٣٠ ثانية',run:math},
 {name:'2048',icon:'🧩',desc:'اجمع الأرقام',run:g2048},
 {name:'تفادى',icon:'🚧',desc:'اهرب من المكعبات',run:dodge},
 {name:'سرعة الرد',icon:'⚡',desc:'اختبر ردة فعلك',run:react},
 {name:'سرعة النقر',icon:'👆',desc:'١٠ ثوانٍ',run:taps},
 {name:'النرد',icon:'🎲',desc:'ارمِ النرد',run:dice}
];
let plan=(()=>{try{return localStorage.getItem('plan')||'prime'}catch(e){return 'prime'}})();
const PLANS={free:{n:'العادية',p:0,max:4},plus:{n:'بلس',p:6,max:99},prime:{n:'برايم',p:12,max:99}};
function renderGames(){const L=$('#list');L.innerHTML='';
 games.forEach((g,i)=>{const lk=i>=PLANS[plan].max,b=document.createElement('button');b.className='game'+(lk?' lock':'');
  b.innerHTML=`<i>${lk?'🔒':g.icon}</i>${g.name}<small>${lk?'تحتاج بلس أو برايم':g.desc}</small>`;
  b.onclick=()=>{if(lk){openPay();return}view('play');$('#title').textContent=g.name;stage.innerHTML='';cleanup=g.run(stage)||null};L.append(b)})}
$('#back').onclick=()=>{if(cleanup)cleanup();cleanup=null;stage.innerHTML='';view('home')};

/* ---------- الحساب ---------- */
const DAY=864e5;
let exp=ld('exp',Date.now()+23*DAY);
function paint(){const f=plan=='free',n=Math.ceil((exp-Date.now())/DAY);
 $('#ex').textContent=f?'—':new Date(exp).toLocaleDateString('ar');
 $('#left').textContent=f?'—':(n>0?n+' يوم':'منتهي');
 $('#st').textContent=f?'مجانية':(n>0?'فعّال':'منتهي');
 $('#pn').textContent=PLANS[plan].n;$('#badge').textContent=$('#badge2').textContent=PLANS[plan].n;
 $('#mbr').textContent=f?'باقة عادية':'عضو '+PLANS[plan].n}
function applyPlan(){paint();renderGames()}
$('#avatar').onclick=()=>{paint();$('#rmsg').textContent='';view('acct')};
$('#back2').onclick=()=>view('home');
$('#renew').onclick=()=>openPay();
$('#back3').onclick=()=>{paint();view('acct')};

const FEAT={
 free:['٤ ألعاب فقط','اللعب أوف لاين','سرعة عادية'],
 plus:['١٢٠ لعبة','أون لاين وأوف لاين','سرعة سريعة'],
 prime:['٥٦٠ لعبة','أون لاين ومع أصدقاء وأوف لاين','سرعة نارية سريعة']};
const PRICE={free:'مجانية',plus:'٦ ريال / الشهر',prime:'١٢ ريال / الشهر'};
const METHODS=['مدى','بطاقة ائتمانية','Apple Pay'];
let selPlan,selM=0,paying=false;
function openPay(){selPlan=plan;$('#pmsg').textContent='';drawPay();view('pay')}
function drawPay(){
 const box=$('#plans');box.innerHTML='';
 ['free','plus','prime'].forEach(k=>{const d=document.createElement('button');d.className='plan'+(k=='prime'?' pc':'')+(k==selPlan?' sel':'');
  d.innerHTML=`<div class="hd">${PLANS[k].n}${k==plan?'<span class="cur">باقتك الحالية</span>':''}<span class="pr">${PRICE[k]}</span></div><ul>${FEAT[k].map(x=>`<li>${x}</li>`).join('')}</ul>`;
  d.onclick=()=>{if(paying)return;selPlan=k;drawPay()};box.append(d)});
 $('#paybox').classList.toggle('hidden',selPlan=='free');
 const m=$('#methods');m.innerHTML='';METHODS.forEach((t,i)=>{const b=document.createElement('button');b.textContent=t;b.className=i==selM?'sel':'';b.onclick=()=>{selM=i;drawPay()};m.append(b)});
 const pb=$('#payBtn'),P=PLANS[selPlan];
 pb.disabled=selPlan=='free'&&plan=='free';
 pb.textContent=selPlan=='free'?(plan=='free'?'هذه باقتك الحالية':'التحويل إلى الباقة العادية'):(selPlan==plan?'تجديد ':'اشترك في ')+P.n+' — ادفع '+P.p+' ريال'}
$('#payBtn').onclick=()=>{if(paying)return;const k=selPlan,msg=$('#pmsg');
 const done=()=>{plan=k;sv('plan',plan);if(k!='free'){exp=(k==plan_prev?Math.max(exp,Date.now()):Date.now())+30*DAY;sv('exp',exp)}
  paying=false;applyPlan();msg.textContent=k=='free'?'تم التحويل للباقة العادية ✅':'تمت العملية بنجاح ✅';setTimeout(()=>{paint();view('acct')},1100)};
 var plan_prev=plan;paying=true;
 if(k=='free')return done();
 msg.textContent='جارٍ الدفع…';setTimeout(done,900)};
$('#logout').onclick=()=>view('out');
$('#login').onclick=()=>view('home');
applyPlan();

/* ---------- الثعبان ---------- */
function snake(root){
 const N=20;let sn,dir,nx,food,score,timer,run=false;
 const info=el('<div class="info"></div>'),cv=el('<canvas width="420" height="420"></canvas>'),go=el('<button class="btn">ابدأ اللعب</button>');
 const pad=el('<div class="pad"><button class="u" data-d="u">▲</button><button class="l" data-d="l">◀️</button><button class="d" data-d="d">▼</button><button class="r" data-d="r">▶️</button></div>');
 root.append(info,cv,go,pad);const x=cv.getContext('2d'),T=cv.width/N;
 const V={u:[0,-1],d:[0,1],l:[-1,0],r:[1,0]};
 const show=()=>info.textContent=`النقاط: ${score||0} — الأفضل: ${ld('sb',0)}`;
 function place(){do{food={x:Math.random()*N|0,y:Math.random()*N|0}}while(sn.some(p=>p.x==food.x&&p.y==food.y))}
 function start(){sn=[{x:10,y:10},{x:9,y:10},{x:8,y:10}];dir=nx=V.r;score=0;place();run=true;go.classList.add('hidden');clearInterval(timer);timer=setInterval(step,120);show();draw()}
 function turn(k){const v=V[k];if(!v||!run||(v[0]==-dir[0]&&v[1]==-dir[1]))return;nx=v}
 function step(){dir=nx;const h={x:sn[0].x+dir[0],y:sn[0].y+dir[1]};
  if(h.x<0||h.y<0||h.x>=N||h.y>=N||sn.some(p=>p.x==h.x&&p.y==h.y))return over();
  sn.unshift(h);if(h.x==food.x&&h.y==food.y){score++;place()}else sn.pop();show();draw()}
 function over(){run=false;clearInterval(timer);if(score>ld('sb',0))sv('sb',score);show();go.textContent='انتهت اللعبة — العب مرة أخرى';go.classList.remove('hidden')}
 function draw(){x.clearRect(0,0,420,420);x.fillStyle='#ff7a59';x.beginPath();x.arc(food.x*T+T/2,food.y*T+T/2,T*.38,0,7);x.fill();
  sn.forEach((p,i)=>{x.fillStyle=i?'#7fe0b0':'#e8fff3';x.beginPath();x.roundRect(p.x*T+1,p.y*T+1,T-2,T-2,6);x.fill()})}
 go.onclick=start;
 pad.querySelectorAll('button').forEach(b=>b.addEventListener('pointerdown',e=>{e.preventDefault();turn(b.dataset.d)}));
 const kd=e=>{const m={ArrowUp:'u',ArrowDown:'d',ArrowLeft:'l',ArrowRight:'r',w:'u',s:'d',a:'l',d:'r'}[e.key];if(m){e.preventDefault();turn(m)}};
 addEventListener('keydown',kd);
 let t0;cv.addEventListener('touchstart',e=>{t0=e.touches[0]},{passive:true});
 cv.addEventListener('touchend',e=>{if(!t0)return;const t=e.changedTouches[0],dx=t.clientX-t0.clientX,dy=t.clientY-t0.clientY;if(Math.max(Math.abs(dx),Math.abs(dy))<20)return;turn(Math.abs(dx)>Math.abs(dy)?(dx>0?'r':'l'):(dy>0?'d':'u'))});
 sn=[{x:10,y:10}];food={x:5,y:5};show();draw();
 return()=>{clearInterval(timer);removeEventListener('keydown',kd)};
}

/* ---------- إكس أو ---------- */
function xo(root){
 const L=[[0,1,2],[3,4,5],[6,7,8],[0,3,6],[1,4,7],[2,5,8],[0,4,8],[2,4,6]];
 let b,over,tm;
 const info=el('<div class="info"></div>'),grid=el('<div class="xo"></div>'),again=el('<button class="btn">لعبة جديدة</button>');
 root.append(info,grid,again);
 const win=p=>L.find(l=>l.every(i=>b[i]==p));
 function reset(){clearTimeout(tm);b=Array(9).fill('');over=false;info.textContent='دورك — أنت ❌';render()}
 function render(){grid.innerHTML='';b.forEach((v,i)=>{const c=document.createElement('button');c.textContent=v;c.onclick=()=>me(i);grid.append(c)})}
 function end(){if(win('X')){info.textContent='فزت! 🎉';return over=true}
  if(win('O')){info.textContent='فاز الكمبيوتر 🤖';return over=true}
  if(b.every(v=>v)){info.textContent='تعادل';return over=true}return false}
 function me(i){if(over||b[i])return;b[i]='X';render();if(end())return;info.textContent='الكمبيوتر يفكر…';tm=setTimeout(cpu,350)}
 function cpu(){const free=b.map((v,i)=>v?-1:i).filter(i=>i>=0);
  const find=p=>free.find(i=>{b[i]=p;const w=win(p);b[i]='';return w});
  let m=find('O');if(m==null)m=find('X');if(m==null)m=b[4]?free[Math.random()*free.length|0]:4;
  b[m]='O';render();if(!end())info.textContent='دورك — أنت ❌'}
 again.onclick=reset;reset();
 return()=>clearTimeout(tm);
}

/* ---------- الذاكرة ---------- */
function mem(root){
 const info=el('<div class="info"></div>'),grid=el('<div class="mem"></div>'),again=el('<button class="btn">لعبة جديدة</button>');
 root.append(info,grid,again);
 let cards,open,lock,moves,found,tm;
 function reset(){clearTimeout(tm);const e=['🍎','🚀','🐱','⚽','🌙','🎸'];cards=[...e,...e].sort(()=>Math.random()-.5);open=[];lock=false;moves=0;found=0;info.textContent='الحركات: 0';grid.innerHTML='';
  cards.forEach((c,i)=>{const b=document.createElement('button');b.onclick=()=>flip(i,b);grid.append(b)})}
 function flip(i,b){if(lock||b.classList.contains('on')||b.classList.contains('ok'))return;b.classList.add('on');b.textContent=cards[i];open.push([i,b]);
  if(open.length==2){moves++;lock=true;const[[i1,b1],[i2,b2]]=open;
   if(cards[i1]==cards[i2]){b1.classList.add('ok');b2.classList.add('ok');found++;open=[];lock=false;info.textContent=found==6?`برافو! أنهيتها في ${moves} حركة 🎉`:`الحركات: ${moves}`}
   else{info.textContent=`الحركات: ${moves}`;tm=setTimeout(()=>{[b1,b2].forEach(x=>{x.classList.remove('on');x.textContent=''});open=[];lock=false},700)}}}
 again.onclick=reset;reset();
 return()=>clearTimeout(tm);
}

/* ---------- خمّن الرقم ---------- */
function guess(root){
 let n,tries;
 const info=el('<div class="info"></div>'),inp=el('<input type="number" inputmode="numeric" min="1" max="100" placeholder="؟">'),ok=el('<button class="btn">خمّن</button>'),again=el('<button class="btn ghost">لعبة جديدة</button>');
 root.append(info,inp,ok,again);
 function reset(){n=Math.random()*100+1|0;tries=0;info.textContent='فكرت في رقم من 1 إلى 100';inp.value='';inp.disabled=false}
 function check(){const v=+inp.value;if(!v||v<1||v>100){info.textContent='اكتب رقمًا من 1 إلى 100';return}
  tries++;if(v==n){info.textContent=`صح! الرقم ${n} — بعد ${tries} محاولة 🎉`;inp.disabled=true}
  else info.textContent=(v<n?'أكبر ⬆️':'أصغر ⬇️')+` — المحاولات: ${tries}`;inp.value=''}
 ok.onclick=check;again.onclick=reset;inp.onkeydown=e=>{if(e.key=='Enter')check()};reset();
}

/* ---------- حجر ورقة مقص ---------- */
function rps(root){
 const E=['✊','✋','✌️'];let w=0,l=0;
 const info=el('<div class="info"></div>'),res=el('<div class="big"></div>'),row=el('<div class="rps"></div>');
 root.append(info,res,row);
 const show=()=>info.textContent=`فزت: ${w} — خسرت: ${l}`;
 E.forEach((e,i)=>{const b=document.createElement('button');b.textContent=e;b.onclick=()=>{const c=Math.random()*3|0;
  const r=i==c?0:(i-c+3)%3==1?1:-1;if(r>0)w++;if(r<0)l++;
  res.textContent=`${e} ضد ${E[c]} — ${r>0?'فزت 🎉':r<0?'خسرت':'تعادل'}`;show()};row.append(b)});
 show();res.textContent='اختر…';
}

/* ---------- اضرب الخلد ---------- */
function whack(root){
 let sc,t,mole=-1,t1,t2,run=false;
 const info=el('<div class="info"></div>'),grid=el('<div class="holes"></div>'),go=el('<button class="btn">ابدأ</button>');
 root.append(info,grid,go);
 const show=()=>info.textContent=`النقاط: ${sc||0} — الوقت: ${t??30}`;
 function render(){grid.innerHTML='';for(let i=0;i<9;i++){const b=document.createElement('button');b.textContent=i==mole?'🐹':'';b.onclick=()=>{if(run&&i==mole){sc++;mole=-1;render();show()}};grid.append(b)}}
 function stop(){clearInterval(t1);clearInterval(t2);run=false;mole=-1;render();info.textContent=`انتهى الوقت! نقاطك: ${sc}`;go.classList.remove('hidden')}
 go.onclick=()=>{sc=0;t=30;run=true;go.classList.add('hidden');show();
  t1=setInterval(()=>{t--;if(t<=0)stop();else show()},1000);
  t2=setInterval(()=>{mole=Math.random()*9|0;render()},650)};
 render();show();
 return()=>{clearInterval(t1);clearInterval(t2)};
}

/* ---------- حساب سريع ---------- */
function math(root){
 let sc,t,ans,t1,run=false;
 const info=el('<div class="info"></div>'),q=el('<div class="big"></div>'),opts=el('<div class="opts"></div>'),go=el('<button class="btn">ابدأ</button>');
 root.append(info,q,opts,go);
 const show=()=>info.textContent=`النقاط: ${sc||0} — الوقت: ${t??30}`;
 function next(){const a=Math.random()*12+2|0,b=Math.random()*12+2|0,o=Math.random()*3|0;
  ans=[a+b,a+b+5>a*b?a*b:a-b+b*2,a*b][o];let s=[`${a} + ${b}`,`${a} × ${b}`,`${a} × ${b}`][o];
  if(o==0)ans=a+b;else{ans=a*b}
  q.textContent=s+' = ؟';const set=new Set([ans]);while(set.size<4)set.add(ans+(Math.random()*10-5|0)||ans+11);
  opts.innerHTML='';[...set].sort(()=>Math.random()-.5).forEach(v=>{const b=document.createElement('button');b.textContent=v;b.onclick=()=>{if(!run)return;if(v==ans)sc++;else sc=Math.max(0,sc-1);show();next()};opts.append(b)})}
 function stop(){clearInterval(t1);run=false;opts.innerHTML='';q.textContent='';info.textContent=`انتهى الوقت! نقاطك: ${sc}`;go.classList.remove('hidden')}
 go.onclick=()=>{sc=0;t=30;run=true;go.classList.add('hidden');show();next();t1=setInterval(()=>{t--;if(t<=0)stop();else show()},1000)};
 show();
 return()=>clearInterval(t1);
}

/* ---------- 2048 ---------- */
function g2048(root){
 let g,sc,dead;
 const info=el('<div class="info"></div>'),board=el('<div class="g2048"></div>'),again=el('<button class="btn">لعبة جديدة</button>');
 root.append(info,board,again);
 function add(){const f=g.map((v,i)=>v?-1:i).filter(i=>i>=0);if(f.length)g[f[Math.random()*f.length|0]]=Math.random()<.9?2:4}
 function render(){board.innerHTML='';g.forEach(v=>{const d=document.createElement('div');if(v){d.textContent=v;const k=Math.log2(v);d.style.background=`hsl(${160-k*12},55%,${Math.max(28,52-k*2)}%)`;d.style.color='#06222a';if(v>=1024)d.style.fontSize='19px'}board.append(d)});
  info.textContent=dead?`انتهت اللعبة — نقاطك ${sc}`:`النقاط: ${sc}`}
 function slide(a){a=a.filter(v=>v);for(let i=0;i<a.length-1;i++)if(a[i]==a[i+1]){a[i]*=2;sc+=a[i];a.splice(i+1,1)}while(a.length<4)a.push(0);return a}
 function lines(d){const r=[];for(let i=0;i<4;i++){const idx=[0,1,2,3].map(j=>d<2?i*4+j:j*4+i);r.push(d%2?idx.reverse():idx)}return r}
 function move(d){if(dead)return;let ch=false;lines(d).forEach(idx=>{const o=idx.map(k=>g[k]),n=slide(o);if(n.some((v,i)=>v!=o[i]))ch=true;idx.forEach((k,i)=>g[k]=n[i])});
  if(ch){add();dead=!can()}render()}
 function can(){if(g.includes(0))return true;for(let i=0;i<16;i++){if(i%4<3&&g[i]==g[i+1])return true;if(i<12&&g[i]==g[i+4])return true}return false}
 function reset(){g=Array(16).fill(0);sc=0;dead=false;add();add();render()}
 const kd=e=>{const m={ArrowLeft:0,ArrowRight:1,ArrowUp:2,ArrowDown:3}[e.key];if(m!=null){e.preventDefault();move(m)}};
 addEventListener('keydown',kd);
 let t0;root.addEventListener('touchstart',e=>{t0=e.touches[0]},{passive:true});
 root.addEventListener('touchend',e=>{if(!t0)return;const t=e.changedTouches[0],dx=t.clientX-t0.clientX,dy=t.clientY-t0.clientY;if(Math.max(Math.abs(dx),Math.abs(dy))<25)return;move(Math.abs(dx)>Math.abs(dy)?(dx>0?1:0):(dy>0?3:2))});
 again.onclick=reset;reset();
 return()=>removeEventListener('keydown',kd);
}

/* ---------- تفادى ---------- */
function dodge(root){
 const info=el('<div class="info">اسحب على اللوحة أو استخدم الأزرار</div>'),cv=el('<canvas width="420" height="420"></canvas>'),go=el('<button class="btn">ابدأ</button>');
 const row=el('<div class="row"><button data-d="-1">◀️</button><button data-d="1">▶️</button></div>');
 root.append(info,cv,go,row);const x=cv.getContext('2d');
 let px=210,hold=0,bl=[],sc=0,fr=0,alive=false,raf;
 const kd=e=>{if(e.key=='ArrowLeft')hold=-1;if(e.key=='ArrowRight')hold=1};
 const ku=e=>{if(e.key=='ArrowLeft'||e.key=='ArrowRight')hold=0};
 addEventListener('keydown',kd);addEventListener('keyup',ku);
 row.querySelectorAll('button').forEach(b=>{b.addEventListener('pointerdown',e=>{e.preventDefault();hold=+b.dataset.d});['pointerup','pointerleave','pointercancel'].forEach(t=>b.addEventListener(t,()=>hold=0))});
 cv.addEventListener('pointermove',e=>{if(!alive)return;const r=cv.getBoundingClientRect();px=(e.clientX-r.left)/r.width*420});
 function loop(){if(!alive)return;fr++;sc++;px=Math.min(395,Math.max(25,px+hold*7));
  if(fr%Math.max(14,40-(sc/60|0))==0){const w=40+Math.random()*60;bl.push({x:Math.random()*(420-w),y:-20,w,v:3+sc/400})}
  bl.forEach(b=>b.y+=b.v);bl=bl.filter(b=>b.y<430);
  x.clearRect(0,0,420,420);x.fillStyle='#ff7a59';
  for(const b of bl){x.fillRect(b.x,b.y,b.w,20);if(b.y+20>385&&b.y<405&&px+22>b.x&&px-22<b.x+b.w){alive=false}}
  x.fillStyle='#7fe0b0';x.beginPath();x.roundRect(px-22,385,44,20,6);x.fill();
  info.textContent=`النقاط: ${sc/10|0}`;
  if(alive)raf=requestAnimationFrame(loop);else{info.textContent=`انتهت اللعبة — نقاطك ${sc/10|0}`;go.textContent='العب مرة أخرى';go.classList.remove('hidden')}}
 go.onclick=()=>{bl=[];sc=0;fr=0;px=210;alive=true;go.classList.add('hidden');raf=requestAnimationFrame(loop)};
 return()=>{alive=false;cancelAnimationFrame(raf);removeEventListener('keydown',kd);removeEventListener('keyup',ku)};
}

/* ---------- سرعة الرد ---------- */
function react(root){
 let st=0,t0,tm;
 const info=el('<div class="info"></div>'),box=el('<button class="rbox">اضغط للبدء</button>');
 root.append(info,box);
 const show=()=>info.textContent=`أفضل زمن: ${ld('rb',0)?ld('rb',0)+' ملي ثانية':'—'}`;
 box.onclick=()=>{
  if(st==0){st=1;box.style.background='#a63b2a';box.textContent='انتظر…';tm=setTimeout(()=>{st=2;t0=performance.now();box.style.background='#2fd36b';box.style.color='#06222a';box.textContent='اضغط الآن!'},1000+Math.random()*3000)}
  else if(st==1){clearTimeout(tm);st=0;box.style.background='';box.style.color='';box.textContent='بدري! اضغط للمحاولة مرة ثانية'}
  else{const ms=Math.round(performance.now()-t0);st=0;box.style.background='';box.style.color='';box.textContent=`${ms} ملي ثانية — اضغط للإعادة`;const b=ld('rb',0);if(!b||ms<b)sv('rb',ms);show()}};
 show();
 return()=>clearTimeout(tm);
}

/* ---------- سرعة النقر ---------- */
function taps(root){
 let n=0,t=10,t1,run=false;
 const info=el('<div class="info"></div>'),b=el('<button class="tap">👆</button>');
 root.append(info,b);
 const show=()=>info.textContent=`النقرات: ${n} — الوقت: ${t} — الأفضل: ${ld('tb',0)}`;
 function stop(){clearInterval(t1);run=false;if(n>ld('tb',0))sv('tb',n);info.textContent=`انتهى! نقراتك: ${n} — الأفضل: ${ld('tb',0)} (اضغط للإعادة)`}
 b.onclick=()=>{if(!run){n=0;t=10;run=true;t1=setInterval(()=>{t--;if(t<=0)stop();else show()},1000)}n++;show()};
 info.textContent='اضغط على الزر للبدء';
 return()=>clearInterval(t1);
}

/* ---------- النرد ---------- */
function dice(root){
 const F='⚀⚁⚂⚃⚄⚅';
 const info=el('<div class="info">ارمِ النرد</div>'),d=el('<div class="dice">⚀ ⚅</div>'),b=el('<button class="btn">ارمِ</button>');
 root.append(info,d,b);let tm;
 b.onclick=()=>{let k=0;clearInterval(tm);tm=setInterval(()=>{const a=Math.random()*6|0,c=Math.random()*6|0;d.textContent=F[a]+' '+F[c];if(++k>8){clearInterval(tm);info.textContent=`المجموع: ${a+c+2}`}},70)};
 return()=>clearInterval(tm);
}
</script>
</body>
</html>