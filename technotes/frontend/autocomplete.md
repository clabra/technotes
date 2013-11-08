Autocomplete js solutions
-------------------------

Sharing some experiences about what autocomplete js solution choose. I need it for suggestions in a input field for <href="http://getbootstrap.com/">Bootstrap</a> modal form

* <a href="http://ivaynberg.github.io/select2/">Select2</a>
** Pros: Work like a charm with bootstrap. 
** Cons: Is to select between given possibilities, you can't enter a new value 

* <a href="http://textextjs.com/">Textext</a>
** Cons: Very complete. You can use it also for tags manager
** Pros: Doesn't work well with boostrap styles

* Bootstrap typeahead.js
** Pros: Easy and integrated in bootstrap
** Cons: Deprecated in new versions in favor of Twitter typeahead.js

* Twitter typeahead.js 
** Pros: Very complete (see cache features)
** Cons: To integrate with bootstrap you have to download CSS. Needs additional template engine

Conclusion: 
Although I'm also tweaking to integrate it in my bootstrap modal form I have choosen Twitter typeahead.js by now
