Projeto de Análise de Acidentes de Trânsito
Este projeto utiliza dados de acidentes de trânsito de duas tabelas diferentes (demostrativo_acidentes_afd e demostrativo_acidentes_arb) para realizar análises e criar visualizações de KPIs (Key Performance Indicators) no Power BI.

Estrutura do Projeto

demostrativo_acidentes_afd.csv: Dados de acidentes de trânsito da tabela demostrativo_acidentes_afd.
demostrativo_acidentes_arb.csv: Dados de acidentes de trânsito da tabela demostrativo_acidentes_arb.

SQL Queries: Consultas SQL para extrair e unir dados das duas tabelas.

Power BI Dashboard: Visualizações dos KPIs no Power BI.

KPIs Extraídos:
1- Total de Ocorrências
2- Distribuição de Tipos de Acidente
3- Total de ocorrências mês 
4- Total de Veículos Envolvidos por Tipo
5- Total de Feridos por Gravidade
6- Índice de Acidentes por Quilômetro
7- Acidentes por Horário do Dia

Total de Acidentes por Gravidade Ano a Ano (considerando ambas as tabelas)
SELECT 
    YEAR(STR_TO_DATE(data, '%d/%m/%Y')) AS ano,
    'afd' AS tabela,
    SUM(ilesos) AS total_ilesos,
    SUM(levemente_feridos) AS total_levemente_feridos,
    SUM(moderadamente_feridos) AS total_moderadamente_feridos,
    SUM(gravemente_feridos) AS total_gravemente_feridos,
    SUM(mortos) AS total_mortos
FROM 
    demostrativo_acidentes_afd
GROUP BY 
    YEAR(STR_TO_DATE(data, '%d/%m/%Y'))
UNION ALL
SELECT 
    YEAR(STR_TO_DATE(data, '%d/%m/%Y')) AS ano,
    'arb' AS tabela,
    SUM(ilesos) AS total_ilesos,
    SUM(levemente_feridos) AS total_levemente_feridos,
    SUM(moderadamente_feridos) AS total_moderadamente_feridos,
    SUM(gravemente_feridos) AS total_gravemente_feridos,
    SUM(mortos) AS total_mortos
FROM 
    demostrativo_acidentes_arb
GROUP BY 
    YEAR(STR_TO_DATE(data, '%d/%m/%Y'))
ORDER BY 
    ano, tabela;
