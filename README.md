# Joogle.law

The search engine for german lawyers and students of law.
It allows everyone to search for definitions of norm terminology in decisions by the BGH. The search will rank the results based on indicators for the relevance to the lawyer.
This tool was built for the LegalTech Hackathon at the University of Heidelberg, Germany on 5.4.-7.4.2019.

![screencast](https://raw.githubusercontent.com/enrico-kaack/LegalHackathon/master/screencast_low.gif)

## Features
- clean and simple interface
- input suggestions
- search results ranking based on a metric suitable for decision texts
## Technical description
- input: relevant components of court decisions stored in json format
- decision grounds (Entscheidungsgründe) is split into sections (Absätze) using beautiful soup to parse the html
- text of each section is preprocessed by an NLP pipeline (tokenizing, stripping, removal of stopwords, stemming)
- keyword search in the preprocessed text of each section
- candidate sections are then passed to the ranking algorithm
- ranking algorithm parameters have been estimated using linear regression
- results are sorted based on their ranking values, so that section containing very relevant information for a jurist appear at the top of the list

## Possible future work
TBD

## Installation

### Prerequesites
- Python 3.x and pip
- Node >= 8.x and npm >= 3.5.x

### Backend
1. Extract urteile.zip to backend/urteil
2. run pip install -r requirements.txt in backend/ to install all backend dependencies
3. instal the stopword corpus by opening an interactive python shell ``python`` and run
```
import nltk
nltk.download('stopwords')
```
4. run 
```python server.py```
to run the Flask server on the default port 5000


### Frontend
1. run `npm install` in frontend/ to install all dev dependencies
2. run `npm run dev` to run a local dev server with hot reloading to serve the website


## Authors
Bente Nittka

Enrico Kaack

Lukas Ballweg

Moritz Winckler

Tianyu Yuan




