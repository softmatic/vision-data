# vision-data
Sample images and data for vision projects. Unless otherwise noted, all data is licensed under CC-BY-4.0 (https://creativecommons.org/licenses/by/4.0/). For code and code snippets the MIT license applies (copyright (c) 2020, Softmatic GmbH).

## 2D

### Receipt scanning

Sample receipts from german grocery and hardware stores, drugstores, gas stations and other businesses. Receipts are cropped (subfolder A) and uncropped (B, C, D) 300dpi scans from a flatbed scanner. File names contain the major data points from the receipt (merchant, date of purchase, number of items, total amount due) so that they can also be used as simple ground truth cases for training receipt parsing or similar OCR applications. The naming scheme is "$MERCHANT_$DATE_$NUMITEMS_$AMOUNT.ext", e.g. "aldi_02032020_19_02423.jpeg".

For each scan, a JSON file is provided that contains the result of Amazon AWS Textract OCR for the respective receipt. The file contains the array of [BLOCKS](https://docs.aws.amazon.com/textract/latest/dg/API_Block.html) as returned from Textract. The naming of the JSON file follows the same scheme, only with an appended "blocks", e.g. "aldi_02032020_19_02423_blocks.json".

Extracting the lines of text from the json in two lines of Python:

```python
file = json.load("aldi_02032020_19_02423_blocks.json")
lines = list(filter(lambda x : x['BlockType'] == 'LINE', file))
```

The *lines* list will then contain the individual line objects with text content, confidence, position on the page etc.; raw JSON sample:

```json
{"BlockType": "LINE", "Confidence": 98.87596130371094, "Text": "BIO HONIG", "Geometry": {"BoundingBox": {"Width": 0.20352864265441895, "Height": 0.015931174159049988, "Left": 0.01894291304051876, "Top": 0.2164158821105957}} ... }
```

Subset from our test cases for the RoboScan receipt scanning app (https://roboscan.app, [Video shows receipt detection, text recognition and parsing on an iPhone SE II](https://youtu.be/MspQtJGhvzI)).

## 3D

None yet
