# 📘 Dicionário de Dados — Camada Silver

Este dicionário descreve as tabelas transformadas na camada **Silver**, com base na ingestão bruta da camada Bronze. As tabelas foram limpas, normalizadas e algumas particionadas para melhor performance.

---

## 🧍‍♂️ Tabela: player

**Descrição:** Dados básicos dos jogadores com transformação de nomes, unidades e conversões de tipo.

| Coluna         | Tipo     | Descrição                              |
|----------------|----------|----------------------------------------|
| id             | long     | Identificador único do jogador         |
| name           | string   | Nome completo do jogador               |
| player_api_id  | long     | ID do jogador na API                   |
| player_fifa_api_id | long | ID do jogador na base FIFA             |
| height_cm      | long     | Altura do jogador (cm)                 |
| weight_kg      | double   | Peso do jogador convertido para kg     |
| birth_date     | date     | Data de nascimento convertida          |
| year           | int      | Ano extraído de `birth_date` (partição)|

---

## 🏃 Tabela: player_attributes

**Descrição:** Atributos técnicos e físicos dos jogadores extraídos da base FIFA.

| Coluna         | Tipo     | Descrição                              |
|----------------|----------|----------------------------------------|
| player_api_id  | long     | Referência ao jogador                  |
| overall_rating | long     | Avaliação geral                        |
| potential      | long     | Potencial futuro                       |
| ...            | long     | Diversos atributos FIFA (stamina, dribbling etc.) |
| preferred_foot | string   | Pé preferido                           |
| attacking_work_rate | string | Intensidade de trabalho ofensivo    |
| defensive_work_rate | string | Intensidade de trabalho defensivo   |
| attr_date      | date     | Data de referência dos atributos       |

---

## 🏟️ Tabela: match

**Descrição:** Resultados e estatísticas de partidas.

| Coluna           | Tipo     | Descrição                                  |
|------------------|----------|--------------------------------------------|
| id               | long     | Identificador da partida                   |
| season           | string   | Temporada (ex: 2011/2012)                  |
| stage            | long     | Rodada da temporada                        |
| home_team_goal   | long     | Gols do time da casa                       |
| away_team_goal   | long     | Gols do time visitante                     |
| match_date       | date     | Data da partida (convertida)              |
| year             | int      | Ano extraído da data da partida            |
| ...              | ...      | Demais colunas mantidas da ingestão Bronze|

---