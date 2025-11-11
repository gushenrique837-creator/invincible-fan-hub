<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Invincible Fan Hub - Portal ULTIMATE</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700;900&family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    
    <style>
        /* ==================== */
        /* 1. CSS VARIABLES (TEMAS FÃS MULTICOLORIDOS) */
        /* ==================== */
        :root {
            /* Tema Padrão: Invincible (Vermelho/Amarelo/Preto) */
            --primary-color: #e4002b;   /* Vermelho Invincible (Ação) */
            --secondary-color: #ffc400; /* Amarelo Invincible (Alerta/Destaque) */
            --accent-color: #008080;    /* Ciano de Destaque (Tecnologia/GDA) */
            --text-light: #f5f5f5;
            --text-dark: #1a1a1a;
            --background-dark: #0a0a0a;
            --background-medium: #1f1f1f;
            --background-light: #e0e0e0;
            --font-heading: 'Montserrat', sans-serif; 
            --font-body: 'Roboto', sans-serif;
            
            --filter-saturate: 100%;
            --filter-contrast: 100%;
        }
        body.theme-eve { /* Tema 2: Atom Eve */
            --primary-color: #ff69b4; --secondary-color: #4CAF50; --accent-color: #0000ff;
            --text-light: #fff; --background-dark: #101010; --background-medium: #2a2a2a;
        }
        body.theme-gda-blue { /* Tema 3: GDA Tático */
            --primary-color: #0d47a1; --secondary-color: #2196f3; --accent-color: #ffc400;
            --text-light: #e3f2fd; --background-dark: #000d1a; --background-medium: #112233;
        }
        
        /* ==================== */
        /* 2. RESET E GERAIS (MODERNO E "BEM BONITO") */
        /* ==================== */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        html { scroll-behavior: smooth; }
        body {
            font-family: var(--font-body); background-color: var(--background-dark);
            color: var(--text-light); line-height: 1.6; overflow-x: hidden;
            transition: background-color 0.5s, color 0.5s; 
            filter: saturate(var(--filter-saturate)) contrast(var(--filter-contrast));
        }
        h1, h2, h3 { font-family: var(--font-heading); text-transform: uppercase; letter-spacing: 1px; }
        h1 { font-size: clamp(2rem, 5vw, 4.5rem); text-shadow: 2px 2px 4px rgba(0,0,0,0.5); }
        h2 { 
            font-size: clamp(1.5rem, 4vw, 2.5rem); 
            color: var(--primary-color); border-bottom: 3px solid var(--secondary-color);
            padding-bottom: 10px; margin-bottom: 30px; text-shadow: 1px 1px 3px rgba(0,0,0,0.5);
        }
        h3 { font-size: clamp(1.2rem, 3vw, 1.8rem); color: var(--secondary-color); margin-bottom: 15px;}
        .container { width: 90%; max-width: 1400px; margin: 0 auto; padding: 60px 0; }
        
        /* Card/Panel Padrão com Borda Brilhante */
        .ui-panel {
            background-color: var(--background-medium); 
            border: 2px solid var(--background-medium); 
            border-left: 5px solid var(--primary-color); 
            padding: 25px; 
            box-shadow: 0 0 10px rgba(255, 196, 0, 0.2); 
            transition: transform 0.3s, border-color 0.3s, box-shadow 0.3s;
            border-radius: 5px;
        }
        .ui-panel:hover {
            transform: translateY(-5px);
            border-color: var(--secondary-color);
            box-shadow: 0 5px 20px rgba(255, 196, 0, 0.5), 0 0 15px var(--primary-color);
        }
        
        /* Botões */
        .btn-ui { 
            display: inline-block; background-color: var(--primary-color); 
            color: var(--text-light); font-family: var(--font-heading); 
            padding: 12px 25px; border: none; cursor: pointer; 
            text-transform: uppercase; font-weight: 900; 
            border-radius: 3px;
            box-shadow: 0 3px 5px rgba(0, 0, 0, 0.4);
        }
        .btn-ui:hover { 
            background-color: var(--secondary-color); 
            color: var(--text-dark);
            transform: scale(1.05); 
            box-shadow: 0 5px 15px rgba(255, 196, 0, 0.5);
        }

        /* Inputs */
        .ui-input, .ui-select, .ui-textarea { 
            width: 100%; padding: 10px; margin: 8px 0 15px 0; 
            background-color: var(--background-dark); color: var(--text-light);
            border: 2px solid var(--primary-color); border-radius: 3px;
        }
        .ui-input:focus, .ui-select:focus, .ui-textarea:focus { border-color: var(--secondary-color); box-shadow: 0 0 8px var(--secondary-color); }

        /* Grids */
        .grid-2 { display: grid; grid-template-columns: 1fr 2fr; gap: 40px; }
        .grid-3 { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 30px; }
        @media (max-width: 992px) { .grid-2 { grid-template-columns: 1fr; } }


        /* ==================== */
        /* 3. HEADER E LOGO (INTEGRAÇÃO DA IMAGEM) */
        /* ==================== */
        .cta-banner {
            background-color: #3b5998; 
            padding: 15px 0;
            text-align: center;
            font-family: var(--font-heading);
            font-size: 1.2rem;
            text-transform: uppercase;
            letter-spacing: 2px;
            box-shadow: 0 0 15px rgba(59, 89, 152, 0.8);
        }
        .cta-banner a { color: var(--secondary-color); text-decoration: none; font-weight: 900; display: block; transition: color 0.3s, transform 0.3s; }
        .cta-banner a:hover { color: #fff; transform: scale(1.02); text-shadow: 0 0 10px #fff; }

        .logo-container {
            /* Usando a logo PNG */
            display: flex; align-items: center;
        }
        .logo-container img {
            height: 40px; /* Tamanho da logo */
            width: auto;
            margin-right: 10px;
        }
        nav a { color: var(--text-light); margin-left: 15px; text-decoration: none; transition: color 0.3s; }
        nav a:hover { color: var(--primary-color); }


        /* ==================== */
        /* 4. SEÇÕES ESPECÍFICAS */
        /* ==================== */
        
        /* Perfil de Personagem */
        .profile-image img { width: 100%; height: auto; border: 5px solid var(--primary-color); border-radius: 5px; }
        .stats-bar-container { background: var(--background-dark); height: 12px; border-radius: 6px; margin-bottom: 15px;}
        .stats-bar { height: 12px; background-color: var(--secondary-color); border-radius: 6px; transition: width 0.7s ease-out; }
        .profile-grid { display: grid; grid-template-columns: 1fr 2fr; gap: 30px; }
        @media (max-width: 768px) {
            .profile-grid { grid-template-columns: 1fr; }
            .profile-image { text-align: center; }
            .profile-image img { max-width: 80%; }
        }

        /* Galeria */
        .media-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(220px, 1fr)); gap: 20px; }
        .media-item { position: relative; overflow: hidden; border-radius: 5px; cursor: pointer; box-shadow: 0 0 10px rgba(0,0,0,0.5); }
        .media-item img { width: 100%; height: 200px; object-fit: cover; transition: transform 0.3s; }
        .media-item:hover img { transform: scale(1.1); filter: brightness(1.2); }

        /* Calculador de Dano */
        .impact-level-fatal { color: #ff0000; font-weight: bold; font-size: 1.1rem; }

        /* Criador de Herói */
        .hero-display { 
            position: relative; overflow: hidden;
            background-size: cover; background-position: center; 
            min-height: 400px; 
        }
        .hero-display img {
            position: absolute; width: 100%; height: 100%; object-fit: cover;
        }

        /* Quiz */
        .quiz-option {
            background: var(--background-dark); padding: 15px; margin-bottom: 10px;
            border-left: 3px solid var(--accent-color); cursor: pointer;
            transition: background 0.2s;
        }
        .quiz-option:hover { background: #2a2a2a; border-left-color: var(--secondary-color); }
        .quiz-option.selected { 
            background: var(--primary-color); color: var(--text-light); 
            border-left-color: var(--secondary-color); font-weight: bold; 
        }

        /* Votação */
        .vote-bar-container { background: var(--background-dark); height: 20px; border-radius: 3px; margin-bottom: 10px; overflow: hidden; }
        .vote-bar { 
            height: 20px; background-color: var(--primary-color); color: var(--text-light); 
            text-align: right; padding-right: 5px; font-weight: bold; font-size: 0.8rem;
            transition: width 1s ease-out;
            display: flex; align-items: center; justify-content: flex-end;
        }

    </style>
</head>
<body>

    <div id="theme-selector" style="position: fixed; top: 10px; right: 10px; z-index: 2000; background: rgba(0,0,0,0.7); padding: 5px 10px; border-radius: 5px;">
        <label style="color: var(--primary-color); font-weight: bold;">TEMA FÃ:</label>
        <button onclick="setTheme('default')" title="Invincible Clássico" style="width: 25px; height: 25px; border-radius: 50%; border: 2px solid var(--text-light); cursor: pointer; margin-left: 5px; background-color: #e4002b; border-color: #ffc400;"></button>
        <button onclick="setTheme('eve')" title="Atom Eve (Rosa/Verde)" style="width: 25px; height: 25px; border-radius: 50%; border: 2px solid var(--text-light); cursor: pointer; margin-left: 5px; background-color: #ff69b4; border-color: #4CAF50;"></button>
        <button onclick="setTheme('gda-blue')" title="GDA Tático (Azul/Ciano)" style="width: 25px; height: 25px; border-radius: 50%; border: 2px solid var(--text-light); cursor: pointer; margin-left: 5px; background-color: #0d47a1; border-color: #2196f3;"></button>
    </div>
    
    <div id="color-filter-controls" style="position: fixed; top: 70px; right: 10px; z-index: 2000; background: rgba(0,0,0,0.7); padding: 10px; border-radius: 5px;">
        <h3>VISUAL DE FÃ</h3>
        <label>SATURAÇÃO: <span id="saturate-val">100%</span></label>
        <input type="range" id="saturate-slider" min="0" max="200" value="100" oninput="applyFilter()">
        <label>CONTRASTE: <span id="contrast-val">100%</span></label>
        <input type="range" id="contrast-slider" min="50" max="200" value="100" oninput="applyFilter()">
    </div>

    <div class="cta-banner">
        <a href="https://www.primevideo.com/invincible" target="_blank">
            <i class="fas fa-play-circle"></i> ASSISTA INVINCIBLE AGORA NA AMAZON PRIME VIDEO! <i class="fas fa-play-circle"></i>
        </a>
    </div>

    <header style="background-color: var(--background-dark);">
        <div class="container" style="display: flex; justify-content: space-between; align-items: center; padding: 15px 0;">
            <div class="logo-container">
                <img src="image_058223.png" alt="Logo Invencível">
                <span style="font-family: var(--font-heading); font-size: 1.5rem; font-weight: 700; color: var(--text-light);">HUB</span>
            </div>
            <nav>
                <a href="#timeline">LINHA DO TEMPO</a>
                <a href="#quiz">QUIZ</a>
                <a href="#threat-simulator">ALERTA</a>
                <a href="#media-archive">GALERIA</a>
            </nav>
        </div>
    </header>

    <section id="hero" style="height: 70vh; background: linear-gradient(rgba(10,10,10,0.8), rgba(10,10,10,0.8)), url('image_418cbb.jpg') no-repeat center center/cover; border-bottom: 8px solid var(--primary-color);">
        <div class="hero-content" style="text-align: center; color: var(--text-light); padding-top: 15vh;">
            <h1>O SEU PORTAL INTERATIVO INVINCIBLE</h1>
            <p style="font-size: clamp(1rem, 2vw, 1.3rem); margin-top: 10px; text-shadow: 1px 1px 5px var(--primary-color);">Gere teorias, crie heróis e vote no futuro da Terra.</p>
            <a href="#media-archive" class="btn-ui" style="margin-top: 30px;">EXPLORE A GALERIA <i class="fas fa-image"></i></a>
        </div>
    </section>

    <section id="timeline">
        <div class="container">
            <h2 style="text-align: center;"><i class="fas fa-history"></i> LINHA DO TEMPO PRINCIPAL (VISUAL)</h2>
            <div class="timeline-horizontal" id="timeline-horizontal" style="display: flex; overflow-x: scroll; padding: 20px 0; gap: 30px;">
                </div>
            <p style="text-align: center; margin-top: 50px; color: #a0a0a0;">**ROLAR PARA VER MAIS EVENTOS**</p>
        </div>
    </section>
    
    <section id="profile" style="background-color: var(--background-medium);">
        <div class="container">
            <h2 style="text-align: center;"><i class="fas fa-user-circle"></i> PERFIL DETALHADO DE PERSONAGEM</h2>

            <div class="ui-panel">
                <div class="profile-grid">
                    <div class="profile-image">
                        <img id="profile-img" src="image_da1b96.jpg" alt="Allen, o Alien">
                    </div>
                    <div>
                        <h3 id="profile-name">ALLEN, O ALIEN</h3>
                        <p id="profile-bio" style="color: #ccc;">Agente de ligação da Coalizão de Planetas. Conhecido por sua força incrível (e seu senso de humor). Tornou-se um aliado crucial de Mark Grayson e um líder na guerra contra os Viltrumitas.</p>
                        
                        <h4 style="color: var(--accent-color); margin-top: 20px;">ESTATÍSTICAS VITAIS</h4>
                        <label id="label-force">FORÇA (80/100)</label>
                        <div class="stats-bar-container"><div id="stat-force" class="stats-bar" style="width: 80%;"></div></div>
                        <label id="label-speed">VELOCIDADE (70/100)</label>
                        <div class="stats-bar-container"><div id="stat-speed" class="stats-bar" style="width: 70%;"></div></div>
                        <label id="label-loyalty">LEALDADE (100/100)</label>
                        <div class="stats-bar-container"><div id="stat-loyalty" class="stats-bar" style="width: 100%;"></div></div>
                        <button class="btn-ui" style="margin-top: 20px;" onclick="toggleProfile()">ALTERNAR PERFIL <i class="fas fa-exchange-alt"></i></button>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section id="quiz">
        <div class="container">
            <h2 style="text-align: center;">QUIZ: QUE TIPO DE HERÓI INVINCIBLE VOCÊ É?</h2>
            <div class="ui-panel">
                <div id="quiz-container">
                    <h3>1. Qual é a sua reação a uma ameaça global?</h3>
                    <div class="quiz-option" data-question="1" data-value="omni" onclick="selectOption(this)">A. Ataco de frente, priorizando o poder bruto. (Omni-Man)</div>
                    <div class="quiz-option" data-question="1" data-value="robot" onclick="selectOption(this)">B. Foco na estratégia e coordenação de equipe. (Robot)</div>
                    <div class="quiz-option" data-question="1" data-value="mark" onclick="selectOption(this)">C. Tento conversar e encontrar uma solução pacífica primeiro. (Mark)</div>
                    <div class="quiz-option" data-question="1" data-value="eve" onclick="selectOption(this)">D. Uso minha inteligência para alterar o campo de batalha. (Eve)</div>
                    
                    <h3>2. Qual é a sua maior fraqueza?</h3>
                    <div class="quiz-option" data-question="2" data-value="omni" onclick="selectOption(this)">A. Raiva incontrolável.</div>
                    <div class="quiz-option" data-question="2" data-value="robot" onclick="selectOption(this)">B. Dificuldade em lidar com emoções humanas.</div>
                    <div class="quiz-option" data-question="2" data-value="mark" onclick="selectOption(this)">C. Insegurança e dúvida.</div>
                    <div class="quiz-option" data-question="2" data-value="eve" onclick="selectOption(this)">D. Sacrificar-se demais pelos outros.</div>
                </div>
                
                <button class="btn-ui" style="margin-top: 25px;" onclick="calculateQuizResult()">VER RESULTADO <i class="fas fa-user-astronaut"></i></button>

                <div id="quiz-result" class="ui-panel" style="margin-top: 25px; display: none; border-left: 5px solid var(--secondary-color);"></div>
            </div>
        </div>
    </section>
    
    <section id="threat-simulator" style="background-color: var(--background-dark);">
        <div class="container">
            <h2 style="text-align: center;"><i class="fas fa-exclamation-triangle"></i> SIMULADOR DE ALERTA DE AMEAÇA</h2>
            <div class="grid-2">
                <div class="ui-panel">
                    <h3>PARAMETROS DA AMEAÇA</h3>
                    <div class="data-input">
                        <label>CLASSIFICAÇÃO DO VILÃO</label>
                        <select id="threat-type" class="ui-select">
                            <option value="alien">ALIENÍGENA DE FORÇA BRUTA (Viltrumita/Thragg)</option>
                            <option value="magic">MÁGICO/DIMENSIONAL (Monstro Girl)</option>
                            <option value="tech">TECNOLÓGICO/CIBERNÉTICO (Robot/Doc Seismic)</option>
                            <option value="horde">ATAQUE EM MASSA (Sequids/Flaxans)</option>
                        </select>
                    </div>
                    <div class="data-input">
                        <label>FORÇA DE ATAQUE ESTIMADA (1-10)</label>
                        <input type="range" id="threat-force" min="1" max="10" value="5" oninput="document.getElementById('force-val').innerText=this.value">
                        <span id="force-val" style="color: var(--secondary-color); font-weight: bold;">5</span>
                    </div>
                    <button class="btn-ui" style="width: 100%; margin-top: 25px;" onclick="simulateThreat()">GERAR ALERTA <i class="fas fa-bell"></i></button>
                </div>
                <div id="alert-display" class="alert-display ui-panel" style="background-color: var(--background-dark); text-align: center;">
                    <h4>>> SISTEMA PRONTO</h4>
                    <i class="fas fa-shield-alt" style="font-size: 4rem; margin-bottom: 20px; color: var(--accent-color);"></i>
                    <p style="margin-top: 15px;">Aguardando a simulação de ameaça.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="voting" style="background-color: var(--background-medium);">
        <div class="container">
            <h2 style="text-align: center;"><i class="fas fa-poll"></i> VOTAÇÃO COMUNITÁRIA: TEORIAS POLÊMICAS</h2>

            <div class="ui-panel">
                <h3>QUEM É O HERÓI MAIS SUBESTIMADO DA SÉRIE?</h3>
                <div class="vote-question" id="question-1" style="display: flex; flex-direction: column; gap: 10px; margin-bottom: 20px;">
                    <label><input type="radio" name="subestimado" value="rex"> Rex Splode (Gostamos de pensar que sim.)</label>
                    <label><input type="radio" name="subestimado" value="duplikate"> Dupli-Kate (Ela não é tão chata quanto parece.)</label>
                    <label><input type="radio" name="subestimado" value="samson"> Black Samson (Ele tem potencial, se não fosse o traje.)</label>
                    <label><input type="radio" name="subestimado" value="rusman"> Rusman (Quem é esse? Exatamente!)</label>
                </div>
                <button class="btn-ui" onclick="castVote(1)">VOTAR E VER RESULTADOS</button>

                <div id="vote-results-1" class="ui-panel" style="margin-top: 20px; display:none;">
                    </div>
            </div>
        </div>
    </section>

    <section id="media-archive" style="background-color: var(--background-dark);">
        <div class="container">
            <h2 style="text-align: center;">GALERIA DE ARTE DE FÃS & IMAGENS</h2>
            
            <div class="post-form ui-panel" style="border-left: 5px solid var(--accent-color);">
                <h3><i class="fas fa-upload" style="color: var(--accent-color);"></i> POSTE SUA ARTE! (Simulação)</h3>
                <input type="text" id="post-title" class="ui-input" placeholder="Título da Arte">
                <input type="text" id="post-url" class="ui-input" placeholder="URL da Imagem (Ex: image_da2279.jpg)">
                <select id="post-type" class="ui-select">
                    <option value=".jpg">Arte Original</option>
                    <option value=".png">Cosplay / Conceito</option>
                </select>
                <button class="btn-ui" style="margin-top: 15px;" onclick="postArt()">POSTAR NA GALERIA <i class="fas fa-paper-plane"></i></button>
            </div>
            
            <div class="archive-controls" style="margin-top: 30px; display: flex; gap: 15px; ">
                <input type="text" id="archive-search" class="ui-input" placeholder="Buscar por tag (ex: Mark, Nolan)" style="flex: 1; margin: 0;">
                <select id="archive-filter" class="ui-select" style="flex: 1; margin: 0;">
                    <option value="">TODAS AS IMAGENS</option>
                    <option value=".jpg">ARTE / CENA</option>
                    <option value=".png">CONCEITOS</option>
                </select>
                <button class="btn-ui" onclick="filterArchive()">FILTRAR <i class="fas fa-filter"></i></button>
            </div>

            <div class="media-grid" id="media-grid" style="margin-top: 30px;">
                </div>
        </div>
    </section>

    <section id="damage-calc">
        <div class="container">
            <h2 style="text-align: center;">SIMULADOR DE DANO VILTRUMITA (ESTIMATIVA)</h2>
            <div class="grid-2">
                <div class="ui-panel">
                    <h3>PARÂMETROS DE COLISÃO</h3>
                    <div class="data-input">
                        <label>MASSA DO OBJETO (TONELADAS)</label>
                        <input type="number" id="mass" class="ui-input" value="80" min="1" max="1000">
                    </div>
                    <div class="data-input">
                        <label>VELOCIDADE DE IMPACTO (MACH)</label>
                        <input type="number" id="velocity" class="ui-input" value="10" min="1" max="50">
                    </div>
                    <div class="data-input">
                        <label>RESISTÊNCIA DO ALVO (1-10)</label>
                        <input type="range" id="resistance" min="1" max="10" value="5" oninput="document.getElementById('res-val').innerText=this.value">
                        <span id="res-val" style="color: var(--secondary-color); font-weight: bold;">5</span>
                    </div>
                    <button class="btn-ui" style="width: 100%; margin-top: 25px;" onclick="calculateDamage()">CALCULAR IMPACTO <i class="fas fa-meteor"></i></button>
                </div>
                
                <div id="damage-output" class="ui-panel" style="background-color: var(--background-dark);">
                    <h4>>> RESULTADO DA SIMULAÇÃO</h4>
                    <p>Preencha os dados de Massa (80t = Omni-Man) e Velocidade (Mach 10 = Rápido) para simular o nível de destruição.</p>
                </div>
            </div>
        </div>
    </section>

    <section id="creator" style="background-color: var(--background-medium);">
        <div class="container">
            <h2 style="text-align: center;">CRIADOR DE PERSONAGEM FAN-HERO</h2>
            <div class="grid-2">
                <div class="ui-panel">
                    <h3>MODELAGEM DO SEU FAN-HERO</h3>
                    <div class="data-input">
                        <label>NOME DO PROTÓTIPO</label>
                        <input type="text" id="hero-name" class="ui-input" value="Viltrumita de Estimação" oninput="updateHeroDisplay()">
                    </div>
                     <div class="data-input">
                        <label>ARTE DE FUNDO (EXEMPLO)</label>
                        <select id="bg-select" class="ui-select" onchange="updateHeroDisplay()">
                            <option value="image_3f33bf.jpg">Cidade em Pânico</option>
                            <option value="image_3ec320.jpg">Espaço Sideral</option>
                            <option value="image_e580b8.jpg">Confronto Urbano</option>
                        </select>
                    </div>
                     <div class="data-input">
                        <label>POESES DISPONÍVEIS</label>
                        <select id="pose-select" class="ui-select" onchange="updateHeroDisplay()">
                            <option value="image_3e55c1.jpg">Pose de Lançamento</option>
                            <option value="image_3ec6e4.jpg">Pose de Voo</option>
                            <option value="image_3ed244.jpg">Pose de Impacto</option>
                        </select>
                    </div>
                </div>

                <div class="hero-display ui-panel" style="padding: 0; min-height: 400px; border: none; border-bottom: 5px solid var(--accent-color); position: relative;">
                    </div>
            </div>
        </div>
    </section>


    <footer style="background-color: #000; color: #555; padding: 20px 0; text-align: center; border-top: 3px solid var(--primary-color);">
        <div class="container" style="padding: 0;">
            <p>Invincible Fan Hub | Desenvolvido pela comunidade de fãs | NÃO É UM SITE OFICIAL.</p>
        </div>
    </footer>

    <script>
        // Array de arquivos de imagem (Com todos os arquivos listados na conversa)
        let USER_IMAGE_FILES = [
            'image_a8d3da.jpg', 'image_a8ea25.jpg', 'image_b2d74c.png', 'image_b2e2cf.png', 'image_b2e348.png', 
            'image_3e55c1.jpg', 'image_3e56a0.jpg', 'image_3ebb20.jpg', 'image_3ec320.jpg', 'image_3ec662.jpg', 
            'image_3ec6e4.jpg', 'image_3eca81.png', 'image_3ed244.jpg', 'image_3ed566.jpg', 'image_3f33bf.jpg', 
            'image_4014b6.png', 'image_4187e1.png', 'image_418bdd.png', 'image_418cbb.jpg', 'image_419363.jpg', 
            'image_4b7223.png', 'image_4b7624.jpg', 'image_4b7d49.png', 'image_4b8924.png', 'image_4b8f8e.png', 
            'image_4dd606.jpg', 'image_d9c867.png', 'image_da1b96.jpg', 'image_da1f38.png', 'image_da2279.jpg', 
            'image_e580b8.jpg', 'image_e583fe.png', 'image_e58478.png', 'image_e58856.jpg'
        ];

        // ===================================
        // 1. LÓGICA GERAL (TEMAS, FILTROS, LOGO)
        // ===================================
        function setTheme(themeName) {
            document.body.className = '';
            document.body.classList.add(`theme-${themeName}`);
            localStorage.setItem('invincibleTheme', themeName);
        }
        window.applyFilter = function() {
            const saturateSlider = document.getElementById('saturate-slider');
            const contrastSlider = document.getElementById('contrast-slider');
            const root = document.documentElement;
            const saturateVal = `${saturateSlider.value}%`;
            const contrastVal = `${contrastSlider.value}%`;

            root.style.setProperty('--filter-saturate', saturateVal);
            root.style.setProperty('--filter-contrast', contrastVal);
            document.getElementById('saturate-val').innerText = saturateVal;
            document.getElementById('contrast-val').innerText = contrastVal;
        }
        const savedTheme = localStorage.getItem('invincibleTheme') || 'default';
        setTheme(savedTheme);


        // ===================================
        // 2. LÓGICA: PERFIL DE PERSONAGEM
        // ===================================
        const characterProfiles = [
            { name: 'ALLEN, O ALIEN', img: 'image_da1b96.jpg', bio: 'Agente de ligação da Coalizão de Planetas. Conhecido por sua força incrível (e seu senso de humor). Tornou-se um aliado crucial de Mark Grayson e um líder na guerra contra os Viltrumitas.', stats: { force: 80, speed: 70, loyalty: 100 } },
            { name: 'ATOM EVE', img: 'image_3eca81.png', bio: 'Capaz de reestruturar a matéria ao nível atômico. Aliada e namorada de Invincible. Sua moral é seu maior poder, e ela luta para usar seus dons para melhorar o mundo, não apenas lutar.', stats: { force: 40, speed: 60, loyalty: 95 } },
            { name: 'OMNI-MAN (NOLAN)', img: 'image_419363.jpg', bio: 'Viltrumita, pai de Mark. Originalmente enviado para conquistar a Terra, mas desenvolveu sentimentos. Sua força é quase imensurável, e seu retorno promete ser o evento mais destrutivo.', stats: { force: 100, speed: 90, loyalty: 20 } }
        ];
        let currentProfileIndex = 0;

        window.toggleProfile = function() {
            currentProfileIndex = (currentProfileIndex + 1) % characterProfiles.length;
            const profile = characterProfiles[currentProfileIndex];

            // 1. Atualiza Informações
            document.getElementById('profile-name').innerText = profile.name;
            document.getElementById('profile-img').src = profile.img;
            document.getElementById('profile-bio').innerText = profile.bio;
            
            // 2. Atualiza Barras e Labels (CORRIGIDO)
            document.getElementById('stat-force').style.width = `${profile.stats.force}%`;
            document.getElementById('stat-speed').style.width = `${profile.stats.speed}%`;
            document.getElementById('stat-loyalty').style.width = `${profile.stats.loyalty}%`;
            
            document.getElementById('label-force').innerText = `FORÇA (${profile.stats.force}/100)`;
            document.getElementById('label-speed').innerText = `VELOCIDADE (${profile.stats.speed}/100)`;
            document.getElementById('label-loyalty').innerText = `LEALDADE (${profile.stats.loyalty}/100)`;
        }
        toggleProfile(); // Chama na inicialização

        // ===================================
        // 3. LÓGICA: LINHA DO TEMPO
        // ===================================
        const timelineData = [
            { title: 'NOLAN CHEGA', desc: 'Omni-Man inicia a "missão".', icon: 'fa-globe-americas' },
            { title: 'MARK ATIVADO', desc: 'Poderes de Invincible se manifestam.', icon: 'fa-bolt' },
            { title: 'MASSACRE G.G.', desc: 'O assassinato dos Guardiões do Globo.', icon: 'fa-skull-crossbones' },
            { title: 'BONDADE DE MARK', desc: 'Mark poupa Allen em sua primeira luta.', icon: 'fa-hands-helping' },
            { title: 'CONFRONTO PAI/FILHO', desc: 'O grande confronto em Chicago e a traição de Nolan.', icon: 'fa-fist-raised' },
            { title: 'REDENÇÃO DE NOLAN', desc: 'Mark encontra Nolan no espaço e ele mostra remorso.', icon: 'fa-undo' },
            { title: 'GUERRA SE APROXIMA', desc: 'Thragg se revela e a Coalizão se prepara.', icon: 'fa-meteor' },
        ];
        const timelineHorizontal = document.getElementById('timeline-horizontal');

        timelineData.forEach(event => {
            const div = document.createElement('div');
            div.style.minWidth = '250px';
            div.classList.add('timeline-event-h', 'ui-panel');
            div.innerHTML = `
                <i class="fas ${event.icon}" style="color: var(--primary-color); float: right; font-size: 1.5rem;"></i>
                <h4>${event.title}</h4>
                <p style="font-size: 0.9rem; color: #aaa;">${event.desc}</p>
            `;
            timelineHorizontal.appendChild(div);
        });

        // ===================================
        // 4. LÓGICA: QUIZ (FINALIZADO)
        // ===================================
        let quizAnswers = {};
        window.selectOption = function(element) {
            const question = element.getAttribute('data-question');
            const value = element.getAttribute('data-value');
            
            document.querySelectorAll(`.quiz-option[data-question="${question}"]`).forEach(opt => {
                opt.classList.remove('selected');
            });

            element.classList.add('selected');
            quizAnswers[question] = value;
        }

        window.calculateQuizResult = function() {
            if (Object.keys(quizAnswers).length < 2) {
                document.getElementById('quiz-result').style.display = 'block';
                document.getElementById('quiz-result').innerHTML = `<p style="color:var(--secondary-color);">**Por favor, responda todas as perguntas!**</p>`;
                return;
            }

            const results = {};
            for (const key in quizAnswers) {
                const answer = quizAnswers[key];
                results[answer] = (results[answer] || 0) + 1;
            }

            let resultHero = 'Mark Grayson (Invincible)';
            if (results['omni'] >= 1) resultHero = 'Omni-Man (O Destruidor)';
            if (results['robot'] >= 1 && results['omni'] === undefined) resultHero = 'Robot (O Estrategista)';
            if (results['eve'] >= 1 && results['omni'] === undefined) resultHero = 'Atom Eve (A Benfeitora)';

            document.getElementById('quiz-result').style.display = 'block';
            document.getElementById('quiz-result').innerHTML = `
                <h4 style="color:var(--primary-color);">SEU RESULTADO É...</h4>
                <p style="font-size: 1.5rem; font-weight: bold;">VOCÊ É: ${resultHero}!</p>
                <p style="margin-top: 10px; color: #ccc;">(Seu resultado é baseado nas suas tendências de Força Bruta (Omni), Inteligência (Robot/Eve) e Moralidade (Mark)).</p>
            `;
        }
        
        // ===================================
        // 5. LÓGICA: SIMULADOR DE ALERTA (FINALIZADO)
        // ===================================
        window.simulateThreat = function() {
            const type = document.getElementById('threat-type').value;
            const force = parseInt(document.getElementById('threat-force').value);
            const display = document.getElementById('alert-display');
            
            let level = '';
            let action = '';
            let icon = 'fa-shield-alt';
            let color = 'var(--accent-color)';
            
            display.classList.remove('alert-critical'); 

            if (force >= 8) {
                level = 'NÍVEL DE AMEAÇA: CRÍTICO (EXTINÇÃO)';
                action = 'ALERTA MÁXIMO! FUGA PARA O SUL OU CHAMAR ALLEN. NÃO ENVOLVA-SE.';
                icon = 'fa-skull-crossbones';
                color = 'var(--primary-color)';
                display.classList.add('alert-critical');
            } else if (force >= 5) {
                level = 'NÍVEL DE AMEAÇA: ALTO (MOBILIZAÇÃO)';
                action = 'MOBILIZAR GUARDIÕES DO GLOBO. EVACUAÇÃO PARCIAL NECESSÁRIA.';
                icon = 'fa-exclamation-triangle';
                color = 'var(--secondary-color)';
            } else {
                level = 'NÍVEL DE AMEAÇA: MODERADO (CONTIDO)';
                action = 'ENVIO DE HERÓI SOLO (INVINCIBLE OU EVE). DANO ESTRUTURAL MÍNIMO ESPERADO.';
                icon = 'fa-check-circle';
                color = 'var(--accent-color)';
            }
            
            let villain_text = '';
            if (type === 'alien' && force >= 8) villain_text = ' (Thragg?).';
            if (type === 'tech' && force >= 8) villain_text = ' (Tentáculo-Espacial?).';
            
            display.innerHTML = `
                <h4 style="color:${color};">${level}</h4>
                <i class="fas ${icon}" style="color: ${color}; font-size: 4rem; margin-bottom: 20px;"></i>
                <p style="margin-top: 15px;">**TIPO DE AMEAÇA:** ${type.toUpperCase()}${villain_text}</p>
                <p style="font-weight: bold; margin-top: 10px;">**AÇÃO RECOMENDADA:** ${action}</p>
            `;
        }

        // ===================================
        // 6. LÓGICA: VOTAÇÃO COMUNITÁRIA (FINALIZADO)
        // ===================================
        const voteData = {
            1: { rex: 35, duplikate: 20, samson: 40, rusman: 5 }
        };
        let hasVoted = false;

        window.castVote = function(questionId) {
            if (hasVoted) {
                 alert('Você já votou nesta enquete. Por favor, aguarde os próximos tópicos!');
                 return;
            }
            
            const container = document.getElementById(`question-${questionId}`);
            const resultDiv = document.getElementById(`vote-results-${questionId}`);
            const options = container.querySelectorAll(`input[name="subestimado"]`);
            let selectedValue = null;
            let totalVotes = 0;

            options.forEach(option => {
                if (option.checked) {
                    selectedValue = option.value;
                }
            });

            if (!selectedValue) {
                alert('Por favor, selecione uma opção antes de votar.');
                return;
            }

            // Simula o incremento de 1 voto
            voteData[questionId][selectedValue] += 1;
            hasVoted = true; 

            // Recalcula o total de votos
            for (const key in voteData[questionId]) {
                totalVotes += voteData[questionId][key];
            }

            // Gera o HTML dos resultados (Barras de progresso)
            let resultHTML = '<h4 style="color:var(--primary-color);">RESULTADO ATUAL DA VOTAÇÃO:</h4>';
            for (const key in voteData[questionId]) {
                const percentage = ((voteData[questionId][key] / totalVotes) * 100).toFixed(1);
                const labelMap = { rex: 'Rex Splode', duplikate: 'Dupli-Kate', samson: 'Black Samson', rusman: 'Rusman' };
                
                resultHTML += `
                    <p style="margin-top: 15px; font-weight: bold;">${labelMap[key]}</p>
                    <div class="vote-bar-container">
                        <div class="vote-bar" style="width: ${percentage}%;">${percentage}%</div>
                    </div>
                `;
            }

            resultDiv.innerHTML = resultHTML;
            resultDiv.style.display = 'block';
        }

        // ===================================
        // 7. LÓGICA: GALERIA DE ARTE (FINALIZADO)
        // ===================================
        const mediaGrid = document.getElementById('media-grid');
        
        window.postArt = function() {
            const title = document.getElementById('post-title').value.trim();
            const url = document.getElementById('post-url').value.trim();
            const type = document.getElementById('post-type').value;
            if (title === '' || url === '') {
                alert('Por favor, preencha o Título e a URL da Imagem.');
                return;
            }
            // Adiciona a imagem ao início da lista com o tipo de arquivo
            USER_IMAGE_FILES.unshift(url.endsWith(type) ? url : url + type); 
            document.getElementById('post-title').value = '';
            document.getElementById('post-url').value = '';
            filterArchive();
            alert(`Sua arte "${title}" foi postada!`);
        }

        window.filterArchive = () => {
            const search = document.getElementById('archive-search').value.toLowerCase();
            const filter = document.getElementById('archive-filter').value;
            mediaGrid.innerHTML = ''; 
            let foundCount = 0;

            USER_IMAGE_FILES.forEach(fileName => {
                const extension = fileName.substring(fileName.lastIndexOf('.'));
                
                const matchesSearch = fileName.toLowerCase().includes(search) || fileName.toLowerCase().split('.')[0].includes(search);
                const matchesFilter = filter === "" || extension === filter;

                if (matchesSearch && matchesFilter) {
                    foundCount++;
                    const item = document.createElement('div');
                    item.classList.add('media-item');
                    item.innerHTML = `
                        <img src="${fileName}" alt="Arte de Fã">
                        <div style="position: absolute; bottom: 0; background: rgba(0,0,0,0.7); width: 100%; padding: 5px; font-size: 0.8rem; overflow: hidden; white-space: nowrap; text-overflow: ellipsis;">${fileName.split('.')[0].replace(/_/g, ' ')}</div>
                    `;
                    mediaGrid.appendChild(item);
                }
            });

            if (foundCount === 0) {
                 mediaGrid.innerHTML = `<p style="color:var(--primary-color); margin-top: 20px; text-align: center;">NENHUMA IMAGEM ENCONTRADA COM ESTES PARÂMETROS. Tente refinar a busca.</p>`;
            }
        };
        filterArchive(); 


        // ===================================
        // 8. LÓGICA: CALCULADOR DE DANO (FINALIZADO)
        // ===================================
        window.calculateDamage = function() {
            const mass = parseFloat(document.getElementById('mass').value); // Toneladas
            const velocity = parseFloat(document.getElementById('velocity').value); // Mach
            const resistance = parseFloat(document.getElementById('resistance').value); // 1-10
            const output = document.getElementById('damage-output');

            // Constantes
            const C = 343; // Velocidade do Som (m/s)
            const JOULES_PER_MEGATON = 4.184e15; // J/Megaton

            // 1. Cálculo da Energia Cinética (em Joules)
            // Massa precisa ser em kg (mass * 1000)
            // Velocidade precisa ser em m/s (velocity * C)
            const kineticEnergy = 0.5 * (mass * 1000) * Math.pow(velocity * C, 2); 
            
            // 2. Conversão para o equivalente em Megatons (Unidade de Destruição)
            const megatonsEquivalent = kineticEnergy / JOULES_PER_MEGATON;

            // 3. Nível de Destruição (Ajustado pela Resistência do Alvo)
            const effectiveDamage = megatonsEquivalent / (resistance / 10);
            
            let levelText;
            let levelStyle = '';

            if (effectiveDamage >= 5) {
                levelText = 'NÍVEL: EXTINÇÃO! (5 Megatons ou mais)';
                levelStyle = 'impact-level-fatal';
                levelDescription = `Dano de Nível Evento de Extinção. Um impacto desta magnitude (equivalente a uma bomba termonuclear de ${megatonsEquivalent.toFixed(2)} Megatons) é irrecuperável.`;
            } else if (effectiveDamage >= 1) {
                levelText = 'NÍVEL: CRÍTICO (1 - 5 Megatons)';
                levelStyle = 'impact-level-fatal';
                levelDescription = `Destruição Continental/Regional. Exige resposta total da GDA. Cidades principais em risco.`;
            } else if (effectiveDamage >= 0.1) {
                levelText = 'NÍVEL: SEVERO (100 Kilotons - 1 Megaton)';
                levelStyle = '';
                levelDescription = `Destruição Localizada. Capacidade de varrer uma cidade grande.`;
            } else {
                levelText = 'NÍVEL: MODERADO (Abaixo de 100 Kilotons)';
                levelStyle = '';
                levelDescription = `Dano Estrutural, mas não catastrófico. Exige reconstrução pesada.`;
            }
            
            output.innerHTML = `
                <h4 style="color:var(--primary-color);">DANO CALCULADO: ${kineticEnergy.toExponential(2)} Joules</h4>
                <p>Equivalente de Energia: ${megatonsEquivalent.toFixed(3)} Megatons (Nuclear)</p>
                <hr style="border-color: var(--accent-color);">
                <p class="${levelStyle}" style="margin-top: 15px;">${levelText}</p>
                <p style="margin-top: 10px; color: #ccc;">${levelDescription}</p>
                <p style="font-size: 0.8rem; margin-top: 10px;">(Resistência do Alvo ${resistance}/10 aplicada)</p>
            `;
        }

        // ===================================
        // 9. LÓGICA: CRIADOR FAN-HERO (FINALIZADO)
        // ===================================
        window.updateHeroDisplay = function() {
            const name = document.getElementById('hero-name').value || "FAN-HERO PROTÓTIPO";
            const bg = document.getElementById('bg-select').value;
            const pose = document.getElementById('pose-select').value;
            const displayDiv = document.querySelector('.hero-display');

            // Inicializa as camadas se ainda não existirem
            if (displayDiv.innerHTML === '' || !document.getElementById('display-background')) {
                 displayDiv.style.position = 'relative'; 
                 displayDiv.innerHTML = `
                    <img id="display-background" src="${bg}" style="position: absolute; width: 100%; height: 100%; object-fit: cover; z-index: 1;"> 
                    <img id="display-pose" src="${pose}" style="position: absolute; width: 100%; height: 100%; object-fit: contain; z-index: 2; opacity: 0.5;"> <img id="display-suit" src="image_4b7d49.png" style="position: absolute; width: 100%; height: 100%; object-fit: contain; z-index: 3;"> <h4 id="display-name" style="position: absolute; top: 0; width: 100%; text-align: center; background: rgba(228, 0, 43, 0.9); padding: 10px 0; z-index: 4; color: var(--secondary-color); text-shadow: 1px 1px 3px var(--background-dark);">${name}</h4>
                `;
            } else {
                // Apenas atualiza as fontes das imagens e o nome
                document.getElementById('display-name').innerText = name;
                document.getElementById('display-background').src = bg;
                document.getElementById('display-pose').src = pose;
                document.getElementById('display-suit').src = 'image_4b7d49.png'; // Traje fixo de exemplo
            }
        }
        window.updateHeroDisplay(); 
    </script>
</body>
</html>
