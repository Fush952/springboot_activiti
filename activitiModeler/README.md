## 结合modeler编辑器运行方式

* 想办法初始化activiti需要的基础信息数据表，配置jdbc信息
* 通过act/model/create接口创建一个新的流程资源图，没有编辑的前提下全都是空的，需要到act_re_model表里面去查找ID
* 然后通过activi/modeler.html?modelId=**访问刚刚新建的流程图，目前的保存功能是完全可行的，/{modelId}/save接口

## 表单功能

#### 表单业务
* 开始+用户任务节点设置表单属性，通过FormService接口获取表单信息，展示给用户判断任务节点的附加信息
</br>例如：提交请假申请的信息需要附带一些信息：包括请假的开始时间+结束时间+请假理由等等信息，这些信息就可以通过activiti的表单功能设置以及展示相关信息


## Activiti启动流程涉及到的数据操作

 * 启动流程涉及到的数据表：act-ru-execution,act-ru-task,act-hi-identitylink
		
 * act-ru-execution插入一条数据表明当前流程的执行状态
		
 * act-ru-task插入一条当前流程任务执行实例
		 
 * act-hi-identitylink插入流程执行的用户信息