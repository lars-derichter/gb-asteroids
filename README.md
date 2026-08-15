# Maak een game voor de Fri3d badge met GB Studio

Code, voorbeelden en slides bij de workshop: “Maak een game voor de badge met GB
Studio” gegeven door [lars-derichter](https://github.com/lars-derichter) &
[wannesdr](https://github.com/wannesdr) op [Fri3d Camp](https://fri3d.be) 2024
en 2026.

- [Slides](https://lars-derichter.github.io/gb-asteroids/): slides bij de
  workshop
- [Releases](https://github.com/lars-derichter/gb-asteroids/releases): alle
  tussentijdse versies; als je vastloopt kan je de versie waaraan we werken
  downloaden en bekijken / verder aanpassen. (Nieuwere versies van GB Studio
  zetten het project bij het opslaan automatisch om naar het nieuwe
  projectformaat.)

## GB Studio

- https://www.gbstudio.dev/
- [Download GB Studio](https://chrismaltby.itch.io/gb-studio)
- [GB Studio documentatie](https://www.gbstudio.dev/docs)

## Sprites/Backgrounds/Palet om te downloaden

- Spaceship alternative 1: ![spaceship alt 1](downloads/spaceship_1.png)
- Spaceship alternative 2: ![spaceship alt 2](downloads/spaceship_2.png)
- Spaceship alternative 3: ![spaceship alt 3](downloads/spaceship_3.png)
- Spaceship alternative 4: ![spaceship alt 4](downloads/spaceship_4.png)
- Spaceship alternative 5: ![spaceship alt 5](downloads/spaceship_5.png)
- Asteroid alternative 1: ![asteroid 1](downloads/asteroid_1.png)
- Asteroid alternative 2: ![asteroid 2](downloads/asteroid_2.png)
- Laser: ![laser](downloads/laser.png)
- Heart: ![heart](downloads/heart.png)
- [Achtergrond](downloads/background.png)
- [Game Over](downloads/game-over.png)
- <a href="https://raw.githubusercontent.com/lars-derichter/gb-asteroids/refs/heads/master/downloads/gb-studio-piskel-sprites-palette.gpl" download>Piskel
  palet</a>

[All in one zip](downloads/all-in-one.zip)

## Game op de Fri3d badge krijgen

### In GB Studio

- Druk rechtsbovenaan op het export icoon
- Kies export ROM
- GB Studio opent de folder met bestanden
- Het .gb bestand bevat je gecompileerde spel

### SD-kaart

- Formatteer een micro SD kaart als FAT32 (kan op de badge zelf: Settings >>
  Format sdcard FAT32)
- Maak op de kaart de folder roms/gb en kopieer de rom erin
- Steek de kaart in de badge

_Zit er een SD-kaart in de badge, dan zie je enkel de spellen op de kaart — de
ROMs in het interne geheugen zijn dan onzichtbaar._

---

## Met de web-ide

- Verbind de badge met de laptop via USB-C
- Ga naar de Fri3d IDE: https://fri3dcamp.github.io/Fri3d-IDE/
- Connect Device (juiste poort selecteren)
- (Op mac moet je soms nog een driver installeren en toestel herstarten:
  https://www.wch-ic.com/downloads/CH34XSER_MAC_ZIP.html (het is de blauwe
  knop))
- Ga naar de File Manager
- Open roms >> gb (of roms >> gb >> homebrew)
- Sleep je rom hierin

## Eventuele uitbreidingen / volgende stappen

### Leventjes met 1 actor weergeven

- [Basics: Creating a HUD | GB Studio Central](https://gbstudiocentral.com/tips/basics-creating-a-hud/)
- [GB Studio - UI Health System - Zelda Combat | Robert Doman Video Tutorial](https://youtu.be/Lgk2CtUUjzY)
- Tip: sinds GB Studio 4.1 kan je met het `Draw Text` event tekst (score,
  levens) rechtstreeks op de achtergrond of overlay tekenen, zonder actors

### Score weergeven in HUD

- [How to make a HUD UI in GB Studio (this is a game changer!) | Robert Doman Video Tutorial](https://youtu.be/9lL1Ze6Ngg8)
- [How to make an overlay HUD with GBVM, part one | GB Studio Lab](https://gbstudiolab.neocities.org/guides/gbvm-overlay-hud)
  & [part two](https://gbstudiolab.neocities.org/guides/gbvm-overlay-hud-2)
- [Vertical Scrolling Shooter Part 10: HUD | codePetersen Video Tutorial](https://www.youtube.com/watch?v=WIyzGxExmgs)

### Meer kleuren met Color Mode

Voor GameBoy Color en Super GameBoy is er een colormode waarbij je verschillende
sprites en backgrounds elk met hun eigen kleurenpalet kan laten werken om zo
meer kleuren te gebruiken.

- [Settings | GB Studio documentatie](https://www.gbstudio.dev/docs/settings/) &
  [Palettes | GB Studio documentatie](https://www.gbstudio.dev/docs/assets/palettes/)
- [Game Boy Color Modes | GB Studio Central](https://gbstudiocentral.com/tips/game-boy-color-modes/)
- [Development Workflow – Chapter 9: Creating a Color Palette (Part 1) | GB Studio Central](https://gbstudiocentral.com/tips/dwf-c9-creating-a-color-palette-part-1/)
  &
  [Development Workflow – Chapter 9: Creating a Color Palette (Part 2) | GB Studio Central](https://gbstudiocentral.com/tips/dwf-c9-creating-a-color-palette-part-2/)

### Sound effects en muziek

- [Music | GB Studio documentation](https://www.gbstudio.dev/docs/assets/music/)
- [Sound effects | GB Studio documentation](https://www.gbstudio.dev/docs/assets/sound-effects)
- [GBS Music](https://music.gbstudio.dev/): de officiële GB Studio music editor
  als web app — componeren in de browser, ook op tablet of telefoon
- [GB Studio - Music Tutorial Intro | Robert Doman Video Tutorial](https://youtu.be/cLlD6lHdKxs)
- [GB Studio Music Editor Tutorial | Yogi (Tronimal) Video Tutorial](https://youtu.be/WNtTF7jf4WE)
  (gemaakt met GB Studio 3.1; de music editor is in 4.3 grondig vernieuwd)
- [Vertical Scrolling Shooter Part 11: Making Music & Adding Sound Effects | codePetersen Video Tutorial](https://www.youtube.com/watch?v=s7rVoMM42ks)

### Betere random

- [When Random Is NOT Random | GB Studio Central](https://gbstudiocentral.com/tips/when-random-is-not-random/)

### Verder bouwen aan een shoot-'em-up

- [How to make a Game Boy SHMUP with GB Studio without losing your mind | GB Studio Central](https://gbstudiocentral.com/tips/how-to-make-a-game-boy-shmup-with-gb-studio-without-losing-your-mind/):
  over de limieten van projectiles en actors, en hoe je er omheen werkt
- [GB Studio Tutorial: Vertical Scrolling Shooter | codePetersen](https://www.youtube.com/watch?v=zCjQOwIdCN0):
  11-delige videoreeks (GB Studio 4) die een volledige verticale shooter bouwt,
  met Piskel en Tiled

## Tutorials en HowTos

- [GB Studio Central](https://gbstudiocentral.com/): archief met 300+ artikels
  (sinds mei 2026 verschijnen er geen nieuwe, de site blijft online)
- [Robert Doman | Youtube](https://www.youtube.com/@RobertDoman)
- [codePetersen | Youtube](https://www.youtube.com/@codepetersen)

## Extra tools

### Piskel om pixel art te maken

- https://www.piskelapp.com/
- [GB Studio kleurenpalet voor Piskel](downloads/gb-studio-piskel-sprites-palette-ca735a4ca7c2924dc00e3dc698186e9f.gpl)

### Tiled map editor om backgrounds te maken

- https://www.mapeditor.org/
- Gebruik voor GB Studio:
  [Vertical Scrolling Shooter Part 4: TileMaps & Levels | codePetersen Video Tutorial](https://www.youtube.com/watch?v=BhUIvzQ_pY8)

## Dankwoord

Dank aan Tom Van Braeckel om Retro-Go te porten naar de badge en om ons attent
te maken op de mogelijkheid om met GB Studio spelletjes hiervoor te maken.
