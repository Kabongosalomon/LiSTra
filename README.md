# LiSTra
This repository contains the "Lingala Speech Translation (LiSTra)" dataset presented on the paper entitled *[LiSTra, Automatic Speech Translation : English to Lingala casestudy]()*.

## Data
For copyright reasons, we are not able to share the audio files however, we provide the extraction pipeline below. We also highlight this pipeline can be used to new languages of interested.

Inside the dataset folder, for each language we provide:
- Alignment textgrids (from Maus forced aligner)
- Final textual output and segments textgrids
- [Mel Filterbank Spectrograms (such as used in the paper's experiments)](https://zenodo.org/record/3354711) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3354711.svg)](https://doi.org/10.5281/zenodo.3354711)


## Pipeline

- Source language Audio Download and Renaming : [01-Audio download Rename.ipynb](link)

- Download the corresponding text file for the source language :  [02-BibleisWebScrapping.ipynb](link).
- Download the corresponding text file for the target language :  [03-JwWebscraping.ipynb](link).
- Generate TextGrid files :  [04-webMausWavGenerator.ipynb](link).
- Rename the wav files :  [05.Rename_wav_files.ipynb](link).


After having you dataset you may need to run the following script to check for specific missing file:
    - If the two forders contains text: `bash check_diff.sh english/ lingala/ false` 
    - If the second folder is a folder to the waves : `bash check_diff.sh english/ wav_verse/ true`
    - To compare raw_txt with TextGrid : `bash check_diff_TextGrid.sh english/raw_txt/ english/maus_textgrid/ true`

Note: Please make sure the first param is the txt and the second is wav, if both are txt juste put the last param to false.



### Downloading Audio chapters for the source language from [bible.is](bible.is).


1.2. The audios were converted from multi to single channel and forced aligned by using [this](https://github.com/getalp/mass-dataset/blob/master/scripts/force-align.py) script. 

1.3. The raw chapter text files are not available for download anymore at the website. Thus, we provide them at dataset/LANGUAGE/raw_txt/. For new languages, chapter text files can be extracted from [this webpage](https://www.faithcomesbyhearing.com/audio-bibles/bible-recordings). 
These .txt files (chapter level) should be put on the same folder than the audios.

### 2) Aligning the data with [Maus forced aligner](https://clarin.phonetik.uni-muenchen.de/BASWebServices/interface/WebMAUSBasic)
For the covered languages, we make available the output from the Maus forced aligner in LANGUAGE/maus\_textgrid/. For new languages, please check the Website.

### 3) Obtaining speech alignment on a verse level
For each language, the audios were sliced in verses considering the output of 1.3. and the generated texgrids (2.). More details available [here](https://github.com/getalp/mass-dataset/blob/master/scripts/alignment/).

### 4) ID equivalence across languages
For translating the IDs in English, we provide the simple python script below.

~~~~
python3 scripts/fetch_data.py <language folder> <output folder> <language code>
~~~~

### 5) Generate a CSV file listing the verses available for each language

Use [this](https://github.com/getalp/mass-dataset/blob/master/scripts/check-verses.py) script to tenerate a CSV files listing the verses available for each language.
As not all the verses of a given language exist in another language, this CSV file can be use to get a list of verses common to all languages.

## Paper Experiments

The speech-to-speech retrieval baseline model proposed at the paper is available [here](https://github.com/getalp/BibleNet).

## Citation

If you use this corpus in your experiments, please use the following bibtex for citation


## Credit

- [MaSS: A Large and Clean Multilingual Corpus of Sentence-aligned Spoken Utterances Extracted from the Bible](https://github.com/getalp/mass-dataset)


## Contact

You can contact them me at skabenamualu@aimsammi.org

