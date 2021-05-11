### 简介
微服务应用监控可以洞察完整事务流程的性能表现，从前端 APP 或浏览器到后端服务器、容器和代码各个级别进行应用性能分析，对系统的可用性和性能进行可视化管理，支持实时告警和全栈根因定位，提升运维开发效率。


### 详细介绍
#### 产品优势
1. 零侵入探针
2. 覆盖 APP、浏览器、服务端应用和中间件的全链路监控
3. 应用性能全栈溯源
4. 可视化的异常根因定位
5. 关键业务持续监控
6. 多维度实时告警和报表


#### 功能概述
##### 应用性能洞察
服务端应用的性能实时监控，提供 Web 事务、数据库查询、JVM 和应用全局拓扑可视化，快速掌握应用运行状态。

##### 浏览器性能洞察
提供基于真实用户访问的浏览器性能监控，快速定位页面访问瓶颈，全面掌握 Web 应用交付质量，并为 Web 站点的高效运营提供技术支撑。

##### 应用异常分析
自动收集和分析应用程序产生的异常，实时告警并提供可视化展示，帮助开发人员快速定位异常。

##### 分布式链路追踪
提供微服务应用系统的实时应用拓扑和调用链路追踪功能，通过记录用户请求在整个应用链路的调用详情，自动还原业务调用关系，快速定位影响业务性能的故障节点。

##### 关键业务持续监控
项目可用性和性能实时监测系统，同时支持业务的持续监控，异常重试及根因追踪定位。

##### 多维度实时告警和报表
提供机器、容器、中间件、应用性能及可用性等多个维度的实时告警，并提供告警根因分析，配合丰富的监控报表，可直接定位故障问题，降低运维成本。

### 使用场景
#### 关键业务持续监测
当前微服务架构下，项目应用都是由多个微小且相对独立的服务组合而成。每个业务场景都可能由多个微服务串联组成，任何一个服务出现异常都会影响到用户的使用和体验。
关键服务的稳定就显得尤为重要，然而在实际中对于部分服务不可用的故障，往往是在用户投诉反馈后才后知后觉。
持续的业务监控，能在第一时间发现业务的异常故障，同时触发故障重试机制，快速追踪定位异常根因。
实时的告警，能及时的通知对应人员，以最快的速度解决问题，恢复线上业务的正常运行。

#### 异常根因定位
在传统运维方式中，应用服务发生异常时，应用开发人员需要远程登录服务器查看异常日志，导致排错效率低下并且不方便事后复盘。针对此问题，应用监控提供了完整的异常大盘监控，展示异常发生次数的趋势，各种异常的所属应用、发生次数及时间、异常栈、请求信息等重要的关键信息，可以时刻了解应用程序的异常情况。异常产生时，应用监控实时发送预警消息，可以快速定位异常代码，并使用告警生成的工单来记录处理流程用于复盘总结，与此同时，应用监控记录应用服务的上下游依赖关系，展示不同应用之间通过 RPC 框架（如 Dubbo、HTTP协议）组成的调用链，并展示在这一次调用过程中分布在不同应用的所有日志，可以轻松地定位异常产生的原因。

#### 性能问题溯源
在微服务架构，我们将系统解耦成更小的服务单元。随着服务的不断增多，一次请求可能会涉及到十几个甚至几十个服务的协同处理，那么如何准确快速的定位到线上故障和性能瓶颈，便成为我们不得不面对的棘手问题。针对此问题，应用监控提供全局应用拓扑和调用链路查询，可以快速定位产生性能瓶颈的应用。接着深入到应用内部，通过慢事务、慢 SQL、GC 等数据分析及查看慢事务所关联的业务日志，找到引发性能瓶颈的业务接口。


### 使用方式

#### 入口
* 点击工作台界面的`微服务治理`中的监控实例。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/6a7c4a4a-418b-4a9e-810f-6fc1a0bc212a.png)
* 点击应用界面的`部署总览`中 monitor 服务插件。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/f29a937b-8abe-493c-b558-6cb8d3928076.png)

#### 功能
* [监控总览](#overview)（展示应用和浏览性能指标概览）
* [应用拓扑](#topology)（展示应用与应用、应用与 addon 之间的调用拓扑）
* [应用性能](#application)（展示 Web 应用程序的性能）
* [浏览性能](#browser)（展示页面应用的性能）
* [链路追踪](#trace)（发起请求记录整个调用链）
* [错误分析](#error)（展示应用每一次 ERROR 级别日志打印的异常）
* [主动监控](#status)（实时检测 URL 运行状态和性能）

#### 概念
* Apdex 指数：Application Performance Index，性能指数，[WIKI](https://en.wikipedia.org/wiki/Apdex)。
* cpm：count per minute，每分钟次数。
* PV：page view，页面浏览量。

<h3 id="overview">监控总览</h3>
`监控总览`展示项目中 Web 应用的性能概览。

用户可以通过这个概览对于项目中的应用整体性能有一个大致上的了解。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/8122e963-9d91-4bfe-84eb-8f44dad26aaf.png)

##### 指标介绍
`页面性能`、`访问量`、`浏览器访问性能`需要接入 ta.js 脚本，详见[浏览器性能](#browser)。
* `页面性能`展示最近一小时内浏览器页面加载性能。
	+ Apdex 指数越接近1表示加载性能越好。
	+ Ajax 错误率表示 Ajax 获取 HTTP 状态码大于400的比率
* `应用性能`展示最近一小时内 Web 应用的性能。
* `访问量`展示了最近七天内页面访问次数按天统计的情况。
* `浏览器访问性能`
	+ `性能区间`展示了最近一小时内页面加载过程中主要步骤的性能。
	+ `Ajax 性能趋势`展示最近一小时内 Ajax 的请求情况。
	+ `HTTP 状态`展示最近一小时内接口请求返回的各种 HTTP 状态码的统计情况。
* `应用性能`展示最近一小时内 Web 应用接收到 HTTP 请求的响应时间和吞吐量的统计情况。

<h3 id="topology">应用拓扑</h3>
`应用拓扑`展示应用与应用之间，应用与 Addon 之间的调用拓扑。

默认展示一小时内变化数据，也可以点击时间选择框选择所需展示时间。

用户可以通过这个拓扑了解项目下各个应用的调用关系与次数。可点击应用图标跳转`应用性能`。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/ac799102-343a-4a6c-937e-b423c7dd76fd.png)

<h3 id="application">应用性能</h3>
`应用性能`展示  事务的大致情况。用户不需要再猜测程序性能瓶颈是来自应用程序本身，CPU 可用性，数据库抖动，还是其它那些完全没有想到的情况。使用 AI，您可以在最终用户受到影响之前快速识别潜在的问题。

默认展示一小时内变化数据，也可以点击时间选择框选择所需展示时间。

功能分为：
* [总览](#application_overview)
* [WEB 事务](#application_web)
* [RPC 事务](#application_rpc)
* [数据库](#application_db)
* [缓存](#application_cache)
* [JVMs](#application_jvms)
* [NodeJS](#application_nodejs)

<h4 id="application_overview">总览</h4>
`总览`展示了 Server 应用的性能总览。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/c6c1b9e1-bfaf-40d3-ae07-af6953c85128.png)

<h4 id="application_web">WEB 事务</h4>
`WEB 事务`展示了 Server 应用的事务详情，以接口维度展示调用明细，耗时前五的 API 性能趋势，总体吞吐量，与慢事务。
* WEB 事务明细：平均响应时间、响应时间占比、吞吐量分别展示了每个事务接口在选择时间内的平均响应时间、每个接口占用总体调用时间的百分比，与每个接口的每分钟调用次数。
* 响应时间 Top5：展示了选择时间内平均响应时间前五的事务接口与趋势。
* 吞吐量 Top5：展示了选择时间内每分钟被请求的次数前五位的事务接口与趋势。
* HTTP 错误：展示了选择时间内 HTTP 请求中状态大于 400 的数量趋势。
* 慢事务追踪 Top10：展示了选择时间内响应时间超过 300 ms 并且排列前十的事务接口的发生次数与平均响应时间等信息。
在选择左侧 WEB 事务列表中的具体接口后，会展示该接口的明细数据，包括其响应时间趋势与每分钟吞吐量趋势。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/e4a47d8d-f2e6-4638-a133-cbac02903068.png)

<h4 id="application_rpc">RPC 事务</h4>
`RPC 事务`展示了应用提供的 RPC 事务详情，以接口维度展示调用明细，耗时前五的 API 性能趋势，总体吞吐量，与慢事务。
* RPC 事务明细：平均响应时间、响应时间占比、吞吐量分别展示了每个事务在选择时间内的平均响应时间、每个事务占用总体调用时间的百分比，与每个事务的每分钟调用次数。
* 响应时间 Top5：展示了选择时间内平均响应时间前五的事务接口与趋势。
* 吞吐量 Top5：展示了选择时间内每分钟被请求的次数前五位的事务与趋势。
* 慢事务追踪 Top10：展示了选择时间内响应时间超过 300 ms 并且排列前十的事务接口的发生次数与平均响应时间等信息。
在选择左侧 RPC 事务列表中的具体接口后，会展示该接口的明细数据，包括其响应时间趋势与每分钟吞吐量趋势。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/eaa256db-7931-4323-bb5c-3cd7b5b5fd37.png)

<h4 id="application_db">数据库</h4>
`数据库`展示了数据库事务详情，以 Server 应用中 SQL 调用明细，耗时前五的查询性能趋势，总体吞吐量，与慢数据库追踪。
* 数据库明细：平均响应时间、吞吐量分别展示了所选时间内每个 SQL 的平均执行时间、每个 SQL 的每分钟调用次数。
* 响应时间 Top5：展示了所选时间内 SQL 执行时间前五的数据库事物与性能趋势。
* 吞吐量 Top5：展示了所选时间内每分钟被请求数据库 SQL 排列前五位的次数与趋势。
* 慢数据库追踪 Top10：慢事物列表展示了所选时间内响应时间超过 250 ms 并且排列前十的 SQL 次数与平均响应时间等信息。
在选择左侧数据库查询 SQL 后，可以单独查看该查询方法的调用响应时长趋势与吞吐量趋势。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/3f29d99b-a592-4eaa-8ea8-cf370ea4e6ca.png)

<h4 id="application_cache">缓存</h4>
`缓存``展示了 redis 调用明细，耗时前五的查询性能趋势，总体吞吐量。
* 缓存明细：平均响应时间、吞吐量分别展示了所选时间内每次 redis 调用的平均执行时间、每个 redis 调用的每分钟调用次数。
* 响应时间 Top5：展示了所选时间内 redis 调用时间排列后前五的redis查询与性能趋势。
* 吞吐量 Top5：展示了所选时间内每分钟 redis 调用排列前五位的次数与趋势。
在选择左侧缓存查询命令后，可以单独查看该查询命令的调用响应时长趋势与吞吐量趋势。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/24bbc9a3-78ae-49dd-bfba-2109724ef483.png)

<h4 id="application_jvms">JVMs</h4>
`JVMs`展示了应用中的各个模块的各个 Java 容器实例状态，并默认显示第一个模块，如果一个应用部署了多个实例，则默认显示第一个模块的第一个实例。可以切换模块名/实例名。
* Heap memory usage：JVM 堆内存使用情况。
* Non Heap memory usage：JVM 非堆内存使用情况。
* PS-Eden-Space，PS-Old-Gen，PS-Survivor-Space：分别表示 jvm 堆内存中伊甸园，老年代区，幸存者区。
* GC 次数，GC 平均时间：分别表示 JVM GC 的次数和平均时间。
* Class count：展示JVM从启动开始加载和卸载的类的个数。
* Thread：JVM加载线程。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/58241571-b805-46da-8b49-c4a10760ba1d.png)

<h4 id="application_nodejs">NodeJS</h4>
`NodeJS`展示了应用中的各个模块的各个 NodeJS 容器实例状态，并默认显示第一个模块，如果一个应用部署了多个实例，则默认显示第一个模块的第一个实例。可以切换模块名/实例名。
* Heap memory usage：NodeJS 堆内存使用情况。
* Non Heap memory usage：NodeJS 非堆内存使用情况。
* Cluster Count：NodeJS 中 cluster 的数量。
* AsyncResource：NodeJS 中的异步资源。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/9c5687aa-ee62-48a2-9404-3e2565f7ca53.png)

<h3 id="browser">浏览性能</h3>
`浏览性能`展示浏览器监控的大致情况。提供了直接面向用户的浏览器应用的性能追踪，包括响应加载时间，页面错误，异步调用，地理追踪等等。

默认展示一小时内变化数据，也可以点击时间选择框选择所需展示时间。

功能分为：
* [总览](#browser_overview)
* [访问域名](#browser_domain)
* [访问页面](#browser_page)
* [定位分析](#browser_location)
* [Ajax接口](#browser_ajax)
* [脚本错误](#browser_script)
* [浏览器性能](#browser_performance)
* [摘要](#browser_summary)
* [地理](#browser_geography)

##### 接入监控
* SPA（single page application）
    1. 修改 pipeline.yml 中的 buildpack 
    ```
    stages:
    - stage:
        - buildpack:
            params:
                bp_repo: ((bp.repo.prefix))/dice-bpack-termspa.git
    ```
    2. 在模板页的 head 中添加 ta.js
    ```
    <script src="/ta"></script>
    <script>
      var _taConfig = window._taConfig;
      if (_taConfig && _taConfig.enabled) {
        !function(e,n,r,t,a,o,c){e[a]=e[a]||function(){(e[a].q=e[a].q||[]).push(arguments)},e.onerror=function(n,r,t,o,c){e[a]("sendExecError",n,r,t,o,c)},n.addEventListener("error",function(n){e[a]("sendError",n)},!0),o=n.createElement(r),c=n.getElementsByTagName(r)[0],o.async=1,o.src=t,c.parentNode.insertBefore(o,c)}(window,document,"script",_taConfig.url,"$ta");
        $ta('start', { udata: { uid: 0 }, ak: _taConfig.ak, url: _taConfig.collectorUrl });
      }
    </script>
    ```
    3. 在 nginx.conf.template 中添加 /ta 请求处理
    ```
        set $taEnabled ${TERMINUS_TA_ENABLE};
        set $taUrl ${TERMINUS_TA_URL};
        set $collectorUrl ${TERMINUS_TA_COLLECTOR_URL};
        set $terminusKey ${TERMINUS_KEY};
        location /ta {
            default_type application/javascript;
            return 200 'window._taConfig={enabled:$taEnabled,ak:"$terminusKey",url:"$taUrl",collectorUrl:"$collectorUrl"}';
        }
    ```
    4. 采集用户 ID ，添加用户维度的统计，需要在前端，用户查询的位置把 userId 设置到 ta.js 的缓存
    ```js
    if (typeof window.$ta !== 'undefined') window.$ta('setUser', [userId])
    ```

* SpringMVC
    1. 添加 Config 类读取 ta.js 环境变量
    ```
    @Component
    @Data
    public class TaConfig {
        @Value("${terminus.ta.collector.url}")
        private String terminusTaCollectorURL;

        @Value("${terminus.ta.enable}")
        private boolean terminusTaEnable;

        @Value("${terminus.ta.url}")
        private String terminusTaURL;

        @Value("${terminus.key}")
        private String terminusKey;
    }
    ```
    2. 添加 Controller 返回 ta.js 的配置
    ```
    @Slf4j
    @RestController
    @RequestMapping("/api/ta")
    public class TaController {

        @Autowired
        private TaConfig config;

        @RequestMapping(produces = "application/javascript")
        @ResponseBody
        public String ta() {
            return String.format("window._taConfig={enabled:%b,ak:\"%s\",url:\"%s\",collectorUrl:\"%s\"}", config.isTerminusTaEnable(), config.getTerminusKey(), config.getTerminusTaURL(), config.getTerminusTaCollectorURL());
        }
    }
    ```
    3. 在需要被监控的页面 head 中添加 ta.js 激活代码
    ```
    <head>
        <script src="/api/ta"></script>
        <script>
            var _taConfig = window._taConfig;
            if (_taConfig && _taConfig.enabled) {
                !function (e, n, r, t, a, o, c) {
                    e[a] = e[a] || function () {
                        (e[a].q = e[a].q || []).push(arguments)
                    }, e.onerror = function (n, r, t, o, c) {
                        e[a]("sendExecError", n, r, t, o, c)
                    }, n.addEventListener("error", function (n) {
                        e[a]("sendError", n)
                    }, !0), o = n.createElement(r), c = n.getElementsByTagName(r)[0], o.async = 1, o.src = t, c.parentNode.insertBefore(o, c)
                }(window, document, "script", _taConfig.url, "$ta");
                $ta('start', {udata: {uid: 0}, ak: _taConfig.ak, url: _taConfig.collectorUrl});
            }
        </script>
    </head>
    ```
* herd
    1. 添加 terminus-key.js 中间件
    ```
    module.exports = () => async (ctx, next) => {
      ctx.herdContext['_TERMINUS_KEY_'] = process.env.TERMINUS_KEY;
      ctx.herdContext['_TA_ENABLE_'] = process.env.TERMINUS_TA_ENABLE || false;
      ctx.herdContext['_TA_URL_'] = process.env.TERMINUS_TA_URL || '//static.terminus.io/ta.js';
      ctx.herdContext['_TA_COLLECT_URL_'] = process.env.TERMINUS_TA_COLLECTOR_URL || '//analytics.terminus.io/collect';
      await next();
    }
    ```
    2. 在 layout.hbs 的 head 中添加 ta.js script
{% raw %}
    ```
     <head>
        <script>
            {{#if _TA_ENABLE_}}
              !function(e,t,n,s,a,c,i){e[a]=e[a]||function(){(e[a].q=e[a].q||[]).push(arguments)},c=t.createElement(n),i=t.getElementsByTagName(n)[0],c.async=1,c.src=s,i.parentNode.insertBefore(c,i)}(window,document,"script","{{_TA_URL_}}","$ta");
              $ta('start',{ udata: { uid: {{#if _USER_}}{{_USER_.id}}{{else}}0{{/if}} }{{#if _TERMINUS_KEY_}}, ak: '{{_TERMINUS_KEY_}}'{{/if}} , url: '{{_TA_COLLECT_URL_}}' })
            {{/if}}
        </script>
      </head>
    ```
{% endraw %}
    3. 采集用户 ID，添加用户维度的统计，需要在前端，用户查询的位置把 userId 设置到 ta.js 的缓存
    ```
    if (typeof window.$ta !== 'undefined') window.$ta('setUser', [userId])
    ```

<h4 id="browser_overview">总览</h4>
`总览`展示浏览器的性能总览。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/41967a4c-ff9d-471d-8094-6b212ce4ef41.png)

<h4 id="browser_domain">访问域名</h4>
一个应用往往会配置多个子域名，例如移动端与PC端的域名、子域名二级域名等等，`访问域名`可以根据域名的维度区分性能数据。

此页面按照应用的域名维度展示页面加载性能趋势、响应时间趋势、吞吐量与慢加载，点击左侧域名后可以查看该域名的明细，并且将页面加载分为白屏时间，首屏时间，网页加载完成，资源加载完成4个时间维度进行查看。
* 白屏时间：从准备加载页面到浏览器开始显示内容的时间
* 首屏时间：指用户看到第一屏，即整个网页顶部大小为当前窗口的区域，显示完整的时间
* 网页加载完成：从接收到页面文档第一个字节到接收到最后一个字节的时间
* 资源加载完成：页面内js、css、image等资源加载时间
在选择左侧访问域名后，可以单独查看该域名访问的性能趋势等信息。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/f4cbc2ed-9bc6-4d77-8c8b-208d1b9c8a0c.png)

<h4 id="browser_page">访问页面</h4>
类似于访问域名，访问页面的性能监控是根据页面维度来展示 BI 性能监控数据的，其交互逻辑与访问域名相同。

在选择左侧访问请求后，可以单独查看该请求的性能趋势等信息。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/fc6e209d-95d5-4839-8424-30c7213148a2.png)

<h4 id="browser_location">定位分析</h4>
定位分析提供用户体验 Apdex，整页加载完成，白屏时间，首屏时间，资源加载完成，网页加载完成，性能分析多个维度的数据对比，同时提供了操作系统，设备，浏览器，域名，页面等多维度数据统计，用于多方位的浏览器浏览性能分析。
* 用户体验 Apdex：Apdex是用户对应用性能满意度的量化值
* 整页加载完成：Page Load Time，是指页面完成整个加载过程的时刻
* 白屏时间：从准备加载页面到浏览器开始显示内容的时间
* 首屏时间：指用户看到第一屏，即整个网页顶部大小为当前窗口的区域，显示完整的时间
* 资源加载完成：页面内js、css、image等资源加载时间
* 网页加载完成：从接收到页面文档第一个字节到接收到最后一个字节的时间
* 性能分析：可以根据以上指标和用户特征进行性能对比
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/1976dc85-263d-470c-af02-bdd6b15d9d07.png)

<h4 id="browser_ajax">Ajax接口</h4>
从 Ajax 维度，展示每条 Ajax 请求的平均响应时间，时间百分比，吞吐量，并且从响应时间 TOP5，吞吐量 TOP5，发送数据，接收数据四个方面展示请求性能趋势。

在选择左侧 Ajax 请求后，可以单独查看该请求的性能趋势等信息。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/47e42ffe-e2a5-4115-9540-ebe2dca0e8f0.png)

<h4 id="browser_script">脚本错误</h4>
从多维度展示 JavaScript 执行过程中的错误信息。
* 错误信息：具体的错误信息，在选择左侧错误信息后，可以单独查看该错误信息的详情。
* 出错页面：错误产生的请求页面
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/fb2ac762-fd17-4c30-aeae-0056e462649f.png)

<h4 id="browser_performance">浏览器性能</h4>
从浏览器维度，展示不同浏览器的性能指标，指标类型与 ajax 接口类似。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/98d84e92-9ca6-4e9b-ba04-384ad43a4bb6.png)

<h4 id="browser_summary">摘要</h4>
从访问域名，访问页面，系统，浏览器，设备等方面展示页面加载的具体详情。

选择左侧某条维度信息后，会展示该维度信息的页面请求过程详情。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/7332ba56-9e15-4388-9fb1-600727160291.png)

<h4 id="browser_geography">地理</h4>
从访问地理维度展示各个地区的访问性能情况。

选择左侧地理信息，会展示该地区的具体访问性能指标。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/6d7fe3a7-9c7e-47d3-af77-e8447ed94444.png)

<h3 id="trace">链路追踪</h3>
`链路追踪`通过模拟用户发送的 HTTP 请求，从 servlet 接收到 request 到返回 response 过程中，包括Dubbo类的RPC调用，数据库、缓存等中间件调用都进行全链路记录，并在监控采集完全后展示出来。

请求流程：
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/03/11/0aea348a-a0e1-4df3-8a3d-cd018958c7fc.png)

通过这个功能可以模拟用户行为观察该行为通过了哪些模块，调用了哪些中间件，每一步的耗时是多少，可以用来追踪问题源头或者性能瓶颈。
* 每次 HTTP 请求发送后都会在查询记录里生成一条记录
* HTTP 请求支持 URL、Method、Params、Headers、Body 的修改，如果请求需要登录，请将 Cookie 放入 Header 中
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/ee1520ef-2895-4fc9-8604-96e1364edc75.png)
* 链路数据支持串联各个开启了 Monitor 功能的不同应用之间的调用。
* 链路数据记录了每次调用的依赖关系、持续时间甚至参数和异常。
* 链路数据中，一行表示一个 Span，表示一次诸如 MySQL 调用、RPC 调用之类的与第三方服务产生调用的操作。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/1b0e0ff9-1c1f-43bb-96e9-aaeaa2d29983.png)
* 每个 Span 都可以点击，展示更多关于这个 Span 的信息
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/615f2cd0-cde8-43ab-8580-a50f79b1d28b.png)

<h3 id="error">错误分析</h3>
`错误分析`记录开启了 Monitor 功能的应用中的每一次 error 级别日志打印时的异常。

通过这个功能可以观察到选定时间内异常出现的次数，并观察到每种异常生成的次数与具体信息，可以帮助研发人员 review 自己的代码质量，改进代码的健壮性。

异常数据来源于项目下所有打开了 Monitor Addon 的应用。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/0b7e16d8-7c0e-4b9b-8687-20a3fd91b2ea.png)
点击异常名称，可以查看异常的详情。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/7082edc6-6cc7-41ea-be7d-8503bfac483d.png)

<h3 id="status">主动监控</h3>
`主动监控`基于 URL 实时检测运行状态和性能，同时还支持事件告警和 Issue 管理的功能。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/d7500dd9-f114-44b2-b660-bd54e9677c1f.png)
* 主动监控支持鉴权，基本原理是：利用账户名密码模拟用户登陆，获取对应的 cookie，然后在访问 url 指标时，在请求头里带上该 cookie 访问。
* 总览页可以进行账户管理，方便之后监控指标的鉴权操作。点击"账户管理"按钮可以跳转账户管理页面。
* 账户管理页新增鉴权需要先新增模板，模板抽象出登陆逻辑，把鉴权设置通过 json 的方式来实现。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/70ed415c-9277-45aa-96d5-b1bef794a5c5.png)
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/a001d039-e9be-48ba-a8d7-4dc8a82d4293.png)
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/9a26d0c1-b00c-4871-b594-5be4f210bae5.png)
    * [必填]auth:  是否开启鉴权， 0 - 不鉴权    1 - 鉴权
    * [必填]username: 登陆的用户名，其中key为form data里的key，value为form data里的value
    * [必填]password: 登陆的密码，其中key为form data里的key，value为form data里的value
    * [必填]url: 登陆请求的URL
    * [选填]method: 登陆请求的类型
    * [选填]content-type: 登陆请求的content-type
    * [选填]referer: 对于类似的第三方登陆，需要设置登陆后跳转到指定系统的redirect url
* 点击"添加监控"可以新增监控指标，可以对返回值的内容进行正则匹配。如果指标异常（请求无响应、内容不匹配等）都会将指标状态变更，同时发出告警。
    ![](//terminus-paas.oss-cn-hangzhou.aliyuncs.com/paas-doc/2019/04/23/c4ef1df0-0002-4cc7-981f-767e3c422d7e.png)
.idea/workspace.xml
