# JDLOGIN-API
# /api/set?username=用户名&password=密码
{
    "status": "success",
    "msg": "初始化成功"
}
初始化成功
{
    "status": "risktime",
    "data": 时间戳13位
}
每日风控超3次 禁止提交
# /api/get?username=用户名&remark=备注
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
# 当SET请求为success时 轮询请求get请求 如果remark传参为空 则默认备注为ptpin的值
