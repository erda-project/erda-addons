### 详细介绍
&emsp;&emsp;提供用户自定义环境变量配置功能，用户手动配置，通过平台的发布流程，将环境变量自动注入；并且提供了项目级别的共享，一次配置，即可应用在项目下所有应用中。

### 使用方式

**我的项目-->服务目录-->添加服务：**
![custom_create.png](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/06/29/90180e6c-c79a-4bab-b8a4-73521febbb8b.png) 
![custom_info.png](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/06/29/fba8119a-4cc8-4500-bb2d-2ac8dc4eeca7.png) 
&emsp;&emsp;名称需要自定义，后续配合平台的发布功能使用

**应用界面，选择代码仓库-->代码浏览-->dice.yml，右上角点击“编辑”，点击“+”号，选择上述创建的addon：**
![custom_attach.png](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/06/29/16bca660-9214-4ca7-b819-a45972a50c72.png) 
**或是点击“编辑”后，切换到代码模式，进行手动添加：**

在dice.yml中，addons标签下，进行如下配置，构建应用后，会自动发布：
```yaml
custom: #创建的时候，指定的名称:
  plan: custom:basic #此处固定
```