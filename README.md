Actuator

Endpoint ID   Description
 auditevents 显示应用暴露的审计事件 (比如认证进入、订单失败) 
info 显示应用的基本信息
 health 显示应用的健康状态
 metrics 显示应用多样的度量信息 
loggers 显示和修改配置的loggers
 logfile 返回log file中的内容(如果logging.file或者logging.path被设置) 
httptrace 显示HTTP足迹，最近100个HTTP request/repsponse 
env 显示当前的环境特性 
flyway 显示数据库迁移路径的详细信息 
liquidbase 显示Liquibase 数据库迁移的纤细信息 
shutdown 让你逐步关闭应用 
mappings 显示所有的@RequestMapping路径
 scheduledtasks 显示应用中的调度任务
 threaddump 执行一个线程dump 
heapdump 返回一个GZip压缩的JVM堆dump



http://localhost:88/monitor/mappings

{
	"/webjars/**": {
		"bean": "resourceHandlerMapping"
	},
	"/**": {
		"bean": "resourceHandlerMapping"
	},
	"/**/favicon.ico": {
		"bean": "faviconHandlerMapping"
	},
	"{[/]}": {
		"bean": "requestMappingHandlerMapping",
		"method": "java.lang.String com.springboot.demo.DemoApplication.index()"
	},
	"{[/error]}": {
		"bean": "requestMappingHandlerMapping",
		"method": "public org.springframework.http.ResponseEntity<java.util.Map<java.lang.String, java.lang.Object>> org.springframework.boot.autoconfigure.web.BasicErrorController.error(javax.servlet.http.HttpServletRequest)"
	},
	"{[/error],produces=[text/html]}": {
		"bean": "requestMappingHandlerMapping",
		"method": "public org.springframework.web.servlet.ModelAndView org.springframework.boot.autoconfigure.web.BasicErrorController.errorHtml(javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse)"
	},
	"{[/monitor/auditevents || /monitor/auditevents.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public org.springframework.http.ResponseEntity<?> org.springframework.boot.actuate.endpoint.mvc.AuditEventsMvcEndpoint.findByPrincipalAndAfterAndType(java.lang.String,java.util.Date,java.lang.String)"
	},
	"{[/monitor/trace || /monitor/trace.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/health || /monitor/health.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.HealthMvcEndpoint.invoke(javax.servlet.http.HttpServletRequest,java.security.Principal)"
	},
	"{[/monitor/heapdump || /monitor/heapdump.json],methods=[GET],produces=[application/octet-stream]}": {
		"bean": "endpointHandlerMapping",
		"method": "public void org.springframework.boot.actuate.endpoint.mvc.HeapdumpMvcEndpoint.invoke(boolean,javax.servlet.http.HttpServletRequest,javax.servlet.http.HttpServletResponse) throws java.io.IOException,javax.servlet.ServletException"
	},
	"{[/monitor/loggers/{name:.*}],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.LoggersMvcEndpoint.get(java.lang.String)"
	},
	"{[/monitor/loggers/{name:.*}],methods=[POST],consumes=[application/vnd.spring-boot.actuator.v1+json || application/json],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.LoggersMvcEndpoint.set(java.lang.String,java.util.Map<java.lang.String, java.lang.String>)"
	},
	"{[/monitor/loggers || /monitor/loggers.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/configprops || /monitor/configprops.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/instances || /monitor/instances.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/mappings || /monitor/mappings.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/env/{name:.*}],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EnvironmentMvcEndpoint.value(java.lang.String)"
	},
	"{[/monitor/env || /monitor/env.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/info || /monitor/info.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/dump || /monitor/dump.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/shutdown || /monitor/shutdown.json],methods=[POST],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.ShutdownMvcEndpoint.invoke()"
	},
	"{[/monitor/autoconfig || /monitor/autoconfig.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	},
	"{[/monitor/metrics/{name:.*}],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.MetricsMvcEndpoint.value(java.lang.String)"
	},
	"{[/monitor/metrics || /monitor/metrics.json],methods=[GET],produces=[application/vnd.spring-boot.actuator.v1+json || application/json]}": {
		"bean": "endpointHandlerMapping",
		"method": "public java.lang.Object org.springframework.boot.actuate.endpoint.mvc.EndpointMvcAdapter.invoke()"
	}
}
http://localhost:88/monitor/configprops

http://localhost:88/monitor/instances/

http://localhost:88/monitor/auditevents
http://localhost:88/monitor/trace
[{
	"timestamp": 1544087564218,
	"info": {
		"method": "GET",
		"path": "/monitor/mappings",
		"headers": {
			"request": {
				"host": "localhost:88",
				"connection": "keep-alive",
				"cache-control": "max-age=0",
				"upgrade-insecure-requests": "1",
				"user-agent": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
				"accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8",
				"accept-encoding": "gzip, deflate, br",
				"accept-language": "zh-CN,zh;q=0.9,en;q=0.8"
			},
			"response": {
				"X-Application-Context": "application:88",
				"Content-Type": "application/vnd.spring-boot.actuator.v1+json;charset=UTF-8",
				"Transfer-Encoding": "chunked",
				"Date": "Thu, 06 Dec 2018 09:12:44 GMT",
				"status": "200"
			}
		},
		"timeTaken": "4"
	}
}, {
	"timestamp": 1544087549264,
	"info": {
		"method": "GET",
		"path": "//monitor/loggers",
		"headers": {
			"request": {
				"host": "localhost:88",
				"connection": "keep-alive",
				"cache-control": "max-age=0",
				"upgrade-insecure-requests": "1",
				"user-agent": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
				"accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8",
				"accept-encoding": "gzip, deflate, br",
				"accept-language": "zh-CN,zh;q=0.9,en;q=0.8"
			},
			"response": {
				"X-Application-Context": "application:88",
				"Content-Type": "application/vnd.spring-boot.actuator.v1+json;charset=UTF-8",
				"Transfer-Encoding": "chunked",
				"Date": "Thu, 06 Dec 2018 09:12:29 GMT",
				"status": "200"
			}
		},
		"timeTaken": "24"
	}
}, {
	"timestamp": 1544086618141,
	"info": {
		"method": "GET",
		"path": "/monitor/configprops",
		"headers": {
			"request": {
				"host": "localhost:88",
				"connection": "keep-alive",
				"cache-control": "max-age=0",
				"upgrade-insecure-requests": "1",
				"user-agent": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
				"accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8",
				"accept-encoding": "gzip, deflate, br",
				"accept-language": "zh-CN,zh;q=0.9,en;q=0.8"
			},
			"response": {
				"X-Application-Context": "application:88",
				"Content-Type": "application/vnd.spring-boot.actuator.v1+json;charset=UTF-8",
				"Transfer-Encoding": "chunked",
				"Date": "Thu, 06 Dec 2018 08:56:58 GMT",
				"status": "200"
			}
		},
		"timeTaken": "92"
	}
}, {
	"timestamp": 1544086611297,
	"info": {
		"method": "GET",
		"path": "/monitor/instances/",
		"headers": {
			"request": {
				"host": "localhost:88",
				"connection": "keep-alive",
				"cache-control": "max-age=0",
				"upgrade-insecure-requests": "1",
				"user-agent": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
				"accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8",
				"accept-encoding": "gzip, deflate, br",
				"accept-language": "zh-CN,zh;q=0.9,en;q=0.8"
			},
			"response": {
				"X-Application-Context": "application:88",
				"Content-Type": "application/vnd.spring-boot.actuator.v1+json;charset=UTF-8",
				"Transfer-Encoding": "chunked",
				"Date": "Thu, 06 Dec 2018 08:56:51 GMT",
				"status": "200"
			}
		},
		"timeTaken": "185"
	}
}, {
	"timestamp": 1544086580911,
	"info": {
		"method": "GET",
		"path": "/monitor/dump",
		"headers": {
			"request": {
				"host": "localhost:88",
				"connection": "keep-alive",
				"cache-control": "max-age=0",
				"upgrade-insecure-requests": "1",
				"user-agent": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
				"accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8",
				"accept-encoding": "gzip, deflate, br",
				"accept-language": "zh-CN,zh;q=0.9,en;q=0.8"
			},
			"response": {
				"X-Application-Context": "application:88",
				"Content-Type": "application/vnd.spring-boot.actuator.v1+json;charset=UTF-8",
				"Transfer-Encoding": "chunked",
				"Date": "Thu, 06 Dec 2018 08:56:20 GMT",
				"status": "200"
			}
		},
		"timeTaken": "161"
	}
}, {
	"timestamp": 1544086550297,
	"info": {
		"method": "GET",
		"path": "/monitor/info",
		"headers": {
			"request": {
				"host": "localhost:88",
				"connection": "keep-alive",
				"cache-control": "max-age=0",
				"upgrade-insecure-requests": "1",
				"user-agent": "Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/70.0.3538.102 Safari/537.36",
				"accept": "text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8",
				"accept-encoding": "gzip, deflate, br",
				"accept-language": "zh-CN,zh;q=0.9,en;q=0.8"
			},
			"response": {
				"X-Application-Context": "application:88",
				"Content-Type": "application/vnd.spring-boot.actuator.v1+json;charset=UTF-8",
				"Transfer-Encoding": "chunked",
				"Date": "Thu, 06 Dec 2018 08:55:50 GMT",
				"status": "200"
			}
		},
		"timeTaken": "57"
	}
}]
http://localhost:88/monitor/health

{"status":"UP","diskSpace":{"status":"UP","total":1000068870144,"free":382773145600,"threshold":10485760}}


http://localhost:88/monitor/info
{}
展示了关于应用的一般信息，这些信息从编译文件比如META-INF/build-info.properties或者Git文件比如git.properties或者任何环境的property中获取。
http://localhost:88/monitor/dump

http://localhost/actuator/shutdown
localhost 拒绝了我们的连接请求。

http://localhost:88/monitor/loggers

