### 系统介绍

基于Vue和NodeJS实现的校园信息交流网站采用前后端分离的架构方式，前台系统实现了用户注册/登录、首页、问答、活动、招聘信息、二手信息、文章/新闻等功能模块，后台系统实现了登录、数据中心、个人中心、审核中心、用户管理、网站管理中心、反馈中心等功能模块。

### 技术选型

开发工具：webstorm2020.3

运行环境：mysql5.7+nodejs16.0.0

服务端技术：express+fastjson+nodemon

前端技术：html+css+vue+axios+element-ui

### 成果展示

前台系统->首页 输入图片说明

前台系统->问答 输入图片说明

前台系统->活动 输入图片说明

前台系统->招聘信息 输入图片说明

前台系统->二手信息 输入图片说明

前台系统->文章/新闻 输入图片说明

前台系统->个人中心 输入图片说明

后台系统->数据中心 输入图片说明

后台系统->个人中心 输入图片说明

后台系统->审核中心 输入图片说明

后台系统->用户管理 输入图片说明

后台系统->网站管理中心 输入图片说明

后台系统->反馈中心 输入图片说明

### 源码展示

//文章详情

exports.getarticlecontent = async (req, res) => {

let info = [req.body.id]

let sql = 'select * from article ,user where article.user_id =user.user_id and article_id=?'

const add = await query('update  article set article_read_num=article_read_num+1 where article_id = ?', info)

const result = await query(sql, info)

if (result.length == 0) {

    data = {
        state: e,
        data: {
        }
    }
    
} else {

    data = {
        state: s,
        data: result[0]
    }
    
}

console.log(result)

res.send(data);

}

//公司详情

exports.getcompanycontent = async (req, res) => {

let info = [req.body.id]

let sql = 'select * from job where  company_id=?'

const company = await query('select * from company where company_id=?', info)

const add = await query('update  company set company_read_num=company_read_num+1 where company_id = ?', info)

const joblist = await query(sql, info)

if (company.length == 0) {

    data = {
        state: e,
        data: {
        }
    }
    
} else {

    data = {
        state: s,
        data: {
            joblist: joblist,
            company: company[0]
        }
    }
    
}

res.send(data);

}

### 账号地址及其它说明

1、地址说明

前台系统：localhost:8080

后台系统：localhost:8081

2、账号说明

用户：wangwu/123456

管理员：admin/admin

3、目录结构展示

输入图片说明

4、项目结构展示

输入图片说明

5、运行步骤

1）创建数据库、导入sql脚本

2）修改DataBase.ini.js中的数据库配置文件，启动服务端

3）分别在web和admin目录下打开cmd，执行npm install下载依赖

4）下载完毕后启动前端npm run serve，访问端口

### 获取方式(可远程调试)

访问链接(在浏览器中手动输入下图中的地址)：

输入图片说明

若资源获取失败，可添加happy35596339(vx)或1204901965(qq)进行交流
