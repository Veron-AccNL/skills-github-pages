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

<ul id="toolkit-files">
  <li>Loading...</li>
</ul>

<script>
  fetch('https://api.github.com/repos/Veron-AccNL/skills-github-pages/contents/toolkit')
    .then(r => r.json())
    .then(files => {
      const list = document.getElementById('toolkit-files');
      list.innerHTML = '';
      files.forEach(file => {
        if (file.type === 'file') {
          list.innerHTML += `
            <li>
              <a href="${file.download_url}" download>${file.name}</a>
              <small>(${(file.size / 1024).toFixed(1)} KB)</small>
            </li>`;
        }
      });
    })
    .catch(() => {
      document.getElementById('toolkit-files').innerHTML = '<li>Could not load files.</li>';
    });
</script>
