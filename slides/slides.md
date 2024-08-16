# Maak je eigen game met GB Studio

---

## Voorstellen

- Lars De Richter: lector graduaat Programmeren aan Thomas More Hogeschool<br />(SKW & Antwerpen)
- Wannes De Richter: leerling STEM aan Novaplus Antwerpen

===

## Installatie

- Download en installeer de versie van GB Studio voor jouw besturingssysteem: https://chrismaltby.itch.io/gb-studio.
- Deze tutorial is gemaakt met v4.0.2 en zou dust met alle 4.x versies moeten werken.

===

## Sample project

- Open GB Studio
- Kies new
- Verwijs bij Path naar je Desktop (of een andere makkelijke locatie)
- Project name: sample
- Template: het kleurrijke sample project
- Create project

---

![Sample project maken](images/sample-project.png)

---

<!-- .slide: data-background-image="images/gb-studio-overview.jpg" data-background-size="contain" -->

---

### Navigator

- linksboven
- laat je snel switchen tussen scenes en onderdelen

![Navigator](images/navigator.png)

---

### Scene overview

- centraal
- grafische weergave van je scenes en hun onderdelen

![Scene overview](images/scene-overview.png)

---

### Editor sidebar

- rechts
- instellingen van geselecteerd onderdeel

![Editor sidebar](images/editor-sidebar.png)

---

### Editor tools

- Dingen selecteren, toevoegen, verwijderen …

![Editor tools](images/editor-tools.png)

===

## v0.0.0

- default sprites
- speler beweegt enkel horizontaal
- speler kan schieten
- 1 asteroide:
  - respawnt op random plek wanneer onderaan
  - respawnt op random plek wanneer geraakt

---

### New, blank project

![Blank project](images/new-project.png)

---

### Test het spel

- Play button rechtsbovenaan
- Player is een pijl
- Kan in 4 richtingen bewegen

**Na elke verandering testen❗️**

---

### Player instellen

- Start position:
  - X: 9 : midden horizontaal (18 posities: 0 - 17; 0 helemaal links)
  - Y: 16 : onderaan (18 posities: 0 -17; 0 helemaal bovenaan)
- Direction: 🔼 (speler kijkt naar boven)

---

### Verticale beweging uitschakelen

- On Init (= bij het begin van de scene):
  - Add Event (= hoe je het spel dingen laat doen)
  - Joypad Input (we willen knoppen aanpassen)
  - Attach Script to button (we willen de functie van de knoppen aanpassen)
  - 🔼 en 🔽 selecteren
  - Override default button action aanduiden (we willen het normale gedrag aanpassen)
  - On press leeg laten (normaal zou je hier een actie zetten, maar we willen dat er niets gebeurt)

---

### A/B knoppen instellen

Nu willen we de A en B knoppen aanpassen: probeer zelf!

---

### Schietfunctie

- Druk op Add Event bij On Press
- Kies Actor
- Kies Launch Projectile
- Direction: Activeer enkel 🔼

---

### Asteroide toevoegen

- Druk op + bij Tools
- Kies Actor (dingen in je spel die iets doen zijn actors)
- Klik ergens bovenaan om de Actor te plaatsen
- Verander naam Actor 1 in Asteroid 1

---

### Asteroide laten bewegen

- On Update
- Add Event
- Actor Move Relative
- X: 0 (geen horizontale beweging)
- Y: 1 (verticaal één stap naar onder)
- Bovenaan Speed ½ (niet te snel beginnen)

---

### Random variabele maken

- probleem: Asteroide vertrekt telkens van dezelfde plek
- X-positie moet random getal tussen 0 en 17 worden:
  - On Init >> Add Event
  - Variable >> Math Functions
  - Variable: Local 0 >> hernoem naar Asteroid1_X (hover over de naam en ✎)
  - Value: Random
  - Min Value: 0; Max Value: 17

---

### Asteroide op random positie zetten

- Add Event
- Actor >> Set Actor Position
- Actor: Self
- X: $Asteroid1_X (eerst op # drukken)
- Y: 0

(je zal merken dat het niet helemaal random is, dat fixen we later misschien)

---

### Asteroide respwant wanneer onderaan

- Meten of Asteroide onderaan is:
  - On Update
  - Add Event >> Actor >> If Actor at Position
  - X: $Asteroid1_X (verandert niet); Y: 17 (onderste positie)
- If deel -> zelfde als Asteroide op Random positie zetten
- Else deel: Self Move Relative hierin slepen

---

### Asteroide respawnt wanneer geraakt

- On Hit >> Group 3 (= Collision Group van Projectile)
- Collision Group: 1 (= Collide With van Projectile)
- Add Event >> Display Dialogue:
  - Hit (of Geraakt of …)
- Add Event >> Actor >> Deactivate Actor
  - Actor: Self (Asteroid 1)

---

- Add Event >> Timer >> Wait
  - Duration: 0.5 (halve seconde wachten)
- Zelfde als Asteroide op Random positie zetten (tip gebruik copy event en paste event)
- Add Event >> Actor >> Activate Actor
  - - Actor: Self (Asteroid 1)

===

## v0.1.0

- betere afbeeldingen:
  - Player sprite
  - Asteroid sprite
  - Laser sprite
  - Background

---

### Sprites en spritesheets

- **sprite:**
  - kleine afbeelding in pixel art
  - spelers en actoren voorstellen in games
- **spritesheet:**
  - grotere afbeelding die alle statussen van de sprite bevat (bijv. vooraanzicht, achteraanzicht, zijaanzicht)

---

### Sprites in GB Studio

- png
- 16 x 16 pixels
- 3 kleuren + transparant (fluo groen)

![Sprite colors](images/sprite-colors.png)

---

### Spritesheets in GB Studio

- png
- 16n x 16 pixels (n = aantal sprites in sheet)

![Sprite sheet](images/sprite-sheet.png)

---

### Sprites en spritesheets maken

- image editor
- bijv. https://www.piskelapp.com/
- mini-demo (meer info: spreek Wannes straks aan)

---

### Sprites importeren

- Verplaats je sprites naar de subfolder assets/sprites van je project folder
- **Tip:** het folder icoon 📁 rechtsbovenaan GB Studio brengt je naar je project folder

---

### Sprites aanpassen

- Selecteer je scene
- Klik op afbeelding bij Player Sprite Sheet en kies je afbeelding
- Klik op Sprite Sheet bij Launch Projectile en kies je afbeelding
- Selecteer de Asteroid 1 actor
- Klik op afbeelding bij Sprite Sheet en kies je afbeelding
-

---

### Achtergronden in GB Studio

- PNG van minimaal 160x144 pixels
- Achtergrond is opgedeeld in tiles van 8x8 pixels, die herhaald kunnen worden
- Maximaal 192 unieke tiles per scene (geheugenbesparing)

---
