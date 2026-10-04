# Apuração 2026

Dashboard de acompanhamento da apuração das Eleições 2026 (1º turno, 04/10/2026) — Brasil, estados e municípios,
lendo direto os arquivos públicos de divulgação do TSE (`resultados.tse.jus.br/oficial/ele2026`).

Publicado em https://spidermanmfs.github.io/apuracao2026/ — também funciona abrindo o `index.html` direto no navegador. Atualiza sozinho a cada 30 s.

## O que mostra

- Abre na visão Brasil (Presidente), com mapa do Brasil colorido por quem lidera em cada estado (ou pelo andamento) e tabela por estado.
- Barra de estados agrupada por região: clique num estado (na barra ou no mapa) para ver só ele, com zoom no mapa.
- Escolha um estado (ou Exterior) para ver Governador, Senador, Deputado Federal e Estadual/Distrital, e os municípios.
- Seções totalizadas, eleitorado, comparecimento e abstenção.
- Composição dos votos: válidos, brancos, nulos e anulados sub judice.
- Ranking com foto, número, partido/coligação, vice ou suplentes, votos e % dos válidos.
  Senador mostra a linha de corte das vagas; Presidente/Governador marcam os 50% dos válidos.
- Deputados: cadeiras projetadas pelo TSE por partido/federação, quociente eleitoral e busca de candidatos.
- Evolução do % de cada candidato conforme as seções entram (gravada no `localStorage` do navegador).
- Andamento dos municípios do estado (mapa de calor + tabela ordenável) e, sob demanda, o líder em cada município.

## Arquivos do TSE usados

| Dado | Caminho (`<ele>` = 6257 federal / 6259 estadual) |
|---|---|
| Resultado (Brasil/estado/exterior) | `<ele>/dados/<uf>/<uf>-c<cargo4>-e<ele6>-u.json` (uf = br, sp, …, zz) |
| Resultado (município) | `<ele>/dados/<uf>/<uf><mun5>-c<cargo4>-e<ele6>-u.json` |
| Andamento por estado | `<ele>/dados/br/br-e<ele6>-ab.json` |
| Andamento por município | `<ele>/dados/<uf>/<uf>-e<ele6>-ab.json` |
| Nomes dos municípios | `<ele>/config/mun-e<ele6>-cm.json` |
| Fotos | `<ele>/fotos/<sp ou br>/<sqcand>.jpeg` |

Cargos: 1 Presidente, 3 Governador, 5 Senador, 6 Dep. Federal, 7 Dep. Estadual, 8 Dep. Distrital (DF).

Contornos dos estados: [click_that_hood](https://github.com/codeforgermany/click_that_hood) (base IBGE), simplificados e embutidos no HTML.
