在交互环境中 (jupyter notebook), 使用await代替asyncio.run.

一般使用async def把函数定义成协程，使用await获得结果。

使用set_result() 方法为 future 对象设置一个值，一旦设置了这个值，这个future就未来完成了，done() 方法将返回 True.

asyncio.create_task创建任务，接收一个协程；
asyncio.gather() 函数有两个参数：
- aws 是一系列可等待的对象。如果 aws 中的任何对象是协程，则 asyncio.gather() 函数会自动将其调度为任务。
- 默认情况下， return_exceptions 为 False 。如果可等待对象中发生异常，则会立即传播到等待 asyncio.gather() 的任务。其他等待项目将继续运行并且不会被取消。
await asyncio.gather(*tasks)，异步完成所有tasks并返回所有结果到一个list里面
