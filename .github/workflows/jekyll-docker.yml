<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Chat Novel Studio</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Sarabun:wght@300;400;500;600;700&family=Noto+Serif+Thai:wght@400;600;700&display=swap');
:root{
  --bg:#0f0f14;--s1:#1a1a24;--s2:#22222f;--bd:#2e2e3e;
  --ac:#c084fc;--ac2:#818cf8;--gd:#fbbf24;--tx:#e2e2f0;
  --t2:#9898b8;--t3:#5a5a7a;--gn:#34d399;--rd:#f87171;
  --pk:#f472b6;--bl:#60a5fa;--cm:#7c3aed;--co:#1e1e2e;
  --r:12px;--rs:8px;
}
*{box-sizing:border-box;margin:0;padding:0;}
body{font-family:'Sarabun',sans-serif;background:var(--bg);color:var(--tx);height:100vh;overflow:hidden;}
/* SHELF */
.ov{position:fixed;inset:0;background:rgba(0,0,0,.78);z-index:300;display:flex;align-items:center;justify-content:center;}
.sb{background:var(--s1);border:1px solid var(--bd);border-radius:var(--r);width:700px;max-height:86vh;display:flex;flex-direction:column;}
.sh{padding:16px 22px;background:var(--s2);border-bottom:1px solid var(--bd);display:flex;align-items:center;gap:12px;}
.st{font-family:'Noto Serif Thai',serif;font-size:17px;font-weight:700;background:linear-gradient(135deg,var(--ac),var(--ac2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;}
.sbd{padding:18px;overflow-y:auto;flex:1;}
.nc{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:13px;}
.ncard{background:var(--s2);border:1px solid var(--bd);border-radius:var(--r);padding:14px;cursor:pointer;transition:all .2s;position:relative;}
.ncard:hover{border-color:var(--ac2);transform:translateY(-1px);}
.ncard.on{border-color:var(--ac);background:#1e1030;}
.nce{font-size:24px;margin-bottom:6px;}
.nct{font-family:'Noto Serif Thai',serif;font-size:13px;font-weight:700;color:var(--tx);margin-bottom:3px;}
.ncm{font-size:11px;color:var(--t3);}
.ncd{position:absolute;top:8px;right:8px;background:none;border:none;color:var(--t3);cursor:pointer;font-size:12px;opacity:0;transition:opacity .2s;}
.ncard:hover .ncd{opacity:1;}
.ncd:hover{color:var(--rd);}
.bnn{width:100%;background:rgba(192,132,252,.07);border:1px dashed var(--ac);color:var(--ac);border-radius:var(--r);padding:11px;font-family:'Sarabun',sans-serif;font-size:13px;cursor:pointer;transition:all .2s;}
.bnn:hover{background:rgba(192,132,252,.15);}
.bon{display:block;width:100%;background:linear-gradient(135deg,#7c3aed,#4f46e5);border:none;border-radius:var(--rs);color:#fff;font-family:'Sarabun',sans-serif;font-size:13px;font-weight:600;padding:11px;cursor:pointer;margin-top:13px;}
.bon:disabled{opacity:.4;cursor:not-allowed;}
.nnf{background:var(--s2);border:1px solid var(--bd);border-radius:var(--r);padding:14px;margin-bottom:12px;}
.nnf.hid{display:none;}
.ep{display:flex;flex-wrap:wrap;gap:5px;margin-bottom:8px;}
.eo{font-size:18px;cursor:pointer;padding:3px 5px;border-radius:var(--rs);border:1px solid transparent;transition:all .2s;}
.eo:hover,.eo.sel{background:rgba(192,132,252,.15);border-color:var(--ac);}
/* HEADER */
.hdr{background:linear-gradient(135deg,#1a0a2e,#16213e,#0f3460);border-bottom:1px solid var(--bd);padding:9px 16px;display:flex;align-items:center;gap:10px;}
.hnb{background:rgba(192,132,252,.1);border:1px solid rgba(192,132,252,.3);border-radius:var(--rs);padding:5px 11px;color:var(--ac);font-family:'Sarabun',sans-serif;font-size:12px;cursor:pointer;display:flex;align-items:center;gap:6px;transition:all .2s;}
.hnb:hover{background:rgba(192,132,252,.2);}
.bb{background:rgba(251,191,36,.1);border:1px solid rgba(251,191,36,.2);border-radius:20px;padding:3px 11px;font-size:11px;color:var(--gd);}
/* LAYOUT */
.lay{display:grid;grid-template-columns:240px 1fr 355px;height:calc(100vh - 48px);}
/* SIDEBAR */
.side{background:var(--s1);border-right:1px solid var(--bd);overflow-y:auto;display:flex;flex-direction:column;}
.slbl{font-size:10px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;color:var(--t3);padding:10px 12px 5px;}
.epl{padding:0 7px;display:flex;flex-direction:column;gap:4px;flex:1;}
.epi{background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);padding:8px 10px;cursor:pointer;transition:all .2s;display:flex;align-items:center;gap:7px;}
.epi:hover{border-color:var(--ac2);}
.epi.on{border-color:var(--ac);background:#2d1a4a;}
.epn{font-size:10px;font-weight:700;color:var(--ac);background:rgba(192,132,252,.1);padding:2px 6px;border-radius:20px;min-width:30px;text-align:center;flex-shrink:0;}
.epi-i{flex:1;min-width:0;}
.epi-t{font-size:12px;color:var(--tx);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;}
.epi-a{font-size:10px;color:var(--t3);}
.epd{width:5px;height:5px;border-radius:50%;flex-shrink:0;}
.dd{background:var(--gn);}.dp{background:var(--t3);}
.sact{padding:7px;}
.baep{width:100%;background:rgba(192,132,252,.07);border:1px dashed var(--ac);color:var(--ac);border-radius:var(--rs);padding:8px;font-family:'Sarabun',sans-serif;font-size:12px;cursor:pointer;transition:all .2s;}
.baep:hover{background:rgba(192,132,252,.15);}
.baep:disabled{opacity:.4;cursor:not-allowed;}
/* MAIN */
.main{overflow-y:auto;padding:18px 20px;background:var(--bg);}
/* CARDS */
.cd{background:var(--s1);border:1px solid var(--bd);border-radius:var(--r);margin-bottom:12px;overflow:hidden;}
.cdh{padding:10px 14px;background:var(--s2);border-bottom:1px solid var(--bd);display:flex;align-items:center;gap:8px;cursor:pointer;user-select:none;}
.cdh:hover{background:#262635;}
.cdi{font-size:13px;}
.cdt{font-size:13px;font-weight:600;}
.cdb{font-size:10px;background:rgba(192,132,252,.12);color:var(--ac);padding:2px 7px;border-radius:20px;}
.cdb.g{background:rgba(251,191,36,.12);color:var(--gd);}
.cdb.r{background:rgba(248,113,113,.12);color:var(--rd);}
.cdb.gn{background:rgba(52,211,153,.12);color:var(--gn);}
.ctg{margin-left:auto;color:var(--t3);font-size:11px;transition:transform .2s;}
.ctg.op{transform:rotate(180deg);}
.cdy{padding:14px;}
.cdy.hid{display:none;}
/* FORM */
.fg{display:flex;flex-direction:column;gap:5px;margin-bottom:11px;}
.fg:last-child{margin-bottom:0;}
.fl{font-size:11px;font-weight:600;color:var(--t2);}
.rq{color:var(--pk);}
input,textarea,select{background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);color:var(--tx);font-family:'Sarabun',sans-serif;font-size:13px;padding:7px 10px;transition:border-color .2s;width:100%;}
input:focus,textarea:focus,select:focus{outline:none;border-color:var(--ac);}
textarea{resize:vertical;min-height:60px;line-height:1.6;}
.g2{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.g3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;}
.chips{display:flex;flex-wrap:wrap;gap:5px;}
.chip{background:var(--s2);border:1px solid var(--bd);border-radius:20px;padding:3px 10px;cursor:pointer;font-size:12px;color:var(--t2);transition:all .2s;font-family:'Sarabun',sans-serif;}
.chip:hover{border-color:var(--ac2);}
.chip.sl{background:rgba(192,132,252,.15);border-color:var(--ac);color:var(--ac);}
/* SCENE */
.scl{display:flex;flex-direction:column;gap:8px;}
.scc{background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);overflow:hidden;}
.sch{padding:8px 11px;display:flex;align-items:center;gap:7px;background:rgba(0,0,0,.2);}
.scn{font-size:10px;font-weight:700;color:var(--ac2);background:rgba(129,140,248,.1);padding:2px 6px;border-radius:20px;}
.scti{background:transparent;border:none;color:var(--tx);font-size:12px;font-weight:600;flex:1;outline:none;font-family:'Sarabun',sans-serif;}
.bdsc{background:none;border:none;color:var(--t3);cursor:pointer;font-size:12px;padding:2px 5px;}
.bdsc:hover{color:var(--rd);}
.scb{padding:10px 11px;display:flex;flex-direction:column;gap:8px;}
.scl2{font-size:10px;color:var(--t3);font-weight:600;margin-bottom:3px;}
.sci{font-size:12px;padding:5px 8px;}
.basc{width:100%;background:transparent;border:1px dashed var(--bd);color:var(--t3);border-radius:var(--rs);padding:6px;font-size:11px;cursor:pointer;font-family:'Sarabun',sans-serif;transition:all .2s;}
.basc:hover{border-color:var(--ac2);color:var(--t2);}
/* TENSION */
.tr{display:flex;align-items:center;gap:8px;margin-bottom:4px;}
.tl{font-size:11px;color:var(--t2);width:65px;flex-shrink:0;}
.ts{flex:1;-webkit-appearance:none;height:3px;border-radius:2px;background:var(--bd);outline:none;}
.ts::-webkit-slider-thumb{-webkit-appearance:none;width:12px;height:12px;border-radius:50%;background:var(--ac);cursor:pointer;}
.tv{font-size:11px;color:var(--gd);width:30px;text-align:right;}
/* CHAR LOCK */
.clg{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;}
.clc{background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);padding:10px;}
.clh{font-size:11px;font-weight:700;margin-bottom:7px;display:flex;align-items:center;gap:5px;}
.cld{width:6px;height:6px;border-radius:50%;}
.cln{background:transparent;border:none;color:var(--tx);font-size:12px;font-weight:700;outline:none;font-family:'Sarabun',sans-serif;width:100%;}
/* CHECKLIST */
.ckl{display:flex;flex-direction:column;gap:4px;}
.cki{display:flex;align-items:center;gap:6px;background:var(--bg);border:1px solid var(--bd);border-radius:var(--rs);padding:5px 9px;}
.cks{font-size:11px;flex-shrink:0;}
.cki input{background:transparent;border:none;font-size:12px;padding:0;}
.bac{background:transparent;border:1px dashed var(--bd);color:var(--t3);border-radius:var(--rs);padding:4px 9px;font-size:11px;cursor:pointer;font-family:'Sarabun',sans-serif;transition:all .2s;text-align:left;width:100%;margin-top:3px;}
.bac:hover{border-color:var(--t2);color:var(--t2);}
/* TAGS */
.tw{background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);padding:5px 8px;display:flex;flex-wrap:wrap;gap:4px;cursor:text;min-height:36px;align-items:center;}
.tw:focus-within{border-color:var(--ac);}
.tg{background:rgba(192,132,252,.15);color:var(--ac);border-radius:20px;padding:2px 8px;font-size:11px;display:flex;align-items:center;gap:3px;}
.tx2{cursor:pointer;opacity:.7;font-size:10px;}
.tx2:hover{opacity:1;}
.ti{border:none;background:transparent;outline:none;font-size:12px;color:var(--tx);min-width:60px;flex:1;padding:1px 0;}
/* PAYOFF */
.poi{display:grid;grid-template-columns:65px 1fr;gap:6px;align-items:center;margin-bottom:5px;}
/* GENERATE */
.gw{padding:12px 0 0;display:flex;gap:8px;}
.bgen{flex:1;background:linear-gradient(135deg,#7c3aed,#4f46e5);border:none;border-radius:var(--r);color:#fff;font-family:'Sarabun',sans-serif;font-size:13px;font-weight:700;padding:12px 14px;cursor:pointer;transition:all .3s;display:flex;align-items:center;justify-content:center;gap:8px;}
.bgen:hover{transform:translateY(-1px);box-shadow:0 8px 24px rgba(124,58,237,.4);}
.bgen:disabled{opacity:.5;cursor:not-allowed;transform:none;}
.bclr{background:var(--s2);border:1px solid var(--bd);border-radius:var(--r);color:var(--t2);font-family:'Sarabun',sans-serif;font-size:12px;padding:12px 12px;cursor:pointer;transition:all .2s;}
.bclr:hover{border-color:var(--rd);color:var(--rd);}
/* EP HEADER */
.eph{background:linear-gradient(135deg,rgba(124,58,237,.1),rgba(79,70,229,.08));border:1px solid rgba(192,132,252,.18);border-radius:var(--r);padding:13px 16px;margin-bottom:14px;display:flex;align-items:flex-start;gap:11px;}
.epi2{flex:1;}
.epnl{font-size:10px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;color:var(--ac2);margin-bottom:3px;}
.epte{background:transparent;border:none;font-family:'Noto Serif Thai',serif;font-size:16px;font-weight:700;color:var(--tx);width:100%;outline:none;margin-bottom:4px;}
.epas{background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);color:var(--ac2);font-family:'Sarabun',sans-serif;font-size:12px;padding:4px 8px;}
.bdep{background:none;border:1px solid var(--bd);border-radius:var(--rs);color:var(--t3);font-family:'Sarabun',sans-serif;font-size:11px;padding:5px 10px;cursor:pointer;transition:all .2s;margin-left:auto;flex-shrink:0;}
.bdep:hover{border-color:var(--rd);color:var(--rd);}
/* OUTPUT */
.op{background:var(--s1);border-left:1px solid var(--bd);display:flex;flex-direction:column;}
.oh{padding:10px 14px;background:var(--s2);border-bottom:1px solid var(--bd);display:flex;align-items:center;justify-content:space-between;}
.oht{font-size:12px;font-weight:600;display:flex;align-items:center;gap:6px;}
.oas{display:flex;gap:6px;}
.bcp,.bdl{background:var(--s1);border:1px solid var(--bd);border-radius:var(--rs);color:var(--t2);font-family:'Sarabun',sans-serif;font-size:11px;padding:4px 9px;cursor:pointer;transition:all .2s;}
.bcp:hover{border-color:var(--gn);color:var(--gn);}
.bdl:hover{border-color:var(--bl);color:var(--bl);}
.ob{flex:1;overflow-y:auto;padding:14px;}
.stb{padding:7px 14px;background:var(--bg);border-top:1px solid var(--bd);display:flex;gap:12px;align-items:center;}
.st{font-size:11px;color:var(--t3);display:flex;align-items:center;gap:3px;}
.sv{color:var(--ac);font-weight:600;}
/* PREVIEW */
.np{display:flex;flex-direction:column;gap:12px;}
.nar{background:rgba(255,255,255,.03);border-left:3px solid var(--ac2);padding:8px 11px;border-radius:0 var(--rs) var(--rs) 0;font-size:12px;color:var(--t2);font-style:italic;line-height:1.7;}
.cbl{background:var(--s2);border:1px solid var(--bd);border-radius:var(--r);overflow:hidden;}
.chb{background:var(--bg);padding:6px 11px;font-size:11px;color:var(--t3);border-bottom:1px solid var(--bd);}
.cms{padding:10px 11px;display:flex;flex-direction:column;gap:7px;}
.br{display:flex;gap:6px;align-items:flex-end;}
.br.r{flex-direction:row-reverse;}
.bav{width:22px;height:22px;border-radius:50%;background:linear-gradient(135deg,var(--ac),var(--ac2));display:flex;align-items:center;justify-content:center;font-size:9px;font-weight:700;flex-shrink:0;color:#fff;}
.bav.o{background:linear-gradient(135deg,#374151,#4b5563);}
.bw{max-width:76%;display:flex;flex-direction:column;gap:2px;}
.br.r .bw{align-items:flex-end;}
.bname2{font-size:10px;color:var(--t3);padding:0 3px;}
.bub{background:var(--co);border:1px solid var(--bd);border-radius:12px 12px 12px 3px;padding:6px 10px;font-size:12px;color:var(--tx);line-height:1.6;word-break:break-word;}
.bub.m{background:var(--cm);border-color:transparent;border-radius:12px 12px 3px 12px;}
.al{font-size:11px;color:var(--t3);font-style:italic;text-align:center;padding:2px;}
.brd{font-size:10px;color:var(--bl);text-align:right;padding:0 3px;}
/* LOADING/EMPTY */
.ld{display:flex;flex-direction:column;align-items:center;justify-content:center;height:260px;gap:12px;}
.sp{width:32px;height:32px;border:3px solid var(--bd);border-top-color:var(--ac);border-radius:50%;animation:spin .8s linear infinite;}
@keyframes spin{to{transform:rotate(360deg);}}
.em{display:flex;flex-direction:column;align-items:center;justify-content:center;height:100%;gap:10px;opacity:.5;text-align:center;padding:30px;}
.ei{font-size:36px;}
.et{font-size:12px;color:var(--t2);line-height:1.7;}
/* WELCOME */
.wc{display:flex;flex-direction:column;align-items:center;justify-content:center;height:100%;text-align:center;gap:13px;padding:32px;}
.wi{font-size:46px;}
.wt{font-family:'Noto Serif Thai',serif;font-size:20px;font-weight:700;}
.ws{font-size:12px;color:var(--t2);line-height:1.8;max-width:320px;}
.wp{background:var(--s2);border:1px solid var(--bd);border-radius:var(--r);padding:12px 16px;text-align:left;width:100%;max-width:320px;}
.wpl{font-size:10px;font-weight:700;color:var(--ac);letter-spacing:1px;text-transform:uppercase;margin-bottom:4px;}
.wpt{font-size:12px;color:var(--t2);line-height:1.6;}
::-webkit-scrollbar{width:4px;}
::-webkit-scrollbar-track{background:transparent;}
::-webkit-scrollbar-thumb{background:var(--bd);border-radius:2px;}
.oel{font-size:10px;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;color:var(--t3);margin-bottom:11px;display:flex;align-items:center;gap:6px;}
.oed{width:5px;height:5px;border-radius:50%;background:var(--ac);}
/* PASTE BRIEF MODAL */
.pb-ov{position:fixed;inset:0;background:rgba(0,0,0,.82);z-index:400;display:none;align-items:center;justify-content:center;}
.pb-ov.open{display:flex;}
.pb-box{background:var(--s1);border:1px solid var(--bd);border-radius:var(--r);width:620px;max-height:88vh;display:flex;flex-direction:column;}
.pb-hd{padding:14px 18px;background:var(--s2);border-bottom:1px solid var(--bd);display:flex;align-items:center;gap:10px;}
.pb-ti{font-family:'Noto Serif Thai',serif;font-size:15px;font-weight:700;background:linear-gradient(135deg,var(--ac),var(--ac2));-webkit-background-clip:text;-webkit-text-fill-color:transparent;}
.pb-body{padding:16px 18px;overflow-y:auto;flex:1;display:flex;flex-direction:column;gap:12px;}
.pb-area{background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);color:var(--tx);font-family:'Sarabun',sans-serif;font-size:12px;padding:10px 12px;resize:none;height:220px;line-height:1.7;transition:border-color .2s;}
.pb-area:focus{outline:none;border-color:var(--ac);}
.pb-hint{font-size:11px;color:var(--t3);line-height:1.7;}
.pb-hint b{color:var(--ac2);}
.pb-ft{padding:12px 18px;background:var(--s2);border-top:1px solid var(--bd);display:flex;gap:8px;align-items:center;}
.pb-parse{flex:1;background:linear-gradient(135deg,#7c3aed,#4f46e5);border:none;border-radius:var(--rs);color:#fff;font-family:'Sarabun',sans-serif;font-size:13px;font-weight:700;padding:10px;cursor:pointer;transition:all .2s;}
.pb-parse:hover{opacity:.9;}
.pb-parse:disabled{opacity:.4;cursor:not-allowed;}
.pb-cancel{background:var(--s1);border:1px solid var(--bd);border-radius:var(--rs);color:var(--t2);font-family:'Sarabun',sans-serif;font-size:12px;padding:10px 14px;cursor:pointer;}
.pb-cancel:hover{border-color:var(--rd);color:var(--rd);}
.pb-preview{background:var(--bg);border:1px solid var(--bd);border-radius:var(--rs);padding:11px 13px;font-size:11px;color:var(--t2);line-height:1.8;display:none;}
.pb-preview.show{display:block;}
.pb-preview b{color:var(--ac);}
.pb-tag{display:inline-block;background:rgba(192,132,252,.12);color:var(--ac);border-radius:20px;padding:1px 7px;font-size:10px;margin:1px;}
.pb-ok{flex:1;background:linear-gradient(135deg,#059669,#0d9488);border:none;border-radius:var(--rs);color:#fff;font-family:'Sarabun',sans-serif;font-size:13px;font-weight:700;padding:10px;cursor:pointer;display:none;}
.pb-ok.show{display:block;}
.bpaste{background:rgba(192,132,252,.08);border:1px solid rgba(192,132,252,.25);border-radius:var(--rs);color:var(--ac);font-family:'Sarabun',sans-serif;font-size:11px;padding:4px 10px;cursor:pointer;transition:all .2s;display:flex;align-items:center;gap:5px;margin-left:auto;}
.bpaste:hover{background:rgba(192,132,252,.18);}
/* API KEY */
.ak-wrap{display:flex;align-items:center;gap:6px;}
.ak-input{background:rgba(0,0,0,.3);border:1px solid var(--bd);border-radius:var(--rs);color:var(--t2);font-family:'Sarabun',sans-serif;font-size:11px;padding:4px 8px;width:200px;transition:border-color .2s;}
.ak-input:focus{outline:none;border-color:var(--ac);color:var(--tx);}
.ak-input::placeholder{color:var(--t3);}
.ak-ok{background:rgba(52,211,153,.1);border:1px solid rgba(52,211,153,.3);border-radius:var(--rs);color:var(--gn);font-family:'Sarabun',sans-serif;font-size:11px;padding:4px 8px;cursor:pointer;}
.ak-ok:hover{background:rgba(52,211,153,.2);}
.ak-dot{width:7px;height:7px;border-radius:50%;background:var(--t3);flex-shrink:0;}
.ak-dot.on{background:var(--gn);}
</style>
</head>
<body>

<div class="ov" id="ovl">
  <div class="sb">
    <div class="sh">
      <span style="font-size:20px">📚</span>
      <div><div class="st">Novel Shelf</div><div style="font-size:11px;color:var(--t3)">เลือกหรือสร้างนิยาย</div></div>
    </div>
    <div class="sbd">
      <div class="nnf hid" id="nnf">
        <div style="font-size:13px;font-weight:600;margin-bottom:11px;color:var(--ac)">✍️ สร้างนิยายใหม่</div>
        <div class="fg"><label class="fl">Emoji</label><div class="ep" id="erow"></div></div>
        <div class="fg"><label class="fl">ชื่อนิยาย <span class="rq">*</span></label><input id="nnTi" type="text" placeholder="ชื่อเรื่อง..."></div>
        <div class="g2">
          <div class="fg"><label class="fl">แนวเรื่อง</label><input id="nnGe" type="text" placeholder="โรแมนติก ดราม่า..."></div>
          <div class="fg"><label class="fl">จำนวนตอน</label><input id="nnEp" type="number" value="20" min="1"></div>
        </div>
        <div class="fg"><label class="fl">Synopsis</label><textarea id="nnSy" placeholder="โครงเรื่องย่อ..." style="min-height:46px"></textarea></div>
        <div style="display:flex;gap:8px;margin-top:4px">
          <button style="flex:1;background:linear-gradient(135deg,#7c3aed,#4f46e5);border:none;border-radius:var(--rs);color:#fff;font-family:'Sarabun',sans-serif;font-size:13px;font-weight:600;padding:9px;cursor:pointer" onclick="createNovel()">✅ สร้าง</button>
          <button style="background:var(--s2);border:1px solid var(--bd);border-radius:var(--rs);color:var(--t2);font-family:'Sarabun',sans-serif;font-size:13px;padding:9px 13px;cursor:pointer" onclick="G('nnf').classList.add('hid')">ยกเลิก</button>
        </div>
      </div>
      <div class="nc" id="nCards"><div style="grid-column:1/-1;text-align:center;color:var(--t3);font-size:12px;padding:22px">ยังไม่มีนิยาย กด "+ สร้างนิยายใหม่"</div></div>
      <button class="bnn" onclick="G('nnf').classList.toggle('hid');G('nnTi')?.focus()">+ สร้างนิยายใหม่</button>
      <button class="bon" id="btnOn" onclick="openNovel()" disabled>📖 เปิดนิยายที่เลือก</button>
    </div>
  </div>
</div>

<div class="hdr">
  <button class="hnb" onclick="G('ovl').style.display='flex';renderShelf()"><span id="hEm">📚</span> <span id="hNm">เลือกนิยาย</span> ▼</button>
  <div style="width:1px;height:20px;background:var(--bd);margin:0 6px"></div>
  <div>
    <div style="font-size:12px;font-weight:600;color:var(--tx)" id="hEp">—</div>
    <div style="font-size:10px;color:var(--t3)" id="hMt"></div>
  </div>
  <div style="margin-left:auto;display:flex;align-items:center;gap:8px">
    <div class="ak-wrap">
      <div class="ak-dot" id="akDot"></div>
      <input class="ak-input" id="akInput" type="text" placeholder="วาง OpenRouter API Key (sk-or-...)" oninput="akChanged()" style="width:270px">
      <button class="ak-ok" onclick="akSave()">บันทึก</button>
      <span id="akStatus" style="font-size:11px;min-width:70px"></span>
    </div>
    <button class="bpaste" id="btnPaste" onclick="openPasteBrief()" disabled>📋 วาง EP Brief</button>
    <div class="bb">🎯 เป้าหมาย 120–150 bubble / ตอน</div>
  </div>
</div>

<!-- PASTE BRIEF MODAL -->
<div class="pb-ov" id="pbOv">
  <div class="pb-box">
    <div class="pb-hd">
      <span style="font-size:20px">📋</span>
      <div><div class="pb-ti">วาง EP Brief</div><div style="font-size:11px;color:var(--t3)">Paste brief แล้วระบบแปลงให้อัตโนมัติ</div></div>
      <button style="margin-left:auto;background:none;border:none;color:var(--t3);cursor:pointer;font-size:18px" onclick="closePasteBrief()">✕</button>
    </div>
    <div class="pb-body">
      <div>
        <div class="fl" style="margin-bottom:6px">📄 วาง Brief ของตอนที่ต้องการ</div>
        <textarea class="pb-area" id="pbText" placeholder="วาง EP Brief ที่นี่...

ตัวอย่างรูปแบบที่รับได้:
🎯 เป้าหมายตอน / Plot Goal
💭 Emotional Goal  
👤 ตัวละคร + สถานะ
✅ ต้องมี / ❌ ห้ามมี
😱 Cliffhanger
🔥 จุดพีค
ฯลฯ" oninput="pbChanged()"></textarea>
      </div>
      <div class="pb-hint">รองรับทุกรูปแบบ: <b>emoji header</b>, <b>เครื่องหมาย *</b>, <b>ข้อความธรรมดา</b> — AI จะแปลงให้เองทั้งหมด</div>
      <div class="pb-preview" id="pbPreview"></div>
    </div>
    <div class="pb-ft">
      <button class="pb-cancel" onclick="closePasteBrief()">ยกเลิก</button>
      <button class="pb-parse" id="pbParseBtn" onclick="parseBrief()" disabled>✨ แปลง Brief → กรอก Field อัตโนมัติ</button>
      <button class="pb-ok" id="pbOkBtn" onclick="applyBrief()">✅ ใช้ข้อมูลนี้เลย</button>
    </div>
  </div>
</div>

<div class="lay">
  <div class="side">
    <div class="slbl">EPISODES</div>
    <div class="epl" id="epList"></div>
    <div class="sact"><button class="baep" id="btnAep" onclick="addEp()" disabled>+ เพิ่มตอนใหม่</button></div>
  </div>

  <div class="main" id="mainArea">
    <div class="wc" id="wsc">
      <div class="wi">📖</div>
      <div class="wt">Chat Novel Studio</div>
      <div class="ws">สร้างนิยายแชทอย่างมีระบบ ตั้งแต่ Story Bible จนถึง Generate ทีละตอน</div>
      <div class="wp"><div class="wpl">Step 1</div><div class="wpt">คลิก <strong style="color:var(--ac)">เลือกนิยาย</strong> ด้านบน<br>สร้างหรือเลือกนิยาย</div></div>
      <div class="wp"><div class="wpl">Step 2</div><div class="wpt">กด <strong style="color:var(--ac)">+ เพิ่มตอนใหม่</strong><br>กรอก Story Bible ทุกฟิลด์</div></div>
      <div class="wp"><div class="wpl">Step 3</div><div class="wpt">กด <strong style="color:var(--ac)">✨ Generate</strong><br>AI เขียน 120–150 bubble ให้เลย</div></div>
    </div>
    <div id="epEd" style="display:none"></div>
  </div>

  <div class="op">
    <div class="oh">
      <div class="oht">📱 <span id="outTi">Preview</span></div>
      <div class="oas">
        <button class="bcp" onclick="copyOut()">📋 Copy</button>
        <button class="bdl" onclick="dlOut()">💾 Save</button>
      </div>
    </div>
    <div class="ob" id="outBd"><div class="em"><div class="ei">📱</div><div class="et">กด Generate<br>เพื่อดู Preview</div></div></div>
    <div class="stb" id="stb" style="display:none">
      <div class="st">💬 <span class="sv" id="sBub">0</span> bubble</div>
      <div class="st">📝 <span class="sv" id="sWd">0</span> คำ</div>
      <div class="st">🕐 <span class="sv" id="sRd">0</span> นาที</div>
    </div>
  </div>
</div>

<script>
const G=id=>document.getElementById(id);
const EM=['📖','💜','🌸','⚡','🔥','🌙','💀','🌊','✨','🏯','🎭','💔','👑','🦋','🌹','🎪','🧊','🍂','🌺','💫'];
const CT=[{k:'DM',i:'📱',l:'DM/LINE'},{k:'GROUP',i:'👥',l:'กลุ่มแชท'},{k:'CALL',i:'📞',l:'โทรศัพท์'},{k:'VIDEOCALL',i:'🎥',l:'วิดีโอคอล'},{k:'IG',i:'📸',l:'Instagram'},{k:'FB',i:'💙',l:'Facebook'},{k:'X',i:'🐦',l:'X/Twitter'},{k:'TIKTOK',i:'🎵',l:'TikTok'},{k:'IRL',i:'🤝',l:'เจอกันจริง'},{k:'SILENT',i:'🌙',l:'Silent'}];
const MO=['ฟิน','หวาน','ตลก','เขิน','หน่วง','อึดอัด','หึง','ใจหาย','ระทึก','เศร้า','โกรธ','ช็อก','ตื่นเต้น','ประชด','อ้อน','ตึงเครียด'];
const RM=['แฟนเก่า','ยังค้างคา','ไม่พร้อมเจอ','ยังไม่มูฟออน','แอบชอบ','งอน','หึง','คืนดี','ห่างกัน','ตึงเครียด','ยังไม่สนิท','เขินกัน','รักกัน','ทะเลาะ'];
const EM2=['ช็อก','อึดอัด','คิดถึง','ใจสั่น','ฟิน','หน่วง','หึง','โกรธ','เจ็บปวด','ตื่นเต้น','ซึ้ง','ตลก','เศร้า'];
const PF=['Inciting Incident','Rising Action','Midpoint','Crisis','Climax','Falling Action','Resolution','Setup','Reveal','Payoff','Breather','Twist'];
const AR=['ARC 1','ARC 2','ARC 3','ARC 4','ARC 5'];

let db={novels:[],cNid:null,cEid:null};
let rawOut='';
let pEm='📖';
let apiKey='';
try{const s=localStorage.getItem('cns4');if(s)db=JSON.parse(s);}catch(e){}
try{apiKey=localStorage.getItem('cns_ak')||'';}catch(e){}
function akChanged(){
  const v=G('akInput').value.trim();
  if(v.length>10){
    apiKey=v;
    try{localStorage.setItem('cns_ak',v);}catch(e){}
    G('akDot').className='ak-dot on';
    G('akStatus').textContent='✓ พร้อมใช้';
    G('akStatus').style.color='var(--gn)';
  } else {
    G('akDot').className='ak-dot';
    G('akStatus').textContent='';
  }
}
function akSave(){
  const v=G('akInput').value.trim();
  if(!v||v.length<10){
    G('akStatus').textContent='❌ Key ไม่ถูกต้อง';
    G('akStatus').style.color='var(--rd)';
    return;
  }
  apiKey=v;
  try{localStorage.setItem('cns_ak',v);}catch(e){}
  G('akDot').className='ak-dot on';
  G('akStatus').textContent='✓ บันทึกแล้ว';
  G('akStatus').style.color='var(--gn)';
}
function akRender(){
  const ok=apiKey&&apiKey.length>10;
  G('akDot').className='ak-dot'+(ok?' on':'');
  if(ok){
    G('akInput').value=apiKey;
    G('akStatus').textContent='✓ พร้อมใช้';
    G('akStatus').style.color='var(--gn)';
  }
}

function sv(){try{localStorage.setItem('cns4',JSON.stringify(db));}catch(e){}}

function renderShelf(){
  G('erow').innerHTML=EM.map(e=>`<span class="eo" onclick="pickE('${e}',this)">${e}</span>`).join('');
  const nc=G('nCards');
  if(!db.novels.length){nc.innerHTML='<div style="grid-column:1/-1;text-align:center;color:var(--t3);font-size:12px;padding:22px">ยังไม่มีนิยาย</div>';G('btnOn').disabled=true;return;}
  nc.innerHTML=db.novels.map(n=>`
    <div class="ncard ${n.id===db.cNid?'on':''}" onclick="selNv(${n.id})">
      <button class="ncd" onclick="event.stopPropagation();delNv(${n.id})">✕</button>
      <div class="nce">${n.emoji||'📖'}</div>
      <div class="nct">${n.title||'ไม่มีชื่อ'}</div>
      <div class="ncm">${n.genre||''} · ${n.eps?.length||0}/${n.totalEps||20} ตอน</div>
      <div class="ncm" style="margin-top:3px">${(n.synopsis||'').substring(0,50)}${(n.synopsis||'').length>50?'...':''}</div>
    </div>`).join('');
  G('btnOn').disabled=!db.cNid;
}
function pickE(e,el){pEm=e;document.querySelectorAll('.eo').forEach(o=>o.classList.remove('sel'));el.classList.add('sel');}
function selNv(id){db.cNid=id;sv();renderShelf();}
function createNovel(){
  const t=(G('nnTi')?.value||'').trim();if(!t){G('nnTi')?.focus();return;}
  const n={id:Date.now(),emoji:pEm||'📖',title:t,genre:G('nnGe')?.value?.trim()||'',totalEps:parseInt(G('nnEp')?.value)||20,synopsis:G('nnSy')?.value?.trim()||'',eps:[]};
  db.novels.push(n);db.cNid=n.id;sv();
  G('nnf').classList.add('hid');
  ['nnTi','nnGe','nnSy'].forEach(id=>{const el=G(id);if(el)el.value='';});
  if(G('nnEp'))G('nnEp').value='20';
  renderShelf();
}
function delNv(id){if(!confirm('ลบนิยายนี้?'))return;db.novels=db.novels.filter(n=>n.id!==id);if(db.cNid===id){db.cNid=null;db.cEid=null;}sv();renderShelf();}
function openNovel(){
  const nv=cNv();if(!nv)return;
  G('ovl').style.display='none';
  G('hEm').textContent=nv.emoji||'📖';G('hNm').textContent=nv.title;
  G('btnAep').disabled=false;db.cEid=null;sv();renderSB();
  G('wsc').style.display='flex';G('epEd').style.display='none';
  G('hMt').textContent=`${nv.eps?.length||0} ตอน · ${nv.genre||''}`;
}
function cNv(){return db.novels.find(n=>n.id===db.cNid);}
function cEp(){const nv=cNv();return nv?.eps?.find(e=>e.id===db.cEid);}

function nwEp(){
  const nv=cNv();if(!nv)return null;
  const num=(nv.eps?.length||0)+1;
  return {id:Date.now(),num,title:`ตอนที่ ${num}`,arc:'ARC 1',plotGoal:[''],emotionalGoal:[],plotFunction:'',theme:'',hook:'',mainChars:[],supportChars:[],mainCharName:'',relationshipMood:[],timeline:'',scenes:[nwSc(1)],charLocks:[{name:'',color:'var(--ac)',rules:['']},{name:'',color:'var(--pk)',rules:['']},{name:'',color:'var(--gd)',rules:['']}],toPlant:[''],payoffs:[{ep:'EP2',text:''}],mustHappen:[''],mustNotHappen:[''],cliffhanger:'',endingPoint:'',readerEmotion:[''],status:'pending',generatedOutput:null};
}
function nwSc(n){return {id:Date.now()+Math.random(),num:n,title:`Scene ${n}`,location:'',time:'',chatType:'DM',participants:[],moods:[],goal:'',tension:5};}
function addEp(){const nv=cNv();if(!nv)return;if(!nv.eps)nv.eps=[];const ep=nwEp();nv.eps.push(ep);sv();renderSB();selEp(ep.id);}
function selEp(id){
  db.cEid=id;sv();renderSB();renderEd(id);
  const ep=cEp();
  G('wsc').style.display='none';G('epEd').style.display='block';
  G('btnPaste').disabled=false;
  if(ep?.generatedOutput)renderOut(ep.generatedOutput,ep);
  else{G('outBd').innerHTML='<div class="em"><div class="ei">✍️</div><div class="et">กรอกข้อมูล<br>แล้วกด Generate</div></div>';G('stb').style.display='none';}
}
function delEp(id){const nv=cNv();if(!nv)return;nv.eps=nv.eps.filter(e=>e.id!==id);nv.eps.forEach((e,i)=>e.num=i+1);db.cEid=null;sv();renderSB();G('wsc').style.display='flex';G('epEd').style.display='none';G('btnPaste').disabled=true;}
function renderSB(){
  const nv=cNv();if(!nv){G('epList').innerHTML='';return;}
  G('hMt').textContent=`${nv.eps?.length||0} ตอน · ${nv.genre||''}`;
  G('hEp').textContent=nv.title;
  if(!nv.eps||nv.eps.length===0){
    G('epList').innerHTML='<div style="padding:16px 10px;text-align:center;color:var(--t3);font-size:11px;line-height:1.8">ยังไม่มีตอน<br><span style="color:var(--ac)">กด "+ เพิ่มตอนใหม่"<br>ด้านล่าง</span></div>';
    return;
  }
  G('epList').innerHTML=(nv.eps||[]).map(ep=>`
    <div class="epi ${ep.id===db.cEid?'on':''}" onclick="selEp(${ep.id})">
      <span class="epn">EP${ep.num}</span>
      <div class="epi-i"><div class="epi-t">${ep.title||`ตอนที่ ${ep.num}`}</div><div class="epi-a">${ep.arc||''}</div></div>
      <div class="epd ${ep.status==='done'?'dd':'dp'}"></div>
    </div>`).join('');
}

function esc(s){return(s||'').replace(/&/g,'&amp;').replace(/"/g,'&quot;').replace(/</g,'&lt;').replace(/>/g,'&gt;');}
function gEp(id){const nv=cNv();return nv?.eps?.find(e=>e.id===id);}
function renderEd(id){const nv=cNv();if(!nv)return;const ep=nv.eps?.find(e=>e.id===id);if(!ep)return;G('epEd').innerHTML=buildEd(ep);G('outTi').textContent=`EP${ep.num} · ${ep.title}`;}

function buildEd(ep){
  const id=ep.id;
  return `
  <div class="eph">
    <div style="font-size:22px">📕</div>
    <div class="epi2">
      <div class="epnl">EP${ep.num} · STORY BIBLE</div>
      <input class="epte" value="${esc(ep.title)}" placeholder="ชื่อตอน..." oninput="upd(${id},'title',this.value)">
      <select class="epas" onchange="upd(${id},'arc',this.value)">${AR.map(a=>`<option ${ep.arc===a?'selected':''}>${a}</option>`).join('')}</select>
    </div>
    <button class="bdep" onclick="delEp(${id})">🗑️ ลบ</button>
  </div>

  <div class="cd">
    <div class="cdh" onclick="tog('pg${id}')"><span class="cdi">🎯</span><span class="cdt">Plot Goal</span><span class="cdb">เป้าหมายตอน</span><span class="ctg op" id="t-pg${id}">▼</span></div>
    <div class="cdy" id="b-pg${id}">
      <div class="fg"><label class="fl">Plot Goal <span class="rq">*</span></label>
        <div class="ckl">${ep.plotGoal.map((g,i)=>`<div class="cki"><span class="cks" style="color:var(--ac)">🎯</span><input type="text" value="${esc(g)}" placeholder="เป้าหมาย..." oninput="ua(${id},'plotGoal',${i},this.value)"></div>`).join('')}</div>
        <button class="bac" onclick="aa(${id},'plotGoal')">+ เพิ่ม</button>
      </div>
      <div class="fg"><label class="fl">Emotional Goal</label><div class="chips">${EM2.map(m=>`<div class="chip ${ep.emotionalGoal.includes(m)?'sl':''}" onclick="ta(${id},'emotionalGoal','${m}',this)">${m}</div>`).join('')}</div></div>
      <div class="g2">
        <div class="fg"><label class="fl">Plot Function</label><select onchange="upd(${id},'plotFunction',this.value)"><option value="">เลือก...</option>${PF.map(p=>`<option ${ep.plotFunction===p?'selected':''}>${p}</option>`).join('')}</select></div>
        <div class="fg"><label class="fl">Timeline</label><input type="text" value="${esc(ep.timeline)}" placeholder="วันแรกที่กลับไทย..." oninput="upd(${id},'timeline',this.value)"></div>
      </div>
      <div class="fg"><label class="fl">Theme</label><input type="text" value="${esc(ep.theme)}" placeholder="บางคนที่คิดว่าหายไปแล้ว..." oninput="upd(${id},'theme',this.value)"></div>
      <div class="fg"><label class="fl">Hook</label><textarea placeholder="ตะขอดึงให้อยากอ่าน..." oninput="upd(${id},'hook',this.value)">${esc(ep.hook)}</textarea></div>
    </div>
  </div>

  <div class="cd">
    <div class="cdh" onclick="tog('cf${id}')"><span class="cdi">👥</span><span class="cdt">Character Focus</span><span class="cdb">ตัวละครในตอน</span><span class="ctg op" id="t-cf${id}">▼</span></div>
    <div class="cdy" id="b-cf${id}">
      <div class="g2">
        <div class="fg"><label class="fl">Main</label>${bTg(id,'mc',ep.mainChars,'ชื่อ + Enter...')}</div>
        <div class="fg"><label class="fl">Support</label>${bTg(id,'sc2',ep.supportChars,'ชื่อ + Enter...')}</div>
      </div>
      <div class="fg"><label class="fl">ตัวละคร "เจ้าของ" bubble (ขวา)</label><input type="text" value="${esc(ep.mainCharName)}" placeholder="ชื่อที่อยู่ฝั่งขวา..." oninput="upd(${id},'mainCharName',this.value)"></div>
      <div class="fg"><label class="fl">Relationship Mood</label><div class="chips">${RM.map(m=>`<div class="chip ${ep.relationshipMood.includes(m)?'sl':''}" onclick="ta(${id},'relationshipMood','${m}',this)">${m}</div>`).join('')}</div></div>
    </div>
  </div>

  <div class="cd">
    <div class="cdh" onclick="tog('sc${id}')"><span class="cdi">🎬</span><span class="cdt">Scene Breakdown</span><span class="cdb g">${ep.scenes.length} ฉาก</span><span class="ctg op" id="t-sc${id}">▼</span></div>
    <div class="cdy" id="b-sc${id}">
      <div class="scl">${ep.scenes.map((sc,i)=>bSc(id,sc,i)).join('')}</div>
      <button class="basc" onclick="addSc(${id})">+ เพิ่ม Scene</button>
      <div style="margin-top:12px"><div class="fl" style="margin-bottom:7px">⚡ Tension Level</div>
        ${ep.scenes.map((sc,i)=>`<div class="tr"><span class="tl">Scene ${i+1}</span><input type="range" class="ts" min="1" max="10" value="${sc.tension||5}" oninput="uSc(${id},'${sc.id}','tension',parseInt(this.value));this.nextElementSibling.textContent=this.value+'/10'"><span class="tv">${sc.tension||5}/10</span></div>`).join('')}
      </div>
    </div>
  </div>

  <div class="cd">
    <div class="cdh" onclick="tog('cl${id}')"><span class="cdi">🔒</span><span class="cdt">Character Lock</span><span class="cdb">บุคลิกที่ต้องรักษา</span><span class="ctg op" id="t-cl${id}">▼</span></div>
    <div class="cdy" id="b-cl${id}">
      <div class="clg">${ep.charLocks.map((cl,i)=>`<div class="clc"><div class="clh"><div class="cld" style="background:${cl.color}"></div><input class="cln" value="${esc(cl.name)}" placeholder="ชื่อ..." oninput="uCL(${id},${i},'name',this.value)"></div>
          <div class="ckl">${cl.rules.map((r,j)=>`<div class="cki" style="padding:4px 8px"><span class="cks" style="color:${cl.color}">•</span><input type="text" value="${esc(r)}" placeholder="กฎ..." style="font-size:12px" oninput="uCLR(${id},${i},${j},this.value)"></div>`).join('')}</div>
          <button class="bac" onclick="aCLR(${id},${i})">+ เพิ่ม</button>
        </div>`).join('')}
      </div>
    </div>
  </div>

  <div class="cd">
    <div class="cdh" onclick="tog('tp${id}')"><span class="cdi">🌱</span><span class="cdt">Things to Plant & Payoff</span><span class="cdb gn">Foreshadowing</span><span class="ctg op" id="t-tp${id}">▼</span></div>
    <div class="cdy" id="b-tp${id}">
      <div class="fg"><label class="fl">Things to Plant</label>
        <div class="ckl">${ep.toPlant.map((p,i)=>`<div class="cki"><span class="cks" style="color:var(--gn)">🌱</span><input type="text" value="${esc(p)}" placeholder="สร้อยข้อมือ..." oninput="ua(${id},'toPlant',${i},this.value)"></div>`).join('')}</div>
        <button class="bac" onclick="aa(${id},'toPlant')">+ เพิ่ม</button>
      </div>
      <div class="fg"><label class="fl">Payoff Later</label>
        ${ep.payoffs.map((p,i)=>`<div class="poi"><input type="text" value="${esc(p.ep)}" placeholder="EP2" style="padding:4px 6px;font-size:11px;font-weight:700;text-align:center;color:var(--ac2);background:rgba(129,140,248,.1)" oninput="uPO(${id},${i},'ep',this.value)"><input type="text" value="${esc(p.text)}" placeholder="สิ่งที่จะ Payoff..." oninput="uPO(${id},${i},'text',this.value)"></div>`).join('')}
        <button class="bac" onclick="aPO(${id})">+ เพิ่ม EP</button>
      </div>
    </div>
  </div>

  <div class="cd">
    <div class="cdh" onclick="tog('mm${id}')"><span class="cdi">⚡</span><span class="cdt">Must / Must NOT</span><span class="cdb r">ข้อบังคับ</span><span class="ctg op" id="t-mm${id}">▼</span></div>
    <div class="cdy" id="b-mm${id}">
      <div class="g2">
        <div class="fg"><label class="fl" style="color:var(--gn)">✅ Must Happen</label>
          <div class="ckl">${ep.mustHappen.map((m,i)=>`<div class="cki"><span class="cks" style="color:var(--gn)">✓</span><input type="text" value="${esc(m)}" placeholder="ต้องเกิด..." oninput="ua(${id},'mustHappen',${i},this.value)"></div>`).join('')}</div>
          <button class="bac" onclick="aa(${id},'mustHappen')">+ เพิ่ม</button>
        </div>
        <div class="fg"><label class="fl" style="color:var(--rd)">❌ Must NOT</label>
          <div class="ckl">${ep.mustNotHappen.map((m,i)=>`<div class="cki"><span class="cks" style="color:var(--rd)">✗</span><input type="text" value="${esc(m)}" placeholder="ห้ามเกิด..." oninput="ua(${id},'mustNotHappen',${i},this.value)"></div>`).join('')}</div>
          <button class="bac" onclick="aa(${id},'mustNotHappen')">+ เพิ่ม</button>
        </div>
      </div>
    </div>
  </div>

  <div class="cd">
    <div class="cdh" onclick="tog('en${id}')"><span class="cdi">🔚</span><span class="cdt">Cliffhanger & Ending</span><span class="ctg op" id="t-en${id}">▼</span></div>
    <div class="cdy" id="b-en${id}">
      <div class="fg"><label class="fl">Cliffhanger</label><textarea placeholder="พายเห็นสร้อยข้อมือเส้นเดิม..." oninput="upd(${id},'cliffhanger',this.value)">${esc(ep.cliffhanger)}</textarea></div>
      <div class="fg"><label class="fl">Ending Point <span class="rq">*</span></label><textarea placeholder="ฉากต้องจบตรงไหน ประโยคสุดท้ายคืออะไร..." oninput="upd(${id},'endingPoint',this.value)">${esc(ep.endingPoint)}</textarea></div>
      <div class="fg"><label class="fl">Reader Emotion After Finish</label>
        <div class="ckl">${ep.readerEmotion.map((r,i)=>`<div class="cki"><span class="cks" style="color:var(--ac)">💭</span><input type="text" value="${esc(r)}" placeholder="อยากรู้เรื่องสร้อย..." oninput="ua(${id},'readerEmotion',${i},this.value)"></div>`).join('')}</div>
        <button class="bac" onclick="aa(${id},'readerEmotion')">+ เพิ่ม</button>
      </div>
    </div>
  </div>

  <div class="gw">
    <button class="bgen" id="gb-${id}" onclick="generate(${id})">✨ Generate EP${ep.num} — ${esc(ep.title)} [120–150 bubble]</button>
    <button class="bclr" onclick="clearOut(${id})">🗑️</button>
  </div>`;
}

function bSc(epId,sc,i){
  return `<div class="scc"><div class="sch"><span class="scn">Scene ${i+1}</span><input class="scti" value="${esc(sc.title||`Scene ${i+1}`)}" oninput="uSc(${epId},'${sc.id}','title',this.value)"><button class="bdsc" onclick="dSc(${epId},'${sc.id}')">✕</button></div>
    <div class="scb">
      <div class="g3">
        <div><div class="scl2">📍 สถานที่</div><input class="sci" type="text" value="${esc(sc.location)}" placeholder="ห้อง1204..." oninput="uSc(${epId},'${sc.id}','location',this.value)"></div>
        <div><div class="scl2">🕒 เวลา</div><input class="sci" type="text" value="${esc(sc.time)}" placeholder="19:00..." oninput="uSc(${epId},'${sc.id}','time',this.value)"></div>
        <div><div class="scl2">📱 ประเภท</div><select class="sci" onchange="uSc(${epId},'${sc.id}','chatType',this.value)">${CT.map(ct=>`<option value="${ct.k}" ${sc.chatType===ct.k?'selected':''}>${ct.i} ${ct.l}</option>`).join('')}</select></div>
      </div>
      <div><div class="scl2">👤 ผู้เข้าร่วม</div>${bTg(epId,'p_'+sc.id,sc.participants,'ชื่อ + Enter...')}</div>
      <div><div class="scl2" style="margin-bottom:4px">💫 Mood</div><div class="chips">${MO.map(m=>`<div class="chip ${sc.moods.includes(m)?'sl':''}" style="font-size:11px;padding:2px 8px" onclick="tSm(${epId},'${sc.id}','${m}',this)">${m}</div>`).join('')}</div></div>
      <div><div class="scl2">🎯 Scene Goal</div><input class="sci" type="text" value="${esc(sc.goal)}" placeholder="เปิดตัวธันว์..." oninput="uSc(${epId},'${sc.id}','goal',this.value)"></div>
    </div>
  </div>`;
}

function bTg(epId,field,vals,ph){
  const tid=`ti-${epId}-${field}`,cid=`tc-${epId}-${field}`;
  return `<div class="tw" id="${cid}" onclick="G('${tid}')?.focus()">
    ${(vals||[]).filter(Boolean).map(v=>`<div class="tg">${v}<span class="tx2" onclick="rmT(${epId},'${field}','${v}')">×</span></div>`).join('')}
    <input class="ti" id="${tid}" placeholder="${ph}" onkeydown="addT(event,${epId},'${field}','${tid}')">
  </div>`;
}

function upd(id,f,v){const ep=gEp(id);if(ep){ep[f]=v;if(f==='title'||f==='arc')renderSB();sv();}}
function ua(id,f,i,v){const ep=gEp(id);if(ep){ep[f][i]=v;sv();}}
function aa(id,f){const ep=gEp(id);if(ep){ep[f].push('');sv();renderEd(id);}}
function ta(id,f,v,el){const ep=gEp(id);if(!ep)return;const i=ep[f].indexOf(v);if(i===-1){ep[f].push(v);el.classList.add('sl');}else{ep[f].splice(i,1);el.classList.remove('sl');}sv();}
function uCL(id,i,f,v){const ep=gEp(id);if(ep){ep.charLocks[i][f]=v;sv();}}
function uCLR(id,ci,ri,v){const ep=gEp(id);if(ep){ep.charLocks[ci].rules[ri]=v;sv();}}
function aCLR(id,ci){const ep=gEp(id);if(ep){ep.charLocks[ci].rules.push('');sv();renderEd(id);}}
function aPO(id){const ep=gEp(id);if(ep){ep.payoffs.push({ep:'EP?',text:''});sv();renderEd(id);}}
function uPO(id,i,f,v){const ep=gEp(id);if(ep){ep.payoffs[i][f]=v;sv();}}
function uSc(epId,scId,f,v){const ep=gEp(epId);if(!ep)return;const sc=ep.scenes.find(s=>String(s.id)===String(scId));if(sc){sc[f]=v;sv();}}
function tSm(epId,scId,m,el){const ep=gEp(epId);if(!ep)return;const sc=ep.scenes.find(s=>String(s.id)===String(scId));if(!sc)return;const i=sc.moods.indexOf(m);if(i===-1){sc.moods.push(m);el.classList.add('sl');}else{sc.moods.splice(i,1);el.classList.remove('sl');}sv();}
function addSc(id){const ep=gEp(id);if(!ep)return;ep.scenes.push(nwSc(ep.scenes.length+1));sv();renderEd(id);}
function dSc(epId,scId){const ep=gEp(epId);if(!ep)return;ep.scenes=ep.scenes.filter(s=>String(s.id)!==String(scId));ep.scenes.forEach((s,i)=>s.num=i+1);sv();renderEd(epId);}
function addT(e,id,field,tid){
  if(e.key!=='Enter')return;const inp=G(tid);const val=inp?.value?.trim();if(!val)return;
  if(field.startsWith('p_')){const scId=field.replace('p_','');const ep=gEp(id);if(ep){const sc=ep.scenes.find(s=>String(s.id)===String(scId));if(sc&&!sc.participants.includes(val))sc.participants.push(val);}}
  else{const ep=gEp(id);if(ep){if(!ep[field])ep[field]=[];if(!ep[field].includes(val))ep[field].push(val);}}
  if(inp)inp.value='';sv();renderEd(id);
}
function rmT(id,field,value){
  if(field.startsWith('p_')){const scId=field.replace('p_','');const ep=gEp(id);if(ep){const sc=ep.scenes.find(s=>String(s.id)===String(scId));if(sc)sc.participants=sc.participants.filter(v=>v!==value);}}
  else{const ep=gEp(id);if(ep&&ep[field])ep[field]=ep[field].filter(v=>v!==value);}
  sv();renderEd(id);
}
function tog(id){const b=G('b-'+id),t=G('t-'+id);if(!b||!t)return;const c=b.classList.toggle('hid');t.textContent=c?'▶':'▼';t.classList.toggle('op',!c);}

// ─── PASTE BRIEF ───────────────────────────────────────────
let parsedBriefData = null;

function openPasteBrief(){
  const ep=cEp();if(!ep)return;
  G('pbOv').classList.add('open');
  G('pbText').focus();
  G('pbPreview').classList.remove('show');
  G('pbOkBtn').classList.remove('show');
  G('pbParseBtn').disabled=true;
  parsedBriefData=null;
}
function closePasteBrief(){G('pbOv').classList.remove('open');}
function pbChanged(){
  const v=G('pbText').value.trim();
  G('pbParseBtn').disabled=!v;
  G('pbPreview').classList.remove('show');
  G('pbOkBtn').classList.remove('show');
  parsedBriefData=null;
}

async function parseBrief(){
  const txt=G('pbText').value.trim();if(!txt)return;
  const btn=G('pbParseBtn');
  btn.disabled=true;btn.innerHTML='<div class="sp" style="width:14px;height:14px;border-width:2px;display:inline-block;vertical-align:middle;margin-right:6px"></div>AI กำลังแปลง...';
  G('pbPreview').innerHTML='';G('pbPreview').classList.remove('show');

  const schema = '{\n  "title":"ชื่อตอน","plotGoal":["เป้าหมาย1"],"emotionalGoal":["อึดอัด"],"plotFunction":"Setup Arc","theme":"","hook":"","mainChars":["ชื่อ1"],"supportChars":["ชื่อ3"],"mainCharName":"ชื่อตัวเอก","relationshipMood":["ยังค้างคา"],"scenes":[{"title":"scene","location":"สถานที่","time":"เวลา","chatType":"DM","participants":["ชื่อ1"],"moods":["ฟิน"],"goal":"goal","tension":5}],"charLocks":[{"name":"ชื่อ","rules":["กฎ1"]}],"toPlant":[""],"mustHappen":[""],"mustNotHappen":[""],"cliffhanger":"","endingPoint":""\n}';
  const rules = 'กฎ:\n- emotionalGoal เลือกจาก: ช็อก,อึดอัด,คิดถึง,ใจสั่น,ฟิน,หน่วง,หึง,โกรธ,เจ็บปวด,ตื่นเต้น,ซึ้ง,ตลก,เศร้า\n- relationshipMood เลือกจาก: แฟนเก่า,ยังค้างคา,ไม่พร้อมเจอ,ยังไม่มูฟออน,แอบชอบ,งอน,หึง,คืนดี,ห่างกัน,ตึงเครียด,ยังไม่สนิท,เขินกัน,รักกัน,ทะเลาะ\n- chatType เลือกจาก: DM,GROUP,CALL,VIDEOCALL,IG,FB,X,TIKTOK,IRL,SILENT\n- charLocks max 3 ตัวละคร\n- ข้อมูลไม่มีให้ใส่ array ว่างหรือ string ว่าง\n- ตอบเป็น JSON เท่านั้น ไม่มี markdown ไม่มีคำอธิบาย';
  const prompt = 'แปลง EP Brief ต่อไปนี้ให้เป็น JSON ตามโครงสร้างนี้:\n' + schema + '\n\n' + rules + '\n\nEP Brief:\n' + txt;

  // ตรวจ API key ก่อน

  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({model:'claude-sonnet-4-6',max_tokens:4000,messages:[{role:'user',content:prompt}]})});
    const data=await res.json();
    if(data.error){throw new Error('API Error: '+JSON.stringify(data.error));} const raw=data.content?.[0]?.text;
    if(!raw){throw new Error('ไม่ได้รับข้อมูล — ลองใหม่อีกครั้ง');}
    const clean=raw.replace(/```json\n?|```\n?/g,'').trim();
    const jsonStart=clean.indexOf('{');const jsonEnd=clean.lastIndexOf('}');
    if(jsonStart===-1||jsonEnd===-1) throw new Error('AI ไม่ได้ return JSON — ลองใหม่อีกครั้ง');
    const jsonStr=clean.slice(jsonStart,jsonEnd+1);
    const parsed=JSON.parse(jsonStr);
    if(Object.keys(parsed).length===0) throw new Error('JSON ว่างเปล่า — ลองใหม่อีกครั้ง');
    parsedBriefData=parsed;
    showBriefPreview(parsed);
  }catch(err){
    G('pbPreview').innerHTML=`<span style="color:var(--rd)">❌ แปลงไม่สำเร็จ: ${err.message}</span>`;
    G('pbPreview').classList.add('show');
  }
  btn.disabled=false;btn.innerHTML='✨ แปลง Brief → กรอก Field อัตโนมัติ';
}

function showBriefPreview(d){
  const tag=v=>`<span class="pb-tag">${v}</span>`;
  let html=`<div style="margin-bottom:8px;font-size:12px;font-weight:700;color:var(--gn)">✅ แปลงสำเร็จ — ตรวจสอบข้อมูลก่อนใช้</div>`;
  if(d.title)html+=`<div><b>📕 ชื่อตอน:</b> ${d.title}</div>`;
  if(d.plotGoal?.filter(Boolean).length)html+=`<div><b>🎯 Plot Goal:</b> ${d.plotGoal.filter(Boolean).map(tag).join('')}</div>`;
  if(d.emotionalGoal?.length)html+=`<div><b>💭 Emotional:</b> ${d.emotionalGoal.map(tag).join('')}</div>`;
  if(d.mainChars?.length)html+=`<div><b>👤 Main:</b> ${d.mainChars.map(tag).join('')}</div>`;
  if(d.supportChars?.length)html+=`<div><b>👥 Support:</b> ${d.supportChars.map(tag).join('')}</div>`;
  if(d.relationshipMood?.length)html+=`<div><b>💞 Mood:</b> ${d.relationshipMood.map(tag).join('')}</div>`;
  if(d.scenes?.length)html+=`<div><b>🎬 Scenes:</b> ${d.scenes.length} ฉาก — ${d.scenes.map(s=>tag(s.title||'?')).join('')}</div>`;
  if(d.charLocks?.filter(c=>c.name).length)html+=`<div><b>🔒 Char Lock:</b> ${d.charLocks.filter(c=>c.name).map(c=>tag(c.name)).join('')}</div>`;
  if(d.mustHappen?.filter(Boolean).length)html+=`<div><b>✅ Must:</b> ${d.mustHappen.filter(Boolean).map(tag).join('')}</div>`;
  if(d.mustNotHappen?.filter(Boolean).length)html+=`<div><b>❌ Must NOT:</b> ${d.mustNotHappen.filter(Boolean).map(tag).join('')}</div>`;
  if(d.cliffhanger)html+=`<div><b>😱 Cliffhanger:</b> ${d.cliffhanger.substring(0,60)}${d.cliffhanger.length>60?'...':''}</div>`;
  G('pbPreview').innerHTML=html;
  G('pbPreview').classList.add('show');
  G('pbOkBtn').classList.add('show');
  G('pbParseBtn').innerHTML='🔄 แปลงใหม่';
}

function applyBrief(){
  const ep=cEp();if(!ep||!parsedBriefData)return;
  const d=parsedBriefData;
  if(d.title)ep.title=d.title;
  if(d.plotGoal?.length)ep.plotGoal=d.plotGoal.filter(Boolean).length?d.plotGoal:[''];
  if(d.emotionalGoal?.length)ep.emotionalGoal=d.emotionalGoal;
  if(d.plotFunction)ep.plotFunction=d.plotFunction;
  if(d.theme)ep.theme=d.theme;
  if(d.hook)ep.hook=d.hook;
  if(d.mainChars?.length)ep.mainChars=d.mainChars;
  if(d.supportChars?.length)ep.supportChars=d.supportChars;
  if(d.mainCharName)ep.mainCharName=d.mainCharName;
  if(d.relationshipMood?.length)ep.relationshipMood=d.relationshipMood;
  if(d.scenes?.length){
    ep.scenes=d.scenes.map((sc,i)=>({
      id:Date.now()+Math.random()+i,num:i+1,
      title:sc.title||`Scene ${i+1}`,
      location:sc.location||'',time:sc.time||'',
      chatType:sc.chatType||'DM',
      participants:sc.participants||[],
      moods:sc.moods||[],
      goal:sc.goal||'',
      tension:sc.tension||5
    }));
  }
  if(d.charLocks?.length){
    const colors=['var(--ac)','var(--pk)','var(--gd)'];
    ep.charLocks=d.charLocks.slice(0,3).map((cl,i)=>({name:cl.name||'',color:colors[i],rules:cl.rules?.length?cl.rules:['']}));
    while(ep.charLocks.length<3)ep.charLocks.push({name:'',color:colors[ep.charLocks.length],rules:['']});
  }
  if(d.toPlant?.filter(Boolean).length)ep.toPlant=d.toPlant;
  if(d.mustHappen?.filter(Boolean).length)ep.mustHappen=d.mustHappen;
  if(d.mustNotHappen?.filter(Boolean).length)ep.mustNotHappen=d.mustNotHappen;
  if(d.cliffhanger)ep.cliffhanger=d.cliffhanger;
  if(d.endingPoint)ep.endingPoint=d.endingPoint;
  sv();renderSB();renderEd(ep.id);
  closePasteBrief();
  G('pbText').value='';parsedBriefData=null;
}
// ───────────────────────────────────────────────────────────

async function generate(id){
  const ep=gEp(id);if(!ep)return;const nv=cNv();if(!nv)return;
  const btn=G(`gb-${id}`);
  btn.disabled=true;btn.innerHTML='<div class="sp" style="width:16px;height:16px;border-width:2px"></div> กำลังเขียน...';
  G('outBd').innerHTML=`<div class="ld"><div class="sp"></div><div style="color:var(--t2);font-size:13px">AI กำลังเขียน EP${ep.num}...</div><div style="color:var(--t3);font-size:11px">เป้าหมาย 120-150 bubble · รอสักครู่</div></div>`;
  G('stb').style.display='none';
  const scDesc=ep.scenes.map((sc,i)=>`Scene ${i+1} — ${sc.title}\n📍 ${sc.location||'?'} · 🕒 ${sc.time||'?'} · 📱 ${CT.find(c=>c.k===sc.chatType)?.l||sc.chatType}\n👤 ${sc.participants.join(', ')||'ตามตัวละครหลัก'}\n💫 Mood: ${sc.moods.join(', ')||'ไม่ระบุ'}\n🎯 Goal: ${sc.goal||'ไม่ระบุ'}\n⚡ Tension: ${sc.tension||5}/10`).join('\n\n');
  const clDesc=ep.charLocks.filter(cl=>cl.name).map(cl=>`${cl.name}: ${cl.rules.filter(Boolean).join(' · ')}`).join('\n');
  const prompt=`คุณคือนักเขียนนิยายแชทรางวัล ที่เขียนนิยายแชทไทยขายดีติดชาร์ท มีสไตล์เป็นของตัวเอง งานของคุณอ่านแล้วลื่น ธรรมชาติ ไม่มีกลิ่น AI

📚 ${nv.title} | ${nv.genre||'โรแมนติก ดราม่า'}
${nv.synopsis ? 'Synopsis: '+nv.synopsis : ''}

📕 EP${ep.num}: ${ep.title} | ${ep.arc}
${ep.plotFunction ? 'Function: '+ep.plotFunction : ''}
${ep.theme ? 'Theme: '+ep.theme : ''}
${ep.hook ? 'Hook: '+ep.hook : ''}
${ep.timeline ? 'Timeline: '+ep.timeline : ''}

🎯 Plot Goal:
${ep.plotGoal.filter(Boolean).map(g=>'• '+g).join('\n')||'ไม่ระบุ'}

💜 Emotional Goal: ${ep.emotionalGoal.join(', ')||'ไม่ระบุ'}
👥 Main: ${ep.mainChars.filter(Boolean).join(', ')||'ไม่ระบุ'} | Support: ${ep.supportChars.filter(Boolean).join(', ')||'ไม่ระบุ'}
💫 Relationship: ${ep.relationshipMood.join(', ')||'ไม่ระบุ'}

🎬 SCENE BREAKDOWN:
${scDesc}

🔒 CHARACTER LOCK — รักษาบุคลิกทุกตัวอย่างเคร่งครัด:
${clDesc||'ไม่ระบุ'}

🌱 THINGS TO PLANT (ปลูกให้เนียน ห้ามโจ่งแจ้ง):
${ep.toPlant.filter(Boolean).map(p=>'• '+p).join('\n')||'ไม่ระบุ'}

✅ ต้องมีในตอนนี้:
${ep.mustHappen.filter(Boolean).map(m=>'✓ '+m).join('\n')||'ไม่ระบุ'}

❌ ห้ามมีเด็ดขาด:
${ep.mustNotHappen.filter(Boolean).map(m=>'✗ '+m).join('\n')||'ไม่ระบุ'}

🔚 Cliffhanger: ${ep.cliffhanger||'ไม่ระบุ'}
🔚 จบที่: ${ep.endingPoint||'จบด้วย hook ให้อยากอ่านต่อ'}

══════════════════════════════════════
⚠️ กฎที่ต้องทำตามทุกข้อ ห้ามฝ่าฝืน
══════════════════════════════════════

【จำนวน bubble — สำคัญที่สุด】
• เขียน 130 bubble ขึ้นไป (ขั้นต่ำ 130 บรรทัด/block)
• bubble คือ: บรรทัดแชท 1 บรรทัด หรือ narration 1 block
• ถ้านับแล้วยังไม่ถึง 130 → เขียนต่อ อย่าหยุด
• ทุก scene ต้องมี bubble อย่างน้อย 20+ bubble

【รูปแบบ output】
• บรรยายฉาก: เขียนเลย ไม่ต้องมี tag (2-4 บรรทัด/block)
• แชท LINE: [LINE — เวลา] แล้วตามด้วย ชื่อ: ข้อความ
• กลุ่ม: [LINE GROUP — ชื่อกลุ่ม]
• โทร: [CALL] / Video: [VIDEO CALL]
• IG: [INSTAGRAM] @ชื่อ 📸 "caption" ❤️ likes แล้ว comment
• เจอหน้า: [สถานที่ · เวลา] ชื่อ: //action หรือ ชื่อ: พูด

【ภาษา — ข้อห้ามเด็ดขาด】
ห้ามใช้คำพวกนี้เลย:
✗ "รู้สึกว่า..." / "ในใจของเธอ..." / "นับเป็น..." / "อย่างไรก็ตาม"
✗ "ด้วยเหตุนี้" / "ขอบคุณที่เข้าใจ" / "เป็นอย่างมาก" / "อย่างล้ำลึก"
✗ บรรยายอารมณ์ตรงๆ เช่น "เธอรู้สึกตื่นเต้น" "เขารู้สึกเจ็บปวด"

ภาษาที่ถูก:
✓ ตัวละครพูดสั้น ตรง ตามบุคลิก
✓ อารมณ์แสดงผ่านคำพูดและ action เท่านั้น
✓ แต่ละตัวมีสำนวนเป็นของตัวเอง
✓ คำแสลงตามอายุ/บุคลิก: "โห" "อ่า" "นะ" "ว่ะ" "เฮ้ย" "555" "kkk" "อิๆ" "ปะ"
✓ ตัวอย่างดี: "ไปด้วยกันมั้ย" / "ไม่ว่างว่ะ" / "เฮ้ย จริงเหรอ??"

【อื่นๆ】
• ห้ามใส่หมายเหตุ อธิบาย หรือ meta-text ใดๆ ทั้งสิ้น
• เขียนนิยายล้วน ตั้งแต่ต้นจนจบ ไม่ต้องมี intro ไม่ต้อง outro

เริ่มเขียน EP${ep.num} เลย (จำไว้: ต้องได้ 130+ bubble):`;

  try{
    const res=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},body:JSON.stringify({model:'claude-sonnet-4-6',max_tokens:8000,messages:[{role:'user',content:prompt}]})});
    const data=await res.json();
    if(data.error){throw new Error('API Error: '+JSON.stringify(data.error));} const text=data.content?.[0]?.text;
    if(!text){throw new Error('ไม่ได้รับข้อมูล — ลองใหม่อีกครั้ง');}
    rawOut=text;ep.generatedOutput=text;ep.status='done';
    sv();renderSB();renderOut(text,ep);
  }catch(err){G('outBd').innerHTML=`<div class="em"><div class="ei">❌</div><div class="et" style="color:var(--rd)">${err.message}</div></div>`;}
  btn.disabled=false;btn.innerHTML=`✨ Generate EP${ep.num} — ${esc(ep.title)} [120–150 bubble]`;
}

function renderOut(text,ep){
  const lines=text.split('\n');
  let blocks=[],cur=null,cT=null;
  for(const line of lines){
    const t=line.trim();
    if(!t){if(cur){blocks.push({type:cT,content:cur});cur=null;cT=null;}continue;}
    if(/^\[/.test(t)&&!cT){cT='CHAT';cur=t;}
    else if(cT==='CHAT'){cur+='\n'+t;}
    else{if(cT!=='NAR'){if(cur)blocks.push({type:cT||'NAR',content:cur});cur=t;cT='NAR';}else{cur+='\n'+t;}}
  }
  if(cur)blocks.push({type:cT||'NAR',content:cur});
  const mc=ep.mainCharName||(ep.mainChars?.[0])||'';
  let bCnt=0;
  let html=`<div class="oel"><div class="oed"></div>EP${ep.num} · ${ep.title}</div><div class="np">`;
  for(const b of blocks){
    if(!b.content?.trim())continue;
    if(b.type==='NAR'){bCnt++;html+=`<div class="nar">${b.content.replace(/\n/g,'<br>')}</div>`;}
    else{
      const cl=b.content.split('\n').filter(l=>l.trim());
      let hdr='',msgs=[];
      for(const c of cl){if(/^\[/.test(c.trim()))hdr=c.trim().replace(/^\[|\]$/g,'');else msgs.push(c);}
      let ch=`<div class="cbl">`;
      if(hdr)ch+=`<div class="chb">💬 ${hdr}</div>`;
      ch+=`<div class="cms">`;
      let lS=null;
      for(const ml of msgs){
        const ci=ml.indexOf(':');if(ci===-1){ch+=`<div class="al">${ml}</div>`;bCnt++;continue;}
        const spk=ml.substring(0,ci).trim();const msg=ml.substring(ci+1).trim();if(!msg)continue;
        if(/^(อ่านแล้ว|\[อ่านแล้ว)/.test(ml)){ch+=`<div class="brd">${ml}</div>`;bCnt++;continue;}
        if(spk.startsWith('[')&&spk.endsWith(']')){ch+=`<div class="al">${ml}</div>`;bCnt++;continue;}
        const isA=msg.startsWith('//');const mine=mc&&spk===mc;const init=spk.charAt(0);const sn=spk!==lS;lS=spk;bCnt++;
        ch+=`<div class="br ${mine?'r':''}">
          ${!mine?`<div class="bav o">${init}</div>`:''}
          <div class="bw">${sn&&!mine?`<div class="bname2">${spk}</div>`:''}${isA?`<div class="al">${msg.replace('//','')}</div>`:`<div class="bub ${mine?'m':''}">${msg}</div>`}</div>
          ${mine?`<div class="bav">${init}</div>`:''}
        </div>`;
      }
      ch+=`</div></div>`;html+=ch;
    }
  }
  html+='</div>';
  G('outBd').innerHTML=html;
  const words=text.replace(/[^\u0E00-\u0E7Fa-zA-Z0-9\s]/g,'').split(/\s+/).length;
  G('sBub').textContent=bCnt;G('sWd').textContent=words;G('sRd').textContent=Math.ceil(words/200);
  G('stb').style.display='flex';
  const bv=G('sBub');bv.style.color=bCnt>=120?'var(--gn)':bCnt>=80?'var(--gd)':'var(--rd)';
}

function clearOut(id){const ep=gEp(id);if(ep){ep.generatedOutput=null;ep.status='pending';sv();renderSB();}G('outBd').innerHTML='<div class="em"><div class="ei">✍️</div><div class="et">กด Generate</div></div>';G('stb').style.display='none';rawOut='';}
function copyOut(){if(!rawOut)return;navigator.clipboard.writeText(rawOut);const b=document.querySelector('.bcp');b.textContent='✅ Copied!';setTimeout(()=>b.innerHTML='📋 Copy',2000);}
function dlOut(){if(!rawOut)return;const ep=cEp();const nv=cNv();const nm=`${nv?.title||'novel'}_EP${ep?.num||'?'}_${ep?.title||''}.txt`;const blob=new Blob([rawOut],{type:'text/plain;charset=utf-8'});const a=document.createElement('a');a.href=URL.createObjectURL(blob);a.download=nm;a.click();}

window.addEventListener('DOMContentLoaded',()=>{
  akRender();
  G('erow').innerHTML=EM.map(e=>`<span class="eo" onclick="pickE('${e}',this)">${e}</span>`).join('');
  renderShelf();
  if(db.cNid){
    const nv=db.novels.find(n=>n.id===db.cNid);
    if(nv){
      G('hEm').textContent=nv.emoji||'📖';G('hNm').textContent=nv.title;
      G('hMt').textContent=`${nv.eps?.length||0} ตอน · ${nv.genre||''}`;
      G('btnAep').disabled=false;G('ovl').style.display='none';
      renderSB();
      if(db.cEid){const ep=nv.eps?.find(e=>e.id===db.cEid);if(ep){G('wsc').style.display='none';G('epEd').style.display='block';G('btnPaste').disabled=false;renderEd(db.cEid);if(ep.generatedOutput)renderOut(ep.generatedOutput,ep);}}
    }
  }
});
</script>
</body>
</html>
