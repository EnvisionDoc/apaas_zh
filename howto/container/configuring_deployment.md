# 配置Deployment

本文章介绍应用开发人员如何配置发布应用的部署信息。

## 前提条件

在新建Deployment之前，需要完成应用创建和基本信息配置。详细步骤，参见[新建应用](../admin/managing_app#newapp)。

## 新建Deployment

应用的Deployment信息可以通过Config和Yaml配置两种方式进行配置。以Config配置方式为例，通过以下步骤为应用新建Deployment：

1. 在项目列表中，点击项目名称，进入项目空间。

2. 在左侧导航栏中，选择 **容器 > Deployments**。

3. 点击 **新建Deployment**，并完成对Deployment的详细配置。

4. 提供Deployment的基本信息：

   - **应用名称**：选择待部署的应用
   - **环境**：选择部署应用的环境，目前支持dev，alpha，beta，ppe，和prod环境
   - **集群**：选择部署应用的集群，目前集群已由系统预先配置
   - **副本数**：输入需要的副本数量

5. 配置应用运行所需的计算 **资源限额**，包括CPU和内存的限额。如下图所示：

   .. image:: ../../media/deployment_config.png

6. （选填）设置运行应用的 **环境变量** 和值。

7. （选填）选择需要注入容器的 **Config Map** 配置，并输入挂载目录。配置Config Map的详细信息，参见[配置Config Map](configuring_configmap_secret)。

8. （选填）设置 **日志采集文件** 的目录。

9. （选填）选择应用的 **存储配置**，并输入挂载目录。配置存储的详细信息，参见[配置Storage](configuring_storage)。

10. （建议填写）配置容器的 **就绪探针**，以检测容器是否就绪。就绪探针的配置信息包括检测任务的超时时间（秒）、探测周期（秒）、失败重试次数、探测延迟时间（秒）、以及探针的方式和参数。有关容器探针的详细介绍，参见[Pod 的生命周期](https://kubernetes.io/zh/docs/concepts/workloads/pods/pod-lifecycle)。

  .. image:: ../../media/probe.png

11. （选填）配置容器的 **存活探针**，配置信息与就绪探针类似。

12. 设置 **容器最小就绪时间**（秒）。

13. 输入对Deployment的描述信息。

14. 点击 **新建Deployment** 按钮，完成配置。

## 管理Deployment

应用Deployment信息创建完成后，可对Deployment进行克隆、编辑、删除、发布、和回滚等操作。

.. image:: ../../media/edit_deployment.png

- **克隆**：在已创建的Deployment列表中，选中Deployment名称，点击 **克隆** 按钮，即可复用Deployment配置信息，快速创建新的Deployment。

- **编辑**：选中Deployment名称，点击 **编辑** 按钮，即可更新Deployment配置信息。

- **删除**：选中Deployment名称，点击 **删除** 按钮并确认，即可删除Deployment配置信息。

- **发布**：选中Deployment名称，点击 **发布** 按钮并配置发布信息。

   - 在 **发布操作** 一栏中，选择Docker镜像后，点击 **开始** 按钮。

     .. image:: ../../media/publish_deployment.png

   - 查看Deployment发布结果和发布历史。

     .. image:: ../../media/publish_result.png

- **历史查询**：选中Deployment名称，点击 **历史查询** 按钮查看对该Deployment的历史操作。点击 **详情** 查看历史操作中Deployment的详细配置；点击 **回滚** 使当前Deployment的配置返回到选中的历史状态。

   .. image:: ../../media/rollback_deployment.png

<!--end-->