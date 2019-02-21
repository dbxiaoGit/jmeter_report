# jmeter_report
这是转报告用的

D:\tools\apache-jmeter-3.3\bin\jmeter.bat -n -t D:\tools\apache-jmeter-3.3\scripts\baidu.jmx -l D:\tools\apache-jmeter-3.3\results\result.jtl -j D:\tools\apache-jmeter-3.3\results\baidu.log    -Djmeter.save.saveservice.output_format=xml -Dsampleresult.default.encoding=utf-8   -Djmeter.save.saveservice.data_type=true   -Djmeter.save.saveservice.label=true   -Djmeter.save.saveservice.response_code=true   -Djmeter.save.saveservice.response_data=true   -Djmeter.save.saveservice.response_data.on_error=false   -Djmeter.save.saveservice.response_message=true   -Djmeter.save.saveservice.successful=true   -Djmeter.save.saveservice.thread_name=true   -Djmeter.save.saveservice.time=true   -Djmeter.save.saveservice.subresults=true   -Djmeter.save.saveservice.assertions=true   -Djmeter.save.saveservice.latency=true   -Djmeter.save.saveservice.connect_time=true   -Djmeter.save.saveservice.samplerData=true   -Djmeter.save.saveservice.responseHeaders=true   -Djmeter.save.saveservice.requestHeaders=true   -Djmeter.save.saveservice.encoding=true   -Djmeter.save.saveservice.bytes=true   -Djmeter.save.saveservice.url=true   -Djmeter.save.saveservice.filename=true   -Djmeter.save.saveservice.hostname=true   -Djmeter.save.saveservice.thread_counts=true   -Djmeter.save.saveservice.sample_count=true   -Djmeter.save.saveservice.idle_time=true 

D:\tools\apache-jmeter-3.3\bin\libxslt\bin\xsltproc D:\tools\apache-jmeter-3.3\bin\libxslt\bin\jmeter.results.shanhe.me.xsl  D:\tools\apache-jmeter-3.3\results\result.jtl >D:\tools\apache-jmeter-3.3\results\result.html



安装startup-trigger-plugin和Groovy插件

>构建触发器
  >>Build when job nodes start

>Execute system Groovy script
  >>Groovy command
    >>>System.setProperty("hudson.model.DirectoryBrowserSupport.CSP", "")

javaw -jar -Dhudson.model.DirectoryBrowserSupport.CSP= jenkins.war --httpPort=8001
***
export JAVA_HOME="/home/xxx/jdk1.8.0_172"

export PATH＝$JAVA_HOME/bin:$PATH
***
***
* 构建-Invoke Ant-
* build file = build.xml
* Properties =
jmeter.home=/home/oracle/tools/apache-jmeter-5.0

report.title=${JOB_NAME}

show-data=y

test=${JOB_NAME}

* 构建后操作
归档成品-用于存档的文件	= *.html
* Editable Email Notification - Default Content	 = 
${BUILD_URL}artifact/${JOB_NAME}.html 

***
export GREP_OPTIONS='--color=auto' GREP_COLOR='1;33'
***
grep -E "<failure>true</failure>|<error>true</error>" ${WORKSPACE}/${JOB_NAME}.jtl
if [ $? -eq 0 ]; then
    echo "fail"
    exit 1
else
    echo "success"
    exit 0
fi


