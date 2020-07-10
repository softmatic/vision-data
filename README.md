# vision-data
Sample images and data for vision projects. Unless otherwise noted, all data is licensed under CC-BY-4.0 (https://creativecommons.org/licenses/by/4.0/). For code and code snippets the MIT license applies (copyright (c) 2020, Softmatic GmbH).

## 2D

### Receipt scanning

Sample receipts from german grocery and hardware stores, drugstores, gas stations and other businesses. Receipts are cropped (subfolder A) and uncropped (B, C, D) 300dpi scans from a flatbed scanner. File names contain the major data points from the receipt (merchant, date of purchase, number of items, total amount due) so that they can also be used as simple ground truth cases for training receipt parsing or similar OCR applications. The naming scheme is "$MERCHANT_$DATE_$NUMITEMS_$AMOUNT.ext", e.g. "aldi_02032020_19_02423.jpeg".

Subset from our test cases for the RoboScan receipt scanning app (https://roboscan.app, [Video shows receipt detection, text recognition and parsing on an iPhone SE II](https://youtu.be/MspQtJGhvzI)).

## 3D

None yet
