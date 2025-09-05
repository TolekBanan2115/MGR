
# Badanie skuteczności algorytmów uczenia głębokiego w kontroli wyposażenia pracowników w środki ochrony indywidualnej 

Praca magisterska polegała na zbudowaniu zbioru danych, przeprowadzeniu adnotacji zdjęć, wytrenowaniu modeli YOLOv10 oraz analizie skuteczności modeli.

## Dataset

Zbiór składa się ze zdjęć przedstawiających osoby w komplecie środków ŚOI, jego części oraz braku ekwipunku BHP. W jego skład wchodzi część zbioru People Clothing Segmentation oraz zdjęcia podglądowe z serwisów stockowych.

<img width="623" height="272" alt="image" src="https://github.com/user-attachments/assets/84052de3-1026-4f3e-b5e4-43dc3d705c13" />

<img width="732" height="462" alt="image" src="https://github.com/user-attachments/assets/95b66c55-2d56-43c0-807e-0afd166f8fac" />


## Oznaczanie obrazów

Proces oznaczania obrazów przeprowadzony został w programie Label Studio. Zaznaczane były obszary, w których brakowało elementów ŚOI.

<img width="624" height="220" alt="image" src="https://github.com/user-attachments/assets/6cc9ae6b-ca8e-4fad-81bf-591e8aae3434" />

### Skrypt do ominięcia limitu 100 zdjęć w projekcie Label Studio

```powershell
$RELATIVE_PATH = "f:\\PRACA_MAGISTERSKA\\IMAGES_TO_LABEL" 
$DATASET_DIR = "IMAGES_TO_LABEL" 
$OUTPUT_FILENAME = "paths.txt" 
# Find all files in the dataset folder and format paths for Label Studio 
Get-ChildItem -Path "$RELATIVE_PATH" -File | ForEach-Object {"/data/local-files/?d=$DATASET_DIR/$($_.Name)"} | Set-Content -Path "$OUTPUT_FILENAME"
```

<img width="1566" height="176" alt="image" src="https://github.com/user-attachments/assets/183049f7-7622-49a9-ade7-35bdaf065d11" />


## Tech Stack

ultralytics, Label Studio, Python
