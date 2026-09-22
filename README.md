# Enemy AI Pathfinding

## 1. Identifikasi Algoritma

Algoritma yang digunakan adalah A* (A-Star Pathfinding)
yang dikombinasikan dengan Enemy Detection dan Distance Checking.

A* digunakan untuk mencari jalur dari posisi Enemy menuju
Player dengan mempertimbangkan obstacle di dalam dungeon.

## 2. Flowchart Algoritma

```mermaid
flowchart TD
    A([Start]) --> B[Enemy mendeteksi Player]
    B --> C{Player terdeteksi?}

    C -- Tidak --> B
    C -- Ya --> D[Hitung jarak Enemy ke Player]

    D --> E{Player dalam jangkauan?}

    E -- Tidak --> F[Enemy patroli / mencari Player]
    F --> B

    E -- Ya --> G[Gunakan Algoritma A*]
    G --> H[Cari jalur menuju Player]

    H --> I{Jalur ditemukan?}

    I -- Tidak --> J[Enemy mencari jalur lain]
    J --> B

    I -- Ya --> K[Enemy mengikuti jalur]
    K --> L[Enemy bergerak menuju Player]

    L --> M{Enemy sudah dekat?}

    M -- Tidak --> K
    M -- Ya --> N[Enemy menyerang Player]

    N --> B
