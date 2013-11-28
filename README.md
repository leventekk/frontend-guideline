Frontend-guideline
==================

##Alap iranyelvek##
 * tagolas 2-es tabbal
 * unix line ending
 * karakterkodolas bom nelkuli utf8
 * maximum 100 karakter hosszu lehet egy sorod 
 
 
##HTML##

###Doctype###

 * ha xhtml oldalt kell keszitened, eleg egy transitional doctype
 
 	`<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
    "http://w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">`
 * html5 eseten pedig az alabbi doctype a hasznalatos
 
 	`<!doctype html>`
 	

###Markup###
 * attributumok eseteben double quote hasznalata kotelezo
 * a sajat magukat lezaro tageket nem kell lezarni.
	* `<input type="text">`
	* `<br>`
 * mindenhol torekedj a szemantikussagra
 	* ha valami headingnek felel meg, ott ne hasznalj 
 	
 		`<div class="secondary-heading">cim</div` 
 		
 		markupot, mert az nem jo. ehelyett `<h2>cim</h2`
 * kepek eseten alt tag **kell**, ha valami placeholder keprol van szo, akkor nem kell kitolteni, mivel nincs jelentese a kepnek. ami hatterkep, az legyen hatterkep, ne pedig img, es ez forditva is igaz. 
 * tablazatot tenylegesen csak tablazatos adatokhoz hasznalj! pelda: ![tabular data](http://www.w3.org/TR/html401/images/table3.gif "Tabular Data")
 * ha sok idod van, mikroformatumokat is hasznalhatsz
 
 
##CSS##

 * stringek eseteben single quote hasznalata kotelezo
 * preprocessor nelkul nem csinalhatsz semmit.
 	* sass/scss, ezek kozul barmelyiket hasznalhatod.
 * csak azt prefixeld, amit valoban kell! illetve ezekhez hasznalj mixint. ehhez tokeletes segitseg: 
 	* [http://peter.sh/experiments/vendor-prefixed-css-property-overview/](http://peter.sh/experiments/vendor-prefixed-css-property-overview/)
 	* [http://prefixr.com/](http://prefixr.com/)
 	* [http://caniuse.com/](http://caniuse.com/)
 	* hasznalj valtozokat, ha mar egyszer van ra lehetoseged
 	* hasznalt a sass altal ajanlott fajl elnevezeseket
 		* amibol outputot szeretnel generalni, azt underscore kezdetu fajlnevvel latod el (main.scss)
 		* amit pedig importalni fogsz, azt underscore-ral kezded (_normalize.scss)
 	* hasznalj normalis mappa strukturat
 		* base/ - _normalize, fonts, main.css_
 		* global/ - _valtozok, mixinek, function-ok_
 		* components/ - _komponensek_
 		* widgets/ - _widgetek, amik barhol mashol felhasznalhatoak az oldalon_
 	* atlathatoan tagold a forraskododat, dokumentald az adott reszt, extrakent markupot is elhelyezhetsz a widgeteknel
 	
 	
##JavaScript##

 * stringek eseteben single quote hasznalata kotelezo
 * Whitespace es formazas

		// rossz!
		if (variable==='variable') {
			doTheMagic();
		}
		
		// kovetendo pelda
		if (variable === 'variable') {
			doTheMagic();
		}
		
		
		// rossz!
		if (isTrue) magic();
		
		// kovetendo pelda
		if (isTrue) {
			magic();
		}
* mindig a strict, tipusos osszehasonlitast hasznalj!

		// ez true lesz, mivel csak erteket nez, tipus nelkul
		if (1 == '1') {
			magic();
		}
		
		// ez false lesz, mivel az ertekuk ugyan megegyezik, de tipusuk nem
		if (1 === '1') {
			magic();
		}
* torekedj arra, hogy ne a globalis nevterbe helyezd a valtozoidat
* valtozoneveket _camelCase_ formaban add meg, ami pedig konstans, azt __CONST_ formaban
* ne hasznald a _new_ operatort peldaul _Object_ vagy _Array_ letrehozasara.


###Altalanos###
 * ne browserre targetelj, hanem feature-re, ehhez nagy segiteseget tud adni a [modernizr](http://modernizr.com)







