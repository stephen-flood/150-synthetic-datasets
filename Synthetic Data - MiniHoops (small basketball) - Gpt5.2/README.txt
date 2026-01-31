**minihoops_teams.csv**
This file is your lookup table for teams. Use `team_id` as the key, and join it onto game or stats tables whenever you want readable team names (`team_name`) and locations (`city`) instead of IDs.

**minihoops_players.csv**
This file is your roster table. Each row is one player with a unique `player_id` and a `team_id` showing which team they’re on. It also includes basic attributes (name, position, role, age, salary) plus skill ratings (shooting, passing, rebounding, defense, usage) that you can use as predictors or to explain performance differences.

**minihoops_games.csv**
This file is your schedule. Each row is one game with `game_id`, date, and the matchup (`home_team_id`, `away_team_id`) plus a venue string. Use `game_id` to connect this table to team and player game stats, and use the home/away fields for split analyses.

**minihoops_team_game_stats.csv**
This file is your team box score by game. You get two rows per game—one for each team—keyed by (`game_id`, `team_id`). It contains team totals (points, shooting, rebounds, assists, turnovers, etc.), opponent points, margin, an estimated possessions value, and derived efficiency metrics (off/def rating) plus a `win` indicator.

**minihoops_player_game_stats.csv**
This file is your player box score by game. You get one row per player per game (including 0-minute appearances), keyed by (`game_id`, `player_id`). It includes minutes, starter flag, scoring and shooting splits, rebounds/assists/turnovers/defensive stats, plus/minus, and a `dnp_reason` field when minutes are 0.

**minihoops_injuries.csv**
This file records injury stints. Each row identifies a player and the inclusive range of games they missed (`start_game_id` through `end_game_id`), with dates, injury type, and severity. Use it to explain DNPs, build availability features, or analyze how missing players affects team results.
