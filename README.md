# LiSTra
This repository contains the "Lingala Speech Translation (LiSTra)" dataset presented on the paper entitled *[LiSTra, Automatic Speech Translation : English to Lingala casestudy](https://github.com/dsfsi/2020-AMMI-salomon)*.

## Data
For copyright reasons, we are not able to share the audio files however, we provide the extraction pipeline below. We also highlight this pipeline can be used to new languages of interested.

## Pipeline

- Source language Audio Download and Renaming : [01-Audio download Rename.ipynb]()
- Download the corresponding text file for the source language :  [02-BibleisWebScrapping.ipynb]().
- Download the corresponding text file for the target language :  [03-JwWebscraping.ipynb]().
- Generate TextGrid files :  [04-webMausWavGenerator.ipynb]().
- Rename the wav files :  [05.Rename_wav_files.ipynb]().


After having you dataset you may need to run the following script to check for specific missing file:
    - If the two forders contains text: `bash check_diff.sh english/ lingala/ false` 
    - If the second folder is a folder to the waves : `bash check_diff.sh english/ wav_verse/ true`
    - To compare raw_txt with TextGrid : `bash check_diff_TextGrid.sh english/raw_txt/ english/maus_textgrid/ true`

Note: Please make sure the first param is the txt and the second is wav, if both are txt juste put the last param to false.

## Paper Experiments

The speech-to-speech retrieval baseline model proposed at the paper is available [here](https://github.com/dsfsi/2020-AMMI-salomon).


## Credit

- [MaSS: A Large and Clean Multilingual Corpus of Sentence-aligned Spoken Utterances Extracted from the Bible](https://github.com/getalp/mass-dataset)
- [Yuchen Liu and al. paper](https://arxiv.org/pdf/1912.07240.pdf)


## Contact

You can contact them me at skabenamualu@aimsammi.org

