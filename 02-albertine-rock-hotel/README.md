# 🏨 Gestion des Stocks — Hôtel Albertine Rock (Ouganda)

**Type :** Stage logistique & data | **Outils :** Excel, Power BI, SQL | **Période :** Juillet–Août 2024

> *Données anonymisées des missions réalisées lors du stage.*

---

## Contexte

Stage au sein de l'**Hôtel Albertine Rock** en Ouganda, établissement boutique sur les rives du lac Albert.
Objectif : fiabiliser les données d'inventaire, construire des indicateurs de suivi opérationnel 
et proposer un plan d'optimisation des approvisionnements basé sur la consommation réelle.

---

## Périmètre

| Dimension          | Détail                                                         |
|--------------------|----------------------------------------------------------------|
| Produits suivis    | 50 références (linge, boissons, cuisine, ménager, équipements) |
| Fournisseurs       | 24 fournisseurs locaux ougandais                               |
| Période            | Juillet–Août 2024 (3 inventaires : 01/07, 01/08, 31/08)        |
| Devise             | Shilling ougandais (UGX) avec conversion EUR                   |
| Livraisons tracées | 50 livraisons avec anomalies et retards identifiés             |

---

## KPIs

| Indicateur                          | Valeur  |
|-------------------------------------|---------|
| Valeur totale du stock (31/08)      | 5 333 € |
| Produits en rupture                 | 4       |
| Produits en alerte                  | 1       |
| Taux de rotation moyen              | 1,23    |
| Délai moyen réappro                 |3,8 jours|
| Taux anomalies Tanzania Distillers  | 100%    |
| Taux anomalies Fresh Produce Uganda | 58,3%   |

---

## Structure du dashboard (3 pages)

### Page 1 — Vue d'ensemble du stock
- 5 KPIs : valeur stock, nb produits, ruptures, alertes, rotation
- Histogramme valeur par catégorie
- Camembert répartition
- Tableau des alertes produits
- Top 10 consommations

### Page 2 — Analyse rotation & statuts
- Slicer catégorie
- Taux de rotation par produit
- Scatter plot : stock final vs taux de rotation
- Tableau détaillé par produit

### Page 3 — Approvisionnement & optimisation
- Slicer fournisseur
- Délai moyen réappro par fournisseur
- Valeur stock par fournisseur
- Tableau d'optimisation avec statut commande

---

## Insights clés

- 🔴 Tanzania Distillers : 100% de taux d'anomalie — sourcing alternatif recommandé
- 📦 Fresh Produce Uganda : livraisons fréquentes mais souvent incomplètes (produits frais)
- 🛏️ Le linge hôtelier représente 55% de la valeur totale du stock
- ♻️ Taux de rotation moyen de 1,23 — stock renouvelé plus d'une fois sur la période
- ⚠️ 4 produits en rupture à la clôture auraient pu être évités avec un suivi hebdomadaire

---

## Captures d'écran

### Page 1 — Vue d'ensemble
![Vue d'ensemble](./screenshots/page1-vue-ensemble.png)

### Page 2 — Rotation & statuts
![Rotation et statuts](./screenshots/page2-rotation-statuts.png)

### Page 3 — Approvisionnement
![Approvisionnement](./screenshots/page3-approvisionnement.png)

---

## Fichiers

| Fichier                                | Description                                       |
|----------------------------------------|---------------------------------------------------|
| `Albertine_Rock_Inventaire.xlsx`       | Base inventaire complète (6 feuilles)             |
| `Albertine_Rock_Flux_Logistiques.xlsx` | Suivi des 50 livraisons avec analyse fournisseurs |
| `Albertine_Rock_Optimisation.xlsx`     | Plan d'optimisation des approvisionnements        |
