---
layout: section
transition: slide-left
number: "05"
eyebrow: v0.2.0
---

# Levens en Game Over

Botsen mag, maar niet eindeloos.

---

## Wat we bouwen

- Player heeft 3 levens
- Botsing met een asteroide:
  - 1 leven eraf
  - Shake Camera
  - Deactivate and respawn Asteroid
  - Dialogue: You have … lives
- Game Over bij 0 levens

---

## 3 levens bij begin

- Selecteer Scene
- Bij On Init
- Add Event >> Variables >> Variable Set To Value
- Variable: Local 0 — hernoem naar Lives
- Value: 3

---

## Leven eraf bij botsing

- Selecteer Scene
- Bij On Player Hit >> Group 1 (= Collision Group van Asteroid 1)
- Add Event >> Variables >> Variable Decrement by 1
- Variable: Lives

---

## Shake Camera

Add Event >> Camera >> Camera Shake

---

## Display lives

- Add Event >> Dialogue & Menus >> Display Dialogues
- Text: You have $Lives Lives

---

## Asteroid deactiveren

Probleem {.eyebrow.maple}

Als we de asteroide niet deactiveren, telt één botsing meerdere keren.

Oplossing {.eyebrow.sage}

- Selecteer Asteroid 1 >> On Hit >> Player
- Voeg deactivate en respawn code toe

---

## Game Over scene

- Bewaar game-over.png in de folder assets/backgrounds
- Druk op + bij Tools
- Selecteer Scene
- Klik in de Scene overview
- Klik op afbeelding bij background en selecteer de juiste
- Hernoem je scene naar Game Over (bovenaan op Scene 2 klikken)

---

## Game Over bij 0 levens

- Ga terug naar de Asteroid collision
- Add Event >> Control Flow >> If
- Condition: Lives
- == : 0

---

## Game Over scene laden

- Add Event (in het If block)
- Scene >> Change Scene
- Scene: Game Over
- Verplaats het respawnen naar het Else block

---
layout: section
eyebrow: v0.2.0
---

# Optimalisaties

Vijf dingen die nu nog niet kloppen.

---

## Player op het scherm

Probleem {.eyebrow.maple}

De speler staat nog in de Game Over scene.

Oplossing {.eyebrow.sage}

- Bij On Init
- Add Event >> Actor >> Hide All Sprites

---

## We geraken niet uit Game Over

Oplossing {.eyebrow.sage}

- Add Event >> Joypad Input >> Attach Script to Button
- Selecteer Start
- Add Event >> Scene >> Change Scene
- Scene: Scene 1 (of Game)
- X: 9
- Y: 16
- Direction: 🔼

---

## Actor blijft hidden

Oplossing {.eyebrow.sage}

In de Game scene bij On Init: Add Event >> Actor >> Show All Sprites

---

## Hit blijft verschijnen

Oplossing {.eyebrow.sage}

Dialogue Event verwijderen

---

## You have 0 lives is overbodig

Oplossing {.eyebrow.sage}

Verplaats de dialoog naar de Else sectie van het If-blok
