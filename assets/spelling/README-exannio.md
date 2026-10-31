The embedded editor supplements Wordcraft's Moby hyphenation word list with
English base words from `dictionary-en@4.0.0` (SCOWL size 60, en_US), distributed
under the accompanying license. The list contains 48,000+ English words,
including `upcoming` and `functionality`. Wordcraft retains its existing inflection
rules and modern vocabulary supplement.
It is bundled at build time; spelling never sends document text to a service.

Source: https://registry.npmjs.org/dictionary-en/-/dictionary-en-4.0.0.tgz
Package repository: https://github.com/wooorm/dictionaries/tree/main/dictionaries/en

This is a modified word list: remove the `index.dic` count header, exclude entries
with the `c` (only-in-compound) flag, strip Hunspell flags after `/`, lowercase,
deduplicate, sort, and retain one word per line. The affix file's rules are not
imported; the host's existing inflection rules apply.

`build-wordcraft.ts` copies the list into the pinned upstream cache before compiling.
The integration patch includes it in the English spelling supplement and suggestions,
leaving hyphenation and other proofing languages unchanged. Its contents and license
are included in the build fingerprint. The license is shipped beside the WASM.
