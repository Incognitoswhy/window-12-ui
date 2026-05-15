[windows_12_interactive.html](https://github.com/user-attachments/files/27789030/windows_12_interactive.html)


<style>
* { margin:0; padding:0; box-sizing:border-box; }
body { font-family: 'Segoe UI', system-ui, sans-serif; background:#0a0a1a; color:#fff; height:620px; overflow:hidden; user-select:none; }
.desktop { width:100%; height:620px; background:linear-gradient(135deg,#0d1b3e 0%,#1a1040 40%,#0d2b3e 100%); position:relative; overflow:hidden; }
.orb { position:absolute; border-radius:50%; pointer-events:none; }
.orb1 { width:400px;height:300px;background:rgba(0,80,200,0.18);top:-80px;left:-80px;filter:blur(70px); }
.orb2 { width:350px;height:350px;background:rgba(80,0,180,0.15);bottom:60px;right:-60px;filter:blur(70px); }
.orb3 { width:250px;height:250px;background:rgba(0,180,160,0.12);top:30%;left:40%;filter:blur(60px); }

.topbar { position:absolute;top:0;left:0;right:0;height:34px;background:rgba(255,255,255,0.04);backdrop-filter:blur(20px);border-bottom:0.5px solid rgba(255,255,255,0.09);display:flex;align-items:center;justify-content:space-between;padding:0 14px;z-index:200; }
.topbar-l { display:flex;align-items:center;gap:10px;font-size:11px;color:rgba(255,255,255,0.6); }
.topbar-r { display:flex;align-items:center;gap:12px;font-size:11px;color:rgba(255,255,255,0.65); }
.ai-badge { background:linear-gradient(90deg,#0078d4,#8b5cf6);color:#fff;font-size:10px;font-weight:600;padding:2px 8px;border-radius:10px; }

.desktop-icons { position:absolute;top:50px;left:18px;display:flex;flex-direction:column;gap:10px; }
.dicon { display:flex;flex-direction:column;align-items:center;gap:4px;cursor:pointer;padding:7px;border-radius:10px;width:66px;transition:background 0.15s; }
.dicon:hover { background:rgba(255,255,255,0.09); }
.dicon-img { width:40px;height:40px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:20px; }
.dicon-lbl { font-size:10px;color:rgba(255,255,255,0.82);text-align:center;text-shadow:0 1px 4px rgba(0,0,0,0.9); }

.ai-bar { position:absolute;top:50px;left:50%;transform:translateX(-50%);width:360px;background:rgba(255,255,255,0.07);backdrop-filter:blur(40px);border:0.5px solid rgba(255,255,255,0.14);border-radius:14px;padding:11px 14px; }
.ai-label { font-size:11px;color:rgba(255,255,255,0.4);margin-bottom:8px;display:flex;align-items:center;gap:6px; }
.ai-dot { width:6px;height:6px;border-radius:50%;background:#0078d4;animation:pulse 2s infinite; }
@keyframes pulse{0%,100%{opacity:1}50%{opacity:0.3}}
.chips { display:flex;gap:5px;flex-wrap:wrap; }
.chip { background:rgba(255,255,255,0.07);border:0.5px solid rgba(255,255,255,0.14);border-radius:20px;padding:4px 10px;font-size:11px;color:rgba(255,255,255,0.8);cursor:pointer;transition:background 0.15s; }
.chip:hover { background:rgba(0,120,212,0.3);border-color:rgba(0,120,212,0.5); }

.widgets { position:absolute;top:50px;right:16px;display:flex;flex-direction:column;gap:9px;width:200px; }
.wcard { background:rgba(255,255,255,0.06);backdrop-filter:blur(30px);border:0.5px solid rgba(255,255,255,0.11);border-radius:13px;padding:12px 14px; }
.wtitle { font-size:10px;color:rgba(255,255,255,0.45);margin-bottom:6px;text-transform:uppercase;letter-spacing:0.8px; }
.temp { font-size:32px;font-weight:300; }
.wsub { font-size:11px;color:rgba(255,255,255,0.45);margin-top:2px; }
.cal-grid { display:grid;grid-template-columns:repeat(7,1fr);gap:2px;margin-top:5px; }
.cd { font-size:10px;text-align:center;padding:3px 1px;color:rgba(255,255,255,0.45); }
.cd.today { background:#0078d4;color:#fff;border-radius:50%;font-weight:600; }
.cd.dim { color:rgba(255,255,255,0.18); }

.window { position:absolute;background:rgba(15,15,35,0.88);backdrop-filter:blur(50px);border:0.5px solid rgba(255,255,255,0.13);border-radius:13px;overflow:hidden;box-shadow:0 24px 70px rgba(0,0,0,0.55);display:none; }
.window.active { display:block; }
.wtitlebar { height:34px;background:rgba(255,255,255,0.04);border-bottom:0.5px solid rgba(255,255,255,0.08);display:flex;align-items:center;padding:0 12px;gap:10px;cursor:move; }
.wctrl { display:flex;gap:5px; }
.wc { width:11px;height:11px;border-radius:50%;cursor:pointer; }
.wc-r { background:#ff5f57; }
.wc-y { background:#febc2e; }
.wc-g { background:#28c840; }
.wtname { font-size:11px;color:rgba(255,255,255,0.55);flex:1;text-align:center; }

.explorer-win { top:100px;left:100px;width:500px; }
.exp-sidebar { width:130px;float:left;height:240px;border-right:0.5px solid rgba(255,255,255,0.08);padding:10px 8px; }
.si { font-size:11px;color:rgba(255,255,255,0.58);padding:5px 7px;border-radius:7px;cursor:pointer;display:flex;align-items:center;gap:6px;margin-bottom:2px; }
.si:hover { background:rgba(255,255,255,0.06); }
.si.act { background:rgba(0,120,212,0.22);color:#78c7ff; }
.exp-main { margin-left:130px;padding:10px; }
.fgrid { display:grid;grid-template-columns:repeat(4,1fr);gap:7px; }
.fitem { display:flex;flex-direction:column;align-items:center;gap:3px;padding:7px 4px;border-radius:7px;cursor:pointer; }
.fitem:hover { background:rgba(255,255,255,0.07); }
.ficon { font-size:26px; }
.fname { font-size:9px;color:rgba(255,255,255,0.68);text-align:center; }
.exp-footer { border-top:0.5px solid rgba(255,255,255,0.08);padding:7px 12px;display:flex;align-items:center;gap:8px;clear:both; }
.sbar { display:flex;align-items:center;background:rgba(255,255,255,0.07);border:0.5px solid rgba(255,255,255,0.11);border-radius:7px;padding:4px 9px;gap:6px;flex:1; }
.sbar input { background:none;border:none;outline:none;color:rgba(255,255,255,0.8);font-size:11px;width:100%; }
.sbar input::placeholder { color:rgba(255,255,255,0.3); }

.settings-win { top:80px;left:80px;width:480px; }
.settings-body { display:flex;height:280px; }
.stabs { width:130px;border-right:0.5px solid rgba(255,255,255,0.08);padding:10px 8px; }
.stab { font-size:11px;color:rgba(255,255,255,0.58);padding:6px 8px;border-radius:7px;cursor:pointer;margin-bottom:2px;display:flex;align-items:center;gap:7px; }
.stab:hover { background:rgba(255,255,255,0.06); }
.stab.act { background:rgba(0,120,212,0.22);color:#78c7ff; }
.spanel { flex:1;padding:14px; }
.spanel h3 { font-size:13px;font-weight:500;margin-bottom:12px;color:rgba(255,255,255,0.85); }
.srow { display:flex;align-items:center;justify-content:space-between;margin-bottom:10px; }
.srow-label { font-size:11px;color:rgba(255,255,255,0.6); }
.toggle { width:36px;height:20px;background:rgba(255,255,255,0.15);border-radius:10px;position:relative;cursor:pointer;transition:background 0.2s; }
.toggle.on { background:#0078d4; }
.toggle::after { content:'';position:absolute;width:16px;height:16px;background:#fff;border-radius:50%;top:2px;left:2px;transition:left 0.2s; }
.toggle.on::after { left:18px; }
.slider-row { margin-bottom:10px; }
.slider-row label { font-size:11px;color:rgba(255,255,255,0.6);display:flex;justify-content:space-between;margin-bottom:4px; }
.slider-row input[type=range] { width:100%;accent-color:#0078d4; }

.copilot-win { top:90px;left:90px;width:340px; }
.cop-body { padding:12px;height:260px;display:flex;flex-direction:column; }
.cop-msgs { flex:1;overflow-y:auto;display:flex;flex-direction:column;gap:8px;margin-bottom:10px; }
.cop-msgs::-webkit-scrollbar { width:4px; }
.cop-msgs::-webkit-scrollbar-thumb { background:rgba(255,255,255,0.15);border-radius:2px; }
.msg { max-width:85%;font-size:11px;line-height:1.5;padding:7px 10px;border-radius:10px; }
.msg-ai { background:rgba(0,120,212,0.2);color:rgba(255,255,255,0.85);align-self:flex-start;border-radius:4px 10px 10px 10px; }
.msg-user { background:rgba(255,255,255,0.1);color:rgba(255,255,255,0.8);align-self:flex-end;border-radius:10px 4px 10px 10px; }
.cop-input { display:flex;gap:6px;align-items:center; }
.cop-input input { flex:1;background:rgba(255,255,255,0.07);border:0.5px solid rgba(255,255,255,0.12);border-radius:8px;padding:6px 10px;color:#fff;font-size:11px;outline:none; }
.cop-input input::placeholder { color:rgba(255,255,255,0.3); }
.cop-send { background:#0078d4;border:none;border-radius:7px;width:28px;height:28px;cursor:pointer;color:#fff;font-size:14px;display:flex;align-items:center;justify-content:center; }

.taskbar { position:absolute;bottom:0;left:0;right:0;height:52px;background:rgba(8,8,22,0.8);backdrop-filter:blur(40px);border-top:0.5px solid rgba(255,255,255,0.07);display:flex;align-items:center;justify-content:center;gap:3px;z-index:200; }
.titem { width:44px;height:44px;border-radius:9px;display:flex;align-items:center;justify-content:center;font-size:21px;cursor:pointer;position:relative;transition:background 0.15s,transform 0.12s; }
.titem:hover { background:rgba(255,255,255,0.1);transform:translateY(-4px); }
.titem.running::after { content:'';position:absolute;bottom:2px;left:50%;transform:translateX(-50%);width:4px;height:4px;border-radius:50%;background:#0078d4; }
.tsep { width:1px;height:26px;background:rgba(255,255,255,0.1);margin:0 3px; }
.startbtn { width:44px;height:44px;border-radius:9px;display:flex;align-items:center;justify-content:center;cursor:pointer;transition:background 0.15s,transform 0.12s; }
.startbtn:hover { background:rgba(255,255,255,0.1);transform:translateY(-4px); }
.winlogo { display:grid;grid-template-columns:1fr 1fr;gap:2px;width:17px;height:17px; }
.wsq { border-radius:2px; }
.s1{background:#f25022}.s2{background:#7fba00}.s3{background:#00a4ef}.s4{background:#ffb900}
.tray { position:absolute;right:12px;display:flex;align-items:center;gap:10px; }
.ticon { font-size:13px;color:rgba(255,255,255,0.6);cursor:pointer; }
.ticon:hover { color:#fff; }
.tclock { text-align:right; }
.tc-time { font-size:11px;color:rgba(255,255,255,0.8); }
.tc-date { font-size:10px;color:rgba(255,255,255,0.42); }

.start-menu { position:absolute;bottom:56px;left:50%;transform:translateX(-50%);width:500px;background:rgba(20,20,45,0.95);backdrop-filter:blur(60px);border:0.5px solid rgba(255,255,255,0.14);border-radius:16px;padding:20px;display:none;z-index:300; }
.start-menu.open { display:block; }
.sm-search { display:flex;align-items:center;gap:8px;background:rgba(255,255,255,0.08);border:0.5px solid rgba(255,255,255,0.14);border-radius:10px;padding:8px 12px;margin-bottom:16px; }
.sm-search input { background:none;border:none;outline:none;color:#fff;font-size:13px;flex:1; }
.sm-search input::placeholder { color:rgba(255,255,255,0.35); }
.sm-pinned { margin-bottom:14px; }
.sm-sect { font-size:11px;color:rgba(255,255,255,0.4);margin-bottom:8px;text-transform:uppercase;letter-spacing:0.8px; }
.sm-apps { display:grid;grid-template-columns:repeat(6,1fr);gap:8px; }
.sm-app { display:flex;flex-direction:column;align-items:center;gap:5px;padding:8px 4px;border-radius:9px;cursor:pointer; }
.sm-app:hover { background:rgba(255,255,255,0.08); }
.sm-app-icon { width:36px;height:36px;border-radius:8px;display:flex;align-items:center;justify-content:center;font-size:18px; }
.sm-app-name { font-size:10px;color:rgba(255,255,255,0.75);text-align:center; }
.sm-user { display:flex;align-items:center;gap:10px;border-top:0.5px solid rgba(255,255,255,0.08);padding-top:12px;margin-top:4px; }
.sm-avatar { width:32px;height:32px;border-radius:50%;background:linear-gradient(135deg,#0078d4,#8b5cf6);display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:600; }
.sm-uname { font-size:12px;color:rgba(255,255,255,0.8); }
.sm-power { margin-left:auto;background:rgba(255,255,255,0.07);border:none;border-radius:7px;width:30px;height:30px;cursor:pointer;color:rgba(255,255,255,0.6);font-size:14px;display:flex;align-items:center;justify-content:center; }
</style>

<div class="desktop">
  <div class="orb orb1"></div>
  <div class="orb orb2"></div>
  <div class="orb orb3"></div>

  <div class="topbar">
    <div class="topbar-l">
      <span class="ai-badge">Copilot+</span>
      <span>Windows 12 Pro</span>
    </div>
    <div class="topbar-r">
      <span id="tb-bat">🔋 94%</span>
      <span>📶 Wi-Fi</span>
      <span>🔊</span>
    </div>
  </div>

  <div class="desktop-icons">
    <div class="dicon" onclick="openWin('explorer')">
      <div class="dicon-img" style="background:linear-gradient(135deg,#0078d4,#005a9e);">🗂️</div>
      <span class="dicon-lbl">Files</span>
    </div>
    <div class="dicon" onclick="openWin('settings')">
      <div class="dicon-img" style="background:linear-gradient(135deg,#555,#333);">⚙️</div>
      <span class="dicon-lbl">Settings</span>
    </div>
    <div class="dicon" onclick="openWin('copilot')">
      <div class="dicon-img" style="background:linear-gradient(135deg,#8b5cf6,#6d28d9);">🤖</div>
      <span class="dicon-lbl">Copilot</span>
    </div>
    <div class="dicon">
      <div class="dicon-img" style="background:linear-gradient(135deg,#107c41,#0a5c2e);">📊</div>
      <span class="dicon-lbl">Excel</span>
    </div>
  </div>

  <div class="ai-bar">
    <div class="ai-label"><div class="ai-dot"></div> Copilot AI — Good afternoon!</div>
    <div class="chips">
      <div class="chip" onclick="openWin('copilot')">✨ Ask Copilot</div>
      <div class="chip" onclick="openWin('explorer')">📁 Open Files</div>
      <div class="chip" onclick="openWin('settings')">⚙️ Settings</div>
      <div class="chip">🎨 Create image</div>
    </div>
  </div>

  <div class="widgets">
    <div class="wcard">
      <div class="wtitle">Weather · Islamabad</div>
      <div style="font-size:28px;margin-bottom:2px;">⛅</div>
      <div class="temp">28°C</div>
      <div class="wsub">Partly Cloudy · Feels 31°</div>
    </div>
    <div class="wcard">
      <div class="wtitle">May 2026</div>
      <div class="cal-grid">
        <div class="cd" style="color:rgba(255,255,255,0.28);font-size:9px;">Su</div>
        <div class="cd" style="color:rgba(255,255,255,0.28);font-size:9px;">Mo</div>
        <div class="cd" style="color:rgba(255,255,255,0.28);font-size:9px;">Tu</div>
        <div class="cd" style="color:rgba(255,255,255,0.28);font-size:9px;">We</div>
        <div class="cd" style="color:rgba(255,255,255,0.28);font-size:9px;">Th</div>
        <div class="cd" style="color:rgba(255,255,255,0.28);font-size:9px;">Fr</div>
        <div class="cd" style="color:rgba(255,255,255,0.28);font-size:9px;">Sa</div>
        <div class="cd dim"></div><div class="cd dim"></div><div class="cd dim"></div>
        <div class="cd">1</div><div class="cd">2</div><div class="cd">3</div><div class="cd">4</div>
        <div class="cd">5</div><div class="cd">6</div><div class="cd">7</div><div class="cd">8</div>
        <div class="cd">9</div><div class="cd">10</div><div class="cd">11</div><div class="cd">12</div>
        <div class="cd">13</div><div class="cd">14</div><div class="cd today">15</div><div class="cd">16</div>
        <div class="cd">17</div><div class="cd">18</div><div class="cd">19</div>
      </div>
    </div>
  </div>

  <!-- File Explorer Window -->
  <div class="window explorer-win" id="win-explorer">
    <div class="wtitlebar" onmousedown="dragStart(event,'win-explorer')">
      <div class="wctrl">
        <div class="wc wc-r" onclick="closeWin('explorer')"></div>
        <div class="wc wc-y" onclick="closeWin('explorer')"></div>
        <div class="wc wc-g"></div>
      </div>
      <div class="wtname">📁 File Explorer</div>
    </div>
    <div style="overflow:hidden;">
      <div class="exp-sidebar">
        <div class="si act">🏠 Home</div>
        <div class="si">📁 Documents</div>
        <div class="si">🖼️ Pictures</div>
        <div class="si">🎵 Music</div>
        <div class="si">📥 Downloads</div>
        <div class="si">☁️ OneDrive</div>
        <div class="si">🤖 AI Gallery</div>
      </div>
      <div class="exp-main">
        <div style="font-size:10px;color:rgba(255,255,255,0.38);margin-bottom:8px;">Recent files</div>
        <div class="fgrid">
          <div class="fitem"><div class="ficon">📄</div><div class="fname">Report.docx</div></div>
          <div class="fitem"><div class="ficon">📊</div><div class="fname">Budget.xlsx</div></div>
          <div class="fitem"><div class="ficon">🖼️</div><div class="fname">Photo.png</div></div>
          <div class="fitem"><div class="ficon">📑</div><div class="fname">Notes.pdf</div></div>
          <div class="fitem"><div class="ficon">🎬</div><div class="fname">Clip.mp4</div></div>
          <div class="fitem"><div class="ficon">📝</div><div class="fname">Ideas.txt</div></div>
          <div class="fitem"><div class="ficon">📂</div><div class="fname">Projects</div></div>
          <div class="fitem"><div class="ficon">🗄️</div><div class="fname">Archive</div></div>
        </div>
      </div>
    </div>
    <div class="exp-footer">
      <div class="sbar"><span style="font-size:12px;color:rgba(255,255,255,0.38);">🔍</span><input type="text" placeholder="Search with AI..."/></div>
      <span style="font-size:10px;color:rgba(255,255,255,0.3);">8 items</span>
    </div>
  </div>

  <!-- Settings Window -->
  <div class="window settings-win" id="win-settings">
    <div class="wtitlebar" onmousedown="dragStart(event,'win-settings')">
      <div class="wctrl">
        <div class="wc wc-r" onclick="closeWin('settings')"></div>
        <div class="wc wc-y" onclick="closeWin('settings')"></div>
        <div class="wc wc-g"></div>
      </div>
      <div class="wtname">⚙️ Settings</div>
    </div>
    <div class="settings-body">
      <div class="stabs">
        <div class="stab act" onclick="showTab('display')">🖥️ Display</div>
        <div class="stab" onclick="showTab('personalize')">🎨 Personalize</div>
        <div class="stab" onclick="showTab('network')">📶 Network</div>
        <div class="stab" onclick="showTab('copilot')">🤖 Copilot AI</div>
        <div class="stab" onclick="showTab('privacy')">🔒 Privacy</div>
      </div>
      <div class="spanel" id="tab-display">
        <h3>Display</h3>
        <div class="srow"><span class="srow-label">Night light</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">HDR</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Auto dark mode</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="slider-row">
          <label><span>Brightness</span><span id="br-val">75%</span></label>
          <input type="range" min="0" max="100" value="75" oninput="document.getElementById('br-val').textContent=this.value+'%'">
        </div>
        <div class="slider-row">
          <label><span>Scale</span><span id="sc-val">125%</span></label>
          <input type="range" min="100" max="200" step="25" value="125" oninput="document.getElementById('sc-val').textContent=this.value+'%'">
        </div>
      </div>
      <div class="spanel" id="tab-personalize" style="display:none">
        <h3>Personalize</h3>
        <div class="srow"><span class="srow-label">Transparency effects</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Animations</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Dynamic wallpaper</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
      </div>
      <div class="spanel" id="tab-network" style="display:none">
        <h3>Network</h3>
        <div class="srow"><span class="srow-label">Wi-Fi</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Bluetooth</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Hotspot</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
      </div>
      <div class="spanel" id="tab-copilot" style="display:none">
        <h3>Copilot AI</h3>
        <div class="srow"><span class="srow-label">Always-on Copilot</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Recall (AI memory)</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">AI image generation</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
      </div>
      <div class="spanel" id="tab-privacy" style="display:none">
        <h3>Privacy</h3>
        <div class="srow"><span class="srow-label">Send diagnostics</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Location services</span><div class="toggle on" onclick="this.classList.toggle('on')"></div></div>
        <div class="srow"><span class="srow-label">Ad personalisation</span><div class="toggle" onclick="this.classList.toggle('on')"></div></div>
      </div>
    </div>
  </div>

  <!-- Copilot Window -->
  <div class="window copilot-win" id="win-copilot">
    <div class="wtitlebar" onmousedown="dragStart(event,'win-copilot')">
      <div class="wctrl">
        <div class="wc wc-r" onclick="closeWin('copilot')"></div>
        <div class="wc wc-y" onclick="closeWin('copilot')"></div>
        <div class="wc wc-g"></div>
      </div>
      <div class="wtname">🤖 Copilot AI</div>
    </div>
    <div class="cop-body">
      <div class="cop-msgs" id="cop-msgs">
        <div class="msg msg-ai">Hi! I'm Copilot, your Windows 12 AI assistant. How can I help you today? ✨</div>
      </div>
      <div class="cop-input">
        <input id="cop-in" type="text" placeholder="Ask me anything..." onkeydown="if(event.key==='Enter')sendCop()"/>
        <button class="cop-send" onclick="sendCop()">➤</button>
      </div>
    </div>
  </div>

  <!-- Start Menu -->
  <div class="start-menu" id="start-menu">
    <div class="sm-search">
      <span style="font-size:14px;color:rgba(255,255,255,0.4);">🔍</span>
      <input type="text" placeholder="Search apps, files, settings..."/>
    </div>
    <div class="sm-pinned">
      <div class="sm-sect">Pinned</div>
      <div class="sm-apps">
        <div class="sm-app" onclick="openWin('explorer');toggleStart()"><div class="sm-app-icon" style="background:linear-gradient(135deg,#0078d4,#005a9e);">🗂️</div><div class="sm-app-name">Files</div></div>
        <div class="sm-app" onclick="openWin('copilot');toggleStart()"><div class="sm-app-icon" style="background:linear-gradient(135deg,#8b5cf6,#6d28d9);">🤖</div><div class="sm-app-name">Copilot</div></div>
        <div class="sm-app" onclick="openWin('settings');toggleStart()"><div class="sm-app-icon" style="background:linear-gradient(135deg,#555,#333);">⚙️</div><div class="sm-app-name">Settings</div></div>
        <div class="sm-app"><div class="sm-app-icon" style="background:linear-gradient(135deg,#107c41,#085a2e);">📊</div><div class="sm-app-name">Excel</div></div>
        <div class="sm-app"><div class="sm-app-icon" style="background:linear-gradient(135deg,#2b7cd3,#1a5ca8);">📄</div><div class="sm-app-name">Word</div></div>
        <div class="sm-app"><div class="sm-app-icon" style="background:linear-gradient(135deg,#e4272b,#a81a1d);">▶️</div><div class="sm-app-name">Media</div></div>
      </div>
    </div>
    <div class="sm-user">
      <div class="sm-avatar">U</div>
      <span class="sm-uname">User</span>
      <button class="sm-power" title="Power">⏻</button>
    </div>
  </div>

  <!-- Taskbar -->
  <div class="taskbar">
    <div class="startbtn" onclick="toggleStart()" id="startbtn">
      <div class="winlogo"><div class="wsq s1"></div><div class="wsq s2"></div><div class="wsq s3"></div><div class="wsq s4"></div></div>
    </div>
    <div class="tsep"></div>
    <div class="titem running" id="tb-explorer" title="File Explorer" onclick="openWin('explorer')">🗂️</div>
    <div class="titem" id="tb-edge" title="Edge">🌐</div>
    <div class="titem" id="tb-settings" title="Settings" onclick="openWin('settings')">⚙️</div>
    <div class="titem running" id="tb-copilot" title="Copilot" onclick="openWin('copilot')">🤖</div>
    <div class="titem" title="Store">🏪</div>
    <div class="titem" title="Photos">🖼️</div>
    <div class="titem" title="Music">🎵</div>
    <div class="tsep"></div>
    <div class="titem" title="Terminal">⬛</div>
    <div class="tray">
      <span class="ticon">🔇</span>
      <span class="ticon">📶</span>
      <span class="ticon">🔋</span>
      <div class="tclock"><div class="tc-time" id="clk-t"></div><div class="tc-date" id="clk-d"></div></div>
    </div>
  </div>
</div>

<script>
const wins = { explorer:'win-explorer', settings:'win-settings', copilot:'win-copilot' };
const openSet = new Set();

function openWin(name) {
  const el = document.getElementById(wins[name]);
  if (!el) return;
  el.classList.add('active');
  el.style.zIndex = 150 + openSet.size;
  openSet.add(name);
}

function closeWin(name) {
  const el = document.getElementById(wins[name]);
  if (el) el.classList.remove('active');
  openSet.delete(name);
}

function toggleStart() {
  document.getElementById('start-menu').classList.toggle('open');
}

document.addEventListener('click', function(e) {
  const sm = document.getElementById('start-menu');
  const sb = document.getElementById('startbtn');
  if (!sm.contains(e.target) && !sb.contains(e.target)) sm.classList.remove('open');
});

function showTab(name) {
  ['display','personalize','network','copilot','privacy'].forEach(t => {
    const el = document.getElementById('tab-'+t);
    if (el) el.style.display = t === name ? 'block' : 'none';
  });
  document.querySelectorAll('.stab').forEach((el, i) => el.classList.remove('act'));
  const tabs = ['display','personalize','network','copilot','privacy'];
  const idx = tabs.indexOf(name);
  document.querySelectorAll('.stab')[idx].classList.add('act');
}

const replies = [
  "Sure! I can help with that. What would you like to know?",
  "Great question! As your AI assistant, I'm always learning to serve you better.",
  "I've searched your files and the web for that — here's what I found...",
  "Done! I've made that change for you. Anything else?",
  "I recommend checking Settings → Copilot AI for more options.",
  "That's an interesting request! Let me process that for you... ✨"
];
let replyIdx = 0;

function sendCop() {
  const input = document.getElementById('cop-in');
  const msgs = document.getElementById('cop-msgs');
  const text = input.value.trim();
  if (!text) return;
  const um = document.createElement('div');
  um.className = 'msg msg-user';
  um.textContent = text;
  msgs.appendChild(um);
  input.value = '';
  msgs.scrollTop = msgs.scrollHeight;
  setTimeout(() => {
    const am = document.createElement('div');
    am.className = 'msg msg-ai';
    am.textContent = replies[replyIdx % replies.length];
    replyIdx++;
    msgs.appendChild(am);
    msgs.scrollTop = msgs.scrollHeight;
  }, 600);
}

let dragEl = null, ox = 0, oy = 0;
function dragStart(e, id) {
  dragEl = document.getElementById(id);
  dragEl.style.zIndex = 180;
  ox = e.clientX - dragEl.offsetLeft;
  oy = e.clientY - dragEl.offsetTop;
  document.onmousemove = function(ev) {
    if (!dragEl) return;
    let nx = ev.clientX - ox;
    let ny = ev.clientY - oy;
    nx = Math.max(0, Math.min(nx, window.innerWidth - dragEl.offsetWidth));
    ny = Math.max(34, Math.min(ny, 568 - dragEl.offsetHeight));
    dragEl.style.left = nx + 'px';
    dragEl.style.top = ny + 'px';
  };
  document.onmouseup = function() { dragEl = null; document.onmousemove = null; };
}

function updateClock() {
  const now = new Date();
  document.getElementById('clk-t').textContent = now.toLocaleTimeString('en-US',{hour:'2-digit',minute:'2-digit'});
  document.getElementById('clk-d').textContent = now.toLocaleDateString('en-US',{month:'short',day:'numeric',year:'numeric'});
}
updateClock();
setInterval(updateClock, 1000);

openWin('explorer');
openWin('copilot');
</script>
