# The Project

Linguistic data especially useful for font designers: pangrams, sample sentences, character sets and metadata for the languages of the world. Extent and completeness of the data is limited, contributions are welcome!

Data structure: [`/dist/entryFormat.md`](https://github.com/hyvyys/language-data/blob/master/dist/entryFormat.md)

# Usage

## ES6 module

Install from GitHub `npm i hyvyys/language-data`, then:

```javascript
import LanguageData from 'language-data';
```

## JSON
Full data is exported as a JSON file in [`/dist/language-data.json`](https://github.com/hyvyys/language-data/blob/master/dist/language-data.json).

If you want a file limited to the data you're interested in, you can build it yourself. You'll need Node.js (>= v10.15.3). Clone the project, install dependencies `npm i`, and build it `npm run build -- [fields]` where `[fields]` is a space-delimited list of fields you want to include, e.g.:

```
npm run build -- script speakers pangrams
```

The list of available fields with their descriptions is in [`/dist/entryFormat.md`](https://github.com/hyvyys/language-data/blob/master/dist/entryFormat.md).

# Roadmap

  * Add missing fields `pangram` — for example choose from [http://clagnut.com/blog/2380/], but not all languages are present there.
  * Add missing fields `lettering` — for example using [Lettering](https://hyvyys.github.io/Lettering/).
  * Add missing fields `alphabet` and `specialCharacters`: develop functions to generate them, for example `specialCharacters` can be generated by removing `/[A-Za-z]/` from `alphabet` if `script == 'Latn'`.

# Contributing

In development, you can test your changes by running:

```
npm run test
```

To build data, run:

```
npm run build
```

Both scripts internally turn debugging messages on.
You can also do this when using the module like this:

```javascript
import { LanguageDataParser } from 'language-data';
new LanguageDataParser({ debug: true }).getData();
```