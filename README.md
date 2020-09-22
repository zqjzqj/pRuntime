#暂只支持芝麻代理
    使用前添加IP白名单
    
    pRuntime.DaemonInit()
    go pRuntime.HandleEndSignal(func() {
		logsKp.PrintlnSuccess("END.....")
	})