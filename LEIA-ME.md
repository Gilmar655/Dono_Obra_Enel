# Dono da Obra — publicação e uso

Site pronto para GitHub Pages, com dados do arquivo Dono_Obra_Site_21_09-_2026.xlsx. Nenhuma instalação ou compilação é necessária. Os arquivos JavaScript necessários estão no pacote; o site também funciona abrindo index.html no computador.

## Publicar no GitHub Pages

1. Extraia este ZIP em uma pasta do computador.
2. Crie ou abra o repositório que deseja usar no GitHub.
3. Use **Add file → Upload files** e envie o conteúdo extraído. O arquivo **index.html deve ficar na raiz do repositório**, ao lado de app.js, styles.css, data.js, Base_Original.xlsx e da pasta vendor. Envie também o arquivo .nojekyll incluído no ZIP.
4. Salve os arquivos em **Commit changes**.
5. Abra **Settings → Pages**. Em **Source**, selecione **Deploy from a branch**; escolha **main** e **/(root)** e clique em **Save**.
6. Aguarde a publicação e copie o endereço exibido pelo GitHub Pages para compartilhar a consulta.

Este pacote não foi publicado automaticamente em nenhum repositório. O link de consulta passa a existir após a publicação. Este site não possui login: os dados publicados ficam disponíveis publicamente, inclusive para baixar.

Referência oficial: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Consultar

- **Visão geral:** indicadores, distribuição por polo, empreiteira, família e programação mensal. Os gráficos de barras permitem aplicar filtros por clique.
- **Base de projetos:** todos os 17 campos, pesquisa, ordenação, paginação e detalhes por projeto.
- **Técnicos:** quantidade, UPS, programação e DELI vencido por responsável, incluindo os não definidos.
- **Conferência:** qualidade da seleção e achados da conferência das seis abas originais. Os achados do arquivo original são fixos e identificados como análise da base completa; os indicadores de qualidade respondem aos filtros.
- **Abas do Excel:** conteúdo de todas as abas, com linhas numeradas e fórmulas em dicas ao passar o cursor. São os valores armazenados no arquivo, sem execução das fórmulas. Formatação e gráficos originais ficam disponíveis no Excel original.
- **Relógio:** atualizado a cada segundo, no fuso de Brasília, usando o relógio do dispositivo. A data de referência dos prazos é independente do relógio e começa em 21/09/2026.

## Importar Excel ou CSV

Clique em **Importar base** e selecione .xlsx, .xls ou .csv, até 25 MB. O arquivo deve conter os mesmos 17 cabeçalhos da base original, em qualquer ordem. No Excel, a aba Base Projetos tem preferência. O cabeçalho pode estar nas primeiras 30 linhas.

Cabeçalhos: definicao_do_projeto; nota; Stt Proj; KPI Nota; Família; Polo; Empreiteira_Contratos; qtdPlanUPS; Circuito; Area; camada; Aging; Prazo DELI; SttProg; PrimDataProg; Dono; CÓDTEC.

Datas textuais são aceitas como dd/mm/aaaa ou aaaa-mm-dd; datas nativas do Excel também são reconhecidas. Para UPS, são aceitos números nativos, ponto decimal (1234.567) ou padrão brasileiro com vírgula decimal (1.234,567). Valores ausentes permanecem ausentes. Nenhuma linha é excluída como duplicada. Projeto vazio, data inválida ou UPS não numérica cancela a importação e mantém a base anterior.

CSV exportado pelo painel usa UTF-8 com BOM e separador ponto e vírgula. Ao importar, o site reconhece UTF-8 e tenta Windows-1252 se necessário. O CSV representa uma única tabela; use Excel para transportar várias abas. Textos iniciados por caracteres de fórmula recebem apóstrofo no CSV para abertura segura no Excel.

**A importação vale apenas para a sessão atual e não modifica o site compartilhado.** Para atualizar a base que todos consultam:

1. Importe e confira a nova base.
2. Abra **Mais opções → Baixar dados para publicar**.
3. Substitua **data.js** na raiz do repositório por esse arquivo e salve em Commit changes.
4. Aguarde a atualização do GitHub Pages e atualize a página.

O botão de Excel original sempre baixa o arquivo de 21/09/2026 incluído neste pacote. A nova importação não substitui esse arquivo automaticamente. As abas da base importada são incorporadas ao novo data.js.

## Exportar

- **Excel:** exporta todos os registros filtrados, em todas as páginas, com os 17 campos originais e uma aba de critérios. Datas são células de data e UPS são números.
- **CSV:** exporta a mesma seleção completa de registros.
- **Mais opções → Exportar todas as abas:** exporta os valores armazenados das abas da base carregada; não conserva fórmulas, gráficos, tabelas dinâmicas ou a formatação original.
- **Mais opções → Baixar Excel original:** baixa uma cópia idêntica do arquivo fornecido, com sua estrutura original.

## Critérios da análise

DELI vencido significa data anterior à referência. DELI em até 15 dias inclui a referência e a data +15 dias. Uma programação passada não comprova atraso de execução, e programação informada não comprova conclusão. O KPI Concluído_Elétricamente é mantido e pode ser filtrado, mas não foi convertido em encerramento integral do projeto. O relatório CONFERENCIA.md documenta os resultados e limites da conferência.

## Arquivos

index.html (página), styles.css (aparência), app.js (funcionalidades), data.js (base e abas), Base_Original.xlsx (arquivo original), .nojekyll (publicação estática), vendor/xlsx.full.min.js e vendor/LICENSE-SheetJS.txt (SheetJS 0.20.3 e licença), CONFERENCIA.md e LEIA-ME.md (documentação).

Documentação SheetJS: https://docs.sheetjs.com/docs/


## Atualização de 22/09/2026 — lista visível

A lista de obras fica logo abaixo dos filtros, em formato de planilha, em todas as seções. As 17 colunas são preservadas, com cabeçalho fixo, rolagem horizontal e vertical, ordenação e opção de mostrar todas as obras filtradas. Os botões Excel da seleção e CSV da seleção exportam todos os resultados filtrados, independentemente da página exibida. A dependência xlsx.full.min.js é carregada da raiz do repositório.
