---
layout:     post
title:      "Clean Code: Miscellaneous Notes"
date:       2017-10-03 07:58:00
summary:    "" 
categories: clean code misc notes
---

### Incremental improvement
* To write clean code, you must first write dirty code *and then clean it*.
* Feature Envy: Methods of a class should be interested in the variable and functions of the class they belong to, and not the variables and functions of other classes.
* Put code in places that is intuitive to readers.
* Refactor your function so that it is so clean and expressive that it's obvious how it works.

### Smells
* True/false selector arguments - For example what does `calculatePay(false)` do? If you find yourself wanting to do this, you might want to split your function up.
* Inappropriate static - `Math.max(1, 2)` is a good static function because all the data comes from its two args. `HourlyPayCalculator.calculatePay(employee, overtimeRate)` would be bad because it's very likely that we may wish to implement severla different algos for calculating hourly pay.
* Make logical dependencies visible. For example:
```
public class HourlyReporter {
    private final int PAGE_SIZE = 55;
    private HourlyReportFormatter formatter;

    public void generateReport(List<HourlyEmployee> employees) {
        addLineItemToPage(e);
        if (page.size() == PAGE_SIZE)
            printAndClearItemList();
    }

    private void printAndClearItemList() {
        formatter.format(page);
        page.clear();
    }
}
```
This assumes that `HourlyReporter` knows what the page size ought to be. Such an assumption is a logical dependency; `HourlyReporter` on the fact that `HourlyReportFormatter` can deal wtih page sizes of 55. This can be made physical by making a method **inside** HourlyReportFormatter which gets the maximum page size. 
