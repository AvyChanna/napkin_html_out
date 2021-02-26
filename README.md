HTML output for napkin.tex

## Things that do not work

These were removed from `Preamble.tex`, All the associated commands were either commented out or made into a no-op.

- biblatex
- scrlayer-scrpage

cleveref was surrounded with \AtBeginDocument. It does not currently work.

## Hacks

diagrams.sty was reverted to v3.93. (It was time-bombed for 2009 but I changed it to work without further errors). This is because the diagrams.4ht shipped with text4ht does not work with the newer version.(And it loads in DVI mode, which is inferior to the default)

further errors while compiling were totally ignored. For example -

- --- TeX4ht warning --- \Link{ }? ---
- ! Missing { inserted.
- ! Missing } inserted.
- ! Missing number, treated as zero.


tocstyle is deprecated now. Use tocbasic or scrwfile instead.

## Results

First run was a disaster. Check `Napkin.html`(with trailing `l`) and Napkin{2,...,69}.html for output.

Second run was pretty good. I split the HTML into multiple chunks. To see the result, open `Napkin.htm`(without a trailing `l`) and the parts `Na*.htm`, `Nach*.htm`, `Napa*.htm`, `Nase*.htm`. These are for Top level, chapters, sections etc

Output is deliberately not `tidy`ed.

Make for yourself with `make4ht -a debug Napkin.tex "htm,3,notoc*"`
No CSS/JS is currently injected.
Some SVG images are not correct. Will look into that.
