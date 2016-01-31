# YunMake-Dev-Interview

## 介绍
在你擅长的平台完成一个 Todo List 项目，平台包括但不局限于：Web, iOS, Android。

## 步骤
1. 前往 [https://interview.zhixingche.com/token](https://interview.zhixingche.com/token) 输入邮箱获取 `token`
2. 根据 [API](#api-list) 开发项目
3. 项目完成后请将项目打包发送邮件至： [shendonghua@yunzao.cn](mailto:shendonghua@yunzao.cn?subject="YunMake-Dev-Interview")

## 说明
1. 请尽量保持界面美观友好
2. 不限制使用第三方库
3. 请创建一个 Readme 文件，需包含项目介绍，所属平台，使用的技术，使用方法，最好可以介绍一下你的项目亮点
4. 如有问题请发送邮件至：[shendonghua@yunzao.cn](mailto:shendonghua@yunzao.cn?subject="YunMake-Dev-Interview 问题")

## API 说明
1. 如无特殊说明，所有请求都使用 `POST`，数据格式为 `JSON`
2. 所有请求都需包含 `token`
3. 所有请求，只有返回结果中 `code` 为 `0` 时，表示请求成功，其余均表示请求失败，错误信息请参考： [错误信息说明](#error_detail)

## <a name="api-list">API 列表</a>
1. [获取所有事项列表](#list)
2. [新建事项](#create_item)
3. [修改事项](#update_item)
4. [删除事项](#delete_item)
5. [完成事项](#finish_item)
6. [撤销完成事项](#revert_item)

## API 详细信息
### <a name="list">1. 获取所有事项列表</a>

**Request**: `/list`

```
{
	token: xxx // String
}
```

**Response**:

```
{
	code: 0, // Number
	data: [
		{
			id: 1, // Number
			title: xxx, // String
			content: xxx, // String
			status: xxx, // Enum: -1(deleted), 0(default), 1(finished)
			created: xxx, // Timestamp
			updated: xxx, // Timestamp
			...
		}
	]
}
```

### <a name="create_item">2. 新建事项</a>

**Request**: `/item/create`

```
{
	token: xxx, // String
	title: xxx, // String
	content: xxx // String
}
```

**Response**: 

```
{
	code: 0, // Number
	data: {
		id: 1 // Number
	{
}
```

### <a name="update_item">3. 修改事项</a>

**Request**: `/item/update`

```
{
	token: xxx, // String
	id: 1, // Number
	title: xxx, // String
	content: xxx // String
}
```

**Response**: 

```
{
	code: 0, // Number
	data: {
		id: 1 // Number
	}
}
```

### <a name="delete_item">4. 删除事项</a>

**Request**: `/item/delete`

```
{
	token: xxx, // String
	id: 1 // Number
}
```

**Response**: 

```
{
	code: 0, // Number
	data: {
		id: 1 // Number
	}
}
```

### <a name="finish_item">5. 完成事项</a>

**Request**: `/item/finish`

```
{
	token: xxx, // String
	id: 1 // Number
}
```

**Response**: 

```
{
	code: 0, // Number
	data: {
		id: 1	 // Number
	}
}
```

### <a name="revert_item">6. 撤销完成事项</a>

**Request**: `/item/revert`

```
{
	token: xxx, // String
	id: 1 // Number
}
```

**Response**: 

```
{
	code: 0, // Number
	data: {
		id: 1 // Number
	}
}
```

## <a name="error_detail">错误信息说明</a>


## Todo
1. [https://interview.zhixingche.com/token](https://interview.zhixingche.com/token) 获取 token 的 web 页面
2. API 开发
3. 整理错误信息