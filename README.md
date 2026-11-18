# Assamese ATR vowel harmony corpus

This repository accompanies the O-COCOSDA 2026 paper *A corpus-based acoustic study of ATR contrast in Assamese vowels* (Ray Barman, Mahanta and Sharma). It holds the metadata for a read-speech corpus built around Assamese vowel harmony, a public sample of the recordings with their Praat annotations, and the model outputs reported in the paper.

The full set of recordings and annotations is shared for research on reasonable request (see [Requesting the full corpus](#requesting-the-full-corpus)).

## The corpus at a glance

| | |
|---|---|
| Language | Assamese (Indo-Aryan), colloquial Upper Assam variety |
| Speakers | 14 adults (8 female, 6 male), aged 19–35 |
| Target words | 80 (41 harmonized, 39 non-harmonized) |
| Word tokens | 4,689 kept after quality control |
| Vowel tokens | 14,448 segmented by hand (8,089 [+ATR], 6,359 [−ATR]) |
| Recording | Sound-attenuated booth, Tascam DR-100 MKII, 48 kHz, 16 bit |
| Elicitation | Carrier sentence *moi ___ buli kolʊ* ‘I say ___’, four or five repetitions per word |
| Annotation | Praat TextGrids with a phone tier and a word tier |

Speakers come from six districts of Upper Assam: Jorhat (4), Dhemaji (3), Golaghat (2), Sivasagar (2), Tinsukia (2) and Dibrugarh (1). All reported Assamese as their first language and no history of speech or hearing disorders.

Assamese has eight surface vowels. /i e o u/ are [+ATR] and /ɛ ɔ ʊ ɑ/ are [−ATR]. The high [+ATR] vowels /i/ and /u/ spread [+ATR] leftward, and the low vowel /ɑ/ blocks the spread. The word list samples fully [+ATR] words, fully [−ATR] words, words with a [+ATR] trigger, and words where /ɑ/ makes the result mixed.

## What is in this repository

```
metadata/
  wordlist.csv            80 target words: Assamese script, IPA, word type, ATR pattern, carrier sentence
  speakers.csv            speaker ID, sex, age group, word tokens kept per speaker
samples/
  beseri/   ekeloge/   dhemali/      .wav + .TextGrid for every sample token
  samples.csv             one row per sample recording
  vowel_segments.csv      one row per vowel in the samples, with onset, offset and ATR value
results/
  lmm_midpoint_table4.csv       linear mixed models at the vowel midpoint (paper Table 4)
  gamm_fitted_trajectories.csv  GAMM fitted trajectories with 95% bands (paper Figs 3 and 4)
docs/
  codebook.md             every column and every annotation label explained
poster/
  OCOCOSDA2026_Assamese_ATR_poster_A0.pdf
scripts/
  make_poster_figures.py  redraws the poster figures from the files above
```

### The sample set

The sample has 138 recordings of three words, chosen because together they show the three outcomes of the harmony system:

| Word | IPA | Pattern | Recordings | Speakers |
|---|---|---|---|---|
| beseri (বেচেৰী) | beseri | all [+ATR] | 53 | 13 |
| ekeloge (একেলগে) | ɛkɛlɔgɛ | all [−ATR] | 47 | 13 |
| dhemali (ধেমালি) | dʰɛmɑli | mixed: /ɑ/ blocks the spread from /i/ | 38 | 11 |

Each recording contains the target word cut from its carrier sentence, as 16 kHz, 16-bit mono WAV. The annotation for each recording has the same file name with a `.TextGrid` extension. File names follow `<word>_<n>.wav`, where `n` is a running number and does not identify the speaker; use `samples/samples.csv` for the speaker of each file.

## Requesting the full corpus

The complete recordings and TextGrids for all 80 words are available for non-commercial research on reasonable request to the corresponding author, Sneha Ray Barman (sneha.barman@iitg.ac.in). Access is limited to the terms of the participants' consent and the ethics approval under which the data were collected. Please say briefly what you plan to do with the data.

## Results files

`results/lmm_midpoint_table4.csv` reproduces Table 4 of the paper: for each of 19 acoustic measures, the ATR coefficient, its t value, the gender coefficient and the marginal R². F1 and F2 are Lobanov-normalized within speaker; the other measures are in their original units.

`results/gamm_fitted_trajectories.csv` holds the fitted curves behind Figures 3 and 4 of the paper: 100 time points per vowel for F1, F2, F3, B1, H2–H4c, H1–A1c and HNR (0–1.5 kHz), separately for [+ATR] and [−ATR], with standard errors and 95% bands. The `diff_plus_minus` column gives the [+ATR] minus [−ATR] difference curve.

See `docs/codebook.md` for the exact column definitions.

## Reproducing the poster figures

```
pip install -r scripts/requirements.txt
python3 scripts/make_poster_figures.py figures_out
```

The poster uses Inria Sans and DejaVu Sans; put the font files in `fonts/` or point `FONT_DIR` at them. Without them the figures still render in matplotlib's default font.

## How to cite

If you use these data, please cite the paper:

```bibtex
@inproceedings{raybarman2026assamese,
  title     = {A corpus-based acoustic study of {ATR} contrast in {A}ssamese vowels},
  author    = {Ray Barman, Sneha and Mahanta, Shakuntala and Sharma, Neeraj Kumar},
  booktitle = {Proceedings of O-COCOSDA 2026},
  address   = {Cebu, Philippines},
  year      = {2026}
}
```

GitHub shows a "Cite this repository" button generated from `CITATION.cff`.

## Licence

The data, annotations and documentation are released under [Creative Commons Attribution 4.0](LICENSE). The code in `scripts/` is released under the [MIT licence](LICENSE-CODE).

## Acknowledgements

We thank all the Assamese speakers who took part in the recordings. The corpus was collected at the Phonetics & Phonology Lab, IIT Guwahati.

## Contact

Sneha Ray Barman, Centre for Linguistic Science & Technology, IIT Guwahati. sneha.barman@iitg.ac.in
