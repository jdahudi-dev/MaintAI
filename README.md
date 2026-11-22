[maintai_frontend_v6.html](https://github.com/user-attachments/files/35237355/maintai_frontend_v6.html)
# MaintAI
Agent IA d'aide à la maintenance 

<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MAINT.AI — Maintenance Intelligence</title>
<style>
:root{--bg:#080d18;--panel:#101a2b;--panel2:#142239;--line:#243550;--text:#edf3ff;--muted:#91a2bd;--blue:#3987ff;--cyan:#43d5e8;--yellow:#f4c542;--red:#ff647c;--green:#39d6a0;--shadow:0 18px 50px #0005}
*{box-sizing:border-box}body{margin:0;background:radial-gradient(circle at 80% -10%,#17345b 0,transparent 32%),var(--bg);color:var(--text);font:14px/1.5 Inter,Segoe UI,Arial,sans-serif}
button,input,select,textarea{font:inherit}button{cursor:pointer}.app{display:grid;grid-template-columns:248px 1fr;min-height:100vh}
.sidebar{background:#0b1322;border-right:1px solid var(--line);padding:24px 16px;display:flex;flex-direction:column;gap:26px;position:sticky;top:0;height:100vh}
.brand{display:flex;align-items:center;gap:12px;padding:0 8px}.logo{width:42px;height:42px;border-radius:13px;background:linear-gradient(135deg,var(--blue),#1748a2);display:grid;place-items:center;font-weight:900;font-size:20px;box-shadow:0 8px 24px #246bdb55}.brand strong{font-size:18px;letter-spacing:1.5px}.brand small{display:block;color:var(--muted);font-size:10px;letter-spacing:1.8px}
.nav-label{color:#637795;font-size:10px;font-weight:800;letter-spacing:1.6px;padding:0 12px;margin-bottom:8px}.nav{display:grid;gap:5px}.nav button{border:0;background:transparent;color:#aab9d0;text-align:left;padding:12px;border-radius:10px;display:flex;align-items:center;gap:12px;transition:.2s}.nav button:hover,.nav button.active{background:#18345b;color:white}.nav button.active{box-shadow:inset 3px 0 var(--blue)}.nav .ico{width:20px;text-align:center;font-size:16px}.side-foot{margin-top:auto;border:1px solid var(--line);border-radius:12px;padding:13px;color:var(--muted);font-size:11px}.status-dot{display:inline-block;width:7px;height:7px;background:var(--green);border-radius:50%;margin-right:6px}
main{min-width:0}.topbar{height:76px;border-bottom:1px solid var(--line);display:flex;align-items:center;justify-content:space-between;padding:0 34px;background:#0b1322b8;backdrop-filter:blur(12px);position:sticky;top:0;z-index:5}.crumb{color:var(--muted);font-size:12px}.top-title{font-size:18px;font-weight:700}.top-right{display:flex;align-items:center;gap:14px}.pill{border:1px solid var(--line);border-radius:30px;padding:7px 11px;color:var(--muted);font-size:11px}.avatar{width:34px;height:34px;border-radius:50%;background:#1c3e6d;display:grid;place-items:center;font-weight:700}
.content{padding:30px 34px 55px;max-width:1500px;margin:auto}.page{display:none}.page.active{display:block}.page-head{display:flex;align-items:flex-start;justify-content:space-between;gap:20px;margin-bottom:25px}.eyebrow{color:var(--cyan);font-size:10px;font-weight:800;letter-spacing:2px;text-transform:uppercase}.page h1{font-size:27px;margin:5px 0 4px;letter-spacing:-.5px}.sub{color:var(--muted);margin:0}.btn{border:1px solid var(--line);background:#17263d;color:var(--text);border-radius:9px;padding:10px 15px;font-weight:650}.btn:hover{border-color:var(--blue);background:#1b3558}.btn.primary{background:linear-gradient(135deg,#2878f5,#1553bd);border-color:#3987ff;box-shadow:0 8px 22px #1c64d744}.btn.small{padding:7px 10px;font-size:12px}.grid{display:grid;gap:16px}.kpis{grid-template-columns:repeat(4,minmax(0,1fr));margin-bottom:18px}.card{background:linear-gradient(145deg,#121e31,#0f1929);border:1px solid var(--line);border-radius:15px;padding:19px;box-shadow:var(--shadow);min-width:0}.kpi-top{display:flex;justify-content:space-between;color:var(--muted);font-size:12px}.kpi-icon{width:31px;height:31px;border-radius:9px;background:#1b3455;display:grid;place-items:center;color:var(--cyan)}.kpi-value{font-size:28px;font-weight:750;margin:12px 0 2px}.kpi-note{font-size:11px;color:var(--muted)}.two-col{grid-template-columns:1.35fr 1fr}.section-title{display:flex;justify-content:space-between;align-items:center;margin-bottom:15px}.section-title h3{font-size:14px;margin:0}.muted{color:var(--muted)}.empty{padding:36px 16px;text-align:center;color:var(--muted);border:1px dashed #304461;border-radius:12px}.empty b{display:block;color:#dce8fa;margin-bottom:5px}.table-wrap{overflow:auto}table{width:100%;border-collapse:collapse;white-space:nowrap}th,td{text-align:left;padding:12px 11px;border-bottom:1px solid #203049;font-size:12px}th{color:#8094b2;font-weight:700;font-size:10px;text-transform:uppercase;letter-spacing:.8px}td{color:#dce6f6}.tag{display:inline-flex;align-items:center;padding:4px 8px;border-radius:20px;font-size:10px;font-weight:800;letter-spacing:.4px;background:#1b2d47;color:#a9c8f8}.tag.green{background:#12372f;color:#54e0b0}.tag.yellow{background:#40351a;color:#f6d36a}.tag.red{background:#421e2b;color:#ff8294}.form-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:14px}.field label{display:block;color:#9fb0c9;font-size:11px;margin-bottom:6px}.field input,.field select,.field textarea{width:100%;background:#0b1525;border:1px solid #2a3d5a;color:var(--text);border-radius:8px;padding:11px;outline:none}.field input:focus,.field select:focus,.field textarea:focus{border-color:var(--blue);box-shadow:0 0 0 3px #3987ff20}.field textarea{min-height:90px;resize:vertical}.field.full{grid-column:1/-1}.form-actions{display:flex;gap:10px;align-items:center;margin-top:18px}.hint{font-size:11px;color:var(--muted)}.result{margin-top:20px;display:none}.result.show{display:block}.result-head{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:12px}.result-score{font-size:32px;font-weight:800}.result-grid{grid-template-columns:repeat(3,1fr)}.result-block{background:#0c1727;border:1px solid #263b59;border-radius:10px;padding:13px}.result-block h4{margin:0 0 8px;font-size:11px;color:var(--muted);text-transform:uppercase}.result-block p{margin:0;font-size:12px;white-space:pre-wrap}.notice{border:1px solid #665321;background:#302714;color:#f3d987;border-radius:10px;padding:12px;font-size:11px;margin-top:14px}.toolbar{display:flex;gap:10px;align-items:center;flex-wrap:wrap;margin-bottom:14px}.toolbar input{background:#0b1525;border:1px solid var(--line);color:white;border-radius:8px;padding:9px 12px;min-width:220px}.metric-line{display:flex;justify-content:space-between;gap:10px;padding:10px 0;border-bottom:1px solid #203049;font-size:12px}.metric-line:last-child{border:0}.bar{height:7px;background:#263750;border-radius:20px;overflow:hidden;margin-top:7px}.bar span{display:block;height:100%;background:linear-gradient(90deg,var(--blue),var(--cyan));border-radius:20px}.setting-row{display:flex;justify-content:space-between;gap:20px;padding:15px 0;border-bottom:1px solid #203049}.setting-row:last-child{border:0}.mobile-menu{display:none}
@media(max-width:1050px){.kpis{grid-template-columns:repeat(2,1fr)}.two-col{grid-template-columns:1fr}.form-grid{grid-template-columns:repeat(2,1fr)}}
@media(max-width:720px){.app{grid-template-columns:1fr}.sidebar{height:auto;position:relative;padding:13px;gap:12px;border-right:0;border-bottom:1px solid var(--line)}.brand{padding:0 4px}.nav-label,.side-foot{display:none}.nav{display:flex;overflow:auto}.nav button{white-space:nowrap;padding:9px 11px;font-size:12px}.topbar{position:relative;padding:0 17px;height:62px}.content{padding:22px 16px 40px}.page-head{display:block}.page-head .btn{margin-top:15px}.kpis{gap:10px}.card{padding:14px}.kpi-value{font-size:23px}.form-grid{grid-template-columns:1fr}.result-grid{grid-template-columns:1fr}.page h1{font-size:23px}.top-right .pill{display:none}}
body:not(.authenticated) .app{display:none}
.auth-screen{min-height:100vh;display:grid;place-items:center;padding:24px;background:radial-gradient(circle at 75% 5%,#17345b 0,transparent 35%),var(--bg)}
body.authenticated .auth-screen{display:none}
.auth-card{width:min(100%,430px);background:linear-gradient(145deg,#121e31,#0f1929);border:1px solid var(--line);border-radius:18px;padding:30px;box-shadow:var(--shadow)}
.auth-brand{display:flex;align-items:center;gap:12px;margin-bottom:25px}.auth-brand .logo{flex:none}
.auth-card h1{font-size:23px;margin:0 0 6px}.auth-card .sub{margin-bottom:22px}
.auth-card .field{margin:14px 0}.auth-card .btn{width:100%;margin-top:10px}
.auth-message{font-size:12px;color:var(--muted);margin-top:14px;min-height:18px}.auth-message.error{color:#ff8294}.auth-message.success{color:var(--green)}
.auth-user{display:flex;align-items:center;gap:10px}.auth-user-info{font-size:11px;color:var(--muted);text-align:right}.auth-user-info b{display:block;color:var(--text);font-size:12px}
.role-tag{font-size:10px;color:var(--cyan);text-transform:uppercase;letter-spacing:.8px}
.password-wrap{position:relative;display:flex;align-items:center}
.password-wrap input{padding-right:48px!important}
.password-toggle{position:absolute;right:7px;top:50%;transform:translateY(-50%);width:34px;height:34px;border:0;border-radius:7px;background:transparent;color:var(--muted);display:grid;place-items:center;padding:0}
.password-toggle:hover{background:#1b3455;color:var(--text)}
.password-toggle svg{width:18px;height:18px;display:block}
</style>
</head>
<body>
<section class="auth-screen" id="authScreen">
 <div class="auth-card">
  <div class="auth-brand"><div class="logo">M</div><div><strong style="font-size:18px;letter-spacing:1.5px">MAINT.AI</strong><small style="display:block;color:var(--muted);font-size:10px;letter-spacing:1.8px">MAINTENANCE INTELLIGENCE</small></div></div>
  <div class="eyebrow">ESPACE SÉCURISÉ</div><h1>Connexion</h1><p class="sub">Connectez-vous pour accéder à votre espace MAINT.AI.</p>
  <form id="loginForm">
   <div class="field"><label for="loginEmail">Adresse e-mail</label><input id="loginEmail" type="email" autocomplete="username" required placeholder="nom@exemple.com"></div>
   <div class="field"><label for="loginPassword">Mot de passe</label><div class="password-wrap"><input id="loginPassword" type="password" autocomplete="current-password" required placeholder="Votre mot de passe"><button class="password-toggle" id="togglePassword" type="button" aria-label="Afficher le mot de passe" aria-pressed="false" title="Afficher le mot de passe"><svg id="eyeIcon" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><path d="M2 12s3.6-7 10-7 10 7 10 7-3.6 7-10 7-10-7-10-7Z"/><circle cx="12" cy="12" r="3"/></svg></button></div></div>
   <button class="btn primary" id="loginButton" type="submit">Se connecter</button>
  </form>
  <div class="auth-message" id="authMessage">Accès réservé aux utilisateurs autorisés.</div>
 </div>
</section>
<div class="app">
<aside class="sidebar">
  <div class="brand"><div class="logo">M</div><div><strong>MAINT.AI</strong><small>MAINTENANCE INTELLIGENCE</small></div></div>
  <div><div class="nav-label">ESPACE DE TRAVAIL</div><nav class="nav">
    <button class="active" data-page="dashboard"><span class="ico">▦</span>Vue d'ensemble</button>
    <button data-page="motors"><span class="ico">◉</span>Moteurs</button>
    <button data-page="diagnostic"><span class="ico">⌁</span>Diagnostic</button>
    <button data-page="history"><span class="ico">◷</span>Historique</button>
    <button data-page="reports"><span class="ico">▤</span>Rapports</button>
  </nav></div>
  <div><div class="nav-label">CONFIGURATION</div><nav class="nav"><button data-page="settings"><span class="ico">⚙</span>Paramètres</button></nav></div>
  <div class="side-foot"><span class="status-dot"></span>Interface opérationnelle<br><span style="display:block;margin-top:7px">Prototype sécurisé · Session utilisateur</span></div>
</aside>
<main>
<header class="topbar"><div><div class="crumb">MAINT.AI / <span id="crumb">Vue d'ensemble</span></div><div class="top-title" id="topTitle">Centre de supervision</div></div><div class="top-right"><span class="pill">● Espace sécurisé</span><div class="auth-user"><div class="auth-user-info"><b id="currentUserEmail">—</b><span class="role-tag" id="currentUserRole">—</span></div><button class="btn small" id="logoutButton" type="button">Déconnexion</button></div></div></header>
<div class="content">
<section class="page active" id="page-dashboard">
 <div class="page-head"><div><div class="eyebrow">SUPERVISION</div><h1>Vue d'ensemble</h1><p class="sub">Suivez l'activité de diagnostic de votre espace MAINT.AI.</p></div><button class="btn primary" onclick="showPage('diagnostic')">＋ Nouveau diagnostic</button></div>
 <div class="grid kpis">
  <div class="card"><div class="kpi-top">Diagnostics réalisés <span class="kpi-icon">⌁</span></div><div class="kpi-value" id="kpi-total">0</div><div class="kpi-note">Dans cette session navigateur</div></div>
  <div class="card"><div class="kpi-top">Moteurs analysés <span class="kpi-icon">◉</span></div><div class="kpi-value" id="kpi-motors">0</div><div class="kpi-note">Identifiants distincts</div></div>
  <div class="card"><div class="kpi-top">Alertes élevées / critiques <span class="kpi-icon">⚠</span></div><div class="kpi-value" id="kpi-alerts">0</div><div class="kpi-note">Sur les diagnostics de session</div></div>
  <div class="card"><div class="kpi-top">Dernier score de risque <span class="kpi-icon">◈</span></div><div class="kpi-value" id="kpi-score">—</div><div class="kpi-note" id="kpi-score-note">Aucun diagnostic enregistré</div></div>
 </div>
 <div class="grid two-col">
  <div class="card"><div class="section-title"><h3>Diagnostics récents</h3><button class="btn small" onclick="showPage('history')">Voir l'historique</button></div><div id="recentTable" class="empty"><b>Aucune donnée dans cette session</b>Lancez un diagnostic pour alimenter le tableau de bord.</div></div>
  <div class="card"><div class="section-title"><h3>Répartition des états</h3><span class="muted" style="font-size:11px">Session courante</span></div><div id="stateSummary" class="empty">Les indicateurs apparaîtront après vos premiers diagnostics.</div></div>
 </div>
 <div class="notice">Les indicateurs de cette page sont calculés uniquement à partir des diagnostics effectués depuis cette interface sur ce navigateur. Ils ne représentent pas encore l'ensemble du parc moteur ni les données complètes de Google Sheets.</div>
</section>
<section class="page" id="page-motors">
 <div class="page-head"><div><div class="eyebrow">PARC ÉQUIPEMENTS</div><h1>Moteurs</h1><p class="sub">Consultez les moteurs identifiés dans vos diagnostics de session.</p></div><button class="btn primary" onclick="showPage('diagnostic')">＋ Analyser un moteur</button></div>
 <div class="card"><div class="toolbar"><input id="motorSearch" placeholder="Rechercher un identifiant moteur…" oninput="renderMotors()"><span class="hint">Référentiel complet à connecter via API n8n.</span></div><div id="motorsTable" class="empty"><b>Aucun moteur affiché</b>Les identifiants apparaîtront après un diagnostic.</div></div>
</section>
<section class="page" id="page-diagnostic">
 <div class="page-head"><div><div class="eyebrow">ANALYSE TECHNIQUE</div><h1>Nouveau diagnostic</h1><p class="sub">Saisissez les mesures disponibles pour lancer l'analyse du moteur.</p></div></div>
 <div class="card">
  <form id="diagnosticForm">
   <div class="section-title"><h3>Identification</h3><span class="tag">Étape 1 · Moteur</span></div>
   <div class="form-grid">
    <div class="field"><label>Identifiant moteur *</label><input name="motor_id" value="MTR-001" required></div>
    <div class="field"><label>Opérateur</label><input name="operateur" placeholder="Nom ou identifiant"></div>
    <div class="field"><label>Source</label><select name="source"><option value="WEB">Interface Web</option><option value="MANUEL">Saisie manuelle</option></select></div>
   </div>
   <div class="section-title" style="margin-top:25px"><h3>Mesures électriques</h3><span class="tag">Étape 2 · Électrique</span></div>
   <div class="form-grid">
    <div class="field"><label>Courant phase L1 (A) *</label><input name="courant_l1" type="number" step="any" min="0" required placeholder="Ex. 12.3"></div>
    <div class="field"><label>Courant phase L2 (A) *</label><input name="courant_l2" type="number" step="any" min="0" required placeholder="Ex. 12.1"></div>
    <div class="field"><label>Courant phase L3 (A) *</label><input name="courant_l3" type="number" step="any" min="0" required placeholder="Ex. 12.4"></div>
    <div class="field"><label>Tension (V)</label><input name="tension_v" type="number" step="any" min="0" placeholder="Ex. 400"></div>
    <div class="field"><label>Vitesse (tr/min)</label><input name="vitesse_rpm" type="number" step="any" min="0" placeholder="Ex. 1470"></div>
    <div class="field"><label>Charge (%)</label><input name="charge_pct" type="number" step="any" min="0" placeholder="Optionnel"></div>
   </div>
   <div class="section-title" style="margin-top:25px"><h3>Mesures mécaniques et thermiques</h3><span class="tag">Étape 3 · État</span></div>
   <div class="form-grid">
    <div class="field"><label>Température carcasse (°C)</label><input name="temperature_c" type="number" step="any" placeholder="Ex. 68"></div>
    <div class="field"><label>Vibrations RMS (mm/s)</label><input name="vibration_mm_s" type="number" step="any" min="0" placeholder="Optionnel"></div>
    <div class="field"><label>Heures de fonctionnement (h)</label><input name="heures_fonctionnement_h" type="number" step="any" min="0" placeholder="Optionnel"></div>
    <div class="field full"><label>Observations</label><textarea name="observations" placeholder="Bruit inhabituel, échauffement, conditions de charge…"></textarea></div>
   </div>
   <div class="form-actions"><button class="btn primary" id="submitBtn" type="submit">Lancer le diagnostic</button><button class="btn" type="reset">Réinitialiser</button><span class="hint" id="formStatus">Les champs marqués * sont obligatoires.</span></div>
  </form>
  <div class="result" id="resultPanel"></div>
 </div>
 <div class="notice">Diagnostic préliminaire d'aide à la décision. Les seuils du prototype sont provisoires et doivent être validés selon la plaque moteur, le constructeur, les conditions d'exploitation et les références applicables.</div>
</section>
<section class="page" id="page-history">
 <div class="page-head"><div><div class="eyebrow">TRAÇABILITÉ</div><h1>Historique</h1><p class="sub">Retrouvez les diagnostics effectués depuis cette interface.</p></div><button class="btn" onclick="exportCSV()">Exporter CSV</button></div>
 <div class="card"><div class="toolbar"><input id="historySearch" placeholder="Filtrer par moteur ou diagnostic…" oninput="renderHistory()"><span class="hint">Historique local de session — pas encore synchronisé en lecture depuis Sheets.</span></div><div id="historyTable" class="empty"><b>Historique vide</b>Les diagnostics réalisés apparaîtront ici.</div></div>
</section>
<section class="page" id="page-reports">
 <div class="page-head"><div><div class="eyebrow">DOCUMENTATION</div><h1>Rapports</h1><p class="sub">Consultez et exportez les comptes rendus générés par MAINT.AI.</p></div></div>
 <div class="card"><div class="section-title"><h3>Rapports de diagnostic</h3><span class="tag">Session courante</span></div><div id="reportsList" class="empty"><b>Aucun rapport disponible</b>Un rapport sera listé après le premier diagnostic.</div></div>
</section>
<section class="page" id="page-settings">
 <div class="page-head"><div><div class="eyebrow">CONFIGURATION</div><h1>Paramètres</h1><p class="sub">Configuration des connexions et informations du prototype.</p></div></div>
 <div class="card">
  <div class="setting-row"><div><b>Webhook n8n</b><div class="muted" style="font-size:11px">URL utilisée pour transmettre les diagnostics.</div></div><span class="tag yellow">Mode test</span></div>
  <div class="field" style="margin:12px 0 18px"><label>URL du webhook</label><input id="webhookInput" type="url" value="https://prototyp.app.n8n.cloud/webhook-test/maintai-diagnostic"></div>
  <div class="setting-row"><div><b>Google Sheets</b><div class="muted" style="font-size:11px">Historisation via le workflow n8n.</div></div><span class="tag green">Archivage testé</span></div>
  <div class="setting-row"><div><b>Analyse IA</b><div class="muted" style="font-size:11px">Interprétation du diagnostic par Claude via n8n.</div></div><span class="tag green">Réponse testée</span></div>
  <div class="setting-row"><div><b>Telegram</b><div class="muted" style="font-size:11px">Canal de messagerie à configurer séparément.</div></div><span class="tag yellow">À configurer</span></div>
  <div class="setting-row"><div><b>Authentification et accès</b><div class="muted" style="font-size:11px">À mettre en place avant toute mise en ligne publique.</div></div><span class="tag red">À sécuriser</span></div>
  <div style="margin-top:18px;display:flex;gap:10px;flex-wrap:wrap"><button class="btn primary" onclick="saveSettings()">Enregistrer l'URL</button><button class="btn" onclick="clearSession()">Effacer les données de cette session</button></div>
  <p class="hint" id="settingsStatus" style="margin-top:12px">Ne placez jamais une clé API ou un mot de passe dans ce fichier HTML.</p>
 </div>
</section>
</div>
</main>
</div>

<script>
const DEFAULT_WEBHOOK='https://prototyp.app.n8n.cloud/webhook-test/maintai-diagnostic';
let WEBHOOK_URL=localStorage.getItem('maintai_webhook')||DEFAULT_WEBHOOK;
let records=[];
try{records=JSON.parse(sessionStorage.getItem('maintai_records')||'[]')}catch(e){records=[]}
document.getElementById('webhookInput').value=WEBHOOK_URL;
const titles={dashboard:['Vue d’ensemble','Centre de supervision'],motors:['Moteurs','Parc équipements'],diagnostic:['Diagnostic','Analyse technique'],history:['Historique','Traçabilité'],reports:['Rapports','Documentation'],settings:['Paramètres','Configuration']};
function showPage(name){document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));document.getElementById('page-'+name).classList.add('active');document.querySelectorAll('.nav button').forEach(b=>b.classList.toggle('active',b.dataset.page===name));document.getElementById('crumb').textContent=titles[name][0];document.getElementById('topTitle').textContent=titles[name][1];if(name==='dashboard')renderDashboard();if(name==='motors')renderMotors();if(name==='history')renderHistory();if(name==='reports')renderReports();window.scrollTo({top:0,behavior:'smooth'})}
document.querySelectorAll('.nav button').forEach(b=>b.addEventListener('click',()=>showPage(b.dataset.page)));
function val(obj,...keys){for(const k of keys){if(obj&&obj[k]!==undefined&&obj[k]!==null&&obj[k]!=='')return obj[k]}return ''}
function normalizeResult(raw,form) {
    let d = raw?.data || raw?.result || raw?.diagnostic || raw;
    if (Array.isArray(d)) d = d[0] || {};
    return {
        id: val(d,'analysis_id','diagnostic_id','id') || 'DX-'+Date.now(),
        motor: val(d,'motor_id') || form.motor_id,
        operator: form.operateur || 'Non renseigné',
        source: form.source || 'WEB',
        measurements: {
            courant_l1: form.courant_l1,courant_l2: form.courant_l2,courant_l3: form.courant_l3,
            tension_v: form.tension_v,temperature_c: form.temperature_c,
            vibration_mm_s: form.vibration_mm_s,vitesse_rpm: form.vitesse_rpm,
            charge_pct: form.charge_pct,heures_fonctionnement_h: form.heures_fonctionnement_h,
            observations: form.observations
        },
        level: String(val(d,'niveau','etat_global','risk_level','classification') || 'INDETERMINE').toUpperCase(),
        score: val(d,'score_risque','score','risk_score'),
        current: val(d,'courant_moyen_a','courant_moyen','current_avg'),
        load: val(d,'taux_charge_pct','taux_charge','load_rate'),
        imbalance: val(d,'desequilibre_courant_pct','desequilibre_courant','current_imbalance'),
        temp: val(d,'temperature_c','temperature_carcasse_c') || form.temperature_c,
        summary: val(d,'resume','synthese','avis_ia','rapport','diagnostic_ia','message') || 'Diagnostic reçu.',
        anomalies: val(d,'anomalies','anomalies_detectees','liste_anomalies'),
        causes: val(d,'causes_probables','causes'),
        checks: val(d,'controles_recommandes','controles'),
        actions: val(d,'actions_recommandees','recommandations'),
        raw: d,created: new Date().toISOString()
    };
}
function esc(s){return String(s??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]))}
function asText(x){if(Array.isArray(x))return x.map(v=>typeof v==='object'?JSON.stringify(v):v).join('\n');if(typeof x==='object'&&x!==null)return JSON.stringify(x,null,2);return String(x||'—')}
function saveRecords(){sessionStorage.setItem('maintai_records',JSON.stringify(records))}
function levelClass(l){return /CRITIQUE/.test(l)?'red':/ÉLEVÉ|ELEVE/.test(l)?'red':/VIGILANCE/.test(l)?'yellow':/NORMAL/.test(l)?'green':'yellow'}
function renderDashboard(){document.getElementById('kpi-total').textContent=records.length;document.getElementById('kpi-motors').textContent=new Set(records.map(r=>r.motor)).size;document.getElementById('kpi-alerts').textContent=records.filter(r=>/ÉLEVÉ|ELEVE|CRITIQUE/.test(r.level)).length;let last=records[0];document.getElementById('kpi-score').textContent=last&&last.score!==''?last.score+'/100':'—';document.getElementById('kpi-score-note').textContent=last?last.level:'Aucun diagnostic enregistré';let recent=records.slice(0,5);document.getElementById('recentTable').innerHTML=recent.length?tableHTML(recent):'<div class="empty"><b>Aucune donnée dans cette session</b>Lancez un diagnostic pour alimenter le tableau de bord.</div>';let counts=['NORMAL','VIGILANCE','ÉLEVÉ','CRITIQUE'].map(l=>[l,records.filter(r=>r.level.includes(l)||(l==='ÉLEVÉ'&&r.level.includes('ELEVE'))).length]);document.getElementById('stateSummary').innerHTML=records.length?counts.map(([l,n])=>`<div class="metric-line"><span>${l}</span><b>${n}</b></div><div class="bar"><span style="width:${100*n/records.length}%"></span></div>`).join(''):'<div class="empty">Les indicateurs apparaîtront après vos premiers diagnostics.</div>'}
function tableHTML(arr){return `<div class="table-wrap"><table><thead><tr><th>Référence</th><th>Moteur</th><th>Date</th><th>État</th><th>Score</th></tr></thead><tbody>${arr.map(r=>`<tr><td>${esc(r.id)}</td><td>${esc(r.motor)}</td><td>${new Date(r.created).toLocaleString('fr-FR')}</td><td><span class="tag ${levelClass(r.level)}">${esc(r.level)}</span></td><td>${r.score!==''?esc(r.score)+'/100':'—'}</td></tr>`).join('')}</tbody></table></div>`}
function renderHistory(){let q=(document.getElementById('historySearch').value||'').toLowerCase();let a=records.filter(r=>(r.motor+' '+r.id+' '+r.level).toLowerCase().includes(q));document.getElementById('historyTable').innerHTML=a.length?tableHTML(a):'<div class="empty"><b>Historique vide</b>Aucun diagnostic correspondant dans cette session.</div>'}
function renderMotors(){let q=(document.getElementById('motorSearch').value||'').toLowerCase();let ids=[...new Set(records.map(r=>r.motor))].filter(x=>x.toLowerCase().includes(q));document.getElementById('motorsTable').innerHTML=ids.length?`<div class="table-wrap"><table><thead><tr><th>Identifiant</th><th>Diagnostics</th><th>Dernier état</th><th>Dernière analyse</th></tr></thead><tbody>${ids.map(id=>{let rs=records.filter(r=>r.motor===id);let r=rs[0];return `<tr><td><b>${esc(id)}</b></td><td>${rs.length}</td><td><span class="tag ${levelClass(r.level)}">${esc(r.level)}</span></td><td>${new Date(r.created).toLocaleString('fr-FR')}</td></tr>`}).join('')}</tbody></table></div>`:'<div class="empty"><b>Aucun moteur affiché</b>Les identifiants apparaîtront après un diagnostic.</div>'}
function renderReports(){document.getElementById('reportsList').innerHTML=records.length?records.map(r=>`<div class="setting-row"><div><b>${esc(r.id)} · ${esc(r.motor)}</b><div class="muted" style="font-size:11px">${new Date(r.created).toLocaleString('fr-FR')} · ${esc(r.level)}</div></div><button class="btn small" onclick="downloadReport('${esc(r.id)}')">Télécharger PDF</button></div>`).join(''):'<div class="empty"><b>Aucun rapport disponible</b>Un rapport sera listé après le premier diagnostic.</div>'}
function displayResult(r){const p=document.getElementById('resultPanel');p.className='result show';p.innerHTML=`<div class="result-head"><div><div class="eyebrow">RÉSULTAT DU DIAGNOSTIC</div><h2 style="margin:5px 0">${esc(r.motor)}</h2><span class="muted" style="font-size:11px">${esc(r.id)}</span></div><div style="text-align:right"><span class="tag ${levelClass(r.level)}">${esc(r.level)}</span><div class="result-score">${r.score!==''?esc(r.score)+'/100':'—'}</div><span class="hint">Score indicatif</span></div></div><div class="grid result-grid"><div class="result-block"><h4>Mesures calculées</h4><p>Courant moyen : ${esc(r.current||'—')} A\nTaux de charge : ${esc(r.load||'—')}%\nDéséquilibre : ${esc(r.imbalance||'—')}%\nTempérature : ${esc(r.temp||'—')} °C</p></div><div class="result-block"><h4>Anomalies détectées</h4><p>${esc(asText(r.anomalies))}</p></div><div class="result-block"><h4>Causes possibles</h4><p>${esc(asText(r.causes))}</p></div><div class="result-block"><h4>Analyse IA</h4><p>${esc(asText(r.summary))}</p></div><div class="result-block"><h4>Contrôles recommandés</h4><p>${esc(asText(r.checks))}</p></div><div class="result-block"><h4>Actions recommandées</h4><p>${esc(asText(r.actions))}</p></div></div><div class="form-actions"><button class="btn" onclick="downloadReport('${esc(r.id)}')">Télécharger le rapport PDF</button><button class="btn" onclick="showPage('history')">Voir l'historique</button></div>`;p.scrollIntoView({behavior:'smooth',block:'start'})}
document.getElementById('diagnosticForm').addEventListener('submit',async e=>{e.preventDefault();const formEl=e.currentTarget;const fd=new FormData(formEl);const f=Object.fromEntries(fd.entries());['courant_l1','courant_l2','courant_l3','tension_v','temperature_c','vibration_mm_s','vitesse_rpm','charge_pct','heures_fonctionnement_h'].forEach(k=>{if(f[k]!==undefined&&f[k]!=='')f[k]=Number(f[k]);else delete f[k]});f.action='diagnostic';const btn=document.getElementById('submitBtn'),status=document.getElementById('formStatus');btn.disabled=true;btn.textContent='Analyse en cours…';status.textContent='Transmission à n8n et attente du diagnostic…';try{const {data:{session}}=await supabaseClient.auth.getSession();if(!session?.access_token)throw new Error('Session expirée. Veuillez vous reconnecter.');const response=await fetch(WEBHOOK_URL,{method:'POST',headers:{'Content-Type':'application/json','Authorization':'Bearer '+session.access_token},body:JSON.stringify(f)});const text=await response.text();let data;try{data=JSON.parse(text)}catch{data={message:text}}if(!response.ok)throw new Error(data.message||data.error||`Erreur HTTP ${response.status}`);const r=normalizeResult(data,f);records.unshift(r);saveRecords();displayResult(r);renderDashboard();status.textContent='Diagnostic reçu. Archivage à confirmer dans Google Sheets.'}catch(err){status.textContent='Échec de la requête.';document.getElementById('resultPanel').className='result show';document.getElementById('resultPanel').innerHTML=`<div class="notice" style="border-color:#79394a;background:#351b26;color:#ffb1bd"><b>Impossible de joindre le webhook.</b><br>${esc(err.message)}<br><br>Vérifiez que le workflow n8n est en écoute (« Execute workflow ») et que l'URL de test est correcte. En mode test, l'écoute peut devoir être relancée avant chaque appel.</div>`}finally{btn.disabled=false;btn.textContent='Lancer le diagnostic'}});
function saveSettings(){WEBHOOK_URL=document.getElementById('webhookInput').value.trim();localStorage.setItem('maintai_webhook',WEBHOOK_URL);document.getElementById('settingsStatus').textContent='URL enregistrée dans ce navigateur.'}
function clearSession(){if(confirm('Effacer les diagnostics enregistrés dans cette session navigateur ?')){records=[];saveRecords();renderDashboard();renderHistory();renderMotors();renderReports();document.getElementById('settingsStatus').textContent='Données de session effacées.'}}
function exportCSV(){
 const rows=[['Référence','Moteur','Date','État','Score','Courant L1','Courant L2','Courant L3','Tension','Température','Vibrations']];
 records.forEach(r=>{const m=r.measurements||{};rows.push([r.id,r.motor,r.created,r.level,r.score,m.courant_l1,m.courant_l2,m.courant_l3,m.tension_v,m.temperature_c,m.vibration_mm_s])});
 const csv='\uFEFF'+rows.map(row=>row.map(v=>'"'+String(v??'').replace(/"/g,'""')+'"').join(';')).join('\r\n');
 const blob=new Blob([csv],{type:'text/csv;charset=utf-8;'});
 const url=URL.createObjectURL(blob);const a=document.createElement('a');a.href=url;a.download='MAINTAI_Historique.csv';a.click();URL.revokeObjectURL(url);
}

/* NOUVELLE FONCTION D'EXPORT PDF */
function downloadReport(id) {
    const r = records.find(x => String(x.id) === String(id));
    if (!r) {
        alert("Rapport introuvable.");
        return;
    }

    const m = r.measurements || {};
    const valeur = v => (v !== undefined && v !== '' && v !== null) ? v : 'Non renseigné';

    const lignes = [
        ['Courant phase L1', valeur(m.courant_l1), 'A'],
        ['Courant phase L2', valeur(m.courant_l2), 'A'],
        ['Courant phase L3', valeur(m.courant_l3), 'A'],
        ['Tension', valeur(m.tension_v), 'V'],
        ['Température carcasse', valeur(m.temperature_c), '°C'],
        ['Vibrations RMS', valeur(m.vibration_mm_s), 'mm/s'],
        ['Vitesse de rotation', valeur(m.vitesse_rpm), 'tr/min'],
        ['Charge', valeur(m.charge_pct), '%'],
        ['Heures de fonctionnement', valeur(m.heures_fonctionnement_h), 'h']
    ];

    const rapportWindow = window.open('', '_blank');

    if (!rapportWindow) {
        alert("La fenêtre du rapport a été bloquée par le navigateur. Autorisez les fenêtres pop-up pour MAINT.AI puis réessayez.");
        return;
    }

    const contenu = `
<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>MAINT.AI - Rapport ${esc(r.id)}</title>
<style>
*{box-sizing:border-box}
body{font-family:Arial,sans-serif;color:#17243a;background:#fff;margin:0;padding:25px;font-size:12px;line-height:1.5}
.report{max-width:850px;margin:auto}
.header{border-bottom:4px solid #2475dc;padding-bottom:15px;margin-bottom:22px}
.header h1{color:#1758ad;margin:0;font-size:28px;letter-spacing:1px}
.header p{margin:3px 0;color:#60718a}
.header h2{margin:20px 0 0;font-size:20px}
h3{color:#1758ad;margin:22px 0 9px;font-size:14px}
table{width:100%;border-collapse:collapse;margin-bottom:18px}
td,th{padding:9px;border:1px solid #d8e0eb;text-align:left}
th{background:#1758ad;color:#fff}
tr:nth-child(even){background:#f0f4fa}
.summary{background:#eef4fc;padding:13px;border-left:4px solid #2475dc;margin-bottom:18px}
.summary p{margin:5px 0}
.content-block{padding:11px;border:1px solid #d8e0eb;margin-bottom:14px;white-space:pre-wrap;overflow-wrap:anywhere}
.ai-block{background:#f0f4fa}
.footer{margin-top:30px;padding-top:12px;border-top:1px solid #ccd5e2;color:#65758b;font-size:10px}
.print-actions{text-align:center;margin:20px auto}
.print-button{background:#1758ad;color:white;border:0;padding:11px 22px;border-radius:6px;font-size:14px;cursor:pointer}
@page{size:A4;margin:15mm}
@media print{
 body{padding:0;font-size:11px}
 .report{max-width:none}
 .print-actions{display:none}
 h3{break-after:avoid}
 table,.summary,.content-block{break-inside:avoid}
}
</style>
</head>
<body>
<div class="report">
    <div class="header">
        <h1>MAINT.AI</h1>
        <p>MAINTENANCE INTELLIGENCE</p>
        <h2>RAPPORT DE DIAGNOSTIC</h2>
        <p>Référence : ${esc(r.id)}</p>
    </div>

    <h3>1. Identification</h3>
    <table>
        <tr><td><b>Moteur</b></td><td>${esc(r.motor)}</td></tr>
        <tr><td><b>Date</b></td><td>${new Date(r.created).toLocaleString('fr-FR')}</td></tr>
        <tr><td><b>Opérateur</b></td><td>${esc(r.operator)}</td></tr>
        <tr><td><b>Source</b></td><td>${esc(r.source)}</td></tr>
    </table>

    <h3>2. Synthèse du diagnostic</h3>
    <div class="summary">
        <p><b>État global :</b> ${esc(r.level)}</p>
        <p><b>Score de risque :</b> ${r.score !== '' ? esc(r.score)+'/100' : 'Non renseigné'}</p>
        <p><b>Courant moyen :</b> ${esc(r.current || 'Non renseigné')} A</p>
        <p><b>Taux de charge :</b> ${esc(r.load || 'Non renseigné')} %</p>
        <p><b>Déséquilibre de courant :</b> ${esc(r.imbalance || 'Non renseigné')} %</p>
    </div>

    <h3>3. Tableau récapitulatif des mesures</h3>
    <table>
        <thead><tr><th>Paramètre</th><th>Valeur mesurée</th><th>Unité</th></tr></thead>
        <tbody>
            ${lignes.map(l=>`<tr><td>${esc(l[0])}</td><td>${esc(l[1])}</td><td>${esc(l[2])}</td></tr>`).join('')}
        </tbody>
    </table>

    <h3>4. Anomalies détectées</h3>
    <div class="content-block">${esc(asText(r.anomalies))}</div>

    <h3>5. Causes possibles</h3>
    <div class="content-block">${esc(asText(r.causes))}</div>

    <h3>6. Analyse de MAINT.AI</h3>
    <div class="content-block ai-block">${esc(asText(r.summary))}</div>

    <h3>7. Contrôles recommandés</h3>
    <div class="content-block">${esc(asText(r.checks))}</div>

    <h3>8. Actions recommandées</h3>
    <div class="content-block">${esc(asText(r.actions))}</div>

    <h3>9. Observations du technicien</h3>
    <div class="content-block">${esc(m.observations || 'Aucune observation renseignée.')}</div>

    <div class="footer">
        Rapport généré par MAINT.AI — Maintenance Intelligence.<br>
        Diagnostic préliminaire d'aide à la décision. Les hypothèses doivent être vérifiées par un technicien qualifié.
        Les seuils doivent être adaptés aux caractéristiques du moteur et à ses conditions d'exploitation.
    </div>
</div>

<div class="print-actions">
    <button class="print-button" onclick="window.print()">Imprimer / Enregistrer en PDF</button>
</div>
</body>
</html>`;

    rapportWindow.document.open();
    rapportWindow.document.write(contenu);
    rapportWindow.document.close();

    rapportWindow.onload = function() {
        rapportWindow.focus();
        rapportWindow.print();
    };
}
</script>

<script>
// Auth MAINT.AI
const SUPABASE_URL = 'https://pckmyzcedbxcoickfpdp.supabase.co';
const SUPABASE_PUBLISHABLE_KEY = 'sb_publishable_OT_jqJ56U0Qv30Ic6TiYmQ_CAq7Fo93';
const authMessage = document.getElementById('authMessage');
const loginForm = document.getElementById('loginForm');
const loginButton = document.getElementById('loginButton');
const passwordInput = document.getElementById('loginPassword');
const passwordToggle = document.getElementById('togglePassword');

passwordToggle.addEventListener('click', () => {
  const reveal = passwordInput.type === 'password';
  passwordInput.type = reveal ? 'text' : 'password';
  passwordToggle.setAttribute('aria-pressed', String(reveal));
  passwordToggle.setAttribute('aria-label', reveal ? 'Masquer le mot de passe' : 'Afficher le mot de passe');
  passwordToggle.title = reveal ? 'Masquer le mot de passe' : 'Afficher le mot de passe';
  document.getElementById('eyeIcon').innerHTML = reveal
    ? '<path d="M3 3l18 18"/><path d="M10.6 10.6a2 2 0 0 0 2.8 2.8"/><path d="M9.9 5.2A10.8 10.8 0 0 1 12 5c6.4 0 10 7 10 7a15.7 15.7 0 0 1-3.1 3.9"/><path d="M6.2 6.2C3.5 8 2 12 2 12s3.6 7 10 7a10.5 10.5 0 0 0 4-.8"/>'
    : '<path d="M2 12s3.6-7 10-7 10 7 10 7-3.6 7-10 7-10-7-10-7Z"/><circle cx="12" cy="12" r="3"/>';
});

let supabaseClient = null;
let authenticatedProfile = null;
let authReady = false;

const rolePages = {
 admin: ['dashboard','motors','diagnostic','history','reports','settings'],
 technicien: ['dashboard','motors','diagnostic','history','reports'],
 consultation: ['dashboard','motors','history','reports']
};

function authNotice(message, type='') {
  authMessage.textContent = message;
  authMessage.className = 'auth-message ' + type;
}

function loadSupabaseLibrary() {
  return new Promise((resolve, reject) => {
    if (window.supabase?.createClient) return resolve();
    const script = document.createElement('script');
    script.src = 'https://cdn.jsdelivr.net/npm/@supabase/supabase-js@2';
    script.onload = () => window.supabase?.createClient ? resolve() : reject(new Error('La bibliothèque Supabase est chargée, mais createClient est indisponible.'));
    script.onerror = () => reject(new Error('Impossible de charger Supabase. Vérifie ta connexion Internet ou essaie en ouvrant le fichier avec un navigateur connecté.'));
    document.head.appendChild(script);
  });
}

async function initSupabase() {
  try {
    await loadSupabaseLibrary();
    supabaseClient = window.supabase.createClient(SUPABASE_URL, SUPABASE_PUBLISHABLE_KEY);
    authReady = true;
    authNotice('Service de connexion prêt. Accès réservé aux utilisateurs autorisés.');
    const { data: { session }, error } = await supabaseClient.auth.getSession();
    if (error) throw error;
    if (session) await loadAuthenticatedUser(session);
    supabaseClient.auth.onAuthStateChange((_event, sessionNow) => {
      if (sessionNow) setTimeout(() => loadAuthenticatedUser(sessionNow), 0);
      else {
        authenticatedProfile = null;
        document.body.classList.remove('authenticated');
      }
    });
  } catch (error) {
    authReady = false;
    authNotice('Initialisation impossible : ' + (error.message || error), 'error');
  }
}

function applyRoleAccess(role) {
  const allowed = rolePages[role] || [];
  document.querySelectorAll('.nav button[data-page]').forEach(button => {
    button.style.display = allowed.includes(button.dataset.page) ? '' : 'none';
  });
  document.querySelectorAll('button[onclick]').forEach(button => {
    const match = (button.getAttribute('onclick') || '').match(/showPage\('([^']+)'\)/);
    if (match && !allowed.includes(match[1])) button.style.display = 'none';
  });
  const activePage = document.querySelector('.page.active')?.id?.replace('page-','');
  if (!allowed.includes(activePage)) showPage('dashboard');
}

async function loadAuthenticatedUser(session) {
  if (!session || !supabaseClient) return;
  try {
    const { data: { user }, error: userError } = await supabaseClient.auth.getUser();
    if (userError) throw userError;
    if (!user) throw new Error('Utilisateur Supabase introuvable.');
    const { data: profile, error: profileError } = await supabaseClient
      .from('profiles').select('id,full_name,role').eq('id', user.id).single();
    if (profileError) throw new Error('Connexion réussie, mais lecture du profil impossible : ' + profileError.message);
    if (!profile || !['admin','technicien','consultation'].includes(profile.role))
      throw new Error('Aucun profil MAINT.AI valide associé à ce compte.');
    authenticatedProfile = { ...profile, email: user.email };
    document.getElementById('currentUserEmail').textContent = profile.full_name || user.email || 'Utilisateur';
    document.getElementById('currentUserRole').textContent = profile.role;
    document.body.classList.add('authenticated');
    applyRoleAccess(profile.role);
  } catch (error) {
    document.body.classList.remove('authenticated');
    authNotice(error.message || 'Erreur lors du chargement du profil.', 'error');
  }
}

loginForm.addEventListener('submit', async event => {
  event.preventDefault();
  event.stopPropagation();
  if (!authReady || !supabaseClient) {
    authNotice('Le service de connexion n’est pas encore prêt. Actualise la page et vérifie ta connexion Internet.', 'error');
    return;
  }
  loginButton.disabled = true;
  loginButton.textContent = 'Connexion…';
  authNotice('Vérification des identifiants…');
  const email = document.getElementById('loginEmail').value.trim();
  const password = document.getElementById('loginPassword').value;
  try {
    const { data, error } = await supabaseClient.auth.signInWithPassword({ email, password });
    if (error) throw error;
    if (!data.session) throw new Error('Supabase n’a pas renvoyé de session. Vérifie la confirmation de ton adresse e-mail.');
    authNotice('Identifiants acceptés. Vérification du profil MAINT.AI…', 'success');
    await loadAuthenticatedUser(data.session);
  } catch (error) {
    authNotice('Connexion impossible : ' + (error.message || error), 'error');
  } finally {
    loginButton.disabled = false;
    loginButton.textContent = 'Se connecter';
  }
});

document.getElementById('logoutButton').addEventListener('click', async () => {
  if (supabaseClient) await supabaseClient.auth.signOut();
  authenticatedProfile = null;
  document.body.classList.remove('authenticated');
  authNotice('Vous êtes déconnecté.');
});

initSupabase();
</script>
</body>
</html>
