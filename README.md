# RAGAS-eval-with-ollama
【必过】使用ollama部署的语言模型和嵌入模型进行ragas评估。

ragas是比较知名的rag评估工具。但是在模型对接方面存在很大局限。官方文档中显示，对OpenAI、Amazon Bedrock、Azure OpenAI提供了较好的支持。而我们通常是使用本地模型搭建的RAG流程，属于Others那就只能自定义了。但是具体怎样自定义的，则基本没提。网上可以找到一些自定义模型的代码，但我拿来执行频繁报错无法解决。获取有些人能成功，但我觉得这个方法磕磕绊绊，难以实施。

后来又看到它还提供了[llamaIndex集成](https://docs.ragas.io/en/latest/howtos/integrations/_llamaindex/)，然而一路进行到搭建QueryEngin进行对话是成功的。一进入评估环节，又是各种报错无法解决。追踪错误进入ragas源码，各种回调和跳转，完全找不到它是怎样调用两种模型的哪个函数的，根本无法分析解决。这条路也是走不通的。

无可奈何之下各种搜索成功案例，几乎没有任何收获。最后绝境逢生，原来openai接口不是只能用openai官方API，而是只要兼容openai风格的API服务就可以。不过也很麻烦，因为大模型部署工具虽然很多，但是适配模型选择广泛，直接提供openai风格API的并不多。像ollama也只是部分兼容。不过拿来对接ragas还不算太难。算是可行的途径。

具体参考另一文档。
