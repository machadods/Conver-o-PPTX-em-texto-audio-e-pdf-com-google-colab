Análise Didática Automatizada com IA (Colab + Gemini + ChatGPT)

Este repositório contém um notebook completo em Google Colab para:

extrair conteúdo educacional de slides universitários (PPTX, PDF, DOCX);

organizar o texto de forma estruturada;

gerar análises didáticas coerentes, em linguagem acadêmica;

converter automaticamente essas análises em:

áudio narrado (MP3)

PDF formatado para estudo

Tudo isso de forma reprodutível, offline-friendly (após extração) e sem dependência de APIs externas no processamento final.

 Objetivo do Projeto

Transformar materiais didáticos brutos (slides e documentos) em conteúdo estruturado de estudo, adequado para:

revisão acadêmica;

estudo por áudio (aprendizado passivo);

geração de apostilas em PDF;

reaproveitamento em plataformas educacionais (como o IAVocacional).

O foco não é resumo superficial, e sim organização conceitual didática, respeitando a ordem e o conteúdo real apresentado pelo professor.

 Visão Geral do Pipeline

O notebook executa as seguintes etapas:

 Montagem do Google Drive

Permite acesso direto aos materiais originais e gravação automática dos resultados.

 Extração de Texto (PPTX, PDF, DOCX)

Arquivos localizados em pastas por área são processados automaticamente:

PPTX → texto por slide

PDF → texto por página

DOCX → texto por parágrafo

Cada área gera um arquivo consolidado:

OUTPUT_TEXTO/
├── algoritmos_TUDO.txt
├── grafos_TUDO.txt
├── paradigmas_TUDO.txt
├── tipos_estruturas_TUDO.txt
└── ...


Com marcações claras de:

área

arquivo de origem

caminho

slide/página

 Chunking Didático

Os textos consolidados são divididos em blocos semânticos de tamanho controlado, respeitando:

continuidade de assunto;

limite de contexto;

leitura humana e análise por IA.

Isso evita resumos genéricos e perda de informação.

Análise Didática Estruturada (IA)

Cada bloco é analisado seguindo estrutura fixa:

BLOCO: [arquivo / tema]

Conceito central do bloco
Conhecimentos que o aluno precisa dominar
Exemplos (citados e explicados)
Síntese técnica curta


Importante
A análise:

respeita o conteúdo real extraído;

usa conhecimento acadêmico clássico apenas para esclarecer o que está implícito;

não inventa temas que não aparecem no material.

Papel das IAs no Projeto
Gemini (Google)

Utilizado dentro do Colab para:

gerar as análises didáticas textuais;

manter coerência acadêmica;

respeitar a estrutura solicitada;

Funcionou como motor de leitura, interpretação e redação técnica.

ChatGPT (OpenAI)

Atuou como arquitetural e corretivo:

desenho do pipeline;

correção de falhas conceituais;

ajuste de prompts;

definição da lógica de chunking;

estruturação da geração de áudio e PDF;

Responsável por evitar soluções manuais, retrabalho e decisões frágeis.

Resumo honesto:

Gemini escreveu o conteúdo.
ChatGPT garantiu que o sistema funcionasse de ponta a ponta.

Geração Automática de Áudio (MP3)

Após a consolidação das análises em uma variável única (ANALISE_COMPLETA):

o texto completo é convertido em um único áudio narrado;

usando edge-tts com voz neural PT-BR;

ideal para estudo passivo (carro, caminhada, rotina).

Arquivo final:

ANALISE_DIDATICA_COMPLETA.mp3

Geração de PDF Formatado

O mesmo conteúdo textual é transformado em PDF profissional, usando reportlab:

títulos destacados por bloco;

subtítulos claros;

texto fluido e narrável;

margens e tipografia adequadas para leitura longa.

Arquivo final:

analise_completa.pdf

Tecnologias Utilizadas

Google Colab

Python

python-pptx

pdfplumber

python-docx

edge-tts

reportlab

Gemini (Google AI)

ChatGPT (OpenAI)

Resultados Obtidos

Pipeline 100% funcional

Zero retrabalho manual

Conteúdo reaproveitável

Áudio e PDF gerados automaticamente

Notebook pronto para:

GitHub

replicação

extensão futura

Observação Final

Este notebook não é um experimento, é um sistema funcional de produção de conteúdo educacional, criado sob restrição real, com foco em eficiência, clareza e reaproveitamento.

Sem a mente genial e humana trabalhando com persistência nada seria produzivel.

Ele serve como base direta para projetos maiores como:

educação assistida por IA

curadoria automática de conteúdo acadêmico
