# Other

## cgroup

> [LINUX CGROUP总结](https://www.cnblogs.com/menkeyi/p/10941843.html)
>
> [linux cgroups详细介绍](https://www.jb51.net/article/146162.htm)
>
> [Linux的Cgroup](https://blog.csdn.net/gaojy19881225/article/details/80019874)
>
> [CGroup的使用方法](https://blog.csdn.net/qq_33932782/article/details/71285764)

​		实现 cgroups 的主要目的是为不同用户层面的资源管理提供一个统一化的接口。从单个任务的资源控制到操作系统层面的虚拟化，cgroups 提供了四大功能：

* 资源限制：cgroups 可以对任务是要的资源总额进行限制。比如设定任务运行时使用的内存上限，一旦超出就发 OOM。
* 优先级分配：通过分配的 CPU 时间片数量和磁盘 IO 带宽，实际上就等同于控制了任务运行的优先级。
* 资源统计：cgoups 可以统计系统的资源使用量，比如 CPU 使用时长、内存用量等。这个功能非常适合当前云端产品按使用量计费的方式。
* 任务控制：cgroups 可以对任务执行挂起、恢复等操作。



## panic

> [linux panic机制](https://blog.csdn.net/pansaky/article/details/90440356)
> [深入 kernel panic 流程【转】](https://www.cnblogs.com/linhaostudy/p/9429511.html)

painc是什么

