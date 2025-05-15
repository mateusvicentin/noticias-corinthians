<h1 align="center">📰 Monitoramento Automatizado de Notícias com Python, Airflow, MongoDB, Streamlit e Telegram</h1>
<p align="center">
  <img src="https://img.shields.io/badge/python-3.10-blue" />
  <img src="https://img.shields.io/badge/airflow-%23017CEE" />
  <img src="https://img.shields.io/badge/mongodb-%2347A248" />
  <img src="https://img.shields.io/badge/streamlit-%23FF4B4B" />
  <img src="https://img.shields.io/badge/telegram-%2326A5E4" />
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/986020af-419b-476a-a6c7-5552bc694980" alt="logo" />
</p>

<p>
  Este projeto nasceu com uma missão clara: criar uma solução de monitoramento automatizado de notícias com foco no Corinthians.
  A proposta é simples e poderosa: coletar notícias em tempo real, processar o conteúdo com inteligência artificial, armazenar tudo em um banco de dados flexível, visualizar em um dashboard interativo e enviar alertas instantâneos para o Telegram.
</p>

<p>
  Trata-se de um pipeline completo de engenharia de dados, com orquestração via Apache Airflow, scraping com newspaper3k,
  NLP com spaCy, armazenamento em MongoDB e visualização com Streamlit. A entrega final é uma experiência de monitoramento contínua e em tempo real,
  ideal para jornalistas, clubes, analistas esportivos ou qualquer pessoa interessada em acompanhar tópicos específicos com profundidade e agilidade.
</p>

<h2>📌 Visão Geral</h2>
<p>
  No centro da arquitetura está uma DAG no Apache Airflow que executa rotinas periódicas:
</p>
<ul>
  <li>1️⃣ Realiza o scraping de sites pré-definidos que publicam notícias do Corinthians.</li>
  <li>2️⃣ Processa os textos extraídos com <strong>análise de entidades nomeadas (NER)</strong>, identificando nomes de jogadores, técnicos, clubes, estádios e organizações.</li>
  <li>3️⃣ Armazena os dados no MongoDB, incluindo título, conteúdo, data, imagem, fonte e entidades extraídas.</li>
  <li>4️⃣ Dispara alertas automáticos no Telegram com resumo, imagem e link direto para leitura.</li>
</ul>

<p>
  O usuário pode então visualizar tudo isso em um dashboard responsivo construído com Streamlit.
  A interface permite aplicar filtros por veículo de notícia e por período, visualizar entidades mais citadas,
  acompanhar a evolução de publicações ao longo dos dias e consultar a notícia completa com imagem e texto.
</p>

<h2>🧠 Stack de Tecnologias</h2>
<ul>
  <li><strong>Python:</strong> A linguagem central utilizada em toda a aplicação — do scraping à visualização.</li>
  <li><strong>Apache Airflow:</strong> Faz a orquestração da pipeline de dados com tarefas programadas e monitoráveis.</li>
  <li><strong>MongoDB:</strong> Banco NoSQL utilizado para armazenar as notícias e metadados de forma flexível.</li>
  <li><strong>newspaper3k:</strong> Biblioteca de scraping de artigos, que extrai título, texto, imagens e metadados automaticamente.</li>
  <li><strong>spaCy:</strong> Motor de NLP usado para análise textual e extração de entidades (NER) em português.</li>
  <li><strong>Telegram Bot API:</strong> Envia mensagens para um grupo ou canal com título, imagem, link e resumo das notícias.</li>
  <li><strong>Streamlit:</strong> Plataforma web leve e intuitiva para exibição das notícias de forma interativa e responsiva.</li>
  <li><strong>Docker + Docker Compose:</strong> Containeriza todo o projeto, facilitando o deploy local e em nuvem.</li>
</ul>

<h2>📂 Estrutura do Projeto</h2>
<pre><code>.
├── dags/
│   └── noticias_corinthians_dag.py        # DAG com scraping, NLP e alertas
├── dashboard/
│   └── streamlit_app.py                   # Interface interativa com filtro e cards
├── telegram_sender.py                     # Envio de mensagens ricas no Telegram
├── data_ingestion/
│   └── coletar_noticias.py                # Lógica de scraping
├── data_processing/
│   └── analisar_texto.py                  # NLP e extração de entidades
├── database/
│   └── mongodb_connector.py               # Conexão reutilizável com MongoDB
├── config_secrets.py                      # Tokens e variáveis sensíveis
├── docker-compose.yml                     # Infraestrutura local do projeto
├── Dockerfile                             # Ambiente de execução
└── requirements.txt                       # Dependências Python
</code></pre>

<h2>📊 O que o Projeto Faz</h2>
<ul>
  <li>⏱️ Executa coletas periódicas automaticamente com agendamento via Airflow.</li>
  <li>🔍 Realiza scraping de vários portais esportivos confiáveis (Globo Esporte, Meu Timão, etc.).</li>
  <li>🧠 Aplica NLP com spaCy para extrair e classificar entidades em pessoas, locais e organizações.</li>
  <li>💾 Salva notícias completas e enriquecidas no MongoDB com controle contra duplicações.</li>
  <li>📤 Envia notificações informativas e formatadas para um grupo Telegram em tempo real.</li>
  <li>📈 Oferece uma interface web para explorar dados, filtrar por data/fonte e acessar cada notícia em detalhe.</li>
</ul>

<h2>🎨 Preview do Dashboard</h2>
<p align="center">
  <img src="https://github.com/user-attachments/assets/f4d4a5f3-69f7-4d2a-8d0f-a268e1d7a6d0" alt="resumo" />
  <img src="https://github.com/user-attachments/assets/9a840145-0ee5-4dbb-8c3e-09fe1a37d05e" alt="entidades" />
  <img src="https://github.com/user-attachments/assets/5b7a4a34-a956-4e65-938f-e60aff3a30ea" alt="noticia1" />
  <img src="https://github.com/user-attachments/assets/6bdc34c8-3b81-4614-9f08-efe0d9b379e1" alt="noticia2" />
</p>

<h2>🔔 Preview do Telegram </h2>
<img src="https://github.com/user-attachments/assets/1f49afca-b3a5-4c65-8b33-e837b311043c" alt="telegram1" />
<img src="https://github.com/user-attachments/assets/eef1676b-8445-4579-92fe-665eb3dbba0a" alt="telegram2" />
