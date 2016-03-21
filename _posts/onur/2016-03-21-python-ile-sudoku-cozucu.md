---
title: Python ile Sudoku çözücü
layout: post
author: onur
date: Mon, 21 Mar 2016 17:48:16 +0200
---

Brute force ile sudoku çözen python ile yazılmış bir sudoku çözücü.


```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

from __future__ import print_function


def uygun_mu(puzzle, satir, sutun, sayi):
    """Verilen sayı, satır ve sütun'a uyuyor mu diye kontrol eder

    :puzzle: 9x9'luk sayılardan oluşan puzzle
    :satir: Bakılacak satır
    :sutun: Bakılacak sütun
    :sayi: Denenecek sayı
    :returns: Uygunsa True değilse False"""

    satir_baslangici = int(satir / 3) * 3
    sutun_baslangici = int(sutun / 3) * 3

    for i in range(9):
        if (puzzle[satir][i] == sayi or
                puzzle[i][sutun] == sayi or
                puzzle[satir_baslangici + (i % 3)]
                      [sutun_baslangici + int(i / 3)] == sayi):
            return False

    return True


def sudoku_coz(puzzle, satir=0, sutun=0):
    """Sudoku çözen fonksiyon

    :puzzle: 9x9 luk sayılardan oluşan puzzle
    :satir: Çözülecek satır
    :sutun: Çözülecek sütun
    :returns: Puzzle çözüldüyse True, çözülemediyse False"""

    # Bakılan kutu asla 9'dan büyük olamaz
    if puzzle[satir][sutun] > 9:
        return False
    # Bakılan kutu zaten çözülmüşse sonrakine geç
    elif puzzle[satir][sutun] != 0:
        if (sutun + 1) < 9:
            return sudoku_coz(puzzle, satir, sutun + 1)
        elif (satir + 1) < 9:
            return sudoku_coz(puzzle, satir + 1, 0)
        else:
            return True

    for i in range(9):
        if uygun_mu(puzzle, satir, sutun, i + 1):
            puzzle[satir][sutun] = i + 1

            if (sutun + 1) < 9:
                if sudoku_coz(puzzle, satir, sutun + 1):
                    return True
                puzzle[satir][sutun] = 0
            elif (satir + 1) < 9:
                if sudoku_coz(puzzle, satir + 1, 0):
                    return True
                puzzle[satir][sutun] = 0
            else:
                return True

    return False


def print_puzzle(puzzle):
    """Puzzle'i ekrana yazdırır

    :puzzle: 9x9'luk sayılardan oluşan puzzle"""
    for i in range(9):
        if i > 0 and i % 3 == 0:
            print('|' + '-' * 7 + '|' + '-' * 7 + '|' + '-' * 7 + '|')
        print('|', end=' ')
        for j in range(9):
            print(puzzle[i][j], end=' ')
            if (j + 1) % 3 == 0:
                print('|', end=' ')
        print()


# Bir örnek
if __name__ == "__main__":
    puzzle = [
        [3, 2, 1, 7, 0, 4, 0, 0, 0],
        [6, 4, 0, 0, 9, 0, 0, 0, 7],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [0, 0, 0, 0, 4, 5, 9, 0, 0],
        [0, 0, 5, 1, 8, 7, 4, 0, 0],
        [0, 0, 4, 9, 6, 0, 0, 0, 0],
        [0, 0, 0, 0, 0, 0, 0, 0, 0],
        [2, 0, 0, 0, 7, 0, 0, 1, 9],
        [0, 0, 0, 6, 0, 9, 5, 8, 2]
    ]
    if (sudoku_coz(puzzle)):
        print_puzzle(puzzle)


# Örnek çıktısı:
# | 3 2 1 | 7 5 4 | 6 9 8 |
# | 6 4 8 | 2 9 3 | 1 5 7 |
# | 5 7 9 | 8 1 6 | 2 3 4 |
# |-------|-------|-------|
# | 7 8 2 | 3 4 5 | 9 6 1 |
# | 9 6 5 | 1 8 7 | 4 2 3 |
# | 1 3 4 | 9 6 2 | 8 7 5 |
# |-------|-------|-------|
# | 8 9 3 | 5 2 1 | 7 4 6 |
# | 2 5 6 | 4 7 8 | 3 1 9 |
# | 4 1 7 | 6 3 9 | 5 8 2 |
```
