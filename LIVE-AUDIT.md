# LIVE-AUDIT — VideoOVNI.fr
Date d’audit : 2026-09-17 (UTC+2). Méthodes : HTTP/curl, WebFetch, WebSearch, RDAP AFNIC, navigateur desktop 1280×800 + mobile CDP 390×844.

## Verdict technique en une phrase
Le site **n’est pas mort faute de contenus** : il est **quasi invisible**, avec un risque crawl (protection DDoS LWS/Anubis) et une jeunesse de domaine qui expliquent mieux les ~5 impressions / 7 j que « il manque des articles ».

## Disponibilité & hébergement
| Check | Résultat |
|---|---|
| `https://videoovni.fr/` | HTTP 200 observé (puis 403 Anubis après charge crawler) |
| `https://www.videoovni.fr/` | 301 → apex (confirmé curl) ; 403 Anubis vu navigateur |
| Hébergeur | LWS (RDAP + footer pages erreur) |
| Domaine | Enregistré **2026-05-02**, expire 2027-05-02 (RDAP nic.fr) — ~4,5 mois |
| Titulaire RDAP | Anonymisé |

## Indexation / crawl
| Check | Résultat |
|---|---|
| `robots.txt` | Présent, cohérent. Disallow admin/private/work/… ; Allow `/` pour Googlebot & majeurs. Bloque GPTBot/ClaudeBot/CCBot (training). Sitemap déclarés. |
| Sitemaps | Index OK. FR **143** `<loc>` ; EN ~110 ; ES/PT-BR/AR ~111–112. lastmod sept. 2026. |
| Contenu FR sitemap | ~93 articles, ~12 topics, + observatoire UAP, pages légales, pages TikTok |
| `site:videoovni.fr` (WebSearch) | **Aucun résultat utile** |
| Mentions web « videoovni.fr » | **Quasi nulles** hors le site lui-même |
| Baseline user | ~5 impressions Google / 7 jours, **0 clic** |
| Protection | **LWS Protection DDoS / Anubis 1.25** : challenge JS. Un UA `Googlebot/2.1` a reçu **403 + page challenge** depuis l’environnement d’audit. Même blocage après une série de requêtes sur articles. |

Implication : même avec sitemaps propres, un WAF qui challenge les bots peut **ralentir ou casser l’indexation**. À vérifier dans Search Console (crawl errors / « Soft 404 » / challenge pages). Ce n’est pas prouvé que Googlebot prod est bloqué en permanence, mais le signal est **rouge** et cohérent avec 5 impressions.

## SEO on-page (home)
- Title : `VIDEO OVNI — Vidéos OVNI, dossiers UAP et enquêtes`
- Meta description : présente, intention documentaire
- Canonical : `https://videoovni.fr/`
- hreflang : fr, en, es, pt-BR, ar, x-default
- Open Graph + JSON-LD : présents
- H1 : VIDEO OVNI
- Densité texte home : ~7–8k caractères visibles ; ticker « LIVE » très présent

## Contenu & architecture
- Positionnement éditorial affiché : dossiers sourcés, documents officiels, analyses prudentes (AARO, NASA, Pentagone, GEIPAN, cas historiques).
- Volume : corpus **déjà large** pour un site de 4 mois (dizaines de dossiers + observatoire PURSUE/AARO).
- `/web/videos.html` : hub **TikTok** (`@video.ovni`), pas une bibliothèque vidéo propriétaire.
- Multilingue (5 langues) **avant** traction FR : coût SEO élevé, autorité diluée.
- Analytics : `G-05T2GDY361` détecté. Pas de `ca-pub` AdSense visible sur la home au moment du scrape.

## UX (synthèse — détail dans `_ux-notes.md`)
- Home desktop : proposition de valeur claire, DA premium, trop de CTA/ticker.
- Différenciation vs YouTube **conceptuellement** claire (contexte + sources), **pas encore tangibilisée** dans le hero.
- Mobile : lisible, ticker/header/CTA à resserrer.
- Screenshots : `screenshots/home-desktop.png`, `screenshots/home-mobile.png`.

## Qualité / fraîcheur / intention
- Fraîcheur : contenus datés mai–août 2026 (PURSUE, actualité US) — frais.
- Intention mixte : informationnel long-form + actualité disclosure US + short TikTok.
- Risque éditorial noté UX : formulations parfois trop affirmatives vs promesse « on vérifie ».

## Diagnostic du problème #1
| Hypothèse | Statut |
|---|---|
| Technique pur (site down) | Non — home sert |
| Indexation / crawl / WAF | **Oui, contributeur majeur** |
| Contenu insuffisant | **Non** — volume déjà là |
| Demande nulle | Non — demande existe mais limitée / episodique |
| Autorité / backlinks / âge | **Oui — domaine neuf, zéro notoriété** |
| Positionnement | **Oui — « vidéo OVNI » = YouTube ; carte FR = CarteOvni/GEIPAN** |

**Problème #1 :** absence de découverte (autorité × âge × distribution) sur une intention déjà captée ailleurs, **aggravée** par un risque WAF/Anubis et un multilangue prématuré — pas un manque de pages.
