# YunMake-Dev-Interview

## 介绍
为了测试你的编码能力以及了解你的编码习惯，我们希望你在你擅长的平台完成一个简单的 To-do 项目，平台包括但不局限于：Web, iOS, Android。

## 步骤
1. 前往 [http://interview.yunzao.cn/token](http://interview.yunzao.cn/token) 输入邮箱获取 `token`
2. 根据 [API](#api-list) 开发项目
3. 项目完成后请将项目打包或 GitHub 地址发送邮件至： [shendonghua@yunzao.cn](mailto:shendonghua@yunzao.cn?subject="YunMake-Dev-Interview") 

## 说明
1. 请尽量保持界面美观友好
2. 不限制使用任何第三方库
3. 请创建一个 Readme 文件，需包含项目介绍，所属平台，使用的技术，使用方法，最好可以介绍一下你的项目亮点
4. 你有5个工作日来完成该项目（自收到邮件开始计时）
5. 如有问题请发送邮件至：[shendonghua@yunzao.cn](mailto:shendonghua@yunzao.cn?subject="YunMake-Dev-Interview 问题")
6. Have fun!

## API 说明
1. API 请求的 Base URL 为 `http://interview.yunzao.cn/api/100/`
2. 如无特殊说明，所有请求都使用 `POST`，数据格式为 `JSON`
3. 所有请求都需包含 `token`
4. 所有请求，只有返回结果中 `code` 为 `0` 时，表示请求成功，其余均表示请求失败，错误信息请参考： [错误信息说明](#error_detail)

## <a name="api-list">API 列表</a>
1. [获取所有事项列表](#list)
2. [新建事项](#create_item)
3. [修改事项](#update_item)
4. [删除事项](#delete_item)
5. [完成事项](#finish_item)
6. [撤销完成事项](#revert_item)

## API 详细说明
### <a name="list">1. 获取所有事项列表</a>

**Request:** `/item/list`

```
{
	token: "token" 				// String
}
```

**Response:**

```
{
	code: 0, 						// Number
	data: [
		{
			id: 1, 					// Number
			user_id: 1,			// Number
			title: "title", 		// String
			content: "content",	// String
			status: 0, 			// Enum: 0(default), 1(finished)
			create_time: 0, 		// Timestamp
			update_time: 0 		// Timestamp
		},
		...
	]
}
```

### <a name="create_item">2. 新建事项</a>

**Request:** `/item/create`

```
{
	token: "token", 				// String
	title: "title", 				// String
	content: "content"			// String
}
```

**Response:** 

```
{
	code: 0, 						// Number
	data: {
		id: 1 						// Number
	{
}
```

### <a name="update_item">3. 修改事项</a>

**Request:** `/item/update`

```
{
	token: "token", 				// String
	id: 1, 							// Number
	title: "title", 				// String
	content: "content"			// String
}
```

**Response:**

```
{
	code: 0, 						// Number
	data: {
		id: 1 						// Number
	}
}
```

### <a name="delete_item">4. 删除事项</a>

**Request:** `/item/delete`

```
{
	token: "token",				// String
	id: 1 							// Number
}
```

**Response:**

```
{
	code: 0, 						// Number
	data: {
		id: 1 						// Number
	}
}
```

### <a name="finish_item">5. 完成事项</a>

**Request:** `/item/finish`

```
{
	token: "token",				// String
	id: 1							// Number
}
```

**Response:**

```
{
	code: 0,						// Number
	data: {
		id: 1						// Number
	}
}
```

### <a name="revert_item">6. 撤销完成事项</a>

**Request:** `/item/revert`

```
{
	token: "token",				// String
	id: 1							// Number
}
```

**Response:**

```
{
	code: 0,						// Number
	data: {
		id: 1						// Number
	}
}
```

## <a name="error_detail">错误信息说明</a>

**Response code:**

```
-1: invalid request
 1: param not set
 2: invalid token
 3: wrong type of param
 4: wrong name of param
 5: wrong password
 6: wrong param
 7: saving error
 8: record doesn't exist
 9: record exists
10: request not allowed
11: invalid verify code
```