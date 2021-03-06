# Lines Charts

这个图的 Y 轴是*数值*维度。该维度有以下聚合可用：

* Count
    [count](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-valuecount-aggregation.html) 聚合返回选中索引模式中元素的原始计数。
* Average
    这个聚合返回一个数值字段的 [average](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-avg-aggregation.html) 。从下拉菜单选择一个字段。
* Sum
    [sum](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-sum-aggregation.html) 聚合返回一个数值字段的总和。从下拉菜单选择一个字段。
* Min
    [min](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-min-aggregation.html) 聚合返回一个数值字段的最小值。从下拉菜单选择一个字段。
* Max
    [max](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-max-aggregation.html) 聚合返回一个数值字段的最大值。从下拉菜单选择一个字段。
* Unique Count
    [cardinality](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-cardinality-aggregation.html) 聚合返回一个字段的去重数据值。从下拉菜单选择一个字段。
* Standard Deviation
    [extended stats](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-extendedstats-aggregation.html) 聚合返回一个数值字段数据的标准差。从下拉菜单选择一个字段。
* Percentile
    [percentile](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-metrics-percentile-rank-aggregation.html) 聚合返回一个数值字段中值的百分比分布。从下拉菜单选择一个字段，然后在 **Percentiles** 框内指定范围。点击 **X** 移除一个百分比框，点击 **+ Add Percent** 添加一个百分比框。
* Percentile Rank
    [percentile ranks](http://www.elastic.co/guide/en/elasticsearch/reference/current//search-aggregations-metrics-percentile-rank-aggregation.html) 聚合返回一个数值字段中你指定值的百分位排名。从下拉菜单选择一个字段，然后在 **Values** 框内指定一到多个百分位排名值。点击 **X** 移除一个百分比框，点击 **+Add** 添加一个数值框。

你可以点击 **+ Add Aggregation** 按键添加一个聚合。

*buckets* 聚合指明从你的数据集中将要检索什么信息。

在你选定一个 buckets 聚合之前，先指定你是要切割单个图的分片，还是切割成多个图形。多图切分必须在其他任何聚合之前要运行。如果你切分图形，你可以选择切分结果是展示成行还是列的形式，点击 **Rows | Columns** 选择器即可。

图形的 X 轴是*buckets* 维度。你可以为 X 轴定义 buckets，同样还可以为图片上的分片区域，或者分割的图片定义 buckets。

该图形的 X 轴支持以下聚合。点击每个聚合的链接查看该聚合的 Elasticsearch 官方文档。

* Date Histogram
    [date histogram](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-datehistogram-aggregation.html) 基于数值字段创建，由时间组织起来。你可以指定时间片的间隔，单位包括秒，分，小时，天，星期，月，年。
* Histogram
    标准 [histogram](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-histogram-aggregation.html) 基于数值字段创建。为这个字段指定一个整数间隔。勾选 **Show empty buckets** 让直方图中包含空的间隔。
* Range
    通过 [range](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-range-aggregation.html) 聚合。你可以为一个数值字段指定一系列区间。点击 **Add Range** 添加一堆区间端点。点击红色 **(x)** 符号移除一个区间。
* Date Range
    [date range](http://www.elastic.co/guide/en/elasticsearch/reference/current//search-aggregations-bucket-daterange-aggregation.html) 聚合计算你指定的时间区间内的值。你可以使用 [date math](http://www.elastic.co/guide/en/elasticsearch/reference/current//mapping-date-format.html#date-math) 表达式指定区间。点击 **Add Range** 添加新的区间端点。点击红色 **(/)** 符号移除区间。
* IPv4 Range
    [IPv4 range](http://www.elastic.co/guide/en/elasticsearch/reference/current//search-aggregations-bucket-iprange-aggregation.html) 聚合用来指定 IPv4 地址的区间。点击 **Add Range** 添加新的区间端点。点击红色 **(/)** 符号移除区间。
* Terms
    [terms](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-terms-aggregation.html) 聚合允许你指定展示一个字段的首尾几个元素，排序方式可以是计数或者其他自定义的metric。
* Filters
    你可以为数据指定一组 [filters](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-filters-aggregation.html)。你可以用 query string，也可以用 JSON 格式来指定过滤器，就像在 Discover 页的搜索栏里一样。点击 **Add Filter** 添加下一个过滤器。
* Significant Terms
    展示实验性的 [significant terms](http://www.elastic.co/guide/en/elasticsearch/reference/current/search-aggregations-bucket-significantterms-aggregation.html) 聚合的结果。

一旦你定义好了一个 X 轴聚合。你可以继续定义子聚合来完善可视化效果。点击 **+ Add Sub Aggregation** 添加子聚合，然后选择 **Split Area** 或者 **Split Chart**，然后从类型菜单中选择一个子聚合。

当一个图形中定义了多个聚合，你可以使用聚合类型右侧的上下箭头来改变聚合的优先级。

你可以点击 **Advanced** 链接显示更多有关聚合的自定义参数：

* Exclude Pattern
    指定一个从结果集中排除掉的模式。
* Exclude Pattern Flags
    排除模式的 Java flags 标准集。
* Include Pattern
    指定一个从结果集中要包含的模式。
* Include Pattern Flags
    包含模式的 Java flags 标准集。
* JSON Input
    一个用来添加 JSON 格式属性的文本框，内容会合并进聚合的定义中，格式如下例：

```
{ "script" : "doc['grade'].value * 1.2" }
```

### 注意

> Elasticsearch 1.4.3 及以后版本，这个函数需要你开启 [dynamic Groovy scripting](http://www.elastic.co/guide/en/elasticsearch/reference/current/modules-scripting.html)。

这些参数是否可用，依赖于你选择的聚合函数。

多选框可以用来控制以下行为：

* Y 轴比例
    可以给图形的 Y 轴选择 **linear**, **log** 或 **square root** 三种比例。你可以给指数变化的数据采用 log 函数比例显示，比如复利图表；也可以用平方根(square root)比例显示数值变化差异极大的数据集。这种可变性本身也算变量的一种的数据，又叫异方差数据。比如，身高和体重的数据集，在较矮的区间变化是很小的，但是在较高另一个区间，数据集就是异方差式的。
* Smooth Lines
    勾选该项，将图中的数据点用平滑曲线连接。注意：平滑曲线在高峰低谷处给人的印象与实际值有较大偏差。
* Show Connecting Lines
    勾选该项，将图中的数据点用折线连接。
* Show Circles
    勾选该项，将图中的数据点绘制成一个小圆圈。
* Current time marker
    对时序数据，勾选该项可以在当前时刻位置标记一条红线。
* Set Y-Axis Extents
    勾选该项，然后在 **y-max** 和 **y-min** 框里输入数值限定 Y 轴为指定数值。
* Show Tooltip
    勾选该项显示工具栏。
* Show Legend
    勾选该项在图形右侧显示图例。
* Scale Y-Axis to Data Bounds
    默认的 Y 轴长度为 0 到数据集的最大值。勾选该项改变 Y 轴的最大和最小值为数据集的返回值。

更新选项后，点击绿色 **Apply changes** 按钮更新你的可视化界面，或者灰色 **Discard changes** 按钮保持原状。

## 气泡图(Bubble Charts)

通过以下步骤，可以转换折线图成气泡图：

1. 为 Y 轴点击 **Add Metrics** 然后选择 **Dot Size**。
2. 从下拉框里选择一个 metric 聚合函数。
3. 在 **Options** 标签里，去掉 **Show Connecting Lines** 的勾选。
4. 点击 **Apply changes** 按钮。
