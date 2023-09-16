# File: istio/pilot/pkg/model/push_context.go

在istio/pilot/pkg/model/push_context.go文件中，定义了PushContext结构体和一些相关的变量、结构体和函数：

1. PushContext：表示推送环境的上下文，维护了推送所需的所有信息和状态。它具有以下方法：
   - `NewPushContext`：创建一个新的推送上下文。
   - `AddPublicServices`：向公共服务列表中添加服务。
   - `AddServiceInstances`：添加服务实例。
   - `StatusJSON`：以JSON格式返回推送上下文的状态。

2. 变量：
   - `_`：用于忽略未使用的变量。
   - `EndpointNoPod`：表示没有可用的Pod的终结点。
   - `ProxyStatusNoService`：表示代理没有关联的服务。
   - `ProxyStatusEndpointNotReady`：表示终结点尚未准备好。
   - `ProxyStatusConflictOutboundListenerTCPOverTCP`：表示出站TCP监听器冲突（TCP over TCP）。
   - `ProxyStatusConflictInboundListener`：表示入站监听器冲突。
   - `DuplicatedClusters`：表示重复的集群。
   - `DNSNoEndpointClusters`：表示没有终结点的DNS集群。
   - `ProxyStatusClusterNoInstances`：表示集群没有实例。
   - `DuplicatedDomains`：表示重复的域。
   - `DuplicatedSubsets`：表示重复的子集。
   - `totalVirtualServices`：虚拟服务的总数。
   - `LastPushStatus`：上次推送的状态。
   - `LastPushMutex`：上次推送的互斥锁。
   - `metrics`：用于跟踪推送过程的指标。
   - `wellknownProviders`：预定义的提供程序列表。
   - `meshGateways`：网格网关列表。

3. 结构体：
   - `ResourceDelta`：表示资源的变化。
   - `ReasonStats`：跟踪推送原因的统计信息。
   - `TriggerReason`：推送触发的原因。
   - `ProxyPushStatus`：代理推送的状态。
   - `gatewayWithInstances`：具有实例的网关。

4. 函数：
   - `newServiceIndex`：创建新的服务索引。
   - `newVirtualServiceIndex`：创建新的虚拟服务索引。
   - `newDestinationRuleIndex`：创建新的目标规则索引。
   - `newSidecarIndex`：创建新的Sidecar索引。
   - `newGatewayIndex`：创建新的网关索引。
   - `IsEmpty`：检查推送上下文是否为空。
   - `NewReasonStats`：创建新的推送原因统计信息。
   - `Add`：向推送原因统计信息中添加原因。
   - `Merge`：合并两个推送原因统计信息。
   - `CopyMerge`：复制并合并两个推送原因统计信息。
   - `Count`：统计推送原因的数量。
   - `Has`：检查推送原因是否存在。
   - `IsRequest`：检查资源是否是推送请求。
   - `IsProxyUpdate`：检查资源是否是代理更新。
   - `PushReason`：返回推送的原因。
   - `AddMetric`：向指标中添加一个值。
   - `AddPublicServices`：向公共服务列表中添加服务。
   - `AddServiceInstances`：添加服务实例。
   - `StatusJSON`：以JSON格式返回推送上下文的状态。
   - `OnConfigChange`：当配置发生更改时更新推送上下文。
   - `UpdateMetrics`：更新指标。
   - `virtualServiceDestinations`：返回虚拟服务的目标帧。
   - `GatewayServices`：为网关获取服务。
   - `ServicesAttachedToMesh`：获取附加到网格的服务。
   - `ServiceAttachedToGateway`：检查服务是否附加到网关。
   - `AssertProvidersHandled`：检查所有提供程序是否已处理。
   - `addHostsFromMeshConfig`：从网格配置中添加主机。
   - `servicesExportedToNamespace`：返回导出到命名空间的服务列表。
   - `GetAllServices`：获取所有服务。
   - `ServiceForHostname`：根据主机名获取服务。
   - `IsServiceVisible`：检查服务是否可见。
   - `VirtualServicesForGateway`：获取网关的虚拟服务。
   - `DelegateVirtualServices`：委托虚拟服务。
   - `getSidecarScope`：获取Sidecar的作用域。
   - `destinationRule`：获取目标规则。
   - `getExportedDestinationRuleFromNamespace`：从命名空间中获取导出的目标规则。
   - `IsClusterLocal`：检查集群是否是本地集群。
   - `InitContext`：初始化上下文。
   - `createNewContext`：创建新的上下文。
   - `updateContext`：更新上下文。
   - `initServiceRegistry`：初始化服务注册表。
   - `SortServicesByCreationTime`：按创建时间对服务进行排序。
   - `initServiceAccounts`：初始化服务账号。
   - `initAuthnPolicies`：初始化认证策略。
   - `initVirtualServices`：初始化虚拟服务。
   - `getGatewayNames`：获取网关名称。
   - `initDefaultExportMaps`：初始化默认导出映射。
   - `initSidecarScopes`：初始化Sidecar作用域。
   - `initDestinationRules`：初始化目标规则。
   - `newConsolidatedDestRules`：创建新的整合目标规则。
   - `SetDestinationRulesForTesting`：用于测试目的设置目标规则。
   - `setDestinationRules`：设置目标规则。
   - `initAuthorizationPolicies`：初始化授权策略。
   - `initTelemetry`：初始化遥测。
   - `initProxyConfigs`：初始化代理配置。
   - `initWasmPlugins`：初始化Wasm插件。
   - `WasmPlugins`：返回Wasm插件列表。
   - `WasmPluginsByListenerInfo`：按监听器信息返回Wasm插件列表。
   - `initEnvoyFilters`：初始化Envoy过滤器。
   - `EnvoyFilters`：返回Envoy过滤器列表。
   - `getMatchedEnvoyFilters`：返回匹配的Envoy过滤器。
   - `HasEnvoyFilters`：检查是否有Envoy过滤器。
   - `initGateways`：初始化网关。
   - `initAmbient`：初始化环境。
   - `mergeGateways`：合并网关。
   - `NetworkManager`：网络管理器。
   - `BestEffortInferServiceMTLSMode`：最佳推断服务的MTLS模式。
   - `ServiceEndpointsByPort`：按端口的服务终结点。
   - `ServiceEndpoints`：服务的终结点。
   - `initKubernetesGateways`：初始化Kubernetes网关。
   - `ReferenceAllowed`：检查引用是否被允许。
   - `ServiceAccounts`：服务账号。
   - `SupportsTunnel`：检查服务是否支持隧道。
   - `WaypointsFor`：获取Waypoint。
   - `WorkloadsForWaypoint`：获取Waypoint的工作负载。
