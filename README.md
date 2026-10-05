<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Acervo de Projetos Escolares</title>
    
    <!-- Google Fonts & Font Awesome -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* CONFIGURAÇÃO DE TEMAS E VARIÁVEIS GLOBAIS */
        :root {
            --bg-principal: #0d1117;
            --bg-card: #161b22;
            --bg-campo: #21262d;
            --borda-cor: #30363d;
            --texto-forte: #f0f6fc;
            --texto-suave: #8b949e;
            --destaque: #3fb950;
            --destaque-hover: #2ea043;
            --destaque-alpha: rgba(63, 185, 80, 0.15);
            --alerta: #f85149;
            --sombra-padrao: 0 8px 24px rgba(0, 0, 0, 0.3);
            --curva-borda: 12px;
        }

        [data-theme="light"] {
            --bg-principal: #f6f8fa;
            --bg-card: #ffffff;
            --bg-campo: #f3f4f6;
            --borda-cor: #d0d7de;
            --texto-forte: #1f2328;
            --texto-suave: #656d76;
            --destaque: #2da44e;
            --destaque-hover: #1f7f3a;
            --destaque-alpha: rgba(45, 164, 78, 0.12);
            --alerta: #cf222e;
            --sombra-padrao: 0 4px 12px rgba(0, 0, 0, 0.05);
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Inter', sans-serif;
            transition: background-color 0.25s ease, border-color 0.25s ease, color 0.25s ease;
        }

        body {
            background-color: var(--bg-principal);
            color: var(--texto-forte);
            padding: 25px 15px;
            min-height: 100vh;
        }

        .app-container {
            max-width: 1140px;
            margin: 0 auto;
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        /* NAVEGAÇÃO / HEADER */
        .top-bar {
            background-color: var(--bg-card);
            border: 1px solid var(--borda-cor);
            border-radius: var(--curva-borda);
            padding: 18px 24px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: var(--sombra-padrao);
            flex-wrap: wrap;
            gap: 15px;
        }

        .brand h1 {
            font-size: 1.4rem;
            font-weight: 700;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .brand p {
            color: var(--texto-suave);
            font-size: 0.85rem;
            margin-top: 3px;
        }

        .controls-group {
            display: flex;
            align-items: center;
            gap: 8px;
            flex-wrap: wrap;
        }

        /* BOTÕES ESTILIZADOS */
        .btn {
            border: none;
            cursor: pointer;
            font-weight: 600;
            font-size: 0.85rem;
            padding: 9px 14px;
            border-radius: 8px;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-outline {
            background-color: var(--bg-campo);
            border: 1px solid var(--borda-cor);
            color: var(--texto-forte);
        }

        .btn-outline:hover {
            border-color: var(--destaque);
            color: var(--destaque);
        }

        .btn-primary {
            background-color: var(--destaque);
            color: #ffffff;
        }

        .btn-primary:hover {
            background-color: var(--destaque-hover);
        }

        .btn-danger {
            background-color: var(--alerta);
            color: #ffffff;
        }

        .btn-subtle {
            background-color: var(--destaque-alpha);
            color: var(--destaque);
        }

        .btn-subtle-danger {
            background-color: rgba(248, 81, 73, 0.15);
            color: var(--alerta);
        }

        .btn-block {
            width: 100%;
            justify-content: center;
            padding: 12px;
        }

        /* CARDS E PAINÉIS */
        .panel {
            background-color: var(--bg-card);
            border: 1px solid var(--borda-cor);
            border-radius: var(--curva-borda);
            padding: 22px;
            box-shadow: var(--sombra-padrao);
        }

        .panel-title {
            font-size: 1.15rem;
            font-weight: 600;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .admin-alert {
            background-color: var(--destaque-alpha);
            border: 1px solid var(--destaque);
            border-radius: 8px;
            padding: 12px 16px;
            font-size: 0.88rem;
            color: var(--texto-forte);
        }

        /* CAMPOS DE ENTRADA */
        .grid-inputs {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
            gap: 10px;
        }

        .form-stack {
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        input, select, textarea {
            width: 100%;
            background-color: var(--bg-campo);
            border: 1px solid var(--borda-cor);
            color: var(--texto-forte);
            padding: 10px 12px;
            border-radius: 8px;
            font-size: 0.88rem;
            outline: none;
        }

        input:focus, select:focus, textarea:focus {
            border-color: var(--destaque);
        }

        .ai-suggestion {
            font-size: 0.8rem;
            color: var(--destaque);
            font-weight: 500;
        }

        /* GRID DA GALERIA */
        .cards-grid {
            list-style: none;
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(310px, 1fr));
            gap: 18px;
        }

        .card-item {
            background-color: var(--bg-card);
            border: 1px solid var(--borda-cor);
            border-radius: var(--curva-borda);
            padding: 18px;
            display: flex;
            flex-direction: column;
            gap: 12px;
        }

        .card-header {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            gap: 10px;
        }

        .card-title {
            font-size: 1rem;
            font-weight: 700;
        }

        .tag-subject {
            font-size: 0.72rem;
            padding: 3px 8px;
            border-radius: 20px;
            background-color: var(--destaque-alpha);
            color: var(--destaque);
            font-weight: 600;
            white-space: nowrap;
        }

        .card-meta {
            font-size: 0.8rem;
            color: var(--texto-suave);
            display: flex;
            gap: 12px;
        }

        .card-description {
            font-size: 0.85rem;
            color: var(--texto-suave);
            line-height: 1.45;
        }

        /* MÍDIAS */
        .media-container {
            display: flex;
            flex-direction: column;
            gap: 8px;
            margin-top: 4px;
        }

        .img-wrapper {
            width: 100%;
            height: 170px;
            border-radius: 8px;
            overflow: hidden;
            border: 1px solid var(--borda-cor);
            position: relative;
            cursor: pointer;
            background-color: #000;
        }

        .img-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .img-wrapper:hover::after {
            content: "Expandir Visualização";
            position: absolute;
            inset: 0;
            background: rgba(0, 0, 0, 0.6);
            color: #fff;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 0.8rem;
            font-weight: 600;
        }

        .video-btn {
            border-radius: 8px;
            background-color: rgba(248, 81, 73, 0.12);
            padding: 10px;
            text-align: center;
            border: 1px solid rgba(248, 81, 73, 0.25);
            cursor: pointer;
            color: var(--alerta);
            font-weight: 600;
            font-size: 0.82rem;
        }

        .video-btn:hover {
            background-color: rgba(248, 81, 73, 0.22);
        }

        .pdf-viewer {
            border-radius: 8px;
            border: 1px solid var(--borda-cor);
            overflow: hidden;
            height: 190px;
            background: var(--bg-campo);
        }

        .pdf-viewer iframe {
            width: 100%;
            height: 100%;
            border: none;
        }

        /* ANOTAÇÕES & FOOTER DO CARD */
        .notes-area {
            display: none;
            padding: 8px;
            background-color: var(--bg-campo);
            border: 1px dashed var(--borda-cor);
            border-radius: 8px;
        }

        .notes-area textarea {
            background: transparent;
            border: none;
            min-height: 45px;
            resize: vertical;
        }

        .card-actions {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding-top: 10px;
            border-top: 1px solid var(--borda-cor);
            margin-top: auto;
        }

        .no-data {
            grid-column: 1 / -1;
            text-align: center;
            color: var(--texto-suave);
            padding: 35px;
            border: 2px dashed var(--borda-cor);
            border-radius: var(--curva-borda);
        }

        /* MODAL */
        .lightbox {
            display: none;
            position: fixed;
            inset: 0;
            z-index: 1000;
            background-color: rgba(0, 0, 0, 0.88);
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .lightbox img {
            max-width: 92vw;
            max-height: 88vh;
            border-radius: 6px;
            object-fit: contain;
        }

        .lightbox-close {
            position: absolute;
            top: 20px;
            right: 25px;
            color: #ffffff;
            font-size: 1.8rem;
            cursor: pointer;
        }

        .hidden { display: none !important; }
    </style>
</head>
<body>

    <div class="app-container">
        <!-- HEADER -->
        <header class="top-bar">
            <div class="brand">
                <h1><i class="fa-solid fa-box-archive"></i> Repositório de Atividades</h1>
                <p>Plataforma de consulta e registro de trabalhos escolares</p>
            </div>
            <div class="controls-group">
                <button class="btn btn-outline" id="btn-export-json"><i class="fa-solid fa-file-export"></i> Baixar JSON</button>
                <button class="btn btn-outline admin-element hidden" id="btn-import-trigger"><i class="fa-solid fa-file-import"></i> Carregar</button>
                <input type="file" id="file-uploader" class="hidden" accept=".json">
                
                <button class="btn btn-outline" id="btn-theme-switcher">
                    <i class="fa-solid fa-moon"></i> <span id="lbl-theme">Escuro</span>
                </button>
                
                <button class="btn btn-primary" id="btn-admin-access">
                    <i class="fa-solid fa-key"></i> <span id="lbl-admin">Acesso Restrito</span>
                </button>
            </div>
        </header>

        <!-- BANNER ADM -->
        <div id="admin-notice-bar" class="admin-alert hidden">
            <i class="fa-solid fa-user-shield"></i> <strong>Sessão Administrativa Ativa:</strong> Acesso liberado para cadastro e alteração de conteúdo.
        </div>

        <!-- FORMULÁRIO DE INSERÇÃO -->
        <section class="panel admin-element hidden">
            <h2 class="panel-title"><i class="fa-solid fa-cloud-arrow-up"></i> Registrar Novo Trabalho</h2>
            <form id="project-form" class="form-stack">
                <div class="grid-inputs">
                    <input type="text" id="field-title" placeholder="Nome do Trabalho *" required>
                    <input type="text" id="field-subject" list="dl-subjects" placeholder="Disciplina *" required>
                    <input type="text" id="field-teacher" list="dl-teachers" placeholder="Docente *" required>
                    <input type="date" id="field-date" required>
                </div>

                <datalist id="dl-subjects"></datalist>
                <datalist id="dl-teachers"></datalist>

                <div id="smart-tag-info" class="ai-suggestion hidden">
                    <i class="fa-solid fa-sparkles"></i> <span id="smart-tag-text"></span>
                </div>
                
                <textarea id="field-desc" placeholder="Resumo detalhado sobre a atividade..." rows="3" required></textarea>

                <div class="grid-inputs">
                    <input type="url" id="field-img-link" placeholder="URL da Imagem (Drive/Link Direto)">
                    <input type="url" id="field-video-link" placeholder="Link do Vídeo (YouTube/Vimeo)">
                    <input type="url" id="field-pdf-link" placeholder="Link do Arquivo PDF">
                </div>

                <button type="submit" class="btn btn-primary btn-block">
                    <i class="fa-solid fa-plus"></i> Salvar e Publicar
                </button>
            </form>
        </section>

        <!-- PAINEL DE FILTROS -->
        <div class="panel">
            <h3 class="panel-title"><i class="fa-solid fa-sliders"></i> Buscar e Filtrar</h3>
            <div class="grid-inputs">
                <input type="text" id="search-query" placeholder="Buscar palavra-chave...">
                <input type="date" id="filter-by-date">
                <select id="filter-by-subject"><option value="">Todas as Disciplinas</option></select>
                <select id="filter-by-teacher"><option value="">Todos os Docentes</option></select>
            </div>
        </div>

        <!-- LISTA PRINCIPAL -->
        <section class="panel">
            <h2 class="panel-title"><i class="fa-solid fa-layer-group"></i> Projetos Armazenados</h2>
            <ul id="gallery-list" class="cards-grid"></ul>
        </section>
    </div>

    <!-- MODAL DE VISUALIZAÇÃO DA IMAGEM -->
    <div id="lightbox-modal" class="lightbox">
        <span class="lightbox-close" id="lightbox-dismiss">&times;</span>
        <img id="lightbox-image" src="" alt="Ampliação">
    </div>

    <script>
        (function() {
            // Mapeamento sintático para autoclassificação
            const KEYWORD_MAP = [
                { keywords: ['python', 'c++', 'codigo', 'algoritmo', 'site', 'html'], subject: 'Programação' },
                { keywords: ['robo', 'robotica', 'arduino', 'sensor'], subject: 'Robótica' },
                { keywords: ['matematica', 'calculo', 'equaçao'], subject: 'Matemática' },
                { keywords: ['redaçao', 'texto', 'portugues'], subject: 'Português' },
                { keywords: ['fisica', 'movimento', 'força'], subject: 'Física' }
            ];

            // Estado global do app
            const AppState = {
                data: JSON.parse(localStorage.getItem('academic_repo_db')) || [],
                isAdmin: false
            };

            // Elementos DOM frequentemente usados
            const DOM = {
                themeBtn: document.getElementById('btn-theme-switcher'),
                themeLbl: document.getElementById('lbl-theme'),
                adminBtn: document.getElementById('btn-admin-access'),
                adminLbl: document.getElementById('lbl-admin'),
                adminBanner: document.getElementById('admin-notice-bar'),
                adminEls: document.querySelectorAll('.admin-element'),
                form: document.getElementById('project-form'),
                titleInput: document.getElementById('field-title'),
                subjectInput: document.getElementById('field-subject'),
                aiTagBox: document.getElementById('smart-tag-info'),
                aiTagTxt: document.getElementById('smart-tag-text'),
                gallery: document.getElementById('gallery-list'),
                searchTxt: document.getElementById('search-query'),
                filterDate: document.getElementById('filter-by-date'),
                filterSubject: document.getElementById('filter-by-subject'),
                filterTeacher: document.getElementById('filter-by-teacher'),
                btnExport: document.getElementById('btn-export-json'),
                btnImportTrigger: document.getElementById('btn-import-trigger'),
                fileUploader: document.getElementById('file-uploader'),
                modal: document.getElementById('lightbox-modal'),
                modalImg: document.getElementById('lightbox-image'),
                modalClose: document.getElementById('lightbox-dismiss')
            };

            // INICIALIZAÇÃO E EVENTOS
            function initApp() {
                applyTheme(localStorage.getItem('academic_repo_theme') || 'dark');
                bindEvents();
                refreshFiltersUI();
                renderCards();
            }

            function bindEvents() {
                DOM.themeBtn.addEventListener('click', toggleThemeMode);
                DOM.adminBtn.addEventListener('click', toggleAdminAuth);
                DOM.titleInput.addEventListener('input', handleAutoCategory);
                DOM.form.addEventListener('submit', handleNewSubmission);
                
                DOM.searchTxt.addEventListener('input', renderCards);
                DOM.filterDate.addEventListener('change', renderCards);
                DOM.filterSubject.addEventListener('change', renderCards);
                DOM.filterTeacher.addEventListener('change', renderCards);

                DOM.btnExport.addEventListener('click', exportDataset);
                DOM.btnImportTrigger.addEventListener('click', () => DOM.fileUploader.click());
                DOM.fileUploader.addEventListener('change', importDataset);

                DOM.modalClose.addEventListener('click', closeModal);
                DOM.modal.addEventListener('click', (e) => {
                    if(e.target === DOM.modal) closeModal();
                });
            }

            // GESTÃO DE TEMAS
            function applyTheme(mode) {
                if (mode === 'light') {
                    document.documentElement.setAttribute('data-theme', 'light');
                    DOM.themeBtn.innerHTML = '<i class="fa-solid fa-sun"></i>';
                    DOM.themeLbl.textContent = 'Claro';
                } else {
                    document.documentElement.removeAttribute('data-theme');
                    DOM.themeBtn.innerHTML = '<i class="fa-solid fa-moon"></i>';
                    DOM.themeLbl.textContent = 'Escuro';
                }
                localStorage.setItem('academic_repo_theme', mode);
            }

            function toggleThemeMode() {
                const isLight = localStorage.getItem('academic_repo_theme') === 'light';
                applyTheme(isLight ? 'dark' : 'light');
            }

            // MODO ADMINISTRATIVO
            function toggleAdminAuth() {
                if (!AppState.isAdmin) {
                    const pwd = prompt("Código de Acesso do Administrador:");
                    if (pwd === "admin123") {
                        AppState.isAdmin = true;
                    } else if (pwd !== null) {
                        alert("Código incorreto!");
                    }
                } else {
                    AppState.isAdmin = false;
                }
                syncAdminState();
            }

            function syncAdminState() {
                if (AppState.isAdmin) {
                    DOM.adminBtn.classList.remove('btn-primary');
                    DOM.adminBtn.classList.add('btn-danger');
                    DOM.adminLbl.textContent = 'Encerrar ADM';
                    DOM.adminBtn.querySelector('i').className = 'fa-solid fa-lock-open';
                    DOM.adminBanner.classList.remove('hidden');
                    DOM.adminEls.forEach(el => el.classList.remove('hidden'));
                } else {
                    DOM.adminBtn.classList.remove('btn-danger');
                    DOM.adminBtn.classList.add('btn-primary');
                    DOM.adminLbl.textContent = 'Acesso Restrito';
                    DOM.adminBtn.querySelector('i').className = 'fa-solid fa-key';
                    DOM.adminBanner.classList.add('hidden');
                    DOM.adminEls.forEach(el => el.classList.add('hidden'));
                }
                renderCards();
            }

            // PARSER DE URLS PARA IMAGENS
            function sanitizeMediaUrl(rawUrl) {
                if (!rawUrl) return '';
                if (rawUrl.includes('drive.google.com') && rawUrl.includes('/file/d/')) {
                    const driveId = rawUrl.split('/file/d/')[1].split('/')[0].split('?')[0];
                    return `https://lh3.googleusercontent.com/d/${driveId}`;
                }
                if (rawUrl.includes('dropbox.com')) {
                    return rawUrl.replace('www.dropbox.com', 'dl.dropboxusercontent.com').replace('?dl=0', '');
                }
                return rawUrl;
            }

            // AUTO-SUGESTÃO POR IA
            function handleAutoCategory(e) {
                const text = e.target.value.toLowerCase();
                const found = KEYWORD_MAP.find(entry => entry.keywords.some(k => text.includes(k)));
                
                if (found && !DOM.subjectInput.value) {
                    DOM.subjectInput.value = found.subject;
                    DOM.aiTagTxt.textContent = `Sugestão automática: ${found.subject}`;
                    DOM.aiTagBox.classList.remove('hidden');
                } else if (!found) {
                    DOM.aiTagBox.classList.add('hidden');
                }
            }

            // PERSISTÊNCIA
            function saveData() {
                localStorage.setItem('academic_repo_db', JSON.stringify(AppState.data));
                refreshFiltersUI();
            }

            function refreshFiltersUI() {
                const listMat = document.getElementById('dl-subjects');
                const listProf = document.getElementById('dl-teachers');

                const subjects = [...new Set(AppState.data.map(i => i.materia))].filter(Boolean);
                const teachers = [...new Set(AppState.data.map(i => i.professor))].filter(Boolean);

                DOM.filterSubject.innerHTML = '<option value="">Todas as Disciplinas</option>' + 
                    subjects.map(s => `<option value="${s}">${s}</option>`).join('');
                
                DOM.filterTeacher.innerHTML = '<option value="">Todos os Docentes</option>' + 
                    teachers.map(t => `<option value="${t}">${t}</option>`).join('');

                listMat.innerHTML = subjects.map(s => `<option value="${s}">`).join('');
                listProf.innerHTML = teachers.map(t => `<option value="${t}">`).join('');
            }

            // CADASTRO DE ITEM
            function handleNewSubmission(e) {
                e.preventDefault();
                if (!AppState.isAdmin) return;

                const newItem = {
                    id: Date.now(),
                    titulo: document.getElementById('field-title').value,
                    materia: document.getElementById('field-subject').value,
                    professor: document.getElementById('field-teacher').value,
                    data: document.getElementById('field-date').value,
                    descricao: document.getElementById('field-desc').value,
                    imagem: document.getElementById('field-img-link').value,
                    video: document.getElementById('field-video-link').value,
                    pdf: document.getElementById('field-pdf-link').value,
                    notas: ''
                };

                AppState.data.push(newItem);
                saveData();
                renderCards();
                DOM.form.reset();
                DOM.aiTagBox.classList.add('hidden');
            }

            // RENDERIZAÇÃO DA LISTA
            function renderCards() {
                const q = DOM.searchTxt.value.toLowerCase();
                const d = DOM.filterDate.value;
                const s = DOM.filterSubject.value;
                const t = DOM.filterTeacher.value;

                const filtered = AppState.data.filter(item => {
                    const matchText = item.titulo.toLowerCase().includes(q) || item.descricao.toLowerCase().includes(q);
                    const matchDate = !d || item.data === d;
                    const matchSubject = !s || item.materia === s;
                    const matchTeacher = !t || item.professor === t;
                    return matchText && matchDate && matchSubject && matchTeacher;
                });

                if (filtered.length === 0) {
                    DOM.gallery.innerHTML = `
                        <div class="no-data">
                            <i class="fa-regular fa-folder-open fa-2x"></i>
                            <p style="margin-top: 10px;">Nenhum registro encontrado no sistema.</p>
                        </div>`;
                    return;
                }

                DOM.gallery.innerHTML = filtered.map(item => {
                    const processedImg = sanitizeMediaUrl(item.imagem);
                    const rawDate = item.data ? item.data.split('-') : [];
                    const formattedDate = rawDate.length === 3 ? `${rawDate[2]}/${rawDate[1]}/${rawDate[0]}` : 'Sem data';

                    return `
                    <li class="card-item">
                        <div class="card-header">
                            <span class="card-title">${item.titulo}</span>
                            <span class="tag-subject">${item.materia}</span>
                        </div>
                        
                        <div class="card-meta">
                            <span><i class="fa-solid fa-user-graduate"></i> ${item.professor}</span>
                            <span><i class="fa-solid fa-clock"></i> ${formattedDate}</span>
                        </div>

                        <p class="card-description">${item.descricao}</p>

                        <div class="media-container">
                            ${processedImg ? `
                                <div class="img-wrapper" onclick="window.viewImage('${processedImg}')">
                                    <img src="${processedImg}" alt="Foto da atividade" onerror="this.parentElement.style.display='none'">
                                </div>
                            ` : ''}

                            ${item.video ? `
                                <div class="video-btn" onclick="window.open('${item.video}', '_blank')">
                                    <i class="fa-brands fa-youtube"></i> Assistir Vídeo do Projeto
                                </div>
                            ` : ''}

                            ${item.pdf ? `
                                <div class="pdf-viewer">
                                    <iframe src="${item.pdf}"></iframe>
                                </div>
                            ` : ''}
                        </div>

                        <div class="notes-area" id="notes-box-${item.id}">
                            <textarea ${!AppState.isAdmin ? 'disabled' : ''} 
                                      onblur="window.updateNotes(${item.id}, this.value)" 
                                      placeholder="Anotações internas...">${item.notas || ''}</textarea>
                        </div>

                        <div class="card-actions">
                            <button class="btn btn-subtle" onclick="window.toggleNotesVisibility(${item.id})">
                                <i class="fa-regular fa-note-sticky"></i> Anotações
                            </button>
                            ${AppState.isAdmin ? `
                                <button class="btn btn-subtle-danger" onclick="window.removeProject(${item.id})">
                                    <i class="fa-regular fa-trash-can"></i> Remover
                                </button>
                            ` : ''}
                        </div>
                    </li>`;
                }).join('');
            }

            // FUNÇÕES DE AÇÃO ANEXADAS AO ESCOPO GLOBAL (Para uso Inline nos Eventos HTML)
            window.removeProject = function(id) {
                if (!AppState.isAdmin) return;
                if (confirm("Confirmar exclusão deste registro?")) {
                    AppState.data = AppState.data.filter(item => item.id !== id);
                    saveData();
                    renderCards();
                }
            };

            window.toggleNotesVisibility = function(id) {
                const box = document.getElementById(`notes-box-${id}`);
                box.style.display = (box.style.display === 'block') ? 'none' : 'block';
            };

            window.updateNotes = function(id, text) {
                if (!AppState.isAdmin) return;
                const target = AppState.data.find(item => item.id === id);
                if (target) {
                    target.notas = text;
                    saveData();
                }
            };

            window.viewImage = function(url) {
                DOM.modalImg.src = url;
                DOM.modal.style.display = 'flex';
            };

            function closeModal() {
                DOM.modal.style.display = 'none';
            }

            // BACKUP DE DADOS
            function exportDataset() {
                if (AppState.data.length === 0) {
                    alert("A base de dados está vazia.");
                    return;
                }
                const blob = new Blob([JSON.stringify(AppState.data, null, 2)], { type: "application/json" });
                const url = URL.createObjectURL(blob);
                const a = document.createElement('a');
                a.href = url;
                a.download = `projetos_backup_${new Date().toISOString().split('T')[0]}.json`;
                a.click();
                URL.revokeObjectURL(url);
            }

            function importDataset(e) {
                const file = e.target.files[0];
                if (!file) return;
                const reader = new FileReader();
                reader.onload = (evt) => {
                    try {
                        AppState.data = JSON.parse(evt.target.result);
                        saveData();
                        renderCards();
                        alert('Base importada com sucesso!');
                    } catch (err) {
                        alert('Falha na leitura do arquivo JSON.');
                    }
                };
                reader.readAsText(file);
            }

            // Inicializar aplicação
            initApp();
        })();
    </script>
</body>
</html>
