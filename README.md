### 系统介绍

基于Vue和NodeJS实现的校园信息交流网站采用前后端分离的架构方式，前台系统实现了用户注册/登录、首页、问答、活动、招聘信息、二手信息、文章/新闻等功能模块，后台系统实现了登录、数据中心、个人中心、审核中心、用户管理、网站管理中心、反馈中心等功能模块。

### 技术选型

开发工具：webstorm2020.3

运行环境：mysql5.7+nodejs16.0.0

服务端技术：express+fastjson+nodemon

前端技术：html+css+vue+axios+element-ui

### 成果展示

前台系统->首页
![前台系统-首页](https://github.com/user-attachments/assets/c370f94e-bfce-4785-9917-3f11aa8d35ca)

前台系统->问答
<img width="1879" height="894" alt="前台系统-问答" src="https://github.com/user-attachments/assets/c7f43e73-179a-4215-8c00-4d2c3cf2e719" />

前台系统->活动
<img width="1877" height="711" alt="前台系统-活动" src="https://github.com/user-attachments/assets/2b0ac6ea-5041-4987-9fd1-6354fe2ff4f7" />

前台系统->招聘信息
<img width="1872" height="806" alt="前台系统-招聘信息" src="https://github.com/user-attachments/assets/29a3c8f3-cf88-476b-bbc4-c53c33077bc5" />

前台系统->二手信息
<img width="1876" height="1004" alt="前台系统-二手信息" src="https://github.com/user-attachments/assets/64672626-e127-41e1-9878-d8dc3061bb7d" />

前台系统->文章/新闻
<img width="1876" height="860" alt="前台系统-文章新闻" src="https://github.com/user-attachments/assets/a2a341d8-37f8-4c1c-bfb4-97538dc3e055" />

前台系统->个人中心
<img width="1879" height="1031" alt="前台系统-个人中心" src="https://github.com/user-attachments/assets/1e49e88a-d309-4981-9645-719abf235c18" />

后台系统->数据中心
<img width="1901" height="1026" alt="后台系统-数据中心" src="https://github.com/user-attachments/assets/bb84c4bb-7b50-4aa6-b389-1b024ce6924e" />

后台系统->个人中心
<img width="1900" height="1029" alt="后台系统-个人中心" src="https://github.com/user-attachments/assets/1ee62c7b-2178-4ff3-9ceb-c6f55991b5e3" />

后台系统->审核中心
<img width="1901" height="1032" alt="后台系统-审核中心" src="https://github.com/user-attachments/assets/f014b7a3-8b09-402f-aca1-00543d993b9e" />

后台系统->用户管理
<img width="1901" height="1032" alt="后台系统-用户管理" src="https://github.com/user-attachments/assets/6d65000b-161e-40c3-a8ec-af65d4aa36c7" />

后台系统->网站管理中心
<img width="1882" height="935" alt="后台系统-网站管理中心" src="https://github.com/user-attachments/assets/e7430165-fe63-4c91-b28c-56a31decb90a" />

后台系统->反馈中心
<img width="1902" height="1029" alt="后台系统-反馈中心" src="https://github.com/user-attachments/assets/ce7a7c26-056f-4bdf-bad8-6b965f796a4d" />

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

<img width="983" height="165" alt="目录结构展示" src="https://github.com/user-attachments/assets/18e8e5ee-8b12-4757-a3b2-90cbf88fcc65" />

4、项目结构展示

<img width="1751" height="850" alt="项目结构" src="https://github.com/user-attachments/assets/75a7c115-b9fd-4c31-b43b-4da8903a47cd" />

5、运行步骤

1）创建数据库、导入sql脚本

2）修改DataBase.ini.js中的数据库配置文件，启动服务端

3）分别在web和admin目录下打开cmd，执行npm install下载依赖

4）下载完毕后启动前端npm run serve，访问端口

### 获取方式(可远程调试)

访问链接(在浏览器中手动输入下图中的地址)：

<img width="1115" height="126" alt="链接" src="https://github.com/user-attachments/assets/f888cc09-3a7a-4c58-8443-b330e5127acb" />

若资源获取失败，可添加happy35596339(vx)或1204901965(qq)进行交流
