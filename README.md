# Assamese vowel harmony corpus

This repository holds the metadata for a read-speech corpus built around Assamese vowel harmony, a public sample of the recordings with their Praat annotations, and the model outputs reported in the paper.

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

Speakers come from six districts of Upper Assam: Jorhat (4), Dhemaji (3), Golaghat (2), Sivasagar (2), Tinsukia (2) and Dibrugarh (1). All reported Assamese as their first language and no history of speech or hearing disorders. Assamese has eight surface vowels. /i e o u/ are [+ATR] and /ɛ ɔ ʊ ɑ/ are [−ATR]. The high [+ATR] vowels /i/ and /u/ spread [+ATR] leftward, and the low vowel /ɑ/ blocks the spread. The word list samples fully [+ATR] words, fully [−ATR] words, words with a [+ATR] trigger, and words where /ɑ/ makes the result mixed.

## Monophthong counts in the available corpus annotations

The table below lists the 8,609 monophthong intervals across 3,123 distinct recordings, with matching audio and annotations.

| Vowel | ATR category | Token count |
|---|---|---:|
| /i/ | [+ATR] | 1,873 |
| /e/ | [+ATR] | 1,547 |
| /o/ | [+ATR] | 1,460 |
| /u/ | [+ATR] | 129 |
| /ɛ/ | [−ATR] | 1,087 |
| /ɔ/ | [−ATR] | 588 |
| /ʊ/ | [−ATR] | 764 |
| /ɑ/ | [−ATR] | 1,161 |
| **Total** | | **8,609** |

Counts include each recording ID once. Where annotated copies overlap, `finaldata_all` takes precedence, followed by `mono_wav` and then `data`; 73 additional annotated recordings come from `mono_wav`. Only separate intervals labeled /i e o u ɛ ɔ ʊ ɑ/ are counted. Diphthong/glide intervals, blank annotations, and TextGrids without matching audio are excluded.

## What is in this repository

```
metadata/
  wordlist.csv            80 target words (W01-W80): Assamese script, IPA, word type, ATR pattern, carrier sentence
  speakers.csv            speaker ID, sex, age group, word tokens kept per speaker
samples/
  beseri/   ekeloge/   dhemali/      .wav + .TextGrid for every sample token
  samples.csv             one row per sample recording (37)
  vowel_segments.csv      one row per vowel in the samples (124), with onset, offset and ATR value
```

### The sample set

The sample has 37 recordings: one token of each of three words from every speaker who produced it. The three words were chosen because together they show the three outcomes of the harmony system.

| Word | IPA | Pattern | Recordings | Speakers |
|---|---|---|---|---|
| beseri (বেচেৰী) | beseri | all [+ATR] | 13 | 13 |
| ekeloge (একেলগে) | ɛkɛlɔgɛ | all [−ATR] | 13 | 13 |
| dhemali (ধেমালি) | dʰɛmɑli | mixed: /ɑ/ blocks the spread from /i/ | 11 | 11 |

For each speaker, we took the first repetition whose annotation matched the word's dictionary form. The sample is intended to check recording quality, annotation conventions, and file formats before requesting the full corpus. Each recording contains the target word extracted from its carrier sentence, at 16 kHz, 16-bit mono WAV. The annotation for each recording has the same file name with a `.TextGrid` extension. File names follow `<word>_<n>.wav`, where `n` is a running number and does not identify the speaker; use `samples/samples.csv` for the speaker of each file.

## Datasheet

**Purpose.** The corpus was built to measure the acoustic correlates of the ATR contrast in Assamese and to study vowel harmony in production. The word list balances harmonized and non-harmonized words.

**Collection.** Speakers were recruited through the IIT Guwahati community and compensated for their time. Each speaker read every word four or five times in a fixed carrier sentence in a sound-attenuated booth. Recordings were made at 48 kHz, 16-bit.

**Consent and ethics.** Informed consent was obtained from every participant. Public release is limited to metadata, model outputs, and the small audio sample in this repository; the full recordings are shared only in accordance with participant consent and institutional ethics approval. Speaker IDs are anonymous, exact ages are not released, and district of origin is reported only in aggregate.

**Annotation.** Phone boundaries were annotated manually in Praat. Tokens with disfluencies, mispronunciations, or recording problems were removed; pronunciation variants that are acceptable forms of the word were kept and labeled as heard.

**Intended uses.** Acoustic and phonological research on Assamese vowels and vowel harmony; comparison with ATR systems in other languages; evaluating speech technology (for example, speech synthesis or recognition) on harmony-sensitive vowel contrasts.


## Requesting the full corpus

The complete recordings and TextGrids for all 80 words are available for non-commercial research on reasonable request to the corresponding author, Sneha Ray Barman (sneha.barman@iitg.ac.in). Access is limited to the terms of the participants' consent and the ethics approval under which the data were collected. Please say briefly what you plan to do with the data.

## How to cite

If you use these data, please cite the paper:

```bibtex
@inproceedings{raybarman2026assamese,
  title     = {A corpus-based acoustic study of {ATR} contrast in {A}ssamese vowels},
  author    = {Ray Barman, Sneha and Mahanta, Shakuntala and Sharma, Neeraj Kumar},
  booktitle = {Proceedings of O-COCOSDA 2026},
  year      = {2026}
}
```

## Acknowledgements

We thank all the Assamese speakers who took part in the recordings. The corpus was collected at the Phonetics & Phonology Lab, IIT Guwahati.

## Contact

Sneha Ray Barman, Centre for Linguistic Science & Technology, IIT Guwahati. sneha.barman@iitg.ac.in
Shakuntala Mahanta, Department of Humanities & Social Sciences, IIT Guwahati. smahanta@iitg.ac.in
Neeraj Kumar Sharma, Mehta Family School of Data Science & Artificial Intelligence. neerajs@iitg.ac.in
