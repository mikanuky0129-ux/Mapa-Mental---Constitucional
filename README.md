<html><head><style>
  @import url('https://fonts.googleapis.com/css2?family=Nunito:wght@400;600;700;800;900&family=Fira+Code:wght@400;500&display=swap');

  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: 'Nunito', sans-serif; background: var(--color-background-tertiary); }

  .mm-root { padding: 16px; max-width: 1100px; margin: 0 auto; }

  .mm-title {
    text-align: center;
    font-size: 22px;
    font-weight: 900;
    color: var(--color-text-primary);
    letter-spacing: -0.5px;
    margin-bottom: 6px;
  }
  .mm-subtitle {
    text-align: center;
    font-size: 13px;
    color: var(--color-text-secondary);
    margin-bottom: 18px;
  }

  .tabs {
    display: flex;
    flex-wrap: wrap;
    gap: 6px;
    margin-bottom: 18px;
    justify-content: center;
  }
  .tab {
    padding: 6px 14px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 700;
    cursor: pointer;
    border: 2px solid transparent;
    transition: all 0.2s;
    user-select: none;
  }
  .tab:hover { transform: translateY(-1px); }
  .tab.active { color: #fff !important; }

  .panel { display: none; }
  .panel.active { display: block; }

  /* CARD SYSTEM */
  .card {
    background: var(--color-background-primary);
    border: 0.5px solid var(--color-border-tertiary);
    border-radius: 14px;
    padding: 14px 16px;
    margin-bottom: 12px;
    position: relative;
    overflow: hidden;
  }
  .card::before {
    content: '';
    position: absolute;
    left: 0; top: 0; bottom: 0;
    width: 4px;
    border-radius: 4px 0 0 4px;
  }
  .card-title {
    font-size: 14px;
    font-weight: 800;
    margin-bottom: 8px;
    display: flex;
    align-items: center;
    gap: 7px;
  }
  .card-icon {
    width: 22px; height: 22px;
    border-radius: 6px;
    display: flex; align-items: center; justify-content: center;
    font-size: 12px;
    flex-shrink: 0;
  }

  /* GRID */
  .grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; }
  .grid-3 { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 12px; }
  @media (max-width: 700px) {
    .grid-2, .grid-3 { grid-template-columns: 1fr; }
  }

  /* TAGS */
  .tag {
    display: inline-block;
    padding: 2px 8px;
    border-radius: 10px;
    font-size: 11px;
    font-weight: 700;
    margin: 2px 2px 2px 0;
  }

  /* TIMELINE */
  .timeline { position: relative; padding-left: 22px; }
  .timeline::before {
    content: '';
    position: absolute;
    left: 8px; top: 6px; bottom: 6px;
    width: 2px;
    background: var(--color-border-secondary);
    border-radius: 2px;
  }
  .titem {
    position: relative;
    margin-bottom: 10px;
    font-size: 13px;
  }
  .titem::before {
    content: '';
    position: absolute;
    left: -18px;
    top: 5px;
    width: 10px; height: 10px;
    border-radius: 50%;
    border: 2px solid var(--color-background-primary);
  }
  .titem-year {
    font-size: 11px;
    font-weight: 800;
    margin-bottom: 1px;
  }
  .titem-text { color: var(--color-text-secondary); font-size: 12px; line-height: 1.5; }

  /* COMPARE TABLE */
  .ctable { width: 100%; border-collapse: collapse; font-size: 12px; }
  .ctable th {
    padding: 6px 10px;
    font-weight: 800;
    font-size: 11px;
    text-align: left;
    border-bottom: 1.5px solid var(--color-border-secondary);
  }
  .ctable td {
    padding: 6px 10px;
    border-bottom: 0.5px solid var(--color-border-tertiary);
    vertical-align: top;
    line-height: 1.5;
  }
  .ctable tr:last-child td { border-bottom: none; }

  /* HIGHLIGHT BOX */
  .hbox {
    border-radius: 10px;
    padding: 10px 13px;
    margin: 8px 0;
    font-size: 12px;
    line-height: 1.6;
    border-left: 3px solid;
  }
  .hbox strong { font-weight: 800; display: block; margin-bottom: 2px; font-size: 12px; }

  /* FLOW STEPS */
  .steps { display: flex; flex-direction: column; gap: 6px; }
  .step {
    display: flex;
    align-items: flex-start;
    gap: 8px;
    font-size: 12px;
    line-height: 1.5;
  }
  .step-num {
    min-width: 22px; height: 22px;
    border-radius: 50%;
    display: flex; align-items: center; justify-content: center;
    font-size: 11px;
    font-weight: 800;
    flex-shrink: 0;
    margin-top: 1px;
  }

  /* BADGE */
  .badge {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    padding: 3px 9px;
    border-radius: 20px;
    font-size: 11px;
    font-weight: 700;
    margin: 3px 3px 3px 0;
  }

  /* PETREA */
  .petrea-box {
    border-radius: 10px;
    padding: 10px 13px;
    display: flex;
    align-items: center;
    gap: 10px;
    margin: 5px 0;
    font-size: 12px;
    font-weight: 700;
  }
  .petrea-icon { font-size: 16px; }

  /* PILLAR */
  .pillar {
    border-radius: 10px;
    padding: 10px;
    text-align: center;
    font-size: 11px;
    font-weight: 700;
    line-height: 1.4;
  }
  .pillar-icon { font-size: 18px; margin-bottom: 4px; }
  .pillar-main { font-size: 12px; font-weight: 800; }

  /* QUOTE */
  .quote {
    border-radius: 10px;
    padding: 10px 14px;
    font-size: 12px;
    font-style: italic;
    line-height: 1.6;
    border-left: 3px solid;
    margin: 6px 0;
  }
  .quote-author { font-style: normal; font-weight: 800; font-size: 11px; margin-top: 4px; display: block; }

  /* POSTIT */
  .postit {
    border-radius: 4px 4px 4px 12px;
    padding: 10px 12px;
    font-size: 12px;
    line-height: 1.5;
    transform: rotate(-0.5deg);
    box-shadow: 2px 2px 0 rgba(0,0,0,0.08);
    margin: 6px 0;
  }
  .postit strong { font-weight: 800; font-size: 12px; display: block; margin-bottom: 3px; }

  /* SEARCH */
  .search-wrap { position: relative; margin-bottom: 14px; }
  .search-input {
    width: 100%;
    padding: 8px 36px 8px 12px;
    border-radius: 20px;
    border: 1px solid var(--color-border-secondary);
    background: var(--color-background-primary);
    font-size: 13px;
    color: var(--color-text-primary);
    font-family: 'Nunito', sans-serif;
  }
  .search-input:focus { outline: none; border-color: #7C5CBF; }
  .search-icon { position: absolute; right: 12px; top: 50%; transform: translateY(-50%); color: var(--color-text-tertiary); font-size: 14px; }

  /* COLORS */
  /* Purple */
  .c1-bg { background: #EDE9FC; } .c1-text { color: #5B2BAF; } .c1-brd { border-color: #7C5CBF; } .c1-lft::before { background: #7C5CBF; }
  /* Blue */
  .c2-bg { background: #E7F0FD; } .c2-text { color: #1A4E99; } .c2-brd { border-color: #3B7FDD; } .c2-lft::before { background: #3B7FDD; }
  /* Teal */
  .c3-bg { background: #E0F5EE; } .c3-text { color: #0A6047; } .c3-brd { border-color: #0F9E72; } .c3-lft::before { background: #0F9E72; }
  /* Amber */
  .c4-bg { background: #FEF4E0; } .c4-text { color: #7A4F0A; } .c4-brd { border-color: #C98010; } .c4-lft::before { background: #C98010; }
  /* Coral */
  .c5-bg { background: #FDEBE6; } .c5-text { color: #8C2E12; } .c5-brd { border-color: #D5541C; } .c5-lft::before { background: #D5541C; }
  /* Pink */
  .c6-bg { background: #FCEAF2; } .c6-text { color: #7D1A43; } .c6-brd { border-color: #C93B6B; } .c6-lft::before { background: #C93B6B; }
  /* Green */
  .c7-bg { background: #EBF5DF; } .c7-text { color: #2C5A0E; } .c7-brd { border-color: #5AA015; } .c7-lft::before { background: #5AA015; }
  /* Red */
  .c8-bg { background: #FEECEC; } .c8-text { color: #7A1212; } .c8-brd { border-color: #D84343; } .c8-lft::before { background: #D84343; }
  /* Gray */
  .c9-bg { background: var(--color-background-secondary); } .c9-text { color: var(--color-text-primary); } .c9-brd { border-color: var(--color-border-secondary); } .c9-lft::before { background: var(--color-border-primary); }

  @media (prefers-color-scheme: dark) {
    .c1-bg { background: #2A1F4A; } .c1-text { color: #C4A8F5; } .c1-brd { border-color: #9A7ADE; }
    .c2-bg { background: #192A48; } .c2-text { color: #90B8F0; } .c2-brd { border-color: #5B95E0; }
    .c3-bg { background: #0E3328; } .c3-text { color: #70D4AC; } .c3-brd { border-color: #1DA87A; }
    .c4-bg { background: #3A2906; } .c4-text { color: #F5C36A; } .c4-brd { border-color: #D99020; }
    .c5-bg { background: #3B180A; } .c5-text { color: #F5A07A; } .c5-brd { border-color: #E06A3A; }
    .c6-bg { background: #3B0E22; } .c6-text { color: #F0A0C0; } .c6-brd { border-color: #D55A8A; }
    .c7-bg { background: #1A3206; } .c7-text { color: #A0D865; } .c7-brd { border-color: #70B820; }
    .c8-bg { background: #3B0808; } .c8-text { color: #F5A0A0; } .c8-brd { border-color: #E06060; }
  }
  .tab-1 { background: #EDE9FC; color: #5B2BAF; border-color: #9A7ADE; }
  .tab-1.active { background: #7C5CBF; border-color: #7C5CBF; }
  .tab-2 { background: #E7F0FD; color: #1A4E99; border-color: #5B95E0; }
  .tab-2.active { background: #3B7FDD; border-color: #3B7FDD; }
  .tab-3 { background: #E0F5EE; color: #0A6047; border-color: #1DA87A; }
  .tab-3.active { background: #0F9E72; border-color: #0F9E72; }
  .tab-4 { background: #FEF4E0; color: #7A4F0A; border-color: #D99020; }
  .tab-4.active { background: #C98010; border-color: #C98010; }
  .tab-5 { background: #FDEBE6; color: #8C2E12; border-color: #E06A3A; }
  .tab-5.active { background: #D5541C; border-color: #D5541C; }
  .tab-6 { background: #EBF5DF; color: #2C5A0E; border-color: #70B820; }
  .tab-6.active { background: #5AA015; border-color: #5AA015; }
  .tab-7 { background: #FCEAF2; color: #7D1A43; border-color: #D55A8A; }
  .tab-7.active { background: #C93B6B; border-color: #C93B6B; }
  @media (prefers-color-scheme: dark) {
    .tab-1 { background: #2A1F4A; color: #C4A8F5; border-color: #9A7ADE; }
    .tab-2 { background: #192A48; color: #90B8F0; border-color: #5B95E0; }
    .tab-3 { background: #0E3328; color: #70D4AC; border-color: #1DA87A; }
    .tab-4 { background: #3A2906; color: #F5C36A; border-color: #D99020; }
    .tab-5 { background: #3B180A; color: #F5A07A; border-color: #E06A3A; }
    .tab-6 { background: #1A3206; color: #A0D865; border-color: #70B820; }
    .tab-7 { background: #3B0E22; color: #F0A0C0; border-color: #D55A8A; }
  }

  ul.dot-list { padding-left: 14px; }
  ul.dot-list li { font-size: 12px; color: var(--color-text-secondary); line-height: 1.6; margin-bottom: 2px; }
  ul.dot-list li strong { color: var(--color-text-primary); font-weight: 700; }

  .section-header {
    font-size: 12px;
    font-weight: 800;
    text-transform: uppercase;
    letter-spacing: 0.8px;
    color: var(--color-text-tertiary);
    margin: 14px 0 8px;
  }

  .formula-box {
    background: var(--color-background-secondary);
    border: 1px solid var(--color-border-secondary);
    border-radius: 8px;
    padding: 10px 13px;
    font-family: 'Fira Code', monospace;
    font-size: 12px;
    line-height: 1.7;
    color: var(--color-text-primary);
    margin: 6px 0;
  }
  .formula-box .fline { display: flex; justify-content: space-between; gap: 8px; border-bottom: 0.5px solid var(--color-border-tertiary); padding-bottom: 4px; margin-bottom: 4px; }
  .formula-box .fline:last-child { border: none; padding: 0; margin: 0; }
  .formula-box .flabel { color: var(--color-text-secondary); }
  .formula-box .fval { color: var(--color-text-primary); font-weight: 600; }
</style>

</head><body><div class="mm-root">
  <div class="mm-title">🏛 Mapa Mental — Direito Constitucional</div>
  <div class="mm-subtitle">Clique nas abas para navegar por cada bloco temático</div>

  <div class="tabs">
    <div class="tab tab-1" onclick="switchTab(1)">📜 Constitucionalismo</div>
    <div class="tab tab-2 active" onclick="switchTab(2)">⚡ Poder Constituinte</div>
    <div class="tab tab-3" onclick="switchTab(3)">📋 Classificação CF</div>
    <div class="tab tab-4" onclick="switchTab(4)">🏗 Estrutura CF/88</div>
    <div class="tab tab-5" onclick="switchTab(5)">🗳 Processo Legislativo</div>
    <div class="tab tab-6" onclick="switchTab(6)">🌐 Competências</div>
    <div class="tab tab-7" onclick="switchTab(7)">🔢 Maiorias &amp; Quórum</div>
  </div>

  <!-- ======= PANEL 1: CONSTITUCIONALISMO ======= -->
  <div class="panel" id="panel-1">
    <div class="grid-2">
      <div>
        <div class="card c1-lft">
          <div class="card-title c1-text">
            <div class="card-icon c1-bg c1-text">📌</div>
            O que é Constitucionalismo?
          </div>
          <div class="hbox c1-bg c1-brd" style="border-left-color:#7C5CBF">
            <strong>Movimento histórico, político e jurídico</strong>
            Surgiu para <b>limitar o poder do Estado</b>. Nasce em oposição ao <b>absolutismo</b>.
          </div>
          <ul class="dot-list" style="margin-top:8px">
            <li>Poder político <strong>não pode ser absoluto</strong></li>
            <li>Deve ser <strong>limitado, controlado e organizado</strong> por normas superiores</li>
            <li>A Constituição é o <strong>fundamento de validade</strong> do poder</li>
          </ul>
        </div>

        <div class="card c2-lft">
          <div class="card-title c2-text">
            <div class="card-icon c2-bg c2-text">⚖️</div>
            Contratualistas — Estado de Natureza
          </div>
          <table class="ctable">
            <thead>
              <tr><th style="width:28%">Autor</th><th>Estado de Natureza</th><th>Modelo</th></tr>
            </thead>
            <tbody>
              <tr>
                <td><span class="tag c8-bg c8-text">Hobbes</span></td>
                <td><i>"Guerra de todos contra todos"</i> — homem é lobo do homem</td>
                <td>Estado <b>Absolutista</b> (Leviatã)</td>
              </tr>
              <tr>
                <td><span class="tag c4-bg c4-text">Locke</span></td>
                <td>Paz <b>instável</b>. Há direitos naturais: vida, liberdade, propriedade</td>
                <td>Monarquia <b>Parlamentar</b> / Estado Liberal</td>
              </tr>
              <tr>
                <td><span class="tag c3-bg c3-text">Rousseau</span></td>
                <td>Liberdade plena — homem é <b>bom por natureza</b>, a sociedade corrompe</td>
                <td>República <b>Democrática</b> — Vontade Geral</td>
              </tr>
            </tbody>
          </table>
        </div>

        <div class="card c4-lft">
          <div class="card-title c4-text">
            <div class="card-icon c4-bg c4-text">📖</div>
            Obras Fundamentais
          </div>
          <div class="steps">
            <div class="step">
              <div class="step-num c8-bg c8-text">1</div>
              <div><strong>Leviatã</strong> — Hobbes (1651): Estado absolutista como solução ao caos</div>
            </div>
            <div class="step">
              <div class="step-num c4-bg c4-text">2</div>
              <div><strong>Dois Tratados</strong> — Locke (1689): Limites ao poder, direitos naturais</div>
            </div>
            <div class="step">
              <div class="step-num c3-bg c3-text">3</div>
              <div><strong>Do Contrato Social</strong> — Rousseau (1762): Soberania popular, vontade geral</div>
            </div>
            <div class="step">
              <div class="step-num c2-bg c2-text">4</div>
              <div><strong>O Espírito das Leis</strong> — Montesquieu (1748): Separação de Poderes</div>
            </div>
          </div>
        </div>
      </div>

      <div>
        <div class="card c5-lft">
          <div class="card-title c5-text">
            <div class="card-icon c5-bg c5-text">🌍</div>
            Revoluções &amp; Marcos Constitucionais
          </div>
          <div class="timeline">
            <div class="titem" style="">
              <div class="titem::before" style="background:#C98010"></div>
              <div class="titem-year c4-text" style="background:#FEF4E0;padding:1px 7px;border-radius:8px;display:inline-block">1688</div>
              <div class="titem-text"><strong>Revolução Gloriosa</strong> — Inglaterra. Enfraquece absolutismo, fortalece Parlamento. Inspira Montesquieu.</div>
            </div>
            <div class="titem">
              <div class="titem-year c5-text" style="background:#FDEBE6;padding:1px 7px;border-radius:8px;display:inline-block">1776</div>
              <div class="titem-text"><strong>Declaração de Independência EUA</strong> — Locke: vida + liberdade + busca da felicidade</div>
            </div>
            <div class="titem">
              <div class="titem-year c2-text" style="background:#E7F0FD;padding:1px 7px;border-radius:8px;display:inline-block">1787</div>
              <div class="titem-text"><strong>Constituição dos EUA</strong> — Primeira CF escrita moderna em vigor. Federalismo + Separação de Poderes</div>
            </div>
            <div class="titem">
              <div class="titem-year c1-text" style="background:#EDE9FC;padding:1px 7px;border-radius:8px;display:inline-block">1789</div>
              <div class="titem-text"><strong>Revolução Francesa</strong> — Declaração dos Direitos do Homem e Cidadão. Sieyès: "O que é o Terceiro Estado?"</div>
            </div>
            <div class="titem">
              <div class="titem-year c8-text" style="background:#FEECEC;padding:1px 7px;border-radius:8px;display:inline-block">1803</div>
              <div class="titem-text"><strong>Marbury vs Madison</strong> — Suprema Corte EUA. Consolida o <b>Judicial Review</b> (Controle de Constitucionalidade)</div>
            </div>
          </div>
        </div>

        <div class="card c3-lft">
          <div class="card-title c3-text">
            <div class="card-icon c3-bg c3-text">🔑</div>
            Conceito de Constituição — Sentidos
          </div>
          <div class="grid-2" style="gap:8px">
            <div class="hbox c1-bg" style="border-color:#7C5CBF">
              <strong>Sociológico — Lassalle</strong>
              CF real = soma dos <b>fatores reais de poder</b>. CF escrita pode ser só "folha de papel".
            </div>
            <div class="hbox c4-bg" style="border-color:#C98010">
              <strong>Político — Carl Schmitt</strong>
              CF = <b>decisão política fundamental</b>. Diferencia CF de leis constitucionais acessórias.
            </div>
            <div class="hbox c2-bg" style="border-color:#3B7FDD">
              <strong>Jurídico — Kelsen</strong>
              CF = norma positiva suprema. <b>Grundnorm</b> (norma fundamental hipotética) funda o sistema.
            </div>
            <div class="hbox c3-bg" style="border-color:#0F9E72">
              <strong>Formal vs Material</strong>
              <b>Formal:</b> o que está no texto. <b>Material:</b> o que é essencial ao Estado (org. do poder, direitos fundamentais).
            </div>
          </div>
        </div>

        <div class="postit c4-bg">
          <strong>⚠️ Constitucionalismo Liberal — Contradição Histórica</strong>
          Universal no <b>discurso</b>, mas excludente na <b>prática</b>: somente homens brancos, adultos, proprietários e alfabetizados eram considerados "livres e iguais". Mulheres, escravos, pobres e indígenas ficavam fora.
        </div>
      </div>
    </div>

    <div class="section-header">⚙️ Conceito Final de Constituição</div>
    <div class="card c9-lft">
      <div style="font-size:13px;line-height:1.7;color:var(--color-text-secondary)">
        <b style="color:var(--color-text-primary)">Constituição</b> é um sistema de normas jurídicas (escritas ou costumeiras) que regula: forma do Estado, forma de governo, aquisição e exercício do poder, organização dos órgãos estatais, limites da atuação estatal, direitos fundamentais e garantias. Ela organiza os elementos constitutivos do Estado: <span class="tag c2-bg c2-text">território</span> <span class="tag c3-bg c3-text">população</span> <span class="tag c1-bg c1-text">governo</span>
      </div>
    </div>
  </div>

  <!-- ======= PANEL 2: PODER CONSTITUINTE ======= -->
  <div class="panel active" id="panel-2">
    <div class="grid-2">
      <div>
        <div class="card c1-lft">
          <div class="card-title c1-text">
            <div class="card-icon c1-bg c1-text">⚡</div>
            Poder Constituinte Originário
          </div>
          <div class="grid-3" style="gap:7px;margin-bottom:10px">
            <div class="pillar c1-bg">
              <div class="pillar-icon">🌱</div>
              <div class="pillar-main c1-text">Inicial</div>
              <div style="font-size:11px;color:var(--color-text-secondary);margin-top:2px">Não deriva de nenhum outro poder anterior</div>
            </div>
            <div class="pillar c8-bg">
              <div class="pillar-icon">♾️</div>
              <div class="pillar-main c8-text">Ilimitado</div>
              <div style="font-size:11px;color:var(--color-text-secondary);margin-top:2px">Não tem limites jurídicos formais</div>
            </div>
            <div class="pillar c4-bg">
              <div class="pillar-icon">🔓</div>
              <div class="pillar-main c4-text">Incondicionado</div>
              <div style="font-size:11px;color:var(--color-text-secondary);margin-top:2px">Não obedece à ordem anterior</div>
            </div>
          </div>
          <div class="hbox c8-bg" style="border-color:#D84343">
            <strong>⚠️ Paradoxo Central</strong>
            O poder que <b>cria limites</b> é, ele próprio, <b>ilimitado na origem</b>. Uma vez criado o sistema, ele precisa se autolimitar para sobreviver. Sem limites → autoritarismo. Sem atualização → anacronismo.
          </div>
        </div>

        <div class="card c2-lft">
          <div class="card-title c2-text">
            <div class="card-icon c2-bg c2-text">🔧</div>
            Poder Constituinte Derivado
          </div>
          <table class="ctable">
            <thead><tr><th>Tipo</th><th>Função</th><th>Base</th></tr></thead>
            <tbody>
              <tr>
                <td><span class="tag c2-bg c2-text">Reformador</span></td>
                <td>Emendas constitucionais. Modifica a CF dentro dos limites do art. 60</td>
                <td><b>Art. 60 CF</b></td>
              </tr>
              <tr>
                <td><span class="tag c3-bg c3-text">Decorrente</span></td>
                <td>Estados-membros elaboram Constituições Estaduais respeitando a CF Federal</td>
                <td><b>Art. 25 + ADCT art. 11</b></td>
              </tr>
            </tbody>
          </table>
          <div class="hbox c3-bg" style="border-color:#0F9E72;margin-top:8px">
            Características do derivado: <span class="badge c2-bg c2-text">Sequencial</span> <span class="badge c4-bg c4-text">Condicionado</span> <span class="badge c8-bg c8-text">Limitado</span>
          </div>
        </div>

        <div class="card c4-lft">
          <div class="card-title c4-text">
            <div class="card-icon c4-bg c4-text">🚧</div>
            Limitações ao Poder Derivado
          </div>
          <div class="steps">
            <div class="step">
              <div class="step-num c5-bg c5-text">1</div>
              <div><strong>Circunstanciais</strong> — Art. 60 §1º: Proibido emendar durante <b>intervenção federal, estado de defesa, estado de sítio</b></div>
            </div>
            <div class="step">
              <div class="step-num c4-bg c4-text">2</div>
              <div><strong>Temporais</strong> — Proibido alterar CF durante certo período após sua criação (ex: ADCT → 5 anos)</div>
            </div>
            <div class="step">
              <div class="step-num c2-bg c2-text">3</div>
              <div><strong>Formais/Procedimentais</strong> — Art. 60 §2º: PEC exige 3/5 em 2 turnos em cada Casa</div>
            </div>
            <div class="step">
              <div class="step-num c8-bg c8-text">4</div>
              <div><strong>Materiais — Cláusulas Pétreas</strong> — Art. 60 §4º: Não se pode tendente a abolir os 4 pilares</div>
            </div>
          </div>
        </div>
      </div>

      <div>
        <div class="card c8-lft">
          <div class="card-title c8-text">
            <div class="card-icon c8-bg c8-text">💎</div>
            Cláusulas Pétreas — Art. 60 §4º CF
          </div>
          <div style="margin-bottom:8px;font-size:12px;color:var(--color-text-secondary)">Proibido emendar para <b>tendente a abolir</b>:</div>
          <div class="petrea-box c2-bg">
            <span class="petrea-icon">🗺️</span>
            <div><strong class="c2-text">Forma Federativa do Estado</strong><br><span style="font-size:11px;color:var(--color-text-secondary)">Brasil mantém: União + Estados + Municípios com autonomia</span></div>
          </div>
          <div class="petrea-box c3-bg">
            <span class="petrea-icon">🗳️</span>
            <div><strong class="c3-text">Voto Direto, Secreto, Universal e Periódico</strong><br><span style="font-size:11px;color:var(--color-text-secondary)">Sistema eleitoral democrático não pode ser abolido</span></div>
          </div>
          <div class="petrea-box c1-bg">
            <span class="petrea-icon">⚖️</span>
            <div><strong class="c1-text">Separação dos Poderes</strong><br><span style="font-size:11px;color:var(--color-text-secondary)">Legislativo + Executivo + Judiciário — evita concentração</span></div>
          </div>
          <div class="petrea-box c5-bg">
            <span class="petrea-icon">🛡️</span>
            <div><strong class="c5-text">Direitos e Garantias Individuais</strong><br><span style="font-size:11px;color:var(--color-text-secondary)">Liberdade, igualdade, direito de defesa, devido processo legal</span></div>
          </div>
          <div class="postit c4-bg" style="margin-top:10px">
            <strong>⚠️ "Tendente a abolir"</strong>
            Não precisa abolir totalmente — se <b>ameaça ou enfraquece gravemente</b> esses princípios, já é inconstitucional. O STF (Art. 102) é o guardião.
          </div>
        </div>

        <div class="card c3-lft">
          <div class="card-title c3-text">
            <div class="card-icon c3-bg c3-text">📜</div>
            Sieyès vs Rousseau — Diferença Central
          </div>
          <table class="ctable">
            <thead><tr><th>Aspecto</th><th>Rousseau — Povo</th><th>Sieyès — Nação</th></tr></thead>
            <tbody>
              <tr><td>Titular</td><td>Indivíduos vivos</td><td>Entidade permanente</td></tr>
              <tr><td>Natureza</td><td>Realidade momentânea</td><td>Realidade histórica</td></tr>
              <tr><td>Exercício</td><td>Democracia <b>direta</b></td><td>Democracia <b>representativa</b></td></tr>
              <tr><td>Soberania</td><td>Não pode ser representada</td><td>Exercida por representantes</td></tr>
            </tbody>
          </table>
        </div>

        <div class="card c5-lft">
          <div class="card-title c5-text">
            <div class="card-icon c5-bg c5-text">🔁</div>
            Efeitos de Nova Constituição
          </div>
          <ul class="dot-list">
            <li><strong>CF anterior:</strong> perde validade — nova CF inaugura nova ordem jurídica</li>
            <li><strong>Leis anteriores:</strong> <b>recepção</b> se compatíveis, revogação automática se incompatíveis</li>
            <li><strong>Repristinação:</strong> lei revogada <b>não volta</b> automaticamente — só se expressamente declarado (LINDB)</li>
            <li><strong>Suspensão de eficácia ≠ Revogação:</strong> norma suspensa existe mas não produz efeitos</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <!-- ======= PANEL 3: CLASSIFICAÇÃO CF ======= -->
  <div class="panel" id="panel-3">
    <div class="section-header">📋 1. Quanto à Forma de Expressão</div>
    <div class="grid-2">
      <div class="card c2-lft">
        <div class="card-title c2-text"><div class="card-icon c2-bg c2-text">📄</div>Escritas (Codificadas)</div>
        <ul class="dot-list">
          <li>Texto único e sistematizado formalmente registrado</li>
          <li>Maior clareza normativa e interpretação jurídica uniforme</li>
          <li>Surgem em <strong>momentos de ruptura política</strong></li>
          <li>Exemplos: <span class="tag c2-bg c2-text">Brasil</span> <span class="tag c2-bg c2-text">EUA</span> <span class="tag c2-bg c2-text">França</span> <span class="tag c2-bg c2-text">Espanha</span></li>
        </ul>
      </div>
      <div class="card c4-lft">
        <div class="card-title c4-text"><div class="card-icon c4-bg c4-text">📜</div>Costumeiras (Não Codificadas)</div>
        <ul class="dot-list">
          <li>Formadas por <strong>costumes, tradições e precedentes jurídicos</strong></li>
          <li>Sempre haverá também alguns textos escritos — sistema <b>híbrido</b></li>
          <li>Surgem <strong>gradualmente</strong> ao longo do tempo</li>
          <li>Exemplos: <span class="tag c4-bg c4-text">Reino Unido</span> <span class="tag c4-bg c4-text">Israel</span> <span class="tag c4-bg c4-text">Nova Zelândia</span></li>
        </ul>
        <div class="hbox c4-bg" style="border-color:#C98010;margin-top:8px">
          <strong>📜 Documentos Históricos ingleses:</strong>
          Magna Carta (1215) — Art. 39: Julgamento pelos pares → base do júri moderno. Bill of Rights (1689).
        </div>
      </div>
    </div>

    <div class="section-header">🔧 2. Quanto à Rigidez (Processo de Reforma)</div>
    <div class="grid-3">
      <div class="card c3-lft">
        <div class="card-title c3-text"><div class="card-icon c3-bg c3-text">🌊</div>Flexível</div>
        <ul class="dot-list">
          <li>Alterada pelo <strong>mesmo procedimento</strong> da lei ordinária</li>
          <li>Sem hierarquia normativa rígida</li>
          <li>Toda CF costumeira é naturalmente <b>flexível</b></li>
        </ul>
        <div class="tag c3-bg c3-text" style="margin-top:8px;display:block;text-align:center;padding:5px">Ex: Reino Unido • Estatuto Albertino (1848)</div>
      </div>
      <div class="card c8-lft">
        <div class="card-title c8-text"><div class="card-icon c8-bg c8-text">🧱</div>Rígida</div>
        <ul class="dot-list">
          <li>Exige <strong>procedimento especial mais complexo</strong></li>
          <li>Quórum qualificado + votação em 2 turnos</li>
          <li>Protege contra mudanças políticas momentâneas</li>
        </ul>
        <div class="tag c8-bg c8-text" style="margin-top:8px;display:block;text-align:center;padding:5px">Ex: Brasil — Art. 60 (PEC: 3/5, 2 turnos, cada Casa)</div>
      </div>
      <div class="card c4-lft">
        <div class="card-title c4-text"><div class="card-icon c4-bg c4-text">⚖️</div>Semirrígida</div>
        <ul class="dot-list">
          <li>Parte pode ser alterada <strong>como lei ordinária</strong></li>
          <li>Outra parte exige <strong>procedimento especial</strong></li>
          <li>Hierarquia <b>interna</b> dentro da própria CF</li>
        </ul>
        <div class="tag c4-bg c4-text" style="margin-top:8px;display:block;text-align:center;padding:5px">Ex: CF brasileira de 1824 (Império)</div>
      </div>
    </div>

    <div class="section-header">🎯 3. Quanto à Missão Histórica</div>
    <div class="grid-2">
      <div>
        <div class="card c3-lft">
          <div class="card-title c3-text"><div class="card-icon c3-bg c3-text">🛡️</div>Constituição-Garantia (Estado Liberal)</div>
          <ul class="dot-list">
            <li>Protege <strong>liberdades individuais</strong> contra o Estado</li>
            <li>Direitos de <b>1ª geração</b>: liberdade, propriedade, igualdade formal</li>
            <li>Estado <b>mínimo</b>, não intervencionista</li>
            <li><b>Igualdade formal:</b> "todos iguais perante a lei" — mas desigualdades sociais persistem</li>
          </ul>
          <div class="postit c3-bg" style="margin-top:8px">
            <strong>Rui Barbosa:</strong> "Igualdade não é tratar todos igualmente, mas tratar desigualmente os desiguais na medida de suas desigualdades." → Antecipa a <b>igualdade material</b>
          </div>
        </div>
        <div class="card c2-lft">
          <div class="card-title c2-text"><div class="card-icon c2-bg c2-text">🎯</div>Constituição-Dirigente (Canotilho)</div>
          <ul class="dot-list">
            <li>Orienta o Estado para um <strong>projeto político e social específico</strong></li>
            <li>Origem: Revolução dos Cravos (Portugal, 1974) → CF portuguesa de 1976</li>
            <li>Influenciou CF brasileira de 1988</li>
            <li>Exemplos no Brasil: <b>IPTU progressivo</b>, inconstitucionalidade por omissão</li>
          </ul>
          <div class="hbox c2-bg" style="border-color:#3B7FDD;margin-top:6px">
            <strong>Despetrificação em Portugal:</strong> Portugal alterou cláusulas rígidas para adaptar ao mercado europeu. Canotilho admitiu que a teoria tinha "carga acadêmica excessiva".
          </div>
        </div>
      </div>
      <div>
        <div class="card c5-lft">
          <div class="card-title c5-text"><div class="card-icon c5-bg c5-text">📋</div>Constituição-Programa</div>
          <ul class="dot-list">
            <li>Contém <strong>normas programáticas</strong> — metas a serem realizadas</li>
            <li>CF não apenas garante direitos, ela <b>planeja políticas públicas</b></li>
            <li>Estado passa a <b>intervir</b> na ordem social e econômica</li>
            <li>Exemplo: Art. 196 CF — "Saúde é direito de todos e <b>dever do Estado</b>"</li>
            <li>Vincula prefeitos, governadores e presidente</li>
          </ul>
          <div class="badge c5-bg c5-text">Normas programáticas não são autoexecutáveis → precisam de lei posterior</div>
        </div>
        <div class="card c1-lft">
          <div class="card-title c1-text"><div class="card-icon c1-bg c1-text">📊</div>Constituição-Balanço (Soviética)</div>
          <ul class="dot-list">
            <li>Registra <strong>conquistas já realizadas</strong> (fotografia do progresso)</li>
            <li>Critica CFs ocidentais por "promessas não cumpridas"</li>
            <li>Contexto: União Soviética — governo Stalin</li>
          </ul>
          <div class="hbox c8-bg" style="border-color:#D84343;margin-top:6px">
            <strong>⚠️ Problema:</strong> Em Estados autoritários o "balanço" pode ser propaganda. Associada à economia planificada e controle político.
          </div>
        </div>
        <div class="card c4-lft" style="margin-top:0">
          <div class="card-title c4-text"><div class="card-icon c4-bg c4-text">📍</div>Quanto ao Processo de Surgimento</div>
          <div class="grid-2" style="gap:8px">
            <div class="hbox c3-bg" style="border-color:#0F9E72">
              <strong>Histórica</strong>
              Formação gradual. Ex: Inglaterra. Toda CF tem história, mas nem toda surgiu sem ruptura.
            </div>
            <div class="hbox c2-bg" style="border-color:#3B7FDD">
              <strong>Dogmática</strong>
              Ruptura política específica. Estabelece "dogmas políticos" (democracia, sep. poderes). Ex: CF 1988.
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="section-header">🇧🇷 4. Constituições Brasileiras</div>
    <div class="card c9-lft">
      <div class="timeline">
        <div class="titem"><div class="titem-year c4-text" style="background:#FEF4E0;padding:1px 7px;border-radius:8px;display:inline-block">1824</div><div class="titem-text"><b>Imperial</b> — Outorgada por D. Pedro I. Semirrígida. 4 poderes (Moderador de Benjamin Constant). Único modelo semirrígido especifico do mundo.</div></div>
        <div class="titem"><div class="titem-year c2-text" style="background:#E7F0FD;padding:1px 7px;border-radius:8px;display:inline-block">1891</div><div class="titem-text"><b>1ª República</b> — Promulgada. Inspirada nos EUA (Rui Barbosa). República presidencialista + Federalismo.</div></div>
        <div class="titem"><div class="titem-year c3-text" style="background:#E0F5EE;padding:1px 7px;border-radius:8px;display:inline-block">1934</div><div class="titem-text"><b>Social</b> — Promulgada. Pós Revolução de 1932 (São Paulo). Primeira a incorporar direitos sociais, voto feminino, voto secreto. Primeira programática no Brasil.</div></div>
        <div class="titem"><div class="titem-year c8-text" style="background:#FEECEC;padding:1px 7px;border-radius:8px;display:inline-block">1937</div><div class="titem-text"><b>Estado Novo</b> — Outorgada por Vargas. Autoritária, inspirada em regimes fascistas europeus. Caso dos Irmãos Naves (condenação por tortura).</div></div>
        <div class="titem"><div class="titem-year c3-text" style="background:#E0F5EE;padding:1px 7px;border-radius:8px;display:inline-block">1946</div><div class="titem-text"><b>Redemocratização</b> — Promulgada. Pós queda de Vargas. Restabelecimento da democracia.</div></div>
        <div class="titem"><div class="titem-year c5-text" style="background:#FDEBE6;padding:1px 7px;border-radius:8px;display:inline-block">1967/69</div><div class="titem-text"><b>Regime Militar</b> — Outorgada. Emenda 1/1969 (pós AI-5): muitos juristas consideram nova CF material.</div></div>
        <div class="titem"><div class="titem-year c1-text" style="background:#EDE9FC;padding:1px 7px;border-radius:8px;display:inline-block">1988</div><div class="titem-text"><b>"Constituição Cidadã"</b> (Ulysses Guimarães) — Promulgada. Social, Dirigente, Rígida, Programática. Estado Democrático de Direito.</div></div>
      </div>
    </div>
  </div>

  <!-- ======= PANEL 4: ESTRUTURA CF/88 ======= -->
  <div class="panel" id="panel-4">
    <div class="grid-2">
      <div>
        <div class="card c2-lft">
          <div class="card-title c2-text"><div class="card-icon c2-bg c2-text">📑</div>Estrutura Topográfica da CF/88</div>
          <div class="steps">
            <div class="step"><div class="step-num c1-bg c1-text">T1</div><div><strong>Princípios Fundamentais</strong> — Arts. 1-4: soberania, cidadania, dignidade, valores sociais do trabalho e livre iniciativa, pluralismo político</div></div>
            <div class="step"><div class="step-num c2-bg c2-text">T2</div><div><strong>Direitos e Garantias Fundamentais</strong> — <i>"Catálogo"</i> de direitos. Mas nem todos os direitos estão apenas aqui.</div></div>
            <div class="step"><div class="step-num c3-bg c3-text">T3</div><div><strong>Organização do Estado</strong> — Arts. 18-43: Bens da União (art. 20), Competências (arts. 21-24), DF, Municípios</div></div>
            <div class="step"><div class="step-num c4-bg c4-text">T4</div><div><strong>Organização dos Poderes</strong> — Legislativo, Executivo, Judiciário. Funções essenciais (MP, Def. Pública, Advocacia)</div></div>
            <div class="step"><div class="step-num c5-bg c5-text">T5</div><div><strong>Defesa do Estado e das Inst.</strong> — Forças Armadas (art. 142). Diferença: soldado (defesa) × policial (segurança interna)</div></div>
            <div class="step"><div class="step-num c6-bg c6-text">T6</div><div><strong>Tributação e Orçamento</strong> — Princípios tributários, limites, competências + Código Tributário Nacional</div></div>
            <div class="step"><div class="step-num c7-bg c7-text">T7</div><div><strong>Ordem Econômica e Financeira</strong> — Atividade econômica, propriedade, intervenção estatal</div></div>
            <div class="step"><div class="step-num c8-bg c8-text">T8</div><div><strong>Ordem Social</strong> — Saúde, Educação, Previdência, SUS, Assistência Social</div></div>
          </div>
        </div>

        <div class="card c4-lft">
          <div class="card-title c4-text"><div class="card-icon c4-bg c4-text">📋</div>ADCT — Ato das Disp. Constitucionais Transitórias</div>
          <ul class="dot-list">
            <li>114 artigos de normas <strong>transitórias</strong> de adaptação entre o sistema antigo e o novo</li>
            <li>Art. 11 ADCT: autoriza Estados-membros a elaborar suas Constituições Estaduais</li>
            <li>Limitação temporal: <strong>5 anos sem emendas</strong> após promulgação</li>
            <li>Contexto: Ulysses Guimarães: <i>"Temos ódio e nojo da ditadura"</i></li>
            <li>Algumas normas transitórias <b>continuam válidas até hoje</b></li>
          </ul>
        </div>
      </div>
      <div>
        <div class="card c3-lft">
          <div class="card-title c3-text"><div class="card-icon c3-bg c3-text">⚙️</div>Microestrutura das Leis — Articulação</div>
          <div class="formula-box">
            <div class="fline"><span class="flabel">Artigo (Art.)</span><span class="fval">Unidade básica. 1º-9º: ordinal. 10+: cardinal</span></div>
            <div class="fline"><span class="flabel">Parágrafo (§)</span><span class="fval">Explicação/exceção. Único quando só há um.</span></div>
            <div class="fline"><span class="flabel">Incisos (I, II...)</span><span class="fval">Listas em algarismos romanos</span></div>
            <div class="fline"><span class="flabel">Alíneas (a, b...)</span><span class="fval">Subdivisões do inciso em letras minúsculas</span></div>
            <div class="fline"><span class="flabel">Itens (1, 2...)</span><span class="fval">Subdivisões das alíneas</span></div>
          </div>
          <div class="formula-box" style="margin-top:8px">
            <div class="fline"><span class="flabel">Macroarticulação</span><span class="fval">Subseção → Seção → Capítulo → Título → Livro → Parte</span></div>
          </div>
        </div>

        <div class="card c1-lft">
          <div class="card-title c1-text"><div class="card-icon c1-bg c1-text">📚</div>Legiferação — LC 95/1998</div>
          <ul class="dot-list">
            <li><strong>Uma lei = um único objeto</strong> (Art. 7º) — evita "contrabando legislativo"</li>
            <li><strong>Vigência expressa</strong> (Art. 8º) — indicar quando a lei entra em vigor</li>
            <li><strong>Vacância</strong>: período entre publicação e entrada em vigor. Fórmula: "entra em vigor após X dias"</li>
            <li><strong>Revogação expressa</strong> (Art. 9º) — deve indicar quais leis são revogadas</li>
            <li>Alteração = <strong>revogação parcial</strong>. Inserção: não renumerar, usar letras (103-A, 103-B)</li>
            <li>Nova redação identificada por: <span class="tag c2-bg c2-text">(NR)</span></li>
            <li>Art. 18: imprecisão formal <b>não</b> autoriza descumprimento</li>
          </ul>
          <div class="hbox c3-bg" style="border-color:#0F9E72;margin-top:6px">
            <strong>Lei boa = Clara + Precisa + Lógica</strong>
            Palavras no sentido comum. Mesma palavra para mesma ideia. Frases curtas. Ordem direta (sujeito → verbo → complemento). Evitar regionalismos. Números por extenso.
          </div>
        </div>

        <div class="card c5-lft">
          <div class="card-title c5-text"><div class="card-icon c5-bg c5-text">🔍</div>LC vs Lei Ordinária</div>
          <table class="ctable">
            <thead><tr><th>Aspecto</th><th>Lei Complementar</th><th>Lei Ordinária</th></tr></thead>
            <tbody>
              <tr><td>Matéria</td><td>Estrutura do Estado, temas constitucionalmente reservados</td><td>Questões cotidianas, administrativas</td></tr>
              <tr><td>Aprovação</td><td><b>Maioria absoluta</b> (Art. 69)</td><td><b>Maioria relativa</b> (Art. 47)</td></tr>
              <tr><td>Hierarquia</td><td colspan="2" style="text-align:center">Não há hierarquia entre elas — matérias distintas</td></tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>

  <!-- ======= PANEL 5: PROCESSO LEGISLATIVO ======= -->
  <div class="panel" id="panel-5">
    <div class="grid-2">
      <div>
        <div class="card c2-lft">
          <div class="card-title c2-text"><div class="card-icon c2-bg c2-text">🗳️</div>Espécies Normativas — Art. 59 CF</div>
          <div class="hbox c1-bg" style="border-color:#7C5CBF">
            <strong>⚠️ PEC não é processo legislativo ordinário!</strong>
            É processo constituinte derivado. Mesmo estando no art. 59 por organização.
          </div>
          <div class="steps" style="margin-top:8px">
            <div class="step"><div class="step-num c8-bg c8-text">▲</div><div><strong>Emendas Constitucionais</strong> — PEC: 3/5, 2 turnos, cada Casa. Sem sanção presidencial</div></div>
            <div class="step"><div class="step-num c1-bg c1-text">●</div><div><strong>Leis Complementares</strong> — maioria absoluta. Art. 69</div></div>
            <div class="step"><div class="step-num c2-bg c2-text">●</div><div><strong>Leis Ordinárias</strong> — maioria relativa. Art. 47</div></div>
            <div class="step"><div class="step-num c4-bg c4-text">●</div><div><strong>Medidas Provisórias</strong> — Presidente. Força de lei. Prazo 60+60 dias</div></div>
            <div class="step"><div class="step-num c3-bg c3-text">●</div><div><strong>Decretos Legislativos</strong> — matérias específicas do Congresso (ex: tratados)</div></div>
            <div class="step"><div class="step-num c9-bg" style="color:var(--color-text-secondary);background:var(--color-background-secondary)">●</div><div><strong>Resoluções</strong> — cada Casa para matérias de interesse próprio</div></div>
          </div>
        </div>

        <div class="card c3-lft">
          <div class="card-title c3-text"><div class="card-icon c3-bg c3-text">👥</div>Iniciativa — Quem pode propor leis?</div>
          <table class="ctable">
            <thead><tr><th>Legitimado</th><th>Casa Iniciadora</th></tr></thead>
            <tbody>
              <tr><td>Deputado Federal</td><td>Câmara → depois Senado (revisão)</td></tr>
              <tr><td>Senador</td><td>Senado → depois Câmara (revisão)</td></tr>
              <tr><td>Presidente da República</td><td>Câmara → depois Senado</td></tr>
              <tr><td>STF / Tribunais Superiores</td><td>Câmara → depois Senado</td></tr>
              <tr><td>PGR</td><td>Câmara → depois Senado</td></tr>
              <tr><td>Cidadãos (Iniciativa Popular)</td><td>Câmara → depois Senado</td></tr>
            </tbody>
          </table>
          <div class="postit c4-bg" style="margin-top:8px">
            <strong>💡 Câmara domina o processo:</strong>
            Inicia ~99% dos projetos (Arts. 61 §2º e 64 CF). Logo, o Senado quase sempre atua como <b>casa revisora</b>.
          </div>
        </div>
      </div>
      <div>
        <div class="card c5-lft">
          <div class="card-title c5-text"><div class="card-icon c5-bg c5-text">🔄</div>Tramitação — Casa Iniciadora × Casa Revisora</div>
          <div class="steps">
            <div class="step"><div class="step-num c2-bg c2-text">1</div><div><strong>Casa Iniciadora:</strong> Aprova ✅ → segue para revisora | Rejeita ❌ → <b>arquivamento</b> (ato de exaurimento)</div></div>
            <div class="step"><div class="step-num c3-bg c3-text">2</div><div><strong>Casa Revisora:</strong><br>• Aprova integralmente → vai para Presidente<br>• Aprova com emendas → volta para Iniciadora<br>• Rejeita in totum → projeto morre</div></div>
            <div class="step"><div class="step-num c4-bg c4-text">3</div><div><strong>Presidente:</strong> Sanção ✅ ou Veto ❌ (total ou parcial). Veto pode ser derrubado pelo Congresso.</div></div>
            <div class="step"><div class="step-num c5-bg c5-text">4</div><div><strong>Promulgação + Publicação</strong> no Diário Oficial → lei existe oficialmente</div></div>
          </div>
          <div class="hbox c8-bg" style="border-color:#D84343;margin-top:8px">
            <strong>PEC: SEM sanção presidencial!</strong>
            Seria dar ao Executivo poder sobre o poder reformador da CF. PEC é promulgada pelas Mesas da Câmara e do Senado diretamente.
          </div>
        </div>

        <div class="card c1-lft">
          <div class="card-title c1-text"><div class="card-icon c1-bg c1-text">📜</div>PEC — Proposta de Emenda Constitucional</div>
          <div class="section-header" style="margin-top:4px">Quem pode propor (Art. 60):</div>
          <div class="grid-3" style="gap:6px;margin-bottom:8px">
            <div class="hbox c2-bg" style="border-color:#3B7FDD;text-align:center"><strong>1/3 da Câmara</strong><br>1/3 × 513 = <b>171 deputados</b></div>
            <div class="hbox c1-bg" style="border-color:#7C5CBF;text-align:center"><strong>1/3 do Senado</strong><br>1/3 × 81 = <b>27 senadores</b></div>
            <div class="hbox c3-bg" style="border-color:#0F9E72;text-align:center"><strong>Assembleias Estaduais</strong><br>Maioria de <b>14</b> das 27 casas</div>
          </div>
          <div class="hbox c4-bg" style="border-color:#C98010">
            <strong>Quórum de Aprovação:</strong>
            3/5 dos membros em <b>2 turnos</b> em <b>cada Casa</b> = 4 votações totais. Câmara: 308 votos. Senado: 49 votos.
          </div>
          <div class="hbox c8-bg" style="border-color:#D84343;margin-top:6px">
            <strong>Se rejeitada:</strong> Arquivamento. Não pode reapresentar a mesma PEC na mesma sessão legislativa.
          </div>
        </div>

        <div class="card c4-lft">
          <div class="card-title c4-text"><div class="card-icon c4-bg c4-text">🏛️</div>Bicameralismo &amp; Federalismo</div>
          <div class="grid-2" style="gap:8px">
            <div class="hbox c2-bg" style="border-color:#3B7FDD">
              <strong>Câmara dos Deputados</strong>
              Representa o <b>povo</b>. 513 dep. Mandato 4 anos. Sistema <b>proporcional</b>. Mín 8, Máx 70 dep/estado.
            </div>
            <div class="hbox c3-bg" style="border-color:#0F9E72">
              <strong>Senado Federal</strong>
              Representa os <b>estados</b>. 81 sen. 3/estado. Mandato 8 anos. Renovação 1/3 e 2/3. Sistema <b>majoritário</b>.
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ======= PANEL 6: COMPETÊNCIAS ======= -->
  <div class="panel" id="panel-6">
    <div class="grid-2">
      <div>
        <div class="card c3-lft">
          <div class="card-title c3-text"><div class="card-icon c3-bg c3-text">🗺️</div>Método das 3 Perguntas (Competência Legislativa)</div>
          <div class="steps">
            <div class="step">
              <div class="step-num c2-bg c2-text">1ª</div>
              <div>
                <strong>É competência da União?</strong> → Art. 22 CF<br>
                <span style="font-size:11px;color:var(--color-text-secondary)">Ex: direito penal, civil, comercial, trabalho, trânsito</span><br>
                <span class="badge c2-bg c2-text">Competência Privativa</span> — pode delegar por LC (Art. 22 p.ú.)
              </div>
            </div>
            <div class="step">
              <div class="step-num c5-bg c5-text">2ª</div>
              <div>
                <strong>É competência do Município?</strong> → Art. 30 CF<br>
                <span style="font-size:11px;color:var(--color-text-secondary)">Art. 30 I: interesse local. Art. 30 II: suplementação</span>
              </div>
            </div>
            <div class="step">
              <div class="step-num c4-bg c4-text">3ª</div>
              <div>
                <strong>Se não é União nem Município → é do Estado</strong><br>
                <span style="font-size:11px;color:var(--color-text-secondary)">Art. 25 §1º — Competência residual dos Estados</span>
              </div>
            </div>
          </div>
          <div class="hbox c8-bg" style="border-color:#D84343;margin-top:8px">
            <strong>⚠️ Sem hierarquia entre lei federal, estadual e municipal!</strong>
            O que existe é <b>repartição de competências</b>. Cada ente legisla em seu campo.
          </div>
        </div>

        <div class="card c2-lft">
          <div class="card-title c2-text"><div class="card-icon c2-bg c2-text">🤝</div>Competência Concorrente — Art. 24 CF</div>
          <div class="hbox c1-bg" style="border-color:#7C5CBF">
            <strong>⚠️ Municípios estão FORA do Art. 24!</strong>
            Concorrência é somente entre <b>União e Estados</b>. Federalismo assimétrico.
          </div>
          <div class="steps" style="margin-top:8px">
            <div class="step"><div class="step-num c2-bg c2-text">§1</div><div><strong>União:</strong> normas <b>gerais</b> (princípios, diretrizes, estrutura)</div></div>
            <div class="step"><div class="step-num c3-bg c3-text">§2/3</div><div><strong>Estado:</strong> normas <b>específicas</b>, ajustadas à realidade regional, orientadas pela norma geral da União</div></div>
            <div class="step"><div class="step-num c4-bg c4-text">§3</div><div><strong>Competência Plena:</strong> se a União <b>não legislou</b> ainda → Estado legisla plenamente (preenche vazio)</div></div>
            <div class="step"><div class="step-num c8-bg c8-text">§4</div><div><strong>Lei Federal superveniente →</strong> lei estadual tem eficácia <b>suspensa</b> no que conflitar (não revogada!)</div></div>
          </div>
          <div class="hbox c3-bg" style="border-color:#0F9E72;margin-top:6px">
            <strong>Suspensão ≠ Revogação</strong>
            Suspensão: norma existe mas não produz efeitos. Se lei federal for declarada inconstitucional → lei estadual volta a produzir efeitos!
          </div>
        </div>
      </div>
      <div>
        <div class="card c5-lft">
          <div class="card-title c5-text"><div class="card-icon c5-bg c5-text">🗳️</div>Federalismo Brasileiro</div>
          <div class="grid-3" style="gap:6px;margin-bottom:8px">
            <div class="pillar c2-bg">
              <div class="pillar-icon">🏛️</div>
              <div class="pillar-main c2-text">União</div>
              <div style="font-size:10px;color:var(--color-text-secondary);margin-top:2px">Congresso + Presidente + Judiciário Federal</div>
            </div>
            <div class="pillar c3-bg">
              <div class="pillar-icon">🏴</div>
              <div class="pillar-main c3-text">Estados</div>
              <div style="font-size:10px;color:var(--color-text-secondary);margin-top:2px">Assembleia + Governador + TJ</div>
            </div>
            <div class="pillar c4-bg">
              <div class="pillar-icon">🏘️</div>
              <div class="pillar-main c4-text">Municípios</div>
              <div style="font-size:10px;color:var(--color-text-secondary);margin-top:2px">Câmara + Prefeito. Sem Judiciário próprio</div>
            </div>
          </div>
          <div class="hbox c5-bg" style="border-color:#D5541C">
            <strong>Federalismo TRINO</strong> — peculiaridade brasileira: municípios são entes federativos autônomos (~5.570). Incomum no mundo. Origem: tradição portuguesa.
          </div>
          <div class="hbox c1-bg" style="border-color:#7C5CBF;margin-top:6px">
            <strong>Federalismo Assimétrico:</strong> SP (70 dep. federais) e Roraima (8) têm ambos 3 senadores. Votos do Acre valem proporcionalmente mais que os de SP.
          </div>
        </div>

        <div class="card c4-lft">
          <div class="card-title c4-text"><div class="card-icon c4-bg c4-text">🔢</div>Deputados Estaduais — Art. 27 CF</div>
          <div class="formula-box">
            <div class="fline"><span class="flabel">Até 36 dep. estaduais:</span><span class="fval">triplo dos dep. federais do estado</span></div>
            <div class="fline"><span class="flabel">Acima de 36:</span><span class="fval">36 + (dep. federais − 12)</span></div>
            <div class="fline"><span class="flabel">São Paulo (70 federais):</span><span class="fval">36 + (70−12) = 36+58 = 94 estaduais</span></div>
            <div class="fline"><span class="flabel">Minas (53 federais):</span><span class="fval">36 + (53−12) = 36+41 = 77 estaduais</span></div>
            <div class="fline"><span class="flabel">Roraima (8 federais):</span><span class="fval">8 × 3 = 24 estaduais</span></div>
          </div>
        </div>

        <div class="card c3-lft">
          <div class="card-title c3-text"><div class="card-icon c3-bg c3-text">⚖️</div>Competência Administrativa Comum — Art. 23</div>
          <div class="hbox c3-bg" style="border-color:#0F9E72">
            <strong>⚠️ Art. 23 ≠ legislativa!</strong>
            É competência <b>administrativa/executiva</b>. Todos os entes podem atuar juntos em: proteção ambiental, saúde, educação, assistência social. Mas isso não significa que todos legislam do mesmo jeito.
          </div>
        </div>
      </div>
    </div>
  </div>

  <!-- ======= PANEL 7: MAIORIAS ======= -->
  <div class="panel" id="panel-7">
    <div class="grid-2">
      <div>
        <div class="card c2-lft">
          <div class="card-title c2-text"><div class="card-icon c2-bg c2-text">🔢</div>Tipos de Maioria</div>
          <div class="hbox c2-bg" style="border-color:#3B7FDD;margin-bottom:8px">
            <strong>Definição STF:</strong> Maioria = <b>número inteiro imediatamente superior à metade</b> (não simplesmente "metade + 1" de forma mecânica — resolve o problema do meio voto)
          </div>
          <table class="ctable">
            <thead><tr><th>Tipo</th><th>Base</th><th>Usado em</th></tr></thead>
            <tbody>
              <tr>
                <td><span class="tag c3-bg c3-text">Absoluta</span></td>
                <td>+50% do <b>total</b> de membros (independe dos presentes)</td>
                <td>LC (Art. 69), quórum mínimo para votar</td>
              </tr>
              <tr>
                <td><span class="tag c4-bg c4-text">Relativa/Simples</span></td>
                <td>+50% dos <b>presentes</b> (varia conforme presença)</td>
                <td>Lei Ordinária (Art. 47)</td>
              </tr>
              <tr>
                <td><span class="tag c8-bg c8-text">Qualificada</span></td>
                <td>Fração definida acima da absoluta (3/5, 2/3, 7/9)</td>
                <td>PEC (3/5), Impeachment (2/3)</td>
              </tr>
            </tbody>
          </table>
          <div class="hbox c8-bg" style="border-color:#D84343;margin-top:8px">
            <strong>Regra de Ouro:</strong> Sem maioria absoluta <b>presente</b> → não há votação válida! (quórum de presença ≠ quórum de aprovação)
          </div>
        </div>

        <div class="card c1-lft">
          <div class="card-title c1-text"><div class="card-icon c1-bg c1-text">😱</div>Situação Paradoxal da Lei Ordinária</div>
          <div class="hbox c1-bg" style="border-color:#7C5CBF">
            <strong>Quanto menos gente presente (respeitando o mínimo) → mais fácil aprovar LO!</strong>
          </div>
          <div class="formula-box" style="margin-top:8px">
            <div class="fline"><span class="flabel">51 presentes na Câmara:</span><span class="fval">precisa só 26 SIM</span></div>
            <div class="fline"><span class="flabel">300 presentes na Câmara:</span><span class="fval">precisa de 151 SIM</span></div>
            <div class="fline"><span class="flabel">LC (sempre):</span><span class="fval">precisa de 257 SIM (fixo)</span></div>
          </div>
          <div class="postit c4-bg" style="margin-top:8px">
            <strong>💡 Estratégia política:</strong> Parlamentares podem faltar propositalmente para impedir quórum (bloquear votação) ou para facilitar aprovação de LO controversa!
          </div>
        </div>
      </div>
      <div>
        <div class="card c3-lft">
          <div class="card-title c3-text"><div class="card-icon c3-bg c3-text">📊</div>Calculadora de Maiorias</div>
          <div style="margin-bottom:10px">
            <label style="font-size:12px;font-weight:700;color:var(--color-text-secondary);display:block;margin-bottom:4px">Selecionar casa legislativa:</label>
            <div style="display:flex;gap:6px;flex-wrap:wrap">
              <button onclick="setHouse(513,'Câmara (513)')" id="btn-c" style="padding:5px 12px;border-radius:20px;border:1.5px solid #3B7FDD;background:#E7F0FD;color:#1A4E99;font-size:12px;font-weight:700;cursor:pointer">Câmara 513</button>
              <button onclick="setHouse(81,'Senado (81)')" id="btn-s" style="padding:5px 12px;border-radius:20px;border:1.5px solid #0F9E72;background:#E0F5EE;color:#0A6047;font-size:12px;font-weight:700;cursor:pointer">Senado 81</button>
              <button onclick="setHouse(94,'SP Estadual (94)')" id="btn-sp" style="padding:5px 12px;border-radius:20px;border:1.5px solid #C98010;background:#FEF4E0;color:#7A4F0A;font-size:12px;font-weight:700;cursor:pointer">SP Estadual 94</button>
            </div>
          </div>
          <div style="display:flex;align-items:center;gap:10px;margin-bottom:10px">
            <label style="font-size:12px;font-weight:700;color:var(--color-text-secondary);white-space:nowrap">Presentes:</label>
            <input type="range" id="present-slider" min="1" max="513" value="300" style="flex:1" oninput="calcMaiorias()">
            <span id="present-val" style="font-size:13px;font-weight:800;color:var(--color-text-primary);min-width:32px">267</span>
          </div>
          <div id="calc-results" class="formula-box"><div class="fline"><span class="flabel">Total de membros</span><span class="fval">513</span></div><div class="fline"><span class="flabel">Presentes selecionados</span><span class="fval">267</span></div><div class="fline"><span class="flabel">Maioria absoluta (mínimo presente / LC)</span><span class="fval">257 votos</span></div><div class="fline"><span class="flabel">Lei Ordinária (maioria relativa)</span><span class="fval">134 votos SIM</span></div><div class="fline"><span class="flabel">Lei Complementar (maioria absoluta)</span><span class="fval">257 votos SIM</span></div><div class="fline"><span class="flabel">PEC — 3/5 dos membros</span><span class="fval">308 votos SIM</span></div><div class="fline"><span class="flabel">Impeachment — 2/3</span><span class="fval">342 votos SIM</span></div></div>
          <div id="calc-warning" style="font-size: 11px; margin-top: 6px; display: none;"><span style="color:#D84343;font-weight:700">❌ Não é possível votar! Quórum mínimo: 257 presentes.</span></div>
        </div>

        <div class="card c4-lft">
          <div class="card-title c4-text"><div class="card-icon c4-bg c4-text">📋</div>Hierarquia Normativa (Pirâmide)</div>
          <div class="steps">
            <div class="step"><div class="step-num c8-bg c8-text">▲</div><div><strong>Constituinte (Primordial)</strong> — Normas da CF. Criadas pelo P.C. Originário ou PEC. Topo do sistema.</div></div>
            <div class="step"><div class="step-num c1-bg c1-text">●</div><div><strong>Legislativo Primário</strong> — Art. 59: LC, LO, MP, DL, Resoluções. Normas infraconstitucionais.</div></div>
            <div class="step"><div class="step-num c3-bg c3-text">●</div><div><strong>Regulamentar (Secundário)</strong> — Decretos, Portarias, Regimentos. <b>Não criam direitos novos!</b> Apenas regulamentam a lei.</div></div>
          </div>
          <div class="hbox c3-bg" style="border-color:#0F9E72;margin-top:6px">
            <strong>Regra de Ouro:</strong> Lei → cria obrigação. Regulamento → explica como cumprir. Nunca o contrário!
          </div>
        </div>

        <div class="card c5-lft">
          <div class="card-title c5-text"><div class="card-icon c5-bg c5-text">💡</div>Frase de Ouro — Síntese Final</div>
          <div class="quote c5-bg" style="border-color:#D5541C">
            "A Constituição não é apenas um instrumento técnico-normativo, mas uma construção histórica e política, na qual a legitimidade decorre da soberania popular, enquanto a técnica jurídica atua como instrumento — e não como fundamento — do poder."
            <span class="quote-author">Prof. Resumo das Aulas</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<script>
function switchTab(n) {
  for (let i = 1; i <= 7; i++) {
    document.getElementById('panel-' + i).classList.toggle('active', i === n);
    document.querySelectorAll('.tab')[i-1].classList.toggle('active', i === n);
  }
}

let currentMax = 513;
function setHouse(max, label) {
  currentMax = max;
  const s = document.getElementById('present-slider');
  s.max = max;
  s.value = Math.min(parseInt(s.value), max);
  calcMaiorias();
}

function ceil(x) { return Math.ceil(x); }

function calcMaiorias() {
  const tot = currentMax;
  const pres = parseInt(document.getElementById('present-slider').value);
  document.getElementById('present-val').textContent = pres;

  const abs = ceil(tot / 2);
  const rel = ceil(pres / 2);
  const pec = ceil(tot * 3 / 5);
  const imp = ceil(tot * 2 / 3);

  const ok = pres >= abs;
  const warn = document.getElementById('calc-warning');

  let html = '';
  html += `<div class="fline"><span class="flabel">Total de membros</span><span class="fval">${tot}</span></div>`;
  html += `<div class="fline"><span class="flabel">Presentes selecionados</span><span class="fval">${pres}</span></div>`;
  html += `<div class="fline"><span class="flabel">Maioria absoluta (mínimo presente / LC)</span><span class="fval">${abs} votos</span></div>`;

  if (!ok) {
    html += `<div class="fline" style="color:#D84343"><span class="flabel">⚠️ Sem quórum mínimo!</span><span class="fval">Faltam ${abs - pres}</span></div>`;
    warn.style.display = 'block';
    warn.innerHTML = `<span style="color:#D84343;font-weight:700">❌ Não é possível votar! Quórum mínimo: ${abs} presentes.</span>`;
  } else {
    html += `<div class="fline"><span class="flabel">Lei Ordinária (maioria relativa)</span><span class="fval">${rel} votos SIM</span></div>`;
    html += `<div class="fline"><span class="flabel">Lei Complementar (maioria absoluta)</span><span class="fval">${abs} votos SIM</span></div>`;
    html += `<div class="fline"><span class="flabel">PEC — 3/5 dos membros</span><span class="fval">${pec} votos SIM</span></div>`;
    html += `<div class="fline"><span class="flabel">Impeachment — 2/3</span><span class="fval">${imp} votos SIM</span></div>`;
    warn.style.display = 'none';
  }

  document.getElementById('calc-results').innerHTML = html;
}

calcMaiorias();
</script>
</body></html>
