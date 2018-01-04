# jmeter_report
这是转报告用的

D:\tools\apache-jmeter-3.3\bin\jmeter.bat -n -t D:\tools\apache-jmeter-3.3\scripts\baidu.jmx -l D:\tools\apache-jmeter-3.3\results\result.jtl -j D:\tools\apache-jmeter-3.3\results\baidu.log    -Djmeter.save.saveservice.output_format=xml -Dsampleresult.default.encoding=utf-8   -Djmeter.save.saveservice.data_type=true   -Djmeter.save.saveservice.label=true   -Djmeter.save.saveservice.response_code=true   -Djmeter.save.saveservice.response_data=true   -Djmeter.save.saveservice.response_data.on_error=false   -Djmeter.save.saveservice.response_message=true   -Djmeter.save.saveservice.successful=true   -Djmeter.save.saveservice.thread_name=true   -Djmeter.save.saveservice.time=true   -Djmeter.save.saveservice.subresults=true   -Djmeter.save.saveservice.assertions=true   -Djmeter.save.saveservice.latency=true   -Djmeter.save.saveservice.connect_time=true   -Djmeter.save.saveservice.samplerData=true   -Djmeter.save.saveservice.responseHeaders=true   -Djmeter.save.saveservice.requestHeaders=true   -Djmeter.save.saveservice.encoding=true   -Djmeter.save.saveservice.bytes=true   -Djmeter.save.saveservice.url=true   -Djmeter.save.saveservice.filename=true   -Djmeter.save.saveservice.hostname=true   -Djmeter.save.saveservice.thread_counts=true   -Djmeter.save.saveservice.sample_count=true   -Djmeter.save.saveservice.idle_time=true 

D:\tools\apache-jmeter-3.3\bin\libxslt\bin\xsltproc D:\tools\apache-jmeter-3.3\bin\libxslt\bin\jmeter.results.shanhe.me.xsl  D:\tools\apache-jmeter-3.3\results\result.jtl >D:\tools\apache-jmeter-3.3\results\result.html
















d:
cd D:\test107\apache-jmeter-3.3
rem del %WORKSPACE%\%JOB_NAME%\testResult.html
del results\%JOB_NAME%.html
del results\%JOB_NAME%.jtl
bin\jmeter.bat -n -t scripts\%JOB_NAME%.jmx -l results\%JOB_NAME%.jtl -Djmeter.save.saveservice.output_format=xml -Dsampleresult.default.encoding=utf-8 -Djmeter.save.saveservice.data_type=true -Djmeter.save.saveservice.label=true -Djmeter.save.saveservice.response_code=true -Djmeter.save.saveservice.response_data=true -Djmeter.save.saveservice.response_data.on_error=false -Djmeter.save.saveservice.response_message=true -Djmeter.save.saveservice.successful=true -Djmeter.save.saveservice.thread_name=true -Djmeter.save.saveservice.time=true -Djmeter.save.saveservice.subresults=true -Djmeter.save.saveservice.assertions=true -Djmeter.save.saveservice.latency=true -Djmeter.save.saveservice.connect_time=true -Djmeter.save.saveservice.samplerData=true -Djmeter.save.saveservice.responseHeaders=true -Djmeter.save.saveservice.requestHeaders=true -Djmeter.save.saveservice.encoding=true -Djmeter.save.saveservice.bytes=true -Djmeter.save.saveservice.url=true -Djmeter.save.saveservice.filename=true -Djmeter.save.saveservice.hostname=true -Djmeter.save.saveservice.thread_counts=true -Djmeter.save.saveservice.sample_count=true -Djmeter.save.saveservice.idle_time=true





d:
cd D:\test107\apache-jmeter-3.3
bin\libxslt-1.1.26.win32\bin\xsltproc bin\libxslt-1.1.26.win32\bin\jmeter.results.shanhe.me.xsl  results\%JOB_NAME%.jtl > results\%JOB_NAME%.html
copy results\%JOB_NAME%.html %WORKSPACE%\testResult.html





d:
cd D:\test107\apache-jmeter-3.3
findstr s=\"false\" results\%JOB_NAME%.jtl 
if %ERRORLEVEL% == 0 (EXIT 1) else (EXIT 0)
