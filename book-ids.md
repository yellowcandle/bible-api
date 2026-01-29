# Bible Book IDs (USFM Standard)

## Scope

This list covers the 66 books of the Protestant canon. The HelloAO API may include additional books (Apocrypha/Deuterocanonical) not listed here.

## Old Testament

| # | ID | Name | Aliases |
|---|-----|------|---------|
| 01 | GEN | Genesis | Gen |
| 02 | EXO | Exodus | Exod, Ex |
| 03 | LEV | Leviticus | Lev |
| 04 | NUM | Numbers | Num |
| 05 | DEU | Deuteronomy | Deut, Dt |
| 06 | JOS | Joshua | Josh |
| 07 | JDG | Judges | Judg, Jdg |
| 08 | RUT | Ruth | Ru |
| 09 | 1SA | 1 Samuel | 1Sam, 1 Sam |
| 10 | 2SA | 2 Samuel | 2Sam, 2 Sam |
| 11 | 1KI | 1 Kings | 1Kgs, 1 Kings |
| 12 | 2KI | 2 Kings | 2Kgs, 2 Kings |
| 13 | 1CH | 1 Chronicles | 1Chr, 1 Chron |
| 14 | 2CH | 2 Chronicles | 2Chr, 2 Chron |
| 15 | EZR | Ezra | Ezr |
| 16 | NEH | Nehemiah | Neh |
| 17 | EST | Esther | Esth |
| 18 | JOB | Job | |
| 19 | PSA | Psalms | Ps, Psalm, Psa |
| 20 | PRO | Proverbs | Prov, Pr |
| 21 | ECC | Ecclesiastes | Eccl, Eccles, Qoh |
| 22 | SNG | Song of Songs | Song, SoS, Song of Solomon, Canticles |
| 23 | ISA | Isaiah | Isa, Is |
| 24 | JER | Jeremiah | Jer |
| 25 | LAM | Lamentations | Lam |
| 26 | EZK | Ezekiel | Ezek, Eze |
| 27 | DAN | Daniel | Dan |
| 28 | HOS | Hosea | Hos |
| 29 | JOL | Joel | Joe |
| 30 | AMO | Amos | Am |
| 31 | OBA | Obadiah | Obad, Ob |
| 32 | JON | Jonah | Jon |
| 33 | MIC | Micah | Mic |
| 34 | NAM | Nahum | Nah |
| 35 | HAB | Habakkuk | Hab |
| 36 | ZEP | Zephaniah | Zeph |
| 37 | HAG | Haggai | Hag |
| 38 | ZEC | Zechariah | Zech |
| 39 | MAL | Malachi | Mal |

## New Testament

| # | ID | Name | Aliases |
|---|-----|------|---------|
| 41 | MAT | Matthew | Matt, Mt |
| 42 | MRK | Mark | Mk |
| 43 | LUK | Luke | Lk |
| 44 | JHN | John | Jn (NOT Jon = Jonah) |
| 45 | ACT | Acts | Ac |
| 46 | ROM | Romans | Rom, Ro |
| 47 | 1CO | 1 Corinthians | 1Cor, 1 Cor |
| 48 | 2CO | 2 Corinthians | 2Cor, 2 Cor |
| 49 | GAL | Galatians | Gal |
| 50 | EPH | Ephesians | Eph |
| 51 | PHP | Philippians | Phil, Php |
| 52 | COL | Colossians | Col |
| 53 | 1TH | 1 Thessalonians | 1Thess, 1 Thess |
| 54 | 2TH | 2 Thessalonians | 2Thess, 2 Thess |
| 55 | 1TI | 1 Timothy | 1Tim, 1 Tim |
| 56 | 2TI | 2 Timothy | 2Tim, 2 Tim |
| 57 | TIT | Titus | Tit |
| 58 | PHM | Philemon | Phlm |
| 59 | HEB | Hebrews | Heb |
| 60 | JAS | James | Jas |
| 61 | 1PE | 1 Peter | 1Pet, 1 Pet |
| 62 | 2PE | 2 Peter | 2Pet, 2 Pet |
| 63 | 1JN | 1 John | 1Jn, 1 John |
| 64 | 2JN | 2 John | 2Jn, 2 John |
| 65 | 3JN | 3 John | 3Jn, 3 John |
| 66 | JUD | Jude | (NOT Judges = JDG) |
| 67 | REV | Revelation | Rev, Apocalypse |

## Common Confusions

| User Says | Correct ID | NOT |
|-----------|-----------|-----|
| John | JHN | JON (Jonah) |
| Judges | JDG | JUD (Jude) |
| Jude | JUD | JDG (Judges) |
| 1 Samuel | 1SA | ISA (Isaiah) |
| Philippians | PHP | PHM (Philemon) |

## Parsing Algorithm

```
1. Normalize: lowercase, trim whitespace
2. Handle numbered books: "1 john" → "1JN", "2 kings" → "2KI"
3. Match against aliases table
4. Return 3-letter USFM ID
```

**Numbered book pattern:** `{number}{space}{name}` → `{number}{first 2 letters}`
- 1 Samuel → 1SA
- 2 Chronicles → 2CH  
- 1 Corinthians → 1CO
- 3 John → 3JN
