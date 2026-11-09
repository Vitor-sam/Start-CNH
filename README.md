```
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>StartCNH — Simulados Teóricos</title>
<style>
:root{
  --primary:#1358d8;--primary-dark:#0d3fa3;--bg:#f4f7fb;--card:#fff;
  --text:#172033;--muted:#667085;--success:#16834b;--danger:#d92d20;
  --border:#e4e7ec;--shadow:0 10px 30px rgba(16,24,40,.08);--radius:18px
}
*{box-sizing:border-box}
body{margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;background:var(--bg);color:var(--text)}
button,input,select,textarea{font:inherit}
button{cursor:pointer}
.hidden{display:none!important}
.app{min-height:100vh}
header{background:#fff;border-bottom:1px solid var(--border);position:sticky;top:0;z-index:10}
.nav{max-width:1180px;margin:auto;padding:14px 20px;display:flex;align-items:center;justify-content:space-between;gap:16px}
.brand{font-weight:900;font-size:21px;color:var(--primary)}
.brand span{color:var(--text)}
.nav-actions{display:flex;align-items:center;gap:8px}
.container{max-width:1180px;margin:auto;padding:28px 20px 50px}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.card{background:var(--card);border:1px solid var(--border);border-radius:var(--radius);padding:24px;box-shadow:var(--shadow)}
.hero{padding:34px;margin-bottom:22px;background:linear-gradient(135deg,#0f4fc4,#2574ee);color:white;border-radius:24px;box-shadow:var(--shadow)}
.hero h1{margin:0 0 10px;font-size:clamp(28px,4vw,44px)}
.hero p{margin:0;opacity:.9;max-width:760px}
h2,h3{margin-top:0}
.muted{color:var(--muted)}
.btn{border:0;border-radius:12px;padding:11px 16px;font-weight:750;transition:.15s}
.btn:hover{transform:translateY(-1px)}
.btn-primary{background:var(--primary);color:#fff}
.btn-primary:hover{background:var(--primary-dark)}
.btn-secondary{background:#eef4ff;color:var(--primary)}
.btn-danger{background:#fff0ef;color:var(--danger)}
.btn-ghost{background:transparent;color:var(--muted)}
.level{min-height:210px;display:flex;flex-direction:column}
.level .icon{font-size:36px}
.level .spacer{flex:1}
.badge{display:inline-flex;align-items:center;padding:5px 9px;border-radius:999px;background:#eef4ff;color:var(--primary);font-size:12px;font-weight:800}
.form{max-width:480px;margin:35px auto}
.field{margin-bottom:15px}
label{display:block;font-weight:700;margin-bottom:7px}
input,select,textarea{width:100%;padding:12px 13px;border:1px solid #d0d5dd;border-radius:11px;background:#fff;outline:none}
input:focus,select:focus,textarea:focus{border-color:var(--primary);box-shadow:0 0 0 3px #dbe8ff}
.row{display:flex;gap:10px;align-items:center;justify-content:space-between;flex-wrap:wrap}
.question-head{display:flex;justify-content:space-between;gap:15px;align-items:center;margin-bottom:20px}
.timer-pill{display:inline-flex;align-items:center;gap:7px;padding:7px 11px;border:1px solid #e4e7ec;border-radius:999px;background:#f8fafc;color:#000;font-size:16px;font-weight:700;font-variant-numeric:tabular-nums;white-space:nowrap}
.timer-pill .timer-dot{width:6px;height:6px;border-radius:50%;background:#98a2b3}
.timer-pill.timer-warning{color:#000;background:#fffaeb;border-color:#fedf89}
.timer-pill.timer-warning .timer-dot{background:#f79009}
.timer-pill.timer-expired{color:#000;background:#fef3f2;border-color:#fecdca}
.timer-pill.timer-expired .timer-dot{background:#f04438}
.progress{height:9px;background:#e9eef6;border-radius:99px;overflow:hidden;margin:10px 0 22px}
.progress>div{height:100%;background:var(--primary);transition:.25s}
.options{display:grid;gap:12px}
.option{display:flex;gap:12px;align-items:flex-start;border:1px solid var(--border);border-radius:14px;padding:15px;text-align:left;background:#fff;width:100%}
.option:hover{border-color:#a8c3ff;background:#f8fbff}
.option.selected{border-color:var(--primary);background:#edf4ff}
.option input{width:auto;margin-top:3px}
.footer-actions{display:flex;justify-content:space-between;gap:10px;margin-top:22px}
.result{border-left:6px solid var(--success)}
.score{font-size:46px;font-weight:900}
.result-metrics{display:grid;grid-template-columns:1fr 1fr;gap:18px;margin:22px 0;padding:22px;border:1px solid #b7f0e5;border-radius:16px;background:#f4fbf9}
.result-metric{display:flex;align-items:center;justify-content:center;gap:18px;padding:10px;text-align:left}
.result-metric+.result-metric{border-left:1px solid #d0d5dd}
.result-metric-label{font-size:20px;font-weight:800;color:#000;margin-bottom:6px}
.result-metric-value{font-size:48px;line-height:1.1;font-weight:900;color:#000;font-variant-numeric:tabular-nums}
.result-metric .score{color:var(--success)}
.result-stopwatch{width:58px;height:58px;flex-shrink:0;color:#000}
@media(max-width:600px){.result-metrics{grid-template-columns:1fr}.result-metric+.result-metric{border-left:0;border-top:1px solid #d0d5dd}.result-metric-value{font-size:40px}.result-metric-label{font-size:18px}}
.good{color:var(--success)}.bad{color:var(--danger)}
.history-table{width:100%;border-collapse:collapse}
.history-table th,.history-table td{padding:12px;border-bottom:1px solid var(--border);text-align:left}
.admin-list{display:grid;gap:12px}
.admin-item{border:1px solid var(--border);border-radius:14px;padding:14px;background:#fff}
.toast{position:fixed;right:20px;bottom:20px;background:#172033;color:white;padding:13px 16px;border-radius:12px;box-shadow:var(--shadow);z-index:100}
.small{font-size:13px}
.empty{padding:30px;text-align:center;color:var(--muted)}
@media(max-width:800px){.grid{grid-template-columns:1fr}.nav{align-items:flex-start}.nav-actions{flex-wrap:wrap}.container{padding:20px 14px 40px}.card{padding:19px}.hero{padding:25px}}
</style>

<link rel="manifest" href="./manifest.webmanifest">
<meta name="theme-color" content="#1358d8">
<meta name="mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="default">
<link rel="icon" href="./icon.svg" type="image/svg+xml">

</head>
<body>
<div id="app" class="app"></div>
<div id="toast" class="toast hidden"></div>

<script>
const STORAGE = {
  users:'simuladetran_users',
  questions:'simuladetran_questions',
  history:'simuladetran_history',
  session:'simuladetran_session',
  quizState:'simuladetran_quiz_state' // Armazenamento do estado do quiz e cronômetro
};

const seedQuestions = [
  {id:'q1',level:'basico',topic:'Sinalização',text:'Qual é a finalidade principal das placas de regulamentação?',options:['Indicar pontos turísticos.','Informar obrigações, proibições ou restrições aos usuários da via.','Indicar somente serviços mecânicos.','Mostrar nomes de cidades.'],answer:1},
  {id:'q2',level:'basico',topic:'Direção defensiva',text:'Uma atitude adequada de direção defensiva é:',options:['Manter atenção às condições da via e antecipar situações de risco.','Acelerar sempre que o trânsito ficar lento.','Usar o celular quando o veículo estiver em movimento.','Ignorar a sinalização quando não houver fiscalização.'],answer:0},
  {id:'q3',level:'basico',topic:'Segurança',text:'Antes de iniciar uma viagem, é recomendável:',options:['Verificar as condições básicas do veículo e planejar o trajeto.','Desligar os equipamentos de segurança.','Reduzir a atenção para chegar mais rápido.','Evitar observar as condições do trânsito.'],answer:0},
  {id:'q4',level:'intermediario',topic:'Sinalização',text:'Ao encontrar sinalização que determina parada obrigatória, o condutor deve:',options:['Parar somente se houver outro veículo.','Respeitar a determinação e realizar a parada de forma segura.','Acelerar para liberar a via.','Parar apenas em rodovias.'],answer:1},
  {id:'q5',level:'intermediario',topic:'Direção defensiva',text:'Em condições adversas de visibilidade, uma conduta preventiva é:',options:['Aumentar a velocidade.','Reduzir a velocidade e ampliar a atenção.','Apagar os dispositivos de iluminação.','Dirigir mais próximo do veículo da frente.'],answer:1},
  {id:'q6',level:'intermediario',topic:'Meio ambiente',text:'Uma prática relacionada à condução econômica e à redução de impactos ambientais é:',options:['Manter manutenção adequada do veículo.','Acelerar e frear bruscamente com frequência.','Ignorar falhas mecânicas.','Manter o motor acelerado sem necessidade.'],answer:0},
  {id:'q7',level:'hard',topic:'Legislação',text:'Em um sistema de simulados, por que é importante manter registrada a resposta escolhida antes de avançar?',options:['Para permitir a correção e a composição do resultado ao final.','Para alterar automaticamente a questão.','Para impedir a consulta ao histórico.','Para remover a questão do banco.'],answer:0},
  {id:'q8',level:'hard',topic:'Direção defensiva',text:'Em uma situação de risco inesperada, a condução preventiva prioriza:',options:['Reação impulsiva e aumento da velocidade.','Avaliação do cenário, controle do veículo e redução segura do risco.','Uso constante da buzina como única medida.','Desconsideração dos demais usuários.'],answer:1},
  {id:'q9',level:'hard',topic:'Primeiros socorros',text:'Em uma ocorrência de trânsito com pessoa ferida, uma atitude geral de segurança é:',options:['Avaliar o local e acionar ajuda especializada quando necessário.','Movimentar imediatamente toda pessoa ferida, independentemente da situação.','Oferecer medicamentos por conta própria.','Deixar o local sem comunicar ninguém.'],answer:0},

   {id:'q10',level:'basico',topic:'Legislação',text:'O uso do cinto de segurança é obrigatório:',options:['Somente para o motorista.','Para todos os ocupantes do veículo, conforme as regras de trânsito.','Apenas em rodovias.','Somente no banco dianteiro.'],answer:1},
   {id:'q11',level:'basico',topic:'Sinalização',text:'A luz amarela do semáforo indica que o condutor deve:',options:['Acelerar para atravessar.','Parar, se puder fazê-lo com segurança.','Ignorar o semáforo.','Dar marcha à ré.'],answer:1},
   {id:'q12',level:'intermediario',topic:'Direção defensiva',text:'Manter distância segura do veículo à frente ajuda a:',options:['Reduzir o tempo de reação.','Evitar qualquer necessidade de frear.','Ter espaço para reagir e parar com segurança.','Permitir dirigir em velocidade maior.'],answer:2},
   {id:'q13',level:'intermediario',topic:'Legislação',text:'Ao se aproximar de uma faixa de pedestres com pessoas atravessando, o condutor deve:',options:['Aumentar a velocidade.','Buzinar para que atravessem mais rápido.','Parar e dar preferência aos pedestres.','Desviar pela contramão.'],answer:2},
   {id:'q14',level:'intermediario',topic:'Segurança',text:'O capacete de segurança para motociclistas deve ser utilizado:',options:['Apenas em vias de alta velocidade.','Pelo condutor e passageiro, conforme as normas.','Somente durante o dia.','Apenas por quem não tem experiência.'],answer:1},
   {id:'q15',level:'intermediario',topic:'Meio ambiente',text:'A fumaça excessiva emitida pelo veículo pode indicar:',options:['Funcionamento sempre normal.','Possível problema de manutenção ou regulagem.','Economia de combustível.','Que os pneus estão calibrados.'],answer:1},
   {id:'q16',level:'intermediario',topic:'Primeiros socorros',text:'Ao presenciar um sinistro de trânsito, antes de prestar auxílio, é importante:',options:['Proteger o local para evitar novos acidentes, sem se colocar em risco.','Retirar todos os veículos imediatamente.','Oferecer alimentos às pessoas envolvidas.','Mover as pessoas feridas sem avaliar a situação.'],answer:0},
   {id:'q17',level:'intermediario',topic:'Sinalização',text:'A placa de advertência tem como função principal:',options:['Informar condições ou situações que exigem atenção.','Autorizar estacionamento em qualquer local.','Indicar apenas serviços turísticos.','Substituir as ordens dos agentes de trânsito.'],answer:0},
   {id:'q18',level:'intermediario',topic:'Legislação',text:'Antes de mudar de faixa, o condutor deve:',options:['Sinalizar e verificar se a manobra pode ser feita com segurança.','Mudar rapidamente sem olhar os espelhos.','Usar a buzina como único aviso.','Frear bruscamente no meio da via.'],answer:0},
   {id:'q19',level:'intermediario',topic:'Direção defensiva',text:'Em pista molhada, a distância necessária para parar o veículo tende a:',options:['Diminuir sempre.','Permanecer idêntica em qualquer condição.','Aumentar.','Ser independente da velocidade.'],answer:2},
   {id:'q20',level:'intermediario',topic:'Segurança',text:'Transportar crianças em veículos deve respeitar:',options:['Apenas a vontade da criança.','As regras de idade, altura e dispositivos de retenção aplicáveis.','Somente o banco escolhido pelo motorista.','A dispensa de qualquer equipamento em trajetos curtos.'],answer:1},
   {id:'q21',level:'hard',topic:'Legislação',text:'Ao encontrar um cruzamento sem sinalização, a conduta correta é:',options:['Acelerar para passar primeiro.','Reduzir a velocidade e observar as regras de preferência.','Parar somente se houver fiscalização.','Presumir que a via mais larga sempre tem preferência.'],answer:1},
   {id:'q22',level:'hard',topic:'Direção defensiva',text:'Ao dirigir sob chuva intensa e baixa visibilidade, é mais seguro:',options:['Manter a velocidade máxima permitida.','Aumentar a distância do veículo à frente e adequar a velocidade.','Usar o pisca-alerta continuamente enquanto estiver em movimento.','Seguir de perto outro veículo como guia.'],answer:1},
   {id:'q23',level:'hard',topic:'Legislação',text:'A ultrapassagem deve ser evitada quando:',options:['A sinalização ou as condições da via não oferecerem segurança.','A pista estiver livre e a manobra for permitida.','O veículo da frente estiver em velocidade reduzida e houver segurança.','Houver visibilidade adequada e sinalização permitindo.'],answer:0},
   {id:'q24',level:'hard',topic:'Sinalização',text:'Uma linha amarela contínua separando fluxos opostos indica, em regra:',options:['Permissão livre para ultrapassar.','Proibição de transpor a linha para ultrapassagem.','Área exclusiva para estacionamento.','Faixa destinada a pedestres.'],answer:1},
   {id:'q25',level:'hard',topic:'Primeiros socorros',text:'Em um atendimento inicial a uma ocorrência de trânsito, deve-se:',options:['Acionar o serviço de emergência e seguir suas orientações.','Dar água a toda vítima imediatamente.','Retirar o capacete de qualquer motociclista ferido.','Movimentar a vítima para liberar a pista sem avaliar riscos.'],answer:0},
   {id:'q26',level:'hard',topic:'Meio ambiente',text:'A manutenção preventiva do veículo contribui para:',options:['Aumentar a emissão de poluentes.','Reduzir falhas, melhorar a eficiência e diminuir impactos ambientais.','Dispensar inspeções dos pneus.','Eliminar a necessidade de condução econômica.'],answer:1},
   {id:'q27',level:'hard',topic:'Legislação',text:'Ao ouvir a sirene e observar a aproximação de veículo de emergência em serviço de urgência, o condutor deve:',options:['Disputar espaço para não perder sua posição.','Facilitar a passagem, deslocando-se com segurança.','Parar imediatamente em qualquer ponto da pista.','Seguir o veículo de emergência de perto.'],answer:1},
   {id:'q28',level:'hard',topic:'Direção defensiva',text:'O ponto cego de um veículo é:',options:['Uma área que não é vista diretamente pelos espelhos ou pelo campo visual do condutor.','Uma falha obrigatória no sistema de iluminação.','O espaço de frenagem em pista seca.','Uma área exclusiva para pedestres.'],answer:0},
   {id:'q29',level:'hard',topic:'Segurança',text:'Pneus com pressão inadequada podem:',options:['Comprometer a estabilidade e aumentar o desgaste.','Garantir menor consumo em qualquer situação.','Eliminar o risco de aquaplanagem.','Melhorar sempre a frenagem.'],answer:0},
   {id:'q30',level:'hard',topic:'Legislação',text:'A condução de veículo exige que o motorista:',options:['Adapte sua conduta às condições de trânsito, clima e via.','Mantenha sempre a mesma velocidade.','Considere apenas as próprias necessidades.','Ignore riscos quando conhece o trajeto.'],answer:0},
   {id:'q31',level:'hard',topic:'Sinalização',text:'Diante de um agente de trânsito que determina parada, mesmo com semáforo verde, o condutor deve:',options:['Obedecer à indicação do agente.','Seguir o semáforo sem considerar o agente.','Aguardar outro veículo passar primeiro.','Buzinar e continuar.'],answer:0},
   {id:'q32',level:'hard',topic:'Direção defensiva',text:'A aquaplanagem ocorre quando:',options:['Os pneus perdem contato adequado com o pavimento por causa de uma camada de água.','O motor superaquece em uma subida.','O veículo trafega em estrada de terra seca.','O sistema de freios é acionado em baixa velocidade.'],answer:0},
   {id:'q33',level:'hard',topic:'Primeiros socorros',text:'Se houver risco de incêndio ou outro perigo imediato no local de um sinistro, a prioridade é:',options:['Preservar a segurança das pessoas e acionar os serviços de emergência.','Registrar fotos antes de qualquer providência.','Reunir curiosos perto do veículo.','Ignorar o perigo até a chegada de outros motoristas.'],answer:0},
   {id:'q34',level:'hard',topic:'Meio ambiente',text:'Uma atitude que favorece a redução do consumo de combustível é:',options:['Acelerar e frear bruscamente.','Manter velocidade regular e realizar manutenção adequada.','Deixar o motor ligado sem necessidade.','Rodar com pneus descalibrados.'],answer:1},
   {id:'q35',level:'hard',topic:'Legislação',text:'Estacionar em local onde a sinalização proíbe essa prática pode:',options:['Gerar medida administrativa e penalidade previstas na legislação.','Ser permitido quando o motorista permanecer no veículo.','Ser permitido durante qualquer horário.','Não produzir consequência se for por pouco tempo.'],answer:0},
   {id:'q36',level:'hard',topic:'Segurança',text:'O uso do telefone celular pelo condutor durante a condução:',options:['Desvia a atenção e aumenta o risco de sinistros.','É seguro sempre que o trânsito estiver lento.','Não interfere na capacidade de reação.','É recomendado em vias conhecidas.'],answer:0},
   {id:'q37',level:'hard',topic:'Direção defensiva',text:'Ao perceber um veículo vindo em sentido contrário na sua faixa, o condutor deve:',options:['Manter a calma, reduzir a velocidade e buscar uma ação segura para evitar a colisão.','Acelerar em direção ao veículo.','Fechar os olhos e frear bruscamente sem observar o entorno.','Desviar para qualquer lado sem avaliar o espaço.'],answer:0}
];

function get(key,fallback){
  try{return JSON.parse(localStorage.getItem(key)) ?? fallback}catch(e){return fallback}
}
function set(key,value){localStorage.setItem(key,JSON.stringify(value))}
function uid(){return Date.now().toString(36)+Math.random().toString(36).slice(2,8)}
function escapeHTML(s){return String(s).replace(/[&<>"']/g,m=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#039;'}[m]))}
function toast(msg){
  const el=document.getElementById('toast');el.textContent=msg;el.classList.remove('hidden');
  clearTimeout(window.toastTimer);window.toastTimer=setTimeout(()=>el.classList.add('hidden'),2600);
}
function init(){
  // Atualiza o banco inicial sem apagar questões cadastradas pelo administrador.
  const storedQuestions=get(STORAGE.questions,[]);
  const knownIds=new Set(storedQuestions.map(q=>q.id));
  const missingSeedQuestions=seedQuestions.filter(q=>!knownIds.has(q.id));
  if(!localStorage.getItem(STORAGE.questions)) set(STORAGE.questions,seedQuestions);
  else if(missingSeedQuestions.length) set(STORAGE.questions,[...storedQuestions,...missingSeedQuestions]);
  // Recupera o estado do quiz do localStorage ao carregar a página
  quizState = get(STORAGE.quizState, null);
  render();
  if(quizState && window.route?.page === 'quiz'){
    startQuizTimer();
  }
}
function session(){return get(STORAGE.session,null)}
function currentUser(){
  const s=session(); if(!s)return null;
  return get(STORAGE.users,[]).find(u=>u.id===s.userId)||null;
}
function saveSession(user){set(STORAGE.session,{userId:user.id})}
function logout(){localStorage.removeItem(STORAGE.session);render();toast('Sessão encerrada.')}
function header(){
  const u=currentUser();
  return `<header><div class="nav">
    <div class="brand">Start<span>CNH</span></div>
    <div class="nav-actions">
      ${u?`<span class="small muted">Olá, ${escapeHTML(u.name)}</span>
      <button class="btn btn-secondary" onclick="go('home')">Início</button>
      <button class="btn btn-secondary" onclick="go('history')">Histórico</button>
      ${u.admin?`<button class="btn btn-secondary" onclick="go('admin')">Administração</button>`:''}
      <button class="btn btn-ghost" onclick="logout()">Sair</button>`
      :`<button class="btn btn-secondary" onclick="go('login')">Entrar</button>
      <button class="btn btn-primary" onclick="go('register')">Criar conta</button>`}
    </div>
  </div></header>`;
}
function go(page, data=null){
  window.route={page,data}; 
  render();
  if(page === 'quiz' && quizState) {
    startQuizTimer();
  }
}
function render(){
  const root=document.getElementById('app');
  root.innerHTML=header()+`<main class="container" id="view"></main>`;
  const page=window.route?.page|| (currentUser()?'home':'login');
  const view=document.getElementById('view');
  if(page==='login') return view.innerHTML=loginView();
  if(page==='register') return view.innerHTML=registerView();
  if(page==='home') return view.innerHTML=homeView();
  if(page==='quiz') return view.innerHTML=quizView();
  if(page==='result') return view.innerHTML=resultView();
  if(page==='history') return view.innerHTML=historyView();
  if(page==='admin') return view.innerHTML=adminView();
  view.innerHTML=homeView();
}
function loginView(){
 return `<div class="card form">
   <h2>Entrar</h2><p class="muted">Acesse seus simulados e histórico.</p>
   <form onsubmit="login(event)">
    <div class="field"><label>E-mail</label><input id="email" type="email" required></div>
    <div class="field"><label>Senha</label><input id="password" type="password" required></div>
    <button class="btn btn-primary" style="width:100%">Entrar</button>
   </form>
   <p class="small muted">Não possui conta? <button class="btn btn-ghost" onclick="go('register')">Cadastre-se</button></p>
 </div>`;
}
function registerView(){
 return `<div class="card form">
   <h2>Criar conta</h2><p class="muted">Cadastre nome, e-mail e senha para começar.</p>
   <form onsubmit="register(event)">
    <div class="field"><label>Nome</label><input id="name" required maxlength="80"></div>
    <div class="field"><label>E-mail</label><input id="email" type="email" required></div>
    <div class="field"><label>Senha</label><input id="password" type="password" minlength="6" required></div>
    <button class="btn btn-primary" style="width:100%">Cadastrar</button>
   </form>
 </div>`;
}
function homeView(){
 const u=currentUser();
 if(!u)return loginView();
 return `<section class="hero">
   <h1>Pratique para a prova teórica</h1>
   <p>Escolha um nível, responda às questões e acompanhe seu desempenho.</p>
 </section>
 <div class="row" style="margin-bottom:15px"><h2>Escolha o nível</h2><span class="badge">Simulados</span></div>
 <div class="grid">
  ${levelCard('basico','🟢','Básico','Questões introdutórias para revisar conceitos fundamentais.')}
  ${levelCard('intermediario','🟡','Intermediário','Questões para consolidar conhecimentos e atenção aos detalhes.')}
  ${levelCard('hard','🔴','Hard','Questões com situações e conceitos mais desafiadores.')}
 </div>
 <div class="card" style="margin-top:20px">
  <div class="row"><div><h3>Seu histórico</h3><p class="muted">Consulte seus resultados anteriores.</p></div><button class="btn btn-secondary" onclick="go('history')">Ver histórico</button></div>
 </div>`;
}
function levelCard(level,icon,title,desc){
 return `<article class="card level"><div class="icon">${icon}</div><h3>${title}</h3><p class="muted">${desc}</p><div class="spacer"></div><button class="btn btn-primary" onclick="startQuiz('${level}')">Iniciar ${title}</button></article>`;
}

let quizState=null;
let quizTimerInterval=null;

function startQuiz(level){
 const questionCounts={basico:5,intermediario:10,hard:20};
 const targetCount=questionCounts[level]||5;
 const all=get(STORAGE.questions,seedQuestions).filter(q=>q.level===level);
 if(all.length<targetCount){toast(`Este nível precisa de ${targetCount} questões cadastradas. Atualmente há ${all.length}.`);return}
 const shuffled=[...all].sort(()=>Math.random()-.5).slice(0,targetCount);
 
 // Cria um novo estado com prazo de 30 minutos a partir de agora e salva no localStorage
 quizState={
   id:uid(),
   level,
   questions:shuffled,
   index:0,
   answers:{},
   startedAt:Date.now(),
   deadline:Date.now()+30*60*1000
 };
 set(STORAGE.quizState, quizState);
 go('quiz');
}

function formatRemainingTime(deadline){
 const remaining=Math.max(0,Math.ceil((deadline-Date.now())/1000));
 return String(Math.floor(remaining/60)).padStart(2,'0')+':'+String(remaining%60).padStart(2,'0');
}

function quizView(){
 if(!quizState)return homeView();
 const q=quizState.questions[quizState.index], total=quizState.questions.length;
 const chosen=quizState.answers[q.id];
 return `<div class="card">
   <div class="question-head"><div><span class="badge">${escapeHTML(q.topic)} · ${labelLevel(quizState.level)}</span><h2 style="margin:10px 0 0">Questão ${quizState.index+1}</h2></div><div style="display:flex;align-items:center;gap:12px"><div id="quizTimer" class="timer-pill" role="timer" aria-live="off"><span class="timer-dot"></span><span id="quizTimerText">${formatRemainingTime(quizState.deadline)}</span></div><strong>${quizState.index+1}/${total}</strong></div></div>
   <div class="progress"><div style="width:${((quizState.index+1)/total)*100}%"></div></div>
   <h3>${escapeHTML(q.text)}</h3>
   <div class="options">${q.options.map((o,i)=>`
    <button type="button" class="option ${chosen===i?'selected':''}" onclick="answer(${i})">
      <input type="radio" ${chosen===i?'checked':''} aria-label="Alternativa ${String.fromCharCode(65+i)}">
      <span><strong>${String.fromCharCode(65+i)})</strong>${escapeHTML(o)}</span>
    </button>`).join('')}</div>
   <div class="footer-actions">
    <button class="btn btn-secondary" onclick="prevQuestion()" ${quizState.index===0?'disabled':''}>Anterior</button>
    ${quizState.index<total-1
      ?`<button class="btn btn-primary" onclick="nextQuestion()">Próxima</button>`
      :`<button class="btn btn-primary" onclick="finishQuiz()">Finalizar simulado</button>`}
   </div>
   <p class="small muted">A resposta é registrada automaticamente nesta sessão.</p>
 </div>`;
}

function startQuizTimer(){
  clearInterval(quizTimerInterval);
  updateQuizTimer();
  quizTimerInterval=setInterval(updateQuizTimer,1000);
}

function updateQuizTimer(){
  if(!quizState || window.route?.page!=='quiz'){clearInterval(quizTimerInterval);return}
  const remaining=Math.max(0,Math.ceil((quizState.deadline-Date.now())/1000));
  const timer=document.getElementById('quizTimer');
  const text=document.getElementById('quizTimerText');
  if(text)text.textContent=formatRemainingTime(quizState.deadline);
  if(timer){
    timer.classList.toggle('timer-warning',remaining<=300&&remaining>0);
    timer.classList.toggle('timer-expired',remaining===0);
  }
  if(remaining===0){
    clearInterval(quizTimerInterval);
    toast('Tempo esgotado. O simulado será finalizado.');
    finishQuiz(true);
  }
}

function answer(i){
  const q=quizState.questions[quizState.index];
  quizState.answers[q.id]=i;
  set(STORAGE.quizState, quizState); // Salva a resposta atualizada
  render();
}

function nextQuestion(){
 const q=quizState.questions[quizState.index];
 if(quizState.answers[q.id]===undefined){toast('Selecione uma alternativa antes de avançar.');return}
 quizState.index++;
 set(STORAGE.quizState, quizState); // Salva o novo índice da questão
 render();
}

function prevQuestion(){
  if(quizState.index>0){
    quizState.index--;
    set(STORAGE.quizState, quizState); // Salva o novo índice da questão
    render();
  }
}

function finishQuiz(timeExpired=false){
 if(!quizState)return;
 if(!timeExpired){
  const unanswered=quizState.questions.filter(q=>quizState.answers[q.id]===undefined).length;
  if(unanswered && !confirm(`Há ${unanswered} questão(ões) sem resposta. Deseja finalizar mesmo assim?`))return;
 }
 clearInterval(quizTimerInterval);
 const correct=quizState.questions.reduce((n,q)=>n+(quizState.answers[q.id]===q.answer?1:0),0);
 const total=quizState.questions.length, pct=Math.round(correct/total*100);
 const approved=pct>=70;
 const result={
  id:quizState.id,userId:currentUser().id,date:new Date().toISOString(),
  level:quizState.level,total,correct,incorrect:total-correct,percentage:pct,approved,
  elapsedSeconds:Math.max(0,Math.floor((Date.now()-(quizState.startedAt||Date.now()))/1000)),
  details:quizState.questions.map(q=>({questionId:q.id,text:q.text,selected:quizState.answers[q.id]??null,correct:q.answer,options:q.options}))
 };
 const h=get(STORAGE.history,[]);h.unshift(result);set(STORAGE.history,h);
 window.lastResult=result;
 
 // Limpa o estado do quiz em andamento após finalizar
 quizState=null;
 localStorage.removeItem(STORAGE.quizState);
 
 go('result');
}

function formatElapsedTime(seconds){
 const s=Math.max(0,Number(seconds)||0);
 const h=Math.floor(s/3600),m=Math.floor((s%3600)/60),sec=s%60;
 return h>0?String(h).padStart(2,'0')+':'+String(m).padStart(2,'0')+':'+String(sec).padStart(2,'0'):String(m).padStart(2,'0')+':'+String(sec).padStart(2,'0');
}

function resultView(){
 const r=window.lastResult;
 if(!r)return homeView();
 return `<div class="card result">
  <span class="badge">${labelLevel(r.level)}</span><h2>Resultado do simulado</h2>
  <div class="result-metrics">
   <div class="result-metric"><div><div class="result-metric-label">Acertos</div><div class="score">${r.percentage}%</div><div>(${r.correct} de ${r.total} questões)</div></div></div>
   <div class="result-metric"><svg class="result-stopwatch" viewBox="0 0 64 64" fill="none" stroke="currentColor" stroke-width="5" stroke-linecap="round" stroke-linejoin="round" aria-hidden="true"><circle cx="32" cy="36" r="22"/><path d="M32 14V7M24 7h16M32 24v13l9 6"/></svg><div><div class="result-metric-label">Tempo utilizado</div><div class="result-metric-value">${formatElapsedTime(r.elapsedSeconds)}</div></div></div>
  </div>
  <h3 class="${r.approved?'good':'bad'}">${r.approved?'Aprovado no critério deste simulador':'Não atingiu o critério deste simulador'}</h3>
  <p><strong>${r.correct}</strong> corretas · <strong>${r.incorrect}</strong> incorretas · ${r.total} questões</p>
  <div class="row" style="margin-top:22px">
    <button class="btn btn-primary" onclick="startQuiz('${r.level}')">Novo simulado</button>
    <button class="btn btn-secondary" onclick="go('history')">Ver histórico</button>
    <button class="btn btn-ghost" onclick="go('home')">Voltar ao início</button>
  </div>
 </div>
 <div class="card" style="margin-top:18px"><h3>Revisão das questões</h3>${r.details.map((d,i)=>{
   const ok=d.selected===d.correct;
   return `<div class="admin-item"><strong class="${ok?'good':'bad'}">${ok?'✓ Correta':'✕ Incorreta'} — Questão ${i+1}</strong>
   <p>${escapeHTML(d.text)}</p>
   <p class="small">Sua resposta: ${d.selected==null?'Não respondida':escapeHTML(d.options[d.selected])}<br>
   Resposta correta: ${escapeHTML(d.options[d.correct])}</p></div>`
 }).join('')}</div>`;
}
function historyView(){
 const u=currentUser(); if(!u)return loginView();
 const h=get(STORAGE.history,[]).filter(x=>x.userId===u.id);
 return `<div class="row"><div><h2>Histórico de desempenho</h2><p class="muted">Resultados armazenados localmente neste protótipo.</p></div><button class="btn btn-primary" onclick="go('home')">Novo simulado</button></div>
 ${h.length?`<div class="card" style="margin-top:18px;overflow:auto"><table class="history-table"><thead><tr><th>Data</th><th>Nível</th><th>Acertos</th><th>Percentual</th><th>Status</th></tr></thead><tbody>${h.map(r=>`<tr><td>${new Date(r.date).toLocaleString('pt-BR')}</td><td>${labelLevel(r.level)}</td><td>${r.correct}/${r.total}</td><td>${r.percentage}%</td><td class="${r.approved?'good':'bad'}">${r.approved?'Aprovado':'Não aprovado'}</td></tr>`).join('')}</tbody></table></div>`
 :`<div class="card empty">Nenhum simulado concluído ainda.</div>`}`;
}
function adminView(){
 const u=currentUser();if(!u||!u.admin)return homeView();
 const qs=get(STORAGE.questions,seedQuestions);
 return `<div class="row"><div><h2>Administração — Banco de questões</h2><p class="muted">Cadastre, edite e exclua questões do protótipo.</p></div></div>
 <div class="card" style="margin:18px 0"><form onsubmit="adminAdd(event)">
  <div class="field"><label>Enunciado</label><textarea id="aq_text" rows="3" required></textarea></div>
  <div class="grid">
   <div class="field"><label>Nível</label><select id="aq_level"><option value="basico">Básico</option><option value="intermediario">Intermediário</option><option value="hard">Hard</option></select></div>
   <div class="field"><label>Tema</label><input id="aq_topic" value="Legislação" required></div>
   <div class="field"><label>Alternativa correta</label><select id="aq_answer"><option value="0">A</option><option value="1">B</option><option value="2">C</option><option value="3">D</option></select></div>
  </div>
  <div class="grid">${[0,1,2,3].map(i=>`<div class="field"><label>Alternativa ${String.fromCharCode(65+i)}</label><input id="aq_${i}" required></div>`).join('')}</div>
  <button class="btn btn-primary">Cadastrar questão</button>
 </form></div>
 <div class="admin-list">${qs.map(q=>`<div class="admin-item"><div class="row"><span class="badge">${labelLevel(q.level)}</span><button class="btn btn-danger small" onclick="adminDelete('${q.id}')">Excluir</button></div><h3>${escapeHTML(q.text)}</h3><p class="small muted">${q.options.map((o,i)=>`${String.fromCharCode(65+i)}) ${escapeHTML(o)}${i===q.answer?' ✓':''}`).join(' · ')}</p></div>`).join('')}</div>`;
}
function adminAdd(e){
 e.preventDefault();
 const qs=get(STORAGE.questions,seedQuestions);
 qs.push({id:uid(),level:aq_level.value,topic:aq_topic.value,text:aq_text.value,options:[aq_0.value,aq_1.value,aq_2.value,aq_3.value],answer:Number(aq_answer.value)});
 set(STORAGE.questions,qs);toast('Questão cadastrada.');go('admin');
}
function adminDelete(id){
 if(!confirm('Excluir esta questão?'))return;
 set(STORAGE.questions,get(STORAGE.questions,seedQuestions).filter(q=>q.id!==id));toast('Questão excluída.');go('admin');
}
function login(e){
 e.preventDefault();
 const email=document.getElementById('email').value.trim().toLowerCase(), password=document.getElementById('password').value;
 const u=get(STORAGE.users,[]).find(x=>x.email===email&&x.password===password);
 if(!u){toast('E-mail ou senha inválidos.');return}
 saveSession(u);go('home');toast('Login realizado.');
}
function register(e){
 e.preventDefault();
 const name=document.getElementById('name').value.trim(),email=document.getElementById('email').value.trim().toLowerCase(),password=document.getElementById('password').value;
 const users=get(STORAGE.users,[]);
 if(users.some(u=>u.email===email)){toast('Este e-mail já está cadastrado.');return}
 const u={id:uid(),name,email,password,admin:false};users.push(u);set(STORAGE.users,users);saveSession(u);go('home');toast('Conta criada.');
}
function labelLevel(x){return x==='basico'?'Básico':x==='intermediario'?'Intermediário':'Hard'}

init();
</script>

<script>
if ('serviceWorker' in navigator && (location.protocol === 'https:' || location.hostname === 'localhost')) {
  window.addEventListener('load', () => navigator.serviceWorker.register('./service-worker.js').catch(console.error));
}
</script>

</body>
</html>
```
