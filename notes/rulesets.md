
Rulesets
========



1 or more rules
drag and drop re-ordering via handle
on/off toggle with clear labeling
grey-out or disabled appearance for rules toggled off

if (conditional) then [action]



Base Conditions
---------------
- `(true)` forces the action to always be peformed unless the rule is turned off
- `(false)` the action will never be performed
- `(value)` the action will be performed if the value can be considered true and the rule is turned on
- `(a ? b)` compare a to b to determine if the condition is true or false
- `a` and `b` can be numeric values or named items such as a specific sensor's current value
- comparison operators `?` can be standard greater than, less than, and/or equal to, bitwise operations, or other methods that result in a true or false value
- named items can refer to specific sensors, locally stored values, registry values, or - for the programmers - a memory location whose value is read and used
- (`interrupt`) evaluates to true if a hardware interrupt has been triggered and not yet cleared


Base Actions
------------
- `Restart` - stop processing rules in the ruleset and start evaluating rules from the first rule
- `Halt` - Cause the robotics platform to cease all on going tasks such as motion or automated scanning
- `Power Down` - `Halt`, then put the robotics platform into a power conservation mode
- `Wait for Update` - Pause evaluating of rules and wait for an updated ruleset to be received and validated by the robotics platform - ruleset evaluation continues with the next rule in the current rules
- `Wait and Restart` - `Wait for Update` but ruleset evaluation starts at the first rule in the new ruleset
- `Skip` - `Skip` over 0 or more rules and continue evaluating from the following rule
- `Set` - Set a specific output or variable to the value specified
- `[]` - No action is performed
- `Delay` - Delay evaluation of the next rule until after the specified time interval has elapsed


Program Flow
------------
- Rulesets are always evaluated starting from the first rule
- Any rule that is toggled Off is skipped over, not being evaluated
- If the current rule's condition is true, it's action is performed
- Evaluation moves to the next rule in the set unless the previously performed action overrides this behavior (e.g. `Stop`, `Restart`, `Skip`, etc)
- After the last rule has been evaluated (and it's action performed if it's condition was true) evaluation starts over from the first rule in the set as if an implicit `Restart` action was performed

