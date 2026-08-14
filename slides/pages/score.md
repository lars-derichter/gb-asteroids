---
layout: section
transition: slide-left
number: "06"
eyebrow: v0.3.0
---

# Hartjes en score

Levens tonen op het scherm, en punten bijhouden.

---

## Wat we bouwen

- Levens tonen
- Score bijhouden en tonen bij Game Over

---

## Heart 1 op scherm toevoegen

- Add Actor (rechtsbovenaan)
- X: 18; Y: 1
- Pin to screen: 📌
- Hernoem naar Heart 1
- Zet image naar hartje (eerst in sprites folder plaatsen)

---

## Heart 2 & 3

- Copy Paste (telkens wat meer naar links)
- Pas namen aan: Heart 2 en Heart 3

---

## Hartjes verwijderen wanneer geraakt

- Kan met 2 extra If-blokken
- Maar properder: Switch (we doen andere dingen voor verschillende waarden van 1 variabele)
- Bij On Player Hit: Add Event >> Control Flow >> Switch
- Variable: $Lives
- Number of options: 2
- Pas Whens aan: 2, 1

---

## De Switch invullen

- **When 2:** Add Event >> Actor >> Hide Actor — Actor: Heart 3
- **When 1:** denk zelf eens na
- **Else:** sleep het event van het If-blok naar hier (Game Over)

<hr class="ldr-rule-maple" />

_Verwijder daarna het oorspronkelijke If-event: we zien onze levens nu met de hartjes._

---

## Score bijhouden

Een nieuwe globale variabele maken, want op verschillende plekken nodig (verschillende actoren en scenes)

---

## Score bij begin op 0 zetten

- Game Scene >> On Init >> Add Event
- Variables >> Variable Set To Value
- Variable 2 hernoemen naar Score
- Value: 0
- (zet dit na de variabele Lives, netjes bij elkaar)

---

## Score optellen

- Bij Asteroid 1 >> On Hit >> Group 3
- Add Event >> Variables >> Math Functions
- Variable: Score
- Operation: Add
- Value: 100
- Sleep dit event tot net na Deactivate Self

---

## Score weergeven

- Bij Game Over Scene >> On Init
- Add Event >> Dialogue & Menus >> Display Dialogue
- Text:  
  Your Score  
  $Score

---

## Eventuele uitbreidingen

- Leventjes in 1 Actor met Spritesheet
- Score weergeven in de scene met een HUD

<hr class="ldr-rule-maple" />

_Zie de README voor links naar tutorials._
