# 🏠 Analyse du Marché Immobilier — Pyrénées-Atlantiques

**Type :** Projet académique | **Outils :** Power BI, Power Query, DAX, INSEE | **Année :** 2025

---

## Contexte

Analyse du marché immobilier du département 64 à partir des **Demandes de Valeurs Foncières (DVF)**, 
base officielle recensant toutes les transactions immobilières réelles françaises.
Enrichissement avec deux sources INSEE officielles pour une analyse socio-économique.

---

## Pipeline de données

| Étape             | Détail                                                            |
|-------------------|-------------------------------------------------------------------|
| Source principale | DVF — 13 790 transactions brutes (2021–2024)                      |
| Nettoyage         | 10 763 transactions après suppression doublons, nulls, aberrants  |
| Enrichissement 1  | Jointure INSEE dep64 — populations légales 2022 (~546 communes)   |
| Enrichissement 2  | Jointure Filosofi 2021 — revenus médians par commune              |
| Clé de jointure   | code_commune DVF (entier) → code_insee INSEE (texte 5 car.)       |

---

## KPIs

| Indicateur             | Valeur  |
|------------------------|---------|
| Transactions analysées | 10 763  |
| Prix moyen au m²       | 2 920 € |
| Médiane prix au m²     | 2 260 € |
| Communes couvertes     | ~546    |

---

## Structure du dashboard (3 pages)

### Page 1 — Vue d'ensemble
- KPIs globaux : nombre de transactions, prix moyen au m², valeur foncière totale
- Courbe d'évolution mensuelle du prix moyen au m²
- Histogramme de répartition par type de bien

### Page 2 — Analyse géographique
- Carte interactive des transactions par commune
- Top 10 communes par prix moyen au m²
- Comparaison prix moyen vs volume de transactions

### Page 3 — Analyse approfondie
- Top 10 communes par médiane du prix au m²
- Scatter plot : relation surface bâtie / prix au m²
- Évolution de la médiane du prix au m² (2021–2024)
- Carte de localisation des transactions

---

## Insights clés

- 📍 Le littoral (Biarritz, Anglet) affiche des prix au m² nettement supérieurs à l'intérieur
- 📈 Corrélation positive identifiée entre revenu médian et prix immobilier par commune
- 🏠 Les maisons représentent ~80% des transactions, concentrées hors des pôles urbains
- 📅 Pic d'activité identifié en janvier 2021 (109 transactions, médiane 4 206€/m²) — effet reprise post-Covid

---

## Captures d'écran

### Page 1 — Vue d'ensemble
![Vue d'ensemble](./screenshots/page1-vue-ensemble.png)

### Page 2 — Analyse géographique
![Analyse géographique](./screenshots/page2-analyse-geo.png)

### Page 3 — Analyse approfondie
![Analyse approfondie](./screenshots/page3-analyse-approfondie.png)

---

## Fichiers

| Fichier                  | Description                         |
|--------------------------|-------------------------------------|
| `Note_Synthese_DVF.docx` | Note de synthèse complète du projet |
