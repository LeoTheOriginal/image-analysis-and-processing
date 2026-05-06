<div align="center">

# Image Analysis and Processing

**Laboratoria z przedmiotu *Analiza i przetwarzanie obrazów***
*AGH WFiIS · Informatyka Stosowana II st. · Semestr I · 2025/2026*

[![Python 3.13](https://img.shields.io/badge/Python-3.13-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![OpenCV 4.13](https://img.shields.io/badge/OpenCV-4.13-5C3EE8?logo=opencv&logoColor=white)](https://opencv.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![DeepFace](https://img.shields.io/badge/DeepFace-face%20analysis-FF6F61)](https://github.com/serengil/deepface)
[![AGH](https://img.shields.io/badge/AGH-WFiIS-CC0000)](https://www.fis.agh.edu.pl/)

</div>

---

Repozytorium gromadzi **8 notebooków laboratoryjnych** i **2 zbiorcze sprawozdania** pokrywające klasyczną i nowoczesną analizę obrazów — od podstaw OpenCV, przez filtrację i segmentację, po transformatę Hougha, detekcję cech i deep learning.

## Spis treści

- [Szybki start](#szybki-start)
- [Mapa laboratoriów](#mapa-laboratoriów)
- [Sprawozdania zbiorcze](#sprawozdania-zbiorcze)
- [Struktura repo](#struktura-repo)
- [Stos technologiczny](#stos-technologiczny)
- [Eksport do PDF](#eksport-do-pdf)
- [Dane wejściowe spoza repo](#dane-wejściowe-spoza-repo)
- [Troubleshooting](#troubleshooting)

## Szybki start

```powershell
git clone https://github.com/LeoTheOriginal/image-analysis-and-processing.git
cd image-analysis-and-processing
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/
```

> Wymaga **Python 3.13**. Pierwsze uruchomienie `lab_8.ipynb` pobiera modele DeepFace (~500 MB) — kolejne odpalenia są instant.

## Mapa laboratoriów

Osiem laboratoriów ułożonych progresywnie — każde buduje na poprzednim.

| #  | Notebook        | Temat                                                                          | Kluczowe techniki                              | Dane                                           |
|:--:|:----------------|:-------------------------------------------------------------------------------|:-----------------------------------------------|:-----------------------------------------------|
| 1  | `lab_1.ipynb`   | Wprowadzenie do OpenCV                                                         | I/O obrazu, BGR↔RGB, ROI, rysowanie            | `images/lab1.jpg`                              |
| 2  | `lab_2.ipynb`   | Reprezentacja obrazu i koloru                                                  | RGB, HSV, segmentacja barwy, histogramy        | `images/lab2.jpg`                              |
| 3  | `lab_3.ipynb`   | Progowanie i segmentacja                                                       | Otsu, `cv2.kmeans`, klasteryzacja barwna       | `images/lab3_1.jpg`, `images/lab3_2.png`       |
| 4  | `lab_4.ipynb`   | Filtracja obrazu                                                               | blur, mediana, Gauss, Sobel                    | `images/lab3_1.jpg`                            |
| 5  | `lab_5.ipynb`   | Wykrywanie krawędzi                                                            | Laplace, Canny, Hough (linie + okręgi)         | `images/lab5_1.jpg`, `images/lab5_2.png`       |
| 6  | `lab_6.ipynb`   | Analiza sekwencji wideo                                                        | Hough klatka po klatce, detekcja ruchu (diff)  | `videos/vid1.mov`, `videos/vid2.mov`           |
| 7  | `lab_7.ipynb`   | Rozpoznawanie cech i obiektów                                                  | Harris, SIFT, SURF, FAST, ORB, kaskada Haara   | `images/lab5_2.png`, `videos/vid1.mov`         |
| 8  | `lab_8.ipynb`   | Deep learning w obrazowaniu                                                    | DeepFace (wiek, płeć, emocje, rasa)            | `images/lab1.jpg`                              |

## Sprawozdania zbiorcze

Pełne sprawozdania ze wstępem, analizą wyników i wnioskami — dwa zbiorcze raporty pokrywające laboratoria 2–7.

<table>
<tr>
<th width="50%">Sprawozdanie 1 — <code>raport_1.ipynb</code></th>
<th width="50%">Sprawozdanie 2 — <code>raport_2.ipynb</code></th>
</tr>
<tr>
<td valign="top">

**Zakres: laboratoria 2–4**

Reprezentacja obrazu, segmentacja, filtracja klasyczna.

- Lab 2 — RGB / HSV, segmentacja koloru, histogramy
- Lab 3 — Otsu, k-means na obrazie kolorowym
- Lab 4 — filtry liniowe i nieliniowe, Sobel

</td>
<td valign="top">

**Zakres: laboratoria 5–7**

Krawędzie, wideo, rozpoznawanie cech.

- Lab 5 — Laplace vs Canny, Hough (linie + okręgi)
- Lab 6 — Hough na wideo, detekcja ruchu metodą różnic klatek
- Lab 7 — porównanie 5 detektorów cech, kaskada Haara

</td>
</tr>
</table>

> `lab_8.ipynb` jest **standalone** — przegląd bibliotek deep learning (DeepFace, face_recognition, MediaPipe) z krótkim demo. Nie jest częścią sprawozdania zbiorczego.

## Struktura repo

```
image-analysis-and-processing/
├── notebooks/         Notebooki: lab_1..8.ipynb + raport_1.ipynb + raport_2.ipynb
├── images/            Statyczne obrazy wejściowe (jpg, png)        — śledzone
├── videos/            Sekwencje wideo (mov)                        — gitignored (rozmiar)
├── output/            Wygenerowane mp4 z lab 6 i lab 7             — gitignored
├── requirements.txt   Zależności pip (OpenCV, DeepFace, nbconvert)
└── README.md          Ten plik
```

## Stos technologiczny

| Warstwa             | Biblioteki                                  | Gdzie używane                                           |
|:--------------------|:--------------------------------------------|:--------------------------------------------------------|
| **Computer vision** | `opencv-python` 4.13                        | wszystkie laby — operacje obrazowe, filtracja, Hough    |
| **Numerics**        | `numpy`                                     | manipulacja tensorami, indeksowanie, maskowanie         |
| **Wizualizacja**    | `matplotlib`                                | wykresy, histogramy, side-by-side comparisons           |
| **Deep learning**   | `deepface` + `tf-keras`                     | lab 8 — analiza wieku/płci/emocji z twarzy              |
| **Obrazy**          | `Pillow`                                    | wsparcie nbconvert, dodatkowe formaty                   |
| **Eksport**         | `nbconvert`, `pypandoc_binary`              | `*.ipynb` → PDF / HTML / LaTeX                          |

## Eksport do PDF

```powershell
jupyter nbconvert --to pdf notebooks/raport_1.ipynb
jupyter nbconvert --to pdf notebooks/raport_2.ipynb
```

`nbconvert` wymaga LaTeX-a w PATH (MiKTeX / TeX Live na Windows). Alternatywnie eksport do HTML działa bez LaTeX-a:

```powershell
jupyter nbconvert --to html notebooks/raport_2.ipynb
```

## Dane wejściowe spoza repo

`videos/*.mov` są gitignored ze względu na rozmiar. Aby uruchomić lab 6 i lab 7, umieść w `videos/`:

- **`vid1.mov`** — sekwencja drogowa (dashcam) — używana w lab 6 (Hough) oraz lab 7 (kaskada Haara na klatkach)
- **`vid2.mov`** — sekwencja w miarę statyczna z ruchomymi obiektami — używana w lab 6 (detekcja ruchu metodą różnic klatek)

## Troubleshooting

<details>
<summary><b>DeepFace przy pierwszym uruchomieniu pobiera kilkaset MB modeli</b></summary>

To normalne — DeepFace lazy-loaduje wagi VGG-Face / FaceNet do `~/.deepface/weights/`. Kolejne uruchomienia są szybkie. Jeśli chcesz przyspieszyć, możesz wstępnie pobrać modele:
```python
from deepface import DeepFace
DeepFace.build_model("VGG-Face")
```
</details>

<details>
<summary><b>cv2.imshow / VideoCapture nie działa w niektórych środowiskach</b></summary>

Notebooki używają `matplotlib` zamiast `cv2.imshow` — działa wszędzie, włącznie z JupyterLabem i remote serverami. Jeśli chcesz oknowy podgląd lokalnie, zainstaluj `opencv-python` (już w requirements) zamiast `opencv-python-headless`.
</details>

<details>
<summary><b>nbconvert → PDF zwraca błąd o brakującym LaTeX-u</b></summary>

Zainstaluj MiKTeX (Windows) lub TeX Live (Linux/Mac). Alternatywą jest eksport do HTML, a stamtąd wydruk do PDF z przeglądarki.
</details>

<details>
<summary><b>Brak <code>vid1.mov</code> / <code>vid2.mov</code></b></summary>

Pliki wideo nie są w repo (gitignored). Bez nich notebooki lab 6 i lab 7 (sekcja B) nie wykonają się — laby 1–5 i 7A działają bez problemu.
</details>

---

<div align="center">
<sub>Autor: <b>Dawid Piotrowski</b> · AGH WFiIS · 2025/2026</sub>
</div>
