---
title: Accessibility Toolkit
---
# Toolkit 2026 – Overzicht

## Doel

De Toolkit 2026 ondersteunt docenten bij het integreren van digitale toegankelijkheid in onderwijs. De inhoud is praktisch, direct toepasbaar en sluit aan op waarden zoals inclusie, privacy en duurzaamheid.

## Structuur van de toolkit

### 0. Algemeen

- Introductie en uitleg van de toolkit

### 1. Kennis

Doel: basiskennis opbouwen

- Presentaties
- Video’s
- Handleidingen en bronnen

### 2. Ervaringsopdrachten

Doel: bewustwording door ervaring

- Oefeningen zonder materialen
- Oefeningen met materialen (incl. bestel-links)
- Workshop-opzet

### 3. Collega’s overtuigen

Doel: draagvlak creëren

- Gespreksstarters
- Mini-activiteiten
- Argumenten-kaarten
- Tips voor teamaanpak

### 4. Integratie in curriculum

Doel: structurele inbedding in onderwijs

- Leeruitkomsten
- Checklists voor projecten
- Opdrachten en casussen
- Toetscriteria en rubrics

### 5. Roadmap voor docenten

Doel: stapsgewijze ontwikkeling

- Quick-scan en groeipad
- Concrete acties (nu, korte termijn)
- Focus op:
  - Basisbegrip
  - Lesontwerp
  - Teamadoptie
  - Borging

### 6. Community

Doel: ondersteuning en kennisdeling

- Teams-kanaal
- Train-de-trainer sessies

## Huidige status

- Kennis en ervaringsopdrachten grotendeels afgerond
- Integratie in curriculum deels open (leerdoelen, opdrachten, rubrics)
- Roadmap vereist verdere uitwerking

## Belangrijke aandachtspunten

- Vertaling naar Engels
- Publicatie en rechten (privacy, auteursrecht)
- Positionering (openbaar vs. gecontroleerde toegang)

## Publicatiestrategie

**Korte termijn**

- Beschikbaar via website op aanvraag

**Lange termijn**

- Volledig openbaar (na juridische check)

## Samenvatting

De toolkit is een vrijwel complete en direct inzetbare verzameling materialen waarmee docenten:

- bewustwording creëren
- kennis opbouwen
- toegankelijkheid integreren in onderwijs
- collega’s meenemen

Het vormt een sterke basis voor opschaling en verdere professionalisering van digitale toegankelijkheid binnen onderwijsinstellingen.

# Downloads
## Downloads

## Toolkit

<div id="toolkit"></div>

<script>
  const REPO = 'Veron-AccNL/skills-github-pages';

  fetch(`https://api.github.com/repos/${REPO}/git/trees/main?recursive=1`)
    .then(r => r.json())
    .then(async data => {

      // 1. Filter to files inside /toolkit and group by immediate subfolder
      const folders = {};
      data.tree
        .filter(item => item.type === 'blob' && item.path.startsWith(toolkit + '/'))
        .forEach(item => {
          const parts = item.path.slice(toolkit.length + 1).split('/');
          if (parts.length < 2) return; // skip root-level files
          const folder = parts[0];
          const filename = parts[1];
          if (!folders[folder]) folders[folder] = { text: null, files: [] };
          if (filename === 'text.md') {
            folders[folder].text = item.path;
          } else {
            folders[folder].files.push({ name: filename, path: item.path });
          }
        });

      // 2. Render each folder
      const container = document.getElementById('toolkit');

      for (const [folder, contents] of Object.entries(folders)) {
        const section = document.createElement('div');

        // Heading
        section.innerHTML = `<h3>${folder}</h3>`;

        // Fetch and render text.md if it exists
        if (contents.text) {
          const rawUrl = `https://raw.githubusercontent.com/${REPO}/main/${contents.text}`;
          const md = await fetch(rawUrl).then(r => r.text());
          const p = document.createElement('p');
          p.textContent = md;
          section.appendChild(p);
        }

        // File list (excluding text.md)
        if (contents.files.length > 0) {
          const ul = document.createElement('ul');
          contents.files.forEach(file => {
            const rawUrl = `https://raw.githubusercontent.com/${REPO}/main/${file.path}`;
            ul.innerHTML += `<li><a href="${rawUrl}" download>${file.name}</a></li>`;
          });
          section.appendChild(ul);
        }

        container.appendChild(section);
      }
    })
    .catch(() => {
      document.getElementById('toolkit').innerHTML = '<p>Could not load toolkit.</p>';
    });
</script>
