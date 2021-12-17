# Environement variable handler

This Solution contains a single Power Automate Cloud Flow that is build to be used as a Child Flow.
This flow takes one (1) input parameter :
- **Environement variable name**

And retrieve one (1) output : 
- **Environment variable value**

Here is the Flow diagram:
![Flow diagram](https://github.com/tchinnin/Power-Platform-Solutions/blob/main/Environment%20variable%20handler/High%20level%20Flow%20diagram.png)

It uses one connection to `Common Data Service (Current Environment)` connector.
It works with all types of Power Platform Environement variable. In all cases, it will return a `Text` value. So you will probably have to convert the output in your Parent Flow using either:
- `if()` for a Boolean variable
- `float()` for a Decimal variable
- `json()` for a JSON variable

_Don't forget that Parent Flows will have to be inside a Solution as well._
_As a matter of fact, the parent Flow will have to be **created** within a solution, not simple **imported for outside a solution**_

### Version History

Version| Date | Description 
--- | --- | --- 
1.1.0.0| 2021/02/24 | Update using Common Data Service (Current Environment) connector 
1.0.0.0 | 2021/02/24 | First version of the solution