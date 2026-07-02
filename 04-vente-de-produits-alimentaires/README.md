# 🛒 Analyse des Ventes de Produits Alimentaires

**Type :** Projet académique | **Outils :** Power BI, Power Query, DAX | **Période :** Mars 2026

---

## Contexte

Analyse décisionnelle des ventes d'un groupe agroalimentaire international sur la période 2012–2014.
Le projet couvre 5 fichiers de données interconnectés représentant plus de 600 clients dans 7 pays,
5 catégories de produits et une équipe de 64 commerciaux répartis sur plusieurs régions.

---

## Périmètre

| Dimension           | Détail                                                                   |
|---------------------|--------------------------------------------------------------------------|
| Période             | 2012 – 2014 (Invoice Date)                                               |
| Zones géographiques | 7 pays : USA, UK, Allemagne, Espagne, Finlande, Danemark, Pays nordiques |
| Volume              | ~600 clients, 64 commerciaux, 83 villes                                  |
| Sources             | 5 fichiers (Excel + CSV)                                                 |
| Outil               | Microsoft Power BI Desktop — modélisation en étoile (Star Schema)        |

---

## Modèle de données — Star Schema

| Table       | Rôle                       | Clé             |
|-------------|----------------------------|-----------------|
| Sales       | Table des faits (centrale) | %KEY            |
| Customer    | Dimension clients          | Customer Number |
| Cities      | Dimension géographique     | City Code       |
| Item master | Dimension produits         | Item Number     |
| Sales rep   | Dimension commerciaux      | Sales Rep ID    |

> ⚠️ **Anomalie résolue :** le client 10021911 apparaissait deux fois dans Customer
> (deux City Codes différents), empêchant la relation 1-*. 
> Supprimé dans Power Query avant import.

---

## Mesures DAX

| Mesure        | Formule                                             | Utilisation                              |
|---------------|-----------------------------------------------------|------------------------------------------|
| `_CA`         | `SUM(Sales[Sales])`                                 | CA global — tous visuels                 |
| `_CA Top5`    | `IF(RANKX(...) <= 5, SUM(Sales[Sales]))`            | Top 5 clients — courbes d'évolution      |
| `_PanierMoyen`| `DIVIDE([_CA], DISTINCTCOUNT(Sales[Order Number]))` | Panier moyen par client                  |
| `_TauxRetour` | `DIVIDE(ABS(CALCULATE(...<0)), ABS(SUM(...)))`      | Taux de retour produits                  |
| `Tranche CA`  | `VAR/RETURN + CALCULATE` — colonne calculée         | Segmentation clients < 1M / 1M–5M / > 5M |

---

## Structure du dashboard (3 pages)

### Page 1 — Ventes
- Graphique combiné (courbes + histogramme) : évolution mensuelle CA et marge 2012–2014
- Graphique en secteurs : répartition du CA par zone géographique
- Graphique en anneau : part du CA par manager commercial
- Graphiques en cascade x2 : CA par famille et sous-famille de produits
- Histogramme Top 5 clients
- Slicer année

### Page 2 — Commerciaux
- Treemap : vision hiérarchique du CA par manager
- Carte à bulles : localisation des ventes par ville
- Carte choroplèthe : intensité du CA par pays
- Segments filtres : Product Line / Product Group

### Page 3 — Clients (analyse croisée)
- Graphique en anneau : segmentation clients par tranche CA (< 1M / 1M–5M / > 5M)
- Courbes Top 5 : évolution du CA des 5 meilleurs clients (fidélité / attrition)
- Histogramme panier moyen par client
- Jauge taux de retour produits
- Carte géographique des clients

---

## Traitements Power Query

| Table         | Traitement                                                           |
|---------------|----------------------------------------------------------------------|
| Sales rep.csv | Extraction Manager et Commercial depuis colonne hiérarchique `Path`  |
| Cities.xlsx   | Extraction du nom de ville depuis colonne `Desc` (Ville, État, Pays) |
| Sales.xlsx    | Ajout colonne `Sales = Cost + Margin` — prix HT calculé              |
| Customer.xlsx | Suppression doublon sur Customer Number (client 10021911)            |

---

## Insights clés

- 🇺🇸 Le marché américain représente plus de 45% du CA total
- 💎 Le CA est concentré sur un nombre restreint de clients à fort panier moyen (segment > 5M)
- 📉 Taux de retour de 1% — faible et non risqué pour la performance commerciale
- 🔍 4 clients allemands non géolocalisables (City Codes absents de la table Cities)
- 📊 L'évolution des Top 5 clients révèle des signaux d'attrition ou de fidélité sur 2012–2014

---

## Captures d'écran

### Page 1 — Ventes
![Ventes](./screenshots/page1-ventes.png)

### Page 2 — Commerciaux
![Commerciaux](./screenshots/page2-commerciaux.png)

### Page 3 — Clients
![Clients](./screenshots/page3-clients.png)

---

## Fichiers

| Fichier | Description |
|---------|-------------|
| `Note_Synthese_Ventes_Alimentaires.docx` | Note de synthèse complète du projet |
