# 匹配功能需求说明


1.首页点击“一键匹配”，出现上滑框，上滑框里有三个选项分别为“附近即刻出行、预约计划出行、取消”。

2.若点击“附近即刻出行”，进入下一页面。该页面为地图栏，人员栏，时间栏，类别栏，计划简述栏。

 - 地图栏：上方为地图显示，即显示你附近的区域地图，等数据量大的时候也可以扫描显示出附近的用户数（如滴滴快车显示周围的车辆一样）。下方有个地图标，点击地图标进入地址选择，可选择附近一个你所在的地址，选好后地址名称就显示在地图标旁边（如滴滴选择附近地址一样）。
 - 人员栏：人员以用户ID显示，默认匹配的用户本人已经加入，可以点击旁边的“邀请”转到侣友好友页面邀请好友加入，加入的好友都是以ID显示，这样后台统计数据算法一个ID就是一个人数（如LOL开黑，先把好友拉近一个房间，再进行匹配一样）。
 - 时间栏：附近即刻旅行的时间栏精确到时和分，日期自动固定在匹配的当天，用户可选择“时”和“分”（比如2017年7月14日  8：00—12：00）。
 - 类别栏：采用下拉列表，进行类别的选择，如运动、唱歌、吃饭、购物、其他等。
 - 计划简述栏：能自行输入字体具体简述自己的匹配出行计划。

3.若点击“预约计划出行”，则进入另一下个页面。该页面为出发地栏，目的地栏，人员栏，时间栏，类别栏，计划简述栏。

 - 出发地栏：可点击转入地图页面，选择自己要出发的地点，点击完成返回。
 - 目的地栏：同上，可点击转入地图页面，选择自己要出发的地点，点击完成返回。
 - 人员栏：同“附近即刻出行”人员栏需求一样。
 - 时间栏：只精确到年月日，用户都可选择（比如2017年7月14日 至 2017年7月20日），但要求“年”的范围与现实符合，不能选择过去时间，且选择的时间跨度不能超过半年（比如今天是2017/7/14，用户最多提前预约半年的时间，2018年1月10日 至2018年1月14日）。
 - 类别栏：选择下拉列表，可以选择周边出行、省内出行、国内出行。
 - 计划简述栏：能自行输入字体具体简述自己的匹配出行计划。
 
 4.两种计划分别填写好了以后，都将点击底部“发布行程”来进行行程的发布，同时数据就进入后台进行处理。后台则根据用户填写的数据来进行相似度计算。
 
  (1).附近即刻出行，依据三个要素。
  
- 距离：根据地图以用户为中心周围几十公里的地区范围（0-50km，用户可在设置里自行选择）；
- 时间：根据用户填写的时间数据，将用户填写时间前后一小时的范围都纳入筛选（如用户填写为13：00—15：00，则筛选范围为12：00—16：00），时间只要有交叉的都进行相似度计算；
- 活动：根据用户所选择的类别进行计算（运动、吃饭、唱歌…其他）。

 (2).预约计划出行，依据三个要素。
 
- 目的地：根据用户填写的目的地进行筛选。周边出行将目的地中心及周围10km的地图范围都纳入；省内出行即将目的地省会全范围纳入；国内出行即依据地图进行分类，将其目的省会都纳入。前期筛选范围较大，但随着发展后期筛选范围会更加小、地点会更加精确。
- 类别：根据用户类别选择的不同将“周边出行、省内出行、国内出行”的人分开，方便进行下一步筛选。
- 时间：预约计划出行的时间只精确到了年月日，要求根据用户所填日期前后扩展两天进行筛选（如用户2017/8/10—2017/8/12，则将2017/8/8—2017/8/14都纳入筛选的范围）。
 
5.计算好之后，就会向用户展示一个列表，列表都是与用户行程相似的用户，且按照相似度高低依次排列，用户自行在列表里查看相似用户的个人信息、出行计划等等，满意地向其发送匹配邀请等待通过，通过后便可与相似用户展看聊天，相互沟通，并能与之添加好友等进一步的操作。

6.用户可在“我的行程管理中”查看匹配行程的进程。若用户发布行程后暂时没有相符合的用户，则此行程的状态将被标注为“待匹配”,用户可点击进去查看和再次进行匹配或取消此行程；若用户发布行程后发出的匹配邀请还没有被相似用户通过，则此行程的状态将被标注为“待通过”，用户可点击进去查看和再次进行匹配，以及查看已经发出邀请的人，取消对他的匹配邀请或取消行程；若用户发布后成功匹配，则此行程的状态将被标注为“已配对”，用户可点击进去查看已经配对了的人，并与之进行对话，并能取消与他的配对。