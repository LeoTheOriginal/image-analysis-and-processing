# Image Analysis and Processing

Laboratoria z przedmiotu **Analiza i przetwarzanie obrazów** — AGH, Informatyka Stosowana II st., semestr I.

## Struktura

```
notebooks/       # Notebooki Jupyter (laboratoria + raporty)
images/          # Obrazy wejściowe (jpg, png)
videos/          # Nagrania wejściowe (mov)
```

## Laboratoria

| Nr | Temat | Notebook |
|----|-------|----------|
| 1 | Wprowadzenie do OpenCV | `lab_1.ipynb` |
| 2 | Reprezentacja obrazu i koloru (RGB, HSV, histogramy) | `lab_2.ipynb` |
| 3 | Progowanie i segmentacja (Otsu, k-means) | `lab_3.ipynb` |
| 4 | Filtracja obrazu (blur, median, Gauss, Sobel) | `lab_4.ipynb` |
| 5 | Wykrywanie krawędzi (Laplace, Canny, Hough) | `lab_5.ipynb` |
| 6 | Analiza sekwencji wideo | `lab_6.ipynb` |
| 7 | Detekcja cech i rozpoznawanie twarzy | `lab_7.ipynb` |
| 8 | Deep learning (DeepFace) | `lab_8.ipynb` |

## Raporty

| Raport | Zakres |
|--------|--------|
| `raport_1.ipynb` | Laboratoria 2–4 |
| `raport_2.ipynb` | Laboratoria 5–8 |

## Uruchomienie

```bash
python -m venv .venv
.venv\Scripts\activate      # Windows
pip install -r requirements.txt
jupyter notebook notebooks/
```

## Technologie

- Python 3.13
- OpenCV 4.13
- NumPy, Matplotlib, DeepFace
