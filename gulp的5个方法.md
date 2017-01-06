###gulp的5个方法
1. task : trask('任务名'，回掉函数);
2. src : src('./*.js')
3. dest 指定文件处理后的输出路径: dest('./minjs/')
4. watch 监视 : watch('./*.js',['任务名1','任务名2']);
5. run 执行指定的任务 : run('任务名');