# QIBAR Center — Site vitrine

Site officiel de QIBAR Center, hébergé sur GitHub Pages.

**URL publique :** https://boozygit.github.io/qibar/
**Futur domaine :** https://qibar.com

---

## Structure du projet

```
qibar/
├── _quarto.yml          # Configuration Quarto
├── styles.css           # Charte graphique QIBAR
├── index.qmd            # Page d'accueil
├── services.qmd         # Page Services
├── about.qmd            # À propos
├── tarifs.qmd           # Tarifs
├── contact.qmd          # Contact
├── images/              # Logo, favicon, og image
│   ├── favicon.png
│   └── og.png
├── .github/
│   └── workflows/
│       └── deploy.yml   # Déploiement automatique
└── docs/                # Généré par quarto render (ne pas éditer)
```

---

## Mise en route locale

```bash
# 1. Cloner le dépôt
git clone https://github.com/boozygit/qibar.git
cd qibar

# 2. Prévisualiser en local
quarto preview

# 3. Générer et déployer
git add .
git commit -m "votre message"
git push
# → GitHub Actions lance automatiquement quarto render + deploy
```

---

## Déploiement GitHub Pages

1. Aller dans **Settings → Pages** du dépôt `qibar`
2. Source : **Deploy from a branch**
3. Branch : **gh-pages** · Folder : **/ (root)**
4. Sauvegarder

Le workflow `.github/workflows/deploy.yml` s'occupe du reste à chaque `git push`.

---

## Domaine personnalisé (quand qibar.com est acheté)

1. Acheter `qibar.com` sur Namecheap ou Gandi (~12$/an)
2. Ajouter un fichier `CNAME` à la racine du repo contenant : `qibar.com`
3. Dans les DNS de votre registrar, ajouter :
   - Type A → 185.199.108.153
   - Type A → 185.199.109.153
   - Type A → 185.199.110.153
   - Type A → 185.199.111.153
   - Type CNAME → www → boozygit.github.io
4. Dans **Settings → Pages** → Custom domain → entrer `qibar.com`

---

## Newsletter (Brevo)

1. Créer un compte sur brevo.com
2. Créer une liste "QIBAR Blog Abonnés"
3. Créer un formulaire d'inscription → copier l'URL d'action
4. Dans `index.qmd`, remplacer `VOTRE_URL_BREVO` par cette URL

---

## Personnalisation à faire

- [ ] `_quarto.yml` → remplacer l'URL LinkedIn réelle
- [ ] `index.qmd` → mettre à jour les URLs des articles du blog
- [ ] `index.qmd` → remplacer les témoignages par des vrais (avec permission)
- [ ] `index.qmd` → remplacer `VOTRE_URL_BREVO` par l'URL Brevo réelle
- [ ] `images/` → ajouter favicon.png (512×512) et og.png (1200×630)
- [ ] `contact.qmd` → remplacer `VOTRE_ID_FORMSPREE` par votre ID Formspree
