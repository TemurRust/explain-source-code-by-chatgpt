# File: pkg/controller/ttl/ttl_controller.go

pkg/controller/ttl/ttl_controller.go文件是Kubernetes中的TTL Controller，用于自动清理无用的Pod和Node对象。具体来说，TTL Controller会根据Pod或Node的TTL注释（Time-To-Live）来判断对象是否需要清理，并根据预设的时间间隔进行检查和清理。

ttlBoundaries是用于检查TTL注释的时间边界值，例如如果注释中的时间超过ttlBoundaries[0]（默认为6小时）则会被认为是无效注释。

Controller是TTL Controller的主要控制器，用于管理TTL Controller的状态和行为。ttlBoundary是用于管理Pod或Node的TTL注释的数据结构，其中包含注释的键和时间边界值。

NewTTLController用于初始化TTL Controller，包括设置队列和工人数量等。Run方法用于启动TTL Controller并处理队列中的项目。addNode，updateNode和deleteNode用于管理节点的添加、更新和删除操作。enqueueNode用于将节点添加到操作队列中。worker是实际执行清理操作的工作人员。

getDesiredTTLSeconds用于获取注释中的TTL时间（以秒为单位），setIntAnnotation用于设置注释键值对，patchNodeWithAnnotation用于更新节点上的注释。updateNodeIfNeeded用于检测节点的注释是否需要更新，并根据需要更新它们。processItem方法是实际执行清理操作的方法。

综上所述，pkg/controller/ttl/ttl_controller.go文件的作用是管理Pod和Node对象的TTL注释以及自动清理过期对象。TTL Controller使用ttlBoundaries数组来检查注释的有效性，Controller和ttlBoundary结构体用于控制Controller的状态和行为，NewTTLController，Run，addNode，updateNode，deleteNode，enqueueNode，worker和processItem等方法则用于实际管理和清理过期对象。

