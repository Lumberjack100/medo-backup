#### 获取api版本信息
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @GET("ApiVersion")
    Observable<ResultWrapper<String>> getApiVerson();

 #### 登录用户
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("SignIn")
    Observable<ResultWrapper<String>> getSingIn(@Body RequestBody parameter);

### 我的模块
#### 获取用户信息

    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @GET("GetMyInfo")
    Observable<ResultWrapper<UserInfo>> getMyInfo(@Header(NetworkConst.ACCESS_TOKEN) String token);

#### 发送登录验证码(间隔60秒，有效期15分钟)
    @Headers({NetworkConst.HEADER_ACCESS_TYPE, NetworkConst.HEADER_APP_KEY, NetworkConst.HEADER_APP_SECRET})
    @POST("SendSmsCode")
    Observable<ResultWrapper<String>> sendSmsCode(@Body RequestBody parameter);

#### 使用手机号和验证码登录
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("SmsLogin")
    Observable<ResultWrapper<String>> SmsLogin(@Body RequestBody parameter);

 #### 系统接口V2-5  检测手机号是否存在
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("CellPhoneExists")
    Observable<ResultWrapper<Boolean>> CellPhoneExists(@Body RequestBody parameter);

#### 系统接口v2  修改当前登录用户的密码
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("ChangeMyPassword")
    Observable<ResultWrapper<String>> ChangeMyPassword(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 系统接口v2  修改我的手机号码
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("UpdateMyCellPhone")
    Observable<ResultWrapper<String>> UpdateMyCellPhone(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 系统接口v2  修改我的信息
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("UpdateMyInfo")
    Observable<ResultWrapper<String>> UpdateMyInfo(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 用户上传头像
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("SetUserHeadPhoto")
    Observable<ResultWrapper<String>> setUserHeadPhoto(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 系统接口v2  公司模块 4.查询单个公司信息
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("GetCompanyInfo")
    Observable<ResultWrapper<CompanyInfo>> GetCompanyInfo(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 系统接口v2  查询用户在其中具有权限的公司，包括该公司的子公司(用于设备分配)
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryUserInCompany")
    Observable<ResultWrapper<PageResult<CompanySimpleInfo>>> QueryUserInCompany(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);


### 项目模块
#### 项目接口V2  查询当前用户的项目列表(列表方式、不分页)
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryUserListProjectEx")
    Observable<ResultWrapper<List<ProjectBaseInfo>>> QueryUserListProject(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 项目接口V2  查询当前用户的项目列表(项目类型方式)
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryUserTypeProject")
    Observable<ResultWrapper<List<IndustryTypeProjectInfo>>> QueryUserTypeProject(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 项目接口V2  查询当前用户的项目列表(行政区域列表方式)
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryUserRegionListProject")
    Observable<ResultWrapper<List<RegionProjectInfo>>> QueryUserRegionListProject(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  项目接口V2  查询当前用户的项目列表（自定义分级方式，不包含空节点）
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("GetLevelProjList")
    Observable<ResultWrapper<List<CustomLevelProjectInfo>>> GetLevelProjList(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 项目接口V2-4  查询警报阈值列表
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryProjectListInfo")
    Observable<ResultWrapper<List<ProjectDetailInfo>>> QueryProjectListInfo(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 系统接口V2-5  用户项目置顶
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("TopUserProject")
    Observable<ResultWrapper<String>> TopUserProject(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

#### 系统接口V2-5  用户项目取消置顶
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("UnTopUserProject")
    Observable<ResultWrapper<String>> UnTopUserProject(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  系统接口v2-2  查询公司设备列表
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryCompanyDevice")
    Observable<ResultWrapper<PageResult<ProjectDeviceInfo>>> QueryCompanyDevice(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  项目接口V2-4  获取单个项目的详细信息
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("GetProjectByIDEx")
    Observable<ResultWrapper<ProjectInfoEx>> GetProjectByIDEx(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  系统接口V2  查询公司设备类型在线统计信息
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryCompanyDeviceOnlineTypeStatistics")
    Observable<ResultWrapper<List<DeviceOnlineTypeStatistic>>> QueryCompanyDeviceOnlineTypeStatistics(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

### 设备模块
#### 系统接口V2-4  查询设备状态历史
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryCmdState")
    Observable<ResultWrapper<PageResult<DevcieHistoryState>>> QueryCmdState(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  系统接口V2-4  查询公司固件列表
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryFirmwareList")
    Observable<ResultWrapper<PageResult<FirmWareInfo>>> QueryFirmwareList(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  系统接口V2-4  固件升级
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("FirmwareUpgrade")
    Observable<ResultWrapper<String>> FirmwareUpgrade(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);


####  系统接口V2  查询设备类型列表
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryDeviceType")
    Observable<ResultWrapper<PageResult<DeviceTypeInfo>>> QueryDeviceType(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);


### 指令交互
####  系统接口V2-4  指令下发
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("DispatchCmd")
    Observable<ResultWrapper<List<DispatchCmdItem>>> DispatchCmd(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  系统接口V2-4  指令透传
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("DispatchRawCmd")
    Observable<ResultWrapper<List<DispatchCmdItem>>> DispatchRawCmd(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  系统接口V2-4  查询指令响应结果
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("QueryCmdResultByMsgID")
    Observable<ResultWrapper<List<QueryCmdResult>>> QueryCmdResultByMsgID(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  系统接口v2  7.10 查询设备的详情信息
    @Headers({NetworkConst.HEADER_ACCESS_TYPE})
    @POST("GetDeviceDetailInfo")
    Observable<ResultWrapper<DeviceDetailInfo>> GetDeviceDetailInfo(@Header(NetworkConst.ACCESS_TOKEN) String token, @Body RequestBody parameter);

####  查询数据
    @POST("queryCloudData")
    Observable<ResultWrapper<List<QueryCloudDataInfo>>> QueryCloudData(@Body RequestBody parameter);