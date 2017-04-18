# csv_parser

This is a simple CSV file parser that reads the file contents into memory.
I used this as an exercise to write the tool explicitly as a finite-state machine.

## Instructions

A CSV_parser object is created using a bufferedReader object
 ```CSVParser parsed_csv = new CSVParser(bufferedReader)```
 
 The parsed information can be retrieved as a 2-dimensional array using:
 ```parsed_csv.getCSV()```
 
 ## Format
 
 The tool will parse a file with the following rules:
 * Cells are delimited by commas that are not enclosed by double-quotes (")
 * If the first and last characters in a cell are double-quotes ("), then all characters in between are read in literally including commas, but excluding double-quotes (see below).
 * Double-quotes can be read in literally by being escaped using another double-quote
    * E.g. `one ,2,"""three""","fo""ur""",five` will be retrieved as `[one ][2]["three"][fo"ur"][five]`
  
