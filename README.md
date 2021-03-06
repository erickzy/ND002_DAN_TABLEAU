# 基于TABLEAU的摩拜单车数据可视化分析

## 1.项目概况
本项目对2016年8月上海地区的摩拜单车用户行为数据进行了整理后进行可视化分析，从而挖掘数据背后存在的客户使用行为规律及特征

## 2.分析步骤
1.首先我观察了原始数据的结构，原始数据包含订单ID、用户ID、车辆ID、
开始结束时间和位置等信息。
2.从这些数据上直观的我们可以衍生出骑行时长、起止点直线距离、骑行速度等信息。通过起始时间相减求出骑行时长`run_mins`,通过起始坐标计算出两点直线距离：`distance`,再通过`distance`（m
) 除以 `run_mins` （min）计算出车速`Speed`（kph）
3.数据中包含了一些骑行时间非常长的数据（如4750min）这种通常是由于没有进行check out等造成的异常值，我们在分析的过程中通过筛选进行剔除。
4.进行图标制作，从时间、地点、车速、距离等多维度进行组合可视化分析

## 3.图表说明
1. 工作表1：对比了不同工作日下、不同时间段下订单数的数量，可以看出周一到周五的订单高峰期与上下班通勤高峰一致，周末主要集中在傍晚时分。
2. 工作表2：在地图上展示出不同时间段下骑行的速度和骑行时长的分布，可以看出原点越大标识骑行时间越长，颜色越红标识骑行速度越快。一般来说骑行范围都集中在市区，骑行时间越长的一般骑行速度都较慢，而早高峰要比晚高峰骑行的平均速度要快。
3. 工作表3：从时段角度对比订单数量，可以看出晚高峰要比早高峰订单数多，同时用线的粗细标识骑行时长，也可以从这个图印证工作表2的结论。
4. 工作表4：骑行速度的分布图，可以看出大多数骑行的速度都在7~9kph，这与我们常识认知相一致。
5. 工作表5：骑行距离的分布图，可以看出大多数骑行的距离都在1km左右，可以说共享单车是解决最后一公里问题的好方法。
6. 工作表6：不同时段下的骑行速度可以看出，下班后的骑行速度要比上班时候悠闲得多。
7. 工作表7：共享单车真的是和别人分享吗？带着这个疑问我分析了订单数、单车数、用户数，我发现，单车ID数竟然是用户ID数的4.682倍，也就是服务一个客户需要将近5辆单车，而单车数和订单数却差别不大，这说明单车的共享率太低了，有很大的优化空间。
8. 工作表8：查看了全月的订单数量的变化，发现整体都是向上增长的态势，也就是说从2016年8月份数据看来，共享单车还是出于快速发展时期

## 4.可视化链接
[摩拜单车2016年8月份上海地区数据分析_V3.0](https://public.tableau.com/profile/erick2761#!/vizhome/mobike_shanghai_sample_dashboard_zy_v3_0/1?publish=yes)

[摩拜单车2016年8月份上海地区数据分析_V2.0](https://public.tableau.com/profile/erick2761#!/vizhome/mobike_shanghai_sample_dashboard_zy/1_2?publish=yes)

[摩拜单车2016年8月份上海地区数据分析_V1.0](https://public.tableau.com/profile/erick2761#!/vizhome/mobike_shanghai_sample_dashboard_zy_v1_0/1_2?publish=yes)

## 文件说明
1. `mobike_shanghai_sample_dashboard_zy_2.0.twbx` 可视化主文件
2. `mobike_shanghai_sample_updated.csv` 数据源文件
3. `mobike_shanghai_sample_clean.csv` 清理后数据文件
4. `MOBIKE 样本数据说明(data_description).pdf` 元数据说明文件
5. `README.md` 项目说明文件

## 参考资料
1. [excel计算两地经纬度距离](https://jingyan.baidu.com/article/48b558e34df4d47f39c09a42.html)
2. [Udacity DAND tableau 课程](https://review.udacity.com/#!/rubrics/1300/view)
3. [Tableau帮助文档](https://onlinehelp.tableau.com/v10.4/pro/desktop/zh-cn/help.htm#extracting_data.html)
