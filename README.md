# mug.github.io
<!DOCTYPE html>
<html lang="zh-CN">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>A面提示</title>
<style>
:root{
  --bg:#f4f1eb;
  --bg-2:#efe9df;
  --surface:rgba(255,255,255,.78);
  --surface-strong:rgba(255,255,255,.92);
  --text:#181512;
  --muted:#6f675f;
  --line:rgba(37,28,20,.08);
  --line-strong:rgba(37,28,20,.14);
  --accent:#b68a52;
  --accent-soft:rgba(182,138,82,.12);
  --shadow:0 12px 40px rgba(39,28,18,.06);
  --shadow-soft:0 6px 20px rgba(39,28,18,.04);
  --radius-xl:28px;
  --radius-lg:22px;
  --radius-md:16px;
}
*{box-sizing:border-box}
html,body{margin:0;padding:0}
body{
  font-family:-apple-system,BlinkMacSystemFont,"PingFang SC","Helvetica Neue","Microsoft YaHei",sans-serif;
  background:
    radial-gradient(circle at top left, rgba(182,138,82,.08), transparent 26%),
    radial-gradient(circle at 100% 20%, rgba(255,255,255,.6), transparent 22%),
    linear-gradient(180deg,var(--bg),var(--bg-2));
  color:var(--text);
  min-height:100vh;
}
.container{max-width:520px;margin:auto;padding:18px 16px 34px}
.hero{
  position:relative;
  overflow:hidden;
  background:linear-gradient(180deg,rgba(255,255,255,.86),rgba(255,255,255,.68));
  border:1px solid var(--line);
  border-radius:32px;
  padding:26px 22px 22px;
  box-shadow:var(--shadow);
  margin-bottom:16px;
  backdrop-filter:blur(12px);
  -webkit-backdrop-filter:blur(12px);
}
.hero::before{
  content:"";
  position:absolute;
  inset:-40% auto auto -10%;
  width:240px;
  height:240px;
  border-radius:50%;
  background:radial-gradient(circle, rgba(182,138,82,.12), transparent 64%);
  pointer-events:none;
}
.hero::after{
  content:"";
  position:absolute;
  right:-60px;
  top:-50px;
  width:180px;
  height:180px;
  border-radius:50%;
  background:radial-gradient(circle, rgba(255,255,255,.72), transparent 70%);
  pointer-events:none;
}
.hero-top{
  position:relative;
  z-index:1;
  display:inline-flex;
  align-items:center;
  gap:8px;
  padding:8px 12px;
  border-radius:999px;
  background:var(--accent-soft);
  color:var(--accent);
  font-size:11px;
  letter-spacing:.18em;
  text-transform:uppercase;
  font-weight:700;
  margin-bottom:16px;
}
.hero-title{
  position:relative;
  z-index:1;
  font-size:40px;
  line-height:1.02;
  font-weight:800;
  letter-spacing:-.04em;
  margin:0;
}
.hero-title small{
  display:block;
  margin-top:8px;
  font-size:17px;
  line-height:1.4;
  letter-spacing:0;
  font-weight:600;
  color:var(--muted);
}
.hero-subtitle{
  position:relative;
  z-index:1;
  margin-top:16px;
  font-size:14px;
  line-height:1.8;
  color:var(--muted);
  max-width:420px;
}
.hero-meta{
  position:relative;
  z-index:1;
  display:flex;
  gap:10px;
  flex-wrap:wrap;
  margin-top:18px;
}
.hero-pill{
  padding:9px 12px;
  border-radius:999px;
  background:rgba(255,255,255,.76);
  border:1px solid rgba(37,28,20,.06);
  box-shadow:var(--shadow-soft);
  font-size:12px;
  color:var(--muted);
}
.search-wrap{margin:0 0 20px}
.search{
  width:100%;
  padding:16px 18px;
  border-radius:18px;
  border:1px solid var(--line);
  background:var(--surface-strong);
  font-size:15px;
  color:var(--text);
  outline:none;
  box-sizing:border-box;
  box-shadow:var(--shadow-soft);
}
.search:focus{
  border-color:rgba(182,138,82,.42);
  box-shadow:0 0 0 4px rgba(182,138,82,.08),var(--shadow-soft);
}
.section{margin-top:8px}
.tabs{
  display:flex;
  gap:10px;
  margin:0 0 18px;
  padding:6px;
  background:rgba(255,255,255,.46);
  border:1px solid var(--line);
  border-radius:18px;
  box-shadow:var(--shadow-soft);
  backdrop-filter:blur(10px);
  -webkit-backdrop-filter:blur(10px);
}
.tab-btn{
  flex:1;
  border:0;
  background:transparent;
  color:var(--muted);
  padding:12px 14px;
  border-radius:14px;
  font-size:14px;
  font-weight:700;
  cursor:pointer;
  transition:.2s ease;
}
.tab-btn.active{
  background:var(--surface-strong);
  color:var(--text);
  box-shadow:var(--shadow-soft);
}
.section-title{
  display:flex;
  align-items:center;
  justify-content:space-between;
  margin-bottom:12px;
  font-size:18px;
  font-weight:700;
  letter-spacing:-.02em;
}
.section-title::after{
  content:"";
  flex:1;
  height:1px;
  margin-left:12px;
  background:linear-gradient(90deg, rgba(37,28,20,.12), rgba(37,28,20,0));
}
.card{
  background:var(--surface-strong);
  border-radius:22px;
  margin-bottom:12px;
  border:1px solid var(--line);
  overflow:hidden;
  box-shadow:var(--shadow-soft);
}
.card.hidden,.section.hidden{display:none}
.card-header{
  position:relative;
  padding:17px 18px;
  cursor:pointer;
  font-weight:700;
  font-size:16px;
  line-height:1.4;
  letter-spacing:-.01em;
}
.card-header::after{
  content:"⌄";
  position:absolute;
  right:18px;
  top:50%;
  transform:translateY(-50%);
  color:var(--muted);
  font-size:18px;
  transition:transform .2s ease;
}
.card.open .card-header::after{transform:translateY(-50%) rotate(180deg)}
.card-content{
  display:none;
  padding:0 14px 16px;
  border-top:1px solid rgba(37,28,20,.06);
  background:linear-gradient(180deg, rgba(255,255,255,.24), rgba(255,255,255,.02));
}
.hint{
  margin-top:10px;
  padding:14px 14px 12px;
  background:rgba(245,243,239,.88);
  border:1px solid rgba(37,28,20,.06);
  border-radius:16px;
  cursor:pointer;
  transition:.18s ease;
}
.hint:hover{background:rgba(255,255,255,.96)}
.hint-label{
  display:flex;
  align-items:center;
  justify-content:space-between;
  font-size:14px;
  font-weight:700;
  color:var(--text);
}
.hint-label::after{
  content:"+";
  font-size:18px;
  line-height:1;
  color:var(--muted);
}
.hint.open .hint-label::after{content:"−"}
.hint-content{
  display:none;
  margin-top:10px;
  padding-top:10px;
  border-top:1px dashed rgba(37,28,20,.1);
  font-size:14px;
  line-height:1.85;
  color:#5f5851;
}
.open>.card-content{display:block}
.open>.hint-content{display:block}
.empty-state{
  display:none;
  padding:18px;
  border-radius:18px;
  background:rgba(255,255,255,.78);
  border:1px solid var(--line);
  color:var(--muted);
  font-size:14px;
  line-height:1.7;
  box-shadow:var(--shadow-soft);
}
.empty-state.show{display:block}
@media (max-width:430px){
  .hero{padding:24px 18px 20px}
  .hero-title{font-size:34px}
}
</style>
</head>
<body>
<div class="container">
<div class="hero">
  <div class="hero-top">Puzzle Guide · Side A</div>
  <h1 class="hero-title">提示A<small>提示B的部分请玩家B扫描对应物料上的二维码查看</small></h1>
  <div class="hero-subtitle">当玩家在双人合作解谜中遇到卡点时，可在此按主线或支线分类，逐层查看对应提示，保留推理过程与游玩节奏。</div>
  <div class="hero-meta">
    <div class="hero-pill">双人协作模式</div>
    <div class="hero-pill">分层提示查看</div>
    <div class="hero-pill">按谜题快速检索</div>
  </div>
</div>

<div class="search-wrap">
  <input id="searchInput" class="search" type="text" placeholder="搜索主线、支线、谜题1、谜题2……" />
</div>

<div class="tabs">
  <button class="tab-btn active" data-tab="主线谜题">主线谜题</button>
  <button class="tab-btn" data-tab="支线谜题">支线谜题</button>
</div>

<div id="emptyState" class="empty-state">没有找到对应提示，请换个关键词试试。</div>

<div class="section" data-section="主线谜题">
<div class="section-title">主线谜题</div>

<script>
const createPuzzle = (name)=>{
return `
<div class="card">
  <div class="card-header">${name}</div>
  <div class="card-content">
    ${[1,2,3].map(i=>`
      <div class="hint">
        <div class="hint-label">提示${i}</div>
        <div class="hint-content">这里填写提示${i}内容</div>
      </div>
    `).join('')}
  </div>
</div>
`}

let mainHTML = ''
for(let i=1;i<=8;i++){
  mainHTML += createPuzzle('主线谜题 · 谜题'+i)
}
document.write(mainHTML)
</script>

</div>

<div class="section" data-section="支线谜题">
<div class="section-title">支线谜题</div>

<script>
let subHTML = ''
for(let i=1;i<=8;i++){
  subHTML += createPuzzle('支线谜题 · 谜题'+i)
}
document.write(subHTML)
</script>

</div>

</div>

<script>
document.addEventListener('click',function(e){
  const header = e.target.closest('.card-header')
  if(header){
    const currentCard = header.parentElement
    const currentSection = currentCard.closest('.section')
    currentSection.querySelectorAll('.card.open').forEach(card => {
      if(card !== currentCard){
        card.classList.remove('open')
        card.querySelectorAll('.hint.open').forEach(hint => hint.classList.remove('open'))
      }
    })
    currentCard.classList.toggle('open')
    if(!currentCard.classList.contains('open')){
      currentCard.querySelectorAll('.hint.open').forEach(hint => hint.classList.remove('open'))
    }
    return
  }

  const hint = e.target.closest('.hint')
  if(hint){
    const currentCard = hint.closest('.card')
    currentCard.querySelectorAll('.hint.open').forEach(item => {
      if(item !== hint){
        item.classList.remove('open')
      }
    })
    hint.classList.toggle('open')
  }
})

const searchInput = document.getElementById('searchInput')
const emptyState = document.getElementById('emptyState')

const tabButtons = document.querySelectorAll('.tab-btn')
let activeTab = '主线谜题'

function applyTab(){
  const sections = document.querySelectorAll('.section[data-section]')
  sections.forEach(section => {
    const isCurrent = section.dataset.section === activeTab
    section.classList.toggle('hidden', !isCurrent)
  })
  tabButtons.forEach(btn => {
    btn.classList.toggle('active', btn.dataset.tab === activeTab)
  })
}

function runSearch(){
  const keyword = (searchInput.value || '').trim().toLowerCase()
  const sections = document.querySelectorAll('.section[data-section]')
  let visibleCount = 0

  sections.forEach(section => {
    const sectionName = (section.dataset.section || '').toLowerCase()
    const cards = section.querySelectorAll('.card')
    let sectionVisible = 0
    const isActiveSection = section.dataset.section === activeTab

    cards.forEach(card => {
      const text = card.innerText.toLowerCase()
      const matched = !keyword || text.includes(keyword) || sectionName.includes(keyword)
      card.classList.toggle('hidden', !matched)
      if(matched && isActiveSection){
        visibleCount++
        sectionVisible++
      }
    })

    section.classList.toggle('hidden', !isActiveSection || sectionVisible === 0)
  })

  emptyState.classList.toggle('show', visibleCount === 0)
}

tabButtons.forEach(btn => {
  btn.addEventListener('click', () => {
    activeTab = btn.dataset.tab
    applyTab()
    runSearch()
  })
})

searchInput.addEventListener('input', runSearch)
applyTab()
runSearch()
</script>

</body>
</html>
