# er代码段生成小工具 for Sublimte Text


## 如何使用

将`snippet`中的文件复制到`{SublimePackage/User}`下

## 命令

### er-Action 

生成一个继承自er/Action的模块；

`触发键`: 

```javascript
er-Action
```

生成的代码段如下：

```javascript
define(function (require) {
    var Action = require('er/Action');
    var util = require('er/util');

    function action() {
        Action.apply(this, arguments);
    }

    action.prototype.modelType = require('./actionModel');
    action.prototype.viewType = require('./actionView');

    action.prototype.initBehavior = function () {
        Action.prototype.initBehavior.apply(this, arguments);
        // 事件绑定...
    };

    util.inherits(action, Action);
    return action;
});
```

### ef-UIModel 

生成一个继承自ef/UIModel的模块；

`触发键`: 

```javascript
ef-UIModel
```

生成的代码段如下：

```javascript
define(function (require) {
    var Model = require('ef/UIModel');
    var util = require('er/util');

    function model() {
        Model.apply(this, arguments);
        // 添加datasource
    }

    model.prototype.prepare = function () {
        // datasource加载完成后、渲染视图前，数据处理...
    };

    util.inherits(model, Model);
    return model;
});
```
### ef-UIView 

生成一个继承自ef/UIView的模块；

`触发键`: 

```javascript
ef-UIView
```

生成的代码段如下：

```javascript
define(function (require) {
    var View = require('ef/UIView');
    var util = require('er/util');

    function view() {
        View.apply(this, arguments);
    }

    view.prototype.template = 'etpl target';

    view.prototype.uiProperties = {
        // 添加控件配置
    };

    view.prototype.uiEvents = {
        // 添加控件事件绑定
    };

    util.inherits(view, View);
    return view;
});
```