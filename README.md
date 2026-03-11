# FIAP - Faculdade de Informática e Administração Paulista

<p align="center">
<a href="https://www.fiap.com.br/"><img src="assets/logo-fiap.png" alt="FIAP - Faculdade de Informática e Administração Paulista" border="0" width=40% height=40%></a>
</p>

<br>

# FarmTech na Era da Cloud Computing — Fase 5: Machine Learning na Cabeça

## Grupo 11

## 👨‍🎓 Integrantes:
- **Viviane de Castro** — RM: **567367**
- **Erick Prados Pereira** — RM: **566833**
- **Guilherme Ferreira Santos** — RM: **568523**
- **André Pessoa Gaidzakian** — RM: **567877**

## 👩‍🏫 Professores:
### Tutor(a)
- **Sabrina Otoni**
### Coordenador(a)
- **André Godoi Chiovato**

---

## 📜 Descrição

Nesta fase, atuamos como time de IA da **FarmTech Solutions**, prestando serviço para uma fazenda de médio porte (≈200 hectares) com múltiplas culturas. O objetivo foi **analisar dados climáticos e de solo** e construir soluções de **Machine Learning** para apoiar decisões agrícolas e estimar produtividade, além de planejar a **infraestrutura em nuvem (AWS)** para hospedar uma API que receberia dados de sensores e executaria inferências do modelo.

Na **Entrega 1**, trabalhamos com o dataset `crop_yield.csv`, contendo 4 culturas (Cocoa beans, Oil palm fruit, Rice paddy, Rubber natural) e variáveis ambientais (precipitação, umidade específica, umidade relativa e temperatura), com o alvo `Yield` (rendimento em ton/ha). Realizamos:

1. **Análise exploratória (EDA)** — compreensão da distribuição das variáveis, correlações e comportamento por cultura;
2. **Aprendizado não supervisionado (clusterização)** — K-Means para identificar tendências de produtividade e DBSCAN para detecção de outliers, conforme o Cap 10 (Machine Learning Sem Supervisão);
3. **Cinco modelos de regressão supervisionada** (algoritmos distintos) para prever o rendimento de safra, conforme o Cap 11 (Modelagem de Dados com Regressão Supervisionada), com avaliação via MAE, RMSE e R².

Na **Entrega 2**, estimamos custos **On-Demand (100%)** na AWS para uma máquina Linux simples (2 vCPU, 1 GiB RAM, até 5 Gbps de rede e 50 GB de armazenamento), comparando as regiões **São Paulo (sa-east-1)** e **Virgínia do Norte (us-east-1)** usando a AWS Pricing Calculator. Justificamos tecnicamente a escolha final considerando restrições legais (LGPD) e latência de acesso.

Todo o passo a passo técnico (código + relatório) está no **Notebook Jupyter**. Este README atua como **guia de navegação** para o repositório e documenta a parte de **Cloud Computing**.

---

## 📁 Estrutura de pastas

```text
.
├── .github/               # Configurações específicas do GitHub
├── assets/                # Imagens e artefatos não estruturados
│   ├── logo-fiap.png
│   └── aws-calculator/    # Prints da calculadora AWS (.pdf)
├── config/                # Arquivos de configuração (se necessário)
├── document/              # Documentos do projeto (se necessário)
├── scripts/
│   └── requirements.txt   # Dependências Python
├── src/
│   └── notebooks/
│       ├── AndrePGaidzakian_rm567877_pbl_fase4.ipynb
│       ├── ErickPPereira_rm566833_pbl_fase4.ipynb
│       ├── GuilhermeFSantos_rm568523_pbl_fase4.ipynb
│       └── VivianeDCastro_rm567367_pbl_fase4.ipynb
├── crop_yield.csv         # Dataset fornecido
└── README.md              # Este arquivo
```

- **Github:** **(https://github.com/DeepThinker-s/Fase5-Cap1-FarmTech-na-Era-da-Cloud-Computing)**

---

## 📊 Entrega 1 — Machine Learning (Notebook Jupyter)

### Notebooks
Os notebooks contêm execuções idênticas do projeto para compor a nota individual de cada integrante do grupo:
- **Arquivos:**
  - [`src/notebooks/AndrePGaidzakian_rm567877_pbl_fase4.ipynb`](src/notebooks/AndrePGaidzakian_rm567877_pbl_fase4.ipynb)
  - [`src/notebooks/ErickPPereira_rm566833_pbl_fase4.ipynb`](src/notebooks/ErickPPereira_rm566833_pbl_fase4.ipynb)
  - [`src/notebooks/GuilhermeFSantos_rm568523_pbl_fase4.ipynb`](src/notebooks/GuilhermeFSantos_rm568523_pbl_fase4.ipynb)
  - [`src/notebooks/VivianeDCastro_rm567367_pbl_fase4.ipynb`](src/notebooks/VivianeDCastro_rm567367_pbl_fase4.ipynb)
- **Conteúdo:**
  - Células de código executadas, com código Python otimizado e comentado
  - Células Markdown com relatório: EDA, achados, conclusões e limitações
  - Clusterização (K-Means + DBSCAN) para tendências e outliers
  - 5 modelos preditivos de regressão com métricas (MAE, RMSE, R²)

### 🎥 Vídeo (Entrega 1)
- **YouTube (não listado):** **(https://youtu.be/8M6ju4jYRBc)**

---

## ☁️ Entrega 2 — Computação em Nuvem (AWS Pricing Calculator)

### 1) Estimativa de Custos (On-Demand – 100%)

**Requisitos da máquina (conforme enunciado):**
- Linux
- 2 vCPU
- 1 GiB RAM
- Até 5 Gbps de rede
- 50 GB de armazenamento (HD)

**Serviço utilizado:** Amazon EC2 (On-Demand, Linux) + EBS gp3 50 GB

**Instância de referência:** `t3.micro` (2 vCPU, 1 GiB RAM, até 5 Gbps rede)

#### Comparação de Custos

| Região | Instância | EC2/mês (USD) | EBS 50GB/mês (USD) | **Total Mensal (USD)** | **Total Anual (USD)** |
|--------|-----------|---------------|---------------------|------------------------|-----------------------|
| **São Paulo (sa-east-1)** | t3.micro | ~$15.06 | ~$4.80 | **~$19.86** | **~$238.32** |
| **Virgínia do Norte (us-east-1)** | t3.micro | ~$7.59 | ~$4.00 | **~$11.59** | **~$139.08** |

> **Nota:** Valores estimados com base nos preços públicos da AWS (fev/2026). Confirmar com a calculadora AWS para valores exatos e atualizados.
>
> **Prints obrigatórios** (salvos em `assets/aws-calculator/`):
> - `aws_calc_sp.pdf` — Print da simulação São Paulo
> - `aws_calc_virginia.pdf` — Print da simulação Virgínia do Norte

---

### 2) Escolha Final — Considerando Restrições Legais e Acesso Rápido

**Pergunta do enunciado:** *"Suponha que você precisa acessar rapidamente os dados dos sensores e que há restrições legais para armazenamento no exterior. Qual opção você escolheria? Justifique."*

**Resposta:**

Mesmo que **us-east-1 (Virgínia do Norte)** apresente menor custo (~$11.59/mês vs ~$19.86/mês), a opção recomendada é **São Paulo (sa-east-1)**, pelos seguintes motivos:

1. **Conformidade legal (LGPD):** A Lei Geral de Proteção de Dados (Lei 13.709/2018) e possíveis restrições contratuais/regulatórias exigem que dados de sensores agrícolas coletados no Brasil sejam armazenados e processados em território nacional. Manter o workload em `sa-east-1` atende essa exigência de conformidade.

2. **Latência e acesso rápido:** A API que receberá dados dos sensores da fazenda (localizada no Brasil) terá latência significativamente menor ao usar a região de São Paulo (~5–15ms) versus Virgínia do Norte (~120–180ms). Isso é crítico para ingestão em tempo real e inferência frequente do modelo de ML.

3. **Redução de risco operacional:** Evita riscos de não conformidade, retrabalho jurídico, auditorias e necessidade de migração futura. O custo adicional (~$8.27/mês) é amplamente justificado pela segurança jurídica e operacional.

✅ **Escolha final: São Paulo (sa-east-1)**

### 🎥 Vídeo (Entrega 2)
- **YouTube (não listado):** **[PREENCHER_LINK_VIDEO_ENTREGA_2]**
> Duração máxima: 5 minutos. Mostra a AWS Pricing Calculator e a comparação SP vs Virgínia.

---

## 🔧 Como executar o código

### Pré-requisitos
- Python **3.10+**
- Jupyter Notebook / JupyterLab (ou Google Colab)

### Execução local

1. **Clone o repositório:**
   ```bash
   git clone https://github.com/DeepThinker-s/Fase5-Cap1-FarmTech-na-Era-da-Cloud-Computing.git
   cd Fase-5-Cap-1-FarmTech
   ```

2. **Crie e ative um ambiente virtual:**
   
   Windows (PowerShell):
   ```powershell
   python -m venv .venv
   .venv\Scripts\Activate.ps1
   ```
   
   macOS/Linux:
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   ```

3. **Instale as dependências:**
   ```bash
   pip install -U pip
   pip install -r scripts/requirements.txt
   ```

4. **Inicie o Jupyter:**
   ```bash
   jupyter notebook
   ```

5. **Abra e execute o notebook:**
   - `src/notebooks/GuilhermeFSantos_rm568523_pbl_fase4.ipynb`

---

## 🗃 Histórico de lançamentos

* **0.2.0 — 22/02/2026**
    * Entrega 1: Notebook com EDA + Clusterização + 5 modelos de regressão supervisionada
    * Entrega 2: Comparação AWS Calculator (SP vs Virgínia) + justificativa técnica
* **0.1.0 — 22/02/2026**
    * Estrutura inicial do repositório seguindo template FIAP

---

## 📋 Licença

<img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/cc.svg?ref=chooser-v1"><img style="height:22px!important;margin-left:3px;vertical-align:text-bottom;" src="https://mirrors.creativecommons.org/presskit/icons/by.svg?ref=chooser-v1"><p xmlns:cc="http://creativecommons.org/ns#" xmlns:dct="http://purl.org/dc/terms/"><a property="dct:title" rel="cc:attributionURL" href="https://github.com/agodoi/template">MODELO GIT FIAP</a> por <a rel="cc:attributionURL dct:creator" property="cc:attributionName" href="https://fiap.com.br">Fiap</a> está licenciado sobre <a href="http://creativecommons.org/licenses/by/4.0/?ref=chooser-v1" target="_blank" rel="license noopener noreferrer" style="display:inline-block;">Attribution 4.0 International</a>.</p>
