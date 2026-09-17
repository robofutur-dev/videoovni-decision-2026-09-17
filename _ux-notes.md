# Audit UX live — VIDEO OVNI

**Date d’observation :** 17 septembre 2026, 23:48–23:50 (UTC+2)  
**Viewport desktop :** 1280×800  
**Simulation mobile :** 390×844, via `Emulation.setDeviceMetricsOverride` (Chrome/CDP).  
**URLs :** `https://videoovni.fr/` chargé correctement. `https://www.videoovni.fr/` a renvoyé une page LWS Protection DDoS / HTTP 403, donc le redirect www n’a pas pu être confirmé.

## Findings UX (10 points)

1. **Proposition de valeur très lisible au-dessus de la ligne desktop :** “Ce que les images, les radars et les pilotes disent vraiment.” Le positionnement documentaire est compris immédiatement, soutenu par “Documents · vidéos · témoignages · auditions”.
2. **Impact visuel élevé mais hiérarchie chargée :** hero sombre, visuel David Grusch, ticker rouge animé et badge vidéo attirent tous l’œil simultanément. Le ticker peut concurrencer le message principal.
3. **CTA présents et variés :** “Lire les dossiers”, “Toutes les vidéos”, “Sources vérifiées”, suivi TikTok et dossier Nimitz. Bon choix d’entrées, mais trop de CTA primaires/secondaires dans le premier écran ; un CTA dominant aiderait la conversion.
4. **Navigation desktop minimale mais cohérente :** marque, Articles, recherche et langue. Les catégories structurantes (Vidéos, Sources, Méthodologie, Dossiers) sont surtout plus bas/footer ; elles gagneraient à être exposées directement dans la navigation principale.
5. **Architecture éditoriale riche :** articles, dossiers, thèmes, sources institutionnelles, lexique et méthodologie. Les sections “Dernières alertes”, “Dossiers incontournables”, “Références & lexique” et “Derniers dossiers” donnent de nombreux parcours, mais la profondeur de page est importante et peut diluer le chemin principal.
6. **Qualité perçue des contenus :** direction artistique premium (noir, rouge, cartes, typographie forte), images éditorialisées et labels de contenu. Les références Pentagon/AARO/NASA/Congrès et la méthode en 4 étapes renforcent la crédibilité perçue.
7. **Point de vigilance factuel/confiance :** certaines formulations de l’article Nimitz sont très affirmatives (“physique de l’impossible”, “aucune explication conventionnelle satisfaisante”). Les distinguer visuellement des faits sourcés, déclarations et hypothèses est essentiel pour ne pas affaiblir la promesse de vérification.
8. **Différenciation vs YouTube claire sur le fond :** le site vend une lecture contextualisée, des sources, des dossiers et une méthode, pas seulement un flux vidéo. Il devrait expliciter encore plus ce bénéfice dans le hero (“chaque vidéo contextualisée et sourcée”) pour rendre l’alternative à YouTube immédiatement tangible.
9. **Mobile observé :** le hero se réorganise bien en colonne et reste lisible ; les boutons sont assez grands. En revanche, le ticker horizontal est tronqué/visible en défilement, le header devient très compact, et plusieurs boutons côte à côte deviennent serrés : tester les libellés longs, le wrapping et les cibles tactiles sur petits écrans.
10. **Éléments mobiles à optimiser :** la vidéo apparaît avant le bloc éditorial, ce qui est engageant mais repousse le contexte ; le bouton flottant “Tic Tac · Rechercher” et le ticker persistent peuvent occuper une part notable du viewport. Prévoir une réduction/masquage au scroll et un état accessible au clavier/lecteur d’écran.

## Écrans observés / captures

- Desktop home (1280×800) : `/workspace/videoovni-decision/screenshots/home-desktop.png`
- Home simulée mobile (390×844) : `/workspace/videoovni-decision/screenshots/home-mobile.png`
- Page intérieure inspectée : article Nimitz 2004, avec sommaire, réponse factuelle, témoignages, vidéo FLIR1, sources et contenus liés. La capture dédiée de cette page n’a pas pu être sauvée : le navigateur a déchargé l’onglet sous pression mémoire puis le site a présenté LWS Protection DDoS/403 lors de la nouvelle ouverture.

## Recommandations prioritaires

- Réduire la concurrence visuelle du ticker et du widget flottant dans le premier écran.
- Exposer “Dossiers / Vidéos / Sources / Méthodologie” dans une navigation ou un menu clairement accessible.
- Choisir un CTA héros principal, puis reléguer TikTok et les entrées secondaires.
- Ajouter une convention visuelle persistante pour distinguer fait vérifié, déclaration, source et hypothèse.
- Tester le mobile à 320–390 px : ticker, boutons à deux colonnes, header et ordre vidéo/contexte.
