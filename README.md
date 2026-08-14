# Investir Long Terme — Infoproduit « Investir long terme, façon Buffett »

Infoproduit complet pour un solopreneur français : un guide PDF de niveau expert (~40 pages) sur l'investissement boursier long terme selon la méthode Buffett, vendu avec une séquence d'emails de 30 jours et un accompagnement mentor.

## 🎯 Positionnement

- **Narratif dominant** : la patience comme avantage (Buffett + la parabole du fermier taoïste).
- **Besoin servi** : éducation financière courte et dense — ni jargon, ni promesses magiques, ni « trading ».
- **Promesse** : « La patience est un avantage — investir comme Buffett sans être riche. »
- **Cible** : débutants et intermédiaires francophones, 25-55 ans, qui veulent un plan 10 ans sans y passer leurs journées.

## 📦 Livrables

```
investir-buffett/
├── index.html                  # Page de vente 3D immersive (Three.js)
├── chatbot.js                  # Widget chatbot autonome (leads + FAQ)
├── chatbot-config.js           # Config chatbot (FAQ, prix, EmailJS)
├── guide-investir-buffett.md   # LE GUIDE — 8 chapitres, ~11 700 mots (~40 pages A4)
├── emails/
│   ├── email-1.md  … email-10.md   # Séquence d'emails quotidiens (10 jours)
└── README.md
```

## 💰 Les 3 offres

| Offre | Prix | Contenu |
|---|---|---|
| **Le Guide** | 19 € | Guide PDF complet (40 pages, 8 chapitres, exemples chiffrés réels + exercices) |
| **Guide + 30 jours d'emails** | 39 € | Guide + 1 email par jour pendant 30 jours (un concept par jour, ton direct, CTA vers le guide) |
| **Pack Mentor** | 79 € | Guide + emails + 1 session de questions (réponse personnalisée sous 72 h) |

- Garantie 14 jours satisfait ou remboursé (affichée sur la page).
- Les 10 premiers emails de la séquence sont livrés dans `emails/` ; les 20 suivants suivent le même format (un concept par jour, CTA vers le guide).

## 🎨 Page de vente (index.html)

- **3D immersive** : scène WebGL (1800 particules + icosaèdres wireframe + anneau orbital), parallaxe souris sur 3 couches, scroll en profondeur, carte 3D inclinable au survol. Template de référence : `~/Documents/chatbot-kit/3d-immersion-template.html` (Three.js r152 via unpkg, build global).
- **Design sombre haut de gamme** : fond `#070b14`, dégradés cyan → violet (`#5eead4 → #38bdf8 → #a78bfa`), glassmorphism, glow au survol.
- **Structure** : hero → 8 chapitres → parabole du fermier → 3 offres (prix affichés) → formulaire EmailJS → FAQ (accordéon) → footer avec disclaimer.
- **Chatbot** : widget autonome (copié de `~/Documents/livrables/ai-course-builder/` et adapté), FAQ sur le produit, capture de leads, intégré à EmailJS.

### EmailJS (réel, pas de simulateur)

Le formulaire de commande et le chatbot envoient de vrais emails via EmailJS :

- `serviceId` : `service_cy1ytdb`
- `templateId` : `template_xpo58cv`
- `publicKey` : `8Pui4ZEqxW2jRVF7h`
- Payload envoyé : `{ site, name, email, question }` — le champ `question` contient l'offre choisie (+ la question de l'acheteur pour le Pack Mentor).

> ⚠️ Les identifiants EmailJS sont en clair dans `index.html` et `chatbot-config.js` : c'est le fonctionnement normal d'EmailJS (clé publique côté client). La protection anti-spam se règle dans le dashboard EmailJS (rate limits, reCAPTCHA si besoin).

## 📖 Le guide (guide-investir-buffett.md)

Niveau expert, ~40 pages, 8 chapitres. Chaque chapitre = leçon dense + exemple chiffré réel + exercice.

1. **La mentalité long terme** — le marché paie les patients (étude Dalbar, règle des 3 mentalités, contrat de patience).
2. **Le cercle de compétence** — investir dans ce qu'on comprend (test de l'ascenseur, règle des 5 minutes).
3. **La marge de sécurité** — acheter 1 € d'actif à 60 centimes (M. Marché, 3 méthodes d'évaluation).
4. **Lire une entreprise en 30 min** — check-list en 6 questions + exemple réel L'Oréal 2023.
5. **L'effet composé** — règle de 72, la crosse de hockey, les 3 ennemis (frais, impôts, inflation), l'exemple des jumeaux.
6. **Ignorer le bruit** — les 5 bruits et leurs antidotes, l'exemple de mars 2020 (écart de 40 000 €).
7. **La patience du fermier** — la parabole taoïste, les 4 saisons du marché, traverser 2000-2024 sans vendre.
8. **Le plan 10 ans** — architecture en 5 étages, enveloppes fiscales françaises (PEA / assurance-vie / CTO), calendrier année par année, 5 règles d'or, plan de 300 €/mois chiffré.

+ Conclusion, glossaire (20 termes), 10 chiffres à retenir, ressources gratuites.

## ✉️ La séquence emails (emails/)

10 emails quotidiens, ton direct, ~3 minutes de lecture chacun, CTA vers le guide à chaque fois :

1. La patience est un avantage · 2. L'effet composé · 3. Le cercle de compétence · 4. La marge de sécurité · 5. Lire une entreprise en 30 min · 6. Ignorer le bruit · 7. La patience du fermier · 8. Les frais, l'ennemi invisible · 9. Le coût de l'attente · 10. Le plan 10 ans (CTA final)

Chaque email inclut l'objet, le corps, le CTA et le P.S. de désinscription (conformité RGPD de bon aloi).

## 🚀 Déploiement

Page 100 % statique (HTML + JS + CDN), aucun backend :

```bash
# Hébergement local
cd ~/Documents/livrables/investir-buffett
python3 -m http.server 8080

# Ou GitHub Pages / Netlify / Vercel : pousser le dossier tel quel
```

**Ne pas publier sur GitHub** tant que la décision n'est pas prise (directive du client : pas de publication sans validation).

## ✅ Checklist de qualité

- [x] Orthographe française vérifiée
- [x] Design sombre haut de gamme (#070b14, cyan/violet)
- [x] Prix affichés (19 € / 39 € / 79 €)
- [x] EmailJS réel configuré (serviceId / templateId / publicKey)
- [x] Zéro simulateur (formulaire + chatbot envoient de vrais emails)
- [x] 3D WebGL fonctionnelle (testée navigateur : WebGL OK, 0 erreur JS)
- [x] Français direct, ton vendeur honnête (pas de promesses magiques)
