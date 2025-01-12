# Furigana/Ruby annotations extension for Markdown.

This extension provides two simple syntaxes to use furigana in a markdown
document.

This version is up to date with Python-Markdown 3.7

## Usage
The following construct

    [a](-b)

gets transformed into

    <ruby><rb>a</rb><rp>(</rp><rt>b</rt><rp>)</rp></ruby>

If you now write the following text in your markdown document

    [図](-と)[書](-しょ)[館](-かん)で[本](-ほん)を[読](-よ)みます。

this becomes

    <ruby><rb>図</rb><rp>(</rp><rt>と</rt><rp>)</rp></ruby><ruby><rb>書</rb><rp>(</rp><rt>しょ</rt><rp>)</rp></ruby>
    <ruby><rb>館</rb><rp>(</rp><rt>かん</rt><rp>)</rp></ruby>で<ruby><rb>本</rb><rp>(</rp><rt>ほん</rt><rp>)</rp></ruby>
    を<ruby><rb>読</rb><rp>(</rp><rt>よ</rt><rp>)</rp></ruby>みます。

If your Japanese IME produces fullwidth parentheses you can also use this syntax

    私（わたし）

The first character has to be a kanji and the characters in the fullwidth
parentheses have to be hiragana. You can then write the sentence from above
like this

    図（と）書（しょ）館（かん）で本（ほん）を読（よ）みます。

## Installation
1. Copy the script into your python markdown extension directory, eg.
`/usr/lib/python3/dist-packages/markdown/extensions/`
2. In `settings.py`, add `"MARKDOWN_EXTENSIONS": [ "markdown.extensions.furigana", ],` to the "default" dictionary 
(and to the dictionaries for variants you use as well).
3. In `settings.py`, add the following to the "WHITELIST_TAGS" list in the "default" dictionary (and any other 
dictionaries you use): `"ruby", "rb", "rp", "rt"`.

## License
furigana_markdown is licensed under the MIT license.