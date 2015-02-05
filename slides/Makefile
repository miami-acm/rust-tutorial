THEME=moon

index.html : slides.rst
	pandoc -t revealjs -s -o index.html slides.rst
	sed -i -e 's/reveal.js\/css\/theme\/simple.css/reveal.js\/css\/theme\/$(THEME).css/' index.html

gh-pages : index.html
	git checkout gh-pages
	cd .. && mv slides/index.html ./index.html
	git add ../index.html
	git commit
