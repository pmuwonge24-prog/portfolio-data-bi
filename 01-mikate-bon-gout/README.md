# 🍽️ Analyse Commerciale — Mikaté Bon Goût

**Type :** Stage commercial | **Outils :** Excel (VBA), Power BI, DAX | **Période :** Mai–Juillet 2025

>  *Données anonymisées des missions réalisées lors du stage.*
---

## Contexte

Stage au sein de **Mikaté Bon Goût**, food truck africain actif à Lyon sur les marchés locaux 
et grands festivals (Fourvière, Festival Miam Street Food).
Objectif : structurer les données de ventes pour produire des indicateurs de pilotage commercial.

---

## Missions réalisées

- Structuration d'une base de ventes (188 transactions, 8 produits, 4 événements)
- Calcul automatisé des coûts et marges en Excel avec prix unitaires réels
- Développement de fonctions VBA personnalisées (`funcNBjours`) pour le comptage des jours uniques
- Formules dynamiques `SOMME.SI.ENS` pour l'analyse hebdomadaire CA et marges
- Construction d'un dashboard Power BI interactif en 3 pages

---

## KPIs

| Indicateur                                                     | Valeur      |
|----------------------------------------------------------------|-------------|
| CA total (mai–juillet 2025)                                    | 44 117,50 € |
| Nombre de transactions                                         |    188,00 € |
| Panier moyen                                                   |    234,67 € |
| Marge brute totale                                             | 29 587,00 € |
| Taux de marge global                                           |    67%    € |
| Meilleur événement (CA)Total - Fourvière Festival (55,0% du CA)| 24 516,00 € |   
| Meilleur produit   (CA)Total - Poulet curry       (36,7% du CA)| 16 192,00 € | 

---

## Structure du dashboard (3 pages)

### Page 1 — Vue d'ensemble
- KPIs : CA total, nb transactions, panier moyen
- Histogramme Top 5 produits par CA
- Camembert répartition par catégorie
- Courbe CA mensuelle (mai → juillet)

### Page 2 — Analyse par événement
- Slicer événement — filtrage dynamique de tous les visuels
- KPIs contextuels réactifs
- Comparaison CA total vs CA moyen par jour par événement
- Tableau récapitulatif avec marges

### Page 3 — Analyse produits & rentabilité
- Graphique combiné : CA (barres) + Quantité vendue (courbe)
- Scatter plot : prix unitaire vs quantité
- Tableau de rentabilité complet

---

## Insights clés

- 🏆 Fourvière Festival = 55% du CA total grâce à sa durée (23 jours)
- ⚡ Festival Miam Street Food = meilleur CA moyen/jour (922€) malgré CA total inférieur
- 🧆 Le Mikaté (beignet) est le produit locomotive en volume (1 129 unités)
- 💰 Le Poulet curry et le Bowl Yassa génèrent l'essentiel de la valeur
- 📊 Taux de marge stable entre 65% et 68% sur 8 semaines

---

## Captures d'écran

### Page 1 — Vue d'ensemble
![Vue d'ensemble](./screenshots/page1-vue-ensemble.png)

### Page 2 — Analyse par événement
![Analyse par événement](./screenshots/page2-analyse-evenement.png)

### Page 3 — Analyse produits
![Analyse produits](./screenshots/page3-analyse-produits.png)

---

## Fichiers

| Fichier                            | Description                                             |
|------------------------------------|---------------------------------------------------------|
| `Mikate_Base_Ventes_Complete.xlsx` | Base de données des ventes avec KPIs et dashboard Excel |
