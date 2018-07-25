# Quart.ai-Code-Challenge

Assumptions:
1. For making cross platform compatible, I am using "JSONData.js" file for json test cases and "Rule.js" file for input rules.
2. In JSONData.js file please make sure, don't rename/remove the variable "JSONInput" and use the same file for other test cases too.
3. In Rule.js file please make sure the following points,
	1. Don't remove/rename the variable "rules".
	2. All the rules should be inserted as comma separated strings like ["ATL1 value should not be HIGH", "ATL2 value should not be HIGH"].
	3. For an valid input rule -
		1. each rule should use only one of these ("SHOULD","SHOULD NOT","SHOULD NEVER") to make positive/negative statement.
		2. for greater than condition, each rule should use only one of these ("RISE","ABOVE","MORE","GREATER","BIG","AFTER").
		3. for less than condition, each rule should use only one of these ("FALL","LOW","LESS","BEFORE").
		4. datetime should be in "YYYY/MM/DD" or "YYYY-MM-DD" format and other than this, use only one of these ("PRESENT", "PAST", "FUTURE").
		5. each rule should contain a valid signal ID.


Discussion Questions:
1. Briefly describe the conceptual approach you chose! What are the trade-offs?
So let's suppose there are total N rules and M signals,
	1. Traverse each rule one by one (from 1st rule to N).
	2. For each rule, Traverse Signal Data and check which one is failing under current rule.
	3. If True then display that signal and continue till last signal and keep checking for rule violation (from 1st signal to M).
	4. once the first rule completes then pick the second rule and do the same.
	5. at the end all the violated signals with respective rules will be displayed.

2. What's the runtime performance? What is the complexity? Where are the bottlenecks?
	1. With the current approach time complexity is directly related to the number of rules and signals, i.e., O(N * M).
	2. bottleneck is only for the worst cases when for a particular rule there is no signal which violates the current rule.

3. If you had more time, what improvements would you make, and in what order of priority?
	1. With more time I would have used Bucketing and hashing style where instead of taking all the signals we would take only those which matches with the current signal ID and in that case time complexity will surely reduced from O(N * M) to O(N + M)


Steps to Run:
1. Place the root folder in any of the working directory.
2. Run the index.html file with any web browser (ex. Google chrome).
3. For code checking purpose, runTest() is the main function in the code.

