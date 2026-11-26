```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Guía Digital de Citas | Clínica Integral Universitaria UNEVE</title>

  <!-- Tipografías institucionales: Plus Jakarta Sans para encabezados y Inter para lectura clínica -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Plus+Jakarta+Sans:wght@600;700;800&display=swap" rel="stylesheet">

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>

  <style>
    /* =========================================================================
       SISTEMA DE DISEÑO CLÍNICO-UNIVERSITARIO · CIU - UNEVE (IDENTIDAD NARANJA)
       ========================================================================= */
    :root {
      --naranja: #E67E22;
      --naranja-oscuro: #D35400;
      --naranja-suave: #FFF4EA;
      --crema: #FFF8F0;
      --gris-fondo: #F4F6F8;
      --superficie: #FFFFFF;
      --borde: #DCE2E8;
      --texto-primario: #1E293B;
      --texto-cuerpo: #334155;
      --texto-muted: #64748B;
      --acento-profundo: #162B40;
    }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 28px;
    }

    body {
      background-color: var(--gris-fondo);
      color: var(--texto-primario);
      font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', sans-serif;
      overflow-x: hidden;
      background-image:
        linear-gradient(180deg, rgba(230, 126, 34, 0.05) 0%, rgba(211, 84, 0, 0.025) 36%, rgba(244, 246, 248, 0) 100%);
    }

    h1, h2, h3, .font-display {
      font-family: 'Plus Jakarta Sans', 'Inter', sans-serif;
    }

    /* =========================================================================
       BARRA LATERAL INSTITUCIONAL NARANJA (ESCRITORIO) Y CABECERA MÓVIL
       ========================================================================= */
    .portal-sidebar {
      width: 300px;
      background: linear-gradient(180deg, var(--naranja) 0%, var(--naranja-oscuro) 100%);
      color: var(--superficie);
      padding: 24px 18px 28px;
      position: fixed;
      top: 0;
      left: 0;
      height: 100vh;
      overflow-y: auto;
      z-index: 40;
      border-right: 1px solid rgba(255, 255, 255, 0.22);
      box-shadow: 8px 0 28px rgba(163, 67, 11, 0.18);
    }

    .brand-lockup {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 10px;
      margin-bottom: 16px;
    }

    .brand-emblem-card {
      background: rgba(255, 255, 255, 0.14);
      border: 1px solid rgba(255, 255, 255, 0.28);
      border-radius: 16px;
      padding: 10px 8px;
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
      transition: background-color 0.2s ease, border-color 0.2s ease, transform 0.2s ease;
    }

    .brand-emblem-card:hover {
      background: rgba(255, 255, 255, 0.22);
      border-color: rgba(255, 255, 255, 0.55);
      transform: translateY(-2px);
    }

    .emblem-frame {
      width: 78px;
      height: 78px;
      border-radius: 50%;
      background-color: var(--superficie);
      padding: 6px;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 2.5px solid var(--superficie);
      box-shadow: 0 6px 16px rgba(0, 0, 0, 0.18);
      overflow: hidden;
    }

    .emblem-frame img {
      width: 100%;
      height: 100%;
      object-fit: contain;
      border-radius: 50%;
      display: block;
    }

    .emblem-caption {
      margin-top: 7px;
      font-size: 0.75rem;
      font-weight: 700;
      color: var(--superficie);
      line-height: 1.2;
      letter-spacing: 0.01em;
    }

    .sidebar-title-box {
      text-align: center;
      padding-bottom: 12px;
      margin-bottom: 14px;
      border-bottom: 1px solid rgba(255, 255, 255, 0.25);
    }

    .sidebar-title-box h2 {
      font-size: 1.15rem;
      font-weight: 800;
      letter-spacing: 0.06em;
      color: var(--superficie);
    }

    .sidebar-title-box p {
      font-size: 0.72rem;
      color: var(--crema);
      margin-top: 2px;
    }

    .sidebar-nav-link {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 10px;
      padding: 10px 13px;
      border-radius: 12px;
      color: var(--superficie);
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 600;
      margin-bottom: 6px;
      border: 1px solid transparent;
      transition: background-color 0.2s ease, color 0.2s ease, border-color 0.2s ease, transform 0.2s ease;
    }

    .sidebar-nav-link:hover {
      background-color: rgba(255, 255, 255, 0.16);
      color: var(--superficie);
      transform: translateX(2px);
    }

    .sidebar-nav-link.active {
      background-color: var(--superficie);
      color: var(--naranja-oscuro);
      font-weight: 700;
      border-color: var(--superficie);
      box-shadow: 0 6px 14px rgba(120, 48, 4, 0.22);
    }

    .nav-index-tag {
      font-size: 0.72rem;
      font-weight: 800;
      letter-spacing: 0.05em;
      padding: 2px 7px;
      border-radius: 999px;
      background-color: rgba(255, 255, 255, 0.18);
      color: var(--superficie);
    }

    .sidebar-nav-link.active .nav-index-tag {
      background-color: var(--naranja-suave);
      color: var(--naranja-oscuro);
    }

    /* =========================================================================
       CONTENEDOR PRINCIPAL Y TARJETAS EDITORIALES CLÍNICAS
       ========================================================================= */
    .portal-main {
      margin-left: 300px;
      width: calc(100% - 300px);
      padding: 28px 34px 40px;
      min-height: 100vh;
    }

    .hero-hospital {
      background: linear-gradient(125deg, var(--superficie) 0%, var(--crema) 62%, var(--naranja-suave) 100%);
      border: 1px solid var(--borde);
      border-top: 4px solid var(--naranja);
      border-radius: 22px;
      padding: 30px 28px;
      box-shadow: 0 10px 28px rgba(211, 84, 0, 0.07);
      margin-bottom: 24px;
    }

    .section-card {
      background-color: var(--superficie);
      border: 1px solid var(--borde);
      border-radius: 20px;
      padding: 26px 28px;
      margin-bottom: 22px;
      box-shadow: 0 6px 20px rgba(30, 41, 59, 0.045);
      transition: border-color 0.22s ease, box-shadow 0.22s ease;
    }

    .section-card:hover {
      border-color: #E5B892;
      box-shadow: 0 10px 26px rgba(211, 84, 0, 0.07);
    }

    .step-badge {
      display: inline-flex;
      align-items: center;
      gap: 6px;
      padding: 4px 11px;
      border-radius: 999px;
      background-color: var(--naranja-suave);
      color: var(--naranja-oscuro);
      border: 1px solid rgba(230, 126, 34, 0.35);
      font-size: 0.75rem;
      font-weight: 800;
      letter-spacing: 0.04em;
      text-transform: uppercase;
    }

    .route-pill {
      display: flex;
      align-items: center;
      gap: 10px;
      padding: 11px 14px;
      border-radius: 14px;
      background-color: var(--superficie);
      border: 1px solid var(--borde);
      text-decoration: none;
      color: var(--texto-primario);
      transition: transform 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
    }

    .route-pill:hover {
      transform: translateY(-2px);
      border-color: var(--naranja);
      box-shadow: 0 6px 14px rgba(211, 84, 0, 0.09);
    }

    /* Checklist interactivo del Paso 1 */
    .doc-check-label {
      display: flex;
      align-items: flex-start;
      gap: 12px;
      padding: 12px 14px;
      border-radius: 14px;
      border: 1px solid var(--borde);
      background-color: var(--crema);
      cursor: pointer;
      user-select: none;
      transition: background-color 0.2s ease, border-color 0.2s ease, box-shadow 0.2s ease;
    }

    .doc-check-label:hover {
      border-color: rgba(230, 126, 34, 0.55);
      background-color: var(--superficie);
    }

    .doc-check-label.is-checked {
      background-color: var(--naranja-suave);
      border-color: var(--naranja);
    }

    .doc-checkbox {
      width: 19px;
      height: 19px;
      margin-top: 2px;
      accent-color: var(--naranja-oscuro);
      cursor: pointer;
      flex-shrink: 0;
    }

    .doc-check-label.is-checked .doc-text {
      color: var(--naranja-oscuro);
      font-weight: 600;
    }

    /* Tarjetas de los 5 servicios disponibles */
    .specialty-card {
      background-color: var(--superficie);
      border: 1px solid var(--borde);
      border-radius: 18px;
      padding: 20px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 16px;
      transition: transform 0.22s ease, border-color 0.22s ease, box-shadow 0.22s ease;
    }

    .specialty-card:hover {
      transform: translateY(-3px);
      border-color: var(--naranja);
      box-shadow: 0 12px 24px rgba(211, 84, 0, 0.1);
    }

    .specialty-code-badge {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-width: 44px;
      height: 34px;
      padding: 0 10px;
      border-radius: 10px;
      background-color: var(--naranja-suave);
      border: 1px solid rgba(230, 126, 34, 0.35);
      color: var(--naranja-oscuro);
      font-size: 0.78rem;
      font-weight: 800;
      letter-spacing: 0.05em;
      flex-shrink: 0;
    }

    .btn-select-service {
      width: 100%;
      padding: 10px 14px;
      border-radius: 11px;
      border: 1px solid var(--naranja);
      background-color: var(--naranja-suave);
      color: var(--naranja-oscuro);
      font-size: 0.86rem;
      font-weight: 700;
      cursor: pointer;
      transition: background-color 0.2s ease, color 0.2s ease, border-color 0.2s ease;
    }

    .btn-select-service:hover {
      background-color: var(--naranja-oscuro);
      border-color: var(--naranja-oscuro);
      color: var(--superficie);
    }

    /* Formulario de pre-registro */
    .form-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(235px, 1fr));
      gap: 16px;
    }

    .form-label {
      display: block;
      font-size: 0.84rem;
      font-weight: 700;
      color: var(--texto-primario);
      margin-bottom: 6px;
    }

    .form-input {
      width: 100%;
      padding: 11px 14px;
      border: 1.5px solid #CBD5E1;
      border-radius: 12px;
      font-size: 0.94rem;
      color: var(--texto-primario);
      background-color: var(--superficie);
      transition: border-color 0.2s ease, box-shadow 0.2s ease;
    }

    .form-input:focus {
      outline: none;
      border-color: var(--naranja);
      box-shadow: 0 0 0 3px rgba(230, 126, 34, 0.18);
    }

    .form-input-error {
      border-color: #DC2626 !important;
      background-color: #FEF2F2 !important;
    }

    .btn-primary-naranja {
      background: linear-gradient(135deg, var(--naranja) 0%, var(--naranja-oscuro) 100%);
      color: var(--superficie);
      font-weight: 700;
      font-size: 0.95rem;
      padding: 12px 20px;
      border-radius: 12px;
      border: none;
      cursor: pointer;
      box-shadow: 0 6px 16px rgba(211, 84, 0, 0.24);
      transition: transform 0.2s ease, box-shadow 0.2s ease, filter 0.2s ease;
    }

    .btn-primary-naranja:hover {
      transform: translateY(-2px);
      box-shadow: 0 10px 20px rgba(211, 84, 0, 0.32);
      filter: brightness(1.03);
    }

    .contact-action-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      padding: 11px 18px;
      border-radius: 12px;
      color: var(--superficie);
      font-size: 0.92rem;
      font-weight: 700;
      text-decoration: none;
      box-shadow: 0 4px 12px rgba(30, 41, 59, 0.1);
      transition: transform 0.2s ease, box-shadow 0.2s ease, filter 0.2s ease;
    }

    .contact-action-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 8px 18px rgba(30, 41, 59, 0.16);
      filter: brightness(1.04);
    }

    /* =========================================================================
       ADAPTACIÓN MÓVIL Y ESTILOS DE IMPRESIÓN
       ========================================================================= */
    @media (max-width: 960px) {
      .portal-sidebar {
        position: relative;
        width: 100%;
        height: auto;
        padding: 18px 16px 20px;
        border-right: none;
        border-bottom: 1px solid rgba(255, 255, 255, 0.22);
      }

      .brand-lockup {
        max-width: 360px;
        margin-left: auto;
        margin-right: auto;
      }

      .portal-main {
        margin-left: 0;
        width: 100%;
        padding: 18px 14px 32px;
      }

      .hero-hospital,
      .section-card {
        padding: 20px 16px;
        border-radius: 18px;
      }
    }

    @media print {
      .portal-sidebar,
      #mobile-nav-wrapper,
      .hero-hospital,
      #documentos,
      #registro,
      #valoracion,
      #servicios,
      #formulario-preregistro-panel,
      #contacto,
      footer,
      .no-print {
        display: none !important;
      }

      .portal-main {
        margin-left: 0 !important;
        width: 100% !important;
        padding: 0 !important;
      }

      #comprobante-formal {
        display: block !important;
        border: 2px solid #D35400 !important;
        box-shadow: none !important;
      }
    }
  </style>
</head>

<body>
  <!-- =======================================================================
       BARRA LATERAL INSTITUCIONAL NARANJA (ESCRITORIO / FLUJO SUPERIOR EN MÓVIL)
       ======================================================================= -->
  <aside class="portal-sidebar" aria-label="Navegación del portal CIU - UNEVE">
    <div class="brand-lockup">
      <!-- 1. Logotipo de Gerontología -->
      <div class="brand-emblem-card">
        <div class="emblem-frame" title="Gerontología · Propter Senectus, invenies sapientia">
          <img
            id="logo-gerontologia-sidebar"
            src="1000313270.png"
            alt="Logotipo de Gerontología UNEVE"
            loading="eager"
            decoding="sync"
          >
        </div>
        <span class="emblem-caption">Gerontología</span>
      </div>

      <!-- 2. Logotipo de UNEVE -->
      <div class="brand-emblem-card">
        <div class="emblem-frame" title="Universidad Estatal del Valle de Ecatepec UNEVE">
          <img
            id="logo-uneve-sidebar"
            src="1000313269.png"
            alt="Logotipo de UNEVE"
            loading="eager"
            decoding="sync"
          >
        </div>
        <span class="emblem-caption">UNEVE</span>
      </div>
    </div>

    <div class="sidebar-title-box">
      <h2>CIU - UNEVE</h2>
      <p>Universidad Estatal del Valle de Ecatepec</p>
    </div>

    <!-- Menú colapsable en dispositivos móviles -->
    <div id="mobile-nav-wrapper" class="lg:hidden mb-3">
      <button
        type="button"
        id="btn-mobile-menu"
        aria-expanded="true"
        aria-controls="sidebar-links"
        onclick="alternarMenuMovil()"
        class="w-full flex items-center justify-between px-4 py-2.5 rounded-xl bg-white/15 hover:bg-white/25 text-white text-sm font-bold border border-white/25 transition cursor-pointer"
      >
        <span>Menú de Secciones</span>
        <span id="mobile-menu-badge" class="text-xs uppercase tracking-wider bg-white/20 px-2.5 py-0.5 rounded-full">
          Ocultar
        </span>
      </button>
    </div>

    <nav id="sidebar-links" aria-label="Secciones de la guía">
      <a href="#inicio" class="sidebar-nav-link active" data-nav="inicio">
        <span>Inicio</span>
        <span class="nav-index-tag">00</span>
      </a>
      <a href="#documentos" class="sidebar-nav-link" data-nav="documentos">
        <span>Paso 1: Documentos</span>
        <span class="nav-index-tag">01</span>
      </a>
      <a href="#registro" class="sidebar-nav-link" data-nav="registro">
        <span>Paso 2: Registro</span>
        <span class="nav-index-tag">02</span>
      </a>
      <a href="#valoracion" class="sidebar-nav-link" data-nav="valoracion">
        <span>Paso 3: Valoración</span>
        <span class="nav-index-tag">03</span>
      </a>
      <a href="#servicios" class="sidebar-nav-link" data-nav="servicios">
        <span>Servicios y Pre-registro</span>
        <span class="nav-index-tag">04</span>
      </a>
      <a href="#contacto" class="sidebar-nav-link" data-nav="contacto">
        <span>Contacto</span>
        <span class="nav-index-tag">05</span>
      </a>
    </nav>

    <div class="mt-6 pt-4 border-t border-white/25 text-xs text-white/95 leading-relaxed">
      <p class="font-bold text-white">Gerontología</p>
      <p class="italic text-amber-100 mt-0.5">“Propter Senectus, invenies sapientia”</p>
    </div>
  </aside>

  <!-- =======================================================================
       CONTENIDO PRINCIPAL DEL PORTAL CLÍNICO-UNIVERSITARIO
       ======================================================================= -->
  <main class="portal-main">
    <!-- Hero Institucional -->
    <section class="hero-hospital" id="inicio">
      <div class="flex flex-col xl:flex-row xl:items-center xl:justify-between gap-6">
        <div class="max-w-3xl">
          <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full text-xs font-bold uppercase tracking-wider bg-white border border-orange-200 text-slate-800 shadow-2xs mb-3">
            <span class="w-2 h-2 rounded-full" style="background-color: var(--naranja-oscuro);"></span>
            <span>Clínica Integral Universitaria UNEVE · CIU - UNEVE</span>
          </div>

          <h1 class="text-2xl sm:text-4xl font-extrabold tracking-tight leading-tight" style="color: var(--texto-primario);">
            Clínica Integral Universitaria UNEVE
          </h1>

          <p class="mt-2 text-base sm:text-xl font-bold" style="color: var(--naranja-oscuro);">
            Guía Digital para Agendar una Cita
          </p>

          <p class="mt-2.5 text-sm sm:text-base text-slate-600 leading-relaxed">
            Portal informativo de atención clínica y formación universitaria. Revisa los requisitos previos, conoce el flujo de admisión y valoración, elige tu área de especialidad y genera tu comprobante de pre-registro.
          </p>

          <!-- Accesos rápidos a Pre-registro y Contacto -->
          <div class="flex flex-wrap items-center gap-3 mt-5">
            <a href="#pre-registro" class="btn-primary-naranja inline-flex items-center gap-2 text-decoration-none">
              <span>Ir a Pre-registro</span>
              <span aria-hidden="true">-&gt;</span>
            </a>

            <a
              href="#contacto"
              class="inline-flex items-center gap-2 px-4 py-3 rounded-xl bg-white hover:bg-orange-50 text-slate-800 border border-slate-300 text-sm font-bold transition"
            >
              <span>Contacto Institucional</span>
            </a>
          </div>
        </div>

        <!-- Identidad visual con ambos logotipos y etiquetas -->
        <div class="grid grid-cols-1 sm:grid-cols-2 xl:grid-cols-1 gap-3 shrink-0 xl:w-80">
          <div class="flex items-center gap-3.5 bg-white p-3.5 rounded-2xl border border-slate-200 shadow-2xs">
            <div class="w-14 h-14 rounded-full bg-white border-2 p-1 flex items-center justify-center shrink-0 overflow-hidden" style="border-color: var(--naranja);">
              <img
                id="logo-gerontologia-hero"
                src="1000313270.png"
                alt="Logotipo de Gerontología"
                class="w-full h-full object-contain rounded-full"
                loading="eager"
                decoding="sync"
              >
            </div>
            <div class="min-w-0">
