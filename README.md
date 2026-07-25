# 🏠 3DHuisje

<img width="50%" height="100%" alt="example_arnhem3d" src="https://github.com/user-attachments/assets/7d8fd895-27fa-4430-82a6-8b4a9d17f359" />



Inspect any Dutch building in 3D with per-wall/surface measurements coming from [3DBAG](https://3dbag.nl).

**3DHuisje** is a single-file, unofficial viewer for [3DBAG](https://3dbag.nl) data. Paste a
building ID (or load a CityJSON file), click a wall, and see its area, height, width, and
orientation. No installation required.

## Features

- **Fetch by ID** : Enter a BAG identifier (e.g. `NL.IMBAG.Pand.0106100000003786`) and the
  building is loaded directly from the [3DBAG API](https://api.3dbag.nl).
  
- **Or load a file** supports plain CityJSON (tiles from the
  [3DBAG download page](https://3dbag.nl/en/download)), CityJSONSeq (`.jsonl`), and the
  CityJSONFeature responses returned by the API.
  
- **Per-surface measurements** every wall, roof plane, and ground surface is listed with
  its area (m²), height (m), width (m), and azimuth (° from North).

## Usage

- **Hosted:** just visit the GitHub Pages URL.
- **Locally:** run `python3 -m http.server 8000` in this folder and open
  `http://localhost:8000/`.

Loading a downloaded file works in both cases.

### Where to find a building ID

<img width="75%" height="100%" alt="example_arnhem" src="https://github.com/user-attachments/assets/d0cce167-e727-403b-89bb-cb1cb5bb603d" />

Open the [3DBAG viewer](https://3dbag.nl), click a building, and copy the **full** `identificatie`
attribute (e.g., `NL.IMBAG.Pand.0202100000253372`).

## Notes & limitations

- 3DBAG models are reconstructed from aerial LiDAR: surfaces are approximations, and small
  walls or roof fragments (a few cm²) are reconstruction artifacts, not real features.
- Surface types (wall / roof / ground) come from 3DBAG's own semantic classification.
  The numbering (*Wall 1*, *Wall 2*, …) carries no architectural meaning.

## Credits

- **Data:** [3DBAG](https://3dbag.nl) by the [3D geoinformation group, TU Delft](https://3d.bk.tudelft.nl/),
  licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). This project is not
  affiliated with or endorsed by TU Delft or the 3DBAG team.
  
- **Built with** [Claude](https://claude.ai) (Anthropic) and [Three.js](https://threejs.org).

## License

MIT — do whatever you like, attribution not required.
