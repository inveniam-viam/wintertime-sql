## SQLite: Safety and Open-Source

SQLite has always operated on mobile devices since the very beginning of the project (it is an embedded database after all).

Mobile devices have batteries, and have (in many cases, used to) storage media that could be removed. This means that SQLite has to be resilient to power failures, or media completely just disappearing.

From a code standpoint, SQLite has 600 lines of test code for every single line of library code!

SQLite has these custom files that work on scenarios such as power outages, media being removed, fuzz tests etc. 

### Open-Source, but not Open-Contribution

SQLite is fully open-source, but they do not accept contributions from outsiders.

To keep the software as reliable and stable as it is, they do not accept contributions from outsiders, which is kind of at odds with the open-source ethos.

However, there is a fork called libsql which does accept contributions from everyone.

