---
layout: section
transition: slide-left
number: "03"
eyebrow: v0.0.0
---

# Het basisspel

Een speler die schiet, en één asteroide die blijft terugkomen.

---

## Wat we bouwen

- Default sprites
- Speler beweegt enkel horizontaal
- Speler kan schieten
- 1 asteroide:
  - respawnt op random plek wanneer onderaan
  - respawnt op random plek wanneer geraakt

---
layout: image-full
image: /new-project.png
fit: contain
eyebrow: Stap 1
---

### New, blank project

---
layout: image-full
image: /no-scene.png
fit: contain
eyebrow: Er is nog geen scene
---

### No scene

---
layout: image-full
image: /plus-scene.png
fit: contain
eyebrow: "+ >> Scene"
---

### Scene toevoegen

---
layout: image-full
image: /place-scene.png
fit: contain
eyebrow: "Klik ergens in de scene overview"
---

### Scene plaatsen

---

## Test het spel

- Play button rechtsbovenaan
- Player is een pijl
- Kan in 4 richtingen bewegen

<hr class="ldr-rule-maple" />

_Test na elke verandering._

---

## Player instellen

- (Als klikken niet lukt om te selecteren, beetje verslepen)
- Start position:
  - X: 9 — midden horizontaal (20 posities: 0 - 19; 0 helemaal links)
  - Y: 16 — onderaan (18 posities: 0 - 17; 0 helemaal bovenaan)
- Direction: 🔼 (speler kijkt naar boven, bij beweging kijkt naar opzij)

---

## Verticale beweging uitschakelen

Bij **On Init** (= bij het begin van de scene):

- Add Event (= hoe je het spel dingen laat doen)
- Joypad Input (we willen knoppen aanpassen)
- Attach Script to button (we willen de functie van de knoppen aanpassen)
- 🔼 en 🔽 selecteren
- Override default button action aanduiden (we willen het normale gedrag aanpassen)
- On press leeg laten (normaal zou je hier een actie zetten, maar we willen dat er niets gebeurt)

---

## A/B knoppen instellen

Nu willen we de A en B knoppen aanpassen.

<hr class="ldr-rule-maple" />

_Probeer zelf._

---

## Schietfunctie

- Druk op Add Event bij On Press
- Kies Actor
- Kies Launch Projectile
- Source >> Direction: activeer enkel 🔼

---

## Asteroide toevoegen

- Druk op + bij Tools
- Kies Actor (dingen in je spel die iets doen zijn actors)
- Klik ergens bovenaan om de Actor te plaatsen
- Verander naam Actor 1 in Asteroid 1

---

## Asteroide laten bewegen

- On Update
- Add Event
- Actor Move Relative
- X: 0 (geen horizontale beweging)
- Y: 1 (verticaal één stap naar onder)
- Bovenaan Speed ½ (niet te snel beginnen)

---

## Random variabele maken

Probleem {.eyebrow.maple}

De asteroide vertrekt telkens van dezelfde plek. De X-positie moet een random getal tussen 0 en 17 worden.

Oplossing {.eyebrow.sage}

- On Init >> Add Event
- Variable >> Math Functions
- Variable: Global 0 >> hernoem naar Asteroid1_X (hover over de naam en ✎)
- Value: Random
- Min Value: 0; Max Value: 17

---

## Asteroide op random positie zetten

- Add Event
- Actor >> Set Actor Position
- Actor: Self
- X: $Asteroid1_X (eerst op # drukken)
- Y: 0

<hr class="ldr-rule-maple" />

_Je zal merken dat het niet helemaal random is._

---

## Asteroide respawnt wanneer onderaan

- Meten of de asteroide onderaan is:
  - On Update
  - Add Event >> Actor >> If Actor at Position
  - X: Tile X (bij Property); Y: 17 (onderste positie)
- If deel: zelfde als asteroide op random positie zetten
- Else deel: Self Move Relative hierin slepen

---

## Asteroide respawnt wanneer geraakt

- Collision Group: 1 (= Collide With van Projectile)
- On Hit >> Group 3 (= Collision Group van Projectile)
- Add Event >> Display Dialogue:
  - Hit (of Geraakt of …)
- Add Event >> Actor >> Deactivate Actor
  - Actor: Self (Asteroid 1)

---

## Asteroide opnieuw activeren

- Add Event >> Timer >> Wait
  - Duration: 0.5 (halve seconde wachten)
- Zelfde als asteroide op random positie zetten (tip: gebruik copy event en paste event)
- Add Event >> Actor >> Activate Actor
  - Actor: Self (Asteroid 1)
