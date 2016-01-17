# ESLint 规则中文翻译版
## 规则说明
ESLint中的规则被分为了多个种类，以便于你能够更好地理解这些规则。所有的规则默认都是不启用的。ESLint推荐给大家一套常用规则来发现比较常见的问题，而且你可以直接在你的配置文件中的`extends`选项下配置`"eslint:recommended"`值，这些被建议的规则就可以直接使用了。下面列出的规则中，指明了含有`(推荐)`的规则，都是在继承了`eslint:recommended`之后会被启用的规则。  
有一些规则是可修复的规则，表示如果在命令行中使用`--fix`参数的话，那么ESLint会自动修复这些规则所描述的问题。下面列出的规则中标注有`(可修复)`的表示此类规则。  

*注：规则说明下面如果有列表项的话，表示该规则可以使用的选项。除个别情况（valid-jsdoc等）外，大部分规则只可以使用一个选项。*  
**用前须知：本人英语和语文处于小学5年级水平!**

## 常见错误
下面列出的规则指出了你可能出现问题的地方。  

- [comma-dangle](http://eslint.org/docs/rules/comma-dangle)：不允许或强制在对象字面量或者数组属性的结尾使用逗号。(__推荐__)
	- `"always"`：必须在对象或者数组的每一个属性后面添加逗号。
	- `"never"`（默认）：不允许在对象或者数组的属性后面添加逗号。
	- `"always-multiline"`：单行的时候不允许添加逗号，多行属性的时候必须在属性后面添加逗号。
- [no-cond-assign](http://eslint.org/docs/rules/no-cond-assign)：条件判断语句中不允许赋值操作。(__推荐__)
	- `"except-parens"`（默认）：不允许赋值操作，除非写在一个括号里面
	- `"always"`：不允许所有情况的赋值
- [no-console](http://eslint.org/docs/rules/no-console)：不允许使用`console`中的所有方法。(__推荐__) 
- [no-constant-condition](http://eslint.org/docs/rules/no-constant-condition)：不允许在条件判断语句中使用常数。(__推荐__)
- [no-control-regex](http://eslint.org/docs/rules/no-control-regex)：正则表达式中不允许使用控制字符。(__推荐__)
- [no-debugger](http://eslint.org/docs/rules/no-debugger)：不允许使用`debugger`。(__推荐__)
- [no-dupe-args](http://eslint.org/docs/rules/no-dupe-args)：方法的参数中不允许有重复值。(__推荐__)
- [no-dupe-keys](http://eslint.org/docs/rules/no-dupe-keys)：定义对象时不允许有重复的键。(__推荐__)
- [no-duplicate-case](http://eslint.org/docs/rules/no-duplicate-case)：`switch`语句中不允许使用相同的`case`值。(__推荐__)
- [no-empty-character-class](http://eslint.org/docs/rules/no-empty-character-class)：不允许在正则表达式中使用空的字符类，即`/^abc[]/`。(__推荐__)
- [no-empty](http://eslint.org/docs/rules/no-empty)：不允许空的块语句。(__推荐__)
- [no-ex-assign](http://eslint.org/docs/rules/no-ex-assign)：不允许对`try...catch`语句中`catch`的参数赋值。(__推荐__)
- [no-extra-boolean-cast](http://eslint.org/docs/rules/no-extra-boolean-cast)：不允许多余的布尔值转换操作。如`!!!foo`或`!!bar ? baz : bat`等。(__推荐__)
- [no-extra-parens](http://eslint.org/docs/rules/no-extra-parens)：不允许在表达式外面套一层多余的括号。
	- `"all"`（默认）：不允许任何情况下出现的多余的括号。
	- `"functions"`：不允许`function`外面包裹多余的括号，其他表达式除外。
- [no-extra-semi](http://eslint.org/docs/rules/no-extra-semi)：不允许多余的分号。(__推荐__)(__可修复__)
- [no-func-assign](http://eslint.org/docs/rules/no-func-assign)：不允许为一个函数赋值。(__推荐__)
- [no-inner-declarations](http://eslint.org/docs/rules/no-inner-declarations)：函数或者变量的声明要放在程序的最外层或者另一个函数体内，不要在`if`等代码块中定义函数和变量。(__推荐__)
	- `"functions"`（默认）：仅限定函数不允许在代码块中定义。
	- `"both"`：限定函数和变量都不允许在代码块中定义。
- [no-invalid-regexp](http://eslint.org/docs/rules/no-invalid-regexp)：不允许在`RegExp`构造函数中传递不合法的正则表达式字符串。(__推荐__)
- [no-irregular-whitespace](http://eslint.org/docs/rules/no-irregular-whitespace)：不允许在字符串外面或者注释中使用不规则的空格。(__推荐__)
- [no-negated-in-lhs](http://eslint.org/docs/rules/no-negated-in-lhs)：在`in`运算的左侧操作数前不允许使用否定符号`!`。(__推荐__)
- [no-obj-calls](http://eslint.org/docs/rules/no-obj-calls):不允许将`Math`、`JSON`等全局的对象当做函数进行调用。(__推荐__)
- [no-regex-spaces](http://eslint.org/docs/rules/no-regex-spaces)：不允许在正则表达式中出现超过1个的连续空格。(__推荐__)
- [no-sparse-arrays](http://eslint.org/docs/rules/no-sparse-arrays)：不允许稀疏数组。(__推荐__)
- [no-unexpected-multiline](http://eslint.org/docs/rules/no-unexpected-multiline)：不允许两行连续但是不相关的代码作为一个连续表达式执行。
- [no-unreachable](http://eslint.org/docs/rules/no-unreachable)：不允许在`return`、`throw`、`continue`、`break`等中断语句之后出现代码，因为这些代码永远不会被执行到。(__推荐__)
- [use-isnan](http://eslint.org/docs/rules/use-isnan)：判断一个数是否是`NaN`的时候不允许使用`foo === NaN`这样的操作，而是使用`isNaN`函数进行判断。(__推荐__)
- [valid-jsdoc](http://eslint.org/docs/rules/valid-jsdoc)：不允许使用不合法的[JSDoc](http://usejsdoc.org/)注释。下列选项均可作为配置选项。
	- `"prefer"`：多个别名的注释标签中强制使用某一个。
	- `"requireReturn"`：函数和方法必须使用`@return`标签。
	- `"requireParamDescription"`：函数或者方法的`@param`标签必须含有参数描述。
	- `"requireReturnDescription"`：函数或者方法的`@return`标签必须含有返回值描述。
	- `"matchDescription"`：指定一个正则表达式在规范`JSDoc`的描述。
	- `"requireReturnType"`：必须为`@return`指定类型。
- [valid-typeof](http://eslint.org/docs/rules/valid-typeof)：`typeof`的结果必须和一个有效的字符串进行比较，如`typeof foo === 'strnig'`即是不合法的字符串。(__推荐__)

## 最好的练习
设计的这些规则都是阻止你犯错的。下面的规则要么是提出一种更好的实践，要么避免出现错误。

- [accessor-pairs](http://eslint.org/docs/rules/accessor-pairs)：在对象中`getter `和`setter`应该成对出现。
	- `"getWithoutSet"`：不允许只有`getter`而没有`setter`。
	- `"setWithoutGet"`：不允许只有`setter`而没有`getter`。
- [block-scoped-var](http://eslint.org/docs/rules/block-scoped-var)：不允许在代码块外使用在代码块内定义的变量。 
- [complexity](http://eslint.org/docs/rules/complexity)：限制代码层级的复杂度，如`if...else if...else`等。配置参数是一个数值，表示层级数量。
- [consistent-return](http://eslint.org/docs/rules/consistent-return)：当函数有分支的时候，确保所有的`return`要么都有返回值，要么都没有返回值。
- [curly](http://eslint.org/docs/rules/curly)：`if...else`、`while`等语句必须使用 大括号`{}`包括。
- [default-case](http://eslint.org/docs/rules/default-case)：`switch`代码块必须含有一个`default`分支。
- [dot-location](http://eslint.org/docs/rules/dot-location)：规定在书写对象的属性或方法时，`.`书写在属性所在行开始还是对象所在行的结束。
	- `"object"`（默认）：写在对象所在行的结尾位置。
	- `"property"`：写在属性或方法所在行的开始位置。
- [dot-notation](http://eslint.org/docs/rules/dot-notation)：建议使用`foo.bar`获取对象的属性，不推荐使用中括号法`foo["bar"]`。下列选项均可作为配置选项。
	- `"allowKeywords"`：关键字属性可以使用中括号法表示，如`foo['class']`。
	- `"allowPattern"`：指定正则表达式字符串，满足正则表达式的属性可以使用中括号法。 
- [eqeqeq](http://eslint.org/docs/rules/eqeqeq)：使用`===`和`!==`代替`==`和`!=`。(__可修复__)
	- `"smart"`：对比字面量值、对比`typeof`计算值或者和`null`对比的时候可以使用`==`或`!=`。
	- `"allow-null"`：和`null`比较的时候可以使用`==`或`!=`。
- [guard-for-in](http://eslint.org/docs/rules/guard-for-in)：`for...in...`语句代码块中必须使用`if`语句来判断对象的属性是否是从原型链上继承而来的。
- [no-alert](http://eslint.org/docs/rules/no-alert)：不允许使用`alert`、`confirm`和`prompt`方法。
- [no-caller](http://eslint.org/docs/rules/no-caller)：不允许使用`arguments.caller`或`arguments.callee`。
- [no-case-declarations](http://eslint.org/docs/rules/no-case-declarations)：不允许在`case`代码块中声明变量。如果确实需要声明变量的话，必须用`{}`包括。
- [no-div-regex](http://eslint.org/docs/rules/no-div-regex)：不允许正则表达式的开头看起来像是一个除号，如`/=bar/`，这样的写法类似`+=`、`-=`等，具有迷惑性，必须使用转义符号才可以`/\=bar/`。
- [no-else-return](http://eslint.org/docs/rules/no-else-return)：如果一个`if`语句含有`return`，就没有必要使用`else`语句块了，原本放在`else`语句块内的代码可以直接写在代码块外。
- [no-empty-label](http://eslint.org/docs/rules/no-empty-label)：`label`只能在迭代或者`seitch`语句之前使用。
- [no-empty-pattern](http://eslint.org/docs/rules/no-empty-pattern)：在结构赋值时，模式不能为空
- [no-eq-null](http://eslint.org/docs/rules/no-eq-null)：和`null`比较时，不允许使用`==`或`!=`，而是使用`===`或`!==`。
- [no-eval](http://eslint.org/docs/rules/no-eval)：不允许使用`eval`语句。
- [no-extend-native](http://eslint.org/docs/rules/no-extend-native)：不允许在原生对象的`prototype`上添加属性。
	- `"exceptions"`：数组，用于指定可以在原型链上添加属性的对象。
- [no-extra-bind](http://eslint.org/docs/rules/no-extra-bind)：避免在`function`上使用没有必要的`bind`。
- [no-fallthrough](http://eslint.org/docs/rules/no-fallthrough)：不允许`switch...case`出现“贯穿”情况，即一个`case`代码块执行过之后继续执行下一个`case`代码块。除非使用`break`、`return`、`throw`或者特殊注释等方法中断下一个`case`执行。(__推荐__)
- [no-floating-decimal](http://eslint.org/docs/rules/no-floating-decimal)：浮点数小数点前后必须有数字。
- [no-implicit-coercion](http://eslint.org/docs/rules/no-implicit-coercion)：不允许使用简写的类型转换方式，如`+foo`、`''+foo`，下列选项均可作为配置选项。
	- `"boolean"`：使用简写操作将变量转化为布尔类型时报错。
	- `"number"`：使用简写操作将变量转化为数字类型时报错。
	- `"string"`：使用简写操作将变量转化为字符串类型时报错。 
- [no-implied-eval](http://eslint.org/docs/rules/no-implied-eval)：不允许使用隐含的`eval`语句，例如`setTimeout('var foo=1;',10)`。 
- [no-invalid-this](http://eslint.org/docs/rules/no-invalid-this)：在严格模式下，不允许在类或者`class-like`的对象外面使用`this`关键字。
- [no-iterator](http://eslint.org/docs/rules/no-iterator)：不允许使用`__iterator__`属性。
- [no-labels](http://eslint.org/docs/rules/no-labels)：不允许使用`label`语句块。
- [no-lone-blocks](http://eslint.org/docs/rules/no-lone-blocks)：不允许使用没有必要的代码块。
- [no-loop-func](http://eslint.org/docs/rules/no-loop-func)：不允许在循环中声明函数。
- [no-magic-numbers](http://eslint.org/docs/rules/no-magic-numbers)：用变量代替数字。下列选项均可作为配置选项。
	- `"ignore"`：指定可以直接使用的数字。
	- `"enforceConst"`：所有数字强制使用常量。
	- `"detectObjects"`：检测对象中是否有属性是数字。
- [no-multi-spaces](http://eslint.org/docs/rules/no-multi-spaces)：在逻辑表达式、条件表达式、申明语句、数组元素、对象属性、sequences、函数参数等地方不使用超过一个的空白符。(__可修复__)
- [no-multi-str](http://eslint.org/docs/rules/no-multi-str)：不允许多行创建字符串。
- [no-native-reassign](http://eslint.org/docs/rules/no-native-reassign)：不允许对原生对象进行重写。
	- `"exceptions"`：指定可以被重写的元素对象。
- [no-new-func](http://eslint.org/docs/rules/no-new-func)：不允许使用`Function`构造函数创建函数。
- [no-new-wrappers](http://eslint.org/docs/rules/no-new-wrappers)：创建基本数据类型的时候不使用构造器函数生成。如`String`、`Number`、`Boolean`等。
- [no-new](http://eslint.org/docs/rules/no-new)：调用`new`关键字生成对象的时候，必须将生成的实例赋值给变量。
- [no-octal-escape](http://eslint.org/docs/rules/no-octal-escape)：不允许使用八进制转义。
- [no-octal](http://eslint.org/docs/rules/no-octal)：不允许使用八进制的语法。(__推荐__)
- [no-param-reassign](http://eslint.org/docs/rules/no-param-reassign)：不允许对函数的形参进行赋值。
	- `"props"`：设置为true的话，修改形参的属性也会报错。
- [no-process-env](http://eslint.org/docs/rules/no-process-env)：不允许使用`process.env`。
- [no-proto](http://eslint.org/docs/rules/no-proto)：不允许使用`__proto__ `属性。
- [no-redeclare](http://eslint.org/docs/rules/no-redeclare)：不允许重复定义变量。(__推荐__)
	- `"builtinGlobals"`：设置为`true`的时候也会检测全局定义的变量是否被重新定义了，如`Object`。
- [no-return-assign](http://eslint.org/docs/rules/no-return-assign)：在`return`语句中不进行赋值操作。
	- `"except-parens"`（默认）：赋值操作被括号括起来的时候不会报错。
	- `"always"`：在`return`语句中出现的任何形式的赋值都会报错。
- [no-script-url](http://eslint.org/docs/rules/no-script-url)：不允许使用`javascript:`这样的语句。如`location.href = "javascript:void(0)";`会报错。
- [no-self-compare](http://eslint.org/docs/rules/no-self-compare)：不允许和自身比较的比较操作。
- [no-sequences](http://eslint.org/docs/rules/no-sequences)：不允许使用逗号操作符。
- [no-throw-literal](http://eslint.org/docs/rules/no-throw-literal)：不允许使用`throw`抛出一个基本数据类型。由于静态检查代码，所以`throw foo;`并不会报错，因为无法确定`foo`是否是`Error`对象。
- [no-unused-expressions](http://eslint.org/docs/rules/no-unused-expressions)：不允许出现没有被使用的表达式或值。下列选项均可作为配置选项。
	- `"allowShortCircuit"`：设置为`true`的时候允许使用短路操作，如`a && b()`;
	- `"allowTernary"`：设置为`true`的时候，允许三元运算。
- [no-useless-call](http://eslint.org/docs/rules/no-useless-call)：不允许使用没必要的`.call()`和`.apply()`。
- [no-useless-concat](http://eslint.org/docs/rules/no-useless-concat)：不允许使用没有必要的字符串连接，如`"a"+"b"`。
- [no-void](http://eslint.org/docs/rules/no-void)：不允许使用`void`操作符。
- [no-warning-comments](http://eslint.org/docs/rules/no-warning-comments)：不允许使用含有警告提示信息的注释。下列选项均可作为配置选项。
	- `"terms"`：指定包含哪些字符为警告信息。默认`["todo", "fixme", "xxx"]`。
	- `"location"`：指定哪些位置的注释需要做匹配。默认是`"start"`。
- [no-with](http://eslint.org/docs/rules/no-with)：不允许使用`with`语句。
- [radix](http://eslint.org/docs/rules/radix)：调用`parseInt`函数的时候必须传递第二个参数指明进制。
	- `"always"`（默认）：必须传递第二个参数。
	- `"as-needed"`：10进制不需要传递。
- [vars-on-top](http://eslint.org/docs/rules/vars-on-top)：变量要在其所在作用域的最开始声明。
- [wrap-iife](http://eslint.org/docs/rules/wrap-iife)：立即执行函数需要使用括号包裹。
	- `"outside"`（默认）：括号包裹在调用外层。如`(function(){}())`。
	- `"inside"`：括号包裹在函数外层。如`(function(){})()`。
	- `"any"`：上述两种风格都可以。
- [yoda](http://eslint.org/docs/rules/yoda)：比较运算中，对象字面量应该写在比较操作符的左边，而变量应该写在比较操作符的右边。
	- `"never"`（默认）：字面量必须在右边。
	- `"always"`：字面量必须在左边。  
	_其他特殊情况，写在规则配置数组的第三个元素位置。_
	- `"exceptRange"`：设置为`true`时，表示范围判断的不需要遵守左右。
	- `"onlyEquality"`：设置为`true`时，表示只有当等于判断时才需要遵守左右。

## 严格模式
这些规则和严格模式有关系。

- [strict](http://eslint.org/docs/rules/strict)：在文件头部或者函数的开始部分使用`"use strict";` 即可开启严格模式。
	- `"never"`：不允许使用严格模式。
	- `"global"`：只允许在全局使用严格模式。
	- `"function"`：只允许在函数开始部分使用严格模式。

## 变量 
这些规则主要是和变量声明有关的。

- [init-declarations](http://eslint.org/docs/rules/init-declarations)：指定变量在定义的时候是否要赋值。
	- `"always"`（默认）：所有变量声明的时候必须赋值。
	- `"never"`：所有变量声明的时候不能赋值，`const`定义的常量除外。  
	下列选项均可额外配置。
	- `"ignoreForLoopInit"`：设置为`true`的时候忽略`for`循环中的变量定义。
- [no-catch-shadow](http://eslint.org/docs/rules/no-catch-shadow)：不在`catch`语句外面的作用域定于和`catch`语句参数同名的变量。
- [no-delete-var](http://eslint.org/docs/rules/no-delete-var)：不允许使用`delete foo`删除变量。(__推荐__)
- [no-label-var](http://eslint.org/docs/rules/no-label-var)：不允许有和某一个`label`同名的变量。
- [no-shadow-restricted-names](http://eslint.org/docs/rules/no-shadow-restricted-names)：声明变量不能覆盖JavaScript中的保留关键字。
- [no-shadow](http://eslint.org/docs/rules/no-shadow)：不允许在当前作用域内定义作用域外已有的同名变量。下列选项均可作为配置选项。
	- `"builtinGlobals"`：设置为`true`的时候，全局变量也不允许重复定义，如`var Object`报错。
	- `"hoist"`：什么情况下定义的变量会报错。有下列三个选项可选。
		- `"all"`：外层作用域中的变量和方法都不允许重新定义
		- `"function"`（默认）：外层作用域中的方法不允许重新定义
		- `"never"`：外层作用域中的变量和方法都可以再重新定义
	- `"allow"`：定义哪些变量是可以重复定义的，一个数组。
- [no-undef-init](http://eslint.org/docs/rules/no-undef-init)：不允许直接将一个变量定义为`undefined`，如`var foo = undefined;`。
- [no-undef](http://eslint.org/docs/rules/no-undef)：不允许使用没有定义的变量。(__推荐__)
	- `"typeof"`：设置为`true`时，执行`typeof`的变量也必须定义。
	- 通过添加注释`/*global foo*/`定义`foo`变量，但是这样定义的变量是只读的。使用`/*global foo:true*/`定义的`foo`变量就不是只读了。
- [no-undefined](http://eslint.org/docs/rules/no-undefined)：不允许使用`undefined`作为变量名或者函数形参。
- [no-unused-vars](http://eslint.org/docs/rules/no-unused-vars)：不允许出现定义了但是没有使用的变量。下列选项均可作为配置选项。(__推荐__)
	- `"vars"`：设置哪些变量可以定义了不使用。有下列两个选项可选。
		- `"all"`（默认）：所有的被定义的变量都必须使用，包括全局的变量。
		- `"local"`：所有本地的变量定义之后必须使用，全局的变量可以不使用。
	- `"args"`：设置函数的参数是否需要都使用。有下列三个选项可选。
		- `"all"`：所有的参数都必须被使用。
		- `"after-used"`（默认）：以被使用的最后一个参数为准，该参数之后的参数会警告没有被使用，之前的参数即使没有被使用也不报错。如`function(a,b){console.log(b);}`这样不会报错。
		- `"none"`：所有的参数都可以不被使用。
	- `"varsIgnorePattern"`：满足该正则的所有参数不会被检测是否被使用。
	- `"argsIgnorePattern"`：满足改正则的所有函数的参数不会被检测是否被使用。
- [no-use-before-define](http://eslint.org/docs/rules/no-use-before-define)：变量应该先定义后使用。
	- `"nofunc"`：函数可以在起定义之前调用。但用法必须是`function foo(){}`，而不能是`var foo = function(){};`。

## Node.js和CommonJS
这些规则是特定应用于运行在Node.js或者浏览器中CommonJS规范的代码。

- [callback-return](http://eslint.org/docs/rules/callback-return)：执行`callback`回调函数的时候必须使用`return`，函数最后调用回调函数的不需要添加`return`。
	- `[]`：数组，指定哪些是表示回调的函数。如`["callback", "cb", "next"]`。
- [global-require](http://eslint.org/docs/rules/global-require)：Node.JS中`require()`方法必须在最外层的作用域进行调用。
- [handle-callback-err](http://eslint.org/docs/rules/handle-callback-err)：回调函数中必须进行错误处理。默认的代表错误变量的参数是`err`。
	- `""`：字符串。指定代表错误变量的参数。如`error`。如果字符串以`^`开头，表示一个正则，如`^.*(e|E)rr`。
- [no-mixed-requires](http://eslint.org/docs/rules/no-mixed-requires)：调用`require()`方法不和其他变量声明或者`require()`混合使用。也就是require多个模块的生活不要使用同一个`var`，即`var fs=require('fs'),path=require('path');`是不允许的。
	- `{"grouping": true}`：默认grouping是开启的，也就是不允许混合使用，设置为`false`就可以是用混合了。
- [no-new-require](http://eslint.org/docs/rules/no-new-require)：不允许使用`new require()`。
- [no-path-concat](http://eslint.org/docs/rules/no-path-concat)：不允许使用`__dirname+"foo.js"`或`__filename+"bar.html"`这样拼接路径，建议使用`path.join`或者`path.resolve`方法。
- [no-process-exit](http://eslint.org/docs/rules/no-process-exit)：不允许使用`process.exit()`方法。
- [no-restricted-modules](http://eslint.org/docs/rules/no-restricted-modules)：限制使用某些模块。
	- `[]`：被限制的模块名称数组。如`['fs','path']`。
- [no-sync](http://eslint.org/docs/rules/no-sync)：不允许使用同步方法，如`fs.readFileSync()`等。

## 格式上的问题
这些规则是纯粹的风格化，使用因人而异。

- [array-bracket-spacing](http://eslint.org/docs/rules/array-bracket-spacing)：数组的`[`之后和`]`之前是否有空格。(__可修复__)
	- `"never"`（默认）：`[`之后和`]`之前不允许有空格。
	- `"always"`：`[`之后和`]`之前必须有空格。  
	_其他特殊情况，写在规则配置数组的第三个元素位置。_   
	- `"singleValue"`：当只有一个元素的时候是否需要使用空格。如`[ 2 ]`或`[{a:2}]`在规则配置为`[2, "always", { singleValue: false }]`时仍然会报错。`[2]`在配置为`[2, "never", { singleValue: true }]`的规则时也会报错。
	- `"objectsInArrays"`：当元素是对象的时候是否需要使用空格，用法同上。
	- `"arraysInArrays"`：当元素是数组的时候是否需要空格，用法同上。
- [block-spacing](http://eslint.org/docs/rules/block-spacing)：对象写在单行的时候是否需要在`{`之后和`}`之前加空格。(__可修复__)
	- `"always"`：必须加空格。
	- `"never"` ：不允许添加空格。
- [brace-style](http://eslint.org/docs/rules/brace-style)：大括号的样式和缩进样式，该规则主要是用来描述大括号在控制语句中的位置。
	- `"1tbs"`（默认）：不要把大括号单独写一行，大括号应该放在与之相对应的语句或者声明语句中。
	- `"stroustrup"`：`if`、`else`、`catch`等应该重起一行书写。
	- `"allman"`：所有的大括号都应该在单独的一行书写。
	_其他特殊情况，写在规则配置数组的第三个元素位置。_   
	- `"allowSingleLine"`：设置`true`或`false`表明大括号的`{`和`}`能否在同一行。
- [camelcase](http://eslint.org/docs/rules/camelcase)：是否使用驼峰命名法。
	- `"Properties"`：是否对对象的属性使用该规则。
		- `"always"`（默认）：检查所有的对象属性名，必须满足驼峰命名法。
		- `"never"`：不检查对象的属性名。
- [comma-spacing](http://eslint.org/docs/rules/comma-spacing)：逗号前后是否添加空格。(__可修复__)
	- `"before"`：逗号前面是否添加空格。
		- `"true"`：必须有空格。
		- `"false"`（默认）：不允许有空格。
	- `"after"`：逗号之后是否添加空格。
		- `"true"`（默认）：必须有空格。
		- `"false"`：不允许有空格。	 
- [comma-style](http://eslint.org/docs/rules/comma-style)：设置逗号放置的位置。
	- `"first"`：逗号放在行首。
	- `"last"`（默认）：逗号放在行尾。  
	_其他特殊情况，写在规则配置数组的第三个元素位置。_   
	- `"exceptions"`：设置意外情况，有下列三个选项可配置，取值为`true`和`false`。
		- `"ArrayExpression"`：`true`表示忽略数组中的逗号设置。
		- `"ObjectExpression"`：`true`表示忽略对象中的逗号设置。
		- `"VariableDeclaration"`：`true`表示忽略声明变量的逗号设置。
- [computed-property-spacing](http://eslint.org/docs/rules/computed-property-spacing)：规定是否在对象的[动态属性](http://babeljs.io/docs/learn-es2015/#destructuring)中添加空格。(__可修复__)
	- `"never"`（默认）：不允许在计算动态属性中添加空格，如`var x = {[ b ]: a}`会报错。
	- `"always"`：计算动态属性中必须添加空格。
- [consistent-this](http://eslint.org/docs/rules/consistent-this)：指定哪些变量可以赋值为`this`。被指定为`this`别名的变量不能被赋予其他值，`this`也只能赋值到这些指定的别名变量上且变量必须在定义的作用域内被赋值，如下代码是错误的。

	```
	"consistent-this": [2, "self"]
	
	var self;
	function foo(){
		self = this;
	}
	```
	- `"xxx"`：指定别名。
- [eol-last](http://eslint.org/docs/rules/eol-last)：文件最后必须有一行空行。(__可修复__)
- [func-names](http://eslint.org/docs/rules/func-names)：方法必须有名字，也就是不允许匿名方法。
- [func-style](http://eslint.org/docs/rules/func-style)：指定使用哪种函数声明方式，即函数申明和函数表达式。
	- `"declaration"`：指定使用函数申明方式创建函数。
	- `"expression"`：指定使用函数表达式创建函数。  
	_其他特殊情况，写在规则配置数组的第三个元素位置。_  
	- `"allowArrowFunctions"`：是否允许ES2015的[箭头函数](https://babeljs.io/docs/learn-es2015/#arrows-and-lexical-this)，当设置为`true`的时候，即使配置为`"declaration"`也是合法的。
- [id-length](http://eslint.org/docs/rules/id-length)：规定标识符的长短，默认最小是2个字符，因为标示符设置太短的话，不利于理解。
	- `"min"`（默认为2）：定义标识符的最小长度。
	- `"max"`（默认无穷大）：定义标识符的最大长度。
	- `"properties"`：是否检查对象属性名。有下列两个值可选。
		- `"always"`（默认）：检查所有对象的属性名
		- `"never"`：对象的变量名不受改规则影响。 
	- `"exceptions"`：定义特殊的标示符数组，这些标示符不受规则影响。
- [id-match](http://eslint.org/docs/rules/id-match)：规定标示符必须符合一定的书写规则。
	- `"xxx"`：描述标示符必须符合的正则表达式。  
	_其他特殊情况，写在规则配置数组的第三个元素位置。_  
	- `"properties"`：对象的属性名是否受影响。取值为`true`或`false`（默认）。
- [indent](http://eslint.org/docs/rules/indent)：规定代码的缩进方式。默认是4个空格。(__可修复__)
	- `"tab"/2`：数字或者`"tab"`数字的话，指定使用几个空格，`"tab"`表示使用tab表示缩进。
	- `{}`：配置可选的验证
		- `"SwitchCase"`：`switch...case`语句的缩进标准，默认是0，也就是上一个配置项设置的缩进的倍数，如下代码不会报错。

		```
		/*eslint indent: [2, 2, {"SwitchCase": 2}]*/
		
		switch(a){
		    case "a":          
		      break;
		    case "b":         
		      break;
		}

		```
		- `"VariableDeclarator"`：指定变量缩进的标准，计算方法类似`"SwitchCase"`，也可以分别对变量标示符进行设置，如`{ "var": 2, "let": 2, "const": 3}`。下面的代码不会报错。

		```
		/* eslint indent: [2, 2, {
				"VariableDeclarator": { "var": 2, "let": 2, "const": 3}
			}] */
		var a,
    	    b,
		    c;
		let a,
		    b,
		    c;
		const a = 1,
		      b = 2,
		      c = 3;
		```
- [jsx-quotes](http://eslint.org/docs/rules/jsx-quotes)：规定JSX语法中，属性使用单引号还是双引号。
	- `"prefer-double"`（默认）：使用双引号。
	- `"prefer-single"`：使用单引号。
- [key-spacing](http://eslint.org/docs/rules/key-spacing)：规定对象字面量中的键值对之间是否有空格。
	- `"beforeColon"`：冒号前是否需要空格。默认`false`。
	- `"afterColon"`：冒号之后是否需要空格。默认`true`。
	- `"mode"`：指定空格的数量。可选配置如下。
		- `"strict"`（默认）：允许使用一个空格。
		- `"minimum"`：允许最少一个空格。
	- `"align"`：取值为`"value"`，表示值对齐。
- [linebreak-style](http://eslint.org/docs/rules/linebreak-style)：规定换行的方式，'LF'和 'CRLF'不能混合使用。
	- `"unix"`：使用Unix风格的换行，也就是`LF`。
	- `"windows"`：使用Windows风格的换行，也就是`CRLF`。
- [lines-around-comment](http://eslint.org/docs/rules/lines-around-comment)：规定注释和代码之间的空行。可选配置如下。
	- `"beforeBlockComment"`（默认为`true`）：`/*xxx*/`块注释之前必须有空行。
	- `"afterBlockComment"`：块注释之后必须有空行。
	- `"beforeLineComment"`：`//xxx`行注释之前必须有空行。
	- `"afterLineComment"`：行注释之后必须有空行。  
	_其他特殊配置_
  	- `"allowBlockStart"`：当设置为`true`的时候，表示允许注释在任何代码块的开始的位置，这时即使设置`"beforeLineComment"`或`"beforeBlockComment"`不生效。 
	- `"allowBlockEnd"`：当设置为`true`的时候，表示允许注释在任何代码块的结尾的位置。`"afterBlockComment"`和`"afterLineComment"`不生效。
	- `"allowObjectStart"`：当设置为`true`的时候，表示允许注释在任何对象的开始的位置，这时即使设置`"beforeLineComment"`或`"beforeBlockComment"`不生效。 
	- `"allowObjectEnd"`：当设置为`true`的时候，表示允许注释在任何对象的结尾的位置。`"afterBlockComment"`和`"afterLineComment"`不生效。
	- `"allowArrayStart"`：当设置为`true`的时候，表示允许注释在任何数组的开始的位置，这时即使设置`"beforeLineComment"`或`"beforeBlockComment"`不生效。
	- `"allowArrayEnd"`：当设置为`true`的时候，表示允许注释在任何数组的结尾的位置。`"afterBlockComment"`和`"afterLineComment"`不生效。
- [max-depth](http://eslint.org/docs/rules/max-depth)：规定代码最大的嵌套层次。设置数字，默认为4。
- [max-len](http://eslint.org/docs/rules/max-len)：规定单行代码最大长度。
	- `{number}`：设置tab缩进，配置在规则的第三个参数。
	_其他特殊情况，写在规则配置数组的第四个元素位置。_   
	- `"ignoreComments"`：是否忽略注释。
	- `"ignoreUrls"`：是否忽略链接地址。
	- `"ignorePattern"`：设置正则表达式，匹配到该正则的代码会被忽略。
- [max-nested-callbacks](http://eslint.org/docs/rules/max-nested-callbacks)：规定回调函数最大的嵌套层次。类似于[max-depth](http://eslint.org/docs/rules/max-depth)
- [max-params](http://eslint.org/docs/rules/max-params)：规定函数参数的最大数量。
- [max-statements](http://eslint.org/docs/rules/max-statements)：规定函数中可以声明的变量的最大个数。
- [new-cap](http://eslint.org/docs/rules/new-cap)：规定作为构造函数的函数名首字母必须大写，不作为构造函数的首字母必须小写。
	- `"capIsNewExceptions"`：数组。指明一些首字母大写，但是不是构造函数的函数名，首字母必须大写，如`["Person"]`。默认值是`["Array","Boolean","Date",...]`。
	- `"newIsCapExceptions"`：数组。指明一些构造函数，首字母是小写的，如`["person"]`。这些函数会被作为构造函数使用。
	- `"newIsCap"`：默认为`true`，表示检测所有的使用`new`运算符的函数必须是首字母大写的。`"newIsCapExceptions"`配置项里设置的除外。
	- `"capIsNew"`：默认为`true`，表示检测所有没有使用`new`的函数首字母必须是小写的。`"capIsNewExceptions"`配置项里设置的除外。
- [new-parens](http://eslint.org/docs/rules/new-parens)：不允许在调用构造函数的时候遗漏`()`，即`new Person`是不合法的。
- [newline-after-var](http://eslint.org/docs/rules/newline-after-var)：规定声明变量之后是否需要空一行在开始其他代码。
	- `"always"`（默认）： 必须空一行。
	- `"never"`：不允许空行。
- [no-array-constructor](http://eslint.org/docs/rules/no-array-constructor)：不允许使用`Array`构造函数创建数组。
- [no-bitwise](http://eslint.org/docs/rules/no-bitwise)：不允许使用位操作符，如`|`、`^`、`~`、`>>`、`<<`等。
- [no-continue](http://eslint.org/docs/rules/no-continue)：不允许使用`continue`语句。
- [no-inline-comments](http://eslint.org/docs/rules/no-inline-comments)：不允许在代码同一行内添加注释。
- [no-lonely-if](http://eslint.org/docs/rules/no-lonely-if)：不允许在`else`语句中只出现一个单独的`if`语句，如下代码。

	```
	if(){
	    //...
	} else {
	    if(){
	        //...
	    }
	}
	```
- [no-mixed-spaces-and-tabs](http://eslint.org/docs/rules/no-mixed-spaces-and-tabs)：不要空格和`tab`混合使用进行缩进。(__推荐__)
	- `"smart-tabs"`：当配置该选项之后，如果空格仅仅是用作对齐的话，并不会报错。通过配置`[2, "smart-tabs"]`开启改选项。
- [no-multiple-empty-lines](http://eslint.org/docs/rules/no-multiple-empty-lines)：规定连续空行的数量。
	- `"max"`：设置连续空行最大数量。
	- `"maxEOF"`：规定文件末尾空行最大数量。
- [no-negated-condition](http://eslint.org/docs/rules/no-negated-condition)：在`if`语句中使用了否定表达式，同时`else`语句又不为空，那么这样的`if-else`语句将被视为不合法的，可以将其反过来，该规则同样使用三元操作符。
- [no-nested-ternary](http://eslint.org/docs/rules/no-nested-ternary)：不允许嵌套三元运算符。
- [no-new-object](http://eslint.org/docs/rules/no-new-object)：不允许使用`new Object()`这样的写法。
- [no-plusplus](http://eslint.org/docs/rules/no-plusplus)：不允许使用`++`和`--`运算符。
	- `"allowForLoopAfterthoughts"`：设置为`true`的时候，`for`循环中出现的`++`或`--`操作不会视为错误。
- [no-restricted-syntax](http://eslint.org/docs/rules/no-restricted-syntax)：不允许使用某些语法。
	- `"FunctionExpression"`：不允许使用函数表达式声明函数。
	- `"WithStatement"`：不允许使用`with`语句。用法`[2, "FunctionExpression", "WithStatement"]`。
- [no-spaced-func](http://eslint.org/docs/rules/no-spaced-func)：函数调用时，允许函数名和括号之间出现空格。(__可修复__)
- [no-ternary](http://eslint.org/docs/rules/no-ternary)：不允许三元运算符。
- [no-trailing-spaces](http://eslint.org/docs/rules/no-trailing-spaces)：行末不允许出现空格。(__可修复__)
	- `"skipBlankLines"`：当设置为`true`的时候，表示忽略空行内的末尾空格。通过`[2, { "skipBlankLines": true }]`开启该配置项。
- [no-underscore-dangle](http://eslint.org/docs/rules/no-underscore-dangle)：不允许在标示符前后使用下划线。
	- `"allow"`：数组，指定哪些标示符是可以添加下划线的，如`[2, { "allow": ["foo_", "_bar"] }]`。
- [no-unneeded-ternary](http://eslint.org/docs/rules/no-unneeded-ternary)：不允许使用没有必要的三元操作符。如`bar ? bar : 1;`。
	- `"defaultAssignment"`（默认为`true`）：默认赋值。设置为`true`的时候，`x ? x : 1;`的语法会报错，`false`的时候不会报错。
- [object-curly-spacing](http://eslint.org/docs/rules/object-curly-spacing)：定义对象字面量的时候`{`之后和`}`之前是否要加空格。
	- `"never"`（默认）：不允许出现空格。
	- `"always"`：必须有空格。
- [one-var](http://eslint.org/docs/rules/one-var)：规定在一个作用域内是否只使用一个`var`或`let`或`const`。
	- `"always"`(默认)：只能使用一个`var`或`let`或`const`。
	- `"never"`：每一个变量需要一个`var`来声明。  
	_以上配置项使用`"one-var": [2, "always"]`的方法来配置，还有一种方式，通过配置一个对象。可选配置如下_   
	- `"var"`：以`var`是否可以多次使用定义变量，可选`always`和`never`。
	- `"let"`：以`let`是否可以多次使用定义变量，可选`always`和`never`。
	- `"const"`：以`const`是否可以多次使用定义变量，可选`always`和`never`。  
	_除了上述三个配置用于针对不同的变量定义符，还可以按照变量是否初始化进行配置。_  
	- `"uninitialized"`：未初始化的变量使用一个`var`，如`var a, b, c;`。
	- `"initialized"`：初始化了值的变量使用多个`var`，如`var foo = true;var bar = false;`。
- [operator-assignment](http://eslint.org/docs/rules/operator-assignment)：规定赋值操作符的简写，如`foo += bar;`。
	- `"always"`：必须使用简写方式。
	- `"never"`：不允许出现简写方式。
- [operator-linebreak](http://eslint.org/docs/rules/operator-linebreak)：换行时，操作符应该写在行首还是行尾。
	- `"after"`（默认）：写在行尾。
	- `"before"`：写在行首。
	- `"none"`：行首行尾都不对，也就是不换行。    
   _其他特殊情况，写在规则配置数组的第三个元素位置。_   
   - `"overrides"`：指定一些运算符特殊情况。如`[2, "before", { "overrides": { "?": "after", "+=": "none" } }]`。
- [padded-blocks](http://eslint.org/docs/rules/padded-blocks)：规定代码块前后是否要加空行。
	- `"always"`（默认）：必须加空行。
	- `"never"`：不允许加空行。
- [quote-props](http://eslint.org/docs/rules/quote-props)：对象的属性名是否需要加引号。
	- `"always"`（默认）：需要添加引号。
	- `"as-needed"`：确实需要的时候添加引号，不需要的时候如果也添加了引号，会报错。
	- `"consistent"`：整个对象保持一致，加引号就都加，不加就都不加。
	- `"consistent-as-needed"`：视情况保持一致，如果有一个属性必须加引号，如`foo-bar`，那么整个对象都必须加，如果都比要加引号，就不必要加了。  
	_当第二个参数设置为`"as-needed"`的时候，下列配置可以写在规则配置数组的第三个元素位置。_    
	- `"keywords"`（默认为`false `）：关键词是否需要添加引号，取值为`true`或`false`。
	- `"unnecessary"`（默认为`true`）：不必要添加引号的属性添加了之后是否报错。
	- `"numbers"`：数字的属性名是否需要引号。取值为`true`或`false`。  
	_当第二个参数设置为`"consistent-as-needed"`的时候，下列配置可以写在规则配置数组的第三个元素位置。_    
	- `"keywords"`：（默认为`false `）：关键词是否需要添加引号，取值为`true`或`false`。
- [quotes](http://eslint.org/docs/rules/quotes)：规定使用单引号、双引号还是反义符（ES2015）。(__可修复__)
	- `"double"`（默认）：使用双引号。
	- `"single"`：使用单引号。
	- `"backtick"`：使用反义符。如\`string\`。  
	_下列配置可以写在规则配置数组的第三个元素位置作为额外配置。_   
	- `"avoid-escape"`：设置该配置项的话，下面代码不会报错。
	
	```
	var str = 'a string containing "double" quotes';
	```
- [require-jsdoc](http://eslint.org/docs/rules/require-jsdoc)：注释要求是[JSDoc](http://usejsdoc.org/)格式。
	- `"FunctionDeclaration"`（默认为`true`）：设置为`true`表示定义函数必须添加JSDoc。
	- `"ClassDeclaration"`（默认为`false`）：设置为`true`表示定义类必须添加JSDoc。
	- `"MethodDefinition"`（默认为`false `）：设置为`true`表示定义方法必须添加JSDoc。		
	
	```
	上述规则通过下列代码进行配置
	"require-jsdoc": [2, {
        "require": {
            "FunctionDeclaration": true,
            "MethodDefinition": false,
            "ClassDeclaration": false
        }
    }]
	```
- [semi-spacing](http://eslint.org/docs/rules/semi-spacing)：定义分号前后是否需要添加空格。配置如`"semi-spacing": [2, {"before": false, "after": true}]`。
	- `"before"`（默认`false`）：分号之前是否需要添加空格。
	- `"after"`（默认`true`）：分号之后是否需要添加空格。
- [semi](http://eslint.org/docs/rules/semi)：分号党和无分号党之争 ：）(__可修复__)
	- `"always"`（默认）：分号党万岁！
	- `"never"`：无分号才是王道。	 
- [sort-vars](http://eslint.org/docs/rules/sort-vars)：定义按照顺序声明变量，如`var a,b,c;`而不是`var b,c,a;`。
	- `"ignoreCase"`：设置为`true`的时候表示忽略变量名大小写。
- [space-after-keywords](http://eslint.org/docs/rules/space-after-keywords)：关键词之后是否需要空格。(__可修复__)
	- `"always"`（默认）：必须添加空格。	 
	- `"never"`：不允许添加空格。
- [space-before-blocks](http://eslint.org/docs/rules/space-before-blocks)：规定在代码块之前是否需要加空格。(__可修复__)
	- `"always"`（默认）：必须添加空格。	 
	- `"never"`：不允许添加空格。  
	*除了上述配置，还可以有下面配置对象。*  
	- `"functions"`：函数代码块之前是否需要空格。可选`always`和`never`。
	- `"keywords"`：关键词（如`if`、`else`、`switch`等）代码块之前是否需要空格。可选`always`和`never`。
- [space-before-function-paren](http://eslint.org/docs/rules/space-before-function-paren)：函数定义的小括号`()`之前是否需要加空格。(__可修复__)
	- `"always"`（默认）：必须添加空格。	 
	- `"never"`：不允许添加空格。  
	*除了上述配置，还可以有下面配置对象。*  
	- `"anonymous"`：匿名函数的`()`之前是否需要空格。可选`always`和`never`。
	- `"named"`：具名函数的`()`之前是否需要空格。可选`always`和`never`。
- [space-before-keywords](http://eslint.org/docs/rules/space-before-keywords)：规定关键字前面是否加空格，包括的关键字有：`if`， `else`， `for`， `while`， `do`， `switch`， `throw`， `try`， `catch`， `finally`，`with`，`break`， `continue`， `return`， `function`， `yield`， `class`。(__可修复__)
	- `"always"`（默认）：必须添加空格。	 
	- `"never"`：不允许添加空格。 
- [space-in-parens](http://eslint.org/docs/rules/space-in-parens)：规定括号内部的空格。规定是否需要在(右边，或者)左边加空格。但是无论哪一种要求，() 写法都是可以的。(__可修复__)
	- `"always"`：必须添加空格。	 
	- `"never"`（默认）：不允许添加空格。   
	_其他特殊情况，写在规则配置数组的第三个元素位置。_   
	- `"exceptions"`：数组，定义哪些是不需要符合规则的，有下列配置项。
		- `"{}"`：括号内有`{}`的话表示不需要遵守规则。
		- `"[]"`：括号内有`[]`的话表示不需要遵守规则。
		- `"()"`：括号内有`()`的话表示不需要遵守规则。
		- `"empty"`：括号内为空的话表示不需要遵守规则。
- [space-infix-ops](http://eslint.org/docs/rules/space-infix-ops)：规定操作符左右是否需要添加空格。(__可修复__)
	- `"int32Hint"`（默认为`false`）：设置为`true`的时候，表示`a|0`这样的运算不需要添加空格。
- [space-return-throw-case](http://eslint.org/docs/rules/space-return-throw-case)：规定`return`，`throw`和`case`之后加一个空格。(__可修复__)
- [space-unary-ops](http://eslint.org/docs/rules/space-unary-ops)：规定在一元操作符前后是否加空格。(__可修复__)
	- `"words"`：应用于关键词操作符，如`delete`，`typeof`，`void`等。 
	- `"nonwords"`：应用于一元操作符，如`++`，`--`，`!!`。
- [spaced-comment](http://eslint.org/docs/rules/spaced-comment)：规定是否需要在代码注释符号（`//`和`/*`）后面加一个空格。
	- `"always"`（默认）：必须添加空格。	 
	- `"never"`：不允许添加空格。   
	_其他特殊情况，写在规则配置数组的第三个元素位置。_   
	- `"markers"`：指定标识来指定哪些注释是不需要符合规则的。
	- `"exceptions"`：数组，如果注释符合是该项配置中的字符串，会忽略配置规则。

	```
	规则配置如下
	"spaced-comment": [2, "always", {
	    "line": {
	        "markers": ["/"],
	        "exceptions": ["-", "+"]
	    },
	    "block": {
	        "markers": ["!"],
	        "exceptions": ["*"]
	    }
	}]
	```
- [wrap-regex](http://eslint.org/docs/rules/wrap-regex)：要求在正则表达式的双斜杠外面加一个圆括号，来消除歧义。如`/foo/.test("bar")`是不合法的，必须是`(/foo/).test("bar")`。

## ECMAScript6(ES2015)
下列的规则都是和ES6语法相关的规则。		

- [arrow-body-style](http://eslint.org/docs/rules/arrow-body-style)：箭头函数的函数体必须使用`{}`包括。
	- `"always"`：强制所有的箭头函数的函数体使用`{}`。
	- `"as-needed"`（默认）：视情况而定是否需要大括号。
- [arrow-parens](http://eslint.org/docs/rules/arrow-parens)：箭头函数的参数必须有括号包裹。
	- `"always"`（默认）：强制使用圆括号包裹参数。
	- `"as-needed"`：视情况而定是否需要圆括号。
- [arrow-spacing](http://eslint.org/docs/rules/arrow-spacing)：箭头函数的“箭头”`=>`前后是否需要空格。如`[2,{ "before": true, "after": true }]`。(__可修复__)
	- `"before"`（默认`true `）：`=>`之前是否需要添加空格。
	- `"after"`（默认`true`）：`=>`之后是否需要添加空格。
- [constructor-super](http://eslint.org/docs/rules/constructor-super)：继承父类的类必须在构造函数中调用`super`。	
- [generator-star-spacing](http://eslint.org/docs/rules/generator-star-spacing)：规定`generator`函数中`*`前后的空白。(__可修复__)
	- `"before"`（默认`true `）：`*`之前是否需要添加空格。
	- `"after"`（默认`false `）：`*`之后是否需要添加空格。  
	*下列简写对应不同的`before`和`after`的搭配*  
	- `"before"`等同于`{"before": true, "after": false}`
	- `"after"`等同于`{"before": false, "after": true}`
	- `"both"`等同于`{"before": true, "after": true}`
	- `"neither"`等同于`{"before": false, "after": false}`   
	也就是说下面两个的配置等同  
	
	```
	"generator-star-spacing": [2, {"before": true, "after": true}]
	"generator-star-spacing": [2, "both"]
	```
- [no-arrow-condition](http://eslint.org/docs/rules/no-arrow-condition)：在条件语句中禁止使用箭头函数，因为箭头函数的`=>`和大于等于符号`=>`很容易混淆。
- [no-class-assign](http://eslint.org/docs/rules/no-class-assign)：禁止重命名classes名。
- [no-const-assign](http://eslint.org/docs/rules/no-const-assign)：禁止修改`const`定义的常量。
- [no-dupe-class-members](http://eslint.org/docs/rules/no-dupe-class-members)：class中的成员不允许有相同的名字。
- [no-this-before-super](http://eslint.org/docs/rules/no-this-before-super)：继承父类的类的构造函数中，调动`super()`之前不允许使用`this/super`。
- [no-var](http://eslint.org/docs/rules/no-var)：不要使用`var`来定义变量，使用`let`和`const`。
- [object-shorthand](http://eslint.org/docs/rules/object-shorthand)：对象字面量中使用简写。
	- `"always"`（默认）：所有地方都使用简写。
	- `"methods"`：只有对象中的方法使用简写。
	- `"properties"`：只有对象中的属性值使用简写。
	- `"never"`：任何地方都不使用简写。
- [prefer-arrow-callback](http://eslint.org/docs/rules/prefer-arrow-callback)：要求在回调函数需是箭头函数，也就是说函数作为函数的参数传入时，传入的函数需要时箭头函数。
- [prefer-const](http://eslint.org/docs/rules/prefer-const)：如果一个变量申明后就不再被修改，那么使用const来申明该变量。
- [prefer-reflect](http://eslint.org/docs/rules/prefer-reflect)：推荐使用Reflect上的方法替代以前老方法。
	- `"exceptions"`：数组，指定哪些是不需要被替代的。如`{exceptions:["getPrototypeOf"] }`
- [prefer-spread](http://eslint.org/docs/rules/prefer-spread)：建议使用`spread`操作来替代`.apply()`。
- [prefer-template](http://eslint.org/docs/rules/prefer-template)：建议使用模板字符串处理字符串拼接。
- [require-yield](http://eslint.org/docs/rules/require-yield)：`generates`函数中必须有`yield`。

## 被移除的
这些规则在早起的ESLint版本中使用，但是现在都有新的规则作为替代。
因为已经被移除了，所以没有罗列，可以去官网[查看](http://eslint.org/docs/rules/#removed)。