# Data Munging

This kata is taken from Dave Thomas's code kata site, codekata.com

## Part One: Weather Data

In weather.dat.csv you’ll find daily weather data for Morristown, NJ for June 2002. Download this text file, then write a program to output the day number (column one) with the smallest temperature spread (the maximum temperature is the second column, the minimum the third column).

## Part Two: TBD

## Part Three: TBD

## Retro

## Reading a File

In order to give everyone a quick start, here are code snippets for reading a file in various languages.

### C\#

In Visual Studio, add the data files to the project folder. Ensure the files are included in the project. Right click on each datafile in turn and select Properties. In the Copy to Output Directory property, select Copy Always.

Here's an example of reading in one of the data files and echoing it to the console:

            using var temperatures = new StreamReader("weather.dat.csv");

            while (!temperatures.EndOfStream)
            {
                var line = temperatures.ReadLine();
                Console.WriteLine(line);
            }

            temperatures.Close();

### JavaScript (NodeJS)

```javascript
var fileName = "weather.dat";
var lines = require("fs")
  .readFileSync(fileName, "utf-8") // Read the entire file as a string (not recommended for very large files, but fine here...)
  .split("\n"); // Split the string on carriage returns, resulting in an array with an entry per line
for (var line of lines) {
  var columns = line.split(/(\s+)/); // Split line on whitespace, to get columns
  // Do stuff with columns array...
}
```

### Java

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

...
String fileName = "weather.dat";
BufferedReader br = null;
try {
    br = new BufferedReader(new FileReader(fileName));
    String line = null;
    while (line = br.readLine() != null) {
        String[] columns = line.split("\\s+"); // Split line on whitespace, to get columns
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
var fileName = "weather.dat"
File(fileName).forEachLine {
    var columns = it.split("\\s+") // Split line on whitespace, to get columns
    // Do stuff with columns array...
}
```

### Python

```python
# Need example here
```
