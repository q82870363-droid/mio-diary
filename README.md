[index (2).html](https://github.com/user-attachments/files/26321413/index.2.html)
<!DOCTYPE html>
<html lang="zh">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>澪音の成長日記</title>
<link href="https://fonts.googleapis.com/css2?family=Noto+Serif+JP:wght@300;400;500&family=Noto+Sans+SC:wght@300;400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --cream: #faf8f4;
    --warm-white: #ffffff;
    --ink: #1a1a1a;
    --ink-light: #555;
    --ink-faint: #999;
    --border: #e8e4de;
    --border-light: #f0ede8;
    --accent: #c8856a;
    --accent-light: #f5ede9;
    --green: #6a9e85;
    --green-light: #eaf3ee;
    --blue: #5a7fa8;
    --blue-light: #eaf0f7;
    --amber: #b8874a;
    --amber-light: #faf0e3;
    --pink: #b06080;
    --pink-light: #f7ecf1;
    --radius: 14px;
    --radius-sm: 8px;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    background: var(--cream);
    color: var(--ink);
    font-family: 'Noto Sans SC', 'Noto Serif JP', sans-serif;
    min-height: 100vh;
    font-size: 15px;
    line-height: 1.7;
  }

  /* ── HEADER ── */
  .site-header {
    background: var(--warm-white);
    border-bottom: 1px solid var(--border);
    padding: 20px 24px 16px;
    text-align: center;
    position: sticky;
    top: 0;
    z-index: 50;
  }
  .site-header h1 {
    font-family: 'Noto Serif JP', serif;
    font-size: 20px;
    font-weight: 400;
    letter-spacing: 0.08em;
    color: var(--ink);
  }
  .site-header p {
    font-size: 12px;
    color: var(--ink-faint);
    margin-top: 3px;
    letter-spacing: 0.05em;
  }

  /* ── LAYOUT ── */
  .container { max-width: 680px; margin: 0 auto; padding: 24px 16px 80px; }

  /* ── STATS ── */
  .stats {
    display: grid;
    grid-template-columns: repeat(3, minmax(0,1fr));
    gap: 10px;
    margin-bottom: 24px;
  }
  .stat {
    background: var(--warm-white);
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    padding: 14px 10px;
    text-align: center;
  }
  .stat-num { font-size: 22px; font-weight: 500; color: var(--accent); }
  .stat-label { font-size: 11px; color: var(--ink-faint); margin-top: 3px; line-height: 1.4; }

  /* ── TOOLBAR ── */
  .toolbar { display: flex; gap: 8px; margin-bottom: 18px; align-items: center; flex-wrap: wrap; }
  .filter-bar { display: flex; gap: 6px; flex-wrap: wrap; flex: 1; }
  .filter-btn {
    font-size: 12px;
    padding: 5px 12px;
    border-radius: 99px;
    border: 1px solid var(--border);
    background: var(--warm-white);
    cursor: pointer;
    color: var(--ink-light);
    white-space: nowrap;
    transition: all 0.15s;
  }
  .filter-btn:hover { border-color: var(--accent); color: var(--accent); }
  .filter-btn.active { background: var(--accent); color: #fff; border-color: var(--accent); }
  .export-btn {
    font-size: 12px;
    padding: 6px 14px;
    border-radius: var(--radius-sm);
    border: 1px solid var(--border);
    background: var(--warm-white);
    cursor: pointer;
    color: var(--ink-light);
    white-space: nowrap;
    transition: all 0.15s;
  }
  .export-btn:hover { background: var(--cream); }

  /* ── ADD BUTTON ── */
  .add-btn {
    width: 100%;
    padding: 14px;
    border: 1.5px dashed var(--border);
    border-radius: var(--radius);
    background: transparent;
    color: var(--ink-faint);
    font-size: 14px;
    cursor: pointer;
    margin-bottom: 20px;
    transition: all 0.15s;
    font-family: inherit;
  }
  .add-btn:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-light); }

  /* ── ENTRY CARD ── */
  .entry {
    background: var(--warm-white);
    border: 1px solid var(--border);
    border-radius: var(--radius);
    padding: 20px;
    margin-bottom: 14px;
    transition: box-shadow 0.15s;
  }
  .entry:hover { box-shadow: 0 2px 12px rgba(0,0,0,0.05); }
  .entry-meta { display: flex; align-items: center; justify-content: space-between; margin-bottom: 10px; }
  .entry-date { font-size: 12px; color: var(--ink-faint); letter-spacing: 0.04em; }
  .entry-tag { font-size: 11px; padding: 3px 10px; border-radius: 99px; letter-spacing: 0.03em; }
  .tag-growth { background: var(--green-light); color: var(--green); }
  .tag-life   { background: var(--blue-light);  color: var(--blue); }
  .tag-feeling{ background: var(--pink-light);  color: var(--pink); }
  .tag-health { background: var(--amber-light); color: var(--amber); }
  .entry-title { font-size: 15px; font-weight: 500; color: var(--ink); margin-bottom: 12px; line-height: 1.5; }
  .lang-tabs {
    display: flex;
    border: 1px solid var(--border);
    border-radius: 6px;
    overflow: hidden;
    width: fit-content;
    margin-bottom: 12px;
  }
  .lang-tab {
    font-size: 12px;
    padding: 3px 12px;
    cursor: pointer;
    background: transparent;
    border: none;
    color: var(--ink-faint);
    font-family: inherit;
    transition: all 0.1s;
  }
  .lang-tab.active { background: var(--cream); color: var(--ink); font-weight: 500; }
  .entry-body    { font-size: 14px; color: var(--ink-light); line-height: 1.85; white-space: pre-wrap; }
  .entry-body-ja { font-size: 13px; color: var(--ink-light); line-height: 1.95; white-space: pre-wrap; font-family: 'Noto Serif JP', serif; }
  .translating   { font-style: italic; color: var(--ink-faint); font-size: 13px; }

  /* ── LOADING / EMPTY ── */
  .loading-msg { text-align: center; color: var(--ink-faint); padding: 40px 0; font-size: 14px; }

  /* ── MODAL ── */
  .modal-overlay {
    position: fixed; inset: 0;
    background: rgba(20,15,10,0.4);
    z-index: 200;
    display: flex;
    align-items: flex-start;
    justify-content: center;
    padding: 24px 16px 40px;
    overflow-y: auto;
  }
  .modal {
    background: var(--warm-white);
    border-radius: var(--radius);
    border: 1px solid var(--border);
    padding: 24px;
    width: 100%;
    max-width: 520px;
    margin: auto;
  }
  .modal h2 { font-size: 17px; font-weight: 500; margin-bottom: 18px; color: var(--ink); }
  .form-group { margin-bottom: 14px; }
  .form-group label { display: block; font-size: 12px; color: var(--ink-faint); margin-bottom: 5px; letter-spacing: 0.03em; }
  .form-group input,
  .form-group select,
  .form-group textarea {
    width: 100%;
    border: 1px solid var(--border);
    border-radius: var(--radius-sm);
    padding: 9px 12px;
    font-size: 14px;
    font-family: inherit;
    color: var(--ink);
    background: var(--warm-white);
    outline: none;
    transition: border-color 0.15s;
  }
  .form-group input:focus,
  .form-group select:focus,
  .form-group textarea:focus { border-color: var(--accent); }
  .form-group textarea { min-height: 100px; resize: vertical; line-height: 1.7; }
  .ja-label { font-size: 11px; color: var(--ink-faint); margin-bottom: 5px; }
  .ja-preview {
    background: var(--cream);
    border: 1px solid var(--border-light);
    border-radius: var(--radius-sm);
    padding: 10px 12px;
    font-size: 13px;
    color: var(--ink-light);
    line-height: 1.85;
    min-height: 54px;
    white-space: pre-wrap;
    font-family: 'Noto Serif JP', serif;
  }
  .modal-btns { display: flex; gap: 8px; justify-content: flex-end; margin-top: 18px; flex-wrap: wrap; }
  .btn {
    font-size: 13px;
    padding: 7px 16px;
    border-radius: var(--radius-sm);
    cursor: pointer;
    font-family: inherit;
    border: 1px solid var(--border);
    background: transparent;
    color: var(--ink-light);
    transition: all 0.15s;
  }
  .btn:hover { background: var(--cream); }
  .btn-accent {
    background: var(--accent);
    color: #fff;
    border-color: var(--accent);
  }
  .btn-accent:hover { background: #b8705a; }
  .btn-green {
    background: var(--green);
    color: #fff;
    border-color: var(--green);
  }
  .btn-green:hover { background: #5a8e75; }
  .btn:disabled { opacity: 0.5; cursor: not-allowed; }

  /* ── SYNC STATUS ── */
  .sync-dot {
    display: inline-block;
    width: 7px; height: 7px;
    border-radius: 50%;
    background: var(--green);
    margin-right: 5px;
    vertical-align: middle;
  }
  .sync-dot.offline { background: var(--ink-faint); }
  .sync-status { font-size: 11px; color: var(--ink-faint); text-align: center; margin-bottom: 14px; }
</style>
</head>
<body>

<header class="site-header">
  <h1>澪音の成長日記 · 澪音的成长日记</h1>
  <p>パパとママからの贈り物 · 爸爸妈妈写给你的故事</p>
</header>

<div class="container">

  <div class="stats">
    <div class="stat">
      <div class="stat-num" id="total-count">—</div>
      <div class="stat-label">日记总篇<br>日記の数</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="age-display">—</div>
      <div class="stat-label">澪音月龄<br>月齢</div>
    </div>
    <div class="stat">
      <div class="stat-num" id="days-display">—</div>
      <div class="stat-label">出生天数<br>生後日数</div>
    </div>
  </div>

  <div class="sync-status" id="sync-status">
    <span class="sync-dot" id="sync-dot"></span><span id="sync-text">接続中…</span>
  </div>

  <div class="toolbar">
    <div class="filter-bar">
      <button class="filter-btn active" data-tag="all"     onclick="filterTag('all')">全部 / すべて</button>
      <button class="filter-btn" data-tag="growth"  onclick="filterTag('growth')">成长 / 成長</button>
      <button class="filter-btn" data-tag="life"    onclick="filterTag('life')">生活</button>
      <button class="filter-btn" data-tag="feeling" onclick="filterTag('feeling')">心情 / 気持ち</button>
      <button class="filter-btn" data-tag="health"  onclick="filterTag('health')">生病与治疗 / 病気</button>
    </div>
    <button class="export-btn" onclick="doExport()">导出 ↓</button>
  </div>

  <button class="add-btn" onclick="openModal()">＋ 写一篇新日记 / 新しい日記を書く</button>

  <div id="entries-list">
    <div class="loading-msg">正在加载日记… / 日記を読み込み中…</div>
  </div>
</div>

<!-- MODAL -->
<div class="modal-overlay" id="modal-overlay" style="display:none;">
  <div class="modal">
    <h2>写一篇新日记 / 新しい日記を書く</h2>
    <div class="form-group">
      <label>日期 / 日付</label>
      <input type="date" id="new-date" />
    </div>
    <div class="form-group">
      <label>标题（中文）/ タイトル</label>
      <input type="text" id="new-title" placeholder="给这篇日记起个名字…" />
    </div>
    <div class="form-group">
      <label>分类 / カテゴリ</label>
      <select id="new-tag">
        <option value="growth">成长 / 成長</option>
        <option value="life">生活</option>
        <option value="feeling">心情 / 気持ち</option>
        <option value="health">生病与治疗 / 病気と治療</option>
      </select>
    </div>
    <div class="form-group">
      <label>内容（中文）/ 内容</label>
      <textarea id="new-body" placeholder="用中文记录今天的点点滴滴…"></textarea>
    </div>
    <div class="form-group">
      <div class="ja-label">日文翻译 / 日本語訳</div>
      <div class="ja-preview" id="ja-preview">点击「自动翻译」，AI将自动翻译成日文 / 「自動翻訳」を押すとAIが翻訳します</div>
    </div>
    <div class="modal-btns">
      <button class="btn" onclick="closeModal()">取消 / キャンセル</button>
      <button class="btn btn-green" onclick="doTranslate()" id="translate-btn">自动翻译 / 自動翻訳</button>
      <button class="btn btn-accent" onclick="saveEntry()" id="save-btn">保存</button>
    </div>
  </div>
</div>

<!-- Firebase SDK -->
<script type="module">
import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
import { getFirestore, collection, addDoc, onSnapshot, orderBy, query, serverTimestamp }
  from "https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js";

const firebaseConfig = {
  apiKey: "AIzaSyBVeNx3mS9YdEFiEfJxQTQ-_n4fAdACJrY",
  authDomain: "mion-1f320.firebaseapp.com",
  projectId: "mion-1f320",
  storageBucket: "mion-1f320.firebasestorage.app",
  messagingSenderId: "211366238172",
  appId: "1:211366238172:web:8e973ec547e50d0f92a119",
  measurementId: "G-Z62H6YEG94"
};

const app = initializeApp(firebaseConfig);
const db  = getFirestore(app);

const BIRTH = new Date('2026-01-23');
const TAG_MAP = {
  growth:  ['成长','成長'],
  life:    ['生活','生活'],
  feeling: ['心情','気持ち'],
  health:  ['生病与治疗','病気と治療']
};
const TAG_CLASS = {
  growth:'tag-growth', life:'tag-life', feeling:'tag-feeling', health:'tag-health'
};

let allEntries   = [];
let currentFilter = 'all';
let activeLangs   = {};
let draftJa       = null;

/* ── FIRESTORE REALTIME LISTENER ── */
const q = query(collection(db,'entries'), orderBy('date','desc'));
onSnapshot(q, snap => {
  allEntries = snap.docs.map(d => ({ id: d.id, ...d.data() }));
  updateStats();
  renderEntries();
  document.getElementById('sync-dot').classList.remove('offline');
  document.getElementById('sync-text').textContent = '已同步 · 同期済み';
}, err => {
  document.getElementById('sync-dot').classList.add('offline');
  document.getElementById('sync-text').textContent = '连接失败 · 接続エラー';
});

/* ── STATS ── */
function updateStats() {
  const now  = new Date();
  const days = Math.floor((now - BIRTH) / 86400000);
  const months = Math.floor(days / 30);
  document.getElementById('total-count').textContent  = allEntries.length;
  document.getElementById('age-display').textContent  = months + '个月';
  document.getElementById('days-display').textContent = days + '天';
}

/* ── RENDER ENTRIES ── */
function renderEntries() {
  const list = currentFilter === 'all'
    ? allEntries
    : allEntries.filter(e => e.tag === currentFilter);

  const el = document.getElementById('entries-list');
  if (!list.length) {
    el.innerHTML = '<div class="loading-msg">暂无日记 / 日記がありません</div>';
    return;
  }
  el.innerHTML = list.map(e => {
    const lang = activeLangs[e.id] || 'zh';
    const tl   = TAG_MAP[e.tag] || ['',''];
    const [y,m,d] = (e.date||'').split('-');
    const dateStr = y ? `${y}年${parseInt(m)}月${parseInt(d)}日` : '';
    return `
    <div class="entry">
      <div class="entry-meta">
        <span class="entry-date">${dateStr}</span>
        <span class="entry-tag ${TAG_CLASS[e.tag]||''}">${tl[0]} / ${tl[1]}</span>
      </div>
      <div class="entry-title">${lang==='zh' ? (e.title||'') : (e.titleJa||e.title||'')}</div>
      <div class="lang-tabs">
        <button class="lang-tab ${lang==='zh'?'active':''}" onclick="window._setLang('${e.id}','zh')">中文</button>
        <button class="lang-tab ${lang==='ja'?'active':''}" onclick="window._setLang('${e.id}','ja')">日本語</button>
      </div>
      ${lang==='zh'
        ? `<div class="entry-body">${e.body||''}</div>`
        : `<div class="entry-body-ja">${e.bodyJa||'<span class="translating">日本語訳なし</span>'}</div>`
      }
    </div>`;
  }).join('');
}

window._setLang = (id, lang) => { activeLangs[id] = lang; renderEntries(); };

/* ── FILTER ── */
window.filterTag = tag => {
  currentFilter = tag;
  document.querySelectorAll('.filter-btn').forEach(b =>
    b.classList.toggle('active', b.dataset.tag === tag));
  renderEntries();
};

/* ── MODAL ── */
window.openModal = () => {
  draftJa = null;
  document.getElementById('new-date').value  = new Date().toISOString().split('T')[0];
  document.getElementById('new-title').value = '';
  document.getElementById('new-body').value  = '';
  document.getElementById('new-tag').value   = 'growth';
  document.getElementById('ja-preview').textContent = '点击「自动翻译」，AI将自动翻译成日文 / 「自動翻訳」を押すとAIが翻訳します';
  document.getElementById('modal-overlay').style.display = 'flex';
};

window.closeModal = () => {
  document.getElementById('modal-overlay').style.display = 'none';
};

/* ── TRANSLATE ── */
async function googleTranslate(text, from, to) {
  const url = `https://translate.googleapis.com/translate_a/single?client=gtx&sl=${from}&tl=${to}&dt=t&q=${encodeURIComponent(text)}`;
  const res = await fetch(url);
  const data = await res.json();
  return data[0].map(s => s[0]).join('');
}

window.doTranslate = async () => {
  const title = document.getElementById('new-title').value.trim();
  const body  = document.getElementById('new-body').value.trim();
  if (!body) { alert('请先填写中文内容'); return; }
  const prev = document.getElementById('ja-preview');
  const btn  = document.getElementById('translate-btn');
  prev.textContent = '翻訳中… / 翻译中…';
  btn.disabled = true;
  try {
    const [jaTitle, jaBody] = await Promise.all([
      title ? googleTranslate(title, 'zh-CN', 'ja') : Promise.resolve(''),
      googleTranslate(body, 'zh-CN', 'ja')
    ]);
    draftJa = { title: jaTitle, body: jaBody };
    prev.textContent = (jaTitle ? jaTitle + '\n\n' : '') + jaBody;
  } catch(e) {
    prev.textContent = '翻译失败，请重试 / 翻訳に失敗しました';
  }
  btn.disabled = false;
};

/* ── SAVE ── */
window.saveEntry = async () => {
  const date  = document.getElementById('new-date').value;
  const title = document.getElementById('new-title').value.trim();
  const tag   = document.getElementById('new-tag').value;
  const body  = document.getElementById('new-body').value.trim();
  if (!date || !body) { alert('请填写日期和内容 / 日付と内容を入力してください'); return; }
  const btn = document.getElementById('save-btn');
  btn.disabled = true;
  btn.textContent = '保存中…';
  try {
    await addDoc(collection(db,'entries'), {
      date, title, tag, body,
      titleJa: draftJa?.title || '',
      bodyJa:  draftJa?.body  || '',
      createdAt: serverTimestamp()
    });
    closeModal();
  } catch(e) {
    alert('保存失败，请重试 / 保存に失敗しました');
  }
  btn.disabled = false;
  btn.textContent = '保存';
};

/* ── EXPORT ── */
window.doExport = () => {
  const sorted = [...allEntries].sort((a,b) => a.date.localeCompare(b.date));
  let html = `<!DOCTYPE html><html lang="zh"><head><meta charset="UTF-8">
<title>澪音の成長日記</title>
<style>
body{font-family:'Noto Serif JP',serif;max-width:700px;margin:40px auto;padding:0 24px;color:#333;line-height:1.85;background:#faf8f4;}
h1{text-align:center;font-size:22px;font-weight:400;margin-bottom:4px;letter-spacing:0.1em;}
.sub{text-align:center;color:#999;font-size:12px;margin-bottom:36px;}
.entry{background:#fff;border:1px solid #e8e4de;border-radius:12px;padding:22px;margin-bottom:20px;page-break-inside:avoid;}
.meta{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px;}
.date{font-size:12px;color:#aaa;}
.tag{font-size:11px;padding:3px 10px;border-radius:99px;}
.tag-growth{background:#eaf3ee;color:#6a9e85;} .tag-life{background:#eaf0f7;color:#5a7fa8;}
.tag-feeling{background:#f7ecf1;color:#b06080;} .tag-health{background:#faf0e3;color:#b8874a;}
.title{font-size:16px;font-weight:500;margin-bottom:10px;}
.body-zh{font-size:14px;white-space:pre-wrap;margin-bottom:12px;color:#555;}
.ja-label{font-size:11px;color:#bbb;margin-bottom:4px;}
.body-ja{font-size:13px;white-space:pre-wrap;color:#777;border-top:1px solid #f0ede8;padding-top:10px;}
</style></head><body>
<h1>澪音の成長日記</h1>
<p class="sub">パパとママからの贈り物 · 爸爸妈妈写给你的故事</p>`;
  sorted.forEach(e => {
    const tl = TAG_MAP[e.tag]||['',''];
    const [y,m,d] = (e.date||'').split('-');
    const dateStr = y?`${y}年${parseInt(m)}月${parseInt(d)}日`:'';
    html += `<div class="entry">
<div class="meta"><span class="date">${dateStr}</span><span class="tag tag-${e.tag}">${tl[0]} / ${tl[1]}</span></div>
${e.title?`<div class="title">${e.title}${e.titleJa?' / '+e.titleJa:''}</div>`:''}
<div class="body-zh">${e.body||''}</div>
${e.bodyJa?`<div class="ja-label">日本語</div><div class="body-ja">${e.bodyJa}</div>`:''}
</div>`;
  });
  html += '</body></html>';
  const a = document.createElement('a');
  a.href = URL.createObjectURL(new Blob([html],{type:'text/html;charset=utf-8'}));
  a.download = '澪音成长日记.html';
  a.click();
};
</script>
</body>
</html>
