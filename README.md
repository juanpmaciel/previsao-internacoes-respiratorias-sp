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

## Fontes e documentação
Manuais do SIH no FTP do DATASUS (ftp2.datasus.gov.br, pasta /public/sistemas/dsweb/SIHD/Manuais/):
- Layout_REDUZIDA.pdf: layout do arquivo RD (AIH Reduzida)
- dicionario_de_dados_AIH.pdf: dicionário de dados da AIH (2016)
- Manual Técnico Operacional do SIH (Ministério da Saúde, 2017)

## Decisões sobre os dados
- Excluir AIH de longa permanência (IDENT = 5): a data de internação é a original e o registro cobre só o mês da cobrança.
- Usar UTI_INT_TO (dias de UTI) em vez de UTI_MES_TO (quantidade de atos).
- Caráter da internação (CAR_INT): 01 eletivo, 02 urgência, 03 acidente no local de trabalho, 04 acidente no trajeto para o trabalho, 05 outros acidentes de trânsito, 06 outras lesões e envenenamentos (Manual do SIH, seção 6.2).
- Pendente: unidade da idade (COD_IDADE), sem documentação oficial encontrada até agora.