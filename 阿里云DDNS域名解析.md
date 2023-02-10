# 利用 Python 和阿里云 SDK 实现 DDNS 域名解析
## 安装阿里云 Python SDK
首先需要确保系统中已经安装了 Python 和 python-pip
## 原版 SDK（不推荐）
### 完成以下操作安装 Python SDK：
1. 安装 SDK 核心库
    + 如果您使用 Python 2.x，执行以下命令，安装阿里云 SDK 核心库：
        ```pip
        pip install aliyun-python-sdk-core
        ```
        依赖链接：https://pypi.org/project/aliyun-python-sdk-core
    + 如果您使用 Python 3.x，执行以下命令，安装阿里云 SDK 核心库：
        ```pip
        pip install aliyun-python-sdk-core-v3
        ```
        依赖链接：https://pypi.org/project/aliyun-python-sdk-core-v3
2. 云解析 DNS
    ```pip
    pip install aliyun-python-sdk-alidns
    ```
    依赖链接：https://pypi.org/project/aliyun-python-sdk-alidns
3. 域名
    ```pip
    pip install aliyun-python-sdk-domain
    ```
    依赖链接：https://pypi.org/project/aliyun-python-sdk-domain

+ 通过 install 升级程序
    ```pip
    pip install aliyun-python-sdk-core --upgrade
    ```
### 示例背景
以下代码详细介绍了 SDK 的使用步骤，仅作步骤示范。示例展示了如何调用 AddCustomLine API 进行添加自定义线路请求。
说明：您需要替换示例中的 region-id、your-access-key-id 和 your-access-key-secret 的值。
#### 完整代码示例
以下为本文示例的完整 Python SDK 代码。
```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-

from aliyunsdkcore.client import AcsClient
from aliyunsdkcore.acs_exception.exceptions import ClientException
from aliyunsdkcore.acs_exception.exceptions import ServerException
from aliyunsdkalidns.request.v20150109.AddCustomLineRequest import AddCustomLineRequest

# 实例化一个阿里云客户端，用于发起请求
# 实例化阿里云客户端时需要设置 AccessKey ID 和 AccessKey Secret
client = AcsClient('<your-access-key-id>', '<your-access-key-secret>', 'cn-hangzhou')

# 创建 API 请求并设置参数
request = AddCustomLineRequest()

# 设置用户语言
request.set_Lang("your_value")

# 设置域名名称
request.set_DomainName("your_value")

# 设置自定义线路名称
request.set_LineName("your_value")

# 发起请求，并得到响应
response = client.do_action_with_exception(request)

# 打印您需要的返回值
# python2: print(response) 
print(str(response, encoding='utf-8'))
```
备注：如果出现该报错：aliyunsdkcore.acs_exception.exceptions.ClientException: SDK.HttpError (‘Connection aborted.’, ConnectionResetError(104, ‘Connection reset by peer’))
安装另一个核心库即可，安装代码如下：
```pip
pip install aliyun-python-sdk-core
```
#### 步骤介绍
1. 实例化一个客户端，从 aliyunsdkcore 包中获取 AcsClient 类实例化对象 client。client 对象存放 ak、secret 和 region_id，region_id 如示例中的 cn-hangzhou。
    ```python
    from aliyunsdkcore.client import AcsClient

    client = AcsClient(
        ak="<your-access-key-id>",
        secret="<your-access-key-secret>",
        region_id='<region-id>'
    )
    ```
2. 创建对应 API 的 Request。类的命名规则为 API 方法名加上 Request。例如：
    ```python
    from aliyunsdkalidns.request.v20150109.AddCustomLineRequest import AddCustomLineRequest

    request = AddCustomLineRequest()
    ```
3. 设置请求类 request 的参数。通过 request 类的 set 方法设置必要的信息，即 API 中必须要提供的信息。例如：
    ```python
    # 该参数值为假设值，请您根据实际情况进行填写
    request.set_Lang("your_value")

    # 该参数值为假设值，请您根据实际情况进行填写
    request.set_DomainName("your_value")

    # 该参数值为假设值，请您根据实际情况进行填写
    request.set_LineName("your_value")
    ```
4. 通过 client 对象获得对应 request 响应 response
    ```python
    response = client.do_action_with_exception(request)
    print(response)
    ```
5. 使用 try...except... 处理服务器报错和客户端报错。
    + 服务端报错
        ```python
        try:
            ...
        except ServerException as e:
            print(e)
        ```
    + 客户端报错
        ```python
        try:
            ...
        except ClientException as e:
            print(e)
        ```

## 升级版 SDK（推荐）
### 环境要求
+ Python 3
+ 安装 SDK 核心库 OpenAPI ，使用 pip 安装包依赖:
    ```pip
    pip install alibabacloud_tea_openapi
    ```
+ 安装云解析 DNS
    ```pip
    pip install alibabacloud_alidns20150109==3.0.1
    ```
### 示例背景
以下代码详细介绍了升级版 SDK 的使用步骤，仅作步骤示范。示例展示了如何调用 AddCustomLine API 进行添加自定义线路请求。
说明： 您需要替换示例中的 access_key_id 和 access_key_secret 的值。
#### 完整代码示例
以下为本文示例的完整 Python SDK 代码。
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# This file is auto-generated, don't edit it. Thanks.

import sys

from typing import List

from alibabacloud_alidns20150109.client import Client as Alidns20150109Client
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_alidns20150109 import models as alidns_20150109_models
from alibabacloud_tea_util import models as util_models
from alibabacloud_tea_util.client import Client as UtilClient


class Sample:
    def __init__(self):
        pass

    @staticmethod
    def create_client(
        access_key_id: str,
        access_key_secret: str,
    ) -> Alidns20150109Client:
        """
        使用AK&SK初始化账号Client
        @param access_key_id:
        @param access_key_secret:
        @return: Client
        @throws Exception
        """
        config = open_api_models.Config(
            # 必填，您的 AccessKey ID，Access Key（AK）
            access_key_id=access_key_id,
            # 必填，您的 AccessKey Secret，Secret Access Key（SK）
            access_key_secret=access_key_secret
        )
        # 访问的域名
        config.endpoint = f'alidns.cn-hangzhou.aliyuncs.com'
        return Alidns20150109Client(config)

    @staticmethod
    def main(
        args: List[str],
    ) -> None:
        # 初始化 Client，采用 AK&SK 鉴权访问的方式，此方式可能会存在泄漏风险，建议使用 STS 方式。鉴权访问方式请参考：https://help.aliyun.com/document_detail/378659.html
        # 获取 AK 链接：https://usercenter.console.aliyun.com
        client = Sample.create_client('accessKeyId', 'accessKeySecret')
        add_custom_line_request = alidns_20150109_models.AddCustomLineRequest(
            # 用户语言，如："zh"、"en"
            lang='zh',
            # 域名名称，如："baidu.com"
            domain_name='baidu.com',
            # 自定义线路名称，如："杭州线路"
            line_name='cn-hangzhou'
        )
        runtime = util_models.RuntimeOptions()
        try:
            # 复制代码运行请自行打印 API 的返回值
            client.add_custom_line_with_options(add_custom_line_request, runtime)
        except Exception as error:
            # 如有需要，请打印 error
            UtilClient.assert_as_string(error.message)

    @staticmethod
    async def main_async(
        args: List[str],
    ) -> None:
        # 初始化 Client，采用 AK&SK 鉴权访问的方式，此方式可能会存在泄漏风险，建议使用 STS 方式。鉴权访问方式请参考：https://help.aliyun.com/document_detail/378659.html
        # 获取 AK 链接：https://usercenter.console.aliyun.com
        client = Sample.create_client('accessKeyId', 'accessKeySecret')
        add_custom_line_request = alidns_20150109_models.AddCustomLineRequest(
            lang='your_value',
            domain_name='your_value',
            line_name='your_value'
        )
        runtime = util_models.RuntimeOptions()
        try:
            # 复制代码运行请自行打印 API 的返回值
            await client.add_custom_line_with_options_async(add_custom_line_request, runtime)
        except Exception as error:
            # 如有需要，请打印 error
            UtilClient.assert_as_string(error.message)


if __name__ == '__main__':
    Sample.main(sys.argv[1:])
```
#### 步骤介绍
1. 初始化配置对象 alibabacloud_tea_openapi.Config。Config 对象存放存放 access_key_id 、access_key_secret 和 endpoint 等配置，Endpoint 如示例中的 alidns.cn-hangzhou.aliyuncs.com
    ```python
    from alibabacloud_tea_openapi import models as open_api_models

    config = open_api_models.Config(
        # 您的AccessKey ID,
        access_key_id=access_key_id,
        # 您的AccessKey Secret,
        access_key_secret=access_key_secret
    )
    # 访问的域名
    config.endpoint = 'alidns.cn-hangzhou.aliyuncs.com'
    ```
2. 实例化一个客户端，从 alibabacloud_alidns20150109.Client 类生成对象 client。后续 request、response 从 alibabacloud_alidns20150109.models 中获得
    ```python
    from alibabacloud_alidns20150109.client import Client as Client
    from alibabacloud_alidns20150109 import models as models

    client = Client(config)
    ```
3. 创建对应 API 的 Request。方法的命名规则为 Create 加上 API 方法名再加上 Request。例如：
    ```python
    request = models.CreateAddCustomLine()
    ```
4. 设置请求类 request 的参数。通过设置 request 类的属性设置参数，即 API 中必须要提供的信息。例如：
    ```python
    # 用户语言
    request.Lang = "your_value";

    # 域名名称
    request.DomainName = "your_value";

    # 自定义线路名称
    request.LineName = "your_value";
    ```
5. 通过 client 对象获得对应 request 响应 response
    ```python
    response = client.addCustomLine(request)
    print(response)
    ```
6. 调用 response 中对应的属性获得返回的参数值。假设您需要获取 requestId：
    ```python
    requestId = response.body.requestId
    print(requestId)
    ```
7. 使用 try...except... 处理报错
    ```python
    from Tea.exceptions import UnretryableException

    try:
        response = client.describe_images(request)
    except UnretryableException as e:
        # Server Error
        print(e.inner_exception.code)
        print(e.inner_exception.message)
    except Exception as e:
        print(e)
    ```
### 采用 AK&SK 鉴权访问的方式进行域名解析的完整代码
```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-

import sys
import socket

from typing import List
# from urllib.request import urlopen

from alibabacloud_alidns20150109.client import Client as AlidnsClient
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_alidns20150109 import models as alidns_models
from alibabacloud_tea_util import models as util_models


class UpdateDNS:
    def __init__(self):
        pass

    @staticmethod
    def create_client(access_key_id: str, access_key_secret: str,) -> AlidnsClient:
        """
        使用AK&SK初始化账号Client
        @param access_key_id:
        @param access_key_secret:
        @return: Client
        @throws Exception
        """
        config = open_api_models.Config(
            # 必填，您的 AccessKey ID,
            access_key_id=access_key_id,
            # 必填，您的 AccessKey Secret,
            access_key_secret=access_key_secret,
            # 通过 HTTPS 协议发送请求
            protocol='HTTPS'
        )
        # 访问的域名
        config.endpoint = f'alidns.cn-hangzhou.aliyuncs.com'
        return AlidnsClient(config)

    @staticmethod
    def main(args: List[str],) -> None:
        # 初始化 Client，采用 AK&SK 鉴权访问的方式，此方式可能会存在泄漏风险，建议使用 STS 方式
        client = UpdateDNS.create_client('accessKeyId', 'accessKeySecret')

        # 查询子域名解析记录
        describe_sub_domain_records_request = alidns_models.DescribeSubDomainRecordsRequest()
        # 子域名名称
        describe_sub_domain_records_request.sub_domain = 'www.huywell.cn'
        # 解析记录类型，类型 A 为 ipv4，类型 AAAA 为 ipv6
        describe_sub_domain_records_request.type = 'AAAA'
        # 初始化 RuntimeObject
        runtime = util_models.RuntimeOptions(ignore_ssl=True)
        # 调用查询 api
        response = client.describe_sub_domain_records_with_options(
            describe_sub_domain_records_request, runtime)
        # 查询到的总记录个数
        total_count = response.body.total_count

        # 获取到的当前 IP 地址
        ip_addr = UpdateDNS.get_ipv6()

        # 判断查询的子域名解析记录是否存在
        if total_count == 0:
            print('解析记录不存在，添加新记录', ip_addr)
            # 添加解析记录
            add_domain_record_request = alidns_models.AddDomainRecordRequest()
            # 添加域名名称
            add_domain_record_request.domain_name = 'huywell.cn'
            # 添加主机记录
            add_domain_record_request.rr = 'www'
            # 添加解析记录类型，类型 A 为 ipv4，类型 AAAA 为 ipv6
            add_domain_record_request.type = 'AAAA'
            # 记录值
            add_domain_record_request.value = ip_addr
            # 调用添加 api
            client.add_domain_record_with_options(
                add_domain_record_request, runtime)
        else:
            # 获取解析记录中已经存在记录的域名
            domain_name = response.body.domain_records.record[0]
            # 获取解析记录中已经存在记录的域名的值
            value = domain_name.value
            # 判断解析记录中的值与获取的当前 IP 地址是否相同
            if value != ip_addr:
                print('解析记录中存在', value, '，与当前获取的值不同，需要更新为：', ip_addr)
                # 更新解析记录
                update_domain_record_request = alidns_models.UpdateDomainRecordRequest()
                # 更新解析记录的 ID
                update_domain_record_request.record_id = domain_name.record_id
                # 更新主机记录
                update_domain_record_request.rr = 'www'
                # 更新解析记录类型，类型 A 为 ipv4，类型 AAAA 为 ipv6
                update_domain_record_request.type = 'AAAA'
                # 更新记录值
                update_domain_record_request.value = ip_addr
                # 调用更新 api
                client.update_domain_record_with_options(
                    update_domain_record_request, runtime)
            else:
                print('解析记录已存在，无需更新')

    # 获取外网 IP 地址
    @staticmethod
    # def get_ipv4():
    #     with urlopen('https://api.ipify.org') as response:
    #         html = response.read()
    #         ip = str(html, encoding='utf-8').replace("\n", "")
    #     return ip
    def get_ipv6():
        s = socket.socket(socket.AF_INET6, socket.SOCK_DGRAM)
        try:
            s.connect(('2400:3200::1', 80))
            ip = s.getsockname()[0]
        finally:
            s.close()
        return ip


if __name__ == '__main__':
    UpdateDNS.main(sys.argv[1:])
```

### 前言
阿里云官网：https://help.aliyun.com/document_detail/315438.html

阿里云新版 Python SDK 基于Python 3.6 以上的版本开发，是通过总结开发者在原版 Python SDK 中遇到的一系列问题后重新开发的一版 SDK。该版本 Python SDK 新增了许多特性，主要以易于用户理解，降低用户接入成本并提升 SDK 的健壮性为主。本文不仅会为大家详细介绍新版 Python SDK 与原版 Python SDK 相比所增加的新特性，也会通过介绍二者使用上的区别来为想从原版 Python SDK 升级到新版 Python SDK 的开发者提供升级指南。
#### 新版 Python SDK 的新特性
新版 Python SDK 是基于阿里云自研的 DSL 语言 Darabonba 生成，通过 DSL 的灵活性不仅可以进行更多的表达而且通过解析 DSL 生成的 AST 也能抹平阿里云不同产品生产的不同风格 OpenAPI 的差异轻松的实现 OpenAPI 到 SDK 的生成。通过 DSL 的方式并结合以往 Python SDK 中的问题，阿里云提供的新版 Python SDK 具备以下的特性：
1. 解决原版 SDK 中产品 OpenAPI 风格不同（RPC或ROA）造成使用方式不一致问题，新版 SDK 中所有云产品的 SDK 使用方式相同，使用体验一致。
2. 通过 DSL 使 SDK 具备逻辑表达能力，从而使新版 SDK 不用像原版 SDK 与 SDK Core（aliyun-python-sdk-core）耦合性高的问题，降低了开发者因为 SDK 的升级带来的开发成本。
3. 每个云产品的 SDK 提供一个 Client 对象，通过实例化 Client 对象就可以调用云产品的所有 API。通过这样钉的方式，不仅解决了原版 SDK 单 Client 容易造成线程安全问题，同时通过该方式使每个云产品之间身份和鉴权信息隔离从而解决了用户使用原版 SDK 造成的 profile 信息在不同产品之间混用造成的权限管理问题。用户也可以根据不同的云产品 OpenAPI 的情况配置不同的参数，例如服务区域、超时时间、HTTP 代理、重试配置等。
4. 新版 SDK 支持更复杂的 OpenAPI 使用场景，例如阿里云的人体人脸（FaceBody）等产品中需要上传图片到 OSS 以后，通过该链接对图片进行人工智能分析处理，就可以通过新版 SDK 组合上传鉴权、上传图片、图片分析三个操作从而实现对该 OpenAPI 使用的简化。
5. 新版 Python SDK 不仅为 SDK 中的所有的 OpenAPI 请求生成相应的示例，同时也通过对 SDK 中的多个 OpenAPI 请求进行组合从而提供 SDK 的场景化示例，这样的示例不仅可以帮助开发者降低接入 SDK 的成本，同时也可以帮助开发者更好的理解云产品的业务场景。
#### 新版SDK升级策略
```bash
# 新版
pip install alibabacloud-ecs20140526
# 原版
pip install aliyun-python-sdk-ecs
```
从示例中可以看出新版 SDK 的命名方式为 `alibabacloud_{产品名}{OpenAPI 版本号}` 的方式命名。开发者也可以通过 SDK 信息中心来查看具体产品的新版 SDK 或原版 SDK 的信息。
### 初始化 Client
#### 新版SDK 初始化
新版 SDK 中因为具备完整的参数处理、返回值处理以及请求逻辑，所以可以给不同云产品的 SDK 生成不同的 Client 并包含其产品下所有的 OpenAPI 请求方法，可以使不同云产品之间的身份及鉴权信息隔离，使用上更加安全，下面是新版 SDK 初始化的示例：
```python
from alibabacloud_tea_openapi import models
from alibabacloud_ecs20140526.client import Client


config = models.Config(
    # 您的AccessKey ID,
    access_key_id='<access_key_id>',
    # 您的AccessKey Secret,
    access_key_secret='<access_secret>',
    # 地域ID
    region_id='cn-hangzhou',
    # 凭证类型
    # type='access_key',
    # 访问的域名
    endpoint = 'ecs-cn-hangzhou.aliyuncs.com'
)

# 实例化一个 Client 对象
client = Client(config)
```
### 使用 SDK Credentials 包
使用 pip 安装（推荐），如未安装 pip，请先安装 pip。
```bash
# 安装 alibabacloud_credentials
pip install alibabacloud_credentials
```
#### 配置 AccessKey
通过用户信息管理设置 access_key，它们具有该账户完全的权限，请妥善保管。有时出于安全考虑，您不能把具有完全访问权限的主账户 AccessKey 交于一个项目的开发者使用，您可以创建RAM子账户并为子账户授权，使用 RAM 子用户的 AccessKey 来进行 API 调用。
```python
from alibabacloud_credentials.client import Client
from alibabacloud_credentials.models import Config

config = Config(
    type='access_key',                    # 凭证类型
    access_key_id='accessKeyId',          # AccessKeyId
    access_key_secret='accessKeySecret',  # AccessKeySecret
)
cred = Client(config)

access_key_id = cred.get_access_key_id()
access_key_secret = cred.get_access_key_secret()
cred_type = cred.get_type()
```
#### 配置 STS Token
通过安全令牌服务（Security Token Service，简称 STS），申请临时安全凭证（Temporary Security Credentials，简称 TSC），创建临时安全凭证。
安装 STS SDK 库
```bash
pip install alibabacloud-sts20150401
```
阿里云 STS（Security Token Service）是阿里云提供的一种临时访问权限管理服务。RAM 提供 RAM 用户和 RAM 角色两种身份。其中，RAM 角色不具备永久身份凭证，而只能通过 STS 获取可以自定义时效和访问权限的临时身份凭证，即安全令牌（STS Token）。
+ 使用 STS Token，减少长期访问密钥（Accesskey）泄露的风险。
+ STS Token具有时效性，可以自定义有效期，到期后将自动失效，无需定期轮换。
+ 可以为 STS Token 绑定自定义权限策略，提供更加灵活和精细的云资源授权。
```python
from alibabacloud_credentials.client import Client
from alibabacloud_credentials.models import Config

config = Config(
    type='sts',                           # 凭证类型
    access_key_id='accessKeyId',          # AccessKeyId
    access_key_secret='accessKeySecret',  # AccessKeySecret
    security_token='securityToken'        # STS Token
)
cred = Client(config)

access_key_id = cred.get_access_key_id()
access_key_secret = cred.get_access_key_secret()
security_token = cred.get_security_token()
cred_type = cred.get_type()
```
#### 配置 RamRoleArn
通过指定 RAM 角色，让凭证自动申请维护 STS Token。你可以通过为 Policy 赋值来限制获取到的 STS Token 的权限。
```python
from alibabacloud_credentials.client import Client
from alibabacloud_credentials.models import Config

config = Config(
    type='ram_role_arn',                  # 凭证类型
    access_key_id='accessKeyId',          # AccessKeyId
    access_key_secret='accessKeySecret',  # AccessKeySecret
    security_token='securityToken',       # STS Token
    role_arn='roleArn',                   # 格式为：acs:ram::userID:role/roleName
    role_session_name='roleSessionName',  # 角色会话名称
    policy='policy',                      # 可选, 限制 STS Token 的权限
    role_session_expiration=3600          # 可选, 限制 STS Token 的有效时间
)
cred = Client(config)

access_key_id = cred.get_access_key_id()
access_key_secret = cred.get_access_key_secret()
security_token = cred.get_security_token()
cred_type = cred.get_type()
```
#### Credentials 示例
```python
# -*- coding: utf-8 -*-
# This file is auto-generated, don't edit it. Thanks.
import sys

from typing import List
from Tea.core import TeaCore

from alibabacloud_ecs20140526.client import Client as Ecs20140526Client
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_ecs20140526 import models as ecs_20140526_models
from alibabacloud_credentials.client import Client
from alibabacloud_credentials.models import Config
from alibabacloud_tea_console.client import Client as ConsoleClient
from alibabacloud_tea_util.client import Client as UtilClient


class Sample:
    def __init__(self):
        pass

    @staticmethod
    def create_client(
    ) -> Ecs20140526Client:
        credConfig = Config(
            type='access_key',                    # 凭证类型
            access_key_id='accessKeyId',          # AccessKeyId
            access_key_secret='accessKeySecret',  # AccessKeySecret
        )
        cred = Client(credConfig)
        clientConfig = open_api_models.Config(
            # 您的AccessKey ID,
            credential=cred
        )
        # 访问的域名
        clientConfig.endpoint = 'ecs-cn-hangzhou.aliyuncs.com'
        return Ecs20140526Client(clientConfig)

    @staticmethod
    def main(
        args: List[str],
    ) -> None:
        client = Sample.create_client()
        describe_instances_request = ecs_20140526_models.DescribeInstancesRequest(
            region_id='cn-hangzhou'
        )
        response=client.describe_instances(describe_instances_request)
        ConsoleClient.log(UtilClient.to_jsonstring(TeaCore.to_map(response)))


if __name__ == '__main__':
    Sample.main(sys.argv[1:])
```
### 新版 SDK 超时机制
新版 SDK 将 Request 中的业务参数和这种运行时参数分开设置避免用户混淆，所以超时的设置新版 SDK 的超时机制为 RuntimeOption -> Config 设置 -> 默认，优先级依次降低；默认连接超时为5秒，读超时为10秒：
```python
from alibabacloud_tea_openapi.models import Config
from alibabacloud_tea_util.models import RuntimeOptions

config = Config(
    access_key_id='<ACCESS-KEY-ID>',
    access_key_secret='<ACCESS-KEY-SECRET>',
    region_id='cn-hangzhou',
    read_timeout=10000,  # 读超时时间 单位毫秒(ms)
    connect_timeout=5000  # 连接超时 单位毫秒(ms)
)

RuntimeOptions(
    read_timeout=10000,  # 读超时时间 单位毫秒(ms)
    connect_timeout=5000  # 连接超时 单位毫秒(ms)
)
```
### 新版本 SDK HTTPS 配置
新版 SDK 中可以通过在 Client 中设置 OpenAPI 的请求协议，Client 设置 -> 默认，优先级依次降低；忽略证书通过运行时参数设置，默认忽略证书报错：
```python
from alibabacloud_tea_openapi.models import Config
from alibabacloud_tea_util.models import RuntimeOptions

config = Config(
    access_key_id='<ACCESS-KEY-ID>',
    access_key_secret='<ACCESS-KEY-SECRET>',
    region_id='cn-hangzhou',
    protocol='HTTPS'  # 通过 HTTPS 协议发送请求
)

RuntimeOptions(
    ignore_ssl=True  # 忽略对 SSL 证书的验证
)
```
### 新版 SDK 代理配置
新版本 SDK 同样可以通过环境变量：
+ HTTP_PROXY 或者 http_proxy
+ HTTPS_PROXY 或者 https_proxy

支持代理或者通过 Config 在初始化 Client 阶段设置请求的代理可以设置，新版 SDK 还支持通过运行时参数配置当前请求的代理优先级：RuntimeOption -> Client > 环境变量：
```python
from alibabacloud_tea_openapi.models import Config
from alibabacloud_tea_util.models import RuntimeOptions

config = Config(
    access_key_id='<ACCESS-KEY-ID>',
    access_key_secret='<ACCESS-KEY-SECRET>',
    region_id='cn-hangzhou',
    http_proxy='http://127.0.0.1:9898',
    https_proxy='http://user:password@127.0.0.1:8989'
)

RuntimeOptions(
    http_proxy='http://127.0.0.1:9898',
    https_proxy='http://user:password@127.0.0.1:8989'
)
```
### 新版 SDK OpenAPI 请求
新版 SDK 中每个产品的 Client 包含了所有的 OpenAPI，所以可以指定 OpenAPI 请求方法来请求，其方法名对应 OpenAPI 首字母小写，一般有三个：
1. 可以不用传入运行参数的请求方法
    ```python
    from alibabacloud_ecs20140526.models import DescribeImagesRequest
    from alibabacloud_ecs20140526.client import Client
    from alibabacloud_tea_openapi.models import Config

    '''云服务器示例'''
    # 初始化Config
    config = Config(
        access_key_id='<ACCESS-KEY-ID>',
        access_key_secret='<ACCESS-KEY-SECRET>',
        region_id='cn-hangzhou'
    )
    client = Client(config)
    # 初始化Request
    request = DescribeImagesRequest(image_id='<image-id>')
    # 调用api
    response = client.describe_images(request)
    ```
2. 需要传入运行参数的请求方法
    ```python
    from alibabacloud_ecs20140526.models import DescribeImagesRequest
    from alibabacloud_ecs20140526.client import Client
    from alibabacloud_tea_openapi.models import Config
    from alibabacloud_tea_util.models import RuntimeOptions

    '''云服务器示例'''
    # 初始化Config
    config = Config(
        access_key_id='<ACCESS-KEY-ID>',
        access_key_secret='<ACCESS-KEY-SECRET>',
        region_id='cn-hangzhou'
    )
    client = Client(config)
    # 初始化Request
    request = DescribeImagesRequest(image_id='<image-id>')
    # 调用api
    response = client.describe_images_with_options(request, RuntimeOptions())
    ```
3. 需要进行文件上传的请求方法，该方法默认需要传入运行时参数，这种方法只有需要用到文件上传的 OpenAPI 才会具备
    ```python
    from alibabacloud_imagesearch20200212.client import Client
    from alibabacloud_imagesearch20200212.models import SearchImageByPicAdvanceRequest
    from alibabacloud_oss_util.models import RuntimeOptions
    from alibabacloud_tea_openapi.models import Config

    '''图像搜索示例'''

    with open('pic.jpg', 'rb') as f:
        # 初始化Request
        request = SearchImageByPicAdvanceRequest(
            instance_name='name',
            pic_content_object=f  # 文件流、BytesIO或者一个类文件对象
        )
        
        # 初始化Config
        config = Config(
            access_key_id='<your_accsee_key_id>',
            access_key_secret='<your_access_key_secret>',
            endpoint='<your_endpoint>',
            region_id='cn-shanghai',
            type='access_key'
        )
        
        # 初始化RuntimeObject
        runtime_option = RuntimeOptions()
        
        # 初始化Client
        client = Client(config)
        
        # 调用api
        response = client.search_image_by_pic_advance(request, runtime_option)
    ```
### 新版 SDK 重试机制
新版 SDK 对 OpenAPI 请求中遇到网络问题的情况会进行重试，对于业务报错则不会重试。在请求中通过运行时参数配置重试，优先级为 RuntimeOption -> 默认；默认不会进行重试，如果打开重试配置未配置重试次数，则默认最多重试3次：
```python
from alibabacloud_tea_util.models import RuntimeOptions

runtime = RuntimeOptions(
    autoretry=True,  # 是否开启重试 默认关闭
    max_attempts=3   # 重试次数 默认3次
)
```
### 新版 SDK 异常
新版 SDK 的将异常的种类进行了一定的细分，主要细分为以下几个 Exception：
1. ValidateException：该异常会在用户没有填写 OpenAPI 必填参数或是填写的参数类型不匹配的情况下抛出，可通过查看异常的 message 来定位错误信息。
2. UnretryableException：该异常主要是因为网络问题造成，一般是网络问题造成达到最大重试次数后抛出。
3. TeaException：在 SDK 的请求中主要以业务报错为主的异常，该异常的示例中提供了三个参数为用户排查问题提供帮助：
    code: OpenAPI 业务报错的错误码。
    message：OpenAPI 业务报错的错误信息，其中会包含本次请求的 RequestId。
    data：OpenAPI 报错后服务端返回的详细信息。
```python
from Tea.exceptions import UnretryableException, TeaRequest
from alibabacloud_ecs20140526.models import DescribeImagesRequest
from alibabacloud_ecs20140526.client import Client
from alibabacloud_tea_openapi.models import Config

'''云服务器示例'''
# 初始化Config
config = Config(
    access_key_id='<ACCESS-KEY-ID>',
    access_key_secret='<ACCESS-KEY-SECRET>',
    region_id='cn-hangzhou'
)
client = Client(config)
# 初始化Request
request = DescribeImagesRequest(image_id='<image-id>')
try:
    response = client.describe_images(request)
except UnretryableException as e:
    # 网络异常
    print(e)
except TeaException as e:
    # 业务异常
    print(e)
except Exception as e:
    # 其他异常
    print(e)
```
### 新版 SDK Endpoint
Endpoint 是请求接口服务的网络域名，如 ecs.cn-hangzhou.aliyuncs.com。
新版 SDK 在 Endpoint 寻址上简化了许多，只提供了最容易理解的两种方式，下面按优先级排列：
1. 用户自定义：用户可以通过在初始化时指定云产品 Client 实例的请求地址，产品的 Endpoint 可以通过 [OpenAPI 开发者门户]（https://next.api.aliyun.com/product/Ecs）的产品主页中查找
    ```python
    from alibabacloud_tea_openapi.models import Config
    from alibabacloud_tea_util.models import RuntimeOptions

    config = Config(
        access_key_id='<ACCESS-KEY-ID>',
        access_key_secret='<ACCESS-KEY-SECRET>',
        region_id='cn-hangzhou',
        endpoint='<endpoint>'  # endpoint
    )
    ```
2. Endpoint 拼接规则：在请求产品 SDK 具有 Endpoint 数据时，当前通过 RegionId 寻址的逻辑才会生效，否则会在实例化 Client 对象时抛出异常 TeaException ，其 message 为 `config.endpoint can not be empty`，必须使用用户自定义的方式指定 Endpoint。Endpoint 数据文件示例（[Ecs Endpoint Data]（https://github.com/aliyun/aliyun-openapi-python-sdk/blob/master/aliyun-python-sdk-ecs/aliyunsdkecs/endpoint.py） ），其中不具备的 Region 会通过拼接规则：`{产品 Id}.{RegionId}.aliyuncs.com` 来进行拼接。
    ```python
    from alibabacloud_tea_openapi.models import Config
    from alibabacloud_tea_util.models import RuntimeOptions

    config = Config(
        access_key_id='<ACCESS-KEY-ID>',
        access_key_secret='<ACCESS-KEY-SECRET>',
        region_id='cn-hangzhou',  # 通过 regionId 映射到 endpoint
    )
    ```
#### 文件上传 Endpoint
新版本 SDK 还为用户提供了文件上传的 Endpoint 配置，分为两个：
+ 鉴权服务 openplatform 的地址，可以在 VPC 环境配置 VPC 地址来请求上传文件的鉴权信息。
    ```python
    from alibabacloud_tea_openapi.models import Config
    from alibabacloud_tea_util.models import RuntimeOptions

    from alibabacloud_facebody20191230.models import DetectBodyCountAdvanceRequest
    from alibabacloud_facebody20191230.client import Client

    runtime = RuntimeOptions()
    config = Config(
        access_key_id='<ACCESS-KEY-ID>',
        access_key_secret='<ACCESS-KEY-SECRET>',
        region_id='cn-hangzhou',
        open_platform_endpoint='openplatform-vpc.cn-shanghai.aliyuncs.com'
    )

    client = Client(config)
    with open('test.txt', 'rb') as f:
        request = DetectBodyCountAdvanceRequest(image_urlobject=f)
        response = client.detect_body_count_advance(request, runtime)
    # response 包含服务端响应的 body 和 headers
    print(response.body)
    print(response.headers)
    ```
+ 上传文件的地址，可以在 VPC 或者内网环境配置内网的地址来上传文件。
    ```python
    from alibabacloud_tea_openapi.models import Config
    from alibabacloud_tea_util.models import RuntimeOptions

    from alibabacloud_facebody20191230.models import DetectBodyCountAdvanceRequest
    from alibabacloud_facebody20191230.client import Client

    runtime = RuntimeOptions()
    config = Config(
        access_key_id='<ACCESS-KEY-ID>',
        access_key_secret='<ACCESS-KEY-SECRET>',
        region_id='cn-hangzhou',
        open_platform_endpoint='openplatform-vpc.cn-shanghai.aliyuncs.com',
        endpoint_type='internal'  # 设置通过 OSS 内网地址上传文件
    )

    client = Client(config)
    with open('test.txt', 'rb') as f:
        request = DetectBodyCountAdvanceRequest(image_urlobject=f)
        response = client.detect_body_count_advance(request, runtime)
    # response 包含服务端响应的 body 和 headers
    print(response.body)
    print(response.headers)
    ```
### 新版 SDK 异步
新版SDK 支持异步请求 async def 定义异步方法通过await client.{方法名}_async() 调用 SDK 异步方法。
```python
import asyncio

from alibabacloud_ecs20140526.models import DescribeImagesRequest
from alibabacloud_ecs20140526.client import Client
from alibabacloud_tea_openapi.models import Config

'''云服务器示例'''

async def main():
    config = Config(
        access_key_id='<ACCESS-KEY-ID>',
        access_key_secret='<ACCESS-KEY-SECRET>',
        region_id='cn-hangzhou'
    )
    client = Client(config)
    request = DescribeImagesRequest(image_id='<image-id>')
    
    response = await client.describe_images_async(request)
    print(response)
    return response


loop = asyncio.get_event_loop()
loop.run_until_complete(main())
```

## 获取扮演角色的临时身份凭证（AssumeRole）
通过调用 AssumeRole 接口，获取一个扮演 RAM 角色的临时身份凭证（STS Token）
使用 pip 安装（推荐）
```bash
pip install alibabacloud_sts20150401
```
获取扮演角色的临时身份凭证有 2 个必填信息
+ RoleArn：要扮演的 RAM 角色 ARN。该角色是可信实体为阿里云账号类型的RAM角色。
    格式：
    ```
    acs:ram::<account_id>:role/<role_name> 。
    ```
+ RoleSessionName：角色会话名称。该参数为用户自定义参数。通常设置为调用该 API 的用户身份，例如：用户名。在操作审计日志中，即使是同一个 RAM 角色执行的操作，也可以根据不同的 RoleSessionName 来区分实际操作者，以实现用户级别的访问审计。长度为 2~64 个字符，可包含英文字母、数字、半角句号（.）、at（@）、短划线（-）和下划线（_）。

有 2 个非必填信息
+ DurationSecondsToken：Token 有效期。单位：秒。Token 有效期最小值为 900 秒，最大值为要扮演角色的MaxSessionDuration时间。默认值为 3600 秒。
    - MaxSessionDuration：RAM角色最大会话时间。取值范围：3600秒~43200秒。默认值：3600秒。取值为空时将采用默认值。
+ Policy：为 STS Token 额外添加的一个权限策略，进一步限制 STS Token 的权限。长度为 1~2048 个字符。
    具体如下：
    - 如果指定该权限策略，则 STS Token 最终的权限策略取 RAM 角色权限策略与该权限策略的交集。
    - 如果不指定该权限策略，则 STS Token 最终的权限策略取 RAM 角色的权限策略。
### 操作流程
1. 创建用于扮演 RAM 角色的 RAM 用户
2. 为 RAM 用户授予 AliyunSTSAssumeRoleAccess 权限（调用STS服务AssumeRole接口的权限）
3. 创建 RAM 角色
4. 为 RAM 角色授予 AliyunDNSFullAccess 的权限（管理云解析(DNS)的权限）
5. 使用 RAM 用户通过扮演 RAM 角色，获取并使用安全令牌（STS Token）访问云解析(DNS)服务
#### 创建 RAM 用户
1. 使用阿里云账号登录 RAM 控制台。
2. 在左侧导航栏，选择身份管理 > 用户。
3. 在用户页面，单击创建用户。
4. 在创建用户页面的用户账号信息区域，输入登录名称和显示名称。
    说明：单击添加用户，可一次性创建多个RAM用户。
5. 在访问方式区域，选择访问方式。
    + 控制台访问：设置控制台登录密码、重置密码策略和多因素认证策略。
        说明：自定义登录密码时，密码必须满足密码复杂度规则
    + OpenAPI 调用访问：自动为 RAM 用户生成访问密钥（AccessKey），支持通过 API 或其他开发工具访问阿里云。
        说明：为了保障账号安全，建议仅为 RAM 用户选择一种登录方式，避免 RAM 用户离开组织后仍可以通过访问密钥访问阿里云资源。
6. 单击确定。建议您访问方式选择 OpenAPI 调用访问方式。
    重要：单击确定后会弹出安全验证窗口，完成安全验证后，会自动生成该 RAM 用户的登录密码和 AccessKey 信息（AccessKey ID 和 AccessKey Secret）。请务必保存好登录密码和 AccessKey 信息，否则后续无法查询。
#### 创建 RAM 角色
说明 下述步骤6中，建议您将角色名称设置为voderole，本文后续描述都以角色名称voderole为例。
1. 使用阿里云账号登录 RAM 控制台。
2. 在左侧导航栏，选择身份管理 > 角色。
3. 在角色页面，单击创建角色。
4. 在创建角色面板，选择可信实体类型为阿里云账号，然后单击下一步。
5. 设置角色信息。
    + 输入角色名称。
    + 可选：输入备注。
    + 选择云账号。
        - 当前云账号：当您允许当前阿里云账号下的 RAM 用户扮演该 RAM 角色时，您可以选择当前云账号。
        - 其他云账号：当您允许其他阿里云账号下的 RAM 用户扮演该 RAM 角色时，您可以选择其他云账号，然后输入其他阿里云账号 ID。该项主要针对跨阿里云账号的资源授权访问场景。
            说明：您可以访问安全设置页面查看阿里云账号 ID。
6. 单击完成。
7. 单击关闭。
### 示例代码
通过运行下面的代码来生成临时身份凭证 Credentials（AccessKeyId、AccessKeySecret 和 SecurityToken）
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# This file is auto-generated, don't edit it. Thanks.
import sys

from typing import List

from alibabacloud_sts20150401.client import Client as Sts20150401Client
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_sts20150401 import models as sts_20150401_models
from alibabacloud_tea_util import models as util_models
from alibabacloud_tea_util.client import Client as UtilClient


class Sample:
    def __init__(self):
        pass

    @staticmethod
    def create_client(
        access_key_id: str,
        access_key_secret: str,
    ) -> Sts20150401Client:
        """
        使用AK&SK初始化账号Client
        @param access_key_id:
        @param access_key_secret:
        @return: Client
        @throws Exception
        """
        config = open_api_models.Config(
            # 必填，您的 AccessKey ID,
            access_key_id=access_key_id,
            # 必填，您的 AccessKey Secret,
            access_key_secret=access_key_secret
        )
        # 访问的域名
        config.endpoint = f'sts.cn-hangzhou.aliyuncs.com'
        return Sts20150401Client(config)

    @staticmethod
    def main(
        args: List[str],
    ) -> None:
        # 工程代码泄露可能会导致AccessKey泄露，并威胁账号下所有资源的安全性。以下代码示例仅供参考，建议使用更安全的 STS 方式，更多鉴权访问方式请参见：https://help.aliyun.com/document_detail/378659.html
        client = Sample.create_client('accessKeyId', 'accessKeySecret')
        assume_role_request = sts_20150401_models.AssumeRoleRequest(
            # 要扮演的RAM角色ARN
            role_arn='RoleArn',
            # 角色会话名称
            role_session_name='RoleSessionName',
            # Token有效期
            duration_seconds=3600,
            # 为STS Token额外添加的一个权限策略，进一步限制STS Token的权限
            policy='Policy'
        )
        runtime = util_models.RuntimeOptions()
        try:
            # 复制代码运行请自行打印 API 的返回值
            response = client.assume_role_with_options(
                assume_role_request, runtime)
            print(response)
        except Exception as error:
            # 如有需要，请打印 error
            UtilClient.assert_as_string(error.message)

    @staticmethod
    async def main_async(
        args: List[str],
    ) -> None:
        # 工程代码泄露可能会导致AccessKey泄露，并威胁账号下所有资源的安全性。以下代码示例仅供参考，建议使用更安全的 STS 方式，更多鉴权访问方式请参见：https://help.aliyun.com/document_detail/378659.html
        client = Sample.create_client('accessKeyId', 'accessKeySecret')
        assume_role_request = sts_20150401_models.AssumeRoleRequest(
            # 要扮演的RAM角色ARN
            role_arn='RoleArn',
            # 角色会话名称
            role_session_name='RoleSessionName',
            # Token有效期
            duration_seconds=3600,
            # 为STS Token额外添加的一个权限策略，进一步限制STS Token的权限
            policy='Policy'
        )
        runtime = util_models.RuntimeOptions()
        try:
            # 复制代码运行请自行打印 API 的返回值
            await client.assume_role_with_options_async(assume_role_request, runtime)
        except Exception as error:
            # 如有需要，请打印 error
            UtilClient.assert_as_string(error.message)


if __name__ == '__main__':
    Sample.main(sys.argv[1:])
```
将生成的临时身份凭证信息填入解析代码的相关位置，即可使用临时身份凭证来解析域名
### 使用临时身份凭证进行域名解析的完整代码
```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-

import sys
import socket

from typing import List

from alibabacloud_alidns20150109.client import Client as AlidnsClient
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_alidns20150109 import models as alidns_models
from alibabacloud_credentials.client import Client
from alibabacloud_credentials.models import Config
from alibabacloud_tea_util import models as util_models


class UpdateDNS:
    def __init__(self):
        pass

    @staticmethod
    def create_client() -> AlidnsClient:
        credConfig = Config(
            # 凭证类型
            type='sts',
            # 必填，您的 AccessKey ID,
            access_key_id='accessKeyId',
            # 必填，您的 AccessKey Secret,
            access_key_secret='accessKeySecret',
            # 必填，您的 STS Token
            security_token='securityToken'
        )
        cred = Client(credConfig)
        clientConfig = open_api_models.Config(
            # 您的AccessKey ID
            credential=cred,
            # 通过 HTTPS 协议发送请求
            protocol='HTTPS'
        )
        # 访问的域名
        clientConfig.endpoint = f'alidns.cn-hangzhou.aliyuncs.com'
        return AlidnsClient(clientConfig)

    @staticmethod
    def main(args: List[str],) -> None:
        # 初始化 Client，这里使用 STS 方式
        client = UpdateDNS.create_client()

        # 查询子域名解析记录
        describe_sub_domain_records_request = alidns_models.DescribeSubDomainRecordsRequest()
        # 子域名名称
        describe_sub_domain_records_request.sub_domain = 'www.huywell.cn'
        # 解析记录类型，类型 A 为 ipv4，类型 AAAA 为 ipv6
        describe_sub_domain_records_request.type = 'AAAA'
        # 初始化 RuntimeObject
        runtime = util_models.RuntimeOptions(ignore_ssl=True)
        # 调用查询 api
        response = client.describe_sub_domain_records_with_options(
            describe_sub_domain_records_request, runtime)
        # 查询到的总记录个数
        total_count = response.body.total_count

        # 获取到的当前 IP 地址
        ip_addr = UpdateDNS.get_ipv6()

        # 判断查询的子域名解析记录是否存在
        if total_count == 0:
            print('解析记录不存在，添加新记录', ip_addr)
            # 添加解析记录
            add_domain_record_request = alidns_models.AddDomainRecordRequest()
            # 添加域名名称
            add_domain_record_request.domain_name = 'huywell.cn'
            # 添加主机记录
            add_domain_record_request.rr = 'www'
            # 添加解析记录类型，类型 A 为 ipv4，类型 AAAA 为 ipv6
            add_domain_record_request.type = 'AAAA'
            # 记录值
            add_domain_record_request.value = ip_addr
            # 调用添加 api
            client.add_domain_record_with_options(
                add_domain_record_request, runtime)
        else:
            # 获取解析记录中已经存在记录的域名
            domain_name = response.body.domain_records.record[0]
            # 获取解析记录中已经存在记录的域名的值
            value = domain_name.value
            # 判断解析记录中的值与获取的当前 IP 地址是否相同
            if value != ip_addr:
                print('解析记录中存在', value, '，与当前获取的值不同，需要更新为：', ip_addr)
                # 更新解析记录
                update_domain_record_request = alidns_models.UpdateDomainRecordRequest()
                # 更新解析记录的 ID
                update_domain_record_request.record_id = domain_name.record_id
                # 更新主机记录
                update_domain_record_request.rr = 'www'
                # 更新解析记录类型，类型 A 为 ipv4，类型 AAAA 为 ipv6
                update_domain_record_request.type = 'AAAA'
                # 更新记录值
                update_domain_record_request.value = ip_addr
                # 调用更新 api
                client.update_domain_record_with_options(
                    update_domain_record_request, runtime)
            else:
                print('解析记录已存在，无需更新')

    # 获取 IPv6 地址
    @staticmethod
    def get_ipv6():
        s = socket.socket(socket.AF_INET6, socket.SOCK_DGRAM)
        try:
            s.connect(('2400:3200::1', 80))
            ip = s.getsockname()[0]
        finally:
            s.close()
        return ip


if __name__ == '__main__':
    UpdateDNS.main(sys.argv[1:])
```

## 获取 IP 地址的 API 接口网站
推荐使用 api.ipify.org，因为它没有次数和频率的限制
```python
api_list = [
    'https://api.ipify.org',
    'https://api4.ipify.org',
    'https://api6.ipify.org',
    'http://www.3322.org/dyndns/getip',
    'https://api-ipv4.ip.sb/ip',
    'https://api-ipv6.ip.sb/ip',
]
```
测试 IPv6
```
http://ip.mir6.com/
http://www.test-ipv6.com/
https://api.vore.top/api/IPdata
```

## 查询解析记录
查询解析记录有 1 个必填项
+ 子域名（sub_domain）

示例如下：
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import sys

from typing import List

from alibabacloud_alidns20150109.client import Client as AlidnsClient
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_alidns20150109 import models as alidns_models
from alibabacloud_tea_util import models as util_models


class UpdateDNS:
    def __init__(self):
        pass

    @staticmethod
    def create_client(access_key_id: str,access_key_secret: str,) -> AlidnsClient:
        config = open_api_models.Config(
            # 必填，您的 AccessKey ID,
            access_key_id=access_key_id,
            # 必填，您的 AccessKey Secret,
            access_key_secret=access_key_secret
        )
        # 访问的域名
        config.endpoint = f'alidns.cn-hangzhou.aliyuncs.com'
        return AlidnsClient(config)

    @staticmethod
    def main(args: List[str],) -> None:
        client = UpdateDNS.create_client('accessKeyId', 'accessKeySecret')
        # 查询子域名解析记录
        describe_sub_domain_records_request = alidns_models.DescribeSubDomainRecordsRequest()
        # 子域名名称
        describe_sub_domain_records_request.sub_domain = 'www.baidu.com'
        # 解析记录类型
        describe_sub_domain_records_request.type = 'A'
        # 发送请求进行查询并返回结果
        response = client.describe_sub_domain_records_with_options(
            describe_sub_domain_records_request, util_models.RuntimeOptions())
        # 查询到的总记录个数
        total_count = response.body.total_count
```
### 查询到的记录数
```python
response = client.describe_sub_domain_records_with_options(
            describe_sub_domain_records_request, util_models.RuntimeOptions())
# 查询到的总记录个数
total_count = response.body.total_count
```
TotalCount 为 0 表示不存在这个子域名的解析记录
TotalCount 为 1 表示存在这个子域名的解析记录
TotalCount 大于 1 表示存在多个子域名的解析记录

## 添加解析记录
添加解析记录有 4 个必填项
+ 域名名称（domain_name）
+ 主机记录（rr）
    主机记录就是域名前缀，常见用法有：
    - www：解析后的域名为 www.aliyun.com。
    - @：直接解析主域名 aliyun.com。
    - *：泛解析，匹配其他所有域名 *.aliyun.com。
    - mail：将域名解析为 mail.aliyun.com，通常用于解析邮箱服务器。
    - 二级域名：如：abc.aliyun.com，填写 abc。
    - 手机网站：如：m.aliyun.com，填写 m。
    - 显性URL：不支持泛解析（泛解析：将所有子域名解析到同一地址）
+ 解析记录类型（type）
    类型名称|类型取值|类型定义|类型描述
    :-:|:-:|:-|:-:|
    A记录|A|参考标准；RR值可为空，即@解析；不允许含有下划线；|IPv4地址格式
    AAAA记录|AAAA|参考标准；RR值可为空，即@解析；不允许含有下划线；|IPv6地址格式
+ 记录值（value）

示例如下：
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import sys

from typing import List

from alibabacloud_alidns20150109.client import Client as AlidnsClient
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_alidns20150109 import models as alidns_models
from alibabacloud_tea_util import models as util_models


class UpdateDNS:
    def __init__(self):
        pass

    @staticmethod
    def create_client(access_key_id: str,access_key_secret: str,) -> AlidnsClient:
        config = open_api_models.Config(
            # 必填，您的 AccessKey ID,
            access_key_id=access_key_id,
            # 必填，您的 AccessKey Secret,
            access_key_secret=access_key_secret
        )
        # 访问的域名
        config.endpoint = f'alidns.cn-hangzhou.aliyuncs.com'
        return AlidnsClient(config)

    @staticmethod
    def main(args: List[str],) -> None:
        client = UpdateDNS.create_client('accessKeyId', 'accessKeySecret')
        # 添加解析记录
        add_domain_record_request = alidns_models.AddDomainRecordRequest()
        # 添加域名名称
        add_domain_record_request.domain_name = 'baidu.com'
        # 添加主机记录
        add_domain_record_request.rr = 'www'
        # 添加解析记录类型
        add_domain_record_request.type = 'A'
        # 记录值
        add_domain_record_request.value = UpdateDNS.get_internet_ip()
        # 发送请求进行添加
        client.add_domain_record_with_options(
            add_domain_record_request, util_models.RuntimeOptions())
    
    @staticmethod
    def get_internet_ip():
        with urlopen('http://www.3322.org/dyndns/getip') as response:
            html = response.read()
            ip = str(html, encoding='utf-8').replace("\n", "")
        return ip
```

## 更新解析记录
更新解析记录有 4 个必填项
+ 解析记录的 ID（record_id）
+ 主机记录（rr）
+ 解析记录类型（type）
+ 记录值（value）

示例如下：
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import sys

from typing import List

from alibabacloud_alidns20150109.client import Client as AlidnsClient
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_alidns20150109 import models as alidns_models
from alibabacloud_tea_util import models as util_models


class UpdateDNS:
    def __init__(self):
        pass

    @staticmethod
    def create_client(access_key_id: str,access_key_secret: str,) -> AlidnsClient:
        config = open_api_models.Config(
            # 必填，您的 AccessKey ID,
            access_key_id=access_key_id,
            # 必填，您的 AccessKey Secret,
            access_key_secret=access_key_secret
        )
        # 访问的域名
        config.endpoint = f'alidns.cn-hangzhou.aliyuncs.com'
        return AlidnsClient(config)

    @staticmethod
    def main(args: List[str],) -> None:
        client = UpdateDNS.create_client('accessKeyId', 'accessKeySecret')
        # 获取解析记录中已经存在记录的域名
        domain_name = response.body.domain_records.record[0]
        # 更新解析记录
        update_domain_record_request = alidns_models.UpdateDomainRecordRequest()
        # 更新解析记录的 ID
        update_domain_record_request.record_id = domain_name.record_id
        # 更新主机记录
        update_domain_record_request.rr = 'www'
        # 更新解析记录类型
        update_domain_record_request.type = 'A'
        # 更新记录值
        update_domain_record_request.value = UpdateDNS.get_internet_ip()
        # 发送请求进行更新
        client.update_domain_record_with_options(
            update_domain_record_request, util_models.RuntimeOptions())
    
    @staticmethod
    def get_internet_ip():
        with urlopen('http://www.3322.org/dyndns/getip') as response:
            html = response.read()
            ip = str(html, encoding='utf-8').replace("\n", "")
        return ip
```

## 删除解析记录
删除解析记录有 1 个必填项
+ 解析记录的 ID（record_id）

示例如下：
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-

import sys

from typing import List

from alibabacloud_alidns20150109.client import Client as AlidnsClient
from alibabacloud_tea_openapi import models as open_api_models
from alibabacloud_alidns20150109 import models as alidns_models
from alibabacloud_tea_util import models as util_models


class UpdateDNS:
    def __init__(self):
        pass

    @staticmethod
    def create_client(access_key_id: str,access_key_secret: str,) -> AlidnsClient:
        config = open_api_models.Config(
            # 必填，您的 AccessKey ID,
            access_key_id=access_key_id,
            # 必填，您的 AccessKey Secret,
            access_key_secret=access_key_secret
        )
        # 访问的域名
        config.endpoint = f'alidns.cn-hangzhou.aliyuncs.com'
        return AlidnsClient(config)

    @staticmethod
    def main(args: List[str],) -> None:
        client = UpdateDNS.create_client('accessKeyId', 'accessKeySecret')
        # 获取解析记录中已经存在记录的域名
        domain_name = response.body.domain_records.record[0]
        # 删除解析记录
        delete_domain_record_request = alidns_models.DeleteDomainRecordRequest()
        # 根据 record_id 删除解析记录
        delete_domain_record_request.record_id = domain_name.record_id
        # 发送删除请求
        client.delete_domain_record_with_options(
            delete_domain_record_request, util_models.RuntimeOptions())
```