# Data Munging

This kata is taken from Dave Thomas's code kata site, codekata.com

## Part One: Weather Data

In weather.dat.csv you’ll find daily weather data for Morristown, NJ for June 2002. Download this text file, then write a program to output the day number (column one) with the smallest temperature spread (the maximum temperature is the second column, the minimum the third column).

## Part Two: TBD

## Part Three: TBD

## Retro

## File IO in various languages

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

### Python

### Java

### Javascript

### Kotlin
