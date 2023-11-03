# Lab Report 3
**By: Wilson Zhu**

**Part 1:**

Failure-inducing input: <br>
```
@Test
  public void avgwolowest5() {
    double[] input1 = {2,2,4,4,5};
    assertEquals(3.75, ArrayExamples.averageWithoutLowest(input1),0.01);
  }
```
No Failure: <br>
```
  @Test
  public void avgwolowest4() {
    double[] input1 = {1.5,3.2,6.6,8.4,2,9,7.7};
    assertEquals(6.15, ArrayExamples.averageWithoutLowest(input1),0.01);
  }
```
JUnit output: <br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/f5542fb1-ce13-4f5c-924f-e60ef909301f)

Code before fix: <br>

```
  static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { 
      return 0.0; 
    }
    double lowest = arr[0];

    for(double num: arr) {
      if(num < lowest) {
         lowest = num; 
        }
    }
    double sum = 0;
    
    for(double num: arr) {
      if(num != lowest) { 
        sum += num; 
      }
    }
    return sum / (arr.length - 1);
  }
``` 

Code after fix: <br>
```
 static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { 
      return 0.0; 
    }
    double lowest = arr[0];
    int lowestInd = 0;

    for(int i = 0; i < arr.length;i++) {
      if(arr[i] < lowest) {
         lowest = arr[i];
         lowestInd = i; 
        }
    }

    double sum = 0;

    for(int i = 0; i < arr.length;i++) {
      if(i != lowestInd) { 
        sum += arr[i]; 
      }
    }
    return sum / (arr.length - 1);
  }
```
The fix addressed the issue of the code truncating all of the lowest numbers rather than one instance of the lowest number. In my case, if the input was `2,2,4,4,5`, it would truncate both 2's rather than just one. The fix I've implemented would send all inputs to an array and then it will compare all elements of the array, searching for the index containing the lowest number. This way, only 1 of the lowest is truncated and the other is kept. <br>

**Part 2:** <br>

Researching the `grep` command. <br>

Options: `-o`, `--color`, `-m NUM`, `-n`.

`-o`:
`grep -o` used in a directory: <br>
```
grep -o "FBI agent" technical/911report/
```
- Output: <br>
```
grep: technical/911report/: Is a directory
```
Note: The `--o` command does not work on directories but rather on files as it searches files matching a phrase and outputs the phrase every time it occurs.  <br>
`grep -o` used in a file: <br>
```
grep -o "FBI agent" technical/911report/chapter-3.txt
```
- Output: <br>
```
FBI agent
FBI agent
FBI agent
FBI agent
FBI agent
FBI agent
FBI agent
```
- Purpose: The purpose of the `-o` command is to parse through a specific text, outputting anything that matches a specific phrase. This is particularly helpful if you want to see how many times a certain phrase shows up in a file. <br>

`--color`:
Using `--color` on a directory: <br>
```
grep --color technical/911report/
```
- Output: <br>
```
grep: technical/911report/: Is a directory
```
Note: The `-color` command does not work on directories but rather on files as it searches files matching a phrase and outputs it in a different color.  <br>
Using `--color` on a file: <br>
```
grep --color "planes" technical/911report/chapter-7.txt
```
- Output: <br>
![image](https://github.com/W6zhu/cse15l-lab-reports/assets/146861759/ebd550f8-2613-4d49-abe5-28f97b6f099d)
 <br>
Note: The output of this example is an image as the color is command-line specific and doesn't translate to code blocks. <br>

- Purpose: The purpose of the `--color` command is to highlight words or phrases matching the input. This acts like a `control+f` or `command+f` in a browser. Instead of highlighting, the command will display the matched words in a different color in the terminal. This command is extremely useful when you are trying to find a specific phrase or words in long reports/chapters like the `911report`. <br>

ChatGPT: Part of the information gathered for this prompt was sourced from ChatGPT. <br>
- Input: `Can you explain to me what "--color [-auto]" does to a file?` <br>
- Output: <br>
```
The `--color` option in various Unix/Linux commands, including `grep`, is used to highlight or colorize the matching text in the output. When you use `--color`, the matched text is displayed in a different color to make it stand out, making it easier to identify matches in the output.

The `--color` option is often followed by an optional argument, `[-auto]`. Here's what they mean:

1. `--color`: This option enables color highlighting for the matching text in the output. When you use `--color`, the matched text is displayed in a different color, making it more visible.

2. `[-auto]`: This is an optional argument that can be used with `--color`. If you include `[-auto]`, it means that the color highlighting is applied automatically without the need for additional options. In other words, it enables color highlighting by default, so you don't have to explicitly use `--color` each time you run the command.

Here's an example of how you might use `grep` with `--color` to search for a pattern in a file and have the matching text highlighted:

bash
grep --color "search_pattern" file.txt

In this command, the matched text that contains "search_pattern" will be displayed in a different color to make it stand out in the output.

If you have the `[-auto]` option enabled, you don't need to use --color explicitly. The color highlighting will be applied automatically when you run the `grep` command without any additional options.

The specific colors used for highlighting may depend on your terminal settings and can vary from one system to another. It's a helpful feature for quickly identifying matched text in the output, especially when dealing with large amounts of data or log files.
```
- Outcome: Using the information provided by ChatGPT, I was able to conclude that I don't need the `[=auto]` part in my command and was able to gain a better understanding of the purpose of the `--color` command. <br>

`-m NUM`:
Where `NUM` is the number of lines to output. <br>
`grep -m NUM` used in a directory: <br>
```
grep -m 2 "flights" technical/911report

```
- Output: <br>
```
grep: technical/911report: Is a directory
```
Note: The `-m NUM` command does not work on directories but rather on files as it searches files matching a phrase and outputs the first 2 lines containing the input `flights`. <br>

`grep -m NUM` used in a file: <br>
```
grep -m 2 "flights" technical/911report/chapter-1.txt
```
- Output: <br>
```
    The 19 men were aboard four transcontinental flights.
    The hijackers attacked sometime between 8:42 and 8:46. They used knives (as reported by two passengers and a flight attendant), Mace (reported by one passenger), and the threat of a bomb (reported by the same passenger). They stabbed members of the flight crew (reported by a flight attendant and one passenger). Both pilots had been killed (reported by one flight attendant). The eyewitness accounts came from calls made from the rear of the plane, from passengers originally seated further forward in the cabin, a sign that passengers and perhaps crew had been moved to the back of the aircraft. Given similarities to American 11 in hijacker seating and in eyewitness reports of tactics and weapons, as well as the contact between the presumed team leaders, Atta and Shehhi, we believe the tactics were similar on both flights.
```
- Purpose: The purpose of the `-m NUM` command is to parse through a specific text, outputting the first `NUM` amount of lines containing the specified phrase. This command is useful as sometimes you may only want a certain amount of matches from the top.<br>
ChatGPT: Part of the information gathered for this prompt was sourced from ChatGPT. <br>
- Input: `What does grep -m NUM do?` <br>
- Output:  <br>
```
The `grep` option `-m` is used to limit the number of matching lines that `grep` will output. When you use `grep -m N`, where N is a number, `grep` will stop searching after it has found and displayed N matching lines. This is particularly useful when you only want to see a limited number of matches from a large file without processing the entire file.

For example, if you have a file named `data.txt` and you want to find the first two lines that contain the word "example," you can use:

bash
grep -m 2 "example" data.txt

In this case, `grep` will stop searching for matches in `data.txt` after it has found and displayed the first two lines that contain "example." This is helpful when you're dealing with large log files or other types of data, and you only want to see the initial occurrences of a specific pattern without processing the entire file.
```

- Outcome: Using the information provided by ChatGPT, I was able to gain a better understanding surrounding the command `-m NUM`, which outputs the first `NUM` amount of lines containing the specified phrase following it. <br>

`-n`:
`grep -n` used in a directory: <br>
```
grep -n "bomb" technical/911report

```
- Output: <br>
```
grep: technical/911report: Is a directory
```
Note: The `-n` command does not work on directories but rather on files as it searches files matching a phrase and outputs its line and the line number where its located. 
`grep -n` used in a file: <br>
```
grep -n "bomb" technical/911report/chapter-2.txt
```
- Output: <br>
```
42:                Islam, and celebrated recent suicide bombings of American military facilities in the
43:                Kingdom. It praised the 1983 suicide bombing in Beirut that killed 241 U.S. Marines,
44:                the 1992 bombing in Aden, and especially the 1993 firefight in Somalia after which
365:                November 24, 1989, when a remotely controlled car bomb killed Azzam and both of his
506:                fatwa demanding their eviction. In December, bombs exploded at two hotels in Aden
522:            In November 1995, a car bomb exploded outside a Saudi-U.S. joint facility in Riyadh
531:            In June 1996, an enormous truck bomb detonated in the Khobar Towers residential
540:                cloudy are the 1993 bombing of the World Trade Center, a plot that same year to
572:                particular interest in learning how to use truck bombs such as the one that had
862:                embassy in Nairobi was an easy target because a car bomb could be parked close by,
900:                Members of the cells rented residences, and purchased bomb-making materials and
919:                bombs, and acquired the delivery vehicles. On August 4, they made one last casing
930:            On the morning of August 7, the bomb-laden trucks drove into the embassies roughly
941:                permissible under Islam." Asked if he had indeed masterminded these bombings, Bin
```

- Purpose: The purpose of the `-n` command is to parse through a specific text, outputting any lines matching the specified phrase and the line number it is located in. This command is particularly useful if we want to find a certain phrase in a text and locate where it is located in the text especially long files. <br>



Source: Googled `grep command line options` and clicked the link that led me to `grep(1) - Linux manual page` which provided the following URL: https://man7.org/linux/man-pages/man1/grep.1.html.

