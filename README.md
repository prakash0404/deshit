<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Deshit — Premium (Single File)</title>

  <!-- Embedded CSS (purple + white premium theme) -->
  <style>
    :root{
      --brand:#6a1b9a;
      --accent:#8e24aa;
      --muted:#6c7280;
      --bg:#ffffff;
      --card-radius:14px;
      --max-width:1200px;
      --glass: rgba(255,255,255,0.7);
    }
    *{box-sizing:border-box}
    body{
      font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      background:linear-gradient(180deg,#fff 0%, #fbf7ff 100%);
      margin:0; color:#222;
    }
    .container{max-width:var(--max-width); margin:0 auto; padding:20px;}
    .header{
      background:linear-gradient(90deg, rgba(106,27,154,0.06), rgba(142,36,170,0.03));
      padding:14px 20px; display:flex; align-items:center; justify-content:space-between;
      box-shadow:0 6px 22px rgba(106,27,154,0.06); border-radius:12px;
    }
    .brand{display:flex; align-items:center; gap:12px;}
    .brand img{height:44px; border-radius:8px; background:var(--glass); padding:4px;}
    .brand .name{font-weight:800; color:var(--brand); letter-spacing:0.2px; font-size:1.05rem;}
    .brand .tag{font-size:0.9rem; color:var(--muted); margin-top:2px;}
    .search {display:flex; gap:10px; align-items:center;}
    .input {padding:10px 12px; border-radius:10px; border:1px solid rgba(106,27,154,0.08); background:white; width:260px; box-shadow:inset 0 1px 0 rgba(0,0,0,0.02);}
    .btn {
      background:var(--brand); color:white; padding:10px 14px; border-radius:10px; border:none; cursor:pointer;
      box-shadow:0 10px 30px rgba(106,27,154,0.12); transition:transform .12s ease, box-shadow .12s ease;
    }
    .btn:hover{transform:translateY(-3px); box-shadow:0 18px 40px rgba(106,27,154,0.14);}
    .btn.secondary{
      background:transparent; color:var(--brand); border:1px solid rgba(106,27,154,0.12);
      box-shadow:none;
    }
    .hero{
      display:flex; gap:20px; padding:34px; align-items:center;
      background:linear-gradient(180deg, rgba(106,27,154,0.03), rgba(142,36,170,0.02));
      border-radius:14px; margin-top:18px; position:relative; overflow:hidden;
    }
    .hero::after{
      content:"";
      position:absolute;
      inset:0;
      background:linear-gradient(90deg, rgba(106,27,154,0.18), rgba(142,36,170,0.08));
      pointer-events:none;
    }
    .hero-left{flex:1; position:relative; z-index:2;}
    .hero-left h1{margin:0 0 8px 0; color:var(--brand);}
    .hero-left p{color:var(--muted); margin:0;}
    .hero-right{position:relative; z-index:1;}
    .hero-right img{max-width:460px; border-radius:14px; box-shadow:0 18px 50px rgba(106,27,154,0.06); border:1px solid rgba(106,27,154,0.02); filter:contrast(1.02) saturate(1.05);}
    .hero-right::before{
      content:"";
      position:absolute;
      inset:0;
      background:linear-gradient(180deg, rgba(106,27,154,0.12), rgba(0,0,0,0));
      border-radius:14px;
      pointer-events:none;
    }
    .grid{display:grid; grid-template-columns:repeat(auto-fit,minmax(260px,1fr)); gap:18px; margin-top:18px;}
    .card{
      background:linear-gradient(180deg,#fff,#fcf8ff); border-radius:var(--card-radius); padding:14px;
      box-shadow:0 12px 30px rgba(20,18,41,0.04); transition:transform .12s ease, box-shadow .12s ease;
      border:1px solid rgba(106,27,154,0.03);
    }
    .card:hover{transform:translateY(-6px); box-shadow:0 30px 60px rgba(20,18,41,0.06);}
    .card img{width:100%; border-radius:10px; object-fit:cover; height:160px;}
    .card .title{font-weight:700; margin-top:10px; color:#221334;}
    .card .muted{color:var(--muted); font-size:0.92rem;}
    .footer{
      margin-top:36px; padding:24px; text-align:center; color:var(--muted); font-size:0.92rem;
      border-top:1px solid rgba(106,27,154,0.04); background:transparent; border-radius:8px;
    }
    .badge{background:var(--accent); color:white; padding:6px 8px; border-radius:10px; font-size:0.78rem;}
    .lang-toggle{background:white; border-radius:8px; padding:6px 8px; border:1px solid rgba(106,27,154,0.06); cursor:pointer;}
    .avatar{width:42px; height:42px; border-radius:8px; object-fit:cover; box-shadow:0 6px 20px rgba(106,27,154,0.06);}
    .role-pill{background:linear-gradient(90deg, rgba(106,27,154,0.12), rgba(142,36,170,0.06)); border-radius:18px; padding:6px 10px; color:var(--brand); font-weight:600; cursor:pointer; border:1px solid rgba(106,27,154,0.05);}
    .nav-links{display:flex; gap:10px; align-items:center;}
    .nav-link{color:var(--brand); text-decoration:none; background:transparent; border:none; cursor:pointer; font-weight:600;}
    .hidden{display:none;}
    @media(max-width:820px){
      .hero{flex-direction:column; text-align:center;}
      .search{flex-direction:column; align-items:stretch;}
      .input{width:100%;}
    }

    /* small helpers */
    .section-title{margin-top:26px; margin-bottom:8px; font-size:1.15rem; color:#221334;}
    .back-link{background:none;border:none;color:var(--brand);cursor:pointer;font-weight:600;padding:0;}
  </style>
</head>
<body>
  <div class="container">

    <!-- HEADER -->
    <header class="header" role="banner" aria-label="Top navigation">
      <div class="brand" role="navigation" aria-label="Brand">
        <img src="https://source.unsplash.com/featured/?logo,construction,abstract" alt="Deshit logo">
        <div>
          <div class="name">Deshit</div>
          <div class="tag">Premium daily-wage workers & construction materials</div>
        </div>
      </div>

      <div style="display:flex;align-items:center;gap:12px;">
        <div id="rolePill" class="role-pill" onclick="setRole(localStorage.getItem('deshit_role')==='client'?'worker':'client')" title="Switch role">Client</div>

        <nav class="nav-links" aria-label="Pages">
          <button class="nav-link" onclick="navigate('home')">Home</button>
          <button class="nav-link" onclick="navigate('materials')">Materials</button>
          <button class="nav-link" onclick="navigate('workerProfile')">Worker</button>
        </nav>

        <div class="search" role="search" style="margin-left:12px;">
          <input id="q1" class="input" placeholder="Search trade or name (mason, plumber...)">
          <input id="q2" class="input" placeholder="City or pincode">
          <button class="btn" onclick="doSearch()">Search</button>
        </div>

        <div style="display:flex;align-items:center;gap:10px;margin-left:12px;">
          <div class="lang-toggle" onclick="toggleLang()">EN/हिं</div>
          <img src="https://source.unsplash.com/collection/542909/?face,portrait" class="avatar" alt="avatar">
        </div>
      </div>
    </header>

    <!-- MAIN: multiple sections (single-file "pages") -->
    <main role="main">

      <!-- HOME -->
      <section id="home" class="page-section">
        <section class="hero" aria-label="Hero">
          <div class="hero-left">
            <h1>Hire premium workers — fast, trusted, local</h1>
            <p class="small">Deshit connects you to vetted masons, plumbers, electricians, painters and building materials with transparent pricing.</p>
            <div style="margin-top:14px;">
              <button class="btn" onclick="navigate('home');">Find Workers</button>
              <button class="btn secondary" onclick="navigate('materials')">Browse Materials</button>
            </div>
          </div>
          <div class="hero-right" aria-hidden="true">
            <img src="https://source.unsplash.com/collection/190727/900x700" alt="construction scene">
          </div>
        </section>

        <h3 class="section-title">Featured Workers</h3>
        <div id="workersGrid" class="grid" aria-live="polite"></div>

        <h3 class="section-title">Featured Materials</h3>
        <div id="materialsGrid" class="grid" aria-live="polite"></div>
      </section>

      <!-- MATERIALS "page" -->
      <section id="materials" class="page-section hidden" aria-hidden="true">
        <div style="display:flex;align-items:center;justify-content:space-between;">
          <div>
            <button class="back-link" onclick="navigate('home')">← Back</button>
            <h2 style="display:inline-block;margin-left:12px;">Materials Catalog</h2>
          </div>
          <div>
            <button class="btn" onclick="alert('View cart (demo)')">View Cart</button>
          </div>
        </div>

        <div id="materialsGridPage" class="grid" style="margin-top:14px;"></div>

        <div style="margin-top:20px;" class="card">
          <div style="display:flex;justify-content:space-between;align-items:center;">
            <div>
              <div style="font-weight:800;">Cart (demo)</div>
              <div class="muted">Your selections are saved in localStorage.</div>
            </div>
            <div>
              <button class="btn" onclick="alert('Open cart (demo)')">Open Cart</button>
            </div>
          </div>
        </div>
      </section>

      <!-- WORKER PROFILE "page" -->
      <section id="workerProfile" class="page-section hidden" aria-hidden="true">
        <div style="display:flex;align-items:center;justify-content:space-between;">
          <div>
            <button class="back-link" onclick="navigate('home')">← Back</button>
            <h2 style="display:inline-block;margin-left:12px;">Worker Profile</h2>
          </div>
          <div>
            <button class="btn" onclick="openHireModalEnhanced(1)">Book Now</button>
          </div>
        </div>

        <div style="display:grid;grid-template-columns:320px 1fr;gap:20px; margin-top:18px;">
          <div class="card" style="padding:18px;">
            <img id="wp_img" src="https://source.unsplash.com/featured/?mason,worker,man" alt="Ramesh" style="width:100%;height:220px;object-fit:cover;border-radius:10px;">
            <div class="title" style="margin-top:12px;" id="wp_name">Ramesh Kumar</div>
            <div class="muted" id="wp_meta">Mason • New Delhi</div>
            <div style="margin-top:12px;"><strong id="wp_rate">₹800/day</strong></div>
            <div class="muted" style="margin-top:10px;" id="wp_exp">Experience: 6 years</div>
            <div style="margin-top:12px;">
              <button class="btn" onclick="openHireModalEnhanced(1)">Hire</button>
              <button class="btn secondary" style="margin-left:8px" onclick="saveWorker(1)">Save</button>
            </div>
          </div>

          <div>
            <div class="card" style="padding:18px;">
              <div style="display:flex;justify-content:space-between;align-items:center;">
                <div>
                  <div style="font-weight:800;font-size:1.05rem;">Profile</div>
                  <div class="muted">Skills, portfolio and reviews</div>
                </div>
                <div class="badge">Top Rated</div>
              </div>

              <div style="margin-top:12px;">
                <div style="font-weight:700;">Skills</div>
                <div class="muted" style="margin-top:6px;">Brickwork, Plaster, Tile fixing</div>

                <div style="margin-top:12px;font-weight:700;">Portfolio</div>
                <div style="display:flex;gap:8px;margin-top:8px;">
                  <img src="https://source.unsplash.com/featured/?construction,worksite" style="width:120px;height:80px;border-radius:8px;object-fit:cover;">
                  <img src="https://source.unsplash.com/featured/?building,site" style="width:120px;height:80px;border-radius:8px;object-fit:cover;">
                  <img src="https://source.unsplash.com/featured/?brickwork" style="width:120px;height:80px;border-radius:8px;object-fit:cover;">
                </div>

                <div style="margin-top:12px;">
                  <div style="font-weight:700;">Reviews</div>
                  <div class="muted" style="margin-top:6px;">4.6 • 120 ratings</div>
                  <div style="margin-top:8px;" class="muted">"Excellent finish and reliable timing." — Client A</div>
                </div>
              </div>
            </div>

            <div class="card" style="margin-top:14px;padding:16px;">
              <div style="font-weight:700;">Availability</div>
              <div class="muted" style="margin-top:8px;">Mon - Sat • 9:00 AM - 6:00 PM</div>
              <div style="margin-top:12px;">
                <button class="btn" onclick="openHireModalEnhanced(1)">Book Now</button>
              </div>
            </div>
          </div>
        </div>
      </section>

    </main>

    <footer class="footer">
      © 2025 Deshit — Premium theme (purple & white)
    </footer>
  </div>

  <!-- Embedded JS (rendering + modal + routing + toggles) -->
  <script>
    /*******************************
     * Single-file Deshit (client-side demo)
     * - Unsplash images used (real photos)
     * - Sections: home, materials, workerProfile
     * - Hire modal + email template (mailto)
     * - Role and language toggles (simple)
     * - LocalStorage saves for hires, cart, saved workers
     *******************************/

    const SAMPLE = {
      workers:[
        {id:1,name:"Ramesh Kumar",trade:"Mason",location:"New Delhi",rate:800,img:"https://source.unsplash.com/featured/?construction,worker,man",contact:"ramesh@example.com"},
        {id:2,name:"Suresh Yadav",trade:"Plumber",location:"Noida",rate:700,img:"https://source.unsplash.com/featured/?plumber,worker",contact:"suresh@example.com"},
        {id:3,name:"Anil Mehta",trade:"Electrician",location:"Gurgaon",rate:900,img:"https://source.unsplash.com/featured/?electrician,worker",contact:"anil@example.com"},
        {id:4,name:"Rahul Singh",trade:"Painter",location:"Faridabad",rate:650,img:"https://source.unsplash.com/featured/?painter,worker",contact:"rahul@example.com"}
      ],
      materials:[
        {id:101,title:"OPC Cement 50kg",price:420,img:"https://source.unsplash.com/featured/?cement,bags"},
        {id:102,title:"Standard Bricks (100 pcs)",price:4500,img:"https://source.unsplash.com/featured/?bricks"},
        {id:103,title:"Floor Tiles (per sqft)",price:55,img:"https://source.unsplash.com/featured/?tiles,floor"}
      ]
    };

    /* -- Renderers -- */
    function renderWorkersGrid(containerId){
      const cont = document.getElementById(containerId);
      if(!cont) return;
      cont.innerHTML = '';
      SAMPLE.workers.forEach(w=>{
        const el = document.createElement('div');
        el.className = 'card';
        el.innerHTML = `
          <img src="${w.img}" alt="${w.name}">
          <div class="title">${w.name}</div>
          <div class="muted">${w.trade} • ${w.location}</div>
          <div style="margin-top:12px;display:flex;justify-content:space-between;align-items:center;">
            <strong>₹${w.rate}/day</strong>
            <div style="display:flex;gap:8px">
              <button class="btn" onclick="openHireModalEnhanced(${w.id})">Hire</button>
              <button class="btn secondary" onclick="saveWorker(${w.id})">Save</button>
            </div>
          </div>`;
        cont.appendChild(el);
      });
    }

    function renderMaterialsGrid(containerId){
      const cont = document.getElementById(containerId);
      if(!cont) return;
      cont.innerHTML = '';
      SAMPLE.materials.forEach(m=>{
        const el = document.createElement('div');
        el.className = 'card';
        el.innerHTML = `
          <img src="${m.img}" alt="${m.title}">
          <div class="title">${m.title}</div>
          <div class="muted">₹${m.price}</div>
          <div style="margin-top:12px;display:flex;gap:8px;">
            <button class="btn secondary" onclick="viewMaterial(${m.id})">Details</button>
            <button class="btn" onclick="addToCart(${m.id})">Add to Cart</button>
          </div>`;
        cont.appendChild(el);
      });
    }

    /* populate materials page grid separately */
    function renderMaterialsPage(){
      const cont = document.getElementById('materialsGridPage');
      if(!cont) return;
      cont.innerHTML = '';
      SAMPLE.materials.forEach(m=>{
        const el = document.createElement('div');
        el.className = 'card';
        el.innerHTML = `
          <img src="${m.img}" alt="${m.title}">
          <div class="title">${m.title}</div>
          <div class="muted">₹${m.price}</div>
          <div style="margin-top:12px;display:flex;gap:8px;">
            <button class="btn secondary" onclick="viewMaterial(${m.id})">Details</button>
            <button class="btn" onclick="addToCart(${m.id})">Add to Cart</button>
          </div>`;
        cont.appendChild(el);
      });
    }

    /* -- Persistence & interactions -- */
    function saveWorker(id){
      const saved = JSON.parse(localStorage.getItem('deshit_saved_workers')||'[]');
      if(!saved.includes(id)) saved.push(id);
      localStorage.setItem('deshit_saved_workers', JSON.stringify(saved));
      toast('Worker saved (demo)');
    }

    function addToCart(id){
      const cart = JSON.parse(localStorage.getItem('deshit_cart')||'[]');
      cart.push({materialId:id,qty:1});
      localStorage.setItem('deshit_cart', JSON.stringify(cart));
      toast('Added to cart (demo)');
    }

    function viewMaterial(id){
      const m = SAMPLE.materials.find(x=>x.id===id);
      if(!m) return alert('Material not found');
      alert(m.title + "\\nPrice: ₹" + m.price + "\\n(This is a demo)");
    }

    /* toast */
    function toast(msg, ms=2000){
      const t = document.createElement('div');
      t.style.position='fixed'; t.style.right='20px'; t.style.bottom='20px';
      t.style.background='white'; t.style.padding='10px 14px'; t.style.borderRadius='10px';
      t.style.boxShadow='0 10px 30px rgba(20,18,41,0.08)'; t.innerText = msg;
      document.body.appendChild(t);
      setTimeout(()=> { t.style.opacity='0'; t.style.transition='opacity .3s'; setTimeout(()=>t.remove(),300); }, ms);
    }

    /* -- Hire modal and email template -- */
    function createHireEmailTemplate(data){
      const subject = encodeURIComponent('Hire Request: ' + (data.workerName || 'Worker'));
      const bodyLines = [
        'Hello ' + (data.workerName || ''),
        '',
        'I would like to hire you for the following job:',
        'Date: ' + (data.jobDate || '-'),
        'Details: ' + (data.message || '-'),
        '',
        'Client: ' + (data.clientName || '-'),
        'Contact: ' + (data.clientContact || '-'),
        '',
        'Please reply to confirm availability.',
        '',
        'Thanks,',
        (data.clientName || '-')
      ];
      return `mailto:${data.workerContact || ''}?subject=${subject}&body=${encodeURIComponent(bodyLines.join('\\n'))}`;
    }

    function openHireModalEnhanced(id){
      const w = SAMPLE.workers.find(x=>x.id===id);
      if(!w) return alert('Worker not found');
      const existing = document.getElementById('deshit-hire-modal');
      if(existing) existing.remove();

      const modal = document.createElement('div');
      modal.id = 'deshit-hire-modal';
      modal.style.position = 'fixed';
      modal.style.inset = '0';
      modal.style.background = 'rgba(10,8,15,0.45)';
      modal.style.display = 'flex';
      modal.style.alignItems = 'center';
      modal.style.justifyContent = 'center';
      modal.style.zIndex = '9999';
      modal.innerHTML = `
        <div style="background:#fff;padding:20px;border-radius:12px;max-width:680px;width:94%;box-shadow:0 30px 60px rgba(26,12,48,0.2);">
          <div style="display:flex;justify-content:space-between;align-items:center;">
            <h3 style="margin:0;color:var(--brand)">Hire ${w.name}</h3>
            <button id="deshit-hire-close" style="border:none;background:none;font-size:22px;cursor:pointer;">&times;</button>
          </div>
          <div style="display:flex;gap:14px;margin-top:12px;">
            <img src="${w.img}" alt="${w.name}" style="width:150px;height:110px;object-fit:cover;border-radius:10px;border:1px solid rgba(106,27,154,0.04);">
            <div style="flex:1;">
              <div style="font-weight:700;color:#221334">${w.name}</div>
              <div class="muted">${w.trade} • ${w.location}</div>
              <div style="margin-top:8px;"><strong>₹${w.rate}/day</strong></div>
              <div style="margin-top:10px;">
                <input id="deshit_client_name" class="input" placeholder="Your name" />
                <input id="deshit_client_contact" class="input" placeholder="Contact (phone/email)" style="margin-top:8px;" />
                <input id="deshit_job_date" type="date" class="input" style="margin-top:8px;" />
                <textarea id="deshit_job_msg" class="input" placeholder="Job details" style="margin-top:8px;height:88px;"></textarea>
                <div style="display:flex;gap:10px;margin-top:12px;">
                  <button class="btn" id="deshit-send-btn">Send Request</button>
                  <button class="btn secondary" id="deshit-email-btn">Email Template</button>
                </div>
              </div>
            </div>
          </div>
        </div>
      `;
      document.body.appendChild(modal);
      document.getElementById('deshit-hire-close').onclick = ()=> modal.remove();
      document.getElementById('deshit-send-btn').onclick = ()=> sendHire(w.id);
      document.getElementById('deshit-email-btn').onclick = ()=> emailHire(w.id);
    }

    function sendHire(id){
      const w = SAMPLE.workers.find(x=>x.id===id);
      const payload = {
        workerId: id,
        workerName: w.name,
        workerContact: w.contact,
        clientName: document.getElementById('deshit_client_name').value || '[Guest]',
        clientContact: document.getElementById('deshit_client_contact').value || '',
        jobDate: document.getElementById('deshit_job_date').value || '',
        message: document.getElementById('deshit_job_msg').value || ''
      };
      const hires = JSON.parse(localStorage.getItem('deshit_hires')||'[]');
      hires.push(payload);
      localStorage.setItem('deshit_hires', JSON.stringify(hires));
      toast('Hire request saved (demo)');
      const modal = document.getElementById('deshit-hire-modal'); if(modal) modal.remove();
    }

    function emailHire(id){
      const w = SAMPLE.workers.find(x=>x.id===id);
      const payload = {
        workerName: w.name,
        workerContact: w.contact,
        clientName: document.getElementById('deshit_client_name').value || '[Guest]',
        clientContact: document.getElementById('deshit_client_contact').value || '',
        jobDate: document.getElementById('deshit_job_date').value || '',
        message: document.getElementById('deshit_job_msg').value || ''
      };
      window.location.href = createHireEmailTemplate(payload);
    }

    /* -- simple client-side routing (show/hide sections) -- */
    function navigate(page){
      const sections = document.querySelectorAll('.page-section');
      sections.forEach(s=>{
        if(s.id === page){
          s.classList.remove('hidden'); s.setAttribute('aria-hidden','false');
        } else {
          s.classList.add('hidden'); s.setAttribute('aria-hidden','true');
        }
      });
      // if navigating to materials page render its grid
      if(page === 'materials') renderMaterialsPage();
      // if navigating to worker profile, populate profile details (demo)
      if(page === 'workerProfile') populateWorkerProfile(1);
      // scroll to top
      window.scrollTo({top:0,behavior:'smooth'});
    }

    function populateWorkerProfile(id){
      const w = SAMPLE.workers.find(x=>x.id===id);
      if(!w) return;
      document.getElementById('wp_img').src = w.img;
      document.getElementById('wp_name').innerText = w.name;
      document.getElementById('wp_meta').innerText = `${w.trade} • ${w.location}`;
      document.getElementById('wp_rate').innerText = `₹${w.rate}/day`;
      document.getElementById('wp_exp').innerText = `Experience: ${w.experience || 6} years`;
    }

    /* -- role & language toggles -- */
    function setRole(role){
      localStorage.setItem('deshit_role', role);
      const pill = document.getElementById('rolePill');
      if(pill) pill.innerText = role === 'client' ? 'Client' : 'Worker';
      toast('Role set to ' + (role==='client'?'Client':'Worker') + ' (demo)');
    }
    function toggleLang(){
      const cur = localStorage.getItem('deshit_lang') || 'en';
      const next = cur === 'en' ? 'hi' : 'en';
      localStorage.setItem('deshit_lang', next);
      toast('Language switched to ' + (next==='en' ? 'English' : 'हिन्दी') + ' (demo)');
    }

    /* -- search (simple filter) -- */
    function doSearch(){
      const q = (document.getElementById('q1').value || '').toLowerCase();
      const loc = (document.getElementById('q2').value || '').toLowerCase();
      const results = SAMPLE.workers.filter(w=>{
        const matchQuery = q ? (w.name + ' ' + w.trade).toLowerCase().includes(q) : true;
        const matchLoc = loc ? w.location.toLowerCase().includes(loc) : true;
        return matchQuery && matchLoc;
      });
      // Render results into workersGrid
      const cont = document.getElementById('workersGrid');
      cont.innerHTML = '';
      if(results.length === 0){
        cont.innerHTML = '<div class="card"><div class="title">No workers found</div><div class="muted">Try a different search.</div></div>';
      } else {
        results.forEach(w=>{
          const el = document.createElement('div');
          el.className='card';
          el.innerHTML = `
            <img src="${w.img}" alt="${w.name}">
            <div class="title">${w.name}</div>
            <div class="muted">${w.trade} • ${w.location}</div>
            <div style="margin-top:12px;display:flex;justify-content:space-between;align-items:center;">
              <strong>₹${w.rate}/day</strong>
              <div style="display:flex;gap:8px">
                <button class="btn" onclick="openHireModalEnhanced(${w.id})">Hire</button>
                <button class="btn secondary" onclick="saveWorker(${w.id})">Save</button>
              </div>
            </div>`;
          cont.appendChild(el);
        });
      }
      // go to top of workers list
      window.scrollTo({top: document.getElementById('workersGrid').offsetTop - 60, behavior:'smooth'});
    }

    /* -- init on load -- */
    document.addEventListener('DOMContentLoaded', ()=>{
      renderWorkersGrid('workersGrid');
      renderMaterialsGrid('materialsGrid');
      // materials page grid separately
      renderMaterialsPage();
      // set role pill text
      const role = localStorage.getItem('deshit_role') || 'client';
      const pill = document.getElementById('rolePill'); if(pill) pill.innerText = role === 'client' ? 'Client' : 'Worker';
      // default show home
      navigate('home');
    });

    /* -- Accessibility: allow Enter to trigger search when typing in q2 */
    document.getElementById('q2').addEventListener('keydown', function(e){
      if(e.key === 'Enter') doSearch();
    });
  </script>
</body>
</html>


