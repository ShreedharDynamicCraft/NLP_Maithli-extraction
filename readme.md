# Maithili Language Analysis - Roll Number 220101038

This project implements an NLP analysis pipeline for the Maithili language as per the assignment requirements. Below is a description and analysis of each step.

## Step 1: Download Wiki Dump
- **Command**: `wget --recursive --level=4 ... https://mai.wikipedia.org/wiki`
- **Description**: Downloaded Maithili Wikipedia pages into `downloaded_site`.
- **Analysis**: Successfully retrieved HTML files, though some pages were incomplete due to depth limitation.

## Step 2: HTML to Text Conversion
- **Module**: `html_to_text`
- **Description**: Extracted main content from `<div class="mw-parser-output">` into `.txt` files.
- **Analysis**: Effective for most pages, with minor noise from unparsed tags.

## Step 3: Combine Text Files
- **Command**: `cat text_files/*.txt > corpus.txt`
- **Description**: Merged all text files into a single corpus.
- **Analysis**: Created a comprehensive text base for analysis.

## Step 4: Sentence Segmentation
- **Module**: `corpus_to_sentences`
- **Description**: Split `corpus.txt` into `sentence-corpus.txt` with one sentence per line.
- **Analysis**: Worked well with `।` as the primary delimiter; some long sentences may need refinement.

## Step 5: Sentence Statistics
- **Module**: `sentence_statistics`
- **Description**: Computed word count, average words, and character count per sentence.
- **Analysis**: Provided useful metrics for understanding text complexity.

## Step 6: Clean Corpus
- **Module**: `clean_corpus`
- **Description**: Removed punctuation (except `।!?`) and saved as `cleanCorpus.txt`.
- **Analysis**: Improved text cleanliness for subsequent steps.

## Step 7: N-gram Generation
- **Module**: `generate_ngrams`
- **Description**: Generated unigram and bigram frequencies, plotted top unigrams.
- **Analysis**: Revealed common words and phrases; plotting enhanced visualization.

## Step 8: Morphological Analyser
- **Module**: `morphological_analysis`
- **Description**: Rule-based analyser for verb tenses and cases.
- **Analysis**: Basic but functional; needs expansion for full morphology.

## Step 9: Stop Words Removal
- **Module**: `remove_stop_words`
- **Description**: Removed stop words (e.g., "क", "म") and saved as `noStopWords.txt`.
- **Analysis**: Stop words were manually selected; a data-driven approach could improve accuracy.

## Files Included
- `220101038.ipynb`: Jupyter notebook with all code.
- `corpus.txt`, `sentence-corpus.txt`, `cleanCorpus.txt`, `wordUnigramFreq.txt`, `wordBigramFreq.txt`, `noStopWords.txt`: Generated outputs.
- `requirements.txt`: Dependencies list.

## Dependencies
See `requirements.txt` for required Python packages.

