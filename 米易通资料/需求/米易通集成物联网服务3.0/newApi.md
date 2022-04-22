### 登录、用户信息模块

#### 用户名密码登录
     Headers {access_type:android}
     POST /auth/api/v1/SignIn

    Params
         {
    "account": "medo_gh",
    "password": "medo123456"
    }

     Response {
        "code": 0,
        "msg": null,
        "data": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI2MzYiLCJjb21wYW55SUQiOiIxMzgiLCJleHAiOjE2NDI3NTQ3MTQsImlhdCI6MTY0MDA3NjMxNCwic3ViamVjdFR5cGUiOiIwIiwic3ViamVjdE5hbWUiOiLlrqvotLoifQ.C76Az5PywG_u0PXud979sWlB5hHtNjTc6WFZsLp5g8A"
    }

#### 发送短信验证码
     Headers 
     POST /auth/api/v1/SendSmsCode

        Params
         {
          "phone": "13915272257"
        }

     Response
      {
        "code": 0,
        "msg": null,
        "data": "验证码已发送"
     }

#### 短信登录
     Headers {access_type:android}
     POST /auth/api/v1/SmsLogin

        Params
         {
            "phone": "13915272257",
            "code": "804147"
        }

     Response
      {
        "code": 0,
        "msg": null,
        "data": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiI2MzYiLCJjb21wYW55SUQiOiIxMzgiLCJleHAiOjE2NDI3NTQ1MjUsImlhdCI6MTY0MDA3NjEyNSwic3ViamVjdFR5cGUiOiIwIiwic3ViamVjdE5hbWUiOiLlrqvotLoifQ.d4iymSGjGV2Olofm3WRFGEUC3lPz2vsanK4O8k9bn8U"
    }

#### 通过token获取用户信息
     Headers {Authorization:""}
     POST /auth/api/v1/GetUserByToken

     Response 
        {
            "code": 0,
            "msg": null,
            "data": {
                "subjectID": 636,
                "subjectName": "宫贺",
                "companyID": 138,
                "subjectType": "USER",
                "imageUrl": null,
                "phone": "13915272257",
                "email": ""
            }
        }

#### 查询用户信息
     Headers {Authorization:""}
     POST /auth/api/v1/QueryUserByID

        Params
         {
            "companyID": "",
            "userID": ""
        }

     Response 
      {
        "code": 0,
        "msg": null,
        "data": {
            "user": {
                "userID": 636,
                "companyID": 138,
                "companyName": "上海米度测控科技有限公司",
                "account": "medo_gh",
                "name": "宫贺",
                "cellPhone": "13915272257",
                "position": "",
                "email": "",
                "phone": "",
                "address": "",
                "allowAccessType": 0,
                "headPhotoPath": null,
                "userEnable": true,
                "createUserID": 1,
                "createTime": "2021-12-20 17:40:31",
                "updateUserID": 1,
                "updateTime": "2021-12-20 17:40:31",
                "expireTime": null,
                "ssoUser": false,
                "ssoToken": null
            },
            "departments": [
                {
                    "id": 326,
                    "name": "产品开发部",
                    "companyID": 138,
                    "parentID": 323,
                    "desc": null,
                    "level": 2,
                    "readOnly": false,
                    "displayOrder": 1,
                    "createUserID": 539,
                    "createTime": "2021-07-22 11:32:08",
                    "updateUserID": 539,
                    "updateTime": "2021-07-22 11:32:08",
                    "hasChild": false,
                    "delete": false
                }
            ],
            "groups": null,
            "lastLoginTime": null,
            "lastLoginIP": null,
            "lastLoginType": null
    }

}

#### 重置用户密码
     Headers {Authorization:""}
     POST /auth/api/v1/ResetPassword

        Params
         {
            "companyID": "",
            "userID": "",
             "newPassword": "",
              "confirmPassword": ""
        }

     Response
        {
            "code": 0,
            "msg": null,
            "data": null
        }

#### 修改用户信息
     Headers {Authorization:""}
     POST /auth/api/v1/UpdateUser

        Params
         {
            "companyID": "",
            "userID": "",
             "name": "",
               "position": "",
              "email": "",
               "cellPhone": "",
                "code": "",
                 "phone": "",
                  "address": "",
                   "allowAccessType": "",
                    "expireTime": "",
                     "headPhotoPath": "",
                      "userEnable": "",
                       "ssoUser": "",
                        "departments": ""
        }

     Response
        {
            "code": 0,
            "msg": null,
            "data": null
        }

#### 上传用户头像
     Headers {Authorization:""}
     POST /auth/api/v1/UploadUserAvatar

        Params
         {
            "companyID": "",
            "userID": "",
             "content": "",
              "extension": ""
        }

     Response
        {
            "code": 0,
            "msg": null,
            "data": null
        }

#### 查询用户在某公司某服务中的所有权限
     Headers {Authorization:""}
     POST /auth/api/v1/QueryAllPermissionInService

        Params
         {
            "companyID": ""
        }

     Response
        {
    "code": 0,
    "msg": null,
    "data": [
        {
            "id": 1019,
            "name": "设置iot配置",
            "permissionToken": "UpdateIotCommonConfig",
            "serviceName": "iot",
            "permissionDesc": "设置iot配置",
            "exValues": null
        },
        {
            "id": 754,
            "name": "修改产品",
            "permissionToken": "UpdateProduct",
            "serviceName": "iot",
            "permissionDesc": "修改产品",
            "exValues": "添加产品"
        },
        {
            "id": 984,
            "name": "管理警报",
            "permissionToken": "ManagerWarn",
            "serviceName": "mdnet",
            "permissionDesc": "管理警报",
            "exValues": null
        },
        {
            "id": 789,
            "name": "更新设备",
            "permissionToken": "UpdateDevice",
            "serviceName": "iot",
            "permissionDesc": "更新设备，设置指令执行结果",
            "exValues": null
        },
        {
            "id": 781,
            "name": "统计公司下的设备",
            "permissionToken": "DescribeIotDashboard",
            "serviceName": "iot",
            "permissionDesc": "IOT服务聚合分析权限",
            "exValues": null
        },
        {
            "id": 755,
            "name": "查询产品列表",
            "permissionToken": "ListProduct",
            "serviceName": "iot",
            "permissionDesc": "查询产品列表",
            "exValues": "查询产品分页列表"
        },
        {
            "id": 962,
            "name": "查询设备组",
            "permissionToken": "ListDeviceGroup",
            "serviceName": "iot",
            "permissionDesc": "查询设备组",
            "exValues": null
        },
        {
            "id": 714,
            "name": "查询用户组列表",
            "permissionToken": "ListPermissionGroup",
            "serviceName": "user",
            "permissionDesc": "查询用户组",
            "exValues": null
        },
        {
            "id": 742,
            "name": "资源转移",
            "permissionToken": "ResourceTransfer",
            "serviceName": "user",
            "permissionDesc": "资源转移",
            "exValues": null
        },
        {
            "id": 970,
            "name": "添加自定义分级",
            "permissionToken": "AddMdnetInfo",
            "serviceName": "mdnet",
            "permissionDesc": "添加项目自定义分级",
            "exValues": null
        },
        {
            "id": 908,
            "name": "删除物联网卡",
            "permissionToken": "DeleteSimList",
            "serviceName": "iot",
            "permissionDesc": "删除物联网卡",
            "exValues": null
        },
        {
            "id": 951,
            "name": "管理MQTT",
            "permissionToken": "ManagerMqtt",
            "serviceName": "iot",
            "permissionDesc": "管理MQTT",
            "exValues": null
        },
        {
            "id": 715,
            "name": "管理用户组下用户",
            "permissionToken": "ManagerUserInGroup",
            "serviceName": "user",
            "permissionDesc": "管理用户组下用户",
            "exValues": null
        },
        {
            "id": 915,
            "name": "查询用户组",
            "permissionToken": "DescribePermissionGroup",
            "serviceName": "user",
            "permissionDesc": "查询用户组",
            "exValues": null
        },
        {
            "id": 957,
            "name": "查询公司中未关联设备的传感器",
            "permissionToken": "ListCompanySensor",
            "serviceName": "iot",
            "permissionDesc": "查询公司中未关联设备的传感器",
            "exValues": null
        },
        {
            "id": 978,
            "name": "描述项目",
            "permissionToken": "DescribeProject",
            "serviceName": "mdnet",
            "permissionDesc": "描述项目\n",
            "exValues": null
        },
        {
            "id": 959,
            "name": "删除设备组",
            "permissionToken": "DeleteDeviceGroup",
            "serviceName": "iot",
            "permissionDesc": "删除设备组",
            "exValues": null
        },
        {
            "id": 717,
            "name": "修改公司",
            "permissionToken": "UpdateCompany",
            "serviceName": "user",
            "permissionDesc": "修改公司",
            "exValues": null
        },
        {
            "id": 963,
            "name": "查询设备组推送详情",
            "permissionToken": "DescribeDeviceGroup",
            "serviceName": "iot",
            "permissionDesc": "查询设备组推送详情",
            "exValues": null
        },
        {
            "id": 751,
            "name": "权限模块管理",
            "permissionToken": "ManagePermission",
            "serviceName": "user",
            "permissionDesc": "权限模块管理",
            "exValues": null
        },
        {
            "id": 980,
            "name": "描述计算任务",
            "permissionToken": "DescribeStability",
            "serviceName": "mdnet",
            "permissionDesc": "描述边坡稳定性分析任务",
            "exValues": null
        },
        {
            "id": 733,
            "name": "Mqtt超级用户校验",
            "permissionToken": "MqttSuperUser",
            "serviceName": "user",
            "permissionDesc": "Mqtt超级用户校验",
            "exValues": null
        },
        {
            "id": 737,
            "name": "添加资源",
            "permissionToken": "AddResources",
            "serviceName": "user",
            "permissionDesc": "添加资源",
            "exValues": null
        },
        {
            "id": 912,
            "name": "修改警报联系人",
            "permissionToken": "UpdateWarnPerson",
            "serviceName": "iot",
            "permissionDesc": "修改警报联系人",
            "exValues": null
        },
        {
            "id": 710,
            "name": "查询权限",
            "permissionToken": "DescribePermission",
            "serviceName": "user",
            "permissionDesc": "查询系统权限",
            "exValues": null
        },
        {
            "id": 920,
            "name": "删除标准功能点",
            "permissionToken": "DeleteStandardFunction",
            "serviceName": "iot",
            "permissionDesc": "删除标准功能点",
            "exValues": null
        },
        {
            "id": 718,
            "name": "删除公司",
            "permissionToken": "DeleteCompany",
            "serviceName": "user",
            "permissionDesc": "删除公司",
            "exValues": null
        },
        {
            "id": 928,
            "name": "管理应用",
            "permissionToken": "ManageApplication",
            "serviceName": "user",
            "permissionDesc": "管理应用",
            "exValues": null
        },
        {
            "id": 988,
            "name": "修改计算任务",
            "permissionToken": "UpdateStability",
            "serviceName": "mdnet",
            "permissionDesc": "修改边坡稳定性分析任务",
            "exValues": null
        },
        {
            "id": 907,
            "name": "批量导入物联网卡",
            "permissionToken": "ImportSimInfo",
            "serviceName": "iot",
            "permissionDesc": "批量导入物联网卡",
            "exValues": null
        },
        {
            "id": 787,
            "name": "添加产品",
            "permissionToken": "AddProduct",
            "serviceName": "iot",
            "permissionDesc": "添加产品",
            "exValues": null
        },
        {
            "id": 792,
            "name": "描述设备",
            "permissionToken": "DescribeDevice",
            "serviceName": "iot",
            "permissionDesc": "描述设备，查询设备最新状态",
            "exValues": null
        },
        {
            "id": 954,
            "name": "查询设备所在公司",
            "permissionToken": "ListDeviceCompany",
            "serviceName": "iot",
            "permissionDesc": "查询设备所在公司",
            "exValues": null
        },
        {
            "id": 735,
            "name": "删除公司外部用户",
            "permissionToken": "DeleteCompanyExternalUser",
            "serviceName": "user",
            "permissionDesc": "删除公司外部用户",
            "exValues": null
        },
        {
            "id": 1018,
            "name": "查询iot配置",
            "permissionToken": "DescribeIotCommonConfig",
            "serviceName": "iot",
            "permissionDesc": "查询iot配置",
            "exValues": null
        },
        {
            "id": 903,
            "name": "批量获取物联网卡基础信息",
            "permissionToken": "ListSim",
            "serviceName": "iot",
            "permissionDesc": "批量获取物联网卡基础信息，查询流量池统计信息，查询公司流量池列表",
            "exValues": null
        },
        {
            "id": 973,
            "name": "删除MD-NET平台信息",
            "permissionToken": "DeleteMdnetInfo",
            "serviceName": "mdnet",
            "permissionDesc": "删除MD-NET平台信息",
            "exValues": null
        },
        {
            "id": 992,
            "name": "删除Mdnet资源",
            "permissionToken": "DeleteMdnetResource",
            "serviceName": "mdnet",
            "permissionDesc": "删除Mdnet资源",
            "exValues": null
        },
        {
            "id": 909,
            "name": "查询物联网卡详情",
            "permissionToken": "DescribeSim",
            "serviceName": "iot",
            "permissionDesc": "查询单个详情，批量查询物联网卡详情，查询流量历史",
            "exValues": null
        },
        {
            "id": 994,
            "name": "查询iot信息",
            "permissionToken": "ListIotInfo",
            "serviceName": "iot",
            "permissionDesc": "查询iot信息",
            "exValues": null
        },
        {
            "id": 788,
            "name": "删除产品",
            "permissionToken": "DeleteProduct",
            "serviceName": "iot",
            "permissionDesc": "删除产品",
            "exValues": null
        },
        {
            "id": 914,
            "name": "查询权限策略",
            "permissionToken": "DescribePermissionStrategy",
            "serviceName": "user",
            "permissionDesc": "查询权限策略",
            "exValues": null
        },
        {
            "id": 983,
            "name": "查询MD-NET平台超级信息",
            "permissionToken": "ListSuperMdnetInfo",
            "serviceName": "mdnet",
            "permissionDesc": "查询MD-NET平台超级信息",
            "exValues": null
        },
        {
            "id": 944,
            "name": "HttpHubFullAccess",
            "permissionToken": "HttpHubFullAccess",
            "serviceName": "iot",
            "permissionDesc": "HttpHubFullAccess",
            "exValues": null
        },
        {
            "id": 982,
            "name": "查询项目列表",
            "permissionToken": "ListProject",
            "serviceName": "mdnet",
            "permissionDesc": "查询项目列表",
            "exValues": null
        },
        {
            "id": 989,
            "name": "修改MD-NET平台超级信息",
            "permissionToken": "UpdateSuperMdnetInfo",
            "serviceName": "mdnet",
            "permissionDesc": "修改MD-NET平台超级信息",
            "exValues": null
        },
        {
            "id": 790,
            "name": "删除设备",
            "permissionToken": "DeleteDevice",
            "serviceName": "iot",
            "permissionDesc": "删除设备",
            "exValues": null
        },
        {
            "id": 712,
            "name": "修改用户组",
            "permissionToken": "UpdatePermissionGroup",
            "serviceName": "user",
            "permissionDesc": "管理用户组",
            "exValues": null
        },
        {
            "id": 937,
            "name": "GNSS平台首页",
            "permissionToken": "DescribeGnssDashboard",
            "serviceName": "gnss",
            "permissionDesc": "登录成功并拥有此权限才能跳转至平台首页",
            "exValues": null
        },
        {
            "id": 953,
            "name": "测试权限",
            "permissionToken": "testtest",
            "serviceName": "user",
            "permissionDesc": "testtest1",
            "exValues": "testtest"
        },
        {
            "id": 739,
            "name": "修改资源组",
            "permissionToken": "UpdateResourceGroup",
            "serviceName": "user",
            "permissionDesc": "修改资源组",
            "exValues": null
        },
        {
            "id": 979,
            "name": "描述项目声光报警",
            "permissionToken": "DescribeProjectWarnLight",
            "serviceName": "mdnet",
            "permissionDesc": "描述项目声光报警",
            "exValues": null
        },
        {
            "id": 927,
            "name": "查询应用列表",
            "permissionToken": "ListApplication",
            "serviceName": "user",
            "permissionDesc": "查询应用列表",
            "exValues": null
        },
        {
            "id": 938,
            "name": "用户权限平台首页",
            "permissionToken": "DescribeUserDashboard",
            "serviceName": "user",
            "permissionDesc": "登录成功并拥有此权限才能跳转至平台首页",
            "exValues": null
        },
        {
            "id": 960,
            "name": "编辑设备组",
            "permissionToken": "UpdateDeviceGroup",
            "serviceName": "iot",
            "permissionDesc": "新增，修改设备组，设备组新增设备，设备组内移除设备",
            "exValues": null
        },
        {
            "id": 987,
            "name": "修改项目所属公司",
            "permissionToken": "UpdateProjectCompany",
            "serviceName": "mdnet",
            "permissionDesc": "修改项目所属公司",
            "exValues": null
        },
        {
            "id": 711,
            "name": "删除权限",
            "permissionToken": "DeletePermission",
            "serviceName": "user",
            "permissionDesc": "删除权限",
            "exValues": null
        },
        {
            "id": 780,
            "name": "查询设备分页列表",
            "permissionToken": "ListDevice",
            "serviceName": "iot",
            "permissionDesc": "查询设备分页列表",
            "exValues": "查询设备分页列表"
        },
        {
            "id": 783,
            "name": "查看产品详情",
            "permissionToken": "DescribeProduct",
            "serviceName": "iot",
            "permissionDesc": "查看产品详情",
            "exValues": null
        },
        {
            "id": 971,
            "name": "添加项目",
            "permissionToken": "AddProject",
            "serviceName": "mdnet",
            "permissionDesc": "在当前公司中添加项目",
            "exValues": null
        },
        {
            "id": 910,
            "name": "查询警报联系人",
            "permissionToken": "ListWarnPerson",
            "serviceName": "iot",
            "permissionDesc": "查询警报联系人",
            "exValues": null
        },
        {
            "id": 761,
            "name": "添加Iot资源",
            "permissionToken": "AddIotResource",
            "serviceName": "iot",
            "permissionDesc": "添加Iot资源",
            "exValues": null
        },
        {
            "id": 921,
            "name": "修改标准功能点",
            "permissionToken": "UpdateStandardFunction",
            "serviceName": "iot",
            "permissionDesc": "修改标准功能点",
            "exValues": null
        },
        {
            "id": 969,
            "name": "设置通用配置",
            "permissionToken": "UpdateCommonConfig",
            "serviceName": "mdnet",
            "permissionDesc": "设置系统通用配置",
            "exValues": null
        },
        {
            "id": 729,
            "name": "删除用户",
            "permissionToken": "DeleteUser",
            "serviceName": "user",
            "permissionDesc": "删除用户",
            "exValues": null
        },
        {
            "id": 975,
            "name": "删除计算任务",
            "permissionToken": "DeleteStability",
            "serviceName": "mdnet",
            "permissionDesc": "删除边坡稳定性分析计算任务",
            "exValues": null
        },
        {
            "id": 943,
            "name": "米度企业权限",
            "permissionToken": "medotest",
            "serviceName": "user",
            "permissionDesc": "仅米度企业权限可见",
            "exValues": null
        },
        {
            "id": 913,
            "name": "删除警报联系人",
            "permissionToken": "DeleteWarnPerson",
            "serviceName": "iot",
            "permissionDesc": "删除警报联系人",
            "exValues": null
        },
        {
            "id": 728,
            "name": "管理用户",
            "permissionToken": "UpdateUser",
            "serviceName": "user",
            "permissionDesc": "管理用户",
            "exValues": null
        },
        {
            "id": 782,
            "name": "创建设备",
            "permissionToken": "AddDevice",
            "serviceName": "iot",
            "permissionDesc": "创建设备",
            "exValues": null
        },
        {
            "id": 794,
            "name": "修改部门",
            "permissionToken": "UpdateDepartment",
            "serviceName": "user",
            "permissionDesc": "修改部门",
            "exValues": null
        },
        {
            "id": 961,
            "name": "新增设备组",
            "permissionToken": "AddDeviceGroup",
            "serviceName": "iot",
            "permissionDesc": "新增设备组",
            "exValues": null
        },
        {
            "id": 964,
            "name": "管理传感器数据",
            "permissionToken": "ManagerSensorData",
            "serviceName": "iot",
            "permissionDesc": "管理传感器数据",
            "exValues": null
        },
        {
            "id": 966,
            "name": "设备导出",
            "permissionToken": "ExportDevice",
            "serviceName": "iot",
            "permissionDesc": "设备导出",
            "exValues": null
        },
        {
            "id": 902,
            "name": "修改权限",
            "permissionToken": "UpdatePermission",
            "serviceName": "user",
            "permissionDesc": "修改权限",
            "exValues": null
        },
        {
            "id": 926,
            "name": "删除应用",
            "permissionToken": "DeleteApplication",
            "serviceName": "user",
            "permissionDesc": "删除应用",
            "exValues": null
        },
        {
            "id": 958,
            "name": "数据基因管理",
            "permissionToken": "ManagerGene",
            "serviceName": "iot",
            "permissionDesc": "数据基因管理",
            "exValues": null
        },
        {
            "id": 791,
            "name": "转移iot资源",
            "permissionToken": "TransferIotResource",
            "serviceName": "iot",
            "permissionDesc": "转移iot资源",
            "exValues": null
        },
        {
            "id": 723,
            "name": "删除部门用户",
            "permissionToken": "DeleteDepartmentUser",
            "serviceName": "user",
            "permissionDesc": "删除部门用户",
            "exValues": null
        },
        {
            "id": 918,
            "name": "删除物联网资源",
            "permissionToken": "DeleteIotResource",
            "serviceName": "iot",
            "permissionDesc": "删除物联网资源",
            "exValues": null
        },
        {
            "id": 752,
            "name": "查询权限列表",
            "permissionToken": "ListPermission",
            "serviceName": "user",
            "permissionDesc": "查询权限列表",
            "exValues": null
        },
        {
            "id": 940,
            "name": "mcloud首页",
            "permissionToken": "DescribeMcloudDashboard",
            "serviceName": "mcloud",
            "permissionDesc": "登录成功并拥有此权限才能跳转至首页",
            "exValues": null
        },
        {
            "id": 990,
            "name": "描述用户访问控制",
            "permissionToken": "DescribeUserAccessControl",
            "serviceName": "mdnet",
            "permissionDesc": "描述用户访问控制",
            "exValues": null
        },
        {
            "id": 726,
            "name": "查询权限策略列表",
            "permissionToken": "ListPermissionStrategy",
            "serviceName": "user",
            "permissionDesc": "查询权限策略列表",
            "exValues": null
        },
        {
            "id": 730,
            "name": "查询用户列表",
            "permissionToken": "ListUser",
            "serviceName": "user",
            "permissionDesc": "查询用户列表",
            "exValues": null
        },
        {
            "id": 734,
            "name": "添加公司外部用户",
            "permissionToken": "AddCompanyExternalUser",
            "serviceName": "user",
            "permissionDesc": "添加公司外部用户",
            "exValues": null
        },
        {
            "id": 906,
            "name": "SIM卡同步信息",
            "permissionToken": "UpdateSim",
            "serviceName": "iot",
            "permissionDesc": "同步更新SIM卡信息，设备绑定，设备解除，设置标签\n同步流量池最新状态,添加流量池",
            "exValues": null
        },
        {
            "id": 917,
            "name": "查询部门",
            "permissionToken": "DescribeDepartment",
            "serviceName": "user",
            "permissionDesc": "查询部门",
            "exValues": null
        },
        {
            "id": 911,
            "name": "添加警报联系人",
            "permissionToken": "AddWarnPerson",
            "serviceName": "iot",
            "permissionDesc": "添加警报联系人",
            "exValues": null
        },
        {
            "id": 738,
            "name": "删除资源",
            "permissionToken": "DeleteResources",
            "serviceName": "user",
            "permissionDesc": "删除资源",
            "exValues": null
        },
        {
            "id": 993,
            "name": "Mdnet资源转移",
            "permissionToken": "TransferMdnetResource",
            "serviceName": "mdnet",
            "permissionDesc": "Mdnet资源转移",
            "exValues": null
        },
        {
            "id": 736,
            "name": "查询公司外部用户列表",
            "permissionToken": "ListExternalPerson",
            "serviceName": "user",
            "permissionDesc": "查询公司外部用户列表",
            "exValues": null
        },
        {
            "id": 968,
            "name": "推送物联网卡临期信息",
            "permissionToken": "SendSimOfNearTime",
            "serviceName": "iot",
            "permissionDesc": "推送物联网卡临期信息",
            "exValues": null
        },
        {
            "id": 985,
            "name": "修改MD-NET平台信息",
            "permissionToken": "UpdateMdnetInfo",
            "serviceName": "mdnet",
            "permissionDesc": "修改MD-NET平台信息",
            "exValues": null
        },
        {
            "id": 731,
            "name": "查询用户",
            "permissionToken": "DescribeUser",
            "serviceName": "user",
            "permissionDesc": "查询用户",
            "exValues": null
        },
        {
            "id": 974,
            "name": "删除项目",
            "permissionToken": "DeleteProject",
            "serviceName": "mdnet",
            "permissionDesc": "删除项目，同时解除该项目和分组、设备的关联",
            "exValues": null
        },
        {
            "id": 981,
            "name": "查询MD-NET平台信息列表",
            "permissionToken": "ListMdnetInfo",
            "serviceName": "mdnet",
            "permissionDesc": "查询MD-NET平台信息列表",
            "exValues": null
        },
        {
            "id": 986,
            "name": "修改项目",
            "permissionToken": "UpdateProject",
            "serviceName": "mdnet",
            "permissionDesc": "修改项目",
            "exValues": null
        },
        {
            "id": 724,
            "name": "修改权限策略",
            "permissionToken": "UpdatePermissionStrategy",
            "serviceName": "user",
            "permissionDesc": "修改权限策略",
            "exValues": null
        },
        {
            "id": 922,
            "name": "添加标准功能点",
            "permissionToken": "AddStandardFunction",
            "serviceName": "iot",
            "permissionDesc": "添加标准功能点",
            "exValues": null
        },
        {
            "id": 786,
            "name": "查询警报联系人设备列表",
            "permissionToken": "DescribeWarnPerson",
            "serviceName": "iot",
            "permissionDesc": "GetDeviceListByWarnPerson",
            "exValues": null
        },
        {
            "id": 991,
            "name": "添加Mdnet资源",
            "permissionToken": "AddMdnetResource",
            "serviceName": "mdnet",
            "permissionDesc": "添加Mdnet资源",
            "exValues": null
        },
        {
            "id": 939,
            "name": "MD-NET平台首页",
            "permissionToken": "DescribeMdnetDashboard",
            "serviceName": "mdnet",
            "permissionDesc": "登录成功并拥有此权限才能跳转至平台首页",
            "exValues": null
        },
        {
            "id": 725,
            "name": "删除权限策略",
            "permissionToken": "DeletePermissionStrategy",
            "serviceName": "user",
            "permissionDesc": "删除权限策略",
            "exValues": null
        },
        {
            "id": 741,
            "name": "查询资源组列表",
            "permissionToken": "ListResourceGroup",
            "serviceName": "user",
            "permissionDesc": "查询资源组列表",
            "exValues": null
        },
        {
            "id": 919,
            "name": "物模型管理",
            "permissionToken": "ListCompanyFunction",
            "serviceName": "iot",
            "permissionDesc": "查询物模型功能点",
            "exValues": null
        },
        {
            "id": 925,
            "name": "修改应用",
            "permissionToken": "UpdateApplication",
            "serviceName": "user",
            "permissionDesc": "修改应用",
            "exValues": null
        },
        {
            "id": 716,
            "name": "查询公司",
            "permissionToken": "DescribeCompany",
            "serviceName": "user",
            "permissionDesc": "查询公司",
            "exValues": null
        },
        {
            "id": 753,
            "name": "查询资源列表",
            "permissionToken": "ListResource",
            "serviceName": "user",
            "permissionDesc": "查询资源列表",
            "exValues": null
        },
        {
            "id": 905,
            "name": "设备下发指令",
            "permissionToken": "DispatchCmd",
            "serviceName": "iot",
            "permissionDesc": "设备下发指令",
            "exValues": null
        },
        {
            "id": 923,
            "name": "查询超级信息",
            "permissionToken": "ListSuperInfo",
            "serviceName": "iot",
            "permissionDesc": "查询超级信息",
            "exValues": null
        },
        {
            "id": 740,
            "name": "删除资源组",
            "permissionToken": "DeleteResourceGroup",
            "serviceName": "user",
            "permissionDesc": "删除资源组",
            "exValues": null
        },
        {
            "id": 972,
            "name": "创建计算任务",
            "permissionToken": "AddStability",
            "serviceName": "mdnet",
            "permissionDesc": "创建边坡稳定性分析计算任务",
            "exValues": null
        },
        {
            "id": 713,
            "name": "删除用户组",
            "permissionToken": "DeletePermissionGroup",
            "serviceName": "user",
            "permissionDesc": "删除用户组",
            "exValues": null
        },
        {
            "id": 977,
            "name": "描述MD-NET平台信息",
            "permissionToken": "DescribeMdnetInfo",
            "serviceName": "mdnet",
            "permissionDesc": "描述MD-NET平台信息",
            "exValues": null
        },
        {
            "id": 721,
            "name": "删除部门",
            "permissionToken": "DeleteDepartment",
            "serviceName": "user",
            "permissionDesc": "删除部门",
            "exValues": null
        },
        {
            "id": 727,
            "name": "管理权限策略分组",
            "permissionToken": "ManageStrategyGroup",
            "serviceName": "user",
            "permissionDesc": "管理权限策略分组",
            "exValues": null
        },
        {
            "id": 967,
            "name": "批量更新指令响应结果",
            "permissionToken": "UpdateCmdStatusByCmdStatusAndTime",
            "serviceName": "iot",
            "permissionDesc": "批量更新指令响应结果",
            "exValues": null
        },
        {
            "id": 976,
            "name": "描述调洪演算",
            "permissionToken": "DescirbeFlood",
            "serviceName": "mdnet",
            "permissionDesc": "描述调洪演算",
            "exValues": null
        },
        {
            "id": 722,
            "name": "添加部门用户",
            "permissionToken": "AddDepartmentUser",
            "serviceName": "user",
            "permissionDesc": "添加部门用户",
            "exValues": null
        },
        {
            "id": 1001,
            "name": "修改Mdnet资源",
            "permissionToken": "UpdateMdnetResourceDesc",
            "serviceName": "mdnet",
            "permissionDesc": "修改Mdnet资源",
            "exValues": null
        }
    ]
}

#### 分页查询用户所在的所有公司
     Headers {Authorization:""}
     POST /auth/api/v1/QueryUserInCompany

        Params
         {
            "pageSize": 5,
            "currentPage": 1,
            "companyName": null,
            "includeChild": false
        }

     Response
     {
        "code": 0,
        "msg": null,
        "data": {
            "totalCount": 1,
            "totalPage": 1,
            "currentPageData": [
                {
                    "companyID": 138,
                    "companyName": "上海米度测控科技有限公司"
                }
            ]
        }
    }

#### 获取公司信息
     Headers {Authorization:""}
     POST /auth/api/v1/GetCompanyInfo

        Params
         {
            "companyID": ""
        }

     Response
        {
    "code": 0,
    "msg": null,
    "data": {
        "id": 138,
        "shortName": "米度测控",
        "fullName": "上海米度测控科技有限公司",
        "parentID": null,
        "desc": "各类工程建设活动；建设工程勘察；建设工程质量检测；水利工程质量检测；地质灾害治理工程施工；测绘服务。（依法须经批准的项目，经相关部门批准后方可开展经营活动，具体经营项目以相关部门批准文件或许可证件为准） 一般项目：测控科技、计算机软硬件、网络科技、电子科技、光机电一体化、能源与环保科技、导航设备领域内的技术开发、技术转让、技术咨询、技术服务，货物进出口，技术进出口，电子产品及配件、导航设备及配件研发，网络工程，电子产品、电子元器件、电线电缆、机电设备、机械设备及配件、照相器材、电讯器材、通讯器材、通信器材、通信设备、仪器仪表、计算机软硬件、摄影器材、实验室设备、导航设备及仪器的销售，卫星导航服务，地理遥感信息服务，信息系统集成服务，安全系统监控服务，水文服务，互联网数据服务，物联网服务，物联网技术服务，卫星技术综合应用系统集成，卫星遥感数据处理，卫星遥感应用系统集成，软件开发，智能水务系统开发，以下制造限分支机构经营：电子产品及配件、机电设备、机械设备及配件、物联网设备，导航、测绘、气象及海洋专用仪器，导航终端，卫星移动通信终端，水质污染物监测及检测仪器仪表，仪器仪表，通信设备;",
        "level": 0,
        "createUserID": 1,
        "createTime": "2020-11-30 17:07:05",
        "updateUserID": 541,
        "updateTime": "2021-07-22 15:17:50",
        "hasChild": true,
        "delete": false,
        "address": "上海市闵行区联航路1188号32号楼",
        "phone": "021-33923627",
        "legalPerson": "李玮煜",
        "scale": "小型(20≤人员<300)",
        "industry": "科技推广和应用服务业",
        "nature": "私营企业",
        "webSite": "http://www.shmedo.cn"
    }
}

### 设备模块
#### 统计公司下的设备
     Headers {Authorization:""}
     POST /iot/manager/api/v1/GetDeviceStatByCompanyID

        Params
         {
            "companyID": ""
        }

     Response
        {
            "code": 0,
            "msg": null,
            "data": {
                "totalCount": 44,
                "onlineCount": null,
                "offlineCount": 21,
                "usableCount": 44,
                "unusableCount": null,
                "onlinePercent": 0.0
            }
        }

#### 分页查询产品列表
     Headers {Authorization:""}
     POST /iot/manager/api/v1/QueryProduct

        Params
         {
            "companyID": "",
            "productName": "",
             "productType": "",
              "useProtocol": "",
               "currentPage": 1,
                "pageSize": 100
        }

     Response
        {
            "code": 0,
            "msg": null,
            "data": {
                "totalCount": 73,
                "totalPage": 1,
                "currentPageData": [
                    {
                        "id": 312,
                        "productName": "test1206",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "HTTP",
                        "deviceNum": null,
                        "createTime": "2021-12-06 14:38:17",
                        "productToken": "test1206",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 310,
                        "productName": "test01129",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "HTTP",
                        "deviceNum": null,
                        "createTime": "2021-11-16 13:58:12",
                        "productToken": "test01116",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 296,
                        "productName": "雨量计",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "HTTP",
                        "deviceNum": 1,
                        "createTime": "2021-09-16 15:18:45",
                        "productToken": "131231",
                        "companyID": 138,
                        "modelNum": 1
                    },
                    {
                        "id": 295,
                        "productName": "地表裂缝计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:27",
                        "productToken": "test44",
                        "companyID": 138,
                        "modelNum": 2
                    },
                    {
                        "id": 294,
                        "productName": "墙裂缝计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:27",
                        "productToken": "test43",
                        "companyID": 138,
                        "modelNum": 5
                    },
                    {
                        "id": 293,
                        "productName": "加速度计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:27",
                        "productToken": "test42",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 292,
                        "productName": "泥位计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:27",
                        "productToken": "test41",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 291,
                        "productName": "雨量计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:27",
                        "productToken": "test40",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 290,
                        "productName": "土壤含水率（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:27",
                        "productToken": "test39",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 289,
                        "productName": "裂缝计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:26",
                        "productToken": "test38",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 288,
                        "productName": "GNSS结果数据（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 16,
                        "createTime": "2021-09-13 15:45:26",
                        "productToken": "test37",
                        "companyID": 138,
                        "modelNum": 1
                    },
                    {
                        "id": 287,
                        "productName": "倾角计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:26",
                        "productToken": "test36",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 286,
                        "productName": "水压力（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:26",
                        "productToken": "test35",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 285,
                        "productName": "次声（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:26",
                        "productToken": "test34",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 284,
                        "productName": "土压力计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:26",
                        "productToken": "test33",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 283,
                        "productName": "振弦式应压力计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:25",
                        "productToken": "test32",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 282,
                        "productName": "地表位移（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:25",
                        "productToken": "test31",
                        "companyID": 138,
                        "modelNum": 1
                    },
                    {
                        "id": 281,
                        "productName": "深部位移（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:25",
                        "productToken": "test30",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 280,
                        "productName": "倾斜仪（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:25",
                        "productToken": "test29",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 279,
                        "productName": "地下水位（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:25",
                        "productToken": "test28",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 278,
                        "productName": "多点位移（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:25",
                        "productToken": "test27",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 277,
                        "productName": "渗压计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:24",
                        "productToken": "test26",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 276,
                        "productName": "流速计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:24",
                        "productToken": "test25",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 275,
                        "productName": "气温（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:24",
                        "productToken": "test24",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 274,
                        "productName": "TDR变形计（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:24",
                        "productToken": "test23",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 273,
                        "productName": "泉水流量（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:24",
                        "productToken": "test22",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 272,
                        "productName": "沉降仪（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:23",
                        "productToken": "test21",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 271,
                        "productName": "泵站数据（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:23",
                        "productToken": "test20",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 270,
                        "productName": "干滩（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:23",
                        "productToken": "test19",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 269,
                        "productName": "浊度（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:23",
                        "productToken": "test18",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 268,
                        "productName": "湿度（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:23",
                        "productToken": "test17",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 267,
                        "productName": "轴力（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:23",
                        "productToken": "test16",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 266,
                        "productName": "PH（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:22",
                        "productToken": "test15",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 265,
                        "productName": "静力水准仪水位数据（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:22",
                        "productToken": "test14",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 264,
                        "productName": "钻孔测协议（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:22",
                        "productToken": "test13",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 263,
                        "productName": "平面位移（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:22",
                        "productToken": "test12",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 262,
                        "productName": "气象观测（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:22",
                        "productToken": "test11",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 261,
                        "productName": "振幅加速度（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:22",
                        "productToken": "test10",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 260,
                        "productName": "设备报警（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:21",
                        "productToken": "test09",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 259,
                        "productName": "设备日志（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:21",
                        "productToken": "test08",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 258,
                        "productName": "预警喇叭（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:21",
                        "productToken": "test07",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 257,
                        "productName": "断线报警器（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:21",
                        "productToken": "test06",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 256,
                        "productName": "GNSS原始数据（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:21",
                        "productToken": "test05",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 255,
                        "productName": "测量点平均值数据（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:21",
                        "productToken": "test04",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 254,
                        "productName": "监测测量结束状态报文（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:20",
                        "productToken": "test03",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 253,
                        "productName": "平差结果（测试）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-09-13 15:45:20",
                        "productToken": "test02",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 251,
                        "productName": "M20-倾角计",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-09-10 10:10:40",
                        "productToken": "M20_1",
                        "companyID": 138,
                        "modelNum": 2
                    },
                    {
                        "id": 249,
                        "productName": "lora（测斜仪）",
                        "productType": "child",
                        "productTypeChName": "子设备",
                        "useProtocol": "Modbus",
                        "deviceNum": 1,
                        "createTime": "2021-09-10 09:55:20",
                        "productToken": "VMS_2",
                        "companyID": 138,
                        "modelNum": 3
                    },
                    {
                        "id": 248,
                        "productName": "lora（钢筋计）",
                        "productType": "child",
                        "productTypeChName": "子设备",
                        "useProtocol": "Modbus",
                        "deviceNum": 1,
                        "createTime": "2021-09-10 09:52:45",
                        "productToken": "VMS_1",
                        "companyID": 138,
                        "modelNum": 3
                    },
                    {
                        "id": 245,
                        "productName": "DAS-静力水准采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-26 16:15:46",
                        "productToken": "DAS-StaticLevelingCollector",
                        "companyID": 138,
                        "modelNum": 5
                    },
                    {
                        "id": 244,
                        "productName": "lora（崩滑仪）",
                        "productType": "child",
                        "productTypeChName": "子设备",
                        "useProtocol": "Modbus",
                        "deviceNum": 2,
                        "createTime": "2021-08-26 15:53:29",
                        "productToken": "VMS",
                        "companyID": 138,
                        "modelNum": 3
                    },
                    {
                        "id": 243,
                        "productName": "M20-GNSS",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-26 15:52:48",
                        "productToken": "M20",
                        "companyID": 138,
                        "modelNum": 2
                    },
                    {
                        "id": 242,
                        "productName": "E40-GNSS",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 2,
                        "createTime": "2021-08-26 15:51:58",
                        "productToken": "E40",
                        "companyID": 138,
                        "modelNum": 4
                    },
                    {
                        "id": 241,
                        "productName": "E60-GNSS",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-26 15:51:15",
                        "productToken": "E60",
                        "companyID": 138,
                        "modelNum": 4
                    },
                    {
                        "id": 240,
                        "productName": "DAS--倾角采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-26 15:50:08",
                        "productToken": "DAS-InclinationCollector",
                        "companyID": 138,
                        "modelNum": 5
                    },
                    {
                        "id": 239,
                        "productName": "DAS--渗流采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-26 15:48:31",
                        "productToken": "DAS-SeepageCollector",
                        "companyID": 138,
                        "modelNum": 5
                    },
                    {
                        "id": 238,
                        "productName": "DAS--内部位移采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-26 15:47:06",
                        "productToken": "DAS-InternalDisplacement",
                        "companyID": 138,
                        "modelNum": 3
                    },
                    {
                        "id": 236,
                        "productName": "DAS-土壤含水率采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-26 15:28:06",
                        "productToken": "DAS-SoilMoistureContent",
                        "companyID": 138,
                        "modelNum": 4
                    },
                    {
                        "id": 235,
                        "productName": "DAS-次声采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-26 15:26:56",
                        "productToken": "DAS-InfrasoundCollector",
                        "companyID": 138,
                        "modelNum": 5
                    },
                    {
                        "id": 234,
                        "productName": "DAS-振弦渗压计",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-26 15:21:45",
                        "productToken": "DAS-VibratingWireCollector",
                        "companyID": 138,
                        "modelNum": 3
                    },
                    {
                        "id": 233,
                        "productName": "DAS-超声波物位采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-26 15:18:58",
                        "productToken": "DAS-UltrasonicLevelCollector",
                        "companyID": 138,
                        "modelNum": 5
                    },
                    {
                        "id": 227,
                        "productName": "DAS-雷达物位采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-26 15:15:21",
                        "productToken": "DAS-RadarLevelCollector",
                        "companyID": 138,
                        "modelNum": 3
                    },
                    {
                        "id": 226,
                        "productName": "DAS-雨量采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-26 15:09:12",
                        "productToken": "DAS-RainfallCollector",
                        "companyID": 138,
                        "modelNum": 2
                    },
                    {
                        "id": 225,
                        "productName": "DAS-裂缝采集器",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-26 15:08:47",
                        "productToken": "DAS-CrackCollector",
                        "companyID": 138,
                        "modelNum": 4
                    },
                    {
                        "id": 224,
                        "productName": "E40S——倾角",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-25 15:09:48",
                        "productToken": "E40S07",
                        "companyID": 138,
                        "modelNum": 4
                    },
                    {
                        "id": 212,
                        "productName": "全站仪监测站（重要勿删）",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-16 21:08:41",
                        "productToken": "iTPS",
                        "companyID": 138,
                        "modelNum": 4
                    },
                    {
                        "id": 211,
                        "productName": "0813测试产品123",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-13 13:23:35",
                        "productToken": "0813test",
                        "companyID": 138,
                        "modelNum": 4
                    },
                    {
                        "id": 210,
                        "productName": "子设备测试",
                        "productType": "child",
                        "productTypeChName": "子设备",
                        "useProtocol": "LORA",
                        "deviceNum": 2,
                        "createTime": "2021-08-13 11:58:15",
                        "productToken": "zishebei",
                        "companyID": 138,
                        "modelNum": 1
                    },
                    {
                        "id": 198,
                        "productName": "0811test",
                        "productType": "gateway",
                        "productTypeChName": "网关设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 1,
                        "createTime": "2021-08-11 10:09:47",
                        "productToken": "0811test",
                        "companyID": 138,
                        "modelNum": 33
                    },
                    {
                        "id": 176,
                        "productName": "LORA网关",
                        "productType": "gateway",
                        "productTypeChName": "网关设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 2,
                        "createTime": "2021-08-04 18:37:53",
                        "productToken": "GW300-LORA网关",
                        "companyID": 138,
                        "modelNum": 5
                    },
                    {
                        "id": 173,
                        "productName": "视频",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": null,
                        "createTime": "2021-08-04 18:23:37",
                        "productToken": "PVS",
                        "companyID": 138,
                        "modelNum": 0
                    },
                    {
                        "id": 132,
                        "productName": "DAS",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 2,
                        "createTime": "2021-07-28 18:21:38",
                        "productToken": "DAS",
                        "companyID": 138,
                        "modelNum": 8
                    },
                    {
                        "id": 131,
                        "productName": "E40S",
                        "productType": "direct",
                        "productTypeChName": "直连设备",
                        "useProtocol": "MQTT",
                        "deviceNum": 4,
                        "createTime": "2021-07-28 14:56:21",
                        "productToken": "E40S",
                        "companyID": 138,
                        "modelNum": 6
                    }
                ]
            }
    } 

#### 查询设备列表
     Headers {Authorization:""}
     POST /iot/manager/api/v1/GetDeviceList

        Params
         {
            "companyID": "",
             "pageSize": 5,
            "currentPage": 1,
            "deviceToken": null,
            "firmwareVersion": null,
            "tokenAndVersion": false,
            "productID": null,
            "tagKey": null,
            "tagValue": null,
            "onlineStatus": null,
            "deviceStatus": null
        }

     Response
         {
    "code": 0,
    "msg": null,
    "data": {
        "totalCount": 44,
        "totalPage": 9,
        "currentPageData": [
            {
                "id": 15427,
                "companyID": 138,
                "companyName": "上海米度测控科技有限公司",
                "deviceToken": "150001L",
                "deviceName": "RTU-T 测试",
                "deviceDesc": null,
                "installLocation": null,
                "gpsLocation": "107.984363,26.577336",
                "onlineStatus": null,
                "deviceStatus": "启用",
                "allowWarn": true,
                "exValues": "12",
                "apiKey": null,
                "productID": 212,
                "productName": "全站仪监测站（重要勿删）",
                "productType": "direct",
                "firmwareVersion": "3.2.6",
                "lastActiveTime": null,
                "simList": null
            },
            {
                "id": 3848,
                "companyID": 138,
                "companyName": "上海米度测控科技有限公司",
                "deviceToken": "test1104",
                "deviceName": "test1104",
                "deviceDesc": null,
                "installLocation": null,
                "gpsLocation": null,
                "onlineStatus": null,
                "deviceStatus": "启用",
                "allowWarn": true,
                "exValues": null,
                "apiKey": null,
                "productID": 296,
                "productName": "雨量计",
                "productType": "direct",
                "firmwareVersion": null,
                "lastActiveTime": null,
                "simList": null
            },
            {
                "id": 2268,
                "companyID": 138,
                "companyName": "上海米度测控科技有限公司",
                "deviceToken": "test101901",
                "deviceName": "test101901",
                "deviceDesc": null,
                "installLocation": null,
                "gpsLocation": null,
                "onlineStatus": null,
                "deviceStatus": "启用",
                "allowWarn": true,
                "exValues": null,
                "apiKey": null,
                "productID": 198,
                "productName": "0811test",
                "productType": "gateway",
                "firmwareVersion": null,
                "lastActiveTime": null,
                "simList": null
            },
            {
                "id": 249,
                "companyID": 138,
                "companyName": "上海米度测控科技有限公司",
                "deviceToken": "217582L",
                "deviceName": "217582L",
                "deviceDesc": null,
                "installLocation": null,
                "gpsLocation": "107.984363,26.577336",
                "onlineStatus": false,
                "deviceStatus": "启用",
                "allowWarn": true,
                "exValues": null,
                "apiKey": null,
                "productID": 233,
                "productName": "DAS-超声波物位采集器",
                "productType": "direct",
                "firmwareVersion": "3.2.6",
                "lastActiveTime": null,
                "simList": [
                    {
                        "id": 1416,
                        "ccid": "89860493262190061966",
                        "simNo": "1440936961966",
                        "simIsp": "中国移动",
                        "vendor": "浙江企朋",
                        "deviceID": 249
                    }
                ]
            },
            {
                "id": 248,
                "companyID": 138,
                "companyName": "上海米度测控科技有限公司",
                "deviceToken": "22T015B",
                "deviceName": "22T016B-Name",
                "deviceDesc": null,
                "installLocation": null,
                "gpsLocation": null,
                "onlineStatus": null,
                "deviceStatus": "启用",
                "allowWarn": true,
                "exValues": null,
                "apiKey": null,
                "productID": 288,
                "productName": "GNSS结果数据（测试）",
                "productType": "direct",
                "firmwareVersion": null,
                "lastActiveTime": null,
                "simList": [
                    {
                        "id": 1301,
                        "ccid": "89860467092090116484",
                        "simNo": "1440673316484",
                        "simIsp": "中国移动",
                        "vendor": "浙江企朋",
                        "deviceID": 248
                    }
                ]
            }
        ]
    }
}

#### 获取设备概要信息
     Headers {Authorization:""}
     POST /iot/manager/api/v1/DescribeDeviceSimpleInfo

        Params
         {
            "deviceID": 15427,
            "deviceToken":"150001L"
         }

     Response
          {
                "code": 0,
                "msg": null,
                "data": {
                    "id": 15427,
                    "companyID": 138,
                    "productID": 212,
                    "productType": "direct",
                    "deviceToken": "150001L",
                    "deviceName": "RTU-T 测试",
                    "parentID": null,
                    "installLocation": null,
                    "gpsLocation": "107.984363,26.577336",
                    "deviceStatus": "启用",
                    "apiKey": "3945b936-3e10-457b-b567-d923545afb57",
                    "firmwareVersion": "3.2.6",
                    "exValues": "12",
                    "uniqueToken": "0669cefa-2651-43e9-9a9e-0054aa707a1b",
                    "allowWarn": true,
                    "warnInterval": 1440
                }
            }
#### 查询固件列表
     Headers {Authorization:""}
     POST /iot/manager/api/v1/GetFirmwareList

        Params
           {
            "companyID": {{companyID}},
            "productID": 224,
            "fwStatus": 0,
            "fwName": "",
            "fwVersion": "",
            "nameAndVersion": false,
            "pageSize": 10,
            "currentPage": 1
        }

     Response
            {
                "code": 0,
                "msg": null,
                "data": {
                    "totalCount": 1,
                    "totalPage": 1,
                    "currentPageData": [
                        {
                            "id": 119,
                            "fwName": "E40S_V1.4.6",
                            "fwVersion": "1111",
                            "fwMd5": "09cbbe068980195060266b4971e7dc38",
                            "fwNote": "",
                            "fwPath": "local-202110-182be7cf-ae83-468c-9bee-1cd3b0c37f5f.bin",
                            "fwSize": 1310744,
                            "productName": "E40S——倾角",
                            "productID": 224,
                            "productToken": "E40S07",
                            "fwStatus": 0,
                            "uploadUser": "测试系统管理员",
                            "uploadTime": "2021-10-13 10:03:25",
                            "uploadUserID": 539,
                            "absolutePath": "http://172.168.5.200:8020/202110/182be7cf-ae83-468c-9bee-1cd3b0c37f5f.bin",
                            "companyID": 138,
                            "companyName": "上海米度测控科技有限公司"
                        }
                    ]
                }
            }
#### 对单个设备进行固件升级
     Headers {Authorization:""}
     POST /iot/interactive/api/v1/FirmwareUpgrade
        Params
           {
            "deviceToken": "22T015B",
            "firmwareID": 119
        }

     Response

### 指令交互
#### 批量透明指令下发(限定同一产品)
   Headers {Authorization:""}
     POST /iot/interactive/api/v1/BatchDispatchRawCmd

        Params
        {
            "deviceTokenList": ["22T015B"],
            "cmdContent": "$cmd=sample"
        }

     Response
        {
            "deviceTokenList": ["22T015B"],
            "cmdContent": "$cmd=sample"
        }

#### 查询指令执行结果
   Headers {Authorization:""}
     POST /iot/manager/api/v1/QueryCmdResultByMsgID

        Params
           {
                "msgIDList": ["242b8636-793c-4342-a39c-17f2a8ecf52a"]
            }

     Response
         {
            "code": 0,
            "msg": null,
            "data": [
                {
                    "msgID": "242b8636-793c-4342-a39c-17f2a8ecf52a",
                    "deviceID": 248,
                    "deviceSN": "22T015B",
                    "cmdEngName": null,
                    "cmdChnName": "自定义指令",
                    "cmdContent": "$cmd=sample&msgid=242b8636-793c-4342-a39c-17f2a8ecf52a&apikey=b2e0cc5a-b935-43be-a14d-be6291d27d90",
                    "dispatchTime": "2021-12-22 15:08:58",
                    "cmdStatus": 1,
                    "cmdStatusString": "已下发等待响应",
                    "responseTime": null,
                    "responseContent": null,
                    "responseStatus": null,
                    "responseStatusString": null,
                    "dispatchUserID": 636,
                    "dispatchUserName": "宫贺",
                    "cmdID": "-1"
                }
            ]
        }