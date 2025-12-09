<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <title>BTX-Tech | App Clínico Simples</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    :root {
      --bg: #020617;
      --card: #020617;
      --azul1: #0f172a;
      --azul2: #1d4ed8;
      --ciano: #22d3ee;
      --texto: #e5e7eb;
      --texto-suave: #9ca3af;
      --borda: #1f2937;
      --ok: #4ade80;
      --alerta: #facc15;
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      padding: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
        sans-serif;
      background: radial-gradient(circle at top, #0f172a 0, #020617 55%);
      color: var(--texto);
      min-height: 100vh;
    }

    .app-container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 16px;
    }

    .header {
      text-align: center;
      margin-bottom: 16px;
    }

    .logo {
      font-size: 1.1rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: var(--ciano);
      font-weight: 600;
    }

    .titulo {
      margin-top: 4px;
      font-size: 1.5rem;
      font-weight: 700;
      color: #f9fafb;
    }

    .card {
      background: rgba(15, 23, 42, 0.95);
      border-radius: 16px;
      border: 1px solid var(--borda);
      padding: 16px;
      box-shadow: 0 18px 45px rgba(15, 23, 42, 0.7);
    }

    h2, h3 {
      margin: 0 0 10px 0;
      font-weight: 600;
      color: #f9fafb;
    }

    .subtitulo {
      font-size: 0.85rem;
      color: var(--texto-suave);
      margin-bottom: 12px;
    }

    label {
      display: block;
      font-size: 0.8rem;
      margin-bottom: 4px;
      color: var(--texto-suave);
    }

    input, textarea {
      width: 100%;
      padding: 8px 10px;
      border-radius: 10px;
      border: 1px solid var(--borda);
      background: #020617;
      color: var(--texto);
      font-size: 0.9rem;
      outline: none;
    }

    input:focus, textarea:focus {
      border-color: var(--azul2);
      box-shadow: 0 0 0 1px rgba(37, 99, 235, 0.4);
    }

    textarea {
      min-height: 88px;
      resize: vertical;
    }

    .grid-2 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
      gap: 10px;
    }

    .grid-3 {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(160px, 1fr));
      gap: 10px;
    }

    .btn-row {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 12px;
      justify-content: flex-end;
    }

    .btn {
      border: none;
      border-radius: 999px;
      padding: 8px 14px;
      font-size: 0.85rem;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      background: #020617;
      color: var(--texto-suave);
      border: 1px solid var(--borda);
    }

    .btn-primary {
      background: linear-gradient(135deg, var(--azul2), var(--ciano));
      color: #0b1120;
      font-weight: 600;
      border: none;
    }

    .btn-small {
      padding: 4px 10px;
      font-size: 0.75rem;
    }

    .btn:hover {
      opacity: 0.9;
    }

    .tabs {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      margin-top: 14px;
      margin-bottom: 10px;
    }

    .tab-btn {
      flex: 1;
      min-width: 120px;
      text-align: center;
      border-radius: 999px;
      padding: 8px 10px;
      background: #020617;
      color: var(--texto-suave);
      border: 1px solid var(--borda);
      cursor: pointer;
      font-size: 0.85rem;
      font-weight: 500;
    }

    .tab-btn.active {
      background: linear-gradient(135deg, var(--azul2), var(--ciano));
      color: #0b1120;
      border-color: transparent;
    }

    .section {
      display: none;
      margin-top: 6px;
    }

    .section.active {
      display: block;
    }

    .secao-titulo-linha {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 12px;
      margin-bottom: 8px;
    }

    .pill {
      font-size: 0.7rem;
      padding: 3px 8px;
      border-radius: 999px;
      background: rgba(148, 163, 184, 0.15);
      border: 1px solid rgba(148, 163, 184, 0.4);
      color: var(--texto-suave);
    }

    .info-texto {
      font-size: 0.75rem;
      color: var(--texto-suave);
      margin-top: 4px;
    }

    .med-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 6px;
      margin-bottom: 8px;
    }

    .med-buttons .btn-small {
      background: rgba(37, 99, 235, 0.16);
      border-color: rgba(37, 99, 235, 0.4);
      color: #bfdbfe;
    }

    .orc-tabela {
      width: 100%;
      border-collapse: collapse;
      margin-top: 8px;
      font-size: 0.8rem;
    }

    .orc-tabela th,
    .orc-tabela td {
      border: 1px solid var(--borda);
      padding: 6px;
      text-align: left;
    }

    .orc-tabela th {
      background: rgba(15, 23, 42, 0.9);
      font-weight: 600;
    }

    .orc-tabela input {
      padding: 4px 6px;
      font-size: 0.8rem;
    }

    .total-box {
      margin-top: 10px;
      text-align: right;
      font-size: 0.9rem;
      font-weight: 600;
      color: var(--ok);
    }

    .status-bar {
      margin-top: 8px;
      font-size: 0.75rem;
      color: var(--ok);
      min-height: 18px;
    }

    @media (max-width: 600px) {
      .titulo {
        font-size: 1.25rem;
      }
      .card {
        padding: 12px;
      }
    }
  </style>
</head>
<body>
  <div class="app-container">
    <div class="header">
      <div class="logo">BTX-Tech</div>
      <div class="titulo">App Clínico Simples</div>
      <div class="subtitulo">
        Ficha clínica, receituário, atestado e orçamento com memória e geração em PDF.
      </div>
    </div>

    <div class="card">
      <!-- CADASTRO DO PROFISSIONAL -->
      <section>
        <h2>Cadastro do Profissional</h2>
        <div class="subtitulo">
          Funciona para qualquer profissão ou conselho de classe (CRO, CRM, CREFITO, etc).
        </div>
        <div class="grid-2">
          <div>
            <label for="profNome">Nome completo</label>
            <input id="profNome" type="text" placeholder="Ex.: Dr(a). Orlando Abreu Gomes da Silva" />
          </div>
          <div>
            <label for="profProfissao">Profissão</label>
            <input id="profProfissao" type="text" placeholder="Ex.: Cirurgião-Dentista, Médico, Fisioterapeuta..." />
          </div>
        </div>

        <div class="grid-3" style="margin-top:8px;">
          <div>
            <label for="profEspecialidade">Especialidade</label>
            <input id="profEspecialidade" type="text" placeholder="Ex.: Bucomaxilofacial, Cardiologia..." />
          </div>
          <div>
            <label for="profConselho">Conselho de classe</label>
            <input id="profConselho" type="text" placeholder="Ex.: CRO-PA 5165, CRM-PA 0000..." />
          </div>
          <div>
            <label for="profTelefone">Telefone / WhatsApp</label>
            <input id="profTelefone" type="tel" placeholder="(xx) xxxxx-xxxx" />
          </div>
        </div>

        <div class="grid-2" style="margin-top:8px;">
          <div>
            <label for="profEndereco">Endereço do consultório</label>
            <input id="profEndereco" type="text" placeholder="Rua, número, bairro" />
          </div>
          <div>
            <label for="profCidade">Cidade / UF</label>
            <input id="profCidade" type="text" placeholder="Ex.: Abaetetuba - PA" />
          </div>
        </div>

        <div class="grid-2" style="margin-top:8px;">
          <div>
            <label for="profLogin">Login (identificação interna)</label>
            <input id="profLogin" type="text" placeholder="Crie um login simples (não é online)" />
          </div>
          <div>
            <label for="profSenha">Senha (uso local)</label>
            <input id="profSenha" type="password" placeholder="Senha apenas para controle pessoal" />
          </div>
        </div>

        <div class="btn-row">
          <button class="btn" type="button" onclick="limparCadastro()">Limpar</button>
          <button class="btn btn-primary" type="button" onclick="salvarCadastro()">Salvar cadastro</button>
        </div>
        <div id="statusCadastro" class="status-bar"></div>
      </section>

      <!-- TABS -->
      <div class="secao-titulo-linha" style="margin-top:16px;">
        <h3 style="margin-bottom:0;">Formulários</h3>
        <span class="pill">Escolha a seção e depois gere o PDF da seção atual</span>
      </div>

      <div class="tabs">
        <button class="tab-btn active" data-target="sec-ficha" onclick="trocarSecao('sec-ficha', this)">
          Ficha Clínica
        </button>
        <button class="tab-btn" data-target="sec-receituario" onclick="trocarSecao('sec-receituario', this)">
          Receituário
        </button>
        <button class="tab-btn" data-target="sec-atestado" onclick="trocarSecao('sec-atestado', this)">
          Atestado
        </button>
        <button class="tab-btn" data-target="sec-orcamento" onclick="trocarSecao('sec-orcamento', this)">
          Orçamento
        </button>
      </div>

      <!-- FICHA CLÍNICA -->
      <section id="sec-ficha" class="section active">
        <div class="secao-titulo-linha">
          <h3>Ficha Clínica</h3>
          <span class="pill">Identificação + Anamnese (SOAP livre) + Procedimentos</span>
        </div>

        <div class="grid-2">
          <div>
            <label for="pacNome">Nome do paciente</label>
            <input id="pacNome" type="text" />
          </div>
          <div>
            <label for="pacNascimento">Data de nascimento</label>
            <input id="pacNascimento" type="date" />
          </div>
        </div>

        <div class="grid-2" style="margin-top:8px;">
          <div>
            <label for="pacMae">Nome da mãe</label>
            <input id="pacMae" type="text" />
          </div>
          <div>
            <label for="pacTelefone">Telefone / WhatsApp</label>
            <input id="pacTelefone" type="tel" />
          </div>
        </div>

        <div style="margin-top:8px;">
          <label for="pacEndereco">Endereço</label>
          <input id="pacEndereco" type="text" />
        </div>

        <div style="margin-top:8px;">
          <label for="pacQueixa">Queixa principal</label>
          <textarea id="pacQueixa" placeholder="Relato do paciente sobre o motivo da consulta..."></textarea>
        </div>

        <div style="margin-top:8px;">
          <label for="pacAnamnese">Anamnese / Entrevista completa (modelo SOAP livre)</label>
          <textarea id="pacAnamnese" placeholder="Use SOAP se quiser (S: queixa e história, O: exame físico, A: hipóteses diagnósticas, P: conduta)..."></textarea>
        </div>

        <div style="margin-top:8px;">
          <label for="pacProcedimentos">Procedimentos realizados (Data – Procedimento – Valor)</label>
          <textarea id="pacProcedimentos" placeholder="Ex.: 08/12/2025 – Restauração em resina elemento 37 – R$ 250,00&#10;08/12/2025 – Radiografia periapical – R$ 60,00"></textarea>
        </div>

        <div class="btn-row">
          <button class="btn" type="button" onclick="limparFicha()">Limpar</button>
          <button class="btn" type="button" onclick="salvarFicha()">Salvar ficha</button>
          <button class="btn btn-primary" type="button" onclick="gerarPDF('sec-ficha')">
            Gerar PDF (Ficha Clínica)
          </button>
        </div>
        <div id="statusFicha" class="status-bar"></div>
      </section>

      <!-- RECEITUÁRIO -->
      <section id="sec-receituario" class="section">
        <div class="secao-titulo-linha">
          <h3>Receituário</h3>
          <span class="pill">As medicações abaixo vão sair no PDF normalmente</span>
        </div>

        <div class="info-texto">
          Cabeçalho usa automaticamente os dados do cadastro (nome, profissão, conselho, endereço, telefone).
        </div>

        <div class="grid-2" style="margin-top:8px;">
          <div>
            <label for="recPaciente">Nome do paciente</label>
            <input id="recPaciente" type="text" />
          </div>
          <div>
            <label for="recData">Data</label>
            <input id="recData" type="date" />
          </div>
        </div>

        <div style="margin-top:8px;">
          <label>Inserir rapidamente medicamentos padrão (clique para adicionar no texto)</label>
          <div class="med-buttons">
            <button type="button" class="btn btn-small" onclick="addMedicamento('Paracetamol')">Paracetamol</button>
            <button type="button" class="btn btn-small" onclick="addMedicamento('Dipirona')">Dipirona</button>
            <button type="button" class="btn btn-small" onclick="addMedicamento('Ibuprofeno')">Ibuprofeno</button>
            <button type="button" class="btn btn-small" onclick="addMedicamento('Diclofenaco de sódio')">Diclofenaco de sódio</button>
            <button type="button" class="btn btn-small" onclick="addMedicamento('Dexametasona')">Dexametasona</button>
            <button type="button" class="btn btn-small" onclick="addMedicamento('Amoxicilina')">Amoxicilina</button>
            <button type="button" class="btn btn-small" onclick="addMedicamento('Cefalexina')">Cefalexina</button>
            <button type="button" class="btn btn-small" onclick="addMedicamento('Amoxicilina + Clavulanato (Clavulin)')">Clavulin</button>
          </div>
        </div>

        <div style="margin-top:4px;">
          <label for="recPrescricao">Prescrição (pode escrever qualquer outro medicamento ou posologia)</label>
          <textarea id="recPrescricao" placeholder="Ex.: Paracetamol 750 mg – tomar 1 comprimido de 8/8h por 3 dias..."></textarea>
        </div>

        <div style="margin-top:8px;">
          <label for="recOrientacoes">Orientações adicionais</label>
          <textarea id="recOrientacoes" placeholder="Ex.: Retornar em caso de dor intensa, febre ou sangramento..."></textarea>
        </div>

        <div style="margin-top:8px;">
          <label for="recCidade">Cidade / UF para assinatura</label>
          <input id="recCidade" type="text" placeholder="Ex.: Abaetetuba - PA" />
        </div>

        <div class="btn-row">
          <button class="btn" type="button" onclick="limparReceituario()">Limpar</button>
          <button class="btn" type="button" onclick="salvarReceituario()">Salvar receituário</button>
          <button class="btn btn-primary" type="button" onclick="gerarPDF('sec-receituario')">
            Gerar PDF (Receituário)
          </button>
        </div>
        <div id="statusReceituario" class="status-bar"></div>
      </section>

      <!-- ATESTADO -->
      <section id="sec-atestado" class="section">
        <div class="secao-titulo-linha">
          <h3>Atestado</h3>
          <span class="pill">Completo, usando endereço e dados do cadastro</span>
        </div>

        <div class="grid-2">
          <div>
            <label for="atPaciente">Nome do paciente</label>
            <input id="atPaciente" type="text" />
          </div>
          <div>
            <label for="atDocumento">Documento (RG / CPF / Prontuário)</label>
            <input id="atDocumento" type="text" />
          </div>
        </div>

        <div class="grid-3" style="margin-top:8px;">
          <div>
            <label for="atCID">CID (opcional)</label>
            <input id="atCID" type="text" placeholder="Ex.: K04.0" />
          </div>
          <div>
            <label for="atDias">Dias de afastamento</label>
            <input id="atDias" type="number" min="0" />
          </div>
          <div>
            <label for="atData">Data</label>
            <input id="atData" type="date" />
          </div>
        </div>

        <div style="margin-top:8px;">
          <label for="atCidade">Cidade / UF</label>
          <input id="atCidade" type="text" placeholder="Ex.: Abaetetuba - PA" />
        </div>

        <div style="margin-top:8px;">
          <label for="atObs">Observações (opcional)</label>
          <textarea id="atObs" placeholder="Ex.: Paciente foi submetido a procedimento cirúrgico odontológico, apresentando dor e limitação funcional..."></textarea>
        </div>

        <div class="btn-row">
          <button class="btn" type="button" onclick="limparAtestado()">Limpar</button>
          <button class="btn" type="button" onclick="salvarAtestado()">Salvar atestado</button>
          <button class="btn btn-primary" type="button" onclick="gerarPDF('sec-atestado')">
            Gerar PDF (Atestado)
          </button>
        </div>
        <div id="statusAtestado" class="status-bar"></div>
      </section>

      <!-- ORÇAMENTO -->
      <section id="sec-orcamento" class="section">
        <div class="secao-titulo-linha">
          <h3>Orçamento</h3>
          <span class="pill">Carro-chefe do app – pensado para PDF</span>
        </div>

        <div class="grid-2">
          <div>
            <label for="orcPaciente">Nome do paciente</label>
            <input id="orcPaciente" type="text" />
          </div>
          <div>
            <label for="orcValidade">Validade do orçamento (data ou prazo)</label>
            <input id="orcValidade" type="text" placeholder="Ex.: Válido por 30 dias" />
          </div>
        </div>

        <table class="orc-tabela" id="orcTabela">
          <thead>
            <tr>
              <th>Procedimento / Descrição</th>
              <th style="width:70px;">Qtd.</th>
              <th style="width:110px;">Valor unitário (R$)</th>
              <th style="width:120px;">Subtotal (R$)</th>
            </tr>
          </thead>
          <tbody id="orcCorpo">
            <!-- Linhas de itens aqui -->
          </tbody>
        </table>

        <div class="btn-row" style="justify-content:flex-start; margin-top:8px;">
          <button class="btn btn-small" type="button" onclick="adicionarItemOrcamento()">+ Adicionar item</button>
          <button class="btn btn-small" type="button" onclick="limparItensOrcamento()">Limpar itens</button>
        </div>

        <div class="total-box">
          Total geral: R$ <span id="orcTotal">0,00</span>
        </div>

        <div style="margin-top:8px;">
          <label for="orcObs">Observações / Condições de pagamento</label>
          <textarea id="orcObs" placeholder="Ex.: Pagamento à vista com desconto de 10%, possibilidade de parcelamento em até 3x..."></textarea>
        </div>

        <div class="btn-row">
          <button class="btn" type="button" onclick="limparOrcamento()">Limpar tudo</button>
          <button class="btn" type="button" onclick="salvarOrcamento()">Salvar orçamento</button>
          <button class="btn btn-primary" type="button" onclick="gerarPDF('sec-orcamento')">
            Gerar PDF (Orçamento)
          </button>
        </div>
        <div id="statusOrcamento" class="status-bar"></div>
      </section>
    </div>
  </div>

  <script>
    // --------- UTILIDADES GERAIS ---------
    function mostrarStatus(id, msg) {
      const el = document.getElementById(id);
      if (!el) return;
      el.textContent = msg;
      if (!msg) return;
      setTimeout(() => {
        el.textContent = "";
      }, 2500);
    }

    function trocarSecao(idSecao, botao) {
      document.querySelectorAll(".section").forEach(sec => {
        sec.classList.remove("active");
      });
      document.getElementById(idSecao).classList.add("active");

      document.querySelectorAll(".tab-btn").forEach(btn => {
        btn.classList.remove("active");
      });
      if (botao) botao.classList.add("active");
    }

    // --------- CADASTRO ---------
    function salvarCadastro() {
      const dados = {
        nome: document.getElementById("profNome").value || "",
        profissao: document.getElementById("profProfissao").value || "",
        especialidade: document.getElementById("profEspecialidade").value || "",
        conselho: document.getElementById("profConselho").value || "",
        telefone: document.getElementById("profTelefone").value || "",
        endereco: document.getElementById("profEndereco").value || "",
        cidade: document.getElementById("profCidade").value || "",
        login: document.getElementById("profLogin").value || "",
        senha: document.getElementById("profSenha").value || ""
      };
      localStorage.setItem("btx_profissional", JSON.stringify(dados));
      mostrarStatus("statusCadastro", "Cadastro salvo com sucesso.");
    }

    function carregarCadastro() {
      const salvo = localStorage.getItem("btx_profissional");
      if (!salvo) return;
      try {
        const d = JSON.parse(salvo);
        document.getElementById("profNome").value = d.nome || "";
        document.getElementById("profProfissao").value = d.profissao || "";
        document.getElementById("profEspecialidade").value = d.especialidade || "";
        document.getElementById("profConselho").value = d.conselho || "";
        document.getElementById("profTelefone").value = d.telefone || "";
        document.getElementById("profEndereco").value = d.endereco || "";
        document.getElementById("profCidade").value = d.cidade || "";
        document.getElementById("profLogin").value = d.login || "";
        document.getElementById("profSenha").value = d.senha || "";
      } catch (e) {
        console.error(e);
      }
    }

    function limparCadastro() {
      ["profNome","profProfissao","profEspecialidade","profConselho",
       "profTelefone","profEndereco","profCidade","profLogin","profSenha"
      ].forEach(id => document.getElementById(id).value = "");
      mostrarStatus("statusCadastro", "Cadastro limpo (não esqueça de salvar novamente).");
    }

    // --------- FICHA CLÍNICA ---------
    function salvarFicha() {
      const f = {
        nome: document.getElementById("pacNome").value || "",
        nasc: document.getElementById("pacNascimento").value || "",
        mae: document.getElementById("pacMae").value || "",
        tel: document.getElementById("pacTelefone").value || "",
        end: document.getElementById("pacEndereco").value || "",
        queixa: document.getElementById("pacQueixa").value || "",
        anamnese: document.getElementById("pacAnamnese").value || "",
        procedimentos: document.getElementById("pacProcedimentos").value || ""
      };
      localStorage.setItem("btx_ficha", JSON.stringify(f));
      mostrarStatus("statusFicha", "Ficha clínica salva.");
    }

    function carregarFicha() {
      const salvo = localStorage.getItem("btx_ficha");
      if (!salvo) return;
      try {
        const f = JSON.parse(salvo);
        document.getElementById("pacNome").value = f.nome || "";
        document.getElementById("pacNascimento").value = f.nasc || "";
        document.getElementById("pacMae").value = f.mae || "";
        document.getElementById("pacTelefone").value = f.tel || "";
        document.getElementById("pacEndereco").value = f.end || "";
        document.getElementById("pacQueixa").value = f.queixa || "";
        document.getElementById("pacAnamnese").value = f.anamnese || "";
        document.getElementById("pacProcedimentos").value = f.procedimentos || "";
      } catch (e) {
        console.error(e);
      }
    }

    function limparFicha() {
      ["pacNome","pacNascimento","pacMae","pacTelefone","pacEndereco",
       "pacQueixa","pacAnamnese","pacProcedimentos"
      ].forEach(id => document.getElementById(id).value = "");
      mostrarStatus("statusFicha", "Ficha clínica limpa.");
    }

    // --------- RECEITUÁRIO ---------
    function addMedicamento(txt) {
      const campo = document.getElementById("recPrescricao");
      if (!campo.value) {
        campo.value = txt + " – ";
      } else {
        campo.value += "\n" + txt + " – ";
      }
      campo.focus();
    }

    function salvarReceituario() {
      const r = {
        paciente: document.getElementById("recPaciente").value || "",
        data: document.getElementById("recData").value || "",
        prescricao: document.getElementById("recPrescricao").value || "",
        orientacoes: document.getElementById("recOrientacoes").value || "",
        cidade: document.getElementById("recCidade").value || ""
      };
      localStorage.setItem("btx_receituario", JSON.stringify(r));
      mostrarStatus("statusReceituario", "Receituário salvo.");
    }

    function carregarReceituario() {
      const salvo = localStorage.getItem("btx_receituario");
      if (!salvo) return;
      try {
        const r = JSON.parse(salvo);
        document.getElementById("recPaciente").value = r.paciente || "";
        document.getElementById("recData").value = r.data || "";
        document.getElementById("recPrescricao").value = r.prescricao || "";
        document.getElementById("recOrientacoes").value = r.orientacoes || "";
        document.getElementById("recCidade").value = r.cidade || "";
      } catch (e) {
        console.error(e);
      }
    }

    function limparReceituario() {
      ["recPaciente","recData","recPrescricao","recOrientacoes","recCidade"]
      .forEach(id => document.getElementById(id).value = "");
      mostrarStatus("statusReceituario", "Receituário limpo.");
    }

    // --------- ATESTADO ---------
    function salvarAtestado() {
      const a = {
        paciente: document.getElementById("atPaciente").value || "",
        doc: document.getElementById("atDocumento").value || "",
        cid: document.getElementById("atCID").value || "",
        dias: document.getElementById("atDias").value || "",
        data: document.getElementById("atData").value || "",
        cidade: document.getElementById("atCidade").value || "",
        obs: document.getElementById("atObs").value || ""
      };
      localStorage.setItem("btx_atestado", JSON.stringify(a));
      mostrarStatus("statusAtestado", "Atestado salvo.");
    }

    function carregarAtestado() {
      const salvo = localStorage.getItem("btx_atestado");
      if (!salvo) return;
      try {
        const a = JSON.parse(salvo);
        document.getElementById("atPaciente").value = a.paciente || "";
        document.getElementById("atDocumento").value = a.doc || "";
        document.getElementById("atCID").value = a.cid || "";
        document.getElementById("atDias").value = a.dias || "";
        document.getElementById("atData").value = a.data || "";
        document.getElementById("atCidade").value = a.cidade || "";
        document.getElementById("atObs").value = a.obs || "";
      } catch (e) {
        console.error(e);
      }
    }

    function limparAtestado() {
      ["atPaciente","atDocumento","atCID","atDias","atData","atCidade","atObs"]
      .forEach(id => document.getElementById(id).value = "");
      mostrarStatus("statusAtestado", "Atestado limpo.");
    }

    // --------- ORÇAMENTO ---------
    function adicionarItemOrcamento(item = {}) {
      const corpo = document.getElementById("orcCorpo");
      const tr = document.createElement("tr");
      tr.className = "orc-item-row";

      tr.innerHTML = `
        <td><input type="text" class="orc-desc" placeholder="Procedimento" value="${item.desc || ""}"></td>
        <td><input type="number" class="orc-qtd" min="1" value="${item.qtd || 1}"></td>
        <td><input type="number" class="orc-valor" min="0" step="0.01" value="${item.valor || ""}"></td>
        <td><input type="text" class="orc-subtotal" readonly></td>
      `;

      corpo.appendChild(tr);
      atualizarTotais();
      tr.querySelectorAll(".orc-qtd, .orc-valor").forEach(inp => {
        inp.addEventListener("input", atualizarTotais);
      });
    }

    function atualizarTotais() {
      let total = 0;
      document.querySelectorAll(".orc-item-row").forEach(row => {
        const qtd = parseFloat(row.querySelector(".orc-qtd").value.replace(",", ".")) || 0;
        const valor = parseFloat(row.querySelector(".orc-valor").value.replace(",", ".")) || 0;
        const subtotal = qtd * valor;
        row.querySelector(".orc-subtotal").value = subtotal.toFixed(2).replace(".", ",");
        total += subtotal;
      });
      document.getElementById("orcTotal").textContent = total.toFixed(2).replace(".", ",");
    }

    function salvarOrcamento() {
      const dados = {
        paciente: document.getElementById("orcPaciente").value || "",
        validade: document.getElementById("orcValidade").value || "",
        obs: document.getElementById("orcObs").value || "",
        itens: []
      };

      document.querySelectorAll(".orc-item-row").forEach(row => {
        const desc = row.querySelector(".orc-desc").value || "";
        const qtd = row.querySelector(".orc-qtd").value || "";
        const valor = row.querySelector(".orc-valor").value || "";
        if (desc || valor) {
          dados.itens.push({ desc, qtd, valor });
        }
      });

      localStorage.setItem("btx_orcamento", JSON.stringify(dados));
      mostrarStatus("statusOrcamento", "Orçamento salvo.");
    }

    function carregarOrcamento() {
      const salvo = localStorage.getItem("btx_orcamento");
      if (!salvo) {
        // cria pelo menos uma linha
        adicionarItemOrcamento();
        return;
      }
      try {
        const d = JSON.parse(salvo);
        document.getElementById("orcPaciente").value = d.paciente || "";
        document.getElementById("orcValidade").value = d.validade || "";
        document.getElementById("orcObs").value = d.obs || "";
        document.getElementById("orcCorpo").innerHTML = "";
        if (d.itens && d.itens.length) {
          d.itens.forEach(it => adicionarItemOrcamento(it));
        } else {
          adicionarItemOrcamento();
        }
        atualizarTotais();
      } catch (e) {
        console.error(e);
        adicionarItemOrcamento();
      }
    }

    function limparItensOrcamento() {
      document.getElementById("orcCorpo").innerHTML = "";
      adicionarItemOrcamento();
      atualizarTotais();
    }

    function limparOrcamento() {
      document.getElementById("orcPaciente").value = "";
      document.getElementById("orcValidade").value = "";
      document.getElementById("orcObs").value = "";
      limparItensOrcamento();
      mostrarStatus("statusOrcamento", "Orçamento limpo.");
    }

    // --------- GERAR PDF (USANDO PRINT) ---------
    function gerarPDF(secaoId) {
      const secao = document.getElementById(secaoId);
      if (!secao) return;

      const cadastroSalvo = JSON.parse(localStorage.getItem("btx_profissional") || "{}");

      // Monta cabeçalho com dados do profissional
      const cabecalhoProf = `
        <div style="text-align:center; margin-bottom:16px; font-family:sans-serif;">
          <div style="font-size:18px; font-weight:bold;">${cadastroSalvo.nome || ""}</div>
          <div style="font-size:14px;">${cadastroSalvo.profissao || ""}${cadastroSalvo.especialidade ? " - " + cadastroSalvo.especialidade : ""}</div>
          <div style="font-size:13px;">${cadastroSalvo.conselho || ""}</div>
          <div style="font-size:12px; margin-top:4px;">${cadastroSalvo.endereco || ""}</div>
          <div style="font-size:12px;">${cadastroSalvo.cidade || ""}</div>
          <div style="font-size:12px;">${cadastroSalvo.telefone || ""}</div>
          <hr style="margin-top:12px;">
        </div>
      `;

      const conteudo = `
        <html>
          <head>
            <meta charset="UTF-8">
            <title>PDF</title>
            <style>
              body {
                font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
                margin: 24px;
                font-size: 13px;
              }
              h2, h3 {
                margin: 0 0 8px 0;
              }
              label {
                font-weight: 600;
                font-size: 12px;
              }
              input, textarea {
                width: 100%;
                font-size: 13px;
              }
              table {
                width: 100%;
                border-collapse: collapse;
                margin-top: 8px;
              }
              th, td {
                border: 1px solid #444;
                padding: 4px;
                font-size: 12px;
              }
              .assinatura {
                margin-top: 40px;
                text-align: center;
                font-size: 12px;
              }
              .assinatura hr {
                width: 60%;
              }
            </style>
          </head>
          <body>
            ${cabecalhoProf}
            ${secao.innerHTML}
            <div class="assinatura">
              <hr>
              <div>${cadastroSalvo.nome || ""}</div>
              <div>${cadastroSalvo.profissao || ""}${cadastroSalvo.especialidade ? " - " + cadastroSalvo.especialidade : ""}</div>
              <div>${cadastroSalvo.conselho || ""}</div>
            </div>
          </body>
        </html>
      `;

      const janela = window.open("", "_blank");
      janela.document.open();
      janela.document.write(conteudo);
      janela.document.close();
      janela.focus();
      janela.print(); // Aqui o usuário escolhe "Salvar como PDF"
    }

    // --------- INICIALIZAÇÃO ---------
    window.addEventListener("load", () => {
      carregarCadastro();
      carregarFicha();
      carregarReceituario();
      carregarAtestado();
      carregarOrcamento();
    });
  </script>
</body>
</html>
