# Referer防盗链<a name="live01000301"></a>

Referer防盗链功能是基于HTTP协议支持的Referer机制，通过播放请求中携带的Referer字段来识别请求来源。配置Referer黑名单或白名单后，CDN会根据名单来对请求来源进行过滤，允许或拒绝播放请求。

## 注意事项<a name="section9354115514113"></a>

-   该功能为可选项，默认不启用。
-   Referer黑名单与Referer白名单互斥，不支持同时设置。
-   黑名单或白名单中的域名最多支持配置100条。
-   黑名单或白名单中配置的域名前不能带协议名，域名为前缀匹配。如填写“example.example01.com“，则“example.example01.com/123“和“example.example01.com.cn“也会匹配成功。

## 操作步骤<a name="section12744193714437"></a>

1.  登录[视频直播控制台](https://console.huaweicloud.com/live)。
2.  在左侧导航树中选择“域名管理“，进入域名管理页面。
3.  在需要配置鉴权信息的播放域名行右侧单击“管理“。
4.  在左侧导航树中选择“基础配置 \> 鉴权配置 \> Referer防盗链“，弹出“Referer防盗链“页面。
5.  单击“开关“，如[图1](#fig657733201016)所示，配置Referer防盗链参数。

    **图 1**  配置Referer防盗链<a name="fig657733201016"></a>  
    ![](figures/配置Referer防盗链.png "配置Referer防盗链")

    防盗链配置及对应访问权限说明如[表1](#zh-cn_topic_0129356805_table837817528191)所示。

    **表 1**  参数说明

    <a name="zh-cn_topic_0129356805_table837817528191"></a>
    <table><thead align="left"><tr id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_row19890101885714"><th class="cellrowborder" valign="top" width="10.67%" id="mcps1.2.3.1.1"><p id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p182343561940"><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p182343561940"></a><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p182343561940"></a>参数名</p>
    </th>
    <th class="cellrowborder" valign="top" width="89.33%" id="mcps1.2.3.1.2"><p id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p6890181895711"><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p6890181895711"></a><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p6890181895711"></a>描述</p>
    </th>
    </tr>
    </thead>
    <tbody><tr id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_row1089016185579"><td class="cellrowborder" valign="top" width="10.67%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p323410562417"><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p323410562417"></a><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p323410562417"></a>类型</p>
    </td>
    <td class="cellrowborder" valign="top" width="89.33%" headers="mcps1.2.3.1.2 "><div class="p" id="p4796204561519"><a name="p4796204561519"></a><a name="p4796204561519"></a>支持黑名单和白名单模式。<a name="ul1528259181510"></a><a name="ul1528259181510"></a><ul id="ul1528259181510"><li>Referer黑名单：允许非名单内的域名请求访问媒资，拒绝名单中的域名请求访问。</li><li>Referer白名单：允许名单内的域名请求访问点播媒资，拒绝其它域名请求访问。</li></ul>
    </div>
    <div class="p" id="p5232182113217"><a name="p5232182113217"></a><a name="p5232182113217"></a>包含空Referer是指HTTP请求Header中的Referer内容为空，或者无Referer。根据选择的黑名单或白名单，勾选“包含空Referer”的效果是不同的。<a name="ul413616772312"></a><a name="ul413616772312"></a><ul id="ul413616772312"><li>黑名单模式：勾选“包含空Referer”表示若请求中的Referer为空，则拒绝该请求，否则允许。</li><li>白名单模式：勾选“包含空Referer”表示若请求中的Referer为空，则允许该请求，否则拒绝。</li></ul>
    </div>
    </td>
    </tr>
    <tr id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_row4725335657"><td class="cellrowborder" valign="top" width="10.67%" headers="mcps1.2.3.1.1 "><p id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p1872653520517"><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p1872653520517"></a><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p1872653520517"></a>规则</p>
    </td>
    <td class="cellrowborder" valign="top" width="89.33%" headers="mcps1.2.3.1.2 "><p id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p15426936145216"><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p15426936145216"></a><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p15426936145216"></a>黑名单或白名单中的域名。</p>
    <a name="zh-cn_topic_0129356805_ul1316151174219"></a><a name="zh-cn_topic_0129356805_ul1316151174219"></a><ul id="zh-cn_topic_0129356805_ul1316151174219"><li>规则最多支持100条（最少1条），每一行一条记录，或者以英文<span class="parmvalue" id="zh-cn_topic_0129356805_parmvalue1116131117425"><a name="zh-cn_topic_0129356805_parmvalue1116131117425"></a><a name="zh-cn_topic_0129356805_parmvalue1116131117425"></a>“;”</span>分隔。</li><li>域名前不能带协议名（http://和https://）。</li><li>域名为前缀匹配，若填写<span class="parmvalue" id="parmvalue1293467145119"><a name="parmvalue1293467145119"></a><a name="parmvalue1293467145119"></a>“example.example01.com”</span>，则<span class="parmvalue" id="parmvalue1793487125112"><a name="parmvalue1793487125112"></a><a name="parmvalue1793487125112"></a>“example.example01.com/123”</span>和<span class="parmvalue" id="parmvalue14934571519"><a name="parmvalue14934571519"></a><a name="parmvalue14934571519"></a>“example.example01.com.cn”</span>也会匹配成功。</li></ul>
    <p id="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p588117345615"><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p588117345615"></a><a name="zh-cn_topic_0129356805_zh-cn_topic_0111450891_p588117345615"></a>示例如下：</p>
    <pre class="screen" id="screen38364143112"><a name="screen38364143112"></a><a name="screen38364143112"></a>example.example01.com
    example.example02.com</pre>
    </td>
    </tr>
    </tbody>
    </table>

6.  配置完成后，单击“确定“。

    配置完成后，需要3\~5分钟才能生效。


