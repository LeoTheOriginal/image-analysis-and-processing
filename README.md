# Image Analysis and Processing

Laboratoria z przedmiotu **Analiza i przetwarzanie obrazów** — AGH WFiIS, Informatyka Stosowana II st., semestr I (rok akademicki 2025/2026).

Repozytorium zawiera notebooki z ośmiu laboratoriów oraz dwa zbiorcze sprawozdania w formacie Jupyter / PDF.

## Struktura

```
notebooks/      # Notebooki Jupyter — laboratoria (lab_*.ipynb) i raporty (raport_*.ipynb)
images/         # Statyczne obrazy wejściowe (jpg, png)
videos/         # Sekwencje wideo wejściowe (mov) — nieśledzone w gicie ze względu na rozmiar
output/         # Generowane wyjścia (mp4 z lab 6, lab 7) — tworzone podczas uruchomienia, gitignored
```

## Laboratoria

| Nr | Temat | Notebook | Dane wejściowe |
|----|-------|----------|----------------|
| 1 | Wprowadzenie do OpenCV — wczytywanie, wyświetlanie, podstawowe operacje | `lab_1.ipynb` | `images/lab1.jpg` |
| 2 | Reprezentacja obrazu i koloru — RGB, HSV, segmentacja kolorystyczna, histogramy | `lab_2.ipynb` | `images/lab2.jpg` |
| 3 | Progowanie i segmentacja — Otsu, k-means | `lab_3.ipynb` | `images/lab3_1.jpg`, `images/lab3_2.png` |
| 4 | Filtracja obrazu — blur, mediana, Gauss, Sobel | `lab_4.ipynb` | `images/lab3_1.jpg` |
| 5 | Wykrywanie krawędzi — Laplace, Canny, transformacja Hougha (linie, okręgi) | `lab_5.ipynb` | `images/lab5_1.jpg`, `images/lab5_2.png` |
| 6 | Analiza sekwencji wideo — Hough na wideo, detekcja ruchu | `lab_6.ipynb` | `videos/vid1.mov`, `videos/vid2.mov` |
| 7 | Rozpoznawanie cech i obiektów — Harris/SIFT/SURF/FAST/ORB, kaskada Haara | `lab_7.ipynb` | `images/lab5_2.png`, `videos/vid1.mov` |
| 8 | Deep learning w przetwarzaniu obrazów — przegląd bibliotek + demo DeepFace | `lab_8.ipynb` | `images/lab1.jpg` |

## Raporty zbiorcze

| Raport | Zakres | Notebook |
|--------|--------|----------|
| Sprawozdanie 1 | Laboratoria **2–4** (reprezentacja koloru, progowanie, filtracja) | `raport_1.ipynb` |
| Sprawozdanie 2 | Laboratoria **5–7** (krawędzie, wideo, rozpoznawanie cech) | `raport_2.ipynb` |

> `lab_8.ipynb` jest standalone — to przegląd bibliotek deep learning (DeepFace, face_recognition, MediaPipe) i krótkie demo, bez sprawozdania zbiorczego.

## Uruchomienie

### Wymagania
- Python 3.13
- ~2 GB miejsca na środowisko (DeepFace pobiera modele przy pierwszym uruchomieniu)

### Setup
```powershell
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/
```

### Eksport raportów do PDF
```powershell
jupyter nbconvert --to pdf notebooks/raport_1.ipynb
jupyter nbconvert --to pdf notebooks/raport_2.ipynb
```
Wymagane są `nbconvert` i `pypandoc_binary` (już w `requirements.txt`).

## Pliki wejściowe spoza repo

`videos/*.mov` są gitignored (rozmiar). Aby uruchomić lab 6 i lab 7, umieść w `videos/`:
- `vid1.mov` — sekwencja drogowa (Hough na wideo, detekcja twarzy)
- `vid2.mov` — sekwencja statyczna (detekcja ruchu)

## Technologie

- **OpenCV 4.13** — operacje obrazowe, filtracja, transformacje, `cv2.kmeans` (lab 3)
- **NumPy + Matplotlib** — manipulacja danymi, wizualizacja
- **DeepFace + tf-keras** — analiza twarzy (lab 8)
- **Pillow, nbconvert, pypandoc_binary** — eksport raportów do PDF
