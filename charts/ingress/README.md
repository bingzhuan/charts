# 说明

- 该charts支持在一个Project中布置多套ingress；
- 同时，charts也支持通过填写节点标签调度到指定节点；
- 另外，在创建ingress规则时，通过ingress.class指定ingress配置推送至哪个（套）ingress上；

# 步骤

- 给节点打上标签，建议：`ingress=true`，`app=xxx`
- 由于后续是多套部署，所以创建时选择`创建新的命名空间`，输入命名空间名称；
- 填写nodeaffinity参数
	- key1：ingress，values：true  //默认已输入，节点标签与此保持一致
	- key2：app，values：xxx       //与检点标签保持一致
- 填写ingress class，建议与xxx保持一致，尽量输入字符能代表一个应用