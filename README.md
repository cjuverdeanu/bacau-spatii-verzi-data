# Registrul Spațiilor Verzi — Municipiul Bacău (Open Data)

Set de date deschise (JSON și GeoJSON) extras și georeferențiat de **Bacău Alert** pe baza fișelor PDF oficiale ale Registrului Local al Spațiilor Verzi publicate de Municipiul Bacău în anul 2024.

## Stadiu actualizare

- **Procent fișe procesate:** **89.0%** (`761` din `855` fișe din registru)
- **Ultima actualizare dataset:** `13.11.2026 14:55`
- **Suprafață totală în fișele procesate:** `379.54` ha
- **Arbori inventariați:** `70774` | **Arbuști:** `11737` | **Gard viu:** `125.83` km

> Procentul de acoperire crește pe măsură ce fișele rămase sunt calibrate și validate spațial. Fiecare actualizare din acest repository menționează explicit procentul curent în mesajul de commit.

## Structura fișierelor

| Fișier | Conținut | Dimensiune |
|---|---|---|
| [`data/spatii_verzi_catalog.json`](data/spatii_verzi_catalog.json) | KPI-uri globale și metadatele tuturor fișelor (fără geometrii) | `2.84 MB` |
| [`data/verde_data.min.json`](data/verde_data.min.json) | Dataset complet într-un singur fișier JSON minificat (atribute + toate geometriile) | `51.49 MB` |
| [`data/geojson/spatii_verzi.geojson`](data/geojson/spatii_verzi.geojson) | Poligoanele zonelor verzi extrase (WGS84 / EPSG:4326) | `19.74 MB` |
| [`data/geojson/limite.geojson`](data/geojson/limite.geojson) | Limitele perimetrale ale fiecărei fișe (WGS84 / EPSG:4326) | `16.51 MB` |
| [`data/geojson/arbori.geojson`](data/geojson/arbori.geojson) | Punctele arborilor vectoriali cu atributele din fișe (WGS84 / EPSG:4326) | `34.06 MB` |
| [`data/geojson/cladiri.geojson`](data/geojson/cladiri.geojson) | Amprentele clădirilor din schițele fișelor (WGS84 / EPSG:4326) | `1.78 MB` |

## Exemple rapide de utilizare

### Python
```python
import json

with open("data/spatii_verzi_catalog.json", encoding="utf-8") as f:
    catalog = json.load(f)

print(catalog["kpi"]["procent_acoperire"], len(catalog["spatii"]))
```

### QGIS
Încărcați direct oricare dintre fișierele din `data/geojson/` prin *Layer → Add Layer → Add Vector Layer...* (sistem de coordonate `EPSG:4326`).

## Licență și sursă

- **Sursa primară:** fișele PDF publice ale Registrului Local al Spațiilor Verzi — Municipiul Bacău (2024), legate prin câmpul `pdf_url` pentru fiecare fișă.
- **Licență:** [CC BY 4.0](LICENSE) — liber de utilizat și adaptat cu atribuirea sursei (`Municipiul Bacău / Bacău Alert`).
