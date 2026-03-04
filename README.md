# 🔐 ZIP Vault

> Gestionnaire de protection ZIP — chiffrement AES-256 natif, 100% dans le navigateur.

![HTML](https://img.shields.io/badge/HTML-Single%20File-orange?style=flat-square&logo=html5)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla%20%2B%20React-yellow?style=flat-square&logo=javascript)
![zip.js](https://img.shields.io/badge/zip.js-2.8.22-blue?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Privacy](https://img.shields.io/badge/Privacy-100%25%20Local-brightgreen?style=flat-square)

---

## ✨ Fonctionnalités

| Fonctionnalité | Description |
|---|---|
| 🔒 **Protéger un ZIP** | Importez un `.zip` existant et ajoutez un mot de passe AES-256 ou ZipCrypto |
| 📁 **Créer un dossier** | Générez un ZIP chiffré vide ou depuis un dossier entier de votre machine |
| 🔑 **Modifier / Supprimer** | Changez ou supprimez la protection d'un ZIP existant |
| ⚡ **100% local** | Aucune donnée ne quitte votre navigateur — zéro serveur, zéro upload |
| 📦 **ZIP standard** | Fichiers compatibles avec 7-Zip, WinRAR, macOS et `unzip -P` |

---

## 🚀 Utilisation

**Aucune installation requise.** Téléchargez le fichier HTML et ouvrez-le dans votre navigateur.

```bash
# Cloner le dépôt
git clone https://github.com/votre-username/zip-vault.git

# Ouvrir l'application
open zip-vault.html   # macOS
xdg-open zip-vault.html  # Linux
start zip-vault.html  # Windows
```

Ou utilisez directement la **[démo en ligne](#)** *(GitHub Pages)*.

---

## 🔐 Chiffrement

ZIP Vault utilise **[@zip.js/zip.js](https://gildas-lormeau.github.io/zip.js/)** pour produire de vrais fichiers ZIP chiffrés selon les standards :

### AES-256 *(recommandé)*
- Chiffrement fort, clé 256 bits
- Compatible : **7-Zip**, **WinRAR**, **macOS Archive Utility**, **`unzip -P`**
- Standard industriel (WinZip AES Extension)

### ZipCrypto *(compatibilité maximale)*
- Chiffrement traditionnel ZIP (PKWARE)
- Compatible : **Windows Explorer** (natif), tous les outils ZIP
- ⚠️ Chiffrement plus faible — à éviter pour des données sensibles

```bash
# Déchiffrer en ligne de commande (AES-256 via 7-Zip)
7z x archive.zip -pmotdepasse

# Déchiffrer (ZipCrypto via unzip)
unzip -P motdepasse archive.zip
```

---

## 📸 Aperçu

```
┌─────────────────────────────────────────┐
│  🔐 ZIP Vault                           │
│  Chiffrement ZIP natif — AES-256        │
├──────────┬──────────┬───────────────────┤
│ 🔒 Prot. │ 📁 Créer │ 🔑 Modifier       │
├──────────┴──────────┴───────────────────┤
│  [ Déposez votre fichier ZIP ici ]      │
│                                         │
│  Type de chiffrement                    │
│  ┌ AES-256 ✓ ┐  ┌ ZipCrypto ┐         │
│  └───────────┘  └───────────┘          │
│                                         │
│  Mot de passe : ••••••••  [Excellent]   │
│  Confirmer    : ••••••••               │
│                                         │
│  [ 🔒 Chiffrer et télécharger ]        │
└─────────────────────────────────────────┘
```

---

## 🛠️ Stack technique

- **[React 18](https://react.dev/)** — UI déclarative (via CDN, transpilé par Babel)
- **[@zip.js/zip.js 2.8.22](https://gildas-lormeau.github.io/zip.js/)** — Chiffrement ZIP natif AES-256 & ZipCrypto (inliné dans le HTML)
- **Babel Standalone** — Transpilation JSX côté navigateur
- **Web API natives** — `File`, `Blob`, `ArrayBuffer`, `URL.createObjectURL`

> **Architecture** : application 100% statique, fichier HTML unique auto-suffisant (~170 KB). Aucun build step, aucun serveur, aucune dépendance npm à installer.

---

## 📋 Compatibilité

| Outil | AES-256 | ZipCrypto |
|---|:---:|:---:|
| 7-Zip | ✅ | ✅ |
| WinRAR | ✅ | ✅ |
| macOS Archive Utility | ✅ | ✅ |
| Windows Explorer (natif) | ⚠️ Win 11 | ✅ |
| `unzip` (Linux/macOS) | ✅ (via p7zip) | ✅ |
| `7z` CLI | ✅ | ✅ |

---

## 🔒 Sécurité & vie privée

- **Aucune donnée transmise** — tout le traitement est effectué localement dans le navigateur
- **Aucun cookie, aucun tracker, aucun analytics**
- Le code source est entièrement auditable (fichier HTML unique)
- La robustesse du chiffrement dépend de la **force de votre mot de passe**

> ⚠️ ZIP Vault ne stocke jamais vos mots de passe. Si vous perdez votre mot de passe, les données sont irrécupérables.

---

## 🤝 Contribution

Les contributions sont les bienvenues !

```bash
# Fork + clone
git clone https://github.com/votre-username/zip-vault.git

# Modifier app.html ou app.jsx
# Rebuilder avec le script Python inclus
python3 build.py

# Soumettre une Pull Request
```

**Idées d'améliorations :**
- [ ] Support drag & drop de dossiers entiers
- [ ] Prévisualisation du contenu avant téléchargement
- [ ] Mode sombre / clair
- [ ] Internationalisation (EN, DE, ES…)
- [ ] PWA (Progressive Web App) pour utilisation hors ligne

---

## 📄 Licence

MIT © 2025 — Libre d'utilisation, de modification et de distribution.

---

<div align="center">
  <sub>Construit avec ❤️ · Propulsé par <a href="https://gildas-lormeau.github.io/zip.js/">zip.js</a> · Aucune donnée collectée</sub>
</div>
