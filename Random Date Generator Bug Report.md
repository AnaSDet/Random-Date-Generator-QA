**Bug Report: Lack of Date Range Validation**

Bug ID: T001

Summary
The random date generator accepts invalid date ranges (start date after end date) without warning.

Steps to Reproduce
- Go to https://codebeautify.org/generate-random-date
- Set the Start Date to "3000-01-01 00:00:00"
- Set End Date to "2099-12-31 23:59:59"
- Click "Generate Random Dates"

Expected Result
Error message displayed, date generation prevented.

Actual Result
Random dates are generated without warning.

Environment
Browser: Chrome Version 128.0.6613.137 (64-bit)

Severity
High

Impact
Users may generate meaningless data, leading to incorrect assumptions or decisions.

Suggested Fix
Implement validation to compare start and end dates before generating. 
Display error for invalid ranges.

Additional Observations Include:
- The tool can handle extremely large date ranges (e.g., start date: 50000-01-01 00:00:00)
- It generates dates far into the future (e.g., 20330-06-30 23:05:04, 27921-06-21 00:56:04)
- Non-standard inputs like "TODAY" and "TOMORROW" are accepted without error messages
- The tool becomes unresponsive with requests for over 1.000.000 dates to generate
