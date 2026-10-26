# Businesscopilot3
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#155eef">
<title>BizManager — Small Business Management</title>
<style>
:root{--blue:#155eef;--navy:#14213d;--bg:#f4f7fb;--card:#fff;--muted:#667085;--line:#e6eaf0;--green:#159947;--red:#d92d20}
*{box-sizing:border-box}body{margin:0;font-family:Inter,system-ui,-apple-system,Segoe UI,sans-serif;background:var(--bg);color:#101828}
header{background:linear-gradient(135deg,#155eef,#3538cd);color:white;padding:22px 18px 24px;border-radius:0 0 24px 24px}
.top{display:flex;align-items:center;justify-content:space-between;gap:10px}.brand{font-size:20px;font-weight:800;letter-spacing:-.4px}.brand span{opacity:.75;font-weight:500}.avatar{width:38px;height:38px;border-radius:50%;background:#ffffff2b;display:grid;place-items:center;font-weight:800}
header p{margin:18px 0 5px;opacity:.85;font-size:13px}header h1{font-size:26px;margin:0;letter-spacing:-.6px}.sub{font-size:13px;opacity:.8;margin-top:7px}
main{max-width:850px;margin:auto;padding:16px 14px 90px}.section-title{display:flex;align-items:center;justify-content:space-between;margin:22px 2px 12px}.section-title h2{font-size:17px;margin:0}.small{font-size:12px;color:var(--muted)}
.stats{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:10px;margin-top:-5px}.stat,.panel,.feature{background:var(--card);border:1px solid var(--line);border-radius:16px;padding:15px;box-shadow:0 2px 8px #10182808}.stat .label{font-size:12px;color:var(--muted)}.stat .value{font-size:23px;font-weight:800;margin:8px 0 4px;letter-spacing:-.5px}.stat .foot{font-size:11px;color:var(--muted)}.stat-icon{float:right;font-size:20px}
.quick{display:grid;grid-template-columns:repeat(3,1fr);gap:9px}.quick button{border:1px solid var(--line);background:white;border-radius:14px;padding:14px 6px;font-size:12px;font-weight:700;color:var(--navy)}.quick b{display:block;font-size:22px;margin-bottom:7px}
.tabs{display:flex;gap:7px;overflow:auto;padding:2px 0 9px}.tab{white-space:nowrap;border:1px solid var(--line);background:white;border-radius:99px;padding:9px 13px;font-size:12px;font-weight:700;color:#475467}.tab.active{background:var(--blue);color:white;border-color:var(--blue)}
.btn{border:0;border-radius:10px;background:var(--blue);color:white;padding:11px 14px;font-weight:750;font-size:13px;cursor:pointer}.btn.secondary{background:#eef4ff;color:var(--blue)}.btn.danger{background:#fef3f2;color:var(--red)}.btn.full{width:100%}
.list{display:grid;gap:9px}.item{display:flex;align-items:center;gap:12px;background:white;border:1px solid var(--line);border-radius:14px;padding:13px}.item-icon{width:42px;height:42px;border-radius:12px;background:#eef4ff;display:grid;place-items:center;font-size:20px;flex-shrink:0}.item-main{min-width:0;flex:1}.item-main strong{font-size:13px;display:block}.item-main small{color:var(--muted);font-size:11px}.amount{font-size:13px;font-weight:800;text-align:right}.pill{display:inline-block;padding:4px 7px;border-radius:99px;font-size:10px;font-weight:800;background:#ecfdf3;color:#027a48;margin-top:5px}.pill.pending{background:#fffaeb;color:#b54708}.pill.overdue{background:#fef3f2;color:#b42318}
.panel h3{margin:0 0 14px;font-size:15px}.form-grid{display:grid;grid-template-columns:1fr 1fr;gap:11px}.field{display:flex;flex-direction:column;gap:5px}.field.wide{grid-column:1/-1}.field label{font-size:11px;color:#475467;font-weight:700}.field input,.field select,.field textarea{font:inherit;font-size:13px;padding:11px;border:1px solid #d0d5dd;border-radius:9px;background:white;width:100%;min-width:0}.field textarea{min-height:70px;resize:vertical}.actions{display:flex;gap:8px;flex-wrap:wrap;margin-top:14px}.empty{text-align:center;padding:24px;color:var(--muted);font-size:13px}
.bottom{position:fixed;bottom:0;left:0;right:0;background:#ffffffed;backdrop-filter:blur(12px);border-top:1px solid var(--line);display:flex;justify-content:space-around;padding:8px 4px max(8px,env(safe-area-inset-bottom));z-index:5}.bottom button{background:none;border:0;color:#667085;font-size:10px;font-weight:700;display:grid;gap:3px;justify-items:center;min-width:48px}.bottom button span{font-size:19px}.bottom button.active{color:var(--blue)}
.hidden{display:none!important}.notice{padding:11px 13px;border-radius:10px;background:#ecfdf3;color:#027a48;font-size:12px;margin-bottom:12px}.muted{color:var(--muted)}.row-between{display:flex;justify-content:space-between;align-items:center;gap:10px}
@media(min-width:650px){.stats{grid-template-columns:repeat(4,1fr)}.stat .value{font-size:25px}.quick{grid-template-columns:repeat(3,1fr)}main{padding-left:22px;padding-right:22px}}
</style>
</head>
<body>
<header><div class="top"><div class="brand">◈ BizManager <span>workspace</span></div><div class="avatar">B</div></div><p>MONDAY • YOUR BUSINESS AT A GLANCE</p><h1>Good business starts here.</h1><div class="sub">Manage your work, customers and cash flow in one place.</div></header>
<main>
<div id="notice" class="notice hidden"></div>
<section id="dashboard">
<div class="section-title"><h2>Business overview</h2><span class="small" id="today"></span></div>
<div class="stats">
<div class="stat"><span class="stat-icon">💵</span><div class="label">Revenue collected</div><div class="value" id="revenue">₹0</div><div class="foot">From paid invoices</div></div>
<div class="stat"><span class="stat-icon">🧾</span><div class="label">Unpaid invoices</div><div class="value" id="unpaid">₹0</div><div class="foot" id="unpaidCount">0 invoices pending</div></div>
<div class="stat"><span class="stat-icon">📉</span><div class="label">Expenses recorded</div><div class="value" id="expenses">₹0</div><div class="foot">All recorded expenses</div></div>
<div class="stat"><span class="stat-icon">👥</span><div class="label">Customers</div><div class="value" id="customersCount">0</div><div class="foot">Saved contacts</div></div>
</div>
<div class="section-title"><h2>Quick actions</h2></div>
<div class="quick">
<button onclick="showPage('invoices');openForm('invoice')"><b>＋</b>Create invoice</button>
<button onclick="showPage('expenses');openForm('expense')"><b>↗</b>Add expense</button>
<button onclick="showPage('appointments');openForm('appointment')"><b>◷</b>Book appointment</button>
</div>
<div class="section-title"><h2>Recent activity</h2><button class="btn secondary" onclick="showPage('invoices')">View invoices</button></div>
<div id="recent" class="list"></div>
</section>
<section id="invoices" class="hidden">
<div class="section-title"><h2>Invoices & estimates</h2><button class="btn" onclick="openForm('invoice')">＋ New</button></div>
<div class="tabs"><button class="tab active" onclick="invoiceFilter='all';renderInvoices(this)">All</button><button class="tab" onclick="invoiceFilter='invoice';renderInvoices(this)">Invoices</button><button class="tab" onclick="invoiceFilter='estimate';renderInvoices(this)">Estimates</button></div>
<div id="invoiceList" class="list"></div>
</section>
<section id="expenses" class="hidden">
<div class="section-title"><h2>Expense tracking</h2><button class="btn" onclick="openForm('expense')">＋ Add expense</button></div>
<div class="panel"><div class="row-between"><div><div class="small">Total recorded expenses</div><div id="expenseTotal" style="font-size:24px;font-weight:800;margin-top:4px">₹0</div></div><div style="font-size:30px">📉</div></div></div>
<div class="section-title"><h2>Expense history</h2></div><div id="expenseList" class="list"></div>
</section>
<section id="appointments" class="hidden">
<div class="section-title"><h2>Appointments</h2><button class="btn" onclick="openForm('appointment')">＋ Book</button></div>
<div id="appointmentList" class="list"></div>
</section>
<section id="customers" class="hidden">
<div class="section-title"><h2>Customers</h2><button class="btn" onclick="openForm('customer')">＋ Add</button></div>
<div class="field" style="margin-bottom:12px"><input id="customerSearch" placeholder="Search customers..." oninput="renderCustomers()"></div><div id="customerList" class="list"></div>
</section>
<section id="reports" class="hidden">
<div class="section-title"><h2>Business reports</h2></div>
<div class="stats"><div class="stat"><div class="label">Paid revenue</div><div class="value" id="reportRevenue">₹0</div></div><div class="stat"><div class="label">Expenses</div><div class="value" id="reportExpenses">₹0</div></div><div class="stat"><div class="label">Net estimate</div><div class="value" id="profit">₹0</div></div><div class="stat"><div class="label">Open invoices</div><div class="value" id="reportOpen">0</div></div></div>
<div class="panel" style="margin-top:12px"><h3>Data backup</h3><p class="small">Export your records as JSON or download a CSV summary. Data is stored in this browser on this device.</p><div class="actions"><button class="btn" onclick="exportJSON()">Export backup</button><button class="btn secondary" onclick="exportCSV()">Export invoices CSV</button><button class="btn danger" onclick="clearData()">Clear all data</button></div></div>
</section>
<section id="formPage" class="hidden">
<div class="section-title"><h2 id="formTitle">Add record</h2><button class="btn secondary" onclick="showPage(currentPage)">Cancel</button></div>
<div class="panel"><form id="recordForm"><div id="formFields" class="form-grid"></div><div class="actions"><button class="btn" type="submit">Save record</button><button class="btn secondary" type="button" onclick="showPage(currentPage)">Cancel</button></div></form></div>
</section>
</main>
<nav class="bottom">
<button class="active" data-page="dashboard" onclick="showPage('dashboard',this)"><span>⌂</span>Home</button>
<button data-page="invoices" onclick="showPage('invoices',this)"><span>▤</span>Invoices</button>
<button data-page="expenses" onclick="showPage('expenses',this)"><span>↗</span>Expenses</button>
<button data-page="appointments" onclick="showPage('appointments',this)"><span>◷</span>Schedule</button>
<button data-page="customers" onclick="showPage('customers',this)"><span>♙</span>Customers</button>
<button data-page="reports" onclick="showPage('reports',this)"><span>▥</span>Reports</button>
</nav>
<script>
const KEY='bizmanager_data_v1';
let data={invoices:[],expenses:[],appointments:[],customers:[]};
try{const saved=localStorage.getItem(KEY);if(saved)data={...data,...JSON.parse(saved)}}catch(e){}
let currentPage='dashboard', formType='invoice', invoiceFilter='all';
const $=id=>document.getElementById(id);
const money=n=>new Intl.NumberFormat('en-IN',{style:'currency',currency:'INR',maximumFractionDigits:2}).format(Number(n)||0);
const esc=s=>String(s??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]));
const save=()=>{localStorage.setItem(KEY,JSON.stringify(data));renderAll()};
const dateToday=()=>new Date().toISOString().slice(0,10);
$('today').textContent=new Date().toLocaleDateString('en-IN',{day:'numeric',month:'short',year:'numeric'});
function showNotice(msg){$('notice').textContent=msg;$('notice').classList.remove('hidden');setTimeout(()=>$('notice').classList.add('hidden'),2600)}
function showPage(page,btn){currentPage=page;document.querySelectorAll('main>section').forEach(s=>s.classList.add('hidden'));$(page).classList.remove('hidden');if(page!=='formPage'){$('formPage').classList.add('hidden');currentPage=page}document.querySelectorAll('.bottom button').forEach(b=>b.classList.toggle('active',b.dataset.page===page));renderAll()}
function field(name,label,type='text',required=true,extra=''){return `<div class="field ${extra}"><label>${label}</label><input name="${name}" type="${type}" ${required?'required':''} ${type==='number'?'min="0" step="0.01"':''}></div>`}
function selectField(name,label,options,extra=''){return `<div class="field ${extra}"><label>${label}</label><select name="${name}" required>${options.map(o=>`<option value="${esc(o[0])}">${esc(o[1])}</option>`).join('')}</select></div>`}
function openForm(type){formType=type;const titles={invoice:'Create invoice',estimate:'Create estimate',expense:'Record expense',appointment:'Book appointment',customer:'Add customer'};$('formTitle').textContent=titles[type]||'Add record';let f='';
if(type==='invoice'||type==='estimate')f=field('customer','Customer name')+field('date','Issue date','date',true)+field('dueDate','Due date','date',true)+field('description','Description')+field('amount','Amount (₹)','number')+selectField('status','Payment status',[['unpaid','Unpaid'],['paid','Paid']])+`<div class="field wide"><label>Notes (optional)</label><textarea name="notes"></textarea></div>`;
if(type==='expense')f=field('title','Expense title')+field('date','Date','date',true)+field('amount','Amount (₹)','number')+selectField('category','Category',[['Supplies','Supplies'],['Travel','Travel'],['Rent','Rent'],['Marketing','Marketing'],['Utilities','Utilities'],['Software','Software'],['Other','Other']])+`<div class="field wide"><label>Notes (optional)</label><textarea name="notes"></textarea></div>`;
if(type==='appointment')f=field('customer','Customer name')+field('title','Appointment / service')+field('date','Date','date',true)+field('time','Time','time',true)+field('phone','Contact phone', 'tel',false)+selectField('status','Status',[['scheduled','Scheduled'],['completed','Completed'],['cancelled','Cancelled']])+`<div class="field wide"><label>Notes</label><textarea name="notes"></textarea></div>`;
if(type==='customer')f=field('name','Customer name')+field('phone','Phone number','tel',false)+field('email','Email address','email',false)+`<div class="field wide"><label>Address / notes</label><textarea name="notes"></textarea></div>`;
$('formFields').innerHTML=f;$('formPage').classList.remove('hidden');document.querySelectorAll('main>section').forEach(s=>{if(s.id!=='formPage')s.classList.add('hidden')});$('recordForm').reset();const date=$('recordForm').elements.date;if(date)date.value=dateToday();const due=$('recordForm').elements.dueDate;if(due){let d=new Date();d.setDate(d.getDate()+7);due.value=d.toISOString().slice(0,10)}}
$('recordForm').addEventListener('submit',e=>{e.preventDefault();const o=Object.fromEntries(new FormData(e.target).entries());o.id=Date.now().toString();if(['invoice','estimate'].includes(formType)){o.amount=Number(o.amount);o.kind=formType;data.invoices.unshift(o)}else if(formType==='expense'){o.amount=Number(o.amount);data.expenses.unshift(o)}else if(formType==='appointment'){data.appointments.unshift(o)}else if(formType==='customer'){data.customers.unshift(o)}save();showPage(currentPage);showNotice('Record saved successfully.')});
function renderAll(){const paid=data.invoices.filter(x=>x.kind==='invoice'&&x.status==='paid').reduce((a,x)=>a+x.amount,0),open=data.invoices.filter(x=>x.kind==='invoice'&&x.status!=='paid'),unpaid=open.reduce((a,x)=>a+x.amount,0),expenses=data.expenses.reduce((a,x)=>a+x.amount,0);$('revenue').textContent=money(paid);$('unpaid').textContent=money(unpaid);$('unpaidCount').textContent=`${open.length} invoice${open.length===1?'':'s'} pending`;$('expenses').textContent=money(expenses);$('customersCount').textContent=data.customers.length;$('expenseTotal').textContent=money(expenses);$('reportRevenue').textContent=money(paid);$('reportExpenses').textContent=money(expenses);$('profit').textContent=money(paid-expenses);$('reportOpen').textContent=open.length;renderInvoices();renderExpenses();renderAppointments();renderCustomers();renderRecent()}
function statusPill(s){let cls=s==='paid'||s==='completed'?'':(s==='overdue'?'overdue':'pending');return `<span class="pill ${cls}">${esc((s||'scheduled').replace(/^./,c=>c.toUpperCase()))}</span>`}
function renderInvoices(btn){if(btn){document.querySelectorAll('#invoices .tab').forEach(b=>b.classList.remove('active'));btn.classList.add('active')}const arr=data.invoices.filter(x=>invoiceFilter==='all'||x.kind===invoiceFilter);$('invoiceList').innerHTML=arr.length?arr.map(x=>`<div class="item"><div class="item-icon">${x.kind==='estimate'?'📋':'🧾'}</div><div class="item-main"><strong>${esc(x.customer)} · ${esc(x.kind==='estimate'?'Estimate':'Invoice')}</strong><small>${esc(x.description)} · ${esc(x.date||'')}</small><div>${statusPill(x.status)}</div></div><div class="amount">${money(x.amount)}<div class="actions" style="justify-content:flex-end;margin-top:7px"><button class="btn secondary" onclick="togglePaid('${x.id}')">${x.status==='paid'?'Mark unpaid':'Mark paid'}</button><button class="btn danger" onclick="removeRecord('invoices','${x.id}')">×</button></div></div></div>`).join(''):'<div class="empty">No invoices yet. Tap “New” to create one.</div>'}
function togglePaid(id){const x=data.invoices.find(x=>x.id===id);if(x)x.status=x.status==='paid'?'unpaid':'paid';save()}
function renderExpenses(){$('expenseList').innerHTML=data.expenses.length?data.expenses.map(x=>`<div class="item"><div class="item-icon">💳</div><div class="item-main"><strong>${esc(x.title)}</strong><small>${esc(x.category)} · ${esc(x.date)}</small></div><div class="amount">${money(x.amount)}<div style="margin-top:7px"><button class="btn danger" onclick="removeRecord('expenses','${x.id}')">Delete</button></div></div></div>`).join(''):'<div class="empty">No expenses recorded yet.</div>'}
function renderAppointments(){$('appointmentList').innerHTML=data.appointments.length?data.appointments.map(x=>`<div class="item"><div class="item-icon">🗓️</div><div class="item-main"><strong>${esc(x.title)} · ${esc(x.customer)}</strong><small>${esc(x.date)} at ${esc(x.time)} ${x.phone?'· '+esc(x.phone):''}</small><div>${statusPill(x.status)}</div></div><button class="btn danger" onclick="removeRecord('appointments','${x.id}')">Delete</button></div>`).join(''):'<div class="empty">No appointments booked yet.</div>'}
function renderCustomers(){const q=($('customerSearch')?.value||'').toLowerCase();const arr=data.customers.filter(x=>(x.name+' '+x.phone+' '+x.email).toLowerCase().includes(q));$('customerList').innerHTML=arr.length?arr.map(x=>`<div class="item"><div class="item-icon">👤</div><div class="item-main"><strong>${esc(x.name)}</strong><small>${esc(x.phone||'No phone')} ${x.email?'· '+esc(x.email):''}</small>${x.notes?`<div class="small">${esc(x.notes)}</div>`:''}</div><button class="btn danger" onclick="removeRecord('customers','${x.id}')">Delete</button></div>`).join(''):'<div class="empty">No customers found. Add your first customer.</div>'}
function renderRecent(){const arr=[...data.invoices.map(x=>({...x,type:x.kind==='estimate'?'Estimate':'Invoice',icon:'🧾'})),...data.expenses.map(x=>({...x,type:'Expense',icon:'💳',customer:x.title}))].slice(0,4);$('recent').innerHTML=arr.length?arr.map(x=>`<div class="item"><div class="item-icon">${x.icon}</div><div class="item-main"><strong>${esc(x.type)} · ${esc(x.customer||'')}</strong><small>${esc(x.date||'')}</small></div><div class="amount">${money(x.amount)}</div></div>`).join(''):'<div class="empty">Your latest invoices and expenses will appear here.</div>'}
function removeRecord(key,id){if(confirm('Delete this record?')){data[key]=data[key].filter(x=>x.id!==id);save()}}
function exportJSON(){download('bizmanager-backup.json',JSON.stringify(data,null,2),'application/json')}
function exportCSV(){const rows=[['Type','Customer','Description','Date','Amount','Status'],...data.invoices.map(x=>[x.kind,x.customer,x.description,x.date,x.amount,x.status])];const csv=rows.map(r=>r.map(v=>'"'+String(v??'').replace(/"/g,'""')+'"').join(',')).join('\n');download('bizmanager-invoices.csv',csv,'text/csv')}
function download(name,content,type){const a=document.createElement('a');a.href=URL.createObjectURL(new Blob([content],{type}));a.download=name;a.click();URL.revokeObjectURL(a.href)}
function clearData(){if(confirm('This permanently deletes all BizManager records stored in this browser. Continue?')){data={invoices:[],expenses:[],appointments:[],customers:[]};save();showNotice('All local records cleared.')}}
renderAll();
</script>
</body></html>
