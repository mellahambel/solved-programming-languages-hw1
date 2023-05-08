Download Link: https://assignmentchef.com/product/solved-programming-languages-hw1
<br>
You will write 11 SML functions (and tests for them) related to calendar dates. In all problems, a “date” is an SML value of type int*int*int, where the first part is the year, the second part is the month, and the third part is the day. A “reasonable” date has a positive year, a month between 1 and 12, and a day no greater than 31 (or less depending on the month). Your solutions need to work correctly only for reasonable dates, but do not check for reasonable dates (that is a challenge problem) and many of your functions will naturally work correctly for some/all non-reasonable dates. A “day of year” is a number from 1 to 365 where, for example, 33 represents February 2. (We ignore leap years except in one challenge problem.)

<ol>

 <li>Write a function is_older that takes two dates and evaluates to true or false. It evaluates to true if the first argument is a date that comes before the second argument. (If the two dates are the same, the result is false.)</li>

 <li>Write a function number_in_month that takes a list of dates and a month (i.e., an int) and returns how many dates in the list are in the given month.</li>

 <li>Write a function number_in_months that takes a list of dates and a list of months (i.e., an int list) and returns the number of dates in the list of dates that are in any of the months in the list of months. <em>Assume the list of months has no number repeated. </em>Hint: Use your answer to the previous problem.</li>

 <li>Write a function dates_in_month that takes a list of dates and a month (i.e., an int) and returns a list holding the dates from the argument list of dates that are in the month. The returned list should contain dates in the order they were originally given.</li>

 <li>Write a function dates_in_months that takes a list of dates and a list of months (i.e., an int list) and returns a list holding the dates from the argument list of dates that are in any of the months in the list of months. <em>Assume the list of months has no number repeated. </em>Hint: Use your answer to the previous problem and SML’s list-append operator (@).</li>

 <li>Write a function get_nth that takes a list of strings and an int<em>n </em>and returns the <em>n<sup>th </sup></em>element of the list where the head of the list is 1<em><sup>st</sup></em>. Do not worry about the case where the list has too few elements: your function may apply hd or tl to the empty list in this case, which is okay.</li>

 <li>Write a function date_to_string that takes a date and returns a string of the form January 20, 2013 (for example). Use the operator ^ for concatenating strings and the library function toString for converting an int to a string. For producing the month part, do <em>not </em>use a bunch of conditionals. Instead, use a list holding 12 strings and your answer to the previous problem. For consistency, put a comma following the day and use capitalized English month names: January, February, March, April, May, June, July, August, September, October, November, December.</li>

 <li>Write a function number_before_reaching_sum that takes an int called <em>sum</em>, which you can assume is positive, and an int list, which you can assume contains all positive numbers, and returns an int. You should return an int <em>n </em>such that the first <em>n </em>elements of the list add to less than sum, but the first <em>n</em>+1 elements of the list add to <em>sum </em>or more. Assume the entire list sums to more than the passed in value; it is okay for an exception to occur if this is not the case.</li>

 <li>Write a function what_month that takes a day of year (i.e., an int between 1 and 365) and returns what month that day is in (1 for January, 2 for February, etc.). Use a list holding 12 integers and your answer to the previous problem.</li>

 <li>Write a function month_range that takes two days of the year day1 and day2 and returns an int list [m1,m2,…,mn] where m1 is the month of day1, m2 is the month of day1+1, …, and mn is the month of day day2. Note the result will have length day2 – day1 + 1 or length 0 if day1&gt;day2.</li>

 <li>Write a function oldest that takes a list of dates and evaluates to an (int*int*int) option. It evaluates to NONE if the list has no dates and SOME<em>d </em>if the date <em>d </em>is the oldest date in the list.</li>

</ol>

1

<ol start="12">

 <li><strong>Challenge Problem: </strong>Write functions number_in_months_challenge and dates_in_months_challenge that are like your solutions to problems 3 and 5 except having a month in the second argument multiple times has no more effect than having it once. (Hint: Remove duplicates, then use previous work.)</li>

 <li><strong>Challenge Problem: </strong>Write a function reasonable_date that takes a date and determines if it describes a real date in the common era. A “real date” has a positive year (year 0 did not exist), a month between 1 and 12, and a day appropriate for the month. Solutions should properly handle leap years. Leap years are years that are either divisible by 400 or divisible by 4 but not divisible by 100.</li>

</ol>

(Do not worry about days possibly lost in the conversion to the Gregorian calendar in the Late 1500s.)

Note: Remember challenge problems are not required for a high grade and will be worth (only) a few points.

Note: The sample solution contains <em>roughly </em>75–80 lines of code, not including challenge problems. <strong>Syntax Hints</strong>

Small syntax errors can lead to strange error messages. Here are 3 examples for function definitions:

<ol>

 <li>int * int * int list means int * int * (int list), not (int * int * int) list.</li>

 <li>fun f x : t means the <em>result type </em>of f is t, whereas fun f (x:t) means the <em>argument type </em>of f is t. There is no need to write result types (and in later assignments, no need to write argument types).</li>

 <li>fun (x t), fun (t x), or fun (t : x) are all wrong, but the error message suggests you are trying to do something much more advanced than you actually are (which is trying to write fun (x : t)).</li>

</ol>

<h2>Summary</h2>

Evaluating a correct homework solution should generate these bindings:

val is_older = fn : (int * int * int) * (int * int * int) -&gt; bool val number_in_month = fn : (int * int * int) list * int -&gt; int val number_in_months = fn : (int * int * int) list * int list -&gt; int val dates_in_month = fn : (int * int * int) list * int -&gt; (int * int * int) list val dates_in_months = fn : (int * int * int) list * int list -&gt; (int * int * int) list val get_nth = fn : string list * int -&gt; string val date_to_string = fn : int * int * int -&gt; string val number_before_reaching_sum = fn : int * int list -&gt; int val what_month = fn : int -&gt; int val month_range = fn : int * int -&gt; int list

val oldest = fn : (int * int * int) list -&gt; (int * int * int) option

Of course, generating these bindings does not guarantee that your solutions are correct. <em>Test your functions: Put your testing code in a separate file. We will not grade the testing file, nor will you turn it in, but surely you want to run your functions and record your test inputs in a file.</em>

<h2>Assessment</h2>

We will automatically test your functions on a variety of inputs, including edge cases. We will also ask peers to evaluate your code for simplicity, conciseness, elegance, and good formatting including indentation and line breaks. Your solution will also be checked for using only features discussed so far in class. In particular, you must not use SML’s mutable references or arrays. Do not use pattern matching (until the next assignment where we will require it).