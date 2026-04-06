---
obsidianUIMode: preview
subscriptions:
  - id: smnnlt585_68r2
    name: tes
    price: 9
    currency: $
    method: Card
    type: recurring
    cycle: monthly
    started: 2026-04-07
    nextDate: 2026-05-07
    status: active
    color: "#0ea5e9"
    category: Entertainment
payment_methods:
  - Card
  - Apple Pay
  - Google Pay
  - PayPal
  - Cash
  - Crypto
currencies:
  - $
  - €
  - £
  - USDT
method_colors:
  Card: "#1a68ff"
  PayPal: "#003087"
  Apple Pay: "#333333"
  Cash: "#22c55e"
categories:
  - Entertainment
  - Technology
  - Membership
  - Other
exchange_rates:
  $: ""
---



```dataviewjs
await (async () => {

  const DEF_CUR='$',GRACE=3;
  const MO=['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
  const td=()=>{const d=new Date();return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0');};
  const td0=()=>{const d=new Date();d.setHours(0,0,0,0);return d;};
  const pd=s=>s?new Date(s+'T00:00:00'):null;
  const fD=s=>{const d=pd(s);if(!d)return'\u2014';return d.getDate()+' '+MO[d.getMonth()]+' '+String(d.getFullYear()).slice(2);};
  const dL=s=>{const d=pd(s);if(!d)return 0;return Math.ceil((d-td0())/864e5);};
  const gid=()=>'s'+Date.now().toString(36)+'_'+Math.random().toString(36).slice(2,6);
  function fP(p,c){const n=Number(p)||0;const f=n%1===0?n.toLocaleString():n.toLocaleString(undefined,{minimumFractionDigits:2,maximumFractionDigits:2});if(c&&c.length===1)return c+f;return f+' '+(c||'$');}
  function fPraw(p){const n=Number(p)||0;return n%1===0?n.toLocaleString():n.toLocaleString(undefined,{minimumFractionDigits:2,maximumFractionDigits:2});}
  function adv(s,cy){const d=pd(s);if(!d)return s;switch(cy){case'monthly':d.setMonth(d.getMonth()+1);break;case'yearly':d.setFullYear(d.getFullYear()+1);break;case'weekly':d.setDate(d.getDate()+7);break;case'quarterly':d.setMonth(d.getMonth()+3);break;case'biannual':d.setMonth(d.getMonth()+6);break;default:d.setMonth(d.getMonth()+1);}const yy=d.getFullYear(),mm=String(d.getMonth()+1).padStart(2,'0'),dd=String(d.getDate()).padStart(2,'0');return yy+'-'+mm+'-'+dd;}
  const fCy=c=>({monthly:'Monthly',yearly:'Yearly',weekly:'Weekly',quarterly:'Every 3 Months',biannual:'Every 6 Months'}[c]||c||'');
  function mathCol(price,cur,cycle){const n=Number(price)||0;if(!cycle||cycle==='monthly'||cycle==='weekly')return'\u2014';const div={yearly:12,quarterly:3,biannual:6}[cycle]||1;return fP(n,cur)+' \u00F7 '+div;}
  const MC={NassPay:{dot:'#ef4444',text:'#fca5a5',bg:'rgba(239,68,68,.08)'},FIB:{dot:'#3b82f6',text:'#93c5fd',bg:'rgba(59,130,246,.08)'},TIB:{dot:'#22c55e',text:'#86efac',bg:'rgba(34,197,94,.08)'},Crypto:{dot:'#7f1d1d',text:'#fca5a5',bg:'rgba(127,29,29,.08)'},'Qi Card':{dot:'#e8a020',text:'#fcd880',bg:'rgba(232,160,32,.08)'},'Apple Credit':{dot:'#38bdf8',text:'#7dd3fc',bg:'rgba(56,189,248,.08)'},'Kazawallet Card':{dot:'#2dd4a8',text:'#fff',bg:'rgba(45,212,168,.08)'},'Google Pay':{dot:'#4285f4',text:'#fff',bg:'rgba(66,133,244,.08)'},'Google Play Credit':{dot:'#84cc16',text:'#bef264',bg:'rgba(132,204,22,.08)'},'Prepaid Card':{dot:'#a855f7',text:'#d8b4fe',bg:'rgba(168,85,247,.08)'}};
  const gmc=m=>{if(D&&D.mColors&&D.mColors[m]){const d=D.mColors[m];const r=parseInt(d.slice(1,3),16),g=parseInt(d.slice(3,5),16),b=parseInt(d.slice(5,7),16);return{dot:d,text:'#'+[r,g,b].map(v=>Math.min(255,v+100).toString(16).padStart(2,'0')).join(''),bg:'rgba('+r+','+g+','+b+',.08)'};}return MC[m]||{dot:'#6b7280',text:'#d1d5db',bg:'rgba(107,114,128,.08)'};};

  const COLORS=[
    {v:'#ef4444',n:'Red'},{v:'#f97316',n:'Orange'},{v:'#eab308',n:'Gold'},
    {v:'#22c55e',n:'Green'},{v:'#0ea5e9',n:'Sky'},{v:'#3b82f6',n:'Blue'},
    {v:'#6366f1',n:'Indigo'},{v:'#8b5cf6',n:'Violet'},{v:'#ec4899',n:'Pink'},
    {v:'#14b8a6',n:'Teal'},{v:'#64748b',n:'Slate'},{v:'#d4a574',n:'Warm'}
  ];
  function clrHex(c){return COLORS.find(x=>x.v===c)?c:(c||COLORS[4].v);}
  function clrDarken(hex){const r=parseInt(hex.slice(1,3),16),g=parseInt(hex.slice(3,5),16),b=parseInt(hex.slice(5,7),16);return'#'+[r,g,b].map(v=>Math.round(v*.65).toString(16).padStart(2,'0')).join('');}

  function vaultImgSrc(path){try{const f=app.vault.getAbstractFileByPath(path);if(f)return app.vault.adapter.getResourcePath(path);}catch(e){}return '';}
  function subIcon(nm,ico,color){
    const c=clrHex(color);const cd=clrDarken(c);
    if(ico){
      if(ico.startsWith('<svg'))return'<div class="VA-icon VA-icon-svg"><div style="width:28px!important;height:28px!important;display:flex!important;align-items:center!important;justify-content:center!important">'+ico.replace(/<svg/,'<svg style="width:28px!important;height:28px!important;display:block!important"')+'</div></div>';
      if(ico.match(/\.(svg|png|jpg|jpeg|webp)$/i)){const src=vaultImgSrc(ico);if(src)return'<div class="VA-icon VA-icon-svg"><img src="'+src+'" style="width:28px!important;height:28px!important;object-fit:contain!important;display:block!important;border-radius:4px!important" /></div>';}
      return'<div class="VA-icon" style="background:linear-gradient(135deg,'+c+','+cd+')!important"><span class="VA-icon-t">'+ico+'</span></div>';
    }
    const w=nm.trim().split(/\s+/);const mn=w.length>=2?(w[0][0]+w[1][0]).toUpperCase():nm.slice(0,2).toUpperCase();
    return'<div class="VA-icon" style="background:linear-gradient(135deg,'+c+','+cd+')!important;box-shadow:0 0 10px '+c+'22!important"><span class="VA-icon-t">'+mn+'</span></div>';
  }
  function subIconSm(nm,ico,color){
    const c=clrHex(color);const cd=clrDarken(c);
    if(ico){
      if(ico.startsWith('<svg'))return'<span class="VA-ico-sm VA-icon-svg" style="width:18px!important;height:18px!important;display:inline-flex!important;align-items:center!important;justify-content:center!important;vertical-align:middle!important;flex-shrink:0!important">'+ico.replace(/<svg/,'<svg style="width:18px!important;height:18px!important;display:block!important"')+'</span>';
      if(ico.match(/\.(svg|png|jpg|jpeg|webp)$/i)){const src=vaultImgSrc(ico);if(src)return'<img class="VA-ico-sm" src="'+src+'" style="width:18px!important;height:18px!important;object-fit:contain!important;display:inline-block!important;vertical-align:middle!important;flex-shrink:0!important;border-radius:3px!important" />';}
      return'<span class="VA-ico-sm" style="width:18px!important;height:18px!important;border-radius:50%!important;background:linear-gradient(135deg,'+c+','+cd+')!important;display:inline-flex!important;align-items:center!important;justify-content:center!important;vertical-align:middle!important;flex-shrink:0!important;font-size:9px!important;font-weight:800!important;color:#fff!important">'+ico+'</span>';
    }
    const w=nm.trim().split(/\s+/);const mn=w.length>=2?(w[0][0]+w[1][0]).toUpperCase():nm.slice(0,2).toUpperCase();
    return'<span class="VA-ico-sm" style="width:18px!important;height:18px!important;border-radius:50%!important;background:linear-gradient(135deg,'+c+','+cd+')!important;display:inline-flex!important;align-items:center!important;justify-content:center!important;vertical-align:middle!important;flex-shrink:0!important;font-size:8px!important;font-weight:800!important;color:#fff!important">'+mn+'</span>';
  }

  const cf=app.workspace.getActiveFile();
  if(!cf){dv.paragraph('No active file.');return;}
  function rd(){const c=app.metadataCache.getFileCache(cf);const f=c?.frontmatter||{};return{subs:JSON.parse(JSON.stringify(f.subscriptions||[])),methods:JSON.parse(JSON.stringify(f.payment_methods||['NassPay','FIB','TIB','Crypto'])),currencies:JSON.parse(JSON.stringify(f.currencies||['$','\u20ac','\u00a3','IQD'])),mColors:JSON.parse(JSON.stringify(f.method_colors||{})),exRates:JSON.parse(JSON.stringify(f.exchange_rates||{})),categories:JSON.parse(JSON.stringify(f.categories||['Entertainment','Technology','Membership','Other']))};}
  async function sv(subs,methods,currencies,mColors,exRates,categories){await app.fileManager.processFrontMatter(cf,fm=>{fm.subscriptions=subs;if(methods)fm.payment_methods=methods;if(currencies)fm.currencies=currencies;if(mColors)fm.method_colors=mColors;if(exRates)fm.exchange_rates=exRates;if(categories)fm.categories=categories;});}

  function toUSD(price,cur){if(!price)return 0;const n=Number(price)||0;if(cur==='$'||!cur)return n;var rate=D.exRates[cur];if(rate&&Number(rate)>0)return n/Number(rate);return n;}
  function toMonthlyUSD(price,cur,cycle){const u=toUSD(price,cur);switch(cycle){case'monthly':return u;case'yearly':return u/12;case'weekly':return u*(52/12);case'quarterly':return u/3;case'biannual':return u/6;default:return u;}}

  function openDaily(dateStr){if(!dateStr)return;const path='Habits/Habit Days/'+dateStr+'.md';const file=app.vault.getAbstractFileByPath(path);if(file)app.workspace.openLinkText(path,'',true);}
  function dailyExists(dateStr){if(!dateStr)return false;return !!app.vault.getAbstractFileByPath('Habits/Habit Days/'+dateStr+'.md');}

  let D=rd(),ns=false;const nw=td();
  D.subs.forEach(s=>{
    if(!s.id){s.id=gid();ns=true;}
    if(!s.color){s.color=COLORS[Math.abs([...s.name].reduce((h,c)=>((h<<5)-h)+c.charCodeAt(0),0))%COLORS.length].v;ns=true;}
    if(s.type==='recurring'&&s.status==='active'&&s.nextDate){let a=false;while(s.nextDate<nw){s.nextDate=adv(s.nextDate,s.cycle||'monthly');a=true;ns=true;}if(a)s.lastAdv=nw;}
    if(s.type==='non-recurring'&&s.status==='active'&&s.nextDate&&s.nextDate<nw){s.status='dead';s.deathDate=s.nextDate;s.deathReason='expired';ns=true;}
  });
  if(ns)await sv(D.subs,D.methods,D.currencies);D=rd();

  const SK='__stA';if(!window[SK])window[SK]={deadOpen:false,filters:{},sorts:{},showUSD:false,mExpAll:{},mExp:{},stTab:'overview',chartMode:'donut',appMode:true};const ST=window[SK];if(!ST.mExpAll)ST.mExpAll={};if(!ST.mExp)ST.mExp={};if(!ST.stTab)ST.stTab='overview';if(!ST.chartMode)ST.chartMode='donut';ST.appMode=true;
  // ====== CSS ======
  const SID='stAcss';document.getElementById(SID)?.remove();
  const sty=document.createElement('style');sty.id=SID;
  sty.textContent=`
#STA,#STA *{box-sizing:border-box!important;margin:0!important;padding:0!important;font-family:-apple-system,BlinkMacSystemFont,'Segoe UI',system-ui,sans-serif!important}
#STA table,#STA table th,#STA table td{border-color:#12202e!important}
#STA{background:#070b14!important;color:#d0dce8!important;border:1px solid #1a2a40!important;border-radius:10px!important;line-height:1.5!important;-webkit-font-smoothing:antialiased!important;position:relative!important;overflow:hidden!important}
#STA .VA-row-hide{display:none!important}
#STA::before{content:''!important;position:absolute!important;top:0!important;left:0!important;right:0!important;height:2px!important;background:linear-gradient(90deg,transparent,#0e4a5e,#22d3ee,#0e4a5e,transparent)!important;border-radius:10px 10px 0 0!important;pointer-events:none!important;z-index:3!important}
#STA::after{content:''!important;position:absolute!important;bottom:0!important;left:0!important;right:0!important;height:1px!important;background:linear-gradient(90deg,transparent,rgba(34,211,238,.08),transparent)!important;pointer-events:none!important;z-index:3!important}
#STA .VA-bg{position:absolute!important;inset:0!important;pointer-events:none!important;z-index:0!important;overflow:hidden!important;border-radius:10px!important;background:radial-gradient(ellipse at 15% 0%,rgba(34,211,238,.07) 0%,transparent 40%),radial-gradient(ellipse at 85% 100%,rgba(167,139,250,.06) 0%,transparent 40%),repeating-linear-gradient(0deg,transparent,transparent 23px,rgba(34,211,238,.04) 23px,rgba(34,211,238,.04) 24px),repeating-linear-gradient(90deg,transparent,transparent 23px,rgba(34,211,238,.025) 23px,rgba(34,211,238,.025) 24px),repeating-linear-gradient(60deg,transparent,transparent 47px,rgba(34,211,238,.018) 47px,rgba(34,211,238,.018) 48px),repeating-linear-gradient(-60deg,transparent,transparent 47px,rgba(167,139,250,.015) 47px,rgba(167,139,250,.015) 48px)!important}
#STA .VA-corner{position:absolute!important;width:20px!important;height:20px!important;pointer-events:none!important;z-index:2!important}#STA .VA-corner::before,#STA .VA-corner::after{content:''!important;position:absolute!important;background:rgba(34,211,238,.22)!important}#STA .VA-corner::before{width:20px!important;height:1px!important}#STA .VA-corner::after{width:1px!important;height:20px!important}#STA .VA-tl{top:8px!important;left:8px!important}#STA .VA-tl::before{top:0;left:0}#STA .VA-tl::after{top:0;left:0}#STA .VA-tr{top:8px!important;right:8px!important}#STA .VA-tr::before{top:0;right:0}#STA .VA-tr::after{top:0;right:0}#STA .VA-bl{bottom:8px!important;left:8px!important}#STA .VA-bl::before{bottom:0;left:0}#STA .VA-bl::after{bottom:0;left:0}#STA .VA-br{bottom:8px!important;right:8px!important}#STA .VA-br::before{bottom:0;right:0}#STA .VA-br::after{bottom:0;right:0}
@keyframes VApulse{0%,100%{opacity:.04}50%{opacity:.1}}
#STA .VA-pulse{position:absolute!important;top:-40px!important;left:-40px!important;width:200px!important;height:200px!important;border-radius:50%!important;background:radial-gradient(circle,rgba(34,211,238,.1),transparent 70%)!important;animation:VApulse 6s ease-in-out infinite!important;pointer-events:none!important;z-index:0!important}
#STA .VA-pulse2{position:absolute!important;bottom:-30px!important;right:-30px!important;width:160px!important;height:160px!important;border-radius:50%!important;background:radial-gradient(circle,rgba(167,139,250,.06),transparent 70%)!important;animation:VApulse 8s ease-in-out infinite!important;animation-delay:3s!important;pointer-events:none!important;z-index:0!important}
.VA-hdr{display:flex!important;align-items:center!important;justify-content:space-between!important;flex-wrap:wrap!important;gap:10px!important;border-bottom:1px solid #152030!important;position:relative!important;z-index:1!important}
.VA-hdr::after{content:''!important;position:absolute!important;bottom:-1px!important;left:20px!important;right:20px!important;height:1px!important;background:linear-gradient(90deg,transparent,rgba(34,211,238,.12),transparent)!important}
.VA-ttl{font-size:16px!important;font-weight:800!important;letter-spacing:4px!important;text-transform:uppercase!important;color:#22d3ee!important;text-shadow:0 0 20px rgba(34,211,238,.2),0 0 40px rgba(34,211,238,.05)!important;border-left:3px solid #22d3ee!important;line-height:1!important}
.VA-btns{display:flex!important;gap:6px!important;flex-wrap:wrap!important}
.VA-b{font-size:11px!important;font-weight:600!important;letter-spacing:1px!important;text-transform:uppercase!important;cursor:pointer!important;transition:all .2s ease!important;user-select:none!important;display:inline-flex!important;align-items:center!important;gap:5px!important;line-height:1!important;white-space:nowrap!important;position:relative!important;border-radius:4px!important}
.VA-b-add{background:linear-gradient(180deg,#0e2a3e,#081828)!important;color:#22d3ee!important;border:1px solid #164e63!important;box-shadow:inset 0 1px 0 rgba(34,211,238,.1),0 0 8px rgba(34,211,238,.04)!important}.VA-b-add:hover{border-color:#22d3ee!important;box-shadow:0 0 16px rgba(34,211,238,.15),inset 0 1px 0 rgba(34,211,238,.15)!important;color:#67e8f9!important}
.VA-b-add .VA-bi{font-size:14px!important;color:#0891b2!important}
.VA-b-g{background:linear-gradient(180deg,#101828,#0a1220)!important;color:#5a8aa0!important;border:1px solid #1a2a40!important;border-radius:4px!important}.VA-b-g:hover{border-color:#22718a!important;color:#22d3ee!important;box-shadow:0 0 12px rgba(34,211,238,.08)!important}
.VA-b-f{background:linear-gradient(180deg,#1a1820,#0f0d18)!important;color:#c4a06a!important;border:1px solid #3d2e1a!important;border-radius:4px!important}.VA-b-f:hover{border-color:#d4a54a!important;color:#f0c060!important;box-shadow:0 0 12px rgba(212,165,74,.12)!important}
.VA-b-d{background:linear-gradient(180deg,#1c0e0e,#140808)!important;color:#ef4444!important;border:1px solid #3a1515!important;border-radius:4px!important}.VA-b-d:hover{border-color:#6b2020!important;box-shadow:0 0 12px rgba(239,68,68,.1)!important;color:#f87171!important}
.VA-sec{border:1px solid #152030!important;background:#0a1220!important;position:relative!important;border-radius:6px!important;overflow:visible!important}
.VA-sec::before{content:''!important;position:absolute!important;top:50%!important;left:-1px!important;width:3px!important;height:30px!important;transform:translateY(-50%)!important;border-radius:0 2px 2px 0!important;pointer-events:none!important}
.VA-sec::after{content:''!important;position:absolute!important;top:50%!important;right:-1px!important;width:3px!important;height:30px!important;transform:translateY(-50%)!important;border-radius:2px 0 0 2px!important;pointer-events:none!important}
.VA-sec-rec{z-index:30!important;border-top:3px solid #0891b2!important;box-shadow:0 -4px 16px rgba(8,145,178,.06)!important}.VA-sec-rec::before,.VA-sec-rec::after{background:rgba(8,145,178,.15)!important}
.VA-sec-non{z-index:20!important;border-top:3px solid #7c3aed!important;box-shadow:0 -4px 16px rgba(124,58,237,.06)!important}.VA-sec-non::before,.VA-sec-non::after{background:rgba(124,58,237,.12)!important}
.VA-sec-ded{z-index:10!important;border-top:3px solid #374151!important}.VA-sec-ded::before,.VA-sec-ded::after{background:rgba(100,116,139,.1)!important}
.VA-sh{background:linear-gradient(180deg,#0e1828,#0b1420)!important;display:flex!important;align-items:center!important;justify-content:space-between!important;flex-wrap:wrap!important;gap:8px!important;border-bottom:1px solid #152030!important}
.VA-sec-rec .VA-sh{background:linear-gradient(180deg,rgba(8,145,178,.06),#0b1420)!important}.VA-sec-non .VA-sh{background:linear-gradient(180deg,rgba(124,58,237,.05),#0b1420)!important}
.VA-shl{display:flex!important;align-items:center!important;gap:10px!important}.VA-sn{font-size:14px!important;font-weight:800!important;letter-spacing:2px!important;text-transform:uppercase!important;line-height:1!important}
.VA-sc{font-size:11px!important;font-weight:700!important;background:rgba(34,211,238,.08)!important;color:#3a8a9e!important;border-radius:10px!important;min-width:22px!important;text-align:center!important;line-height:1!important}
.VA-stog{font-size:11px!important;color:#4a6a80!important;cursor:pointer!important;transition:color .15s!important}.VA-stog:hover{color:#22d3ee!important}
.VA-usd{font-size:9px!important;color:#2a5a70!important;cursor:pointer!important;transition:all .2s!important;letter-spacing:.5px!important;border:1px solid #1a3a50!important;border-radius:12px!important;background:linear-gradient(180deg,#0c1828,#081420)!important;display:inline-flex!important;align-items:center!important;gap:3px!important}.VA-usd:hover{color:#22d3ee!important;border-color:#1a6a80!important;box-shadow:0 0 8px rgba(34,211,238,.08)!important}.VA-usd.act{color:#22d3ee!important;border-color:#0891b2!important;background:linear-gradient(180deg,#0e2a3e,#081828)!important;box-shadow:0 0 10px rgba(34,211,238,.1)!important}
.VA-metog{font-size:10px!important;color:#3a6a80!important;cursor:pointer!important;border:1px solid #1a3a50!important;border-radius:12px!important;display:none!important;transition:all .2s!important;background:linear-gradient(180deg,#0c1828,#081420)!important}.VA-metog:hover{color:#22d3ee!important;border-color:#1a6a80!important;box-shadow:0 0 8px rgba(34,211,238,.08)!important}.VA-metog.VA-metog-open{color:#22d3ee!important;border-color:#0891b2!important}
.VA-tb{background:linear-gradient(180deg,#091018,#0a1220)!important;border-top:1px solid #12202e!important;border-bottom:1px solid #12202e!important;display:flex!important;align-items:center!important;gap:8px!important;flex-wrap:wrap!important}
.VA-srch{width:160px!important;font-size:12px!important;border:1px solid #1a2a40!important;background:#070b14!important;color:#d0dce8!important;outline:none!important;transition:border-color .15s,box-shadow .15s!important;line-height:1.3!important;height:auto!important;-webkit-appearance:none!important;appearance:none!important;box-shadow:inset 0 1px 2px rgba(0,0,0,.3)!important;border-radius:4px!important}
.VA-srch:focus{border-color:#1a6a80!important;box-shadow:0 0 8px rgba(34,211,238,.06)!important}.VA-srch::placeholder{color:#2a4a5e!important;font-size:11px!important}
.VA-sep{width:1px!important;height:16px!important;background:linear-gradient(180deg,transparent,#1a2a40,transparent)!important;flex-shrink:0!important}
.VA-fwrap{position:relative!important;display:inline-block!important}
.VA-fb{font-size:10px!important;font-weight:600!important;letter-spacing:.5px!important;text-transform:uppercase!important;cursor:pointer!important;transition:all .15s!important;border:1px solid #1a2a40!important;background:linear-gradient(180deg,#0e1828,#0a1018)!important;color:#4a7a90!important;display:inline-flex!important;align-items:center!important;gap:5px!important;border-radius:4px!important;white-space:nowrap!important}
.VA-fb:hover{border-color:#1a5a70!important;color:#22d3ee!important}.VA-fb.act{border-color:#164e63!important;color:#22d3ee!important;background:rgba(34,211,238,.04)!important}
.VA-farr{font-size:7px!important;transition:transform .15s!important}.VA-fwrap.open .VA-farr{transform:rotate(180deg)!important}
.VA-fpop{position:absolute!important;top:calc(100% + 4px)!important;left:0!important;min-width:160px!important;background:#0c1828!important;border:1px solid #1a3048!important;border-radius:6px!important;z-index:999!important;display:none!important;box-shadow:0 8px 24px rgba(0,0,0,.5),0 0 1px rgba(34,211,238,.1)!important}
.VA-fwrap.open .VA-fpop{display:flex!important;flex-wrap:wrap!important;gap:4px!important}
.VA-fp{font-size:10px!important;font-weight:600!important;letter-spacing:.3px!important;cursor:pointer!important;transition:all .12s!important;border:1px solid #152030!important;background:#0a1220!important;color:#4a7a90!important;display:inline-flex!important;align-items:center!important;gap:5px!important;border-radius:4px!important;white-space:nowrap!important}
.VA-fp:hover{border-color:#1a4a60!important;color:#8abac8!important}.VA-fp.act{border-color:#164e63!important;background:rgba(34,211,238,.06)!important;color:#22d3ee!important}
.VA-fpdot{width:6px!important;height:6px!important;border-radius:50%!important;flex-shrink:0!important;display:inline-block!important}
.VA-slbl{font-size:10px!important;color:#3a5a70!important;letter-spacing:.8px!important;font-weight:600!important;text-transform:uppercase!important}
.VA-sp{font-size:10px!important;font-weight:600!important;cursor:pointer!important;transition:all .15s!important;border:1px solid #152030!important;background:transparent!important;color:#3a6a80!important;border-radius:4px!important;white-space:nowrap!important;letter-spacing:.3px!important}
.VA-sp:hover{color:#6aacbe!important;border-color:#1a4060!important;background:rgba(34,211,238,.02)!important}.VA-sp.act{color:#22d3ee!important;border-color:#164e63!important;background:rgba(8,145,178,.06)!important;box-shadow:0 0 8px rgba(34,211,238,.06)!important}
.VA-tw{overflow-x:auto!important;background:#0a1220!important;scrollbar-width:none!important;-ms-overflow-style:none!important}.VA-tw::-webkit-scrollbar{display:none!important}
.VA-t{width:100%!important;border-collapse:collapse!important;min-width:700px!important;border:none!important}
.VA-t th{text-align:left!important;font-size:11px!important;font-weight:700!important;text-transform:uppercase!important;letter-spacing:1.5px!important;color:#5a7a94!important;background:linear-gradient(180deg,#0c1828,#0a1420)!important;border:none!important;border-bottom:1px solid #152030!important;border-right:1px solid #10182a!important;white-space:nowrap!important;line-height:1!important}
.VA-t th:last-child{text-align:right!important;border-right:none!important}
.VA-t td{border:none!important;border-bottom:1px solid #0e1828!important;border-right:1px solid #0c1420!important;vertical-align:middle!important;line-height:1.3!important;background:transparent!important}.VA-t td:last-child{border-right:none!important}
.VA-t tbody tr{transition:background .15s!important;background:#0a1220!important}.VA-t tbody tr:nth-child(even){background:#0c1628!important}
@media(hover:hover){.VA-t tbody tr:hover{background:#0e1c32!important;box-shadow:inset 2px 0 0 rgba(34,211,238,.15)!important}.VA-sec-non .VA-t tbody tr:hover{box-shadow:inset 2px 0 0 rgba(167,139,250,.15)!important}}
.VA-t .VA-emp td{text-align:center!important;color:#2a4a60!important;font-size:12px!important;letter-spacing:1px!important;background:#0a1220!important;border-right:none!important}
.VA-icon{width:32px!important;height:32px!important;border-radius:50%!important;display:inline-flex!important;align-items:center!important;justify-content:center!important;flex-shrink:0!important;vertical-align:middle!important;box-shadow:0 2px 8px rgba(0,0,0,.3)!important;overflow:hidden!important}
.VA-icon-svg{width:28px!important;height:28px!important;border-radius:0!important;box-shadow:none!important;overflow:visible!important;background:none!important;border:none!important}
.VA-icon-t{font-size:12px!important;font-weight:800!important;color:#fff!important;text-shadow:0 1px 3px rgba(0,0,0,.4)!important;line-height:1!important;letter-spacing:-.5px!important}
.VA-nm-wrap{display:inline-flex!important;align-items:center!important;gap:10px!important;max-width:100%!important;min-width:0!important;overflow:hidden!important}
.VA-nm{font-size:13px!important;font-weight:700!important;color:#d0dce8!important;white-space:nowrap!important;overflow:hidden!important;text-overflow:ellipsis!important;max-width:200px!important;display:inline-block!important;vertical-align:middle!important}
.VA-pr{font-size:13px!important;font-weight:800!important;color:#34d399!important;white-space:nowrap!important;letter-spacing:.2px!important;text-shadow:0 0 8px rgba(52,211,153,.1)!important}
.VA-ded .VA-pr{color:#2a4a60!important}
.VA-pu{font-size:9px!important;color:#1a5a6a!important;font-weight:600!important}
.VA-cy{font-size:12px!important;color:#5a8aaa!important;font-style:italic!important;white-space:nowrap!important}
.VA-mt{display:inline-flex!important;align-items:center!important;gap:6px!important;white-space:nowrap!important;border-radius:4px!important;border:1px solid transparent!important;flex-shrink:0!important}
.VA-mtd{width:7px!important;height:7px!important;border-radius:50%!important;flex-shrink:0!important;display:inline-block!important}
.VA-mtn{font-size:11px!important;font-weight:600!important}
.VA-mtn-grad{background:linear-gradient(90deg,#22c55e,#2dd4a8,#38bdf8)!important;-webkit-background-clip:text!important;background-clip:text!important;-webkit-text-fill-color:transparent!important}
.VA-mtn-goog{background:linear-gradient(90deg,#4285f4,#ea4335,#fbbc04,#0f9d58)!important;-webkit-background-clip:text!important;background-clip:text!important;-webkit-text-fill-color:transparent!important}
.VA-dt{font-size:12px!important;color:#5a8aaa!important;white-space:nowrap!important}
.VA-dtlink{cursor:pointer!important;transition:color .12s!important;text-decoration:none!important}.VA-dtlink:hover{color:#22d3ee!important;text-decoration:underline!important}
.VA-dl{font-size:13px!important;font-weight:800!important;white-space:nowrap!important}.VA-dl-ok{color:#0ea5c0!important}.VA-dl-w{color:#d97706!important}.VA-dl-c{color:#ef4444!important;text-shadow:0 0 6px rgba(239,68,68,.15)!important}
.VA-rsn{font-size:11px!important;font-weight:700!important;letter-spacing:.4px!important}.VA-rsn-e{color:#4a6a80!important}.VA-rsn-c{color:#c04040!important}
.VA-acts{text-align:right!important;white-space:nowrap!important}
.VA-ab{font-size:10px!important;font-weight:600!important;letter-spacing:.5px!important;text-transform:uppercase!important;cursor:pointer!important;transition:all .15s!important;background:transparent!important;display:inline-block!important;border-radius:4px!important}
.VA-ab-e{border:1px solid #1a2a40!important;color:#4a8aa0!important}.VA-ab-e:hover{border-color:#22718a!important;color:#22d3ee!important;box-shadow:0 0 8px rgba(34,211,238,.08)!important}
.VA-ab-can{border:1px solid #2a1828!important;color:#8a4a6a!important}.VA-ab-can:hover{color:#e060a0!important;border-color:#4a2040!important}
.VA-ab-arc{border:1px solid #2a1818!important;color:#7a3a3a!important}.VA-ab-arc:hover{color:#ef4444!important;border-color:#4a1818!important}
.VA-ab-rev{border:1px solid #1a2a40!important;color:#4a8aa0!important}.VA-ab-rev:hover{border-color:#22718a!important;color:#22d3ee!important}
.VA-grace{font-size:9px!important;font-weight:700!important;border:1px solid rgba(217,119,6,.2)!important;color:#d97706!important;cursor:pointer!important;vertical-align:middle!important;background:rgba(217,119,6,.04)!important;border-radius:4px!important}
.VA-cbadge{font-size:8px!important;font-weight:700!important;border:1px solid rgba(224,96,160,.2)!important;color:#e060a0!important;vertical-align:middle!important;background:rgba(224,96,160,.04)!important;border-radius:4px!important;letter-spacing:.4px!important;text-transform:uppercase!important}
.VA-mbg{position:fixed!important;inset:0!important;z-index:9998!important;background:rgba(4,6,12,.9)!important;backdrop-filter:blur(12px)!important;-webkit-backdrop-filter:blur(12px)!important;display:flex!important;align-items:center!important;justify-content:center!important}
.VA-mod{width:100%!important;max-width:420px!important;max-height:calc(100vh - 40px)!important;overflow-y:auto!important;background:linear-gradient(180deg,#0e1828,#0a1220)!important;border:1px solid #1a2a40!important;border-top:2px solid #164e63!important;position:relative!important;border-radius:8px!important;box-shadow:0 12px 48px rgba(0,0,0,.6),0 0 24px rgba(34,211,238,.04)!important;-webkit-overflow-scrolling:touch!important}
.VA-mod::before{content:''!important;position:absolute!important;top:0!important;left:0!important;right:0!important;height:2px!important;background:linear-gradient(90deg,transparent,#22d3ee,transparent)!important;border-radius:8px 8px 0 0!important}
.VA-mtl{font-size:14px!important;font-weight:800!important;letter-spacing:2px!important;text-transform:uppercase!important;color:#22d3ee!important;border-left:3px solid #22d3ee!important;line-height:1!important;text-shadow:0 0 12px rgba(34,211,238,.15)!important}
.VA-fld{display:block!important}.VA-fr{display:flex!important;gap:12px!important}.VA-fr .VA-fld{flex:1!important;min-width:0!important}
.VA-lbl{font-size:10px!important;font-weight:700!important;letter-spacing:1.5px!important;text-transform:uppercase!important;color:#4a7a90!important;display:block!important;line-height:1!important}
.VA-inp{width:100%!important;border:1px solid #1a2a40!important;background:#070b14!important;color:#d0dce8!important;font-size:13px!important;outline:none!important;transition:border-color .15s,box-shadow .15s!important;line-height:1.3!important;height:auto!important;min-height:36px!important;-webkit-appearance:none!important;appearance:none!important;box-shadow:inset 0 1px 3px rgba(0,0,0,.3)!important;border-radius:5px!important}
.VA-inp:focus{border-color:#1a6a80!important;box-shadow:0 0 8px rgba(34,211,238,.06),inset 0 1px 3px rgba(0,0,0,.3)!important}.VA-inp::placeholder{color:#2a4a5e!important;font-size:12px!important}
.VA-ta{width:100%!important;border:1px solid #1a2a40!important;background:#070b14!important;color:#d0dce8!important;font-size:11px!important;outline:none!important;line-height:1.3!important;min-height:60px!important;resize:vertical!important;border-radius:5px!important;font-family:monospace!important;-webkit-appearance:none!important}
.VA-ta:focus{border-color:#1a6a80!important}
select.VA-inp{cursor:pointer!important;background-repeat:no-repeat!important;background-position:right 10px center!important;background-color:#070b14!important}
select.VA-inp option{background:#0a1220!important;color:#d0dce8!important}
input[type="date"].VA-inp{color-scheme:dark!important}
.VA-hint{font-size:10px!important;color:#1a6a80!important;cursor:pointer!important;transition:color .12s!important;display:block!important}.VA-hint:hover{color:#22d3ee!important}
.VA-mft{display:flex!important;justify-content:flex-end!important;gap:8px!important;border-top:1px solid #152030!important}
.VA-ctxt{color:#6a9ab0!important;font-size:13px!important;line-height:1.5!important}.VA-ctxt strong{color:#22d3ee!important;font-weight:700!important}
.VA-cinfo{font-size:11px!important;color:#4a7a90!important;line-height:1.4!important}
.VA-stats{width:100%!important;max-width:550px!important;max-height:calc(100vh - 40px)!important;overflow-y:auto!important;-webkit-overflow-scrolling:touch!important;scroll-behavior:smooth!important;background:#0a1220!important;border:1px solid #1a2a40!important;position:relative!important;border-radius:8px!important;box-shadow:0 12px 48px rgba(0,0,0,.7),0 0 30px rgba(34,211,238,.05)!important}
.VA-stats::before{content:''!important;position:absolute!important;top:0;left:0;right:0;height:2px!important;background:linear-gradient(90deg,transparent,#22d3ee,transparent)!important;z-index:2!important;border-radius:8px 8px 0 0!important}
.VA-sthdr{display:flex!important;align-items:center!important;justify-content:space-between!important;background:linear-gradient(180deg,#0e1c2e,#0b1420)!important;position:sticky!important;top:0!important;z-index:3!important}
.VA-sttl{font-size:15px!important;font-weight:800!important;letter-spacing:2.5px!important;text-transform:uppercase!important;color:#22d3ee!important;text-shadow:0 0 14px rgba(34,211,238,.2)!important}
.VA-stclose{font-size:18px!important;color:#3a5a70!important;cursor:pointer!important;transition:color .15s!important;line-height:1!important}.VA-stclose:hover{color:#22d3ee!important}
.VA-sttabs{display:flex!important;gap:2px!important;background:#070b14!important;position:sticky!important;top:52px!important;z-index:3!important}
.VA-sttab{flex:1!important;text-align:center!important;font-size:10px!important;font-weight:700!important;letter-spacing:1px!important;text-transform:uppercase!important;cursor:pointer!important;color:#3a5a70!important;background:#0a1420!important;transition:all .15s!important;border-bottom:2px solid transparent!important}
.VA-sttab:hover{color:#6a9ab0!important}.VA-sttab.act{color:#22d3ee!important;border-bottom-color:#22d3ee!important;background:#0c1828!important}
.VA-stpanel{display:none!important}.VA-stpanel.act{display:block!important}
.VA-stgrid{display:grid!important;grid-template-columns:1fr 1fr!important;gap:1px!important;background:#070b14!important}
.VA-stcard{background:linear-gradient(180deg,#0c1828,#0a1420)!important;position:relative!important;overflow:hidden!important}
.VA-stcard::after{content:''!important;position:absolute!important;top:0;left:0;width:2px!important;height:100%!important}
.VA-stcard-t::after{background:#0891b2!important}.VA-stcard-g::after{background:#34d399!important}.VA-stcard-p::after{background:#7c3aed!important}.VA-stcard-r::after{background:#ef4444!important}.VA-stcard-y::after{background:#d97706!important}
.VA-stcard-w{grid-column:1/-1!important}
.VA-stlbl{font-size:10px!important;font-weight:700!important;letter-spacing:1.5px!important;text-transform:uppercase!important;color:#4a6a80!important;display:block!important}
.VA-stval{font-size:22px!important;font-weight:800!important;color:#d0dce8!important;line-height:1!important}
.VA-stval-t{color:#22d3ee!important}.VA-stval-g{color:#34d399!important;text-shadow:0 0 10px rgba(52,211,153,.1)!important}.VA-stval-p{color:#a78bfa!important}.VA-stval-y{color:#d97706!important}
.VA-stsub{font-size:10px!important;color:#4a6a80!important;display:block!important}
.VA-bkd-sec{font-size:9px!important;font-weight:700!important;letter-spacing:1.5px!important;text-transform:uppercase!important;color:#3a6a80!important;border-bottom:1px solid #12202e!important}
.VA-bkd-tbl{width:100%!important;border-collapse:collapse!important;border:none!important;table-layout:fixed!important}
.VA-bkd-tbl td{border:none!important;vertical-align:middle!important;white-space:nowrap!important;line-height:1.6!important;background:transparent!important;padding:2px 3px!important}
.VA-bkd-tbl tr{border-bottom:1px solid #0e1828!important}.VA-bkd-tbl tr:last-child{border-bottom:none!important}
.VA-bkd-tbl th{border:none!important;background:transparent!important;padding:0 0 2px!important;font-size:8px!important;font-weight:700!important;color:#3a5a70!important;text-transform:uppercase!important;letter-spacing:1px!important}
.VA-bkd-tbl .bkd-c-ico{width:24px!important}
.VA-bkd-tbl .bkd-c-nm{width:auto!important;overflow:hidden!important;text-overflow:ellipsis!important}
.VA-bkd-tbl .bkd-c-cy{width:90px!important;text-align:center!important}
.VA-bkd-tbl .bkd-c-math{width:100px!important;text-align:right!important}
.VA-bkd-tbl .bkd-c-amt{width:60px!important;text-align:right!important}
.VA-bkd-nm{font-size:13px!important;font-weight:600!important;color:#7aaabe!important;overflow:hidden!important;text-overflow:ellipsis!important}
.VA-bkd-cy{font-size:11px!important;font-weight:600!important;color:#5a8aaa!important;font-style:italic!important}
.VA-bkd-math{font-size:11px!important;font-weight:600!important;color:#3a6a80!important}
.VA-bkd-amt{font-size:13px!important;font-weight:800!important;color:#34d399!important}
.VA-pie-wrap{display:flex!important;gap:16px!important;align-items:flex-start!important}
.VA-pie-svg-wrap{flex-shrink:0!important;position:relative!important}
.VA-pie-deco{position:absolute!important;border-radius:50%!important;pointer-events:none!important}
.VA-pie-center{position:absolute!important;top:50%!important;left:50%!important;transform:translate(-50%,-50%)!important;text-align:center!important;pointer-events:none!important}
.VA-pie-ct-val{font-size:22px!important;font-weight:800!important;color:#d0dce8!important;display:block!important;line-height:1!important}
.VA-pie-ct-lbl{font-size:8px!important;font-weight:700!important;color:#4a6a80!important;letter-spacing:1.5px!important;text-transform:uppercase!important;display:block!important;margin-top:2px!important}
.VA-pie-ct-sub{font-size:9px!important;color:#3a6a80!important;display:block!important;margin-top:3px!important}
.VA-pie-leg{flex:1!important;min-width:0!important;overflow-y:auto!important;max-height:230px!important;scrollbar-width:none!important;-ms-overflow-style:none!important}.VA-pie-leg::-webkit-scrollbar{display:none!important}
.VA-pie-item{display:flex!important;align-items:center!important;gap:6px!important;border-radius:4px!important;transition:background .15s,box-shadow .15s!important;cursor:default!important}
.VA-pie-item.VA-pie-hl{background:rgba(34,211,238,.06)!important;box-shadow:inset 2px 0 0 var(--hl-color,#22d3ee)!important}
.VA-pie-dot{width:8px!important;height:8px!important;border-radius:50%!important;flex-shrink:0!important}
.VA-pie-ico{flex-shrink:0!important}
.VA-pie-nm{font-size:11px!important;color:#7aaabe!important;flex:1!important;overflow:hidden!important;text-overflow:ellipsis!important;white-space:nowrap!important}
.VA-pie-val{font-size:11px!important;font-weight:700!important;color:#34d399!important;flex-shrink:0!important}
.VA-pie-seg{cursor:pointer!important;transition:stroke-width .2s,filter .2s,opacity .15s!important}
.VA-chtog{display:inline-flex!important;gap:2px!important;background:#070b14!important;border:1px solid #152030!important;border-radius:4px!important;overflow:hidden!important}
.VA-chtog-b{font-size:9px!important;font-weight:700!important;letter-spacing:.8px!important;text-transform:uppercase!important;cursor:pointer!important;color:#3a5a70!important;background:transparent!important;transition:all .15s!important;border:none!important}
.VA-chtog-b.act{color:#22d3ee!important;background:#0c1828!important}.VA-chtog-b:hover{color:#6a9ab0!important}
.VA-costbar{display:flex!important;align-items:center!important;gap:4px!important;border-bottom:1px solid #0e1828!important}.VA-costbar:last-child{border-bottom:none!important}
.VA-costbar-ico{flex-shrink:0!important;width:22px!important;max-width:22px!important;display:inline-flex!important;justify-content:center!important;overflow:hidden!important}.VA-costbar-ico img{max-width:100%!important}
.VA-costbar-nm{font-size:10px!important;font-weight:600!important;color:#7aaabe!important;width:70px!important;text-align:right!important;overflow:hidden!important;text-overflow:ellipsis!important;white-space:nowrap!important;flex-shrink:0!important;margin-left:0!important}
.VA-costbar-bg{flex:1!important;height:14px!important;background:#070b14!important;border:1px solid #12202e!important;border-radius:3px!important;overflow:hidden!important}
.VA-costbar-fill{height:100%!important;border-radius:2px!important;transition:width .5s ease-out!important}
.VA-costbar-val{font-size:10px!important;font-weight:700!important;color:#34d399!important;width:50px!important;flex-shrink:0!important}
.VA-mpill{display:inline-flex!important;align-items:center!important;gap:6px!important;background:#070b14!important;border:1px solid #152030!important;border-radius:20px!important;transition:border-color .15s!important}.VA-mpill:hover{border-color:#1a3a50!important}
.VA-mpill-dot{width:8px!important;height:8px!important;border-radius:50%!important;flex-shrink:0!important}
.VA-mpill-nm{font-size:11px!important;font-weight:600!important;color:#7aaabe!important}
.VA-mpill-ct{font-size:11px!important;font-weight:800!important;color:#22d3ee!important}
.VA-curbar{display:flex!important;align-items:center!important;gap:8px!important}
.VA-curbar-sym{font-size:14px!important;font-weight:800!important;color:#5a8aa0!important;width:32px!important;text-align:center!important;flex-shrink:0!important}
.VA-curbar-bg{flex:1!important;height:10px!important;background:#070b14!important;border:1px solid #12202e!important;border-radius:5px!important;overflow:hidden!important}
.VA-curbar-fill{height:100%!important;border-radius:5px!important;background:linear-gradient(90deg,#0891b2,#22d3ee)!important;transition:width .5s ease-out!important}
.VA-curbar-ct{font-size:10px!important;font-weight:700!important;color:#4a6a80!important;width:16px!important;flex-shrink:0!important}
.VA-li{display:flex!important;align-items:center!important;gap:10px!important;background:#070b14!important;border:1px solid #152030!important;border-radius:5px!important;transition:border-color .15s!important}.VA-li:hover{border-color:#1a3a50!important}
.VA-lin{flex:1!important;font-size:12px!important;color:#d0dce8!important;font-weight:600!important}
.VA-lix{font-size:18px!important;color:#4a2a2a!important;cursor:pointer!important;transition:color .12s!important;line-height:1!important}.VA-lix:hover{color:#ef4444!important}
.VA-lar{display:flex!important;gap:8px!important}
.VA-sdiv{height:1px!important;background:linear-gradient(90deg,transparent,#152030 20%,#1a3048 50%,#152030 80%,transparent)!important;position:relative!important;z-index:1!important}
.VA-stft{background:#070b14!important;border-top:1px solid #12202e!important;text-align:center!important}
.VA-stft-txt{font-size:10px!important;color:#2a4a60!important;letter-spacing:.8px!important}
@media(max-width:600px){
.VA-t{min-width:0!important}.VA-t thead{display:none!important}
.VA-t tbody tr{display:flex!important;flex-wrap:wrap!important;padding:8px 12px!important;margin:3px 6px!important;border:1px solid #152030!important;border-radius:6px!important;background:#0c1628!important;gap:0!important;align-items:center!important;box-shadow:none!important;cursor:pointer!important;transition:background .15s!important;overflow:hidden!important}
.VA-t tbody tr.VA-card-open{padding:10px 12px!important;gap:6px 14px!important}
.VA-t td{display:none!important;border:none!important;padding:2px 0!important;align-items:center!important;flex-direction:column!important}
.VA-t td::before{content:attr(data-label)!important;font-size:8px!important;font-weight:700!important;color:#3a5a70!important;text-transform:uppercase!important;letter-spacing:1px!important;display:block!important;margin-bottom:1px!important;align-self:flex-start!important}
.VA-t td[data-label=""]::before{display:none!important}
.VA-t td:first-child{display:inline-flex!important;flex:1!important;flex-direction:row!important;min-width:0!important;overflow:hidden!important}.VA-t td:first-child::before{display:none!important}
.VA-t td[data-label="Price"]{display:inline-flex!important;flex-direction:row!important;flex-shrink:0!important}.VA-t td[data-label="Price"]::before{display:none!important}
.VA-t td[data-label="Method"]{display:inline-flex!important;flex-direction:row!important;flex-shrink:0!important;max-width:40%!important;overflow:hidden!important}.VA-t td[data-label="Method"]::before{display:none!important}
.VA-card-open td{display:inline-flex!important}
.VA-card-open td:first-child{flex-basis:100%!important}
.VA-card-open .VA-nm{max-width:none!important;white-space:normal!important;overflow:visible!important;text-overflow:unset!important}
.VA-card-open td:last-child{flex-basis:100%!important;flex-direction:row!important;justify-content:center!important;gap:8px!important;border-top:1px solid #12202e!important;padding-top:6px!important;margin-top:4px!important}.VA-card-open td:last-child::before{display:none!important}
.VA-nm{max-width:120px!important}
.VA-hdr{padding:14px 14px 10px!important}
.VA-btns{width:100%!important;justify-content:flex-start!important}
.VA-tb{padding:8px 12px!important}.VA-srch{width:100%!important;flex:1!important}
.VA-metog{display:inline-flex!important}
.VA-stats{max-width:calc(100vw - 16px)!important;max-height:calc(100vh - 60px)!important;margin:30px 8px 8px!important}
.VA-sthdr{padding-top:8px!important}
.VA-sttabs{top:44px!important}
.VA-pie-wrap{flex-direction:column!important;align-items:center!important}
.VA-pie-leg{max-height:none!important}
}
body.st-app-mode .view-header{display:none!important}
body.st-app-mode .mobile-toolbar{display:none!important}
body.st-app-mode .mobile-navbar{display:none!important}
body.st-app-mode .mobile-navbar-actions{display:none!important}
body.st-app-mode .workspace-drawer{display:none!important}
body.st-app-mode .status-bar{display:none!important}
body.st-app-mode .workspace-tab-header-container{display:none!important}
body.st-app-mode .workspace-ribbon{display:none!important}
body.st-app-mode .workspace-split.mod-root{background:#070b14!important;width:100%!important}
body.st-app-mode .workspace-split.mod-root .view-content{padding:0!important;background:#070b14!important}
body.st-app-mode .workspace-split.mod-root .markdown-reading-view{padding:0!important;max-width:100%!important;width:100%!important;background:#070b14!important}
body.st-app-mode .workspace-split.mod-root .markdown-preview-view{padding:0!important;max-width:100%!important;width:100%!important;background:#070b14!important}
body.st-app-mode .workspace-split.mod-root .markdown-preview-sizer{padding:0!important;max-width:100%!important;width:100%!important;margin:0!important}
body.st-app-mode .workspace-split.mod-root .markdown-preview-section{padding:0!important;width:100%!important}
body.st-app-mode .workspace-split.mod-root .mod-header{display:none!important}
body.st-app-mode .workspace-split.mod-root .workspace-leaf-content[data-type='markdown']{padding:0!important;background:#070b14!important}
body.st-app-mode .workspace-split.mod-root .workspace-leaf-content{width:100%!important;background:#070b14!important}
body.st-app-mode .workspace-split.mod-root .workspace-leaf{width:100%!important;background:#070b14!important}
body.st-app-mode .workspace-split.mod-root .cm-sizer{max-width:100%!important;padding:0!important}
body.st-app-mode .workspace-split.mod-root .cm-contentContainer{max-width:100%!important}
body.st-app-mode .workspace-split.mod-root .workspace-leaf-resize-handle{display:none!important}
body.st-app-mode .block-language-dataviewjs{padding:0!important;margin:0!important;width:100%!important}
body.st-app-mode #STA{border:none!important;border-radius:0!important;min-height:100vh!important;padding-top:env(safe-area-inset-top,20px)!important;padding-bottom:20px!important}
body.st-app-mode.is-mobile [class*='bottom-bar']{display:none!important}
body.st-app-mode.is-mobile [class*='navbar']{display:none!important}
.VA-guide-pg{display:none!important}.VA-guide-pg.act{display:block!important}
.VA-guide-ico{font-size:36px!important;display:block!important;text-align:center!important;margin-bottom:10px!important;filter:grayscale(0)!important}
.VA-guide-ttl{font-size:15px!important;font-weight:800!important;color:#22d3ee!important;text-align:center!important;letter-spacing:1.5px!important;text-transform:uppercase!important;margin-bottom:10px!important;text-shadow:0 0 12px rgba(34,211,238,.2)!important}
.VA-guide-body{font-size:12px!important;color:#8aa8c0!important;line-height:1.7!important;text-align:left!important}
.VA-guide-body b{color:#c0dce8!important;font-weight:700!important}
.VA-guide-body .g-hl{color:#22d3ee!important;font-weight:700!important}
.VA-guide-body .g-step{display:flex!important;gap:8px!important;margin:6px 0!important;align-items:flex-start!important}
.VA-guide-body .g-num{background:linear-gradient(180deg,#0e2a3e,#081828)!important;color:#22d3ee!important;font-size:10px!important;font-weight:800!important;min-width:20px!important;height:20px!important;display:flex!important;align-items:center!important;justify-content:center!important;border-radius:50%!important;border:1px solid #164e63!important;flex-shrink:0!important;margin-top:1px!important}
.VA-guide-nav{display:flex!important;justify-content:space-between!important;align-items:center!important;margin-top:16px!important;padding-top:12px!important;border-top:1px solid #12202e!important}
.VA-guide-dots{display:flex!important;gap:6px!important}
.VA-guide-dot{width:7px!important;height:7px!important;border-radius:50%!important;background:#1a2a40!important;transition:all .2s!important}
.VA-guide-dot.act{background:#22d3ee!important;box-shadow:0 0 6px rgba(34,211,238,.3)!important}
`;
  document.head.appendChild(sty);

  let root=document.getElementById('STA');
  if(!root){root=document.createElement('div');root.id='STA';dv.container.appendChild(root);}else root.innerHTML='';
  function setAppMode(on){ST.appMode=on;if(on)document.body.classList.add('st-app-mode');else document.body.classList.remove('st-app-mode');}
  if(ST.appMode)document.body.classList.add('st-app-mode');
  if(!window.__stAppCleanup){window.__stAppCleanup=true;app.workspace.on('active-leaf-change',function(){var af=app.workspace.getActiveFile();if(!af||af.path!==cf.path){document.body.classList.remove('st-app-mode');}else if(ST.appMode){document.body.classList.add('st-app-mode');}});}

  let mo=false;let __jf=false;
  function openM(fn){if(mo)return;mo=true;const bg=document.createElement('div');bg.className='VA-mbg';bg.style.cssText='padding:14px !important';const cd=document.createElement('div');cd.className='VA-mod';cd.style.cssText='padding:22px !important';function cl(){bg.remove();mo=false;}bg.addEventListener('click',e=>{if(e.target===bg)cl();});cd.addEventListener('click',e=>e.stopPropagation());fn(cd,cl);bg.appendChild(cd);document.body.appendChild(bg);}
  function selO(arr,sel){return arr.map(v=>'<option value="'+v+'" '+(v===sel?'selected':'')+'>'+v+'</option>').join('');}

  function openAE(es){
    const ie=!!es;const sub=ie?{...es}:{name:'',price:'',currency:DEF_CUR,method:'',type:'recurring',cycle:'monthly',started:td(),nextDate:'',status:'active',icon:'',color:COLORS[4].v,category:''};
    if(!sub.cycle)sub.cycle='monthly';if(!sub.icon)sub.icon='';if(!sub.color)sub.color=COLORS[4].v;if(!sub.category)sub.category='';
    openM((cd,cl)=>{
      function bld(){
        const ir=sub.type==='recurring';const sugDate=sub.started?adv(sub.started,sub.cycle||'monthly'):'';
        const colorOpts=COLORS.map(c=>'<option value="'+c.v+'" '+(c.v===sub.color?'selected':'')+'>'+c.n+'</option>').join('');
        const curIcoMode=sub.icon?(sub.icon.startsWith('<')?'svg':(sub.icon.match(/\.(svg|png|jpg|jpeg|webp)$/i)?'image':'emoji')):'none';
        cd.innerHTML='<div class="VA-mtl" style="padding-left:12px !important;margin-bottom:18px !important">'+(ie?'Edit':'New')+' Subscription</div>'+
          '<div class="VA-fld" style="margin-bottom:12px !important"><label class="VA-lbl" style="margin-bottom:5px !important">Name</label><input class="VA-inp" id="sf-n" type="text" autocomplete="off" style="padding:9px 12px !important" /></div>'+
          '<div class="VA-fr" style="margin-bottom:12px !important"><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">Price</label><input class="VA-inp" id="sf-p" type="number" step="0.01" value="'+sub.price+'" autocomplete="off" style="padding:9px 12px !important" /></div><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">Currency</label><select class="VA-inp" id="sf-cur" style="padding:9px 26px 9px 12px !important">'+selO(D.currencies,sub.currency)+'</select></div></div>'+
          '<div class="VA-fld" style="margin-bottom:12px !important"><label class="VA-lbl" style="margin-bottom:5px !important">Payment Method</label><select class="VA-inp" id="sf-m" style="padding:9px 26px 9px 12px !important"><option value=""></option>'+selO(D.methods,sub.method)+'</select></div>'+
          '<div class="VA-fld" style="margin-bottom:12px !important"><label class="VA-lbl" style="margin-bottom:5px !important">Category</label><select class="VA-inp" id="sf-cat" style="padding:9px 26px 9px 12px !important"><option value="">— none —</option>'+selO(D.categories,sub.category)+'</select></div>'+
          '<div class="VA-fr" style="margin-bottom:12px !important"><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">Type</label><select class="VA-inp" id="sf-ty" style="padding:9px 26px 9px 12px !important"><option value="recurring" '+(sub.type==='recurring'?'selected':'')+'>Recurring</option><option value="non-recurring" '+(sub.type==='non-recurring'?'selected':'')+'>Non-recurring</option></select></div><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">Cycle</label><select class="VA-inp" id="sf-cy" style="padding:9px 26px 9px 12px !important"><option value="monthly" '+(sub.cycle==='monthly'?'selected':'')+'>Monthly</option><option value="yearly" '+(sub.cycle==='yearly'?'selected':'')+'>Yearly</option><option value="weekly" '+(sub.cycle==='weekly'?'selected':'')+'>Weekly</option><option value="quarterly" '+(sub.cycle==='quarterly'?'selected':'')+'>Every 3 Months</option><option value="biannual" '+(sub.cycle==='biannual'?'selected':'')+'>Every 6 Months</option></select></div></div>'+
          '<div class="VA-fr" style="margin-bottom:12px !important"><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">Started</label><input class="VA-inp" id="sf-ds" type="date" value="'+sub.started+'" style="padding:9px 12px 9px 28px !important" /></div><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">'+(ir?'Renews':'Ends')+'</label><input class="VA-inp" id="sf-nd" type="date" value="'+sub.nextDate+'" style="padding:9px 12px 9px 28px !important" />'+(sugDate&&!sub.nextDate?'<div class="VA-hint" style="margin-top:4px !important" id="sf-hint">\u21B3 '+fD(sugDate)+' \u2014 click to apply</div>':'')+'</div></div>'+
          '<div class="VA-fr" style="margin-bottom:12px !important;align-items:flex-end!important"><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">Color</label><select class="VA-inp" id="sf-clr" style="padding:9px 26px 9px 12px !important">'+colorOpts+'</select></div><div class="VA-fld"><label class="VA-lbl" style="margin-bottom:5px !important">Icon</label><select class="VA-inp" id="sf-icomode" style="padding:9px 26px 9px 12px !important"><option value="none" '+(curIcoMode==='none'?'selected':'')+'>None (monogram)</option><option value="emoji" '+(curIcoMode==='emoji'?'selected':'')+'>Emoji</option><option value="svg" '+(curIcoMode==='svg'?'selected':'')+'>SVG Code</option><option value="image" '+(curIcoMode==='image'?'selected':'')+'>Vault Image</option></select></div></div>'+
          '<div id="sf-icowrap" style="margin-bottom:12px !important"></div>'+
          '<div id="sf-preview" style="margin-bottom:14px !important;display:flex!important;align-items:center!important;gap:10px!important"></div>'+
          '<div class="VA-mft" style="margin-top:16px !important;padding-top:14px !important"><div class="VA-b VA-b-g" id="sf-x" style="padding:8px 16px !important">Cancel</div><div class="VA-b VA-b-add" id="sf-s" style="padding:8px 16px !important"><span class="VA-bi">\u2295</span> Save</div></div>';
        const nameInp=cd.querySelector('#sf-n');nameInp.value=sub.name;
        function getIcoVal(){const el=cd.querySelector('#sf-ico');return el?el.value.trim():'';}
        function updIcoArea(){
          const mode=cd.querySelector('#sf-icomode').value;const w=cd.querySelector('#sf-icowrap');
          if(mode==='emoji'){w.innerHTML='<div class="VA-fld"><input class="VA-inp" id="sf-ico" type="text" placeholder="Paste emoji" autocomplete="off" style="padding:9px 12px !important;font-size:18px!important" /></div>';const ei=w.querySelector('#sf-ico');ei.value=(curIcoMode==='emoji'?sub.icon:'');ei.addEventListener('input',updPreview);}
          else if(mode==='svg'){w.innerHTML='<div class="VA-fld"><label class="VA-lbl" style="margin-bottom:4px!important;font-size:9px!important">SVG Code</label><textarea class="VA-ta" id="sf-ico" rows="3" placeholder="Paste SVG code" style="padding:8px!important"></textarea></div>';const ti=w.querySelector('#sf-ico');ti.value=(curIcoMode==='svg'?sub.icon:'');ti.addEventListener('input',updPreview);}
          else if(mode==='image'){w.innerHTML='<div class="VA-fld"><label class="VA-lbl" style="margin-bottom:4px!important;font-size:9px!important">Vault Image Path</label><input class="VA-inp" id="sf-ico" type="text" placeholder="e.g. icons/spotify.png" autocomplete="off" style="padding:9px 12px !important" /></div>';const ii=w.querySelector('#sf-ico');ii.value=(curIcoMode==='image'?sub.icon:'');ii.addEventListener('input',updPreview);}
          else{w.innerHTML='';}
          updPreview();
        }
        function updPreview(){
          const pv=cd.querySelector('#sf-preview');const nm=cd.querySelector('#sf-n').value||'Name';const clr=cd.querySelector('#sf-clr').value;const icoVal=getIcoVal();
          pv.innerHTML='<span style="font-size:10px!important;color:#3a5a70!important;font-weight:700!important;letter-spacing:1px!important;text-transform:uppercase!important">Preview:</span>'+subIcon(nm,icoVal,clr)+'<span style="font-size:13px!important;color:#d0dce8!important;font-weight:700!important">'+nm+'</span>';
        }
        updIcoArea();
        cd.querySelector('#sf-icomode').addEventListener('change',()=>{const mode=cd.querySelector('#sf-icomode').value;if(mode==='none'){sub.icon='';cd.querySelector('#sf-icowrap').innerHTML='';updPreview();return;}updIcoArea();});
        cd.querySelector('#sf-clr').addEventListener('change',updPreview);
        cd.querySelector('#sf-n').addEventListener('input',updPreview);
        cd.querySelector('#sf-hint')?.addEventListener('click',()=>{cd.querySelector('#sf-nd').value=sugDate;cd.querySelector('#sf-hint')?.remove();});
        cd.querySelector('#sf-ty').addEventListener('change',e=>{sub.type=e.target.value;sub.name=cd.querySelector('#sf-n').value;sub.price=cd.querySelector('#sf-p').value;sub.currency=cd.querySelector('#sf-cur').value;sub.method=cd.querySelector('#sf-m').value;sub.started=cd.querySelector('#sf-ds').value;sub.nextDate=cd.querySelector('#sf-nd').value;sub.cycle=cd.querySelector('#sf-cy').value;sub.color=cd.querySelector('#sf-clr').value;sub.icon=getIcoVal();bld();});
        cd.querySelector('#sf-cy').addEventListener('change',e=>{sub.cycle=e.target.value;sub.name=cd.querySelector('#sf-n').value;sub.price=cd.querySelector('#sf-p').value;sub.currency=cd.querySelector('#sf-cur').value;sub.method=cd.querySelector('#sf-m').value;sub.started=cd.querySelector('#sf-ds').value;sub.nextDate='';sub.type=cd.querySelector('#sf-ty').value;sub.color=cd.querySelector('#sf-clr').value;sub.icon=getIcoVal();bld();});
        cd.querySelector('#sf-ds')?.addEventListener('change',e=>{sub.started=e.target.value;sub.name=cd.querySelector('#sf-n').value;sub.price=cd.querySelector('#sf-p').value;sub.currency=cd.querySelector('#sf-cur').value;sub.method=cd.querySelector('#sf-m').value;sub.nextDate='';sub.type=cd.querySelector('#sf-ty').value;sub.cycle=cd.querySelector('#sf-cy').value;sub.color=cd.querySelector('#sf-clr').value;sub.icon=getIcoVal();bld();});
        cd.querySelector('#sf-x').addEventListener('click',cl);
        cd.querySelector('#sf-s').addEventListener('click',async()=>{
          const nm=cd.querySelector('#sf-n').value.trim();if(!nm){cd.querySelector('#sf-n').style.borderColor='#ef4444';return;}
          const mt=cd.querySelector('#sf-m').value;if(!mt){cd.querySelector('#sf-m').style.borderColor='#ef4444';return;}
          const ty=cd.querySelector('#sf-ty').value;let nD=cd.querySelector('#sf-nd').value;const cy=cd.querySelector('#sf-cy').value||'monthly';
          if(!nD&&cd.querySelector('#sf-ds').value)nD=adv(cd.querySelector('#sf-ds').value,cy);
          const icoVal=getIcoVal();const clr=cd.querySelector('#sf-clr').value;const cat=cd.querySelector('#sf-cat').value||'';
          const o={id:ie?sub.id:gid(),name:nm,price:parseFloat(cd.querySelector('#sf-p').value)||0,currency:cd.querySelector('#sf-cur').value||DEF_CUR,method:mt,type:ty,cycle:cy,started:cd.querySelector('#sf-ds').value||td(),nextDate:nD||'',status:'active',color:clr,category:cat};
          if(icoVal)o.icon=icoVal;
          if(ie&&es.cancelled)o.cancelled=es.cancelled;
          const subs=rd().subs;if(ie){const i=subs.findIndex(s=>s.id===sub.id);if(i>=0)subs[i]={...subs[i],...o};if(!icoVal&&subs[i]){delete subs[i].icon;}}else subs.push(o);
          await sv(subs);D=rd();cl();setTimeout(renderAll,150);
        });
      }bld();
    });
  }

  function openCancel(sub){openM((cd,cl)=>{
    const hasTime=sub.nextDate&&sub.nextDate>=nw;
    cd.innerHTML='<div class="VA-mtl" style="padding-left:12px !important;margin-bottom:14px !important">Cancel Renewal</div><div class="VA-ctxt" style="margin-bottom:14px !important">Stop recurring payments for <strong>'+sub.name+'</strong>?'+(hasTime?'<div class="VA-cinfo" style="margin-top:5px !important">Access until <strong>'+fD(sub.nextDate)+'</strong>. Moves to Non-Recurring.</div>':'')+'</div><div class="VA-mft" style="margin-top:14px !important;padding-top:12px !important"><div class="VA-b VA-b-g" id="cc-n" style="padding:8px 16px !important">Keep</div><div class="VA-b VA-b-d" id="cc-y" style="padding:8px 16px !important">Cancel</div></div>';
    cd.querySelector('#cc-n').addEventListener('click',cl);
    cd.querySelector('#cc-y').addEventListener('click',async()=>{const subs=rd().subs;const s=subs.find(x=>x.id===sub.id);if(s){if(hasTime){s.type='non-recurring';s.cancelled=true;}else{s.status='dead';s.deathDate=td();s.deathReason='cancelled';}}await sv(subs);D=rd();cl();setTimeout(renderAll,150);});
  });}

  function openArchive(sub){openM((cd,cl)=>{
    cd.innerHTML='<div class="VA-mtl" style="padding-left:12px !important;margin-bottom:14px !important">Archive</div><div class="VA-ctxt" style="margin-bottom:14px !important">Archive <strong>'+sub.name+'</strong>?</div><div class="VA-mft" style="margin-top:14px !important;padding-top:12px !important"><div class="VA-b VA-b-g" id="aa-n" style="padding:8px 16px !important">Keep</div><div class="VA-b VA-b-d" id="aa-y" style="padding:8px 16px !important">Archive</div></div>';
    cd.querySelector('#aa-n').addEventListener('click',cl);
    cd.querySelector('#aa-y').addEventListener('click',async()=>{const subs=rd().subs;const s=subs.find(x=>x.id===sub.id);if(s){s.status='dead';s.deathDate=td();s.deathReason='cancelled';}await sv(subs);D=rd();cl();setTimeout(renderAll,150);});
  });}

  function openCatPicker(sub){openM((cd,cl)=>{
    const cats=D.categories||[];
    const pills=cats.map(c=>'<span class="VA-catpill'+(sub.category===c?' act':'')+'" style="padding:8px 14px !important;margin:3px !important;font-size:11px!important;font-weight:700!important;letter-spacing:.5px!important;cursor:pointer!important;border-radius:4px!important;background:'+(sub.category===c?'rgba(167,139,250,.15)':'#070b14')+'!important;color:'+(sub.category===c?'#a78bfa':'#5a8aa0')+'!important;border:1px solid '+(sub.category===c?'rgba(167,139,250,.3)':'#152030')+'!important;transition:all .15s!important;display:inline-block!important" data-cv="'+c+'">'+c+'</span>').join('');
    const nonePill='<span class="VA-catpill'+((!sub.category)?' act':'')+'" style="padding:8px 14px !important;margin:3px !important;font-size:11px!important;font-weight:700!important;letter-spacing:.5px!important;cursor:pointer!important;border-radius:4px!important;background:'+((!sub.category)?'rgba(167,139,250,.15)':'#070b14')+'!important;color:'+((!sub.category)?'#a78bfa':'#5a8aa0')+'!important;border:1px solid '+((!sub.category)?'rgba(167,139,250,.3)':'#152030')+'!important;transition:all .15s!important;display:inline-block!important" data-cv="">— none —</span>';
    cd.innerHTML='<div class="VA-mtl" style="padding-left:12px !important;margin-bottom:14px !important">Set Category</div><div class="VA-ctxt" style="margin-bottom:14px !important">Choose a category for <strong>'+sub.name+'</strong></div><div style="display:flex!important;flex-wrap:wrap!important;gap:0!important;margin-bottom:14px!important">'+nonePill+pills+'</div><div class="VA-mft" style="margin-top:12px !important;padding-top:12px !important"><div class="VA-b VA-b-g" id="cp-x" style="padding:8px 16px !important">Cancel</div></div>';
    cd.querySelector('#cp-x').addEventListener('click',cl);
    cd.querySelectorAll('[data-cv]').forEach(el=>{el.addEventListener('click',async()=>{const subs=rd().subs;const s=subs.find(x=>x.id===sub.id);if(s){s.category=el.dataset.cv||'';}await sv(subs);D=rd();cl();setTimeout(renderAll,150);});});
  });}

  function openLE(title,key){openM((cd,cl)=>{
    let items=[...D[key]];
    let mClrs=D.mColors?{...D.mColors}:{};
    const isM=key==='methods';
    const locked=['Google Pay','Kazawallet Card'];
    function ren(){
      const rows=items.map((m,i)=>{const mc=isM?gmc(m):{dot:'#6b7280'};const isLocked=isM&&locked.includes(m);return'<div class="VA-li" style="padding:10px 14px !important;margin-bottom:4px !important">'+(isM?'<span class="VA-mpill-dot" style="width:12px!important;height:12px!important;border-radius:50%!important;background:'+mc.dot+'!important;flex-shrink:0!important;box-shadow:0 0 4px '+mc.dot+'44!important"></span>':'')+'<span class="VA-lin">'+m+'</span>'+(isM?'<input type="color" value="'+mc.dot+'" data-ci="'+i+'" '+(isLocked?'disabled title="Locked"':'')+' style="width:28px!important;height:22px!important;padding:0!important;border:1px solid #1a2a40!important;background:#070b14!important;cursor:'+(isLocked?'not-allowed':'pointer')+'!important;border-radius:3px!important;-webkit-appearance:none!important;appearance:none!important;flex-shrink:0!important" />':'')+'<span class="VA-lix" data-i="'+i+'">\u00D7</span></div>';}).join('');
      cd.innerHTML='<div class="VA-mtl" style="padding-left:12px !important;margin-bottom:14px !important">'+title+'</div><div>'+rows+'</div><div class="VA-lar" style="margin-top:10px !important;margin-bottom:14px !important"><input class="VA-inp" id="le-n" type="text" placeholder="Name" style="flex:1 !important;padding:8px 12px !important" autocomplete="off" />'+(isM?'<input type="color" id="le-clr" value="#6b7280" style="width:34px!important;height:36px!important;padding:0!important;border:1px solid #1a2a40!important;background:#070b14!important;cursor:pointer!important;border-radius:4px!important;-webkit-appearance:none!important;flex-shrink:0!important" />':'')+'<div class="VA-b VA-b-add" id="le-a" style="padding:8px 14px !important"><span class="VA-bi">\u2295</span> Add</div></div><div class="VA-mft" style="margin-top:12px !important;padding-top:12px !important"><div class="VA-b VA-b-add" id="le-d" style="padding:8px 16px !important">Done</div></div>';
      cd.querySelectorAll('[data-i]').forEach(el=>{el.addEventListener('click',()=>{const nm=items[+el.dataset.i];items.splice(+el.dataset.i,1);if(isM&&mClrs[nm])delete mClrs[nm];ren();});});
      if(isM){cd.querySelectorAll('[data-ci]').forEach(el=>{el.addEventListener('input',e=>{const nm=items[+el.dataset.ci];mClrs[nm]=e.target.value;const dot=el.parentElement.querySelector('.VA-mpill-dot');if(dot){dot.style.background=e.target.value+'!important';dot.style.boxShadow='0 0 4px '+e.target.value+'44';}});});}
      cd.querySelector('#le-a').addEventListener('click',()=>{const v=cd.querySelector('#le-n').value.trim();if(v&&!items.includes(v)){items.push(v);if(isM){const clrInp=cd.querySelector('#le-clr');if(clrInp)mClrs[v]=clrInp.value;}ren();}});
      cd.querySelector('#le-n').addEventListener('keydown',e=>{if(e.key==='Enter')cd.querySelector('#le-a').click();});
      cd.querySelector('#le-d').addEventListener('click',async()=>{const subs=rd().subs;await sv(subs,key==='methods'?items:D.methods,key==='currencies'?items:D.currencies,isM?mClrs:D.mColors,D.exRates,key==='categories'?items:D.categories);D=rd();cl();setTimeout(renderAll,150);});
    }ren();
  });}

  function openExRates(){openM((cd,cl)=>{
    var rates={};D.currencies.forEach(function(c){rates[c]=D.exRates[c]||'';});
    function ren(){
      var rows=D.currencies.filter(function(c){return c!=='$';}).map(function(c){return'<div class="VA-li" style="padding:10px 14px !important;margin-bottom:4px !important"><span class="VA-lin" style="min-width:50px!important;font-weight:700!important;color:#22d3ee!important;flex-shrink:0!important">'+c+'</span><span style="font-size:10px!important;color:#3a5a70!important;flex:1!important;text-align:right!important;padding-right:6px!important">= $1</span><input class="VA-inp" type="number" step="any" value="'+(rates[c]||'')+'" data-rc="'+c+'" placeholder="Rate per $1" style="width:100px!important;padding:6px 8px!important;text-align:right!important;flex-shrink:0!important" autocomplete="off" /></div>';}).join('');
      cd.innerHTML='<div class="VA-mtl" style="padding-left:12px !important;margin-bottom:6px !important">Exchange Rates</div><div style="padding:0 0 6px!important;margin-bottom:10px!important"><span style="font-size:10px!important;color:#4a6a80!important;display:block!important;padding-left:12px!important">Units of each currency per $1 USD</span></div><div>'+rows+'</div><div class="VA-mft" style="margin-top:12px !important;padding-top:12px !important"><div class="VA-b VA-b-g" id="er-x" style="padding:8px 16px !important">Cancel</div><div class="VA-b VA-b-add" id="er-s" style="padding:8px 16px !important">Save</div></div>';
      cd.querySelector('#er-x').addEventListener('click',cl);
      cd.querySelector('#er-s').addEventListener('click',async function(){cd.querySelectorAll('[data-rc]').forEach(function(inp){var v=parseFloat(inp.value);if(v&&v>0)rates[inp.dataset.rc]=v;else delete rates[inp.dataset.rc];});var subs=rd().subs;await sv(subs,D.methods,D.currencies,D.mColors,rates);D=rd();cl();setTimeout(renderAll,150);});
    }ren();
  });}

  function openGuide(){openM(function(cd,cl){
    var pg=0;
    var pages=[
      {ico:'\u2728',ttl:'Welcome',body:'<b>Subscription Tracker</b> is a privacy-first subscription manager that lives entirely inside your Obsidian vault.<div style="margin:10px 0!important"><div class="g-step"><span class="g-num">\u2713</span><span><b>100% Local</b> \u2014 your data never leaves your device</span></div><div class="g-step"><span class="g-num">\u2713</span><span><b>No accounts</b> \u2014 no sign-ups, no servers, no tracking</span></div><div class="g-step"><span class="g-num">\u2713</span><span><b>Fully yours</b> \u2014 stored as plain text in your vault</span></div></div><span style="color:#3a6a80!important;font-size:11px!important">Use the arrows below to walk through the guide.</span>'},
      {ico:'\u2795',ttl:'Adding Subscriptions',body:'Tap <span class="g-hl">\u2295 Add</span> to create a new subscription.<div style="margin:8px 0!important"><div class="g-step"><span class="g-num">1</span><span>Enter the <b>name</b>, <b>price</b>, and pick a <b>currency</b></span></div><div class="g-step"><span class="g-num">2</span><span>Choose a <b>payment method</b> and <b>billing cycle</b> (monthly, yearly, etc.)</span></div><div class="g-step"><span class="g-num">3</span><span>Set the <b>start date</b> \u2014 the next renewal date is calculated automatically, but you can also pick your own if needed</span></div><div class="g-step"><span class="g-num">4</span><span>Pick an <b>accent color</b> \u2014 ideally one that matches the subscription\'s logo color</span></div></div><div style="margin:6px 0 4px!important;padding:8px 10px!important;border:1px solid #152030!important;border-radius:5px!important;background:rgba(10,18,32,.5)!important"><div style="font-size:11px!important;color:#5a8aa0!important;margin-bottom:8px!important"><b style="color:#8aa8c0!important">Icon</b> \u2014 you have four choices. Pick <b>one</b>:</div><div class="g-step"><span class="g-num">A</span><span><b>Monogram</b> (default) \u2014 do nothing; the first letter of the name is shown automatically</span></div><div class="g-step"><span class="g-num">B</span><span><b>Emoji</b> \u2014 just type or paste an emoji into the icon field</span></div><div style="margin:8px 0 4px!important;font-size:10px!important;color:#3a6a80!important;letter-spacing:.5px!important">\u2500 Want the actual logo? Two more options \u2500</div><div class="g-step"><span class="g-num">C</span><span><b>SVG code</b> \u2014 get an SVG logo from one of these sites:</span></div><div style="padding-left:30px!important;margin:-2px 0 4px!important"><span style="display:inline-block!important;background:#0a1628!important;border:1px solid #1a2a40!important;border-radius:3px!important;padding:2px 7px!important;margin:2px 3px 2px 0!important;font-size:10px!important;color:#22d3ee!important;cursor:text!important;user-select:all!important">allogo.org</span> <span style="display:inline-block!important;background:#0a1628!important;border:1px solid #1a2a40!important;border-radius:3px!important;padding:2px 7px!important;margin:2px 3px 2px 0!important;font-size:10px!important;color:#22d3ee!important;cursor:text!important;user-select:all!important">dashboardicons.com</span> <span style="display:inline-block!important;background:#0a1628!important;border:1px solid #1a2a40!important;border-radius:3px!important;padding:2px 7px!important;margin:2px 3px 2px 0!important;font-size:10px!important;color:#22d3ee!important;cursor:text!important;user-select:all!important">boxicons.com</span></div><div style="padding-left:30px!important;font-size:11px!important;color:#6a8a9a!important;line-height:1.6!important">Open the site \u2192 search for the subscription (e.g. Netflix) \u2192 click the result \u2192 click <b style="color:#8aa8c0!important">SVG</b> \u2192 <b style="color:#8aa8c0!important">Copy</b> \u2192 paste into the icon field.</div><div class="g-step" style="margin-top:6px!important"><span class="g-num">D</span><span><b>Vault image</b> \u2014 use any PNG or JPG saved in your vault:</span></div><div style="padding-left:30px!important;font-size:11px!important;color:#6a8a9a!important;line-height:1.6!important">Save the image in your vault \u2192 in Obsidian\'s file explorer, right-click the image \u2192 <b style="color:#8aa8c0!important">Copy path</b> \u2192 <b style="color:#8aa8c0!important">From vault folder</b> \u2192 paste into the icon field.</div></div>You can <b>Edit</b>, <b>Cancel</b>, or <b>Archive</b> any subscription from its row.'},
      {ico:'\uD83D\uDCB3',ttl:'Payment Methods',body:'Tap <span class="g-hl">Methods</span> to manage your payment methods.<div style="margin:8px 0!important"><div class="g-step"><span class="g-num">\u2022</span><span>Add new methods by typing a name and pressing <b>Add</b></span></div><div class="g-step"><span class="g-num">\u2022</span><span>Each method gets a <b>signature color</b> \u2014 click the color swatch to change it</span></div><div class="g-step"><span class="g-num">\u2022</span><span>Method colors appear as <b>badges</b> next to subscriptions</span></div></div>Use <span class="g-hl">Filter</span> in each section to view subscriptions by a specific method.'},
      {ico:'\uD83D\uDCCA',ttl:'Stats Dashboard',body:'Tap <span class="g-hl">Stats</span> to see your spending overview.<div style="margin:8px 0!important"><div class="g-step"><span class="g-num">\u2022</span><span><b>Overview</b> \u2014 total monthly cost, yearly projection, cost breakdown per subscription</span></div><div class="g-step"><span class="g-num">\u2022</span><span><b>Charts</b> \u2014 interactive donut chart showing how your spending is distributed</span></div><div class="g-step"><span class="g-num">\u2022</span><span><b>Methods</b> \u2014 pie chart of how many subscriptions each payment method handles</span></div></div>Click any donut segment or legend item to highlight it.'},
      {ico:'\uD83D\uDCB1',ttl:'Currencies & Rates',body:'If you use currencies other than USD, this is for you.<div style="margin:8px 0!important"><div class="g-step"><span class="g-num">1</span><span>Tap <span class="g-hl">Currencies</span> to add the currencies you use (e.g. EUR, GBP)</span></div><div class="g-step"><span class="g-num">2</span><span>Tap the <span class="g-hl">\u21C5 Rates</span> button and enter how many units of each currency equal <b>$1 USD</b></span></div><div class="g-step"><span class="g-num">3</span><span>Once a rate is set, the <span class="g-hl">$ USD</span> toggle in each section will show dollar equivalents next to your prices</span></div></div>Example: if 1 USD = 0.86 EUR, enter <b>0.86</b> as the EUR rate.'},
      {ico:'\uD83D\uDD2D',ttl:'Focus Mode',body:'The <span style="color:#c4a06a!important;font-weight:700!important">amber-colored button</span> in the header toggles <b>Focus Mode</b>.<div style="margin:8px 0!important"><div class="g-step"><span class="g-num">\u2022</span><span>Focus Mode hides Obsidian\'s UI to give the tracker an <b>app-like</b> feel</span></div><div class="g-step"><span class="g-num">\u2022</span><span>It activates <b>automatically</b> when you open this file</span></div><div class="g-step"><span class="g-num">\u2022</span><span>Click it to <b>exit</b> focus mode and navigate to other files</span></div></div>On mobile, focus mode also hides toolbars for a true full-screen experience.'},
      {ico:'\uD83D\uDE80',ttl:'Tips & Tricks',body:'<div style="margin:4px 0!important"><div class="g-step"><span class="g-num">\u2726</span><span><b>Search</b> \u2014 type in the search bar to instantly filter subscriptions by name</span></div><div class="g-step"><span class="g-num">\u2726</span><span><b>Sort</b> \u2014 sort by date, price, or name with one click</span></div><div class="g-step"><span class="g-num">\u2726</span><span><b>Expand/Collapse</b> \u2014 on mobile, tap a subscription row to reveal full details</span></div><div class="g-step"><span class="g-num">\u2726</span><span><b>Archive</b> \u2014 don\'t delete old subs, archive them for historical records</span></div><div class="g-step"><span class="g-num">\u2726</span><span><b>Grace period</b> \u2014 a "didn\'t renew?" prompt appears when a renewal date passes</span></div></div><div style="text-align:center!important;margin-top:12px!important;color:#3a6a80!important;font-size:11px!important">That\'s it! You\'re all set. \u2728</div>'}
    ];
    function ren(){
      var dots='';for(var i=0;i<pages.length;i++)dots+='<span class="VA-guide-dot'+(i===pg?' act':'')+'" data-gdot="'+i+'"></span>';
      var p=pages[pg];
      cd.innerHTML='<div style="max-width:380px!important;margin:0 auto!important"><div class="VA-guide-ico">'+p.ico+'</div><div class="VA-guide-ttl">'+p.ttl+'</div><div class="VA-guide-body">'+p.body+'</div><div class="VA-guide-nav">'+(pg>0?'<div class="VA-b VA-b-g" data-gprev style="padding:6px 14px!important"><svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important"><polyline points="15 18 9 12 15 6"/></svg> Back</div>':'<div></div>')+'<div class="VA-guide-dots">'+dots+'</div>'+(pg<pages.length-1?'<div class="VA-b VA-b-add" data-gnext style="padding:6px 14px!important">Next <svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important"><polyline points="9 18 15 12 9 6"/></svg></div>':'<div class="VA-b VA-b-add" data-gclose style="padding:6px 14px!important">Done \u2713</div>')+'</div></div>';
      var prev=cd.querySelector('[data-gprev]');if(prev)prev.addEventListener('click',function(){pg--;ren();});
      var next=cd.querySelector('[data-gnext]');if(next)next.addEventListener('click',function(){pg++;ren();});
      var done=cd.querySelector('[data-gclose]');if(done)done.addEventListener('click',cl);
      cd.querySelectorAll('[data-gdot]').forEach(function(d){d.addEventListener('click',function(){pg=parseInt(d.dataset.gdot);ren();});});
    }ren();
  });}

  function showGrace(sub){if(sub.type!=='recurring'||sub.status!=='active'||!sub.lastAdv)return false;return Math.ceil((td0()-pd(sub.lastAdv))/864e5)<=GRACE;}
  function firstWord(nm){if(!nm)return'';const w=nm.trim().split(/\s+/);return w[0]||nm;}

  function clrMute(hex){const r=parseInt(hex.slice(1,3),16),g=parseInt(hex.slice(3,5),16),b=parseInt(hex.slice(5,7),16);return'#'+[r,g,b].map(v=>Math.round(v*.92).toString(16).padStart(2,'0')).join('');}

  function clrLighten(hex,amt){const r=parseInt(hex.slice(1,3),16),g=parseInt(hex.slice(3,5),16),b=parseInt(hex.slice(5,7),16);return'#'+[r,g,b].map(v=>Math.min(255,v+amt).toString(16).padStart(2,'0')).join('');}

  function buildPie(items,total,subs){
    if(!items.length||!total)return'';
    const R=80,CX=115,CY=115,SW=32,C=2*Math.PI*R;let off=0;
    var glowCircles='';var off2=0;items.forEach(function(it,i){var pct=it.monthly/total;var dash=pct*C;glowCircles+='<circle cx="'+CX+'" cy="'+CY+'" r="'+R+'" fill="none" stroke="'+it.color+'" stroke-width="'+(SW+16)+'" stroke-dasharray="'+dash.toFixed(2)+' '+(C-dash).toFixed(2)+'" stroke-dashoffset="'+(-off2).toFixed(2)+'" transform="rotate(-90 '+CX+' '+CY+')" opacity="0.25" style="pointer-events:none!important"/>';glowCircles+='<circle cx="'+CX+'" cy="'+CY+'" r="'+R+'" fill="none" stroke="'+it.color+'" stroke-width="'+(SW+30)+'" stroke-dasharray="'+dash.toFixed(2)+' '+(C-dash).toFixed(2)+'" stroke-dashoffset="'+(-off2).toFixed(2)+'" transform="rotate(-90 '+CX+' '+CY+')" opacity="0.08" style="pointer-events:none!important"/>';off2+=dash;});
    const segs=items.map((it,i)=>{const pct=it.monthly/total;const dash=pct*C;const bs=clrLighten(it.color,30);const s='<circle class="VA-pie-seg" data-idx="'+i+'" data-rawclr="'+it.color+'" cx="'+CX+'" cy="'+CY+'" r="'+R+'" fill="none" stroke="'+bs+'" stroke-width="'+SW+'" stroke-dasharray="'+dash.toFixed(2)+' '+(C-dash).toFixed(2)+'" stroke-dashoffset="'+(-off).toFixed(2)+'" transform="rotate(-90 '+CX+' '+CY+')"><title>'+it.name+': $'+it.monthly.toFixed(2)+'/mo ('+(pct*100).toFixed(0)+'%)</title></circle>';off+=dash;return s;}).join('');
    const topSub=items[0];const topPct=((topSub.monthly/total)*100).toFixed(0);
    const origSubs=subs||[];
    const leg=items.map((it,i)=>{const pc=clrMute(it.color);const orig=origSubs.find(s=>s.name===it.name);const ico=orig?subIconSm(orig.name,orig.icon,orig.color):'';return'<div class="VA-pie-item" data-pidx="'+i+'" style="padding:4px 6px !important;--hl-color:'+pc+'!important"><span class="VA-pie-dot" style="background:'+pc+'!important;box-shadow:0 0 4px '+it.color+'55!important"></span>'+ico+'<span class="VA-pie-nm">'+it.name+'</span><span class="VA-pie-val">$'+it.monthly.toFixed(2)+'</span></div>';}).join('');
    return'<div class="VA-pie-wrap"><div class="VA-pie-svg-wrap"><div class="VA-pie-deco" style="top:-8px!important;left:-8px!important;right:-8px!important;bottom:-8px!important;border:1px solid rgba(34,211,238,.05)!important"></div><div class="VA-pie-deco" style="top:-16px!important;left:-16px!important;right:-16px!important;bottom:-16px!important;border:1px dashed rgba(34,211,238,.03)!important"></div><svg viewBox="0 0 230 230" width="230" height="230" style="display:block!important;overflow:visible!important"><circle cx="'+CX+'" cy="'+CY+'" r="'+R+'" fill="none" stroke="#12202e" stroke-width="'+SW+'"/>'+glowCircles+segs+'</svg><div class="VA-pie-center"><span class="VA-pie-ct-val">$'+total.toFixed(0)+'</span><span class="VA-pie-ct-lbl">/month</span><span class="VA-pie-ct-sub">'+items.length+' subs</span></div></div><div class="VA-pie-leg" style="padding:4px 0 !important">'+leg+'</div></div>';
  }

  function buildCostBars(items,subs){
    if(!items.length)return'';
    const mx=Math.max(...items.map(i=>i.monthly));const origSubs=subs||[];
    return items.map((it,i)=>{const pct=Math.round((it.monthly/mx)*100);const pc=clrMute(it.color);const pcL=clrLighten(it.color,20);const orig=origSubs.find(s=>s.name===it.name);const ico=orig?subIconSm(orig.name,orig.icon,orig.color):'';return'<div class="VA-costbar" style="padding:4px 0!important"><span class="VA-costbar-ico">'+ico+'</span><span class="VA-costbar-nm">'+it.name+'</span><div class="VA-costbar-bg"><div class="VA-costbar-fill" style="width:'+pct+'%!important;background:linear-gradient(90deg,'+pc+','+pcL+')!important"></div></div><span class="VA-costbar-val">$'+it.monthly.toFixed(2)+'</span></div>';}).join('');
  }

  function openStats(){
    if(mo)return;mo=true;
    const bg=document.createElement('div');bg.className='VA-mbg';bg.style.cssText='padding:14px !important';
    const cd=document.createElement('div');cd.className='VA-stats';
    function cl(){bg.remove();mo=false;}
    bg.addEventListener('click',e=>{if(e.target===bg)cl();});cd.addEventListener('click',e=>e.stopPropagation());
    const subs=D.subs;const active=subs.filter(s=>s.status==='active');const rec=active.filter(s=>s.type==='recurring');const non=active.filter(s=>s.type==='non-recurring');const dead=subs.filter(s=>s.status==='dead');
    function buildItems(list){const items=[];list.forEach(s=>{const cy=s.cycle||'monthly';const m=toMonthlyUSD(s.price,s.currency,cy);items.push({name:s.name,monthly:m,cycle:cy,price:Number(s.price)||0,currency:s.currency||'$',color:clrHex(s.color)});});return items;}
    const recItems=buildItems(rec);const nonItems=buildItems(non);
    let totalMonthly=0;recItems.forEach(i=>totalMonthly+=i.monthly);nonItems.forEach(i=>totalMonthly+=i.monthly);
    const allItems=[...recItems,...nonItems].sort((a,b)=>b.monthly-a.monthly);
    let yearlyCost=0;rec.forEach(s=>{let u=toUSD(s.price,s.currency);switch(s.cycle){case'monthly':u*=12;break;case'weekly':u*=52;break;case'quarterly':u*=4;break;case'biannual':u*=2;break;case'yearly':break;default:u*=12;}yearlyCost+=u;});
    let topSub=null,topVal=0;active.forEach(s=>{const v=toMonthlyUSD(s.price,s.currency,s.cycle||'monthly');if(v>topVal){topVal=v;topSub=s;}});
    const methodCounts={};active.forEach(s=>{methodCounts[s.method]=(methodCounts[s.method]||0)+1;});
    const curCounts={};active.forEach(s=>{curCounts[s.currency]=(curCounts[s.currency]||0)+1;});
    const maxCurC=Math.max(...Object.values(curCounts),1);
    const totalMethods=Object.values(methodCounts).reduce((a,b)=>a+b,0)||1;
    function bkdHTML(list,origList){var hd='<thead><tr><th class="bkd-c-ico"></th><th class="bkd-c-nm"></th><th class="bkd-c-cy" style="text-align:center!important">Cycle</th><th class="bkd-c-math"></th><th class="bkd-c-amt" style="text-align:right!important">Monthly</th></tr></thead>';return hd+list.sort((a,b)=>b.monthly-a.monthly).map(it=>{const mc=mathCol(it.price,it.currency,it.cycle);const orig=origList.find(s=>s.name===it.name);const ico=orig?subIconSm(orig.name,orig.icon,orig.color):'';return'<tr><td class="bkd-c-ico">'+ico+'</td><td class="bkd-c-nm"><span class="VA-bkd-nm">'+it.name+'</span></td><td class="bkd-c-cy"><span class="VA-bkd-cy">'+fCy(it.cycle)+'</span></td><td class="bkd-c-math"><span class="VA-bkd-math">'+mc+'</span></td><td class="bkd-c-amt"><span class="VA-bkd-amt">$'+it.monthly.toFixed(2)+'</span></td></tr>';}).join('');}
    const recBkd=bkdHTML(recItems,rec);const nonBkd=bkdHTML(nonItems,non);
    function buildMethodsPie(){const R2=80,CX2=90,CY2=90;const mEntries=Object.entries(methodCounts).sort((a,b)=>b[1]-a[1]);let angle=0;const mSegs=mEntries.map(([m,c],i)=>{const mc=gmc(m);const pct=c/totalMethods;const sweep=pct*360;const a1=angle*Math.PI/180;const a2=(angle+sweep)*Math.PI/180;const lg=sweep>180?1:0;const x1=CX2+R2*Math.cos(a1);const y1=CY2+R2*Math.sin(a1);const x2=CX2+R2*Math.cos(a2);const y2=CY2+R2*Math.sin(a2);const d='M '+CX2+' '+CY2+' L '+x1.toFixed(2)+' '+y1.toFixed(2)+' A '+R2+' '+R2+' 0 '+lg+' 1 '+x2.toFixed(2)+' '+y2.toFixed(2)+' Z';const s='<path class="VA-pie-seg" data-midx="'+i+'" d="'+d+'" fill="'+mc.dot+'" stroke="#070b14" stroke-width="1.5" style="filter:drop-shadow(0 0 4px '+mc.dot+'66)!important;cursor:pointer!important;transition:filter .2s,transform .2s!important;transform-origin:'+CX2+'px '+CY2+'px!important"><title>'+m+': '+c+' ('+(pct*100).toFixed(0)+'%)</title></path>';angle+=sweep;return s;}).join('');const mLeg=mEntries.map(([m,c],i)=>{const mc=gmc(m);return'<div class="VA-pie-item" data-midx="'+i+'" style="padding:4px 6px !important;--hl-color:'+mc.dot+'!important"><span class="VA-pie-dot" style="background:'+mc.dot+'!important;box-shadow:0 0 4px '+mc.dot+'55!important"></span><span class="VA-pie-nm" style="color:'+mc.text+'!important">'+m+'</span><span class="VA-pie-val" style="color:#22d3ee!important">'+c+'</span></div>';}).join('');return'<div class="VA-pie-wrap"><div class="VA-pie-svg-wrap"><svg viewBox="0 0 180 180" width="180" height="180" style="display:block!important">'+mSegs+'</svg></div><div class="VA-pie-leg" style="padding:4px 0 !important">'+mLeg+'</div></div>';}

    const curTab=ST.stTab||'overview';const curChart=ST.chartMode||'donut';

    const curBars=Object.entries(curCounts).sort((a,b)=>b[1]-a[1]).map(([c,n])=>{const pct=Math.round((n/maxCurC)*100);return'<div class="VA-curbar" style="margin-bottom:6px !important"><span class="VA-curbar-sym">'+c+'</span><div class="VA-curbar-bg"><div class="VA-curbar-fill" style="width:'+pct+'%!important"></div></div><span class="VA-curbar-ct">'+n+'</span></div>';}).join('');
    const catCounts={};const catCosts={};active.forEach(s=>{const c=s.category||'Uncategorised';catCounts[c]=(catCounts[c]||0)+1;catCosts[c]=(catCosts[c]||0)+toMonthlyUSD(s.price,s.currency,s.cycle||'monthly');});
    const catColors={'Entertainment':'#ec4899','Technology':'#3b82f6','Membership':'#22c55e','Other':'#eab308','Uncategorised':'#64748b'};
    const maxCatC=Math.max(...Object.values(catCounts),1);
    const catEntries=Object.entries(catCounts).sort((a,b)=>b[1]-a[1]);
    const totalCatMethods=Object.values(catCounts).reduce((a,b)=>a+b,0)||1;
    function buildCatPie(){const R2=80,CX2=90,CY2=90;let angle=0;const segs=catEntries.map(([c,ct],i)=>{const clr=catColors[c]||'#6b7280';const pct=ct/totalCatMethods;const sweep=pct*360;const a1=angle*Math.PI/180;const a2=(angle+sweep)*Math.PI/180;const lg=sweep>180?1:0;const x1=CX2+R2*Math.cos(a1);const y1=CY2+R2*Math.sin(a1);const x2=CX2+R2*Math.cos(a2);const y2=CY2+R2*Math.sin(a2);const d='M '+CX2+' '+CY2+' L '+x1.toFixed(2)+' '+y1.toFixed(2)+' A '+R2+' '+R2+' 0 '+lg+' 1 '+x2.toFixed(2)+' '+y2.toFixed(2)+' Z';const s='<path d="'+d+'" fill="'+clr+'" stroke="#070b14" stroke-width="1.5" style="filter:drop-shadow(0 0 4px '+clr+'66)!important"><title>'+c+': '+ct+' ('+(pct*100).toFixed(0)+'%)</title></path>';angle+=sweep;return s;}).join('');const leg=catEntries.map(([c,ct])=>{const clr=catColors[c]||'#6b7280';const cost=catCosts[c]||0;return'<div class="VA-pie-item" style="padding:4px 6px !important;--hl-color:'+clr+'!important"><span class="VA-pie-dot" style="background:'+clr+'!important;box-shadow:0 0 4px '+clr+'55!important"></span><span class="VA-pie-nm">'+c+'</span><span style="font-size:10px!important;color:#4a6a80!important;margin-left:auto!important;padding-right:6px!important">'+ct+' subs</span><span class="VA-pie-val">$'+cost.toFixed(2)+'/mo</span></div>';}).join('');return'<div class="VA-pie-wrap"><div class="VA-pie-svg-wrap"><svg viewBox="0 0 180 180" width="180" height="180" style="display:block!important">'+segs+'</svg></div><div class="VA-pie-leg" style="padding:4px 0 !important">'+leg+'</div></div>';}
    const catPanel='<div class="VA-stpanel'+(curTab==='categories'?' act':'')+'" data-sp="categories" style="padding:16px 18px!important"><span class="VA-stlbl" style="margin-bottom:12px !important;display:block!important">Spending by Category</span>'+buildCatPie()+'</div>';
    cd.innerHTML='<div class="VA-sthdr" style="padding:14px 18px !important"><div class="VA-sttl">Dashboard</div><span class="VA-stclose" id="stx">\u00D7</span></div>'+
      '<div class="VA-sttabs"><span class="VA-sttab'+(curTab==='overview'?' act':'')+'" style="padding:10px 8px!important" data-stab="overview">Overview</span><span class="VA-sttab'+(curTab==='charts'?' act':'')+'" style="padding:10px 8px!important" data-stab="charts">Charts</span><span class="VA-sttab'+(curTab==='methods'?' act':'')+'" style="padding:10px 8px!important" data-stab="methods">Methods</span><span class="VA-sttab'+(curTab==='categories'?' act':'')+'" style="padding:10px 8px!important" data-stab="categories">Categories</span></div>'+
      '<div class="VA-stpanel'+(curTab==='overview'?' act':'')+'" data-sp="overview"><div class="VA-stgrid">'+
        '<div class="VA-stcard VA-stcard-g VA-stcard-w" style="padding:16px 18px !important"><span class="VA-stlbl" style="margin-bottom:8px !important">Total Monthly Cost</span><span class="VA-stval VA-stval-g" style="margin-bottom:6px !important">$'+totalMonthly.toFixed(2)+'</span><div style="margin-top:8px !important;padding-top:8px !important;border-top:1px solid #12202e !important">'+(rec.length?'<div class="VA-bkd-sec" style="padding:3px 0 5px !important">Recurring \u00B7 '+rec.length+'</div><table class="VA-bkd-tbl">'+recBkd+'</table>':'')+(non.length?'<div class="VA-bkd-sec" style="padding:'+(rec.length?'8':'3')+'px 0 5px !important">Non-Recurring \u00B7 '+non.length+'</div><table class="VA-bkd-tbl">'+nonBkd+'</table>':'')+(!rec.length&&!non.length?'<span class="VA-stsub">No active subs</span>':'')+'</div></div>'+
        '<div class="VA-stcard VA-stcard-y" style="padding:14px 16px !important"><span class="VA-stlbl" style="margin-bottom:5px !important">Yearly Recurring</span><span class="VA-stval VA-stval-y">$'+yearlyCost.toFixed(0)+'</span></div>'+
        '<div class="VA-stcard VA-stcard-t" style="padding:14px 16px !important"><span class="VA-stlbl" style="margin-bottom:5px !important">Active</span><span class="VA-stval VA-stval-t">'+active.length+'</span><span class="VA-stsub" style="margin-top:3px !important">'+rec.length+' rec \u00B7 '+non.length+' one-time</span></div>'+
        '<div class="VA-stcard VA-stcard-p" style="padding:14px 16px !important"><span class="VA-stlbl" style="margin-bottom:5px !important">Archived</span><span class="VA-stval VA-stval-p">'+dead.length+'</span></div>'+
        '<div class="VA-stcard VA-stcard-r" style="padding:14px 16px !important"><span class="VA-stlbl" style="margin-bottom:5px !important">Costliest</span><span class="VA-stval" style="font-size:15px !important;color:#d0dce8 !important">'+(topSub?topSub.name:'\u2014')+'</span><span class="VA-stsub" style="margin-top:3px !important">'+(topSub?fP(topSub.price,topSub.currency):'')+'</span></div>'+
      '</div></div>'+
      '<div class="VA-stpanel'+(curTab==='charts'?' act':'')+'" data-sp="charts" style="padding:16px 18px!important"><div style="display:flex!important;align-items:center!important;justify-content:space-between!important;margin-bottom:12px!important"><span class="VA-stlbl">Cost Distribution</span><div class="VA-chtog"><span class="VA-chtog-b'+(curChart==='donut'?' act':'')+'" style="padding:5px 10px!important" data-cht="donut">Donut</span><span class="VA-chtog-b'+(curChart==='bars'?' act':'')+'" style="padding:5px 10px!important" data-cht="bars">Bars</span></div></div><div id="st-chart-area">'+(curChart==='donut'?(buildPie(allItems,totalMonthly,active)||'<span class="VA-stsub">No data</span>'):(buildCostBars(allItems,active)||'<span class="VA-stsub">No data</span>'))+'</div></div>'+
      '<div class="VA-stpanel'+(curTab==='methods'?' act':'')+'" data-sp="methods" style="padding:16px 18px!important"><span class="VA-stlbl" style="margin-bottom:12px !important;display:block!important">Payment Methods</span>'+buildMethodsPie()+'<div style="margin-top:16px!important;padding-top:12px!important;border-top:1px solid #12202e!important"><span class="VA-stlbl" style="margin-bottom:10px!important;display:block!important">Currencies</span>'+(curBars||'<span class="VA-stsub">\u2014</span>')+'</div></div>'+
      catPanel+
      '<div class="VA-stft" style="padding:8px 14px !important"><span class="VA-stft-txt">'+active.length+' active \u00B7 '+dead.length+' archived</span></div>';
    cd.querySelector('#stx').addEventListener('click',cl);
    cd.querySelectorAll('.VA-sttab').forEach(tab=>{tab.addEventListener('click',()=>{ST.stTab=tab.dataset.stab;cd.querySelectorAll('.VA-sttab').forEach(t=>t.classList.remove('act'));tab.classList.add('act');cd.querySelectorAll('.VA-stpanel').forEach(p=>p.classList.remove('act'));cd.querySelector('[data-sp="'+tab.dataset.stab+'"]')?.classList.add('act');});});
    cd.querySelectorAll('.VA-chtog-b').forEach(btn=>{btn.addEventListener('click',()=>{ST.chartMode=btn.dataset.cht;cd.querySelectorAll('.VA-chtog-b').forEach(b=>b.classList.remove('act'));btn.classList.add('act');const area=cd.querySelector('#st-chart-area');if(btn.dataset.cht==='donut'){area.innerHTML=buildPie(allItems,totalMonthly,active)||'<span class="VA-stsub">No data</span>';bindPieHover(cd);}else area.innerHTML=buildCostBars(allItems,active)||'<span class="VA-stsub">No data</span>';setTimeout(()=>{cd.querySelectorAll('.VA-costbar-fill,.VA-curbar-fill').forEach(b=>{const w=b.style.width;b.style.width='0%';setTimeout(()=>{b.style.width=w;},30);});},30);});});
    function setGlow(el,val){el.style.filter=val;el.style.webkitFilter=val;}function bindPieHover(container){container.querySelectorAll('.VA-pie-seg[data-idx]').forEach(seg=>{seg.addEventListener('mouseenter',function(){const raw=this.dataset.rawclr||this.getAttribute('stroke');setGlow(this,'drop-shadow(0 0 12px '+raw+') drop-shadow(0 0 20px '+raw+'66)');this.style.strokeWidth='36';const idx=this.dataset.idx;container.querySelectorAll('.VA-pie-item').forEach(it=>{it.classList.remove('VA-pie-hl');if(it.dataset.pidx===idx)it.classList.add('VA-pie-hl');});});seg.addEventListener('mouseleave',function(){const raw=this.dataset.rawclr||this.getAttribute('stroke');setGlow(this,'drop-shadow(0 0 6px '+raw+') drop-shadow(0 0 14px '+raw+'55)');this.style.strokeWidth='32';container.querySelectorAll('.VA-pie-item').forEach(it=>it.classList.remove('VA-pie-hl'));});seg.addEventListener('click',function(){const idx=this.dataset.idx;const raw=this.dataset.rawclr||this.getAttribute('stroke');const isActive=this.dataset.glowActive==='1';container.querySelectorAll('.VA-pie-seg[data-idx]').forEach(s=>{var rc=s.dataset.rawclr||s.getAttribute('stroke');setGlow(s,'drop-shadow(0 0 6px '+rc+') drop-shadow(0 0 14px '+rc+'55)');s.style.strokeWidth='32';s.dataset.glowActive='0';});container.querySelectorAll('.VA-pie-item').forEach(it=>it.classList.remove('VA-pie-hl'));if(!isActive){setGlow(this,'drop-shadow(0 0 16px '+raw+') drop-shadow(0 0 24px '+raw+'88)');this.style.strokeWidth='36';this.dataset.glowActive='1';const item=container.querySelector('.VA-pie-item[data-pidx="'+idx+'"]');if(item){item.classList.add('VA-pie-hl');item.scrollIntoView({behavior:'smooth',block:'nearest'});}}});});}
    function bindMethodsPieHover(container){container.querySelectorAll('.VA-pie-seg[data-midx]').forEach(seg=>{seg.addEventListener('mouseenter',function(){const clr=this.getAttribute('fill');const idx=this.dataset.midx;setGlow(this,'drop-shadow(0 0 8px '+clr+') drop-shadow(0 0 16px '+clr+'66)');this.style.transform='scale(1.04)';container.querySelectorAll('.VA-pie-item').forEach(it=>{it.classList.remove('VA-pie-hl');if(it.dataset.midx===idx)it.classList.add('VA-pie-hl');});});seg.addEventListener('mouseleave',function(){const clr=this.getAttribute('fill');setGlow(this,'drop-shadow(0 0 4px '+clr+'66)');this.style.transform='scale(1)';container.querySelectorAll('.VA-pie-item').forEach(it=>it.classList.remove('VA-pie-hl'));});seg.addEventListener('click',function(){const clr=this.getAttribute('fill');const idx=this.dataset.midx;container.querySelectorAll('.VA-pie-seg[data-midx]').forEach(s=>{var sc=s.getAttribute('fill');setGlow(s,'drop-shadow(0 0 4px '+sc+'66)');s.style.transform='scale(1)';s.dataset.glowActive='0';});container.querySelectorAll('.VA-pie-item').forEach(it=>it.classList.remove('VA-pie-hl'));var isActive=this.dataset.glowActive==='1';if(!isActive){setGlow(this,'drop-shadow(0 0 12px '+clr+') drop-shadow(0 0 20px '+clr+'88)');this.style.transform='scale(1.04)';this.dataset.glowActive='1';var item=container.querySelector('.VA-pie-item[data-midx="'+idx+'"]');if(item){item.classList.add('VA-pie-hl');item.scrollIntoView({behavior:'smooth',block:'nearest'});}}});});}
    bindPieHover(cd);
    bindMethodsPieHover(cd);
    bg.appendChild(cd);document.body.appendChild(bg);
    setTimeout(()=>{cd.querySelectorAll('.VA-costbar-fill,.VA-curbar-fill').forEach(b=>{const w=b.style.width;b.style.width='0%';setTimeout(()=>{b.style.width=w;},30);});},30);
  }

  function bRow(sub,sec){
    const isDead=sec==='dead';const m=gmc(sub.method);const dl=dL(sub.nextDate);
    const dlC=dl<=3?'VA-dl-c':dl<=7?'VA-dl-w':'VA-dl-ok';
    const ico=subIcon(sub.name,sub.icon,sub.color);
    let gr='';if(sec==='recurring'&&showGrace(sub))gr='<span class="VA-grace" style="padding:3px 6px !important;margin-left:6px !important" data-act="didnt-renew" data-id="'+sub.id+'">didn\'t renew?</span>';
    const cBadge=sub.cancelled?'<span class="VA-cbadge" style="padding:2px 5px !important;margin-left:5px !important">cancelled</span>':'';
    const catBadge='<span class="VA-catbadge" style="padding:2px 6px !important;margin-left:5px !important;font-size:9px!important;font-weight:700!important;letter-spacing:.5px!important;text-transform:uppercase!important;border-radius:3px!important;cursor:pointer!important;display:inline-flex!important;align-items:center!important;gap:3px!important;background:rgba(167,139,250,.1)!important;color:#a78bfa!important;border:1px solid rgba(167,139,250,.2)!important;white-space:nowrap!important;vertical-align:middle!important;transition:border-color .15s!important" data-act="setcat" data-id="'+sub.id+'">'+(sub.category||'uncategorised')+'<svg xmlns="http://www.w3.org/2000/svg" width="8" height="8" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important;opacity:.6!important"><path d="M12 20h9"/><path d="M16.5 3.5a2.121 2.121 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg></span>';
    const hasRate=sub.currency!=='$'&&D.exRates[sub.currency]&&Number(D.exRates[sub.currency])>0;
    const usdEq=ST.showUSD&&hasRate?'<span class="VA-pu" style="margin-left:4px !important">\u2248$'+(Number(sub.price)/Number(D.exRates[sub.currency])).toFixed(2)+'</span>':'';
    const usdNorm=toUSD(sub.price,sub.currency);
    const sL=sub.started&&dailyExists(sub.started)?'<span class="VA-dt VA-dtlink" data-open="'+sub.started+'">'+fD(sub.started)+'</span>':'<span class="VA-dt">'+fD(sub.started)+'</span>';
    const fw=firstWord(sub.name);
    const P='style="padding:10px 12px !important"';const PL='style="padding:10px 8px !important"';
    if(isDead){const rc=sub.deathReason==='expired';return'<tr data-id="'+sub.id+'" data-nm="'+(sub.name||'').toLowerCase()+'" data-mt="'+sub.method+'" data-cat="'+(sub.category||'')+'" data-pr="'+usdNorm+'" data-dt="'+(sub.deathDate||sub.nextDate||'')+'" data-fw="'+fw+'"><td '+P+' data-label=""><span class="VA-nm-wrap">'+ico+'<span class="VA-nm" data-full="'+sub.name+'">'+sub.name+'</span></span>'+catBadge+'</td><td '+P+' data-label="Price"><span class="VA-pr">'+fP(sub.price,sub.currency)+'</span>'+usdEq+'</td><td '+P+' data-label="Method"><span class="VA-mt" style="background:'+m.bg+' !important;border-color:'+m.dot+' !important;padding:3px 8px !important"><span class="VA-mtd" style="background:'+m.dot+' !important;box-shadow:0 0 4px '+m.dot+' !important"></span><span class="VA-mtn'+(sub.method==='Kazawallet Card'?' VA-mtn-grad':sub.method==='Google Pay'?' VA-mtn-goog':'')+'" style="color:'+m.text+' !important">'+(sub.method||'\u2014')+'</span></span></td><td '+P+' data-label="Started">'+sL+'</td><td '+P+' data-label="Ended"><span class="VA-dt">'+fD(sub.deathDate||sub.nextDate)+'</span></td><td '+P+' data-label="Status"><span class="VA-rsn '+(rc?'VA-rsn-e':'VA-rsn-c')+'">'+(rc?'Expired':'Cancelled')+'</span></td><td '+PL+' class="VA-acts" data-label=""><span class="VA-ab VA-ab-rev" style="padding:5px 10px !important" data-act="reactivate" data-id="'+sub.id+'">Revive</span></td></tr>';}
    const isRec=sec==='recurring';
    return'<tr data-id="'+sub.id+'" data-nm="'+(sub.name||'').toLowerCase()+'" data-mt="'+sub.method+'" data-cat="'+(sub.category||'')+'" data-pr="'+usdNorm+'" data-dt="'+(sub.nextDate||'')+'" data-dl="'+dl+'" data-fw="'+fw+'"><td '+P+' data-label=""><span class="VA-nm-wrap">'+ico+'<span class="VA-nm" data-full="'+sub.name+'">'+sub.name+'</span></span>'+gr+cBadge+catBadge+'</td><td '+P+' data-label="Price"><span class="VA-pr">'+fP(sub.price,sub.currency)+'</span>'+usdEq+'</td><td '+P+' data-label="Cycle"><span class="VA-cy">'+(fCy(sub.cycle)||'One-time')+'</span></td><td '+P+' data-label="Method"><span class="VA-mt" style="background:'+m.bg+' !important;border-color:'+m.dot+' !important;padding:3px 8px !important"><span class="VA-mtd" style="background:'+m.dot+' !important;box-shadow:0 0 4px '+m.dot+' !important"></span><span class="VA-mtn'+(sub.method==='Kazawallet Card'?' VA-mtn-grad':sub.method==='Google Pay'?' VA-mtn-goog':'')+'" style="color:'+m.text+' !important">'+(sub.method||'\u2014')+'</span></span></td><td '+P+' data-label="Started">'+sL+'</td><td '+P+' data-label="'+(isRec?'Renews':'Ends')+'"><span class="VA-dt">'+fD(sub.nextDate)+'</span></td><td '+PL+' data-label="Days"><span class="VA-dl '+dlC+'">'+dl+'d</span></td><td '+PL+' class="VA-acts" data-label=""><span class="VA-ab VA-ab-e" style="padding:5px 10px !important" data-act="edit" data-id="'+sub.id+'">Edit</span>'+(isRec?' <span class="VA-ab VA-ab-can" style="padding:5px 10px !important;margin-left:3px !important" data-act="cancel" data-id="'+sub.id+'">Cancel</span>':'')+' <span class="VA-ab VA-ab-arc" style="padding:5px 10px !important;margin-left:3px !important" data-act="archive" data-id="'+sub.id+'">Archive</span></td></tr>';
  }

  function bSec(title,subs,sec,color){
    const isDead=sec==='dead';const open=isDead?ST.deadOpen:true;
    const secC=sec==='recurring'?'VA-sec-rec':sec==='dead'?'VA-sec-ded':'VA-sec-non';
    const THP='style="padding:10px 12px !important"';
    const aH='<th '+THP+'>Name</th><th '+THP+'>Price</th><th '+THP+'>Cycle</th><th '+THP+'>Method</th><th '+THP+'>Started</th><th '+THP+'>'+(sec==='recurring'?'Renews':'Ends')+'</th><th '+THP+'>Days</th><th '+THP+'></th>';
    const dH='<th '+THP+'>Name</th><th '+THP+'>Price</th><th '+THP+'>Method</th><th '+THP+'>Started</th><th '+THP+'>Ended</th><th '+THP+'>Status</th><th '+THP+'></th>';
    const rows=subs.map(s=>bRow(s,sec)).join('');
    const empty=subs.length===0?'<tr class="VA-emp"><td colspan="8" style="padding:20px 12px !important">\u2014 no subscriptions \u2014</td></tr>':'';
    const cff=ST.filters[sec]||'all';const fLabel=cff==='all'?'Filter':cff;
    const pills='<span class="VA-fp'+(cff==='all'?' act':'')+'" style="padding:5px 8px !important" data-fv="all" data-fs="'+sec+'">All</span>'+D.methods.map(m=>{const c=gmc(m);return'<span class="VA-fp'+(cff===m?' act':'')+'" style="padding:5px 8px !important" data-fv="'+m+'" data-fs="'+sec+'"><span class="VA-fpdot" style="background:'+c.dot+' !important"></span>'+m+'</span>';}).join('');
    const cs=ST.sorts[sec]||'date-asc';
    const sorts=[{v:'date-asc',l:'Soonest'},{v:'date-desc',l:'Latest'},{v:'price-desc',l:'Priciest'},{v:'price-asc',l:'Cheapest'},{v:'name-asc',l:'A\u2192Z'}].map(s=>'<span class="VA-sp'+(cs===s.v?' act':'')+'" style="padding:4px 8px !important" data-sv="'+s.v+'" data-ss="'+sec+'">'+s.l+'</span>').join('');
    var hasAnyRate=D.currencies.some(function(c){return c!=='$'&&D.exRates[c]&&Number(D.exRates[c])>0;});
    const usdToggle='<span class="VA-usd'+(ST.showUSD?' act':'')+'" style="padding:5px 10px !important;'+(hasAnyRate?'':'opacity:.35!important;')+'" data-usdtog><svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important"><line x1="12" y1="1" x2="12" y2="23"/><path d="M17 5H9.5a3.5 3.5 0 0 0 0 7h5a3.5 3.5 0 0 1 0 7H6"/></svg> USD</span>';
    const mExpAll=ST.mExpAll[sec];const meTog='<span class="VA-metog" style="padding:5px 10px!important" data-metog="'+sec+'"><svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important">'+(mExpAll?'<polyline points="4 14 10 20 20 4"/>':'<polyline points="15 3 21 3 21 9"/><path d="M21 3l-7 7"/><polyline points="9 21 3 21 3 15"/><path d="M3 21l7-7"/>')+'</svg> '+(mExpAll?'Collapse':'Expand')+'</span>';
    return'<div class="VA-sec '+secC+' '+(isDead?'VA-ded':'')+'" data-sec="'+sec+'" style="margin-bottom:10px !important"><div class="VA-sh" style="padding:10px 14px 8px !important"><div class="VA-shl"><span class="VA-sn" style="color:'+color+' !important">'+title+'</span><span class="VA-sc" style="padding:2px 8px !important">'+subs.length+'</span>'+(isDead?'<span class="VA-stog" data-tog="dead">'+(open?'\u25BE hide':'\u25B8 show')+'</span>':'')+'</div><div style="display:flex!important;gap:6px!important;align-items:center!important">'+meTog+usdToggle+'</div></div>'+(!open?'':'<div class="VA-tb" style="padding:6px 14px !important"><input class="VA-srch" type="text" placeholder="Search\u2026" style="padding:6px 10px !important" data-sr="'+sec+'" autocomplete="off" /><span class="VA-sep"></span><div class="VA-fwrap" data-fw="'+sec+'"><span class="VA-fb" style="padding:6px 10px !important"><span>'+fLabel+'</span><span class="VA-farr">\u25BE</span></span><div class="VA-fpop" style="padding:6px !important">'+pills+'</div></div><span class="VA-sep"></span><span class="VA-slbl">Sort:</span>'+sorts+'</div><div class="VA-tw"><table class="VA-t"><thead><tr>'+(isDead?dH:aH)+'</tr></thead><tbody data-tb="'+sec+'">'+(rows||empty)+'</tbody></table></div>')+'</div>';
  }

  function renderAll(){
    D=rd();const subs=D.subs;
    const corners='<div class="VA-corner VA-tl"></div><div class="VA-corner VA-tr"></div><div class="VA-corner VA-bl"></div><div class="VA-corner VA-br"></div>';
    root.innerHTML=corners+'<div class="VA-bg"></div><div class="VA-pulse"></div><div class="VA-pulse2"></div>'+
      '<div class="VA-hdr" style="padding:14px 18px 10px !important;margin-bottom:8px !important"><div class="VA-ttl" style="padding-left:12px !important;margin-left:2px !important">Subscriptions</div><div class="VA-btns"><div class="VA-b VA-b-add" id="st-add" style="padding:7px 14px !important"><span class="VA-bi">\u2295</span> Add</div><div class="VA-b VA-b-g" id="st-stats" style="padding:7px 14px !important">Stats</div><div class="VA-b VA-b-g" id="st-met" style="padding:7px 14px !important">Methods</div><div class="VA-b VA-b-g" id="st-cur" style="padding:7px 14px !important">Currencies</div><div class="VA-b VA-b-g" id="st-cat" style="padding:7px 14px !important">Categories</div><div class="VA-b VA-b-g" id="st-rates" style="padding:7px 10px !important" title="Exchange Rates"><svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important"><path d="M3 8l4-4 4 4"/><path d="M7 4v16"/><path d="M21 16l-4 4-4-4"/><path d="M17 20V4"/></svg></div><div class="VA-b VA-b-g" id="st-guide" style="padding:7px 10px !important" title="Guide"><svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important"><circle cx="12" cy="12" r="10"/><path d="M9.09 9a3 3 0 0 1 5.83 1c0 2-3 3-3 3"/><line x1="12" y1="17" x2="12.01" y2="17"/></svg></div><div class="VA-b VA-b-f" id="st-focus" style="padding:7px 10px !important" title="Toggle Focus Mode"><svg xmlns="http://www.w3.org/2000/svg" width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important">'+(ST.appMode?'<path d="M8 3v3a2 2 0 0 1-2 2H3m18 0h-3a2 2 0 0 1-2-2V3m0 18v-3a2 2 0 0 1 2-2h3M3 16h3a2 2 0 0 1 2 2v3"/>':'<path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/>')+'</svg></div></div></div>'+
      '<div style="padding:0 10px 10px !important;position:relative !important;z-index:1 !important">'+
      bSec('Recurring',subs.filter(s=>s.status==='active'&&s.type==='recurring'),'recurring','#22d3ee')+
      '<div class="VA-sdiv" style="margin:3px 0 !important"></div>'+
      bSec('Non-Recurring',subs.filter(s=>s.status==='active'&&s.type==='non-recurring'),'non-recurring','#a78bfa')+
      '<div class="VA-sdiv" style="margin:3px 0 !important"></div>'+
      bSec('Archived',subs.filter(s=>s.status==='dead'),'dead','#64748b')+
      '</div>';
    bindEv();
    ['recurring','non-recurring','dead'].forEach(sec=>{applyS(sec);applyF(sec);applyME(sec);});
  }

  function applyF(sec){const tb=root.querySelector('[data-tb="'+sec+'"]');if(!tb)return;const si=root.querySelector('.VA-srch[data-sr="'+sec+'"]');const q=si?si.value.toLowerCase():'';const fv=ST.filters[sec]||'all';tb.querySelectorAll('tr[data-id]').forEach(r=>{var show=(!q||(r.dataset.nm||'').includes(q))&&(fv==='all'||r.dataset.mt===fv);if(show){r.classList.remove('VA-row-hide');r.style.removeProperty('display');}else{r.classList.add('VA-row-hide');r.style.setProperty('display','none','important');}});}
  function applyS(sec){const tb=root.querySelector('[data-tb="'+sec+'"]');if(!tb)return;const s=ST.sorts[sec]||'date-asc';const[k,dir]=s.split('-');const asc=dir==='asc';const rows=Array.from(tb.querySelectorAll('tr[data-id]'));rows.sort((a,b)=>{if(k==='price')return asc?(parseFloat(a.dataset.pr)||0)-(parseFloat(b.dataset.pr)||0):(parseFloat(b.dataset.pr)||0)-(parseFloat(a.dataset.pr)||0);if(k==='name')return asc?(a.dataset.nm||'').localeCompare(b.dataset.nm||''):(b.dataset.nm||'').localeCompare(a.dataset.nm||'');return asc?(a.dataset.dt||'').localeCompare(b.dataset.dt||''):(b.dataset.dt||'').localeCompare(a.dataset.dt||'');});rows.forEach(r=>tb.appendChild(r));}
  function applyME(sec){const isMobile=window.innerWidth<=600;if(!isMobile)return;const tb=root.querySelector('[data-tb="'+sec+'"]');if(!tb)return;const expAll=ST.mExpAll[sec];const expMap=ST.mExp[sec]||{};tb.querySelectorAll('tr[data-id]').forEach(r=>{if(expAll||expMap[r.dataset.id]){r.classList.add('VA-card-open');const nm=r.querySelector('.VA-nm');if(nm&&nm.dataset.full)nm.textContent=nm.dataset.full;}else{r.classList.remove('VA-card-open');const nm=r.querySelector('.VA-nm');if(nm&&nm.dataset.full){const full=nm.dataset.full;nm.textContent=full;setTimeout(()=>{if(nm.scrollWidth>nm.clientWidth)nm.textContent=firstWord(full);},0);}}});}

  function bindEv(){
    if(!root._evBound){
    root._evBound=true;
    root.addEventListener('input',function(e){var inp=e.target.closest('.VA-srch');if(inp)applyF(inp.dataset.sr);});
    root.addEventListener('click',function(e){
      var t=e.target;
      if(t.closest('.VA-srch')||t.closest('.VA-tb input'))return;
      var addBtn=t.closest('#st-add');if(addBtn){openAE(null);return;}
      var stBtn=t.closest('#st-stats');if(stBtn){openStats();return;}
      var metBtn=t.closest('#st-met');if(metBtn){openLE('Payment Methods','methods');return;}
      var curBtn=t.closest('#st-cur');if(curBtn){openLE('Currencies','currencies');return;}
      var catBtn=t.closest('#st-cat');if(catBtn){openLE('Categories','categories');return;}
      var ratesBtn=t.closest('#st-rates');if(ratesBtn){openExRates();return;}
      var guideBtn=t.closest('#st-guide');if(guideBtn){openGuide();return;}
      var focBtn=t.closest('#st-focus');if(focBtn){setAppMode(!ST.appMode);renderAll();return;}
      var togDead=t.closest('[data-tog="dead"]');if(togDead){ST.deadOpen=!ST.deadOpen;renderAll();return;}
      var usdT=t.closest('[data-usdtog]');if(usdT){ST.showUSD=!ST.showUSD;renderAll();return;}
      var meT=t.closest('[data-metog]');if(meT){var sec=meT.dataset.metog;ST.mExpAll[sec]=!ST.mExpAll[sec];if(!ST.mExpAll[sec])ST.mExp[sec]={};applyME(sec);var svgExp='<svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important"><polyline points="15 3 21 3 21 9"/><path d="M21 3l-7 7"/><polyline points="9 21 3 21 3 15"/><path d="M3 21l7-7"/></svg> Expand';var svgCol='<svg xmlns="http://www.w3.org/2000/svg" width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5" stroke-linecap="round" stroke-linejoin="round" style="vertical-align:middle!important;display:inline-block!important"><polyline points="4 14 10 20 20 4"/></svg> Collapse';meT.innerHTML=ST.mExpAll[sec]?svgCol:svgExp;return;}
      var actEl=t.closest('[data-act]');if(actEl){e.stopPropagation();var act=actEl.dataset.act,id=actEl.dataset.id;var sub=D.subs.find(function(s){return s.id===id;});if(!sub)return;if(act==='edit')openAE(sub);else if(act==='cancel'||act==='didnt-renew')openCancel(sub);else if(act==='archive')openArchive(sub);else if(act==='setcat')openCatPicker(sub);else if(act==='reactivate'){(async function(){var subs=rd().subs;var s=subs.find(function(x){return x.id===id;});if(s){s.status='active';s.type='recurring';delete s.deathDate;delete s.deathReason;delete s.cancelled;if(!s.cycle)s.cycle='monthly';if(s.nextDate&&s.nextDate<td()){while(s.nextDate<td())s.nextDate=adv(s.nextDate,s.cycle);}}await sv(subs);D=rd();renderAll();})();}return;}
      var openEl=t.closest('[data-open]');if(openEl){e.stopPropagation();openDaily(openEl.dataset.open);return;}
      var fpEl=t.closest('.VA-fp');if(fpEl){e.stopPropagation();e.preventDefault();__jf=true;var sec=fpEl.dataset.fs;var val=fpEl.dataset.fv;ST.filters[sec]=val;var fw=fpEl.closest('.VA-fwrap');fw.querySelectorAll('.VA-fp').forEach(function(x){x.classList.remove('act');});fpEl.classList.add('act');var btn=fw.querySelector('.VA-fb');btn.querySelector('span:first-child').textContent=val==='all'?'Filter':val;if(val!=='all')btn.classList.add('act');else btn.classList.remove('act');fw.classList.remove('open');applyF(sec);setTimeout(function(){__jf=false;},200);return;}
      var fbEl=t.closest('.VA-fb');if(fbEl){e.stopPropagation();e.preventDefault();var fw=fbEl.closest('.VA-fwrap');root.querySelectorAll('.VA-fwrap.open').forEach(function(f){if(f!==fw)f.classList.remove('open');});fw.classList.toggle('open');return;}
      var spEl=t.closest('.VA-sp');if(spEl){var sec=spEl.dataset.ss;ST.sorts[sec]=spEl.dataset.sv;root.querySelectorAll('.VA-sp[data-ss="'+sec+'"]').forEach(function(x){x.classList.remove('act');});spEl.classList.add('act');applyS(sec);return;}
      root.querySelectorAll('.VA-fwrap.open').forEach(function(f){f.classList.remove('open');});
      if(window.innerWidth<=600){var tr=t.closest('.VA-t tbody tr[data-id]');if(tr&&!t.closest('.VA-tb')&&!t.closest('.VA-sh')){var sec=tr.closest('[data-sec]');sec=sec?sec.dataset.sec:null;if(!sec)return;var id=tr.dataset.id;if(!ST.mExp[sec])ST.mExp[sec]={};var nm=tr.querySelector('.VA-nm');if(tr.classList.contains('VA-card-open')){tr.classList.remove('VA-card-open');delete ST.mExp[sec][id];if(nm&&nm.dataset.full){var full=nm.dataset.full;nm.textContent=full;setTimeout(function(){if(nm.scrollWidth>nm.clientWidth)nm.textContent=firstWord(full);},0);}}else{tr.classList.add('VA-card-open');ST.mExp[sec][id]=true;if(nm&&nm.dataset.full)nm.textContent=nm.dataset.full;}}}
    });
    }
    root.querySelectorAll('.VA-srch').forEach(function(inp){inp.addEventListener('input',function(){applyF(inp.dataset.sr);});});
    root.querySelectorAll('.VA-fp').forEach(function(fp){fp.addEventListener('click',function(e){e.stopPropagation();e.preventDefault();var sec=fp.dataset.fs;var val=fp.dataset.fv;ST.filters[sec]=val;var fw=fp.closest('.VA-fwrap');if(fw){fw.querySelectorAll('.VA-fp').forEach(function(x){x.classList.remove('act');});fp.classList.add('act');var btn=fw.querySelector('.VA-fb');if(btn)btn.querySelector('span:first-child').textContent=val==='all'?'Filter':val;if(val!=='all'&&btn)btn.classList.add('act');else if(btn)btn.classList.remove('act');fw.classList.remove('open');}applyF(sec);});});
    if(window.innerWidth<=600){root.querySelectorAll('.VA-t tbody tr[data-id]').forEach(function(tr){var nm=tr.querySelector('.VA-nm');if(nm&&nm.dataset.full&&!tr.classList.contains('VA-card-open')){setTimeout(function(){if(nm.scrollWidth>nm.clientWidth)nm.textContent=firstWord(nm.dataset.full);},0);}});}
  }

  renderAll();
})();
```
