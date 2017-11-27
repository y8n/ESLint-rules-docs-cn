# [ESLint-angular-rules](https://github.com/Gillespie59/eslint-plugin-angular) #


eslint-plugin-angular中的规则分成了多个不同的分类，能帮助你更好的理解他们代表的含义。

### 可能的错误
下面的规则检查模式会检查出错误。
- [module-getter](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/module-getter.md)：使用module的时候，避免直接用一个变量，而是使用getter的链式语法
- [module-setter](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/module-setter.md)：不使用任何一个使用了setter语法的变量来定义modules。【不是很明白，看例子好像是说不要把模块赋值到变量】
- [no-private-call](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-private-call.md)：不允许使用以`$$`开头的angular私有变量。
	- `allow`：数组，指定哪些私有变量是可以使用的 

### 最好的实践
这些规则都是为了避免你犯错误。他们制定了一个更好的做事方式或帮助你避免失误。

- [component-limit](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/component-limit.md)：一个文件中应该被限制多少个angular 组件，这里的组件指的是controller，directive等，默认为1。通过`angular/component-limit: [2,3]`可以指定想要限定的数量。
- [controller-as-route](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/controller-as-route.md)：在定义router或state的时候，应该使用angular的controllerAs语法。这样使用的好处参考[style guide](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md#style-y031)。
- [controller-as-vm](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/controller-as-vm.md)：使用controllerAs语法时把this 赋值给一个可捕获的变量，选择一个有代表性的名称，例如vm代表ViewModel。
	- `"xxx"`：定义使用哪些变量，如

	```
	angular/controller-as-vm: [2,"viewModel"]
	```
- [controller-as](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/controller-as.md)：参考[y031 by johnpapa - controllerAs Controller Syntax](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md#style-y031)，不要在`$scope`上面添加属性，使用`controllerAs`语法将数据和属性添加到`this`上。
- [deferred](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/deferred.md)：定义promise的时候不要使用`$q.deferred`，而是`$q(function(resolve, reject){})`。
- [di-unused](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/di-unused.md)：不用的依赖就不要注入。
- [directive-restrict](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/directive-restrict.md)：当创建一个directive需要作为一个独立元素时，restrict值设置为E（自定义元素），也可以设置可选值A（自定义属性）。一般来说，如果它就是为了独立存在，用E是合适的做法。一般原则是允许EA，但是当它是独立的时候这更倾向于作为一个元素来实施，当它是为了增强已存在的DOM元素时则更倾向于作为一个属性来实施。定义指令的时候，`restrict`属性只能设置为`A`、`E`或`AE`，不能使用`C`和`M`。
	- explicit：是否需要指定`restrict`属性，有`always`和`never`可选。
	- restrict：指定可以使用的`restrict`属性，如`{"restrict":"A"}`，则定义指令的时候不允许使用`"restrict":"E"`或`"restrict":"AE"`。
- [empty-controller](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/empty-controller.md)：不要定义空的`controller`。
- [no-controller](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-controller.md)：根据Component-First原则，不允许定义和使用`controller`。
- [no-inline-template](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-inline-template.md)：不允许使用template属性定义模块，建议使用templateUrl，从外部文件定义模板。
	- allowSimple：是否允许简单的内联模板，默认为`true`，即简单的模板（有不超过两个闭合标签或一个自闭和标签）可以定义在template属性中，如`template:"<div>I'm inline template。</div>"`。
- [no-run-logic](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-run-logic.md)：在`run`方法中不能包含逻辑代码，仅作为入口。
	- `allowParams`：`run`方法中注入的参数在调用的时候是否可以传递参数进去。默认为`true`，当设置为`false`的时候，下列代码视为错误.

	```
	angular.module('app').run(function(startup) {
	    startup('foo', true, 1);
	});
	```
- [no-services](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-services.md)：不允许注入特定的一些services，如`$http`不应该注入到controller中。
	- 可以按照services进行配置，也可以按照controller或directive等进行配置。

- [on-watch](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/on-watch.md)：scope对象中的`$on`和`$watch`方法应该被赋值到变量中，以便在`$destroy`事件中删除。

### Angular弃用的特性
这些规则帮助你避免使用Angular中已经弃用的属性。

- [no-cookiestore](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-cookiestore.md)：在Angular1.4中，`$cookieStore`这个service已经被弃用了，取而代之的是`$cookies`。
- [no-directive-replace](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-directive-replace.md)：1.3之后的版本中，定义指令的时候不允许使用`replace`属性。
	- `ignoreReplaceFalse`：默认为`false`，指明当`replace`设置为`false`的时候是否忽略该属性。
- [no-http-callback](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-http-callback.md)：不允许使用`$http`方法返回的`Promise`的`success`和`error`方法，应该使用标准的`promise`API，即`then`。

### 命名
这些规则帮你指定一些命名方面的约定。

- [controller-name](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/controller-name.md)：为所有controller提供统一的名称，先特征后名字，鉴于controller是构造函数，所以要采用UpperCamelCase（每个单词首字母大写）的方式。
	- 可以配置一个字符串参数，如果是普通的字符串，表示待检测的controller名字里必须包含这个字符串，如

	```
	angular/controller-name:[2,"Ctrl"]
	app.controller("demoCtrl")或app.controller("demoCtrlTest")
	都不会报错
	```
	字符串也可以为正则，如`angular/controller-name:[2,"/[A-Z].*Ctrl/"]`
- [directive-name](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/directive-name.md)：提供一个短小、唯一、具有描述性的directive前缀，例如acmeSalesCustomerInfo在HTML中声明为acme-sales-customer-info。这样方便快速识别directive的内容和起源，例如acme-可能预示着这个directive是服务于Acme company。_避免使用ng-为前缀_
	- 和`controller-name`规则相同的是，同样可以指定字符串或者正则，不同点是该规则主要用于指定前缀。
- [file-name](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/file-name.md)：组件文件名能够描述组件功能，给所有的组件提供统一的命名，推荐的做法是`feature.type.js`。大多数文件都有2个名字。
	- 文件名 (avengers.controller.js)
	- 带有Angular的注册组件名 (AvengersController)
	有以下配置项
	- `nameStyle`:名字格式，可选择`"dash"`、`"dot"`和`"underscore"`三种，如

	```
	angular/file-name: [2,{"nameStyle":"dot"}]
	// 文件 src/app/my.util.services.js 中的services可以如下定义
	app.service('myUtilServices')
	```
	- `typeSeparator`:名字和类型之间的分隔符类型，也可选择`"dash"`、`"dot"`和`"underscore"`三种，如

	```
	angular/file-name: [2,{"typeSeparator":"underscore"}]
	// 文件 src/app/myUtil_services.js 中的services可以如下定义
	app.service('myUtilServices')
	```
	- `ignoreTypeSuffix`:配置是否忽略类型后缀，可选`true`和`false`

	```
	angular/file-name: [2,{"typeSeparator":"underscore","ignoreTypeSuffix":true}]
	// 文件 src/app/myUtil_services.js 中的services可以如下定义
	app.service('myUtil') //注意这里不再使用myUtilServices
	```
	- `ignorePrefix`:是否忽略特定前缀，如

	```
	angular/file-name: [2,{"typeSeparator":"dot","ignorePrefix":"ui"}]
	// 文件 src/app/modal.directive.js 中的directive可以如下定义
	app.service('uiModalDirective') 
	```
- [filter-name](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/filter-name.md)：需要为所有的`filter`名字指定字符串前缀。
	- 配置同`directive-name`
- [module-name](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/module-name.md)：需要为所有的`module`名字指定字符串前缀。
	- 配置同`directive-name`
- [service-name](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/service-name.md)：需要为所有的`service`名字指定字符串前缀。
	- 配置同`directive-name`

### 约定
Angular会为一种实现提供多种不同的方法，这些规则帮助你在项目中定义约定

- [di-order](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/di-order.md)：依赖注入的参数列表应该按照字母表排序。
	- 指定是否忽略首尾有`_`的参数的下划线。可以是`true`或`false`，如`inject(function (_$compile_, $httpBackend, _$log_, _$rootScope_)`在该项配置为`false`的时候报错，为`true`的时候不报错。
- [di](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/di.md)：所有的依赖注入使用同一种方法。
	- 指定依赖注入的方式，可选`array`，`function`和`$inject`。默认为`function`
- [dumb-inject](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/dumb-inject.md)：单元测试中使用依赖注入以及对外部变量赋值的时候严格按照字母表排序，并且在注入的函数中只对外部变量进行赋值，不进行其他操作。
- [function-type](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/function-type.md)：指定回调函数使用命名函数亦或是匿名函数。
	- 指定使用何种函数，可选配置项为`named`和`anonymous`。默认为使用匿名函数
	- 指定哪些angular对象需要被检查，数组。可选的值有`['animation', 'config', 'constant', 'controller', 'directive', 'factory', 'filter', 'provider', 'service', 'value', 'decorator']`
- [module-dependency-order](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/module-dependency-order.md)：模块的依赖项应该有一个合理的排列顺序。有分组和不分组两种方式可配置。
	- `grouped`：是否分组，默认为true，即分为标准模块（`ngAnimate`等），第三方模块（`ui.router`），自定义模块(`myModule`)三组，并按此顺序，同一个组内的模块按照字母表顺序排列。标准模块包括`['ng','ngAnimate','ngAria','ngCookies','ngLocale','ngMessageFormat','ngMessages','ngMock','ngResource','ngRoute','ngSanitize','ngTouch','ngMaterial','ngNewRouter']`
	- `prefix`：指定一个前缀，模块名有此前缀的表示为自定义模块。当没有指定该参数的时候，非标准模块都算是自定义模块一组的，指定了该参数之后，既不是标准模块，也不符合这个前缀的模块被视为第三方模块。
- [no-service-method](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-service-method.md)：定义`service`的时候不要使用`app.service('myServices')`方法，而是使用`factory`方法。参考[angular.service vs angular.factory](http://stackoverflow.com/questions/14324451/angular-service-vs-angular-factory)
- [one-dependency-per-line](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/one-dependency-per-line.md)：每一个依赖注入独占一行，如下

	```
	app.controller('MyController', [
    '$http',
    '$q',
    function($http,
             $q) {
    }]);
	```
- [rest-service](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/rest-service.md)：调用REST API的service中应该使用统一的rest service，可选择的有` '$http'`、`'$resource'`和`'Restangular'`
	- 指定使用哪个service	
- [watchers-execution](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/watchers-execution.md)：手动触发脏数据检查的时候使用`$apply`方法还是`$digest`，两者的不同点在于:`$digest`从我们调用方法的作用域开始执行数据检查，而`$apply`方法会从`$rootScope`逐层往下进行数据检查。
	- 指定使用何种方法，默认是`$digest`。

### Angular封装
这些规则帮助你强制使用angular的内置封装（service）

- [angularelement](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/angularelement.md)：使用`angular.element`作为选择器，而不是使用`$`或`jQuery`。即使代码中使用了jQuery，`angular.element`也会调用jQuery的方法。
- [definedundefined](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/definedundefined.md)：判断一个变量是否是`undefined`的时候使用`angular.isUndefined`或`angular.isDefined`，注意不要使用`!angular.isUndefined(foo)`或`!angular.isDefined(foo)`
- [document-service](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/document-service.md)：使用`$document`代替`document`
- [foreach](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/foreach.md)：使用`angular.forEach`方法来进行遍历，不使用数组原生的`Array.prototype.forEach`方法。
- [interval-service](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/interval-service.md)：使用`$interval`代替`setInterval`
- [json-functions](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/json-functions.md)：使用`angular.fromJson`代替`JSON.parse`，使用`angular.toJson`代替`JSON.stringify`
- [log](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/log.md)：使用`$log`service代替`console`中的方法，包括`log()`、`warn()`、`error()`、`debug()`和`info()`
- [no-angular-mock](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-angular-mock.md)：`angular.mock`中定义的所有的方法同样可以在`window`中进行直接调用，使用这些方法的时候就不要使用`angular.mock`了，直接调用即可。
- [no-jquery-angularelement](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/no-jquery-angularelement.md)：经过`angular.element`初始化的方法已经是jqlite对象了，不需要再用`$`或`jQuery`。
- [timeout-service](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/timeout-service.md)：使用`$timeout`代替`setTimeout`
- [typecheck-array](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/typecheck-array.md)：判断一个值是否是数组的时候使用`angular.isArray()`
- [typecheck-date](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/typecheck-date.md)：判断一个值是否是日期对象的时候使用`angular.isDate()`
- [typecheck-function](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/typecheck-function.md)：判断一个值是否是函数的时候使用`angular.isFunction()`
- [typecheck-number](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/typecheck-number.md)：判断一个值是否是数字的时候使用`angular.isNumber()`
- [typecheck-object](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/typecheck-object.md)：判断一个值是否是对象的时候使用`angular.isObject()`
- [typecheck-string](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/typecheck-string.md)：判断一个值是否是字符串的时候使用`angular.isString()`
- [window-service](https://github.com/Gillespie59/eslint-plugin-angular/blob/master/docs/rules/window-service.md)：使用`$window`代替`window`

# 参考资料 #
[angular-styleguide](https://github.com/johnpapa/angular-styleguide/blob/master/a1/i18n/zh-CN.md)
