# timepicker
很好用的时间插件

实例地址为：https://yueveryoung.github.io/timepicker/

## 1、在页面head中引入css文件：

```
<link href="wp-content/plugins/timepicker/css/jquery-ui.css" rel="stylesheet"/>
<link href="/resources/plugins/timepicker/css/jquery-ui-timepicker-addon.css" rel="stylesheet"/>
```
在页面的foot中引入JS文件：

```
<script src="wp-content/resources/js/jquery-1.8.3.min.js"></script> 

<script type="text/javascript" src="/resources/plugins/timepicker/js/jquery-ui.min.js"></script>
<script type="text/javascript" src="/resources/plugins/timepicker/js/jquery-ui-timepicker-addon.js"></script>
<script type="text/javascript" src="/resources/plugins/timepicker/js/jquery-ui-sliderAccess.js"></script>
```

## 2、HTML中的时间元素

注意：create_time_start和create_time_end的名称是有要求的，这个必须和JS中的一样才可以。才能保证该元素被设置为时间样式

```
<input type="text" class="form-control" id="create_time_start" placeholder="创建时间（开始）">
<input type="text" class="form-control" id="create_time_end" placeholder="创建时间（结束）">
```

## 3、JS 代码

```
    $(function () {
        $.datepicker.regional['zh-CN'] = {
            changeMonth: true,
            changeYear: true,
            clearText: '清除',
            clearStatus: '清除已选日期',
            closeText: '关闭',
            closeStatus: '不改变当前选择',
            prevText: '<上月',
            prevStatus: '显示上月',
            prevBigText: '<<',
            prevBigStatus: '显示上一年',
            nextText: '下月>',
            nextStatus: '显示下月',
            nextBigText: '>>',
            nextBigStatus: '显示下一年',
            currentText: '今天',
            currentStatus: '显示本月',
            monthNames: ['一月', '二月', '三月', '四月', '五月', '六月', '七月', '八月', '九月', '十月', '十一月', '十二月'],
            monthNamesShort: ['1', '2', '3', '4', '5', '6', '7', '8', '9', '10', '11', '12'],
            monthStatus: '选择月份',
            yearStatus: '选择年份',
            weekHeader: '周',
            weekStatus: '年内周次',
            dayNames: ['星期日', '星期一', '星期二', '星期三', '星期四', '星期五', '星期六'],
            dayNamesShort: ['周日', '周一', '周二', '周三', '周四', '周五', '周六'],
            dayNamesMin: ['日', '一', '二', '三', '四', '五', '六'],
            dayStatus: '设置 DD 为一周起始',
            dateStatus: '选择 m月 d日, DD',
            dateFormat: 'yy-mm-dd',
            firstDay: 1,
            initStatus: '请选择日期',
            isRTL: false
        };

    });
    $(function () {
        $.datepicker.setDefaults($.datepicker.regional['zh-CN']);
        $('#create_time_start').prop("readonly", true).datetimepicker({
            timeText: '时间',
            hourText: '小时',
            minuteText: '分钟',
            secondText: '秒',
            currentText: '现在',
            closeText: '完成',
            showSecond: true, //显示秒
            timeFormat: 'HH:mm:ss' //格式化时间
        });
    });

    $(function () {
        $.datepicker.setDefaults($.datepicker.regional['zh-CN']);
        $('#create_time_end').prop("readonly", true).datetimepicker({
            timeText: '时间',
            hourText: '小时',
            minuteText: '分钟',
            secondText: '秒',
            currentText: '现在',
            closeText: '完成',
            showSecond: true, //显示秒
            timeFormat: 'HH:mm:ss' //格式化时间
        });
    });
```
