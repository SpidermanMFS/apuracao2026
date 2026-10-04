# Apuração SP 2026

Dashboard de acompanhamento da apuração das Eleições 2026 (1º turno, 04/10/2026) em São Paulo,
lendo direto os arquivos públicos de divulgação do TSE (`resultados.tse.jus.br/oficial/ele2026`).

Publicado em https://spidermanmfs.github.io/apuracao2026/ — também funciona abrindo o `index.html` direto no navegador. Atualiza sozinho a cada 30 s.

## O que mostra

- Cargos: Presidente (SP ou Brasil), Governador, Senador, Deputado Federal e Deputado Estadual.
- Seções totalizadas, eleitorado, comparecimento e abstenção.
- Composição dos votos: válidos, brancos, nulos e anulados sub judice.
- Ranking com foto, número, partido/coligação, vice ou suplentes, votos e % dos válidos.
  Senador mostra a linha de corte das vagas; Presidente/Governador marcam os 50% dos válidos.
- Deputados: cadeiras projetadas pelo TSE por partido/federação, quociente eleitoral e busca de candidatos.
- Evolução do % de cada candidato conforme as seções entram (gravada no `localStorage` do navegador).
- Andamento dos 645 municípios (mapa de calor + tabela ordenável) e, sob demanda, o líder em cada município.

## Arquivos do TSE usados

| Dado | Caminho (`<ele>` = 6257 federal / 6259 estadual) |
|---|---|
| Resultado (estado) | `<ele>/dados/sp/sp-c<cargo4>-e<ele6>-u.json` |
| Resultado (município) | `<ele>/dados/sp/sp<mun5>-c<cargo4>-e<ele6>-u.json` |
| Resultado Brasil (Presidente) | `6257/dados/br/br-c0001-e006257-u.json` |
| Andamento por município | `<ele>/dados/sp/sp-e<ele6>-ab.json` |
| Nomes dos municípios | `<ele>/config/mun-e<ele6>-cm.json` |
| Fotos | `<ele>/fotos/<sp ou br>/<sqcand>.jpeg` |

Cargos: 1 Presidente, 3 Governador, 5 Senador, 6 Dep. Federal, 7 Dep. Estadual.
