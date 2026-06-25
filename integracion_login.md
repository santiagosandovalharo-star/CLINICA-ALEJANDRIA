# Integración del login institucional — Camino A (reskin en index.html)

REGLAS:
- NO tocar JavaScript (doLogin, checkLoginCloud, entrarApp quedan igual).
- CONSERVAR los IDs: login-screen, login-user, login-pass, login-btn, login-error.
- El botón #login-btn debe quedar SOLO con texto (el JS le hace textContent='Entrando...').
- Son 3 ediciones. Aplicar las tres, guardar (Cmd+S), y probar.
- Para revertir: deshacer las 3 ediciones. Todo está respaldado en GitHub.

================================================================
EDICIÓN 1 — Fuentes en el <head>
================================================================
BUSCAR esta línea (línea 6):

<title>ERP Beta - Clinica Alejandria</title>

AGREGAR JUSTO DEBAJO estas tres líneas:

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Source+Serif+4:ital,opsz,wght@0,8..60,400;0,8..60,500;0,8..60,600;1,8..60,400&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">


================================================================
EDICIÓN 2 — CSS del login  (reemplazar el bloque de estilos)
================================================================
REEMPLAZAR EXACTAMENTE este bloque (desde .login-overlay hasta .login-version):

.login-overlay{position:fixed;top:0;left:0;width:100%;height:100%;background:linear-gradient(135deg,#1a3a5c 0%,#1e4d7a 50%,#1a3a5c 100%);display:flex;align-items:center;justify-content:center;z-index:9999}
.login-box{background:#fff;border-radius:16px;padding:40px 36px;width:360px;box-shadow:0 20px 60px rgba(0,0,0,.3);text-align:center}
.login-logo{width:72px;height:72px;border-radius:50%;background:linear-gradient(135deg,#1a3a5c,#2a6cb0);display:flex;align-items:center;justify-content:center;font-size:28px;font-weight:800;color:#fff;margin:0 auto 16px;border:3px solid #e8edf2}
.login-title{font-size:20px;font-weight:700;color:#1a3a5c;margin-bottom:4px}
.login-sub{font-size:12px;color:#8a95a3;margin-bottom:24px}
.login-field{margin-bottom:16px;text-align:left}
.login-field label{display:block;font-size:11px;font-weight:600;color:#5a6474;margin-bottom:5px;text-transform:uppercase;letter-spacing:.5px}
.login-field input{width:100%;padding:12px 14px;font-size:14px;border:1.5px solid #dce2e8;border-radius:8px;outline:none;transition:border .2s}
.login-field input:focus{border-color:#2a6cb0;box-shadow:0 0 0 3px rgba(42,108,176,.12)}
.login-btn{width:100%;padding:13px;font-size:15px;font-weight:700;border-radius:8px;cursor:pointer;border:none;background:linear-gradient(135deg,#1a3a5c,#2a6cb0);color:#fff;transition:opacity .2s;margin-top:4px}
.login-btn:hover{opacity:.9}
.login-btn:active{opacity:.8}
.login-error{display:none;font-size:12px;color:#b83232;background:#fce8e8;border:1px solid #f0b8b8;border-radius:6px;padding:8px 12px;margin-top:12px}
.login-footer{font-size:10px;color:#aab4c0;margin-top:20px}
.login-version{font-size:9px;color:#c0c8d2;margin-top:8px}

POR ESTE BLOQUE NUEVO:

.login-overlay{position:fixed;top:0;left:0;width:100%;height:100%;background:#eef1f4;display:flex;align-items:center;justify-content:center;z-index:9999;padding:24px;box-sizing:border-box}
.al-card{display:flex;width:100%;max-width:920px;min-height:520px;background:#fff;border-radius:14px;overflow:hidden;box-shadow:0 1px 3px rgba(14,44,71,.06),0 12px 40px rgba(14,44,71,.10);font-family:'Inter',system-ui,sans-serif}
.al-left{flex:0 0 42%;position:relative;background:#0e2c47;padding:38px;display:flex;flex-direction:column;justify-content:flex-end;overflow:hidden}
.al-geo{position:absolute;inset:0;opacity:.55}
.al-brand{position:relative}
.al-mark{font-family:'Source Serif 4',Georgia,serif;font-weight:600;color:#fff;font-size:32px;letter-spacing:4px;line-height:1}
.al-his{color:#9fb3c8;font-size:10px;letter-spacing:3px;margin-top:11px}
.al-rule{width:38px;height:1px;background:#c7a35a;margin:20px 0 13px}
.al-tag{font-family:'Source Serif 4',Georgia,serif;font-style:italic;color:#c7a35a;font-size:13.5px}
.al-right{flex:1;display:flex;align-items:center;justify-content:center;padding:40px}
.al-form{width:100%;max-width:300px}
.al-h{font-family:'Source Serif 4',Georgia,serif;font-weight:500;color:#0e2c47;font-size:29px;letter-spacing:-.01em;margin:0}
.al-sub{color:#64748b;font-size:13px;margin:7px 0 26px}
.al-lab{display:block;font-size:11px;color:#64748b;margin:16px 0 6px}
.al-in{width:100%;box-sizing:border-box;font-family:'Inter',system-ui,sans-serif;font-size:14px;color:#0e2c47;padding:11px 13px;border:1px solid #d9e0e8;border-radius:8px;background:#fff;outline:none;transition:border-color .15s,box-shadow .15s}
.al-in:focus{border-color:#1c5d99;box-shadow:0 0 0 3px rgba(28,93,153,.13)}
.al-pw{position:relative}
.al-eye{position:absolute;right:6px;top:50%;transform:translateY(-50%);background:none;border:none;color:#64748b;font-size:12px;cursor:pointer;padding:6px;font-family:'Inter',system-ui,sans-serif}
#login-btn{width:100%;font-family:'Inter',system-ui,sans-serif;font-size:14px;font-weight:500;color:#fff;background:#1c5d99;border:none;border-radius:8px;padding:12px;cursor:pointer;margin-top:22px;transition:background .15s}
#login-btn:hover{background:#184f83}
.login-error{display:none;font-size:12.5px;color:#b3261e;background:#fdecea;border:1px solid #f3c9c4;border-radius:8px;padding:9px 12px;margin-top:14px}
.al-foot{font-size:10px;color:#94a3b8;margin-top:20px;letter-spacing:.3px}
@media (max-width:820px){.al-card{flex-direction:column;max-width:440px;min-height:0}.al-left{flex:0 0 auto;min-height:130px;padding:26px 30px;justify-content:center}.al-mark{font-size:25px}.al-right{padding:30px 26px 38px}}


================================================================
EDICIÓN 3 — Markup del login  (reemplazar el HTML)
================================================================
REEMPLAZAR EXACTAMENTE este bloque (desde <div class="login-overlay" hasta su </div> de cierre):

<div class="login-overlay" id="login-screen">
  <div class="login-box">
    <div class="login-logo">CA</div>
    <div class="login-title">Clinica Alejandria</div>
    <div class="login-sub">Plataforma de Gestion Hospitalaria</div>
    <div class="login-field">
      <label>Usuario</label>
      <input id="login-user" type="text" placeholder="Ingresa tu usuario" value="admin">
    </div>
    <div class="login-field">
      <label>Contrasena</label>
      <input id="login-pass" type="password" placeholder="Ingresa tu contrasena">
    </div>
    <button class="login-btn" id="login-btn">Iniciar sesion</button>
    <div class="login-error" id="login-error">Usuario o contrasena incorrectos</div>
    <div class="login-footer">Acceso restringido &middot; Solo personal autorizado</div>
    <div class="login-version">ERP Beta v1.0 &middot; Alejandria Core</div>
  </div>
</div>

POR ESTE BLOQUE NUEVO:

<div class="login-overlay" id="login-screen">
  <div class="al-card">
    <div class="al-left" aria-hidden="true">
      <svg class="al-geo" viewBox="0 0 420 560" preserveAspectRatio="xMidYMid slice">
        <g stroke="#ffffff" stroke-width="0.6" fill="none">
          <line x1="40" y1="0" x2="40" y2="560"/><line x1="110" y1="0" x2="110" y2="560"/>
          <line x1="180" y1="0" x2="180" y2="560"/><line x1="250" y1="0" x2="250" y2="560"/>
          <line x1="320" y1="0" x2="320" y2="560"/><line x1="390" y1="0" x2="390" y2="560"/>
          <line x1="0" y1="120" x2="420" y2="120"/><line x1="0" y1="280" x2="420" y2="280"/>
          <line x1="0" y1="440" x2="420" y2="440"/>
        </g>
        <g stroke="#ffffff" stroke-width="0.5" fill="none" opacity="0.6">
          <line x1="0" y1="200" x2="420" y2="60"/><line x1="0" y1="500" x2="420" y2="360"/>
        </g>
      </svg>
      <div class="al-brand">
        <div class="al-mark">ALEJANDR&Iacute;A</div>
        <div class="al-his">HOSPITAL INFORMATION SYSTEM</div>
        <div class="al-rule"></div>
        <div class="al-tag">Precision. Ethics. Innovation.</div>
      </div>
    </div>
    <div class="al-right">
      <div class="al-form">
        <div class="al-h">Bienvenido</div>
        <div class="al-sub">Ingrese sus credenciales institucionales.</div>
        <label class="al-lab" for="login-user">Correo electr&oacute;nico</label>
        <input class="al-in" id="login-user" type="email" placeholder="nombre@alejandria.mx" autocomplete="email">
        <label class="al-lab" for="login-pass">Contrase&ntilde;a</label>
        <div class="al-pw">
          <input class="al-in" id="login-pass" type="password" placeholder="&bull;&bull;&bull;&bull;&bull;&bull;&bull;&bull;" autocomplete="current-password">
          <button type="button" class="al-eye" aria-label="Mostrar contrase&ntilde;a" onclick="var p=document.getElementById('login-pass'),s=p.type==='password';p.type=s?'text':'password';this.textContent=s?'Ocultar':'Ver';">Ver</button>
        </div>
        <button class="login-btn" id="login-btn">Iniciar sesi&oacute;n</button>
        <div class="login-error" id="login-error">Correo o contrase&ntilde;a incorrectos</div>
        <div class="al-foot">Acceso restringido &middot; Solo personal autorizado</div>
      </div>
    </div>
  </div>
</div>

================================================================
CÓMO PROBAR (después de Cmd+S)
================================================================
1. Recargar index.html en Safari con consola abierta.
2. Ver el login institucional (panel azul con ALEJANDRÍA + formulario a la derecha).
3. Probar el ojo "Ver/Ocultar" de la contraseña.
4. Iniciar sesión con tu correo de siempre -> debe entrar igual que antes.
5. En consola debe seguir saliendo [ROLES] Rol activo: Dirección, sin errores rojos nuevos.
