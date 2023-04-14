# 支持 start stop restart reload 4种信号

# 安装
    go get -u github.com/zqjzqj/pRuntime

# 使用
    //设置pid文件位置 默认 /tmp/pRuntime.pid 可以不设置
    pRuntime.SetPidFile("xxxxx")
    pRuntime.RunDaemon(true)
    
    //程序stop时的处理方法
    end := pRuntime.HandleEndSignal(func() {
		log.Println("END.....")
	})
	
	//程序reload的处理方法 可再次方法中重新载入配置文件
    pRuntime.HandleReloadSignal(func() {
        log.Println("Reload....")
    })

    //等待方法执行完毕
    <-end
