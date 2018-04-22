# Order-Dinner-Iplements-BE

## 数据库
+ db: orderDinnerDB
  - collections: ids 

    `{createTimes:String, ids: String}`
  - collections: users

    `{uid:String,name:String,phone:String}`



## 配置
```js
{
  "env":{
    "port": "8000" //系统运行端口
  },
  "time":{
    "startTime":[8,15], // 接受订餐起始时间 [小时，分钟]
    "finshTime":[16,20], // 接受订餐结束时间
    "sendTime":[16,25], // 生成png-发送邮件的时间
    "cleanTime":[8,0] // 清除订餐列表时间
  },
  "db":{
    "url":"mongodb://localhost:27017/orderDinnerDB" //数据库连接配置
  },
  "mail":{
   "transporter":{
      "host": "xxx", //邮件服务器
      "port": 25, //邮箱端口
      "secure": false,  //邮箱私密协议
      "auth": {
        "user": "xxx", //发件账号
        "pass": "xxx" // 发件密码
      }
    },
    "mailOptions":{
      "from": "'xxx' xxx", //发件人 "Name <邮箱地址>"
      "to": "xxx", // 收件人
      "subject": "今日订餐人员名单", // 邮件标题
      "text": "今日订餐人员名单" // 邮件内容
    }
  }
}
```

## 环境
+ 数据库
  - MongoDB
  - 导入CSV

    `mongoimport --db orderDinnerDB --collection users --type csv  --ignoreBlanks --columnsHaveTypes --fields "uid.string(),name.string(),phone.string()" --file users.csv`

+ npm install
  - node-canvas 需要特别[安装运行环境](https://github.com/Automattic/node-canvas)

+ npm start

## 附件
- users.csv
