# 🏆 Dicionário de Dados — Camada Gold

Este dicionário descreve os datasets analíticos gerados a partir das tabelas da **Silver**, com foco em análises agregadas e rankings, organizados para consumo direto.

---

## 🏅 Tabela: player_analytics/top_players

**Descrição:** Ranking dos 10 jogadores com maior avaliação geral (`overall_rating`) e potencial (`potential`).

| Coluna         | Tipo     | Descrição                              |
|----------------|----------|----------------------------------------|
| player_api_id  | long     | Identificador do jogador na API        |
| overall_rating | long     | Avaliação geral do jogador             |
| potential      | long     | Potencial futuro do jogador            |

---

## 📊 Tabela: player_analytics/agg_attributes

**Descrição:** Médias dos principais atributos técnicos e físicos dos jogadores.

| Coluna             | Tipo   | Descrição                               |
|--------------------|--------|-----------------------------------------|
| avg_curve          | double | Média de curvatura em cobranças         |
| avg_vision         | double | Média de visão de jogo                  |
| avg_agility        | double | Média de agilidade                      |
| avg_balance        | double | Média de equilíbrio                     |
| ...                | ...    | Médias para demais atributos (stamina, dribbling, etc.) |

---

## 🏟️ Tabela: match_analytics/total_matches

**Descrição:** Total de partidas disputadas por temporada.

| Coluna  | Tipo   | Descrição                    |
|--------- |------- |-----------------------------|
| season   | string | Temporada (ex: 2011/2012)   |
| total_matches | long | Número total de partidas |

---

## 📈 Tabela: match_analytics/stddev_goals

**Descrição:** Desvio padrão de gols marcados por temporada, separado por mandantes e visitantes.

| Coluna             | Tipo   | Descrição                                  |
|--------------------|--------|--------------------------------------------|
| season             | string | Temporada                                  |
| stddev_home_goals  | double | Desvio padrão de gols dos mandantes         |
| stddev_away_goals  | double | Desvio padrão de gols dos visitantes        |

---

## 📊 Tabela: match_analytics/max_min_goals

**Descrição:** Valores máximo e mínimo de gols marcados por temporada.

| Coluna           | Tipo   | Descrição                            |
|------------------|--------|--------------------------------------|
| season           | string | Temporada                            |
| max_home_goals   | long   | Máximo de gols do time da casa       |
| min_home_goals   | long   | Mínimo de gols do time da casa       |
| max_away_goals   | long   | Máximo de gols do time visitante     |
| min_away_goals   | long   | Mínimo de gols do time visitante     |

---

## ⚽ Tabela: match_analytics/goal_diff

**Descrição:** Diferença média de gols por temporada.

| Coluna              | Tipo   | Descrição                            |
|---------------------|--------|--------------------------------------|
| season              | string | Temporada                            |
| avg_goal_difference | double | Diferença média de gols              |

---

## 🏡 Tabela: match_analytics/avg_home_goals

**Descrição:** Média de gols marcados pelos times como mandantes.

| Coluna            | Tipo   | Descrição                            |
|-------------------|--------|--------------------------------------|
| home_team_api_id  | long   | ID do time mandante                  |
| avg_home_goals    | double | Média de gols do time como mandante  |

---

## 🛫 Tabela: match_analytics/avg_away_goals

**Descrição:** Média de gols marcados pelos times como visitantes.

| Coluna            | Tipo   | Descrição                            |
|-------------------|--------|--------------------------------------|
| away_team_api_id  | long   | ID do time visitante                 |
| avg_away_goals    | double | Média de gols do time como visitante |

---

