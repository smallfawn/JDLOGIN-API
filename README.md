# JDLOGIN-API 京东账密协议版本 DOCKER部署 
购买地址 http://smshop.back1.idcfengye.com/

体验地址 http://smjd.back1.idcfengye.com/

# /api/set?username=用户名
{
    "status": "success",
    "msg": "初始化成功"
}
初始化成功
{
    "status": "risktime",
    "data": 时间戳13位
}
每日风控超2次 禁止提交
# /api/get?username=用户名&remark=备注&password=密码
{
    "status": "success",
    "msg": "登录成功",
    "data": "pt_pin=jd_abcd;"
}
{
    "status": "wait",
    "msg": "正在登录中",
    "data": "手机号"
}
{
    "status": "risk",
    "msg": "触发风控",
    "data": "url" //风控需要自己过一下滑块 这里返回链接
}
{
    "status": "risktime",
    "msg":"登录风控今日上限,请于明日再来登录",
    "data": 时间戳13位
}
{
    "status": "fail",
    "msg":"账号或密码错误",
    "data": "https://m.jd.com" //自己现在官网登录一下
}
{
    "status": "error",
    "msg":"未知错误",
    "data": "" 
}
# 当SET请求为success时 轮询请求get请求(最多15s )如果remark传参为空 则默认备注为ptpin的值
