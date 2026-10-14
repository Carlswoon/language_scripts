# Language Learning Automation Toolkit

A collection of Python scripts built to automate repetitive language-learning workflows, particularly the creation of media and study resources for Anki.

The toolkit processes vocabulary data from Excel files and automates tasks such as downloading pronunciation audio, retrieving Chinese stroke-order animations, and preparing language-learning resources.

## Features

- Generate Chinese pronunciation audio from vocabulary lists
- Generate Korean pronunciation audio
- Download Chinese stroke-order animations
- Process vocabulary directly from Excel spreadsheets
- Skip duplicate or previously downloaded files
- Automatically save generated media into an Anki media directory
- Perform concurrent downloads to reduce processing time
- Additional translation and audio-processing utilities for Chinese and Korean

## Tech Stack

- Python
- pandas
- requests
- BeautifulSoup
- ThreadPoolExecutor
- Excel
- Anki

## Scripts

### `chinese_google_audio.py`

Reads Chinese vocabulary from an Excel spreadsheet and downloads pronunciation audio.

The script:

- Parses vocabulary using pandas
- Generates text-to-speech requests
- Sanitises generated filenames
- Prevents duplicate downloads
- Saves `.mp3` files directly into an Anki media directory
- Uses concurrent requests to process multiple entries

### `chinese_stroke_order.py`

Downloads animated stroke-order GIFs for Chinese characters.

The script:

- Reads vocabulary from Excel
- Breaks words into individual characters
- Retrieves stroke-order pages
- Parses the HTML using BeautifulSoup
- Finds the relevant animation
- Downloads GIF files into the Anki media directory
- Uses concurrent workers to improve download speed

### Other Scripts

The repository also includes utilities for:

- Chinese translation processing
- Korean translation processing
- Korean text-to-speech generation
- Korean audio extraction

## Motivation

I built these scripts to reduce the repetitive work involved in creating language-learning flashcards.

Instead of manually downloading pronunciation audio, stroke-order animations, and other media for individual vocabulary items, the scripts automate the process using structured spreadsheet data.

This allowed me to turn a repetitive manual workflow into a reusable automation pipeline.

## Requirements

Install the required Python packages:

```bash
pip install pandas requests beautifulsoup4 openpyxl
