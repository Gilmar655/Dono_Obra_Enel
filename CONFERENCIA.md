# Conferência — Dono da Obra

Arquivo: Dono_Obra_Site_21_09-_2026.xlsx. Referência: 21/09/2026.

A conferência abrange as seis abas e compara seus valores salvos à Base Projetos. Não inclui validação de campo, consulta ao SIGEO ou comprovação de encerramento. O arquivo original foi preservado integralmente.

## Indicadores recalculados

| Indicador | Resultado |
|---|---:|
| Registros | 4880 |
| Projetos únicos | 4880 |
| Notas únicas não vazias | 2574 |
| UPS planejadas | 890892.593 |
| Com data de programação | 334 |
| Sem Prazo DELI | 4130 |
| DELI anterior à referência | 352 |
| DELI de 21/09 a 06/10/2026, inclusive | 51 |
| Programação anterior à referência | 189 |
| Programação de 21/09 a 06/10/2026, inclusive | 112 |
| Dono ausente ou A Definir | 4376 |
| Camada não definida | 3557 |
| Código técnico - | 4403 |
| Duplicidades: projeto + nota + circuito | 0 |
| Aging divergente na condição de vencimento | 182 |

## Revisão por aba

### Capa — Cobertura do arquivo

**Observação.** O total de 4.880 registros confere. O índice da capa não lista a aba Análise Técnicos, que está presente e foi incluída no site.

### Relatório Gerencial — Campos vazios subcontados nas distribuições

**Divergência.** A89:C89 contabiliza a palavra “Ausente”, não células vazias: empreiteiras ausentes = 4, e não 0. A110:C110 tem a mesma condição para Dono: 1, e não 0. Os indicadores de campos incompletos B29 e B31 estão corretos.

### Dashboard — Indicadores de prazo usam critérios diferentes

**Critério.** A9/C9 usam PrimDataProg e TODAY(): valores salvos 189/112. Recalculados em 21/09/2026: 189/112. O Relatório Gerencial usa Prazo DELI e referência fixa: 352/51. O site separa programação passada de DELI vencido.

### Análise Técnicos — Totais de responsáveis e códigos reconciliados

**Conferido.** Tabela dinâmica: 4.880 registros e 890.892,593 UPS. São 504 registros com dono definido; 477 com código técnico definido. Há 27 registros com dono definido e código “-”.

### Análises — Distribuições com categorias ausentes

**Divergência.** As linhas rotuladas “Ausente” procuram texto literal em vez de vazio. Categorias vazias devem compor os totais. No site elas são agrupadas como “Não informado”.

### Base Projetos — Projetos e programação

**Conferido.** 4880 projetos únicos; 0 duplicidades pela chave projeto + nota + circuito; 0 divergências entre SttProg e presença de PrimDataProg. Notas repetidas não foram excluídas: uma nota pode estar vinculada a vários projetos.

### Base Projetos — Aging exige atualização

**Revisar.** Aging registra 234 linhas como Vencida; há 352 DELI anteriores à referência. 182 linhas divergem na classificação vencida/não vencida. O site calcula os prazos diretamente pelas datas.

### Relatório Gerencial — Período de programação incorreto no texto

**Divergência.** A célula A2 informa programação até 09/06/2028. As 334 datas da base vão de 10/01/2026 a 18/10/2026; não há programação em 2028. O período do painel é calculado diretamente pela base. Datas foram preservadas, sem tentar inverter dia e mês.

### Base Projetos — Conclusão elétrica e prazo

**Revisar.** Existem 76 registros com KPI Nota Concluído_Elétricamente, sendo 59 com DELI anterior à referência. Esse KPI não comprova encerramento integral do projeto; os vencidos incluem esses registros. Use o filtro KPI da nota para separá-los.

### Todas as abas — Fórmulas e reconciliação

**Conferido.** 1956 fórmulas inspecionadas; 1624 fórmulas simples COUNTIF/SUMIF conferidas contra a base: 0 divergências de resultado armazenado. 0 células com erro Excel. Esta verificação não equivale a recalcular todas as fórmulas no Excel.

## Rastreabilidade e limites

- Base Projetos: cabeçalhos na linha 2; 4.880 registros nas linhas 3 a 4.882; 17 campos com dados. A coluna 18 está vazia.
- Análises: E28:G28 subconta empreiteira vazia (esperado: 4); A80:C80 subconta dono vazio (esperado: 1). As fórmulas retornam corretamente para o texto literal, mas esse critério não representa células ausentes.
- Relatório Gerencial: B89 = 0, correto para o texto Ausente, mas há 4 empreiteiras em branco; B110 = 0, mas há 1 dono em branco.
- Notas únicas = 2.574, excluindo a nota vazia. Repetição de nota em projetos distintos não foi classificada como duplicidade.
- Totais por polo: Leste 2.634; Norte 2.148; Sul 87; Oeste 11. Total: 4.880.
- 334/4.880 = 6,8443% dos registros têm programação; 4.546 estão sem data.
- UPS zeradas: 63; UPS negativas: 0. Zeradas requerem interpretação operacional, não foram tratadas automaticamente como erro.
- Sem recálculo completo no Excel: 1.956 fórmulas inspecionadas, 1.624 COUNTIF/SUMIF simples reconciliadas por código com a base. Fórmulas matriciais, datas e proporções tiveram seus principais indicadores confrontados, sem executar um motor Excel. Nenhum erro de célula Excel foi encontrado.
- Dados de prazo e Aging foram sinalizados, sem inverter datas ou substituir classificações da origem.
- Mudanças de referência e filtros recalculam os indicadores do painel, mas não reescrevem as abas históricas nem os achados desta conferência.

## Recomendações

1. Corrigir o texto do período no Relatório Gerencial A2 para 10/01/2026 a 18/10/2026.
2. Ajustar as fórmulas das categorias Ausente para contar células vazias e somar suas UPS.
3. Uniformizar a data de referência e nomear explicitamente o campo usado: Prazo DELI ou PrimDataProg.
4. Conferir os 182 registros de Aging divergente; o filtro de prazos utiliza as datas originais.
5. Separar, pela seleção de KPI da nota, os 76 registros Concluído_Elétricamente quando a análise pedir essa distinção. Não inferir conclusão integral.
6. Priorizar o preenchimento de programação, dono, código técnico e camada, sem excluir registros incompletos.

## Validação do site

Testes locais aprovaram filtros, leitura das seis abas, importação do arquivo original, rejeição de estrutura inválida com manutenção da base anterior e exportação/reimportação em Excel e CSV. O Excel exportado foi comparado independentemente célula a célula à base: 4.880 registros, 17 campos e nenhuma diferença. A validação visual e dos cliques em navegador foi bloqueada pela política do ambiente e não foi concluída.
