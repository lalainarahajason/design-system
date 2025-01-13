## 1. Comprendre l’échelle typographique
Une échelle typographique est un système hiérarchique de tailles de texte basé sur des proportions cohérentes, aidant à établir une hiérarchie visuelle dans votre application. Cela inclut les titres, sous-titres, corps de texte, annotations, etc.

Pourquoi une échelle ?
- Assure une lecture fluide.
- Renforce l'identité visuelle.
- Améliore l'expérience utilisateur en guidant l'œil.

---

## 2. Choisir un ratio typographique
Le ratio détermine la différence entre les tailles successives. Voici quelques ratios courants :
- Ratio mineur (1.2 – 1.25) : Pour des applications sobres et professionnelles.
- Ratio classique (1.3 – 1.414) : Pour une hiérarchie modérée.
- Ratio large (1.5 – 1.618) : Idéal pour des designs audacieux avec de grandes différences entre les titres et le corps.

Exemple avec un ratio 1.25 (taille de base = 16px) :
- h1 : 16px × 1.25⁴ ≈ 31px
- h2 : 16px × 1.25³ ≈ 25px
- h3 : 16px × 1.25² ≈ 20px
- Corps : 16px
- Légende : 16px ÷ 1.25 ≈ 13px

---

## 3. Définir les styles typographiques
Voici une structure typique pour une application :
| Rang         | Nom          | Taille (px) | Poids   | Utilisation                        |
|--------------|--------------|-------------|---------|------------------------------------|
| h1           | Titre 1      | 32px        | 700     | Titre principal de page.           |
| h2           | Titre 2      | 24px        | 600     | Sous-titres importants.            |
| h3           | Titre 3      | 20px        | 500     | Sous-sections ou éléments clés.    |
| h4           | Titre 4      | 18px        | 500     | Sous-sections ou points de détail. |
| h5           | Titre 5      | 16px        | 500     | Titres mineurs, listes détaillées. |
| Body         | Corps        | 16px        | 400     | Texte principal.                   |
| Caption      | Légende      | 14px        | 400     | Notes, instructions secondaires.   |

---

## 4. Configurer dans le CSS ou Tailwind
### En CSS :
:root {
  --font-size-base: 16px;
  --font-scale: 1.25;
  --font-size-h1: calc(var(--font-size-base) * var(--font-scale) * var(--font-scale) * var(--font-scale));
  --font-size-h2: calc(var(--font-size-base) * var(--font-scale) * var(--font-scale));
  --font-size-h3: calc(var(--font-size-base) * var(--font-scale));
  --font-size-h4: calc(var(--font-size-base) * 0.875); /* Ajustement à 18px */
  --font-size-h5: var(--font-size-base); /* Identique à la taille du corps */
  --font-size-caption: calc(var(--font-size-base) / var(--font-scale));
}

h1 { font-size: var(--font-size-h1); font-weight: 700; }
h2 { font-size: var(--font-size-h2); font-weight: 600; }
h3 { font-size: var(--font-size-h3); font-weight: 500; }
h4 { font-size: var(--font-size-h4); font-weight: 500; }
h5 { font-size: var(--font-size-h5); font-weight: 500; }

### Avec Tailwind CSS :
module.exports = {
  theme: {
    extend: {
      fontSize: {
        h1: ['32px', { lineHeight: '40px', fontWeight: '700' }],
        h2: ['24px', { lineHeight: '32px', fontWeight: '600' }],
        h3: ['20px', { lineHeight: '28px', fontWeight: '500' }],
        h4: ['18px', { lineHeight: '24px', fontWeight: '500' }],
        h5: ['16px', { lineHeight: '24px', fontWeight: '500' }],
        body: ['16px', { lineHeight: '24px', fontWeight: '400' }],
        caption: ['14px', { lineHeight: '20px', fontWeight: '400' }],
      },
    },
  },
};
