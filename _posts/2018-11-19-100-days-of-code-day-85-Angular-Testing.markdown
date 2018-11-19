---
layout: post
title:  "100 Days of Code Day 85 - TSLint issues"
date:   2018-11-19 07:00:00
categories: 100DaysOfCode
---

# Resolving TSLint issues

Wondering what I need to do or configure to detect these issues before deliberately running yarn run lint locally or having the DSpace Travis build execute it.

# Line and character numbers

```
ERROR: src/app/app.component.ts[47, 48]: Parentheses are required around the parameters of an arrow function definition
ERROR: src/app/app.component.ts[47, 94]: Parentheses are required around the parameters of an arrow function definition
```

In such reports, 47 is the line number and 48 is the index of the character on the line.

# Automated import statements

```typescript
ERROR: src/app/shared/lang-switch/lang-switch.component.spec.ts[1, 48]: " should be '
ERROR: src/app/shared/lang-switch/lang-switch.component.spec.ts[2, 35]: " should be '
```

I had a whole bunch of reports like these, and verified that when I use IntelliJ IDEA's auto suggestions for imports, the imports get in there with double quotes instead of single quotes.

[Editor > Typescript > Code Style > Punctuation is where this is done](https://stackoverflow.com/questions/39779272/webstorm-phpstorm-double-quotes-in-typescript-auto-import)

# Ignoring quotemark rule for JSON

In JSON, only double quotes are allowed. So instead of just blindly changing the quotemarks there, I had to disable the quotemark rule and enable it again after the block.

[TSLint Rule flag](https://palantir.github.io/tslint/usage/rule-flags/)

# Blacklisted import

```
ERROR: src/app/shared/lang-switch/lang-switch.component.spec.ts[6, 27]: This import is blacklisted, import a submodule instead
```

And the offending code was

```
import {Observable} from 'rxjs';
```

[Resolving Blacklisted RxJS Import TSLint Error](https://kendaleiv.com/resolving-blacklisted-rxjs-import-tslint-error/)

# Knowing which rule I offended

Wondering if there is a way to run tslint in a way where it also outputs the offending rule itself instead of only the message of the rule, so it's easier to know which rule to disable.

This was possible with the ["verbose" formatter](https://palantir.github.io/tslint/formatters/).
I modified package.json, where the definitions of the yarn scripts are located, to include -t verbose.


# Day 86 Plan

Investigate and address the following remaining tslint issues

```
ERROR: (no-shadowed-variable) src/app/shared/lang-switch/lang-switch.component.spec.ts[141, 55]: Shadowed name: 'LangConfig'
ERROR: (array-type) src/app/shared/lang-switch/lang-switch.component.ts[19, 16]: Array type using 'Array<T>' is forbidden for simple types. Use 'T[]' instead.
ERROR: (no-shadowed-variable) src/app/shared/lang-switch/lang-switch.component.ts[31, 54]: Shadowed name: 'LangConfig'
ERROR: (no-shadowed-variable) src/app/shared/lang-switch/lang-switch.component.ts[39, 35]: Shadowed name: 'LangConfig'
ERROR: (no-shadowed-variable) src/app/shared/lang-switch/lang-switch.component.ts[46, 35]: Shadowed name: 'LangConfig'
ERROR: (no-input-rename) src/app/shared/testing/query-params-directive-stub.ts[9, 3]:
In the class "QueryParamsDirectiveStub", the directive input property "queryParams" should not be renamed.
However, you should use an alias when the directive name is also an input property, and the directive name
doesn't describe the property. In this last case, you can disable this rule with `tslint:disable-next-line:no-input-rename`.

ERROR: (array-type) src/config/global-config.interface.ts[21, 14]: Array type using 'Array<T>' is forbidden for simple types. Use 'T[]' instead.
```

# Future days - DSpace 7 Angular

* Investigate writing of tests and write tests for the original language switch.
* Continue with implementing the actions and the reducer for the language switch.
* Continue implementation of the action to deactivate a language.
* Build a feature where users can customize their own language tags, straight from the UI, by switching on some kind of "translator" mode, to do these changes at runtime
* UI for exporting their customized messages
* UI for enabling/disabling particular languages
* Learn how to write tests and write them for the language functionality
* [Angular Universal](https://angular.io/guide/universal) tutorial based on Tour of Heroes
* Continue where I left off in ng-book

# Future days - Analyzer.atmire.com work

* Change String based implementation of error message handling with types and objects, according to Antoine Snyers recent Atmire DevTalk.
* Change string based implementation of the different browse styles to an object, according to Antoine Snyers recent Atmire DevTalk
* Optimize my hideous methods for getItemcount and getRepoCount.
* Re-test the check if we return the right repository to a user who tries to add a new one
* Updating a repository: touch/change the base URL or not?
* Batch ingest: switch to newer add repository methods.
* WCAG testing against the start page to ensure it's accessible for people who rely on assistive tools.
* Transition from plain CSS to SASS to make it prettier and learn about SASS at the same time
* Instead of the 5 minute cron job, look into a gitlab webhook that executes the update script on prod whenever something is committed to master.
* Add documentation to the methods of the item controller
* Change the back button on the item page with a real link back to the repository analysis, instead of the current history -1 hack.

# Future Days - Productivity

* Get my IntelliJ IDEA Shortcuts for comments in order

# Future days - Jekyll http://bram-atmire.github.io/ site

* Make it prettier

# Future Days - Atmire.com work

Investigate and work on search engine optimization (SEO) for the main atmire.com website.

# Future Days - Learning just for learning

* CSS: Go through the fabulous [CSS Diner](https://flukeout.github.io/)

# Sustainability challenge - Finish before Christmas

If I continue like October, I could hit day 68 by end of October and day 98 by end of November.