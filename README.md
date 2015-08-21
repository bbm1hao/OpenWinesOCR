# WineOCR

OCR-based tool, used to feed [OpenWines](http://openwines.eu)open-data, using wine bottle labels images:

![etiquette_3.jpg](etiquette_3.jpg)

## Usage:

```
$ node wineocr.js [file_path] [layout_analysis_option] [language_code]
```

__Example__: see `etiquette_3.jpg` in the example folder

```bash
$ node wineocr.js ./examples/etiquette_3.jpg
```

which is the equivalent of the default options:

```bash
$ node wineocr.js etiquette_3.jpg 3 fra
```

Argument details:

- `etiquette_3.jpg` is a filepath
- `3` is a layout analysis option for `tesseract` OCR
- `fra` is a language code. Available languages depend on your tesseract installation (see below).


## Output:

```
$ node wineocr.js etiquette_3.jpg                                                        11:40  ronan@cider


CHÂTEAU MERCIER

CÔTES DE BOURG

APPELLATION CÔTES DE BOURG CONTRÔLÉE

2000

15H ml
ÇERÊRÏﬁLL MIS EN BOUTEILLE AU CHATEAU

“l |
S.C.E.A. FAMILLE CHETY, PRODUCTEUR A SA|NT—TROJAN (GIRONDE) FRANCE  .
```


## Installation


### 1/2 - Install tesseract

[tesseract](https://code.google.com/p/tesseract-ocr/) is an open-source project and a madatory dependency for WineOCR.

For Mac OS X:

```bash
brew install tesseract --all-languages
```

For other OS as Windows or GNU/Linux, and details about installing only certain languages packs, check out the [tesseract-ocr Project](https://code.google.com/p/tesseract-ocr/) website.


### 2/2 Install dependencies (node-tesseract, etc.)

```bash
npm install
```


## Options at run:

`layout_analysis_option` argument (see `psm` argument in `node-tesseract` lib) tells Tesseract OCR binary to only run a subset of layout analysis and assume a certain form of image. The options are:
 
- 0 = Orientation and script detection (OSD) only.
- 1 = Automatic page segmentation with OSD.
- 2 = Automatic page segmentation, but no OSD, or OCR.
- 3 = Fully automatic page segmentation, but no OSD. (Default)
- 4 = Assume a single column of text of variable sizes.
- 5 = Assume a single uniform block of vertically aligned text.
- 6 = Assume a single uniform block of text.
- 7 = Treat the image as a single text line.
- 8 = Treat the image as a single word.
- 9 = Treat the image as a single word in a circle.
- 10 = Treat the image as a single character.

`3` seems to be a good option for most wine bottle labels.

## License

MIT License - See [license](LICENSE) file.

Sources are available at [OpenWines/WineOCR](https://github.com/OpenWines/WineOCR/issues) on Github.


## Issues, support

Please check [OpenWines/WineOCR/issues](https://github.com/OpenWines/WineOCR/issues) page on Github.