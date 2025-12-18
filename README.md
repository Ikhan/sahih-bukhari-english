# Sahih al-Bukhari - Complete English Translation (JSON)

A comprehensive, machine-readable JSON dataset of **Sahih al-Bukhari**, one of the most authentic collections of Hadith (sayings and actions of Prophet Muhammad) in Islamic literature.

## About Sahih al-Bukhari

Sahih al-Bukhari is a collection of hadith compiled by Imam Muhammad al-Bukhari (810–870 CE). It is considered the most authentic hadith collection by Sunni Muslims, containing traditions that al-Bukhari meticulously verified through rigorous methods of authentication.

## Dataset Statistics

| Metric | Value |
|--------|-------|
| Total Books | 97 |
| Total Hadiths | 7,277 |
| Languages | English & Arabic |
| Format | JSON |

## File Structure

```
sahih-bukhari/
├── book-01.json          # Individual book files (1-97)
├── book-02.json
├── ...
├── book-97.json
├── bukhari-all-books.json    # Complete collection in one file (~29 MB)
├── compact-index.json        # Lightweight index for quick lookups
└── search-index.json         # Pre-built search index
```

## Data Schema

### Book Structure
```json
{
  "bookNumber": 1,
  "bookName": {
    "english": "Revelation",
    "arabic": "كتاب بدء الوحى"
  },
  "chapters": [...]
}
```

### Hadith Structure
```json
{
  "hadithNumber": 1,
  "inBookHadithNumber": 1,
  "chapterNumber": 1,
  "narrator": "'Umar bin Al-Khattab",
  "english": "Narrated 'Umar bin Al-Khattab: I heard Allah's Messenger (ﷺ) saying...",
  "arabic": "حَدَّثَنَا الْحُمَيْدِيُّ عَبْدُ اللَّهِ بْنُ الزُّبَيْرِ...",
  "inBookReference": "Book 1, Hadith 1",
  "uscMsaReference": "Vol. 1, Book 1, Hadith 1",
  "grade": "Sahih"
}
```

## Books Overview

The collection covers various aspects of Islamic jurisprudence and practice:

1. Revelation
2. Belief
3. Knowledge
4. Ablutions (Wudu')
5. Bathing (Ghusl)
6. Menstrual Periods
7. Rubbing Hands and Feet with Dust
8. Prayers (Salat)
9. Times of the Prayers
10. Call to Prayers
... and 87 more books covering topics including Zakat, Fasting, Hajj, Trade, Marriage, Jihad, Prophets, and more.

## Usage Examples

### JavaScript/Node.js
```javascript
const fs = require('fs');

// Load a specific book
const book1 = JSON.parse(fs.readFileSync('book-01.json', 'utf8'));
console.log(book1.bookName.english); // "Revelation"

// Access hadiths
book1.chapters.forEach(chapter => {
  chapter.hadiths.forEach(hadith => {
    console.log(`Hadith ${hadith.hadithNumber}: ${hadith.narrator}`);
  });
});
```

### Python
```python
import json

# Load the complete collection
with open('bukhari-all-books.json') as f:
    data = json.load(f)

print(f"Total Hadiths: {data['totalHadiths']}")

# Load individual book
with open('book-01.json') as f:
    book = json.load(f)

for chapter in book['chapters']:
    for hadith in chapter['hadiths']:
        print(f"{hadith['hadithNumber']}: {hadith['english'][:100]}...")
```

## Use Cases

- Building Islamic mobile/web applications
- Hadith search engines
- Natural Language Processing (NLP) research on religious texts
- Educational platforms
- Comparative religious studies
- Text analysis and data visualization

## License

This dataset is provided for educational and research purposes. The hadith texts are part of the Islamic religious heritage and are in the public domain.

## Contributing

Contributions are welcome! If you find any errors in the translation or data structure, please open an issue or submit a pull request.

## Acknowledgments

- Imam Muhammad al-Bukhari for compiling this invaluable collection
- The scholars who have preserved and transmitted these traditions through generations
- The translators who made this work accessible in English
