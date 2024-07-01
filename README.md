Projeto de Análise de Acidentes de Trânsito
Este projeto utiliza dados de acidentes de trânsito de duas tabelas diferentes (demostrativo_acidentes_afd e demostrativo_acidentes_arb) para realizar análises e criar visualizações de KPIs (Key Performance Indicators) no Power BI.

Estrutura do Projeto

demostrativo_acidentes_afd.csv: Dados de acidentes de trânsito da tabela demostrativo_acidentes_afd.
demostrativo_acidentes_arb.csv: Dados de acidentes de trânsito da tabela demostrativo_acidentes_arb.

SQL Queries: Consultas SQL para extrair e unir dados das duas tabelas.

Power BI Dashboard: Visualizações dos KPIs no Power BI.

KPIs Extraídos:

1- Total de Ocorrências
SELECT 
    'AFD' AS tabela, 
    COUNT(*) AS total_ocorrencias 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    COUNT(*) AS total_ocorrencias 
FROM 
    demostrativo_acidentes_arb;
    
2- Distribuição de Tipos de Acidente
SELECT 
    'AFD' AS tabela, 
    tipo_de_acidente, 
    COUNT(*) AS total
FROM 
    demostrativo_acidentes_afd
GROUP BY 
    tipo_de_acidente
UNION ALL
SELECT 
    'ARB' AS tabela, 
    tipo_de_acidente, 
    COUNT(*) AS total
FROM 
    demostrativo_acidentes_arb
GROUP BY 
    tipo_de_acidente
ORDER BY 
    total DESC;



3- Total de ocorrências mês 
SELECT 
    'AFD' AS tabela, 
    'Ilesos' AS gravidade, 
    SUM(ilesos) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Ilesos' AS gravidade, 
    SUM(ilesos) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Levemente Feridos' AS gravidade, 
    SUM(levemente_feridos) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Levemente Feridos' AS gravidade, 
    SUM(levemente_feridos) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Moderadamente Feridos' AS gravidade, 
    SUM(moderadamente_feridos) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Moderadamente Feridos' AS gravidade, 
    SUM(moderadamente_feridos) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Gravemente Feridos' AS gravidade, 
    SUM(gravemente_feridos) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Gravemente Feridos' AS gravidade, 
    SUM(gravemente_feridos) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Mortos' AS gravidade, 
    SUM(mortos) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Mortos' AS gravidade, 
    SUM(mortos) AS total 
FROM 
    demostrativo_acidentes_arb
ORDER BY 
    total DESC;

4- Total de Veículos Envolvidos por Tipo
SELECT 
    'AFD' AS tabela, 
    'Automovel' AS tipo_veiculo, 
    SUM(automovel) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Automovel' AS tipo_veiculo, 
    SUM(automovel) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Bicicleta' AS tipo_veiculo, 
    SUM(bicicleta) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Bicicleta' AS tipo_veiculo, 
    SUM(bicicleta) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Caminhao' AS tipo_veiculo, 
    SUM(caminhao) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Caminhao' AS tipo_veiculo, 
    SUM(caminhao) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Moto' AS tipo_veiculo, 
    SUM(moto) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Moto' AS tipo_veiculo, 
    SUM(moto) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Onibus' AS tipo_veiculo, 
    SUM(onibus) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Onibus' AS tipo_veiculo, 
    SUM(onibus) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Outros' AS tipo_veiculo, 
    SUM(outros) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Outros' AS tipo_veiculo, 
    SUM(outros) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Tracao Animal' AS tipo_veiculo, 
    SUM(tracao_animal) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Tracao Animal' AS tipo_veiculo, 
    SUM(tracao_animal) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Transporte de Cargas Especiais' AS tipo_veiculo, 
    SUM(transporte_de_cargas_especiais) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Transporte de Cargas Especiais' AS tipo_veiculo, 
    SUM(transporte_de_cargas_especiais) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Trator Maquinas' AS tipo_veiculo, 
    SUM(trator_maquinas) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Trator Maquinas' AS tipo_veiculo, 
    SUM(trator_maquinas) AS total 
FROM 
    demostrativo_acidentes_arb
UNION ALL
SELECT 
    'AFD' AS tabela, 
    'Utilitarios' AS tipo_veiculo, 
    SUM(utilitarios) AS total 
FROM 
    demostrativo_acidentes_afd
UNION ALL
SELECT 
    'ARB' AS tabela, 
    'Utilitarios' AS tipo_veiculo, 
    SUM(utilitarios) AS total 
FROM 
    demostrativo_acidentes_arb
ORDER BY 
    total DESC;

    
5- Total de Feridos por Gravidade
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

6- Índice de Acidentes por Quilômetro
SELECT 
    'AFD' AS tabela, 
    km, 
    COUNT(*) AS total_acidentes 
FROM 
    demostrativo_acidentes_afd 
GROUP BY 
    km 
UNION ALL
SELECT 
    'ARB' AS tabela, 
    km, 
    COUNT(*) AS total_acidentes 
FROM 
    demostrativo_acidentes_arb 
GROUP BY 
    km 
ORDER BY 
    total_acidentes DESC;

7- Acidentes por Horário do Dia
SELECT 
    'AFD' AS tabela, 
    horario, 
    COUNT(*) AS total_acidentes 
FROM 
    demostrativo_acidentes_afd 
GROUP BY 
    horario 
UNION ALL
SELECT 
    'ARB' AS tabela, 
    horario, 
    COUNT(*) AS total_acidentes 
FROM 
    demostrativo_acidentes_arb 
GROUP BY 
    horario 
ORDER BY 
    total_acidentes DESC;



![Design sem nome (4)](https://github.com/ferocfon/ProjetoRodovias1/assets/130929264/165ae34c-7b02-49a8-b28e-ce442210b0c0)





