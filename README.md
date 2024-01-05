|major | minor | 备注 |
|:-:|:-:|:-:|
|1|9|0|运行|

<details>
<summary>示例</summary>
<summary>发送</summary>
<!-- 启动方案，会和前端页面产生冲突 -->
{
    major: 1,
    minor: 9
}

<summary>接收</summary>
{
  "major": 2,
  "minor": 5,
  "value": true
}
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|15|更改图像尺寸/相机分辨率|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
    major: 1,
    minor: 9
}

<summary>接收</summary>
{
  "major": 2,
  "minor": 5,
  "value": true
}
</details>

|major | minor  | 备注 |
|:-:|:-:|:-:|
|1|21||FTP设置|
<details>
<summary>示例</summary>
<summary>发送</summary>
return {
    major: 1,
    minor: 21, // 设置FTP路径
    value: {
        'name': 'FTP设置',//设置取名
  'ip': param.ip,//ftp服务器ip
  'path': param.path,//放置路径
  'user': param.user,//用户名
  'password': param.password//密码
    }
  }
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628384C5F",
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "minor": 21,
    "success": true,
    "value": {
      "ip": "192.168.10.128",
      "name": "FTP设置",
      "password": "1",
      "path": "/home",
      "user": "liua"
    }
  }
}

</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|25|GPO调试|
<details>
<summary>示例</summary>
<summary>发送</summary>
return {
    major: 1,
    minor: 25,
    value: {
        index: 0, // 灯的序号
        mode: {
            items: ['低电平', '高电平'],
            default: 0//默认状态为0或1
        }
    }
  }
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628384C5F",
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "minor": 25,
    "success": true,
    "value": {
      "index": 0,
      "mode": {
        "default": 0,
        "items": [
          "低电平",
          "高电平"
        ]
      }
    }
  }
}
</details>

|major | minor|备注 |
|:-:|:-:|:-:|
|1|28|时间校准|
<details>
<summary>示例</summary>
<summary>发送</summary>
return {
    major: 1,
    minor: 28,
    value: [2020, 7, 17, 16, 24, 45]//时间
  }
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628384C5F",
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "minor": 28,
    "success": true,
    "value": [
      2020,
      7,
      17,
      16,
      24,
      45
    ]
  }
}

</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|30|FTP测试|
<details>
<summary>示例</summary>
<summary>发送</summary>
return {
    major: 1,
    minor: 30
  }
<summary>接收</summary>
{
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "message": "NEED_STOP",
    "minor": 30,
    "success": false
  }
}

</details>

|major | minor|备注|
|:-:|:-:|:-:|
|1|31|修改相机id|

<details>
<summary>示例</summary>
<summary>发送</summary>

return {
    major: 1,
    minor: 31,
    value: 'name'//id名
  }
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628DEDD4D",
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "minor": 31,
    "success": true,
    "value": "camera002"
  }
}

</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|32|value取:1 使用全局曝光配置 2 使用工程曝光配置|

<details>

<summary>示例</summary>
<summary>发送</summary>
{
 "major": 1,
 "minor": 32,
 "value": 1//1 使用全局曝光配置 2 使用工程曝光配置
}
<summary>接收</summary>

{
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "message": "NEED_STOP",
    "minor": 32,
    "success": false
  }
}

</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|33|删除文件，value为数组，后端需要返回成功信息给前端|
<details>
<summary>示例</summary>
<summary>发送</summary>
{
 "major": 1,
 "minor": 33,
 "value": ["image/camera001_2020-07-29_07-39-36.jpg",
 "image/camera001_2020-07-30_07-18-36.jpg",
 "image/camera001_2020-07-30_13-27-50.jpg"]//要删除的数据
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628E9DEBD",
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "minor": 33,
    "success": true,
    "value": [
      "image/camera001_2020-07-29_07-39-36.jpg"
    ]
  }
}

</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|34|设置相机采图默认旋转角度|
<details>
<summary>示例</summary>
<summary>发送</summary>
{
 "major": 1,
 "minor": 34,
 "value": 0 // 0 旋转0度，1 旋转90度，2 旋转180度，3 旋转270度
}
<summary>接收</summary>

{
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "message": "NEED_STOP",
    "minor": 34,
    "success": false
  }
}
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|35|重启相机|
<details>
<summary>示例</summary>
<summary>发送</summary>

{
 "major": 1,
 "minor": 35
}
<summary>接收</summary>
无
</details>

|major | minor| 备注 |
|:-:|:-:|:-:|
|1|36|恢复出厂设置|
<details>
<summary>示例</summary>
<summary>发送</summary>
{
 "major": 1,
 "minor": 36
}
<summary>接收</summary>
无
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|41|查询后端固件版本|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
    "major":1,
    "minor":41
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628E9DEBD",
  "major": 2,
  "minor": 16,
  "value": "2023-12-14 15:45:47"//固件版本
}
</details>

|major | minor| 备注 |
|:-:|:-:|:-:|
|1|44|查询全局config|
<details>
<summary>示例</summary>
<summary>发送</summary>
{
    "major": 1,
    "minor": 44
}
<summary>接收</summary>
<!-- 超大json数据，内容为全局config -->
{"from":"camera001","mac":"001628DEDD4D","major":2,"minor":44,"value":{"set":{"AI":{"helmet":{"default":{"_ItemE":{"determineStrategy":["Center","BottomCenter","AnyPix"]},"aiLoopConfig":{"aiLoopActionTriggerMode":0,"detectInterval":100,"reportCount":5},"aiModelFile":{"classKey":["hat","no-hat"],"falseClassName":["hat"],"fileItems":[],"fileKey":["helmet"],"filename":"helmet.npubin","trueClassName":["no-hat"]},"aiOutputBoolText":{"outputLevelFalseText":"Safe","outputLevelTrueText":"Warning"},"aiWorkMode":0,"detectThreadholds":0.69999999999999996,"determineStrategy":0,"doOperatorWhen":{"whenFalse":false,"whenTrue":false},"doRecordVideoWhen":{"whenFalse":false,"whenTrue":false},"doReportWhen":{"whenFalse":false,"whenTrue":false},"doSnapWhen":{"whenFalse":false,"whenTrue":false},"estimateB..............}(未全部显示)
</details>

|major | minor |备注 |
|:-:|:-:|:-:|
|1|45|查询所有模板|
<details>
<summary>示例</summary>
<summary>发送</summary>

{
    "major": 1,
    "minor": 45
}
<summary>接收</summary>
{
  "major": 2,
  "minor": 45,
  "value": [
    "/appfs/camapp/www/matchingmodel/test/",//所有模板
    "/appfs/camapp/www/matchingmodel/test/modelconfig.json",
    "/appfs/camapp/www/matchingmodel/test/template.shm",
    "/appfs/camapp/www/matchingmodel/test/image.png"
  ]
}
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|46|删除一个模板|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
    "major": 1,
    "minor": 46,
    "value": "模板1"
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628DEDD4D",
  "major": 2,
  "minor": 80,
  "value": {
    "error": "delete matching model fail.",//错误提示
    "major": 1,
    "minor": 46,
    "success": false,
    "value": "模板1"
  }
}
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|57|查询系统状态|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
 "major": 1,
 "minor": 57,
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628E9DEBD",
  "major": 2,
  "minor": 57,
  "value": {
    "diskInfo": {//存储信息
      "emmc": {
        "availabSize": 169377792,
        "blockSize": 4096,
        "freeSize": 174743552,
        "totalSize": 260014080
      },
      "sdcard": {
        "availabSize": 108015529984,
        "blockSize": 4096,
        "freeSize": 114045259776,
        "totalSize": 117771988992
      }
    },
    "ramInfo": {//ran信息
      "MemoryBuffers": 51480,
      "MemoryCached": 95852,
      "MemoryFree": 654820,
      "MemoryLeft": 802152,
      "MemoryTotal": 980792
    },
    "temperature": 58//温度
  }
}

</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|60|取默认AI功能配置|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
    "major": 1,
    "minor": 60
}
<summary>接收</summary>
{
  "major": 2,
  "minor": 60,
  "value": {//ai默认配置
    "_ItemE": {
      "determineStrategy": [
        "Center",
        "BottomCenter",
        "AnyPix"
      ]
    },
    "aiLoopConfig": {
      "aiLoopActionTriggerMode": 0,
      "detectInterval": 80,
      "reportCount": 5
    },
    "aiModelFile": {
      "classKey": [],
      "falseClassName": [],
      "fileItems": [
        "/appfs/camapp/addition/objmodel/cycle.npubin",
        "/appfs/camapp/addition/objmodel/helmet.npubin"
      ],
      "fileKey": [],
      "filename": "",
      "trueClassName": []
    },
    "aiOutputBoolText": {
      "outputLevelFalseText": "DECT2",
      "outputLevelTrueText": "DECT1"
    },
    "aiWorkMode": 0,
    "detectThreadholds": 0.8,
    "determineStrategy": 0,
    "doOperatorWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "doRecordVideoWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "doReportWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "doSnapWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "estimateBase": 3,
    "estimateFuncName": "",
    "estimateReverse": false,
    "estimateThreshold": 0.1,
    "imageSaveLocation": 0,
    "name": "",
    "outputLevel": 0,
    "policy": {
      "name": "",
      "para": ""
    },
    "preChar4False": 68,
    "preChar4Group": 82,
    "preChar4True": 70,
    "reportFuncName": "",
    "resultQueueLen": 10,
    "rois": {
      "polygon": [],
      "rect": []
    },
    "version": 1
  }
}
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|61|ping||

<details>
<summary>示例</summary>
<summary>发送</summary>
{
  "major": 1,
  "minor": 61
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628D3FA6A",
  "major": 2
}
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|65|查询指定的异常检测模型配置文件内容|
<details>
<summary>示例</summary>
<summary>发送</summary>
{
    "major": 1,
    "minor": 65,
    "value": {
        "modelname": "test."
    }
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628D3FA6A",
  "major": 2,
  "minor": 80,
  "value": {//查询的配置内容
    "error": "Model path not exist.",
    "major": 1,
    "minor": 65,
    "success": false,
    "value": {
      "modelname": "test."
    }
  }
}
</details>

|major | minor | 备注 |
|:-:|:-:|:-:|
|1|66|取默认异常检测功能配置|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
    "major": 1,
    "minor": 66
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628D3FA6A",
  "major": 2,
  "minor": 66,
  "value": {//默认异常检测功能配置
    "aiLoopConfig": {
      "aiLoopActionTriggerMode": 0,
      "detectInterval": 80,
      "reportCount": 5
    },
    "aiModelCommonConfig": {
      "cuttingROI": {
        "polygon": [],
        "rect": []
      },
      "editTime": "",
      "imgSize": {
        "height": 5763224,
        "width": 127
      },
      "tLength": -405337392,
      "type": "",
      "version": ""
    },
    "aiModelName": "",
    "aiOutputBoolText": {
      "outputLevelFalseText": "Normal",
      "outputLevelTrueText": "Anomaly"
    },
    "aiWorkMode": 0,
    "detectThreadholdDefault": 0.5,
    "detectThreadholdMaxs": [],
    "detectThreadholds": [],
    "doOperatorWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "doRecordVideoWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "doReportWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "doSnapWhen": {
      "whenFalse": false,
      "whenTrue": false
    },
    "estimateBase": 1,
    "estimateFuncName": "",
    "estimateReverse": false,
    "estimateThreshold": 0.5,
    "externNPU": true,
    "imageSaveLocation": 0,
    "modelList": [],
    "name": "AnomDectConfigDefault",
    "outputLevel": 0,
    "policy": {
      "name": "",
      "para": ""
    },
    "preChar4False": 78,
    "preChar4Group": 82,
    "preChar4True": 65,
    "reportFuncName": "",
    "resultQueueLen": 10,
    "userRois": {
      "polygon": [],
      "rect": []
    },
    "version": 1
  }
}
</details>

|major | minor| 备注 |
|:-:|:-:|:-:|
|1|95|设置RTSP预览参数|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
    "major": 1,
    "minor": 95,
    "value": {
        "defaultTip": "是否启用RTSP预览,RTSP地址:rtsp://相机IP:8554/live",
        "default": false,
        "bitrateTip": "RTSP码率,单位bps",
        "bitrate": 17000
    }
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "001628D3FA6A",
  "major": 2,
  "minor": 80,
  "value": {
    "error": "设置rtsp预览成功.",
    "major": 1,
    "minor": 95,
    "success": true,
    "value": {
      "bitrate": 17000,
      "bitrateTip": "RTSP码率,单位bps",
      "default": false,
      "defaultTip": "是否启用RTSP预览,RTSP地址:rtsp://相机IP:8554/live"
    }
  }
}
</details>

|major | minor| 备注 |
|:-:|:-:|:-:|
|1|107|设置eth 通信配置|

<details>
<summary>示例</summary>
<summary>发送</summary>
{
    'major': 1,
    'minor': 107,
    'value': {
      'eth':[
  {
   "enable" : false,
   "type" : "TCPIP_SERVER",
   "value" :
   {
    "port" : 6000
   }
  },
  {
   "enable" : false,
   "type" : "TCPIP_CLIENT",
   "value" :
   {
    "ip" : "",
    "port" : 0
   }
  },
  {
   "enable" : false,
   "type" : "MODBUS_TCP_SERVER",
   "value" :
   {
    "readAddress" : 32,
    "readByteLen" : 200,
    "serverPort" : 502,
    "slaveId" : 255,
    "writeAddress" : 0,
    "writeByteMaxLen" : 64
   }
  },
  {
   "enable" : false,
   "type" : "MODBUS_TCP_CLIENT",
   "value" :
   {
    "readAddress" : 32,
    "readByteLen" : 200,
    "serverIp" : "",
    "serverPort" : 502,
    "slaveId" : 1,
    "writeAddress" : 0,
    "writeByteMaxLen" : 64
   }
  }]
    }
}
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "0016288D07CD",
  "major": 2,
  "minor": 80,
  "value": {
    "major": 1,
    "minor": 107,
    "success": true,
    "value": {
      "eth": [
        {
          "enable": false,
          "type": "TCPIP_SERVER",
          "value": {
            "port": 6000
          }
        },
        {
          "enable": false,
          "type": "TCPIP_CLIENT",
          "value": {
            "ip": "",
            "port": 0
          }
        },
        {
          "enable": false,
          "type": "MODBUS_TCP_SERVER",
          "value": {
            "readAddress": 32,
            "readByteLen": 200,
            "serverPort": 502,
            "slaveId": 255,
            "writeAddress": 0,
            "writeByteMaxLen": 64
          }
        },
        {
          "enable": false,
          "type": "MODBUS_TCP_CLIENT",
          "value": {
            "readAddress": 32,
            "readByteLen": 200,
            "serverIp": "",
            "serverPort": 502,
            "slaveId": 1,
            "writeAddress": 0,
            "writeByteMaxLen": 64
          }
        }
      ]
    }
  }
}
</details>

|major | minor| 备注 |
|:-:|:-:|:-:|
|2|94|相机上报检测结果|
<details>
<summary>示例</summary>
<summary>接收</summary>
{
    "from": "camera001", //相机名称
    "mac": "0016288D07CD", //相机mac地址
    "major": 2, //2为相机向外发送的消息
    "minor": 94, //94表示为相机检测结果消息
    "value": {
        "isDetect": false, //检测目标是否在roi种
        "object": [{
            "classId": 2, //检测到的目标类别
            "classType": 1, //检测到的目标是否为真类
            "rect": { //检测到的目标在哪个矩阵中
                "_centerX": 0.50052599906921391,
                "_centerY": 0.55987021923065194,
                "_group": 0,
                "_height": 0.54222207069396977,
                "_rotate": 0,
                "_width": 0.23108673095703125
            }
        }],
        "roi": { //roi检测框的信息，方案中画出的
            "polygon": null,
            "rect": null
        }
    }
}
</details>

|major | minor| 备注 |
|:-:|:-:|:-:|
|2|15|心跳包|
<details>
<summary>示例</summary>
<summary>接收</summary>
{
  "from": "camera001",
  "mac": "0016288D07CD",
  "major": 2,
  "minor": 15,
  "running": true,//是否运行
  "timestamp": 1704361856412//时间戳
}
</details>
