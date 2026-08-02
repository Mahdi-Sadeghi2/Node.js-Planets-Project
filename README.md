# Node.js Planets Project

A simple Node.js application that reads NASA's Kepler exoplanet data and finds potentially habitable planets.

## What it does

The script streams and parses the `kepler_data.csv` file, then filters planets using scientific criteria for habitability:

- **Disposition**: Must be `CONFIRMED`
- **Insolation flux** (`koi_insol`): Between `0.36` and `1.11` (Earth-like stellar flux)
- **Planetary radius** (`koi_prad`): Less than `1.6` Earth radii

At the end it prints the names of the habitable planets and the total count.

## Requirements

- Node.js (v14 or higher recommended)
- `csv-parse` package

## Installation

```bash
npm install csv-parse


Make sure the file kepler_data.csv is in the same folder as index.js.
Usage
Bashnode index.js
Example output
text[
  'Kepler-22 b',
  'Kepler-62 f',
  ...
]
8 habitable planet found!


 Code Overview:

Part,Purpose
csv-parse,Parses the CSV stream into JavaScript objects
fs.createReadStream,Efficiently reads the large CSV file
isHabitablePlanet(),Filters planets using the scientific criteria
habitablePlanets array,Stores matching planets