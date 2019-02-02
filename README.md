## Recommended Sublime Text packages

* Citer - provides completion and search when citing bibtex entries
  - Citer: Search
  - Citer: Show All
* LaTeXTools - convenience
* Pandoc - takes care of transforming markdown into pdf or Word
* Markdown Extended
* Reindent on save - for json (settings) files

## Citer

The workspace is configured for Citer to look for `./library.bib`. You can change this in the workspace or user settings.

## Recommended Pandoc package settings

You have to add these to the global package settings for SublimeText. Doesn't work in project settings. Note that `pdflatex` and `pandoc-citeproc` need to be on your path.

Pandoc.sublime-settings:
```json
{
	"default": {

		"pandoc-path": "/usr/local/bin/pandoc",

		"transformations": {

			"HTML 5": {
				"scope": {
					"text.html.markdown": "markdown"
				},
				"syntax_file": "Packages/HTML/HTML.tmLanguage",
				"pandoc-arguments": [
					"-t", "html",
					"--filter", "/usr/local/bin/pandoc-citeproc",
					"--to=html5",
					"--no-highlight", 
				]
			},

			"PDF": {
				"scope": {
					"text.html": "html",
					"text.html.markdown": "markdown"
				},
				"pandoc-arguments": [
					"-t", "pdf", 
					
					"--pdf-engine=pdflatex",
					"--filter", "pandoc-citeproc"
				]
			},

			"Microsoft Word": {
				"scope": {
					"text.html": "html",
					"text.html.markdown": "markdown"
				},
				"pandoc-arguments": [
					"-t", "docx",  
					"--filter", "/usr/local/bin/pandoc-citeproc"
				]
			},

		},
		"pandoc-format-file": ["docx", "epub", "pdf", "odt", "html"]

	}

}
```
## Travis
### Build
Link the repository to Travis and push a new commit.
### Deploy pdf to Github releases
First run `travis setup releases`. Replace `[API KEY]` with the one generated. Push a new tag to trigger a release.
