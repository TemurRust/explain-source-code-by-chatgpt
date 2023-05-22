# explain-source-code-by-chatgpt

<br>


- 令chatgpt讲解Go核心源码中每个文件，变量，结构体，方法的作用；目前仅针对[runtime](https://github.com/cuishuang/explain-source-code-by-chatgpt/tree/main/runtime)包，后续会陆续增加**sync**，**net**，**cmd/go**等核心package


- 内容由chatgpt生成，仅供参考，不作为面试依据；内容必然存在大量错误，如果尽信，指定得被带到沟里..欢迎指出&提issue探讨,提pr勘误👏🏻


- 但用它来解释源码依然是非常有价值的，对底层原理有兴趣的开发者，可借此建立大概框架，一些具体和准确的细节再去相应添砖加瓦。…以往听到一种声音 说去读源码的注释，实践下来这种方式并不高效实用。在这块我投入了大量精力，之间的关联性，脉络，依然很多时候如同黑盒。另外不应过分高估源码中注释的质量，本人对Go仓库的几十次提交，有将近一半是修正注释

- 现阶段AI还只能充当「辅助驾驶员」角色，人手不能离开方向盘。也幸甚如此，作为「信息时代的司机」，最近一两年还不至于集体下岗；善用工具，让我们明年也不会下岗😄


