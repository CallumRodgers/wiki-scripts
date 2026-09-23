- Page translators write links to other pages using simple \[\[Page]] syntax.
- Algorithm:
1. For a given page P:
	1. Read P's content language LANG
	2. If LANG is English, skip P
	3. For every internal wiki link L in P:
		1. if L links to a specific section, skip # Can't automate localisation of section titles
		2. if not, check if linked page X has a page in LANG
			1. if true:
				1. if L links to English: # If L links to a third language, it's likely for a very specific reason and it shouldn't be changed.
					1. if L has custom text T:
						1. Set link to \[\[X (LANG)|T]]
					2. else:
						1. Set link to \[\[X (LANG)|X]]
				2. else if L links to X (LANG) && has no custom text:
					1. Set link to \[\[X (LANG)|X]] # Cleaner for readers.