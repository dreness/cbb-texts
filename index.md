---
title: Comedy Bang Bang Texts
layout: Home
---

## Comedy Bang Bang Texts

[![Github Pages Deployment Status](https://github.com/dreness/cbb-texts/actions/workflows/pages.yml/badge.svg)](https://github.com/dreness/cbb-texts/actions/workflows/pages.yml)

This site contains automated transcriptions of (some of) the Comedy Bang Bang podcast episodes. Try the search!

## Technical Details

The transcriptions were created using the fantastic [whisper.cpp](https://github.com/ggerganov/whisper.cpp) project, using the 'medium-en' model. I wrote a little [script](https://gist.github.com/dreness/2ca0bbd16402ff00621974e7815c51ca) to mostly automate the process, in particular to support clean interrupt and resume.

whisper.cpp can produce transcriptions in various file formats (vtt, srt, text, csv), however none of those are quite right for Github Pages, which wants markdown. Some decisions have to be made regarding how to format the markdown text, since a single line break doesn't affect the layout of normal body text. I tried a few differnet things and for now settled on one sentence per line, which in markdown means one sentence every *two* lines.

To do the conversion from vtt to markdown, I used [vtt2txt](https://github.com/TruthfulTechnology/pm-vtt2txt) with two small modifications:

* add two line breaks instead of one between each sentence
* remove duplicate sentences

### Future Possibilities...

* Much better frontmatter metadata to hold tags for things like
  * date / time
  * episode number
  * guest names
  * topics
* word cloud?
* automated cross-reference?