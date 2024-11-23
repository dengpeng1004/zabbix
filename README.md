# zabbix-win
1.编译链接
  https://www.zabbix.com/documentation/6.0/zh/manual/installation/install/win_agent 不要使用 PCRE2,PCRE就行了
2.错误处理:
   ZABBIX_RC_NUM 
       修改 报错的 resource.rc 文件,要是图省事，直接改个日期就行
   zabbix_sender_send_values 崩溃:
       common_log.c
       void	zbx_log_handle(int level, const char *fmt, ...)
       {
        	va_list args;
        
        	va_start(args, fmt);
        	if(log_func_callback) log_func_callback(level, fmt, args);
        	va_end(args);
        }
      
