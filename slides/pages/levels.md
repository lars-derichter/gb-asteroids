---
layout: section
transition: slide-left
number: "07"
eyebrow: v0.4.0
---

# Levels

Hoe hoger de score, hoe lastiger het wordt.

---

## Wat we bouwen

- Snellere asteroide
- Extra asteroides

---

## Plaats levelcode

- Alle code in verband met levels hoort in de On Update routine van een actor. Meest logische keuze: Asteroid 1
- We zullen meerdere levels hebben, afhankelijk van de Score — Switch is hier geschikt voor
- Bij Asteroid 1 >> On Update: Add Event >> Control Flow >> Switch
- Variable: Score

---

## Level 2: asteroide versnellen

- Na 4 rake hits (Score: 400) versnellen we
- Eerste When: Value: 400
  - Add Event >> Set Actor Movement Speed
  - Actor: Self (Asteroid 1)
  - Speed: Speed 1

---

## Level 3: extra asteroide

- Copy-Paste Asteroid 1
- Hernoem naar Asteroid 2
- We moeten een nieuwe variabele Asteroid2_X maken en overal aanpassen in de code voor Asy-teroid 2
- Sprite Sheet eventueel aanpassen
- Switch statement met Score verwijderen (alle level stuff blijft op Asteroid 1)

---

## Extra asteroide deactiveren en activeren

- Scene >> On Init: Actor deactiveren (je weet hoe)
- In het Switch statement bij Asteroid 1 (On Update):
  - 2de When: 700
  - Add Event >> Actor >> Activate Actor
  - Actor: Asteroid 2

---

## Extra levels

- Je kan Switch waarden bijmaken
  - Je kan één of meerdere asteroides bijmaken
  - Je kan één of meer asteroides versnellen
