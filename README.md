# Vigilantes da Luz — monitoramento de interrupções no RJ

Mapa interativo dos locais que ficaram sem luz após o temporal de 7 de novembro de 2026, em todo o estado do Rio de Janeiro. Base de pontos revisada em 19/11/2026; triagem de pistas e monitoramento atualizados em 22/11/2026.


## Verificação complementar — 22/11/2026 (09h12 BRT)

**Resultado:** nenhum novo ponto confirmado e nenhuma nova pista coletiva com endereço/quarteirão identificável desde a atualização das 08h14. O Top 20 e a camada cartográfica permanecem inalterados.

- **Nova pista individual — Light, município do Rio de Janeiro:** reclamação publicada em 21/11 às 18h33 relata cerca de três dias sem energia na residência do consumidor e aproximadamente dez contatos com a concessionária. Não informa bairro, rua, vizinhos atingidos ou coordenadas. Foi acrescentada a `dados/pistas_nao_verificadas.csv` exclusivamente para auditoria; não é ocorrência coletiva comprovada e não deve ser mapeada.
- **Triagem negativa — Enel, município do Rio de Janeiro:** reclamação publicada em 22/11 às 00h46 contém apenas manifestação genérica de insatisfação e a frase “ficar sem luz”, sem descrever episódio, data de início, duração, bairro, rua ou extensão. Não foi adicionada à base para evitar transformar desabafo sem ocorrência identificável em evidência.
- **Pistas anteriores verificadas contra duplicidade:** a reclamação da Light sobre baixa tensão em vários imóveis de uma rua (publicada em 21/11 às 22h19), a reclamação sobre vizinhos com apenas uma fase desde 11/11 (21/11 às 16h12), o relato de oscilações com quatro solicitações (21/11 às 23h05), o caso da Tijuca/Rua Araújo Pena, nº 83, e a pista rural de Valença já constam da triagem de 08h14. Não foram duplicados.
- **Sinal operacional:** a página estadual do Powercut continua exibindo o retrato de **21/11 às 08h20: 173 faltas e 3.049 clientes**, portanto está defasada para esta verificação. A base do projeto já guarda o snapshot separado do feed `br-enel-rj` de **22/11 às 08h10:13 BRT, 127 ocorrências**, que é contagem de eventos do feed, não de clientes. Não foi possível obter um novo retrato verificável às 09h12; não apresentamos esses números como situação atual.
- **Fontes primárias:** o mapa da Enel abriu, mas permaneceu em “Buscando áreas de falta de energia”, sem tabela preenchida na extração textual; a própria página alerta que pode incluir interrupções momentâneas inferiores a três minutos. O mapa da Light abriu sem conteúdo textual legível. Não foi encontrada nesta rodada nova publicação oficial de prefeitura, Defesa Civil, Procon ou ANEEL com endereço e coordenadas de quarteirão.
- **Deduplicação da base principal:** `dados/pontos.csv` permanece com 120 registros e `dados/pontos.geojson` com 120 feições. A auditoria existente indica 24 registros com precisão declarada como rua, 15 como ponto e 81 como bairro; as 96 posições marcadas como conferidas não significam 96 endereços de quarteirão. Nenhuma coordenada, foto, fluxo ou recorrência foi inventada.
- **Arquivos:** `dados/pistas_nao_verificadas.csv` recebeu uma linha individual, explicitamente fora do mapa. `dados/pontos.csv`, `dados/pontos.geojson`, `dados/resumo_por_municipio.csv` e `index.html` foram preservados. Raio de 2 km e Top 20 não recalculados. **PDF não regenerado**, pois nenhum ponto definitivo novo foi aprovado.

Fontes: [reclamação Light — três dias sem energia em residência](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/estou-ha-3-dias-sem-luz-e-a-light-nao-resolve-meu-problema_lq5NVyyWpmGbOKu0/); [reclamação Enel — manifestação genérica de 22/11](https://www.reclameaqui.com.br/enel-distribuicao-rio/minha-conta-de-luz-so-aumenta-e-o-servico-esta-cada-dia-pior_8009DNAPCQbKYdXp/); [Powercut — Estado do RJ](https://powercut.io/br/estado-do-rio-de-janeiro/); [Powercut — metadados do feed](https://powercut.io/api/now.json); [Mapa da Enel](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa de Ocorrências Emergenciais da Light](https://mapa-ocorrencias.light.com.br/); [ANEEL — interrupções nas redes de distribuição](https://dadosabertos.aneel.gov.br/dataset/interrupcoes-de-energia-eletrica-nas-redes-de-distribuicao).

---

## Atualização matinal — 22/11/2026 (08h14 BRT)

**Resultado cartográfico:** nenhum novo ponto confirmado. A busca identificou novas reclamações e um endereço numerado na Tijuca, mas não foi possível obter coordenada específica e verificável do imóvel/trecho. O Top 20, `dados/pontos.csv`, `dados/pontos.geojson`, `dados/resumo_por_municipio.csv` e `index.html` foram preservados.

### Novas pistas publicadas após 21/11 às 08h29

- **Tijuca — Rua Araújo Pena, nº 83 (poste em frente ao Edifício Maria Eduarda):** reclamação publicada em 21/11 às 18h18 diz que houve furto de cabo às 17h de 19/11 e que o prédio ficou parcialmente sem energia. O número 83 foi corroborado por listagens do edifício e por página que usa dados de ITBI/IPTU/cadastro municipal. Não foi obtida coordenada específica do prédio. O CEP do logradouro oferece apenas uma coordenada aproximada de rua (`-22.9227, -43.21954`), que não foi usada. Prioridade alta para geocodificação de endereço numerado; não inserir no mapa ainda.
- **Tijuca — Rua Araújo Pena / Largo da Segunda-Feira:** busca retrospectiva encontrou outra reclamação, publicada em 19/11 às 23h47, que menciona furto de cabo e quase 20h sem energia. Está fora da janela de novas publicações; foi registrada como pista histórica relacionada, mas não fundida com o relato do nº 83 porque os horários descritos não coincidem.
- **Méier:** reclamação de 21/11 às 18h34 diz que um prédio inteiro estava sem energia desde 02h, após vandalismo alegado em poste. Mais de 50 chamados são mencionados; sem rua ou número.
- **Niterói:** duas reclamações Enel em 21/11 às 22h47 e 23h05 descrevem falta de energia desde o dia anterior e interrupções em dois dias consecutivos. Podem se referir ao mesmo agrupamento; endereços mascarados e sem coordenadas, por isso não foram contadas como dois eventos distintos.
- **Valença — área rural:** reclamação Light publicada em 22/11 às 07h46 informa mais de 12h sem energia após chuva e afirma que episódios semelhantes podem levar mais de 48h para atendimento. Sem localidade ou logradouro.
- **Magé:** reclamação Enel publicada em 21/11 às 10h35 relata mais de 24h sem energia e falta d'água, mas não informa bairro/rua nem comprova alcance coletivo.
- **Rio de Janeiro (capital):** novas reclamações Light relatam vizinhos com fornecimento em apenas uma fase desde 11/11, baixa tensão em vários imóveis ao longo de uma rua (endereço mascarado), oscilações recorrentes em residência e interrupções individuais prolongadas. Sem bairro/logradouro ou coordenadas; há possível sobreposição entre relatos genéricos da capital.
- **Recorrência Enel na capital:** reclamação publicada em 21/11 às 13h07 fala em faltas semanais em condomínio, mas o último evento específico reproduzido no texto tem previsão de restabelecimento em 12/11. Foi guardada como contexto de recorrência, não como novo evento.
- **Pistas individuais:** foram preservadas reclamações de Magé e da capital sem evidência de imóveis vizinhos; permanecem fora do mapa.

### Snapshot operacional — Enel Rio

A API pública do agregador Powercut, consultada às **08h10:13 BRT de 22/11**, indicava o feed `br-enel-rj` com **127 ocorrências**, `ok=true` e `stale=false`. Esse é o contador de ocorrências do feed, não de clientes afetados. O snapshot de página estadual disponível às 05h20 informava 127 faltas e 5.325 clientes, mas não deve ser tratado como fotografia das 08h10. O agregador não lista a Light como fonte; não cobre a capital pela fonte Enel Rio e não fornece coordenadas individuais neste endpoint.

### Qualidade e cobertura das fontes

- **Enel oficial:** página do Mapa da Energia acessível, com mapa dinâmico; a extração textual consultada ainda mostrava “Buscando áreas de falta de energia” e tabela sem linhas preenchidas. A página alerta que o número pode incluir desligamentos momentâneos inferiores a três minutos e refletir manobras operacionais.
- **Light oficial:** Mapa de Ocorrências Emergenciais acessível, mas sem linhas de texto extraíveis nesta consulta.
- **ANEEL:** não foi localizada nova publicação de fiscalização ou base georreferenciada de eventos diários para 21–22/11. DEC/FEC seguem sendo indicadores agregados por conjuntos de unidades consumidoras, com atualização defasada; não localizam rua/quarteirão em tempo real.
- **Prefeituras, Defesa Civil, Procons e imprensa local:** não foi localizada nova publicação com endereço e coordenadas verificáveis na janela pesquisada.
- **Reclame Aqui:** trouxe sinais úteis e horários de publicação, mas a maioria dos endereços está mascarada; reclamações individuais não comprovam interrupção coletiva.

### Auditoria da base

- 120 pontos no CSV e 120 feições no GeoJSON.
- 96 posições marcadas como conferidas; isso não significa que todas tenham precisão de quarteirão.
- Precisão declarada: 24 registros rua, 15 ponto e 81 bairro.
- Nenhuma coordenada foi criada ou alterada; Top 20 preservado.
- 12 novos registros de pista/qualidade publicados após a atualização anterior, 1 pista retrospectiva da Tijuca e 1 snapshot operacional foram acrescentados a `dados/pistas_nao_verificadas.csv`. Todos permanecem fora da camada cartográfica.

**PDF:** não gerado nesta rodada porque nenhum novo ponto cumpriu simultaneamente os critérios de endereço verificável e coordenadas específicas verificáveis. O relatório de investigação está nesta seção e no CSV de pistas.

---

## Atualização matinal — 21/11/2026 (08h29 BRT)

**Resultado cartográfico:** nenhum novo ponto confirmado. Nenhum candidato novo apresentou, simultaneamente, endereço de ocorrência verificável e coordenadas verificáveis. O Top 20, dados/pontos.csv, dados/pontos.geojson, dados/resumo_por_municipio.csv e index.html foram preservados.

### Sinais novos em investigação

- **São Gonçalo — Portão do Rosa, Rua Fernandes de Mendonça:** reclamação publicada em 20/11 às 22h03 diz que a rua estava sem luz e que moradores já haviam reclamado. A existência do logradouro e sua associação ao bairro são corroboradas por referência pública de endereço, mas não foi obtida coordenada verificável do trecho. Prioridade alta; não inserir no mapa até geocodificação confiável.
- **Arraial do Cabo:** relato publicado em 20/11 às 18h31 descreve interrupções diárias desde 17/11, transformador antigo e troca de poste; sem bairro ou rua.
- **São Francisco de Itabapoana:** relato de 20/11 às 23h55 afirma 5–6 interrupções por dia e baixa tensão em várias residências; sem localidade.
- **Belford Roxo:** relato de 21/11 às 04h26 diz que a energia oscilou desde a tarde de 20/11 e caiu totalmente à noite; bairro e rua não informados.
- **Nova Iguaçu — Botafogo:** relato de 21/11 às 04h27 descreve quedas repetidas em casas vizinhas desde 20/11; sem rua.
- **Rio de Janeiro (capital):** duas reclamações novas na janela de publicação: uma relata falta desde 19/11 às 14h36 (36h50 até a publicação de 21/11 às 03h26); outra, publicada em 20/11, afirma falta desde 11/11 e aponta possível problema em fase no poste. Ambas sem bairro/logradouro; não há confirmação de abrangência coletiva.
- **Saquarema:** menção municipal genérica publicada em 21/11 às 05h50. Pode se sobrepor tematicamente às pistas anteriores de Saquarema e Vilatur; não contar como ocorrência distinta.
- **Rio de Janeiro — Edifício Portobianco:** relato de 20/11 às 22h48 atribui a interrupção ao corte/furto de cabos no poste em frente ao edifício. Endereço mascarado e possível sobreposição com reclamação anterior de condomínio; não contar separadamente até deduplicação.

### Snapshot operacional agregado

Powercut, às **08h20 de 21/11**: **173 faltas** e **3.049 clientes sem energia** na página estadual. Maiores agrupamentos identificados como Enel Rio: Cidade Parque Paulista (572), Guapimirim (441), Araruama (421), São José do Vale do Rio Preto (218), Santa Lúcia (182), Itatiaia (134), Itaperuna (114), Tamoios (110), Jacuacanga (67), Casimiro de Abreu (66), Cantagalo (61) e Jaconé (46).

Comparação com o snapshot estadual de 20/11 às 08h40 (212 faltas e 4.545 clientes): redução de 39 registros e 1.496 clientes no retrato agregado. Isso não prova que cada ocorrência anterior foi encerrada. O total estadual pode reunir mais de uma distribuidora; os agrupamentos acima aparecem identificados como Enel Rio. O agregador declara coletar os mapas públicos a cada 10 minutos e não fornece endereço, início, duração ou coordenadas individuais.

### Qualidade e cobertura das fontes

- **Enel:** página oficial do Mapa da Energia acessível; mapa dinâmico não apresentou tabela preenchida na extração desta rodada. A própria página alerta que os registros podem incluir desligamentos inferiores a três minutos e refletir manobras operacionais.
- **Light:** Mapa de Ocorrências Emergenciais acessível, mas sem conteúdo textual legível para extração nesta consulta.
- **ANEEL:** indicadores coletivos DEC/FEC disponíveis; atualização mensal e granularidade por conjunto de unidades consumidoras, inadequados para localizar ocorrência diária por rua.
- **Prefeituras/Defesa Civil/Procons e imprensa:** nenhuma nova publicação com endereço e coordenadas verificáveis foi localizada na janela pesquisada.

### Auditoria da base

- 120 pontos no CSV e 120 feições no GeoJSON.
- 96 registros com posicao_conferida=sim; isso indica conferência de posição, não necessariamente precisão de quarteirão.
- Precisão declarada no CSV: 24 registros rua, 15 ponto e 81 bairro.
- Nenhuma coordenada nova foi criada, nenhuma posição foi alterada e o Top 20 foi preservado.
- As 9 pistas desta rodada e o snapshot agregado foram acrescentados a dados/pistas_nao_verificadas.csv; permanecem fora da camada cartográfica.

**PDF:** não gerado nesta rodada porque não houve novo ponto confirmado para incorporar. O relatório de investigação fica registrado nesta seção e no CSV de pistas.



Abra `index.html` no navegador (Chrome ou Edge, com internet).

## Cobertura

- **Grande Rio e Baixada** (Light e Enel): imprensa, prefeituras e relatos de moradores.
- **Região dos Lagos** (Enel): protestos em Saquarema (RJ-106, km 73) e Cabo Frio (Maria Joaquina e Jardim Caiçara), além de relatos em Iguaba, Saquarema, Cabo Frio, Búzios e Araruama.
- **Norte e Noroeste** (Enel): protestos na BR-356 em Cardoso Moreira; bairros sem luz em Cambuci e Itaperuna; pico de 13 mil unidades em Campos.
- **Serra, Sul Fluminense e Costa Verde**: não houve notícia de falta de luz ligada ao temporal; há relatos isolados de moradores em Petrópolis, Miguel Pereira e Macaé.
- **Energisa** (região de Nova Friburgo): sem relatos ligados ao temporal.

## Fontes

- Imprensa e prefeituras, 8 a 13/11 (links em cada ponto).
- Reclamações públicas no Reclame Aqui contra Light, Enel Rio e Energisa, 7 a 16/11.
- Não incluídos: X, Instagram, Facebook, Threads e Bluesky, que exigem conta para busca.

## Arquivos

| Arquivo | Conteúdo |
|---|---|
| `index.html` | Mapa com filtros (nível, concessionária, origem), raio de busca e exportação em CSV e KML |
| `dados/pontos.csv` | Todos os pontos com coordenadas, nível, horas sem luz e links das fontes |
| `dados/pontos.geojson` | Os mesmos pontos em GeoJSON |
| `dados/resumo_por_municipio.csv` | Pico de clientes sem luz (imprensa) e reclamações por município |

## Critérios

- **Crítico**: protesto no local ou 70 h ou mais sem luz.
- **Alto**: 48 h ou mais, ou apontado como o caso mais grave do município.
- **Afetado**: citado sem duração ou com menos de 48 h.

Relatos de moradores usam as horas informadas pelo próprio morador. Coordenadas marcadas como conferidas foram checadas no geocodificador da Esri; as demais são aproximadas.

## Privacidade

Nenhum nome de pessoa é publicado. Ruas aparecem sem número. As reclamações do Reclame Aqui já são públicas e mascaradas pela plataforma.

## Verificação de monitoramento — 18/11/2026, 16h40

- Não foram identificados novos pontos que cumpram simultaneamente os critérios de endereço verificável, coordenadas e evidência corroborável desde a rodada anterior.
- A base permanece com **120 registros**; **96** têm posição marcada como conferida. O ranking Top 20 foi preservado, sem reordenação.
- Foram registradas pistas novas de Paciência e Nova Jersey (Rio de Janeiro), além de relatos individuais sem logradouro identificável; permanecem fora da camada de pontos confirmados.
- O arquivo `dados/pontos.geojson` foi reconstruído a partir de `dados/pontos.csv`, sem inclusão ou alteração de ocorrências, porque a versão anterior terminava incompleta. A nova versão contém 120 feições válidas.
- Nenhum relatório PDF foi gerado nesta rodada, pois não houve novo ponto confirmado a incorporar.


## Verificação de monitoramento — 19/11/2026, 08h33

- **Nenhum novo ponto confirmado**: não apareceu candidato com rua/trecho verificável e coordenadas sustentadas por fonte suficiente. A base cartográfica permanece com **120 pontos**, dos quais **96** têm posição marcada como conferida; Top 20 preservado, sem reordenação.
- Três novas pistas públicas foram separadas em `dados/pistas_nao_verificadas.csv`: Niterói (Enel, relato de interrupções recorrentes em todo o quarteirão, sem logradouro), Maricá (Enel, rua mascarada) e município do Rio de Janeiro (Light, flutuação/falta de fase em algumas casas, sem bairro ou rua). Nenhuma foi adicionada ao CSV/GeoJSON de pontos.
- Uma reclamação de Petrópolis sobre falta de energia após troca de titularidade e pedido de religação foi triada fora da camada de interrupções de rede: o relato descreve uma ligação individual, sem evidência de falha coletiva da distribuição.
- O mapa oficial da Enel informa que os dados são dinâmicos e podem incluir interrupções momentâneas inferiores a três minutos, além de mudar após manobras de telecomando. O extrator público consultado indicou o feed Enel Rio ativo às 08h20 (horário de Brasília), com 192 registros no feed; esse número é de registros, não de clientes afetados, e não fornece, nesta consulta, evidência de endereço e coordenadas para inclusão.
- O mapa institucional da Light está publicado, mas seu mapa incorporado não entregou conteúdo textual extraível nesta rodada. Não foi localizada nova publicação de ANEEL, prefeitura, Defesa Civil ou imprensa local com endereço e coordenadas verificáveis no período.
- **Nenhum PDF foi gerado**, pois não houve ponto confirmado a incorporar. O mapa, o ranking e os arquivos de pontos foram preservados sem alteração.

Fontes consultadas: [Mapa da Energia — Enel Rio](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa de Ocorrências Emergenciais — Light](https://www.light.com.br/SitePages/MapaDeOcorrenciasEmergenciais.aspx); [feed público de estado das fontes](https://powercut.io/api/now.json); [pista Niterói](https://www.reclameaqui.com.br/enel-distribuicao-rio/estou-sem-luz-em-minha-regiao-ha-dias-e-a-enel-nao-resolve_DQ0sFIIm0SBpckhj/); [pista Maricá](https://www.reclameaqui.com.br/enel-distribuicao-rio/minha-energia-oscila-e-falta-luz-em-marica-ha-anos_LUQeC34AsGRKog8O); [pista Light — Rio de Janeiro](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/problema-recorrente-de-falta-ds-energia-no-local_ZxwXCjDJjcsunCAH/).


## Verificação de monitoramento — 19/11/2026, 09h05

- **Novos pontos confirmados:** nenhum. A base de pontos permanece com **120 registros**, dos quais **96** têm posição marcada como conferida. O Top 20 foi preservado, sem reordenação.
- **Novas pistas registradas:** uma reclamação da Light publicada em 18/11, às 20h17, informa uma rua sem energia por cerca de 6 horas no município do Rio de Janeiro, mas não divulga bairro ou logradouro; foi incluída em `dados/pistas_nao_verificadas.csv`.
- **Sinais operacionais agregados:** a página estadual do Powercut apresentava um retrato atualizado às **06h20 de 19/11** com **128 falhas e 7.280 clientes sem energia** no RJ. Entre as localidades identificadas, foram registradas como pistas: Pipeiras (São João da Barra, 812 clientes), Balneário da Praia de João Francisco de Paula (Quissamã, 533), São José do Vale do Rio Preto (523, rótulo municipal), Barracão (São Gonçalo, 283), Sumidouro (258, rótulo municipal), Parque Santo Antônio (Campos dos Goytacazes, 246), Canellas City (Iguaba Grande, 237), Virgem Santa (Macaé, 224) e Araçatiba (Maricá, 204). Esses números são um retrato agregado de falhas, não duração, gravidade ou confirmação de apagão persistente. A fonte informa coleta dos mapas públicos em intervalos de dez minutos, mas o snapshot acessível nesta execução é de 06h20 e não deve ser apresentado como estado em tempo real às 09h05.
- **Deduplicação:** Itaipava (Petrópolis) também apareceu no feed com 169 clientes, mas já existe ponto na localidade; não foi criada uma segunda entrada. As localidades Soledade e Bairro I não foram atribuídas a municípios porque o rótulo é ambíguo. A pista de Niterói de 18/11 e a pista de Maricá de 18/11 já constavam no arquivo e não foram duplicadas.
- **Triagem negativa:** reclamações sobre religação após troca de titularidade, nova ligação e rompimento do fio de uma residência foram excluídas da lista de candidatos coletivos, por não comprovarem falha de rede em quarteirão.
- **Fontes primárias:** o mapa da Enel estava acessível, mas o conteúdo dinâmico não expôs os números/ocorrências em texto nesta consulta; a própria Enel alerta que o painel pode incluir interrupções momentâneas inferiores a três minutos. O portal da Light confirmou a existência do mapa institucional, mas seu conteúdo interativo não ficou legível para extração. A base de interrupções da ANEEL tem frequência mensal e granularidade por conjunto de unidades consumidoras; o recurso de 2026 consultado estava atualizado em **04/09/2026**, portanto não foi usado para confirmar ocorrências do dia.
- **HTML, pontos.csv e GeoJSON:** preservados, sem alterações, pois nenhuma pista alcançou endereço e coordenadas verificáveis em nível de quarteirão. **PDF:** não regenerado, pelo mesmo motivo. O raio espacial de 2 km e o ranking Top 20 não foram recalculados.

Fontes: [Mapa da Enel](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa de Ocorrências Emergenciais da Light](https://www.light.com.br/SitePages/MapaDeOcorrenciasEmergenciais.aspx); [Powercut — Estado do RJ](https://powercut.io/br/estado-do-rio-de-janeiro/); [Powercut — Campos dos Goytacazes](https://powercut.io/br/campos-dos-goytacazes/); [reclamação Light — rua sem luz por cerca de 6 horas](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/minha-horas-e-ninguem-me-da-informacao_KExPGZzVxQHUKg-S/); [ANEEL — interrupções nas redes de distribuição](https://dadosabertos.aneel.gov.br/dataset/interrupcoes-de-energia-eletrica-nas-redes-de-distribuicao).

## Verificação de monitoramento — 19/11/2026, 16h23

- **Novos pontos confirmados: nenhum.** A base cartográfica permanece com **120 registros**, dos quais **96** têm posição marcada como conferida. O Top 20 foi preservado, sem reordenação; nenhum endereço ou coordenada foi criado.
- **Nova pista coletiva não verificada:** reclamação publicada pela Light às 09h24 relata interrupções recorrentes em uma rua do município do Rio, com cerca de dez condomínios supostamente dependentes de um único transformador; a rua teria ficado sem energia durante toda a noite anterior e novamente no momento da publicação. O resultado público não informa bairro nem logradouro. Pista adicionada a `dados/pistas_nao_verificadas.csv`, sem coordenadas e fora da camada de pontos.
- **Reforço institucional de Paquetá:** a Defensoria Pública do RJ informou em 18/11 a abertura de procedimento administrativo sobre a Light, após relatos de apagões por semanas. A DPRJ relata que a Light enviou quatro geradores como medida paliativa e que, antes disso, havia interrupções de 1 a 3 horas em partes da ilha e de até três dias em regiões específicas. A fonte foi acrescentada ao registro já existente de Ilha de Paquetá no CSV e no GeoJSON; coordenadas, precisão, nível e ranking não foram alterados.
- **Snapshot operacional às 16h20:** Powercut registrou **268 falhas e 13.945 clientes sem energia** na página estadual. Principais rótulos identificados como Enel Rio: Barra de São João (4.106), Tamoios (732), Cascatinha (710), Guia de Pacobaíba (463), Duas Barras (412), Itaperuna (405), Cidade Parque Paulista (350), Parque Jóckey Club (348), Piratininga (332), Petrópolis (293), Maricá (261) e Ajuda de Cima (257). Às 12h20, o mesmo painel mostrava 267 falhas e 9.183 clientes; diferença de +1 falha e +4.762 clientes no snapshot das 16h20. São contagens dinâmicas e agregadas, sem endereço, hora inicial, duração ou coordenadas; não foram convertidas em pontos. O painel também informa que reúne dados de mais de um operador, portanto o total estadual não deve ser tratado como total exclusivo da Enel Rio.
- **Deduplicação:** Engenho do Mato, Piratininga, Petrópolis, Maricá e outras áreas já aparecem na base ou em pistas anteriores; a leitura operacional não gerou novas feições. Rótulos como Barra de São João, Tamoios e Cascatinha permanecem sinais a investigar, não endereços.
- **Triagem negativa:** foram excluídos como candidatos coletivos relatos de residência isolada sem energia após manutenção, medidor com aquecimento/fogo em uma única unidade, divergência cadastral de medidor, ligação/religação individual e corte por cobrança. Uma reclamação de fase parcial em residência sem bairro/logradouro também não foi promovida a ponto.
- **Fontes primárias e limitações:** o mapa da Enel informa dados dinâmicos por município e alerta que pode refletir desligamentos momentâneos inferiores a três minutos; o mapa institucional da Light existe, mas o conteúdo interativo não foi extraível em texto nesta consulta. A base pública da ANEEL foi atualizada em **12/11/2026**, tem frequência mensal e granularidade por conjunto de unidades consumidoras, não por rua. A Defensoria Pública trouxe a nova confirmação institucional sobre Paquetá.
- **Arquivos:** `dados/pistas_nao_verificadas.csv` recebeu a nova pista coletiva e o snapshot agregado; `dados/pontos.csv` e `dados/pontos.geojson` receberam apenas o reforço de fonte/fato do registro existente de Paquetá. Nenhuma nova feição foi criada. `index.html`, resumo municipal e Top 20 não foram alterados. **PDF não regenerado**, pois não houve novo ponto confirmado.

Fontes: [DPRJ — atuação pela normalização do fornecimento em Paquetá](https://defensoria.rj.def.br/noticia/detalhes/33174-DPRJ-atua-pela-normalizacao-do-fornecimento-de-energia-eletrica-em-Paqueta-que-sofre-com-apagoes); [reclamação Light — interrupções recorrentes em rua com cerca de dez condomínios](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/minha-rua-esta-sem-energia-eletrica-constantemente-e-minha-geladeira-quebrou_EDatL2KTomyVIo0S/); [Powercut — Estado do RJ](https://powercut.io/br/estado-do-rio-de-janeiro/); [Mapa da Enel](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa de Ocorrências Emergenciais da Light](https://www.light.com.br/SitePages/MapaDeOcorrenciasEmergenciais.aspx); [ANEEL — interrupções nas redes de distribuição](https://dadosabertos.aneel.gov.br/dataset/interrupcoes-de-energia-eletrica-nas-redes-de-distribuicao).


## Verificação de monitoramento — 20/11/2026, 08h46

- **Novos pontos confirmados: nenhum.** A base dados/pontos.csv permanece com **120 registros**, dos quais **96** têm posição marcada como conferida; dados/pontos.geojson mantém **120 feições**. O ranking Top 20 foi preservado, sem reordenação. Não foram criados endereços ou coordenadas. A auditoria dos campos de precisão mostra **24 registros marcados como rua, 15 como ponto e 81 como bairro**; portanto, os 96 marcados como posição conferida não equivalem a 96 localizações em nível de quarteirão. Os 81 registros de bairro permanecem como legado da base, sem serem promovidos a precisão de rua.
- **Pista prioritária — Vilatur, Saquarema (Enel):** reclamação pública de 20/11 às 00h17 relata interrupções frequentes, oscilações e falta de energia no momento da publicação. O bairro é identificável, mas não há rua/trecho, início exato ou duração do episódio. Como sinal auxiliar, o Powercut listou Vilatur com **660 clientes** no snapshot de 19/11 às 19h20; no snapshot das 08h40 de 20/11 Vilatur não aparece entre as 12 maiores localidades, o que não prova normalização nem persistência. Mantida apenas como pista, sem coordenadas.
- **Pista genérica — Saquarema (Enel):** reclamação de 19/11 às 21h12 relata queda de fase todas as noites e equipamentos oscilando, sem bairro ou rua. Mantida separada de Vilatur porque não há prova de que seja a mesma ocorrência.
- **Pista de qualidade de fornecimento — Mesquita (Light):** reclamação de 19/11 às 22h46 atribui quedas frequentes na rua a possível transformador insuficiente. Não informa logradouro e também descreve uma interrupção individual/histórica antes da regularização em 2026; não confirma falta coletiva atual. Mesquita já tem pontos na base, mas a falta de endereço impede deduplicação espacial.
- **Snapshot operacional agregado — 20/11 às 08h40:** Powercut apresentava **212 faltas e 4.545 clientes sem energia** na página estadual. Maiores rótulos identificados como Enel Rio: Triunfo (501), Itacurussá (418), Arraial do Cabo (292), Mangaratiba (232), Maricá (221), São José do Vale do Rio Preto (215), Itaperuna (164), Monsuaba (155), Parque Bela Vista (150), Itambi (145), Petrópolis (136) e Itaipava (115). O total da página reúne mais de um operador e não é exclusivo da Enel Rio; o agregador não fornece rua, início, duração ou coordenadas. Em relação ao snapshot de 19/11 às 16h20 (268 falhas e 13.945 clientes), a leitura atual é menor em 56 falhas e 9.400 clientes, mas essa diferença entre retratos agregados não prova quais ocorrências foram encerradas.
- **Triagem negativa:** reclamações novas sobre religação/corte de uma unidade em Campos dos Goytacazes, furto de cabos e dano de medidor em uma residência na capital, corte individual em Nova Iguaçu e dano de aparelhos em uma residência de São Gonçalo não foram promovidas a ocorrências coletivas de rede. Permanecem fora do mapa.
- **Qualidade e cobertura das fontes:** o mapa oficial da Enel foi acessado, mas seus valores dinâmicos não ficaram legíveis na extração textual; a própria página descreve cobertura municipal da Região Metropolitana e alerta que os números podem refletir interrupções momentâneas inferiores a três minutos. O mapa institucional da Light está publicado, mas o conteúdo interativo não apresentou dados extraíveis nesta consulta. O Powercut é um agregador de mapas públicos e lista Enel Rio, CEMIG e outras operações; não inclui Light entre as fontes exibidas, portanto não cobre sozinho o estado. O conjunto da ANEEL tem frequência mensal e granularidade por conjunto de unidades consumidoras; o recurso de interrupções de 2026 consultado estava atualizado em 04/09/2026, sem utilidade para confirmar ocorrências de rua em 20/11. Não foi localizada nova publicação de prefeitura, Defesa Civil, Procon ou imprensa local com endereço e coordenadas verificáveis na janela.
- **Arquivos:** dados/pistas_nao_verificadas.csv recebeu três novas pistas e o snapshot de 20/11 às 08h40. dados/pontos.csv, dados/pontos.geojson, dados/resumo_por_municipio.csv e index.html não foram alterados. Top 20 preservado. **PDF não gerado**, pois não houve novo ponto confirmado a incorporar.

Fontes: [Reclamação — Vilatur, Saquarema](https://www.reclameaqui.com.br/enel-distribuicao-rio/minha-energia-eletrica-em-vilatur-saquarema-esta-com-falhas-constantes-e-oscilacoes_6lHz9YbNnhq-yy6_/); [Reclamação — Saquarema, queda de fase diária](https://www.reclameaqui.com.br/enel-distribuicao-rio/minha-energia-tem-queda-de-fase-todo-dia-e-nao-consigo-reclamar_HeID0Z2PXsJ9zFGT/); [Reclamação — Mesquita, transformador](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/minha-energia-eletrica-cai-toda-hora-e-a-light-nao-instala-transformador_giWb4lkj6fMqXQv3/); [Powercut — Estado do RJ](https://powercut.io/br/estado-do-rio-de-janeiro/); [Mapa oficial da Enel](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa de Ocorrências Emergenciais da Light](https://www.light.com.br/SitePages/MapaDeOcorrenciasEmergenciais.aspx); [ANEEL — interrupções nas redes de distribuição](https://dadosabertos.aneel.gov.br/dataset/interrupcoes-de-energia-eletrica-nas-redes-de-distribuicao).

## Verificação de monitoramento — 20/11/2026, 09h25

- **Novos pontos definitivos:** nenhum. A base principal permanece com 120 registros; os 96 pontos marcados com posição conferida e o Top 20 foram preservados. Não houve endereço e coordenadas de quarteirão novos que justificassem alterar dados/pontos.csv, dados/pontos.geojson ou o HTML.
- **Nova pista coletiva da Light — município do Rio de Janeiro:** reclamação publicada em 20/11 às 05h29 informa que dois andares de um condomínio, totalizando 25 apartamentos, estavam sem luz desde 19/11 às 15h40. Duração aproximada até a publicação: 13h49. Bairro e logradouro não aparecem; também não é possível distinguir falha da rede de problema interno do condomínio. Registrada como pista, não como ponto.
- **Atualização da pista de Vilatur, Saquarema:** a reclamação de 20/11 às 00h17 já estava registrada. No snapshot Powercut de 19/11 às 19h20, a localidade aparecia com 660 clientes; no retrato de 20/11 às 08h40, aparece na listagem completa em 105º lugar, com 2 clientes. Isso indica redução no retrato agregado, mas não comprova normalização nem elimina a recorrência alegada pelo consumidor. Sem rua e coordenadas, continua fora do mapa.
- **Nova evidência municipal para Guapimirim:** a Prefeitura informou oficialmente que, após o temporal de 07/11, registrou 13 ocorrências de grande porte em diferentes bairros; 10 ainda estavam sem solução no levantamento e a Ouvidoria recebeu 56 reclamações de interrupções superiores a 72 horas. É evidência forte da gravidade municipal, mas sem discriminação dos bairros/ruas e sem coordenadas. A pista foi adicionada separadamente. No snapshot Powercut de 20/11 às 08h40, Guapimirim ainda aparecia com 15 clientes afetados; esse número é apenas um retrato agregado.
- **Ocorrências excluídas da triagem de apagão coletivo:** reclamação de Campos dos Goytacazes publicada em 20/11 às 04h04 descreve corte individual por alegada irregularidade e demora de religação; reclamação da Light publicada às 03h56 descreve furto de cabos e dano ao medidor de uma residência. Nenhuma comprova interrupção coletiva da rede no quarteirão.
- **Fontes oficiais:** a página da Enel Rio exibe mapa municipal dinâmico e alerta que os registros podem incluir interrupções momentâneas inferiores a três minutos ou cenários já reduzidos por manobras. O conteúdo do mapa incorporado não forneceu nesta consulta a tabela municipal legível. O mapa da Light abriu sem conteúdo textual extraível. O recurso 2026 da ANEEL consultado continua com última atualização em 04/09/2026, portanto não confirma ocorrências de 20/11.
- **Arquivos:** dados/pistas_nao_verificadas.csv atualizado; HTML, pontos.csv, pontos.geojson e Top 20 preservados. PDF não regenerado porque nenhum ponto definitivo foi incluído.

Fontes: [Powercut — retrato estadual de 20/11 às 08h40](https://powercut.io/br/estado-do-rio-de-janeiro/); [reclamação coletiva da Light no Rio](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/meus-2-andares-do-condominio-estao-sem-luz-desde-ontem-e-a-light-nao-aparece_srT4aBDi4cJx2EiE/); [Prefeitura de Guapimirim — dados da Ouvidoria e ocorrências na rede](https://guapimirim.rj.gov.br/2026/11/justica-determina-que-enel-cumpra-imediatamente-ordem-de-restabelecimento-de-energia-em-guapimirim/); [Vilatur — reclamação de oscilações](https://www.reclameaqui.com.br/enel-distribuicao-rio/minha-energia-eletrica-em-vilatur-saquarema-esta-com-falhas-constantes-e-oscilacoes_6lHz9YbNnhq-yy6_/); [Mapa da Enel Rio](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa da Light](https://mapa-ocorrencias.light.com.br/); [ANEEL — base histórica de interrupções](https://dadosabertos.aneel.gov.br/dataset/interrupcoes-de-energia-eletrica-nas-redes-de-distribuicao).

## Verificação de monitoramento — 21/11/2026, 09h07

- **Novos pontos confirmados: nenhum.** Nenhuma ocorrência encontrada nesta rodada apresentou endereço e coordenadas verificáveis em granularidade de quarteirão, com evidência suficiente para inclusão definitiva. A base principal segue com **120 registros** e o Top 20 foi preservado, sem reordenação.
- **Nova pista de qualidade do fornecimento — Light, município do Rio de Janeiro:** reclamação publicada em 21/11 às 00h27 descreve oscilações e desligamentos repentinos há aproximadamente três meses, sobretudo entre 19h e 23h. É relato atribuído a uma residência; não há bairro, rua, quarteirão ou confirmação de imóveis vizinhos. Registrada somente como pista, sem coordenadas.
- **Nova pista genérica — Light, município do Rio de Janeiro:** reclamação publicada em 21/11 às 00h07 diz que a energia voltou a cair, indo e vindo, com falta de fase. Sem bairro, rua, início, duração ou extensão coletiva; não contar como ocorrência independente das demais reclamações genéricas da capital.
- **Duas reclamações de qualidade de tensão — Enel, São Gonçalo:** publicadas em 21/11 às 00h06 e 02h51, relatam quedas/oscilação e danos em eletrodomésticos de residências. Não informam bairro, rua ou vizinhos afetados. Foram registradas como pistas residenciais, sem tratá-las como prova de apagão de quarteirão nem como dois eventos geográficos independentes.
- **Deduplicação das pistas já existentes:** os relatos de Belford Roxo (publicado às 04h26), Botafogo/Nova Iguaçu (04h27), Saquarema (05h50) e a interrupção residencial no Rio desde 19/11 (03h26) já constavam do CSV; não foram duplicados. A reclamação de Portão do Rosa, São Gonçalo, na Rua Fernandes de Mendonça, também permanece como pista anterior: bairro e rua identificados, mas coordenadas verificáveis do trecho ainda ausentes.
- **Monitoramento operacional Enel Rio:** o retrato da página estadual do Powercut, atualizado às **08h20**, mostrava **173 falhas e 3.049 clientes sem energia**. Entre os maiores rótulos identificados como Enel Rio: Cidade Parque Paulista (572), Guapimirim (441), Araruama (421), São José do Vale do Rio Preto (218), Santa Lúcia (182), Itatiaia (134), Itaperuna (114), Tamoios (110), Jacuacanga (67), Casimiro de Abreu (66), Cantagalo (61) e Jaconé (46). A listagem completa contém localidades com contagens menores. O total da página pode reunir fontes de outros operadores; os rótulos citados estão identificados como Enel Rio. O retrato não fornece rua, início, duração ou coordenadas individuais.
- **Prioridade territorial dentro da cobertura do projeto:** Cidade Parque Paulista (572) foi associado a Duque de Caxias por referência territorial; Guapimirim (441), Araruama (421) e Itaperuna (114) correspondem diretamente a municípios já cobertos. Tamoios (110) é distrito de Cabo Frio, também coberto. Jaconé (46) é um rótulo territorial limítrofe entre Saquarema e Maricá; como o feed não especifica o lado/município, mantido sem atribuição definitiva. Nenhum desses rótulos contém endereço de quarteirão ou coordenada da falha. Fontes de referência territorial: Cidade Parque Paulista/Duque de Caxias; Tamoios/Cabo Frio; Jaconé/Saquarema.
- **Verificação do feed:** o endpoint de metadados do Powercut indicava br-enel-rj com **176 ocorrências no feed** às 08h40 (timestamp UTC 2026-11-21T11:40:13.543Z). Esse número é contagem de ocorrências do feed, não clientes afetados, e não deve ser somado ou comparado diretamente com os 173 registros/3.049 clientes exibidos na página às 08h20.
- **Fontes oficiais e limitações:** o mapa da Enel informa visualização por município na Região Metropolitana e alerta que os dados podem refletir interrupções momentâneas inferiores a três minutos ou cenários já reduzidos por manobras. O mapa institucional da Light está disponível, mas o mapa interativo não apresentou conteúdo textual legível nesta consulta. A ANEEL mantém frequência mensal e granularidade geográfica por conjunto de unidades consumidoras; a página do conjunto registra última atualização de metadados em 19/10/2026, mas o recurso de dados de 2026 consultado estava atualizado em 04/09/2026. Não serve para confirmar ocorrências de rua de 21/11. Não foi encontrada nova publicação municipal, da Defesa Civil ou da imprensa local com endereço e coordenadas de quarteirão verificáveis nesta rodada.
- **Arquivos:** dados/pistas_nao_verificadas.csv recebeu quatro novas reclamações/pistas de qualidade do fornecimento e o snapshot do feed Enel Rio às 08h40. dados/pontos.csv, dados/pontos.geojson, dados/resumo_por_municipio.csv e index.html foram preservados. O raio de 2 km e o Top 20 não foram recalculados. **PDF não regenerado**, pois nenhum ponto definitivo foi incluído.

Fontes: [Powercut — Estado do RJ](https://powercut.io/br/estado-do-rio-de-janeiro/); [Powercut — metadados dos feeds](https://powercut.io/api/now.json); [reclamação Light — oscilações há três meses](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/minha-energia-eletrica-oscila-e-cai-constantemente-e-a-light-nao-resolve_F13gSQU9GKLpO2vl/); [reclamação Light — nova falta de fase](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/estou-sem-luz-novamente-e-a-light-nao-me-da-paz_fszw7KqOqESpxcjB/); [reclamação Enel — TV danificada após oscilações](https://www.reclameaqui.com.br/enel-distribuicao-rio/minha-tv-queimou-apos-oscilacoes-de-energia-e-a-enel-nao-resolve_gARtNB2qg-cdX2Mw/); [reclamação Enel — eletrodomésticos danificados](https://www.reclameaqui.com.br/enel-distribuicao-rio/minha-geladeira-e-ar-condicionado-foram-danificados-por-queda-de-energia-e-a-light-nao-deixa-eu-solicitar-o-ressarcimento_k6Sf5EZ-1H8nRLTD/); [Mapa da Enel](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa de Ocorrências Emergenciais da Light](https://www.light.com.br/SitePages/MapaDeOcorrenciasEmergenciais.aspx); [ANEEL — interrupções nas redes de distribuição](https://dadosabertos.aneel.gov.br/dataset/interrupcoes-de-energia-eletrica-nas-redes-de-distribuicao).


---

## Verificação complementar — 23/11/2026 (08h48 BRT)

**Resultado cartográfico:** nenhum novo ponto aprovado para o mapa. Foram encontradas pistas novas com maior precisão territorial em Araruama, além de reclamações de recorrência em Saquarema e no município do Rio. O Top 20, `dados/pontos.csv`, `dados/pontos.geojson`, `dados/resumo_por_municipio.csv` e `index.html` foram preservados.

### Pistas novas e prioridades

- **Araruama — Fonte Limpa, Loteamento Girassóis II (Enel):** reclamação publicada em 22/11 às 10h45 relata interrupções durante quase todo novembro, várias equipes no loteamento e informação de uma equipe de que um transformador teria queimado; o consumidor diz que estava havia dois dias consecutivos sem energia. A loteadora identifica o empreendimento em **Rua Um, s/n**; anúncio imobiliário também usa **Estrada Itatiquara, s/n** e descreve 20 quadras, 16 ruas e 365 lotes. Esses endereços são referências do loteamento, não o trecho comprovadamente afetado. **Prioridade alta para individualizar a quadra e a rua; não mapear ainda.**
- **Saquarema — município, bairro não informado (Enel):** reclamação de 23/11 às 05h22 afirma faltas diárias superiores a seis horas durante novembro e perda de geladeira e computador. É uma pista de recorrência relevante, mas não permite atribuição a Vilatur nem a qualquer outro bairro.
- **Rio de Janeiro — rua não divulgada (Light):** reclamação de 23/11 às 04h40 descreve sequência de quedas em 18/11 (estabilização somente após 04h de 19/11), 20/11 às 23h46, 22/11 às 01h07 e 23/11 às 04h12. A rua está mascarada; há risco de sobreposição com outras reclamações genéricas da capital.
- **Barra da Tijuca — Condomínio Oceana Golf (Light):** quatro interrupções em três semanas, duas em dias consecutivos (22 e 23/11), relatadas por um único morador. A própria reclamação admite possível falha interna do condomínio. Referências públicas divergem entre Avenida das Américas, 10.001 e Avenida Ermanno Dallari, 811. Não há comprovação de falha coletiva; manter fora do mapa.
- **Nilópolis (Light):** relato de 22/11 às 08h25 descreve perda de fase e baixa tensão desde a segunda-feira anterior, sem bairro ou rua.
- **Rio de Janeiro (Light):** relato de 22/11 às 15h20 afirma tensão entre 98 V e 121 V, cerca de sete dias sem conseguir usar eletrodomésticos e histórico de dois anos de instabilidade. Sem localização e sem verificação independente.

### Monitoramento operacional

- **Powercut — página estadual:** snapshot retornado para 23/11 às 05h20: **227 falhas e 11.903 clientes sem energia**. Maiores rótulos listados: Pipeiras (2.399), Centro (1.185), Praia Brava (561), Itatiaia (501), Parque Barão do Rio Branco (435), Campinas (423), Areal (413), São Joaquim (368), Meudon (338), Gravatá (277), Praia do Jardim (276) e São José do Vale do Rio Preto (266). A página reúne fontes de diferentes operadores; não atribuir o total inteiro à Enel Rio.
- **Powercut — API do feed Enel Rio:** às **08h40:13 BRT**, `br-enel-rj` registrava **279 ocorrências**, com `ok=true` e `stale=false`. É contador de eventos do feed, não de clientes. A descrição da fonte cobre Niterói, São Gonçalo e outros 64 municípios do RJ, não a cidade do Rio. Não comparar diretamente com o total de clientes da página estadual.
- **Contexto meteorológico:** o INMET publicou aviso de tempestade para 23/11, com baixo risco de corte de energia; o aviso inclui regiões Metropolitana do Rio, Baixadas e outras áreas. É risco meteorológico, não evidência de apagão ocorrido.

### Fontes primárias e limitações

- **Enel:** mapa oficial aberto às 08h48, mas a extração ainda mostrava “Carregando mapa / Buscando áreas de falta de energia” e tabela sem linhas. A própria página informa que pode incluir desligamentos momentâneos inferiores a três minutos e cenários já reduzidos por manobras operacionais.
- **Light:** página institucional confirma o Mapa de Ocorrências Emergenciais em conformidade com a REN 1.137/ANEEL, mas não expôs dados individuais legíveis nesta consulta.
- **ANEEL:** página de distribuição modificada em 18/11 lista indicadores coletivos DEC/FEC, individuais DIC/FIC/DMIC/DICRI e relatórios de continuidade; não forneceu nesta consulta eventos diários com endereço e coordenadas de quarteirão.
- Não foi encontrada nesta rodada nova publicação municipal ou de Defesa Civil com endereço e coordenadas suficientes para inclusão.

### Deduplicação e arquivos

- As pistas de Saquarema foram mantidas separadas de Vilatur porque não há bairro/logradouro que permita confirmar ou descartar sobreposição.
- A reclamação da rua sem nome no Rio foi marcada como possível sobreposição com outras pistas genéricas da Light; não foi contada como novo cluster espacial.
- O condomínio Oceana Golf e os relatos individuais de baixa tensão foram registrados como pistas de qualidade do fornecimento, não como apagões coletivos confirmados.
- `dados/pistas_nao_verificadas.csv` recebeu seis pistas novas e dois snapshots operacionais.
- `dados/pontos.csv` permanece com 120 registros; `dados/pontos.geojson` permanece com 120 feições; `index.html` e o ranking Top 20 foram preservados.
- As 96 posições anteriormente marcadas como conferidas não significam precisão de quarteirão para todos os registros. Nenhuma coordenada foi criada, alterada ou inferida a partir de CEP.
- Raio de 2 km não recalculado. **PDF não regenerado**, pois nenhum novo ponto definitivo foi aprovado.

Fontes: [reclamação Enel — Fonte Limpa/Girassóis II](https://www.reclameaqui.com.br/enel-distribuicao-rio/fiquei-sem-luz-quase-o-mes-todo-e-a-enel-nao-resolve_vM7fCUhWqt-Z97SV/); [Lotecon — endereço de referência do Girassóis II](https://loteconempreendimentos.com.br/imovel/loteamento-girassois-ii/); [descrição imobiliária — 20 quadras e 16 ruas](https://www.rosanecastilhoimoveis.com.br/imovel/3632174/terreno-venda-araruama-rj-fonte-limpa); [reclamação Enel — Saquarema](https://www.reclameaqui.com.br/enel-distribuicao-rio/falta-de-luz-todos-os-dias-em-saquarema-rj-ja-perdi-eletrodomesticos_sL8CTpQ6OX488pxq/); [reclamação Light — quedas repetidas em rua não divulgada](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/minha-rua-sofre-com-constantes-quedas-de-energia-e-a-concessionaria-nao-resolve_LQc3OCaRosbw1XpU/); [reclamação Light — Oceana Golf](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/quatro-quedas-de-energia-em-tres-semanas-no-meu-apartamento_-MMqHpwux_UgsWmO/); [reclamação Light — Nilópolis](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/minha-energia-esta-ruim-e-a-empresa-nao-resolve-o-problema-recorrente_FNzJ_W5ycWgvQItx/); [reclamação Light — baixa tensão por sete dias](https://www.reclameaqui.com.br/light-servicos-de-eletricidade/estou-ha-7-dias-sem-luz-e-a-tensao-esta-muito-baixa-a-light-nao-resolve_QOEQvGcWbmz4u-cj/); [Powercut — Estado do RJ](https://powercut.io/br/estado-do-rio-de-janeiro/); [Powercut — API](https://powercut.io/api/now.json); [Mapa oficial Enel](https://www.enel.com.br/pt/Informativos/mapa-falta-de-luz.html); [Mapa de Ocorrências Emergenciais da Light](https://www.light.com.br/SitePages/MapaDeOcorrenciasEmergenciais.aspx); [ANEEL — indicadores de distribuição](https://www.gov.br/aneel/pt-br/centrais-de-conteudos/relatorios-e-indicadores/distribuicao); [INMET — aviso de tempestade de 23/11](https://avisos.inmet.gov.br/56476).
