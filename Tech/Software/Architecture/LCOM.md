Lack of cohesion in methods

used to define how [[Cohesion|Cohesive]] a module is

## Example

for each function/method that communicate, decrement one from the metric
for each function/method that doesnt communicati, increment one to the metric

in the end -> a high LCOM, means it can be broken down into smaller modules, a low LCOM means the module is nicely placed

(when defining the LCOM of a module, its important to consider that it may not present a low LCOM currently, but the system can change, and sometimes those changes need to be anticipated, like not refactoring that specific module because you know it will grow.)