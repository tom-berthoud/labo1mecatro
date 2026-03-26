

- [ ] Ajouter les schémas de mesure 
- [ ] Ajouter les appareils de mesure, référence 

Hadrien :
- [x] 2.1 Mettre photo dimensions + photo Bobinage, enlever le textes inutiles
- [x] 2.2 Schéma périmètre
- [-] 2.3 Dire que l'on va prendre comme ref 0.3 A selon les indications de la pratique
- [x] 2.4 Schéma magnétique équivalent -> intégrer schéma et calcul iPad + mettre les 2 schémas un avec mur infini et un avec mur  = 400
- [x] 2.5 Vérifier les calculs
- [x] 2.6 Vérif hypothèses et domaine de validité
- [x] 2.3-4-5-6-7 enlever les lamda et mettre lfer/mur
- [x] 2.7 Enlever les mesures on est dans la théorie à comparer plus tard
- [x] 2.8 Contrôler
- [x] 2.9 Contrôler

Tom :
- [ ] 3.2 Controler les numéros et demander à Blatti leur numéro du convertisseur + ajouter la résolution
- [x] 3.3.1 Dégager la formule et simplifier 
- [x] 3.3.2 Tableau bof
- [x] 3.5.1 image petite et enlever *
- [x] 3.5.2 Ne répond pas bien à la question
- [x] 3.6 Ajouter sur le graph f35hz
- [ ] 3.7 Voir pourquoi grosse diff mesure-théorie Regarde demain
- [x] 3.8 Améliorer le tableau et mettre liens vers les parties du rapport
- [ ] 4 conlusion séparée entre analyse



---

avis claude :

# Corrections à apporter — Labo 1 : Circuit et hystérèse magnétiques

## 🔴 Priorité haute — à corriger absolument

### 1. Schéma magnétique équivalent (Fig. 3) — refaire proprement
- La Fig. 3 actuelle est une photo d'un brouillon manuscrit, ce qui est inacceptable pour un rapport rendu.
- **À faire :** redessiner le schéma magnétique équivalent avec un outil (LTspice, Inkscape, PowerPoint, draw.io, etc.) en montrant :
  - La source de force magnétomotrice $\mathcal{F} = N_1 I$
  - Les réluctances du fer (colonne centrale, branches latérales, traverses) clairement nommées
  - Les réluctances d'entrefer (centrale + 2 latérales)
  - Le schéma simplifié final avec les hypothèses clairement annotées à côté ($\mu_r \to \infty$ puis $\mu_r = 400$)
- Les hypothèses doivent être **listées explicitement dans le texte juste avant ou après le schéma** (pas dispersées dans le rapport), conformément à la demande §3.2.1.1 de la donnée.


---

### 3. Explication conceptuelle du diagramme x-y / B-H — à étoffer (§3.6)
- La donnée §4.3.3 pose une question de fond explicite : *"Que représente ce diagramme ? Expliquer la relation avec un diagramme du type B-H."*
- La réponse actuelle dans §3.6 est trop technique (facteur d'échelle) et ne répond pas à la question conceptuelle.
- **À faire :** ajouter un paragraphe expliquant :
  - Axe x = $i_1(t)$ ∝ champ $H(t)$ (car $H = N_1 i_1 / \ell_{total}$)
  - Axe y = sortie de l'intégrateur ∝ flux totalisé $\Psi_2(t)$ ∝ induction $B(t)$ (car $B = \Psi_2 / (N_2 \cdot S)$)
  - Le tracé x-y est donc bien une boucle B-H à facteurs d'échelle près
  - La boucle fermée représente le cycle d'hystérèse : le matériau ne suit pas le même chemin à la montée et à la descente du champ
  - L'aire de la boucle est proportionnelle aux pertes par hystérèse par cycle

---

## 🟡 Priorité moyenne — améliore la note

### 4. Comparaison commentée des courbes B=f(x) — µr→∞ vs µr=400
- La Fig. 4 montre les deux courbes mais le texte ne les compare pas explicitement.
- **À faire :** ajouter 3–4 lignes dans §2.7 commentant :
  - Pourquoi les deux courbes convergent pour les grands entrefers (le fer devient négligeable)
  - Pourquoi l'écart est maximal pour les petits entrefers (le fer représente une fraction plus grande de la réluctance totale)
  - Valeur numérique de l'écart à $x = 1\,\text{mm}$ : environ 20 mT, soit ~15%

### 5. Variation de U2 en fonction de la fréquence — à développer (§2.9)
- La donnée §3.3.2 demande d'indiquer comment le courant (et U2) varie en fonction de la fréquence.
- **À faire :** ajouter quelques lignes expliquant :
  - Pour $\omega L_{11} \ll R_1$ : $U_2 \approx j\omega L_{12} U_1 / R_1$ → U2 croît linéairement avec f
  - Pour $\omega L_{11} \gg R_1$ : $U_2 \approx (N_2/N_1) U_1$ → U2 est indépendant de f (régime transformateur)
  - Fréquence de transition : $f^* = R_1 / (2\pi L_{11})$ — calculer numériquement pour x=0 et x=2mm

### 6. Variation de la boucle B-H avec l'entrefer — quantifier (§3.6)
- Actuellement la description est qualitative uniquement ("s'allonge, s'amincit").
- **À faire :** ajouter une observation chiffrée :
  - $x=0$ : boucle étroite, grande pente → fort couplage, faibles pertes apparentes
  - $x=2\,\text{mm}$ : boucle plus large horizontalement (courant plus grand pour même flux), énergie dissipée visible
  - Relier l'amincissement à la réduction de l'hystérèse : l'entrefer "court-circuite" magnétiquement le fer, le point de fonctionnement du matériau est moins profond dans la saturation

### 7. Explication de l'écart sur R1 — plus rigoureuse (§3.3.3)
- L'écart de −7.3% est attribué aux "tolérances de fabrication du fil".
- **À faire :** mentionner aussi :
  - Tolérance sur la résistivité du cuivre (±2–3% selon norme)
  - Incertitude sur la longueur exacte du fil (longueur de spire estimée, pas mesurée)
  - Température de mesure non identique à 20°C exactement

---

## 🟢 Priorité basse — soigné mais non bloquant

### 8. Incohérence de numérotation des sections pratiques
- La partie pratique est structurée en §3.3–3.7 au lieu de §4.1–4.3 comme dans la donnée.
- **À faire :** soit harmoniser la numérotation avec la donnée, soit ajouter une correspondance explicite en début de section pratique.

### 9. Légende de la Fig. 5
- La Fig. 5 annonce "courbes théoriques et points mesurés" dans son titre/légende mais ne montre que la théorie.
- **À faire :** soit corriger la légende pour indiquer "courbes théoriques uniquement", soit fusionner avec la Fig. 9.

### 10. Dérivation de λ = 0.4 mm — à expliciter
- La valeur $\lambda = \ell_{fer,eq}/\mu_r = 0.4\,\text{mm}$ est utilisée sans montrer le calcul complet des longueurs de chemin dans le fer.
- **À faire :** ajouter un court calcul numérique montrant comment les longueurs de chemin dans le fer (colonnes centrale, latérales, traverses) sont sommées pour obtenir $\ell_{fer,eq}$, puis divisées par $\mu_r = 400$.

---

## Résumé des priorités

| # | Action | Impact | Effort |
|---|--------|--------|--------|
| 1 | Refaire le schéma magnétique (Fig. 3) | ★★★ | Moyen |
| 2 | Compléter la Table 6 (mesures AC) | ★★★ | Faible |
| 3 | Explication conceptuelle diagramme B-H | ★★★ | Faible |
| 4 | Commenter comparaison courbes B=f(x) | ★★ | Faible |
| 5 | Développer variation U2 vs fréquence | ★★ | Faible |
| 6 | Quantifier variation boucle avec entrefer | ★★ | Faible |
| 7 | Affiner explication écart R1 | ★ | Faible |
| 8 | Harmoniser numérotation des sections | ★ | Faible |
| 9 | Corriger légende Fig. 5 | ★ | Minimal |
| 10 | Dériver λ = 0.4 mm explicitement | ★ | Faible |