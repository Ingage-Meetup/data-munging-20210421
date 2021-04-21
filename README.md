# Data Munging

This kata is taken from Dave Thomas's code kata site, codekata.com

## Part One: Weather Data

In weather.dat.csv you’ll find daily weather data for Morristown, NJ for June 2002. Download this text file, then write a program to output the day number (column one) with the smallest temperature spread (the maximum temperature is the second column, the minimum the third column).

## Part Two: Soccer League Table

The file football.dat contains the results from the English Premier League for 2001/2. The columns labeled ‘F’ and ‘A’ contain the total number of goals scored for and against each team in that season (so Arsenal scored 79 goals against opponents, and had 36 goals scored against them). Write a program to print the name of the team with the smallest difference in ‘for’ and ‘against’ goals.

## Part Three: Dry Fusion

Take the two programs written previously and factor out as much common code as possible, leaving you with two smaller programs and some kind of shared functionality.

## Retro

To what extent did the design decisions you made when writing the original programs make it easier or harder to factor out common code?

Was the way you wrote the second program influenced by writing the first?

Is factoring out as much common code as possible always a good thing? Did the readability of the programs suffer because of this requirement? How about the maintainability?

## Reading a File

In order to give everyone a quick start, here are code snippets for reading a file in various languages.

### C\#

In Visual Studio, add the data files to the project folder. Ensure the files are included in the project. Right click on each datafile in turn and select Properties. In the Copy to Output Directory property, select Copy Always.

Here's an example of reading in one of the data files and echoing it to the console:

```c#
    string fileName = "weather.dat.csv";
    using var temperatures = new StreamReader(fileName);

    while (!temperatures.EndOfStream)
    {
        var line = temperatures.ReadLine();
            var columns = line.split(','); // Split line on commas, to get columns
            // Do stuff with columns array...
        }

    temperatures.Close();
```

### JavaScript (NodeJS)

```javascript
var fileName = "weather.dat.csv";
var lines = require("fs")
  .readFileSync(fileName, "utf-8") // Read the entire file as a string (not recommended for very large files, but fine here...)
  .split("\n"); // Split the string on carriage returns, resulting in an array with an entry per line
for (var line of lines) {
  var columns = line.split(","); // Split line on commas, to get columns
  // Do stuff with columns array...
}
```

### Java

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

...
String fileName = "weather.dat.csv";
BufferedReader br = null;
try {
    br = new BufferedReader(new FileReader(fileName));
    String line = null;
    while (line = br.readLine() != null) {
        String[] columns = line.split(","); // Split line on commas, to get columns
        // Do stuff with columns array...
    }
} catch (IOException e) {
    e.printStackTrace();
} finally {
    br.close();
}
```

### Kotlin

```kotlin
var fileName = "weather.dat.csv"
File(fileName).forEachLine {
    var columns = it.split(",") // Split line on commas, to get columns
    // Do stuff with columns array...
}
```

### Python

```python
fileName = "weather.dat.csv"
weatherFile = open(fileName, "r")

for line in weatherFile:
    columns = line.split(",")  # Split the line on commas, to get columns
    # Do stuff here
```
