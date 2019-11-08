# 说明

- 该charts支持在一个Project中布置多套ingress；
- 同时，charts也支持通过填写节点标签调度到指定节点；
- 另外，在创建ingress规则时，通过ingress.class指定ingress配置推送至哪个（套）ingress上；

# 步骤

- 给节点打上两个标签
	- 第一个必须是：`ingress=true`；
	- 第二个建议是：`app=xxx`，尽量输入字符能代表一个应用；
- 由于后续是多套部署，所以创建时选择`创建新的命名空间`，输入命名空间名称；
- 填写nodeaffinity参数
	- NodeAffinity Key：app（与节点标签保持一致）
	- NodeAffinity Values：xxx（与节点标签保持一致）
- 填写ingress class，建议与xxx保持一致，尽量输入字符能代表一个应用；