# Ru's Magic PDF Generator

A simple script which generates multiple* PDF documents from a single HTML template, replacing values from a csv.
Adding a long csv might crash your browser or flood your download folder with pdfs. Use it wisely or face the consequences!
#### Expected input:
- CSV: 
  * Comma separated values, each row of data on a new line
  * First row defines the keys, which will be replaced in the template
  * The rest of the rows should contain the data to be replaced in each PDF (1 row = 1 pdf)
  * The number of values in each row should match the number of keys defined in the first one.
    
- HTML template
  * The placeholders should be passed in {{ $key_name }} format. {{ + space + dollarsign + key_name + space + }}. Dont skip spaces, it will break.


####Basic example

```
csv:

name,family,age
John,Doe,30
Jane,Doe,25
```

```html
html template:

<p>Hi, my name is {{ $name }} {{ $family }} and I am {{ $age }} years old.</p>
```

Submitting the data and template above will create and download (in the default downloads folder of your browser)
*current_timestamp*-John-Doe.pdf
and *current_timestamp*-Jane-Doe.pdf. The content of the files will be the rendered template with values replaced.