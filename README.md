# 支持 start stop restart reload 4种信号
    pRuntime.DaemonInit()
    
    //程序stop时的处理方法
    go pRuntime.HandleEndSignal(func() {
		log.Println("END.....")
	})
	
	//程序reload的处理方法 可再次方法中重新载入配置文件
    go pRuntime.HandleReloadSignal(func() {
        log.Println("Reload....")
    })
