# Previsão de internações respiratórias no estado de SP

Projeto de ciência de dados com dados públicos do SUS (SIH/DATASUS) para prever internações por doenças respiratórias e ajudar a antecipar a pressão sobre leitos.

## Status
Em andamento. Semana 1 concluída: ambiente configurado e primeiro download de dados.

## Dados
- Fonte: SIH (Sistema de Informações Hospitalares), grupo RD, via biblioteca PySUS.
- Os dados brutos não ficam neste repositório (pasta data/ ignorada pelo Git).

## Privacidade
Os dados originais têm colunas que podem identificar pessoas (CEP, data de nascimento, número da AIH). O projeto usa só colunas necessárias e resultados agregados, e nenhum dado individual é publicado.

## Como rodar
1. Python 3.12
2. Criar o ambiente virtual: python -m venv .venv
3. Instalar as dependências: pip install -r requirements.txt
4. Abrir notebooks/01_primeiro_download.ipynb

## Estrutura
- notebooks/: análises
- src/: código reutilizável
- app/: painel (futuro)
- data/: dados locais (não versionados)