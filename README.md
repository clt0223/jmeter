# jmeter
jmeter接口脚本
<?xml version="1.0" encoding="UTF-8"?>
<jmeterTestPlan version="1.2" properties="3.2" jmeter="3.2 r1790748">
  <hashTree>
    <TestPlan guiclass="TestPlanGui" testclass="TestPlan" testname="测试计划" enabled="true">
      <stringProp name="TestPlan.comments"></stringProp>
      <boolProp name="TestPlan.functional_mode">false</boolProp>
      <boolProp name="TestPlan.serialize_threadgroups">false</boolProp>
      <elementProp name="TestPlan.user_defined_variables" elementType="Arguments" guiclass="ArgumentsPanel" testclass="Arguments" testname="用户定义的变量" enabled="true">
        <collectionProp name="Arguments.arguments"/>
      </elementProp>
      <stringProp name="TestPlan.user_define_classpath"></stringProp>
    </TestPlan>
    <hashTree>
      <ThreadGroup guiclass="ThreadGroupGui" testclass="ThreadGroup" testname="线程组" enabled="true">
        <stringProp name="ThreadGroup.on_sample_error">continue</stringProp>
        <elementProp name="ThreadGroup.main_controller" elementType="LoopController" guiclass="LoopControlPanel" testclass="LoopController" testname="循环控制器" enabled="true">
          <boolProp name="LoopController.continue_forever">false</boolProp>
          <stringProp name="LoopController.loops">1</stringProp>
        </elementProp>
        <stringProp name="ThreadGroup.num_threads">1</stringProp>
        <stringProp name="ThreadGroup.ramp_time">1</stringProp>
        <longProp name="ThreadGroup.start_time">1570764537000</longProp>
        <longProp name="ThreadGroup.end_time">1570764537000</longProp>
        <boolProp name="ThreadGroup.scheduler">false</boolProp>
        <stringProp name="ThreadGroup.duration"></stringProp>
        <stringProp name="ThreadGroup.delay"></stringProp>
      </ThreadGroup>
      <hashTree>
        <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="投递搜索_获取最新at和rt" enabled="true">
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="用户定义的变量" enabled="true">
            <collectionProp name="Arguments.arguments">
              <elementProp name="userId" elementType="HTTPArgument">
                <boolProp name="HTTPArgument.always_encode">false</boolProp>
                <stringProp name="Argument.value">1017922981</stringProp>
                <stringProp name="Argument.metadata">=</stringProp>
                <boolProp name="HTTPArgument.use_equals">true</boolProp>
                <stringProp name="Argument.name">userId</stringProp>
              </elementProp>
              <elementProp name="access_token" elementType="HTTPArgument">
                <boolProp name="HTTPArgument.always_encode">false</boolProp>
                <stringProp name="Argument.value">06241e4a115d41bba8a3d97742443377Do37</stringProp>
                <stringProp name="Argument.metadata">=</stringProp>
                <boolProp name="HTTPArgument.use_equals">true</boolProp>
                <stringProp name="Argument.name">access_token</stringProp>
              </elementProp>
            </collectionProp>
          </elementProp>
          <stringProp name="HTTPSampler.domain">api.open.zhaopin.com</stringProp>
          <stringProp name="HTTPSampler.port"></stringProp>
          <stringProp name="HTTPSampler.protocol">http</stringProp>
          <stringProp name="HTTPSampler.contentEncoding"></stringProp>
          <stringProp name="HTTPSampler.path">passportapi/auth/loginbyuserid</stringProp>
          <stringProp name="HTTPSampler.method">GET</stringProp>
          <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
          <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
          <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
          <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
          <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
          <stringProp name="HTTPSampler.connect_timeout"></stringProp>
          <stringProp name="HTTPSampler.response_timeout"></stringProp>
        </HTTPSamplerProxy>
        <hashTree>
          <com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.JSONPathExtractor guiclass="com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.gui.JSONPathExtractorGui" testclass="com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.JSONPathExtractor" testname="jp@gc - JSON Path Extractor--access_token(提取at)" enabled="true">
            <stringProp name="VAR">access_token</stringProp>
            <stringProp name="JSONPATH">$.access_token</stringProp>
            <stringProp name="DEFAULT">null</stringProp>
            <stringProp name="VARIABLE"></stringProp>
            <stringProp name="SUBJECT">BODY</stringProp>
          </com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.JSONPathExtractor>
          <hashTree/>
          <com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.JSONPathExtractor guiclass="com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.gui.JSONPathExtractorGui" testclass="com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.JSONPathExtractor" testname="jp@gc - JSON Path Extractor--refresh_token（提取rt）" enabled="true">
            <stringProp name="VAR">refresh_token</stringProp>
            <stringProp name="JSONPATH">$.refresh_token</stringProp>
            <stringProp name="DEFAULT">null</stringProp>
            <stringProp name="VARIABLE"></stringProp>
            <stringProp name="SUBJECT">BODY</stringProp>
          </com.atlantbh.jmeter.plugins.jsonutils.jsonpathextractor.JSONPathExtractor>
          <hashTree/>
        </hashTree>
        <ConfigTestElement guiclass="HttpDefaultsGui" testclass="ConfigTestElement" testname="HTTP请求默认值" enabled="true">
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments" guiclass="HTTPArgumentsPanel" testclass="Arguments" testname="用户定义的变量" enabled="true">
            <collectionProp name="Arguments.arguments"/>
          </elementProp>
          <stringProp name="HTTPSampler.domain">rd.zhaopin.com</stringProp>
          <stringProp name="HTTPSampler.port"></stringProp>
          <stringProp name="HTTPSampler.protocol">https</stringProp>
          <stringProp name="HTTPSampler.contentEncoding">utf-8</stringProp>
          <stringProp name="HTTPSampler.path">/api/bapp</stringProp>
          <stringProp name="HTTPSampler.concurrentPool">6</stringProp>
          <stringProp name="HTTPSampler.connect_timeout"></stringProp>
          <stringProp name="HTTPSampler.response_timeout"></stringProp>
        </ConfigTestElement>
        <hashTree/>
        <HeaderManager guiclass="HeaderPanel" testclass="HeaderManager" testname="HTTP信息头管理器" enabled="true">
          <collectionProp name="HeaderManager.headers">
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">content-type</stringProp>
              <stringProp name="Header.value">application/json</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-client-type</stringProp>
              <stringProp name="Header.value">i</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-business-system</stringProp>
              <stringProp name="Header.value">24</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">accept</stringProp>
              <stringProp name="Header.value">*/*</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-device-id</stringProp>
              <stringProp name="Header.value">DE32E765AD8BFF612781832CBF32AE43</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-channel</stringProp>
              <stringProp name="Header.value">AppStore</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-version</stringProp>
              <stringProp name="Header.value">5.4.2</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-at</stringProp>
              <stringProp name="Header.value">${access_token}</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">accept-language</stringProp>
              <stringProp name="Header.value">zh-cn</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">content-length</stringProp>
              <stringProp name="Header.value">360</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">user-agent</stringProp>
              <stringProp name="Header.value">iPhone6,2(iOS/12.4) WeexGroup(</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">wtoken</stringProp>
              <stringProp name="Header.value">KIUR_yXjC6I320t53gf/4SieWDRC1lTapwqjp4+YnqKJmNWkZT2yp75Keu6H6ba4FXSl/HrWRVqEhdAPqSUSIVcBM/wEja2EAhsmKfu6AfmUODaIvqjMPKZYYqSS2+L08fYws3ZK8+4yIe9cllCwoXAELaJ9eVY0G2mZMIu/Q3LT7wi6MHF9IsTbFsI0Xq5gWMdOSkf1UjKg32wRz8ZgtbdHXUFsbyigjCHf3GM/X/ggu0yn4n1Mm0mokxMQOFqf5dNL5bKDy8YTtTt1TtjaG26EO16OEAGzaMyORRqejltgTss6AdZATAz+b2zQ47B1iJHU975+LJlrZkJBte9LEEtIZrGuQiNBw4zuTiQeHRNK9uVnHxk9zqtUkgclh+1y0GOpT4L3M1MpOVlewncSYZr/aWYQuvAVQnreVzAyMvAZjm5m3qTkg9galUUwZSaqXB17O&amp;IMHW_i00138c7b8ea82c211f504e062cde00065450f640cec1</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-client-id</stringProp>
              <stringProp name="Header.value">DE32E765AD8BFF612781832CBF32AE43</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-departmentid</stringProp>
              <stringProp name="Header.value">84027024</stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-user-agent</stringProp>
              <stringProp name="Header.value"></stringProp>
            </elementProp>
            <elementProp name="" elementType="Header">
              <stringProp name="Header.name">x-zp-rt</stringProp>
              <stringProp name="Header.value">${refresh_token}</stringProp>
            </elementProp>
          </collectionProp>
        </HeaderManager>
        <hashTree/>
        <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="待处理" enabled="true">
          <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
            <collectionProp name="Arguments.arguments">
              <elementProp name="" elementType="HTTPArgument">
                <boolProp name="HTTPArgument.always_encode">false</boolProp>
                <stringProp name="Argument.value">{&#xd;
	&quot;query&quot;: &quot;query ($path: String, $params: Raw!) { proxy(path: $path, params: $params)}&quot;,&#xd;
	&quot;variables&quot;: {&#xd;
		&quot;path&quot;: &quot;bapp/resume/resumelistbykey&quot;,&#xd;
		&quot;params&quot;: {&#xd;
			&quot;jobNo&quot;: &quot;&quot;,&#xd;
			&quot;rowsCount&quot;: 20,&#xd;
			&quot;startNum&quot;: 0,&#xd;
			&quot;follow&quot;: false,&#xd;
			&quot;orderFlag&quot;: &quot;deal&quot;,&#xd;
			&quot;resumeSource&quot;: &quot;-1&quot;,&#xd;
			&quot;countFlag&quot;: 1,&#xd;
			&quot;candidateStatus&quot;: &quot;deal&quot;&#xd;
		}&#xd;
	}&#xd;
}</stringProp>
                <stringProp name="Argument.metadata">=</stringProp>
              </elementProp>
            </collectionProp>
          </elementProp>
          <stringProp name="HTTPSampler.domain"></stringProp>
          <stringProp name="HTTPSampler.port"></stringProp>
          <stringProp name="HTTPSampler.protocol"></stringProp>
          <stringProp name="HTTPSampler.contentEncoding"></stringProp>
          <stringProp name="HTTPSampler.path"></stringProp>
          <stringProp name="HTTPSampler.method">POST</stringProp>
          <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
          <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
          <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
          <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
          <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
          <stringProp name="HTTPSampler.connect_timeout"></stringProp>
          <stringProp name="HTTPSampler.response_timeout"></stringProp>
        </HTTPSamplerProxy>
        <hashTree>
          <BeanShellPostProcessor guiclass="TestBeanGUI" testclass="BeanShellPostProcessor" testname="提取jobResumeIds" enabled="false">
            <stringProp name="filename"></stringProp>
            <stringProp name="parameters"></stringProp>
            <boolProp name="resetInterpreter">false</boolProp>
            <stringProp name="script">import org.json.JSONObject;
import org.json.JSONArray;
import java.util.ArrayList;
import java.util.List;

public static String jobResumeIds;
String response_data = prev.getResponseDataAsString();//获取String格式的response数据
JSONObject jsonObject = new JSONObject(response_data);//将整个Response转为JSON对象
//JSONArray listArray = jsonObject.get(&quot;data&quot;).get(&quot;proxy&quot;).get(&quot;data&quot;).get(&quot;deal&quot;).getJSONArray(&quot;results&quot;);
log.info(&quot;-------------------------&quot;+ results );
//JSONArray listArray = jsonObject.get(&quot;data&quot;).get(&quot;proxy&quot;).get(&quot;data&quot;).get(&quot;deal&quot;).get(&quot;results[0].id&quot;);
//JSONArray listArray = jsonObject.get(&quot;data&quot;).get(&quot;proxy&quot;).get(&quot;data&quot;).get(&quot;deal&quot;).get(&quot;results[1]&quot;).get(&quot;id&quot;).getJSONArray(&quot;list&quot;);
//log.info(&quot;-------------------------&quot;+ id );
//
List list  = new ArrayList();
for(int i=0;i&lt;2;i++){
	String id = listArray.getJSONObject(i).get(&quot;id&quot;).toString();
	jobResumeIds = id + &quot;,&quot;;
	list.add(id);
    }
    String str_jobResumeIds = list.toString().replaceAll(&quot;;&quot;,&quot;&quot;,&quot;&quot;).replaceAll(&quot; &quot;,&quot;&quot;,&quot;&quot;);
    String str_1 = str.substring(1, str.length() - 1);
log.info(&quot;----------------------&quot;+ id );
//log.info(str.substring(1, str.length() - 1));
//log.info(&quot;jobResumeIds:&quot;+ jobResumeIds);
//vars.put(&quot;jobResumeIds&quot;,str.substring(1, str.length() - 1));


</stringProp>
          </BeanShellPostProcessor>
          <hashTree/>
          <BeanShellPostProcessor guiclass="TestBeanGUI" testclass="BeanShellPostProcessor" testname="BeanShell PostProcessor" enabled="true">
            <boolProp name="resetInterpreter">false</boolProp>
            <stringProp name="parameters"></stringProp>
            <stringProp name="filename"></stringProp>
            <stringProp name="script">import org.json.JSONObject;
import org.json.JSONArray;
import java.util.ArrayList;
import java.util.List;

public static String jobResumeIds;
String response_data = prev.getResponseDataAsString();//获取String格式的response数据
JSONObject jsonObject = new JSONObject(response_data);//将整个Response转为JSON对象
JSONArray listArray = jsonObject.get(&quot;data&quot;).get(&quot;proxy&quot;).get(&quot;data&quot;).get(&quot;deal&quot;).getJSONArray(&quot;results&quot;);
//log.info(&quot;=============&quot; + listArray );
//int leng = listArray.length();
//log.info(&quot;=============&quot; + leng );

List list  = new ArrayList();
for(int i=0;i&lt;2;i++){
	String id = listArray.getJSONObject(i).get(&quot;id&quot;).toString();
	list.add(id);
    }
String str_jobResumeIds = list.toString().replaceAll(&quot;;&quot;,&quot;&quot;,&quot;&quot;).replaceAll(&quot; &quot;,&quot;&quot;,&quot;&quot;);
vars.put(&quot;jobResumeIds&quot;,list.toString());
//log.info(&quot;=============&quot; + jobResumeIds )
</stringProp>
          </BeanShellPostProcessor>
          <hashTree/>
        </hashTree>
        <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="批量处理" enabled="true">
          <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
            <collectionProp name="Arguments.arguments">
              <elementProp name="" elementType="HTTPArgument">
                <boolProp name="HTTPArgument.always_encode">false</boolProp>
                <stringProp name="Argument.value">{&#xd;
	&quot;query&quot;: &quot;query ($path: String, $params: Raw!) { proxy(path: $path, params: $params)}&quot;,&#xd;
	&quot;variables&quot;: {&#xd;
		&quot;path&quot;: &quot;resumeapi/apply/batchMarkInappropriate&quot;,&#xd;
		&quot;params&quot;: {&#xd;
			&quot;userSource&quot;: 1,&#xd;
			&quot;jobResumeIds&quot;: [&quot;527928733401&quot;, &quot;527925867001&quot;]&#xd;
		}&#xd;
	}&#xd;
}</stringProp>
                <stringProp name="Argument.metadata">=</stringProp>
              </elementProp>
            </collectionProp>
          </elementProp>
          <stringProp name="HTTPSampler.domain"></stringProp>
          <stringProp name="HTTPSampler.port"></stringProp>
          <stringProp name="HTTPSampler.protocol"></stringProp>
          <stringProp name="HTTPSampler.contentEncoding"></stringProp>
          <stringProp name="HTTPSampler.path"></stringProp>
          <stringProp name="HTTPSampler.method">POST</stringProp>
          <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
          <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
          <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
          <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
          <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
          <stringProp name="HTTPSampler.connect_timeout"></stringProp>
          <stringProp name="HTTPSampler.response_timeout"></stringProp>
        </HTTPSamplerProxy>
        <hashTree/>
        <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="有意向" enabled="true">
          <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
            <collectionProp name="Arguments.arguments">
              <elementProp name="" elementType="HTTPArgument">
                <boolProp name="HTTPArgument.always_encode">false</boolProp>
                <stringProp name="Argument.value">{&#xd;
	&quot;query&quot;: &quot;query ($path: String, $params: Raw!) { proxy(path: $path, params: $params)}&quot;,&#xd;
	&quot;variables&quot;: {&#xd;
		&quot;path&quot;: &quot;bapp/resume/resumelistbykey&quot;,&#xd;
		&quot;params&quot;: {&#xd;
			&quot;jobNo&quot;: &quot;&quot;,&#xd;
			&quot;rowsCount&quot;: 20,&#xd;
			&quot;startNum&quot;: 0,&#xd;
			&quot;follow&quot;: false,&#xd;
			&quot;orderFlag&quot;: &quot;commu&quot;,&#xd;
			&quot;resumeSource&quot;: &quot;-1&quot;,&#xd;
			&quot;countFlag&quot;: 1,&#xd;
			&quot;candidateStatus&quot;: &quot;commu&quot;&#xd;
		}&#xd;
	}&#xd;
}</stringProp>
                <stringProp name="Argument.metadata">=</stringProp>
              </elementProp>
            </collectionProp>
          </elementProp>
          <stringProp name="HTTPSampler.domain"></stringProp>
          <stringProp name="HTTPSampler.port"></stringProp>
          <stringProp name="HTTPSampler.protocol"></stringProp>
          <stringProp name="HTTPSampler.contentEncoding"></stringProp>
          <stringProp name="HTTPSampler.path"></stringProp>
          <stringProp name="HTTPSampler.method">POST</stringProp>
          <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
          <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
          <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
          <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
          <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
          <stringProp name="HTTPSampler.connect_timeout"></stringProp>
          <stringProp name="HTTPSampler.response_timeout"></stringProp>
        </HTTPSamplerProxy>
        <hashTree/>
        <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="发面邀" enabled="true">
          <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
            <collectionProp name="Arguments.arguments">
              <elementProp name="" elementType="HTTPArgument">
                <boolProp name="HTTPArgument.always_encode">false</boolProp>
                <stringProp name="Argument.value">{&#xd;
	&quot;query&quot;: &quot;query ($path: String, $params: Raw!) { proxy(path: $path, params: $params)}&quot;,&#xd;
	&quot;variables&quot;: {&#xd;
		&quot;path&quot;: &quot;bapp/resume/resumelistbykey&quot;,&#xd;
		&quot;params&quot;: {&#xd;
			&quot;jobNo&quot;: &quot;&quot;,&#xd;
			&quot;rowsCount&quot;: 20,&#xd;
			&quot;startNum&quot;: 0,&#xd;
			&quot;follow&quot;: false,&#xd;
			&quot;orderFlag&quot;: &quot;interview&quot;,&#xd;
			&quot;resumeSource&quot;: &quot;-1&quot;,&#xd;
			&quot;countFlag&quot;: 1,&#xd;
			&quot;candidateStatus&quot;: &quot;interview&quot;&#xd;
		}&#xd;
	}&#xd;
}</stringProp>
                <stringProp name="Argument.metadata">=</stringProp>
              </elementProp>
            </collectionProp>
          </elementProp>
          <stringProp name="HTTPSampler.domain"></stringProp>
          <stringProp name="HTTPSampler.port"></stringProp>
          <stringProp name="HTTPSampler.protocol"></stringProp>
          <stringProp name="HTTPSampler.contentEncoding"></stringProp>
          <stringProp name="HTTPSampler.path"></stringProp>
          <stringProp name="HTTPSampler.method">POST</stringProp>
          <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
          <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
          <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
          <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
          <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
          <stringProp name="HTTPSampler.connect_timeout"></stringProp>
          <stringProp name="HTTPSampler.response_timeout"></stringProp>
        </HTTPSamplerProxy>
        <hashTree/>
        <HTTPSamplerProxy guiclass="HttpTestSampleGui" testclass="HTTPSamplerProxy" testname="不合适" enabled="true">
          <boolProp name="HTTPSampler.postBodyRaw">true</boolProp>
          <elementProp name="HTTPsampler.Arguments" elementType="Arguments">
            <collectionProp name="Arguments.arguments">
              <elementProp name="" elementType="HTTPArgument">
                <boolProp name="HTTPArgument.always_encode">false</boolProp>
                <stringProp name="Argument.value">{&#xd;
	&quot;query&quot;: &quot;query ($path: String, $params: Raw!) { proxy(path: $path, params: $params)}&quot;,&#xd;
	&quot;variables&quot;: {&#xd;
		&quot;path&quot;: &quot;bapp/resume/resumelistbykey&quot;,&#xd;
		&quot;params&quot;: {&#xd;
			&quot;jobNo&quot;: &quot;&quot;,&#xd;
			&quot;rowsCount&quot;: 20,&#xd;
			&quot;startNum&quot;: 0,&#xd;
			&quot;follow&quot;: false,&#xd;
			&quot;orderFlag&quot;: &quot;noSuit&quot;,&#xd;
			&quot;resumeSource&quot;: &quot;-1&quot;,&#xd;
			&quot;countFlag&quot;: 1,&#xd;
			&quot;edu&quot;: &quot;&quot;,&#xd;
			&quot;workYears&quot;: &quot;&quot;,&#xd;
			&quot;desiredSlary&quot;: &quot;&quot;,&#xd;
			&quot;newDesiredIndustry&quot;: &quot;&quot;,&#xd;
			&quot;tagLabelIds&quot;: &quot;&quot;,&#xd;
			&quot;interviewStatus&quot;: &quot;&quot;,&#xd;
			&quot;candidateStatus&quot;: &quot;noSuit&quot;&#xd;
		}&#xd;
	}&#xd;
}</stringProp>
                <stringProp name="Argument.metadata">=</stringProp>
              </elementProp>
            </collectionProp>
          </elementProp>
          <stringProp name="HTTPSampler.domain"></stringProp>
          <stringProp name="HTTPSampler.port"></stringProp>
          <stringProp name="HTTPSampler.protocol"></stringProp>
          <stringProp name="HTTPSampler.contentEncoding"></stringProp>
          <stringProp name="HTTPSampler.path"></stringProp>
          <stringProp name="HTTPSampler.method">POST</stringProp>
          <boolProp name="HTTPSampler.follow_redirects">true</boolProp>
          <boolProp name="HTTPSampler.auto_redirects">false</boolProp>
          <boolProp name="HTTPSampler.use_keepalive">true</boolProp>
          <boolProp name="HTTPSampler.DO_MULTIPART_POST">false</boolProp>
          <stringProp name="HTTPSampler.embedded_url_re"></stringProp>
          <stringProp name="HTTPSampler.connect_timeout"></stringProp>
          <stringProp name="HTTPSampler.response_timeout"></stringProp>
        </HTTPSamplerProxy>
        <hashTree/>
        <ResultCollector guiclass="ViewResultsFullVisualizer" testclass="ResultCollector" testname="察看结果树" enabled="true">
          <boolProp name="ResultCollector.error_logging">false</boolProp>
          <objProp>
            <name>saveConfig</name>
            <value class="SampleSaveConfiguration">
              <time>true</time>
              <latency>true</latency>
              <timestamp>true</timestamp>
              <success>true</success>
              <label>true</label>
              <code>true</code>
              <message>true</message>
              <threadName>true</threadName>
              <dataType>true</dataType>
              <encoding>true</encoding>
              <assertions>true</assertions>
              <subresults>true</subresults>
              <responseData>true</responseData>
              <samplerData>true</samplerData>
              <xml>true</xml>
              <fieldNames>true</fieldNames>
              <responseHeaders>true</responseHeaders>
              <requestHeaders>true</requestHeaders>
              <responseDataOnError>true</responseDataOnError>
              <saveAssertionResultsFailureMessage>true</saveAssertionResultsFailureMessage>
              <assertionsResultsToSave>2</assertionsResultsToSave>
              <bytes>true</bytes>
              <sentBytes>true</sentBytes>
              <url>true</url>
              <fileName>true</fileName>
              <hostname>true</hostname>
              <threadCounts>true</threadCounts>
              <sampleCount>true</sampleCount>
              <idleTime>true</idleTime>
              <connectTime>true</connectTime>
            </value>
          </objProp>
          <stringProp name="filename"></stringProp>
        </ResultCollector>
        <hashTree/>
      </hashTree>
    </hashTree>
    <WorkBench guiclass="WorkBenchGui" testclass="WorkBench" testname="工作台" enabled="true">
      <boolProp name="WorkBench.save">true</boolProp>
    </WorkBench>
    <hashTree/>
  </hashTree>
</jmeterTestPlan>
