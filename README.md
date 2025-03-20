# Decoroutinator failing example

`./gradlew run` to run the example.

Main function fails with exception:

```
Exception in thread "main" java.lang.VerifyError: Bad type on operand stack
Exception Details:
  Location:
    org/example/MainKt$main$1$invokeSuspend$$inlined$transform$1.invokeSuspend(Ldev/reformator/stacktracedecoroutinator/provider/DecoroutinatorSpec;Ljava/lang/Object;)Ljava/lang/Object; @5: getfield
  Reason:
    Type 'dev/reformator/stacktracedecoroutinator/provider/DecoroutinatorSpec' (current frame, stack[0]) is not assignable to 'org/example/MainKt$main$1$invokeSuspend$$inlined$transform$1'
  Current Frame:
    bci: @5
    flags: { }
    locals: { 'dev/reformator/stacktracedecoroutinator/provider/DecoroutinatorSpec', 'java/lang/Object' }
    stack: { 'dev/reformator/stacktracedecoroutinator/provider/DecoroutinatorSpec' }
  Bytecode:
    0000000: b800 3c57 2ab4 003e aa00 0000 0000 00b3
    0000010: 0000 0000 0000 0000 0000 0014 2bb8 0044
    0000020: 2ab9 007f 0100 3d2a b900 8301 009a 0049
    0000030: 2ab9 0087 0100 2ab9 008b 0100 2b1c ab00
    0000040: 0000 0026 0000 0002 0000 0000 0000 001a
    0000050: 0000 0024 0000 0020 b600 90a7 000e b600
    0000060: 90a7 0008 5857 a700 3d4c 2b2a b900 9301
    0000070: 00a6 0005 2bb0 2a2b 1cab 0000 0000 0029
    0000080: 0000 0002 0000 0000 0000 001b 0000 0024
    0000090: 0000 0023 b900 9602 00a7 0008 b900 9602
    00000a0: 00b0 58bb 0098 59bb 009a 5912 9cb7 009d
    00000b0: 1cb6 00a1 b600 a5b7 00a6 bfbb 005d 5912
    00000c0: 5fb7 0062 bf                           
  Stackmap Table:
    same_frame(@28)
    full_frame(@88,{Object[#123],Object[#103],Integer},{Object[#141],Object[#123],Object[#103]})
    full_frame(@94,{Object[#123],Object[#103],Integer},{Object[#141],Object[#123],Object[#103]})
    full_frame(@100,{Object[#123],Object[#103],Integer},{Object[#141],Object[#123],Object[#103]})
    same_locals_1_stack_item_frame(@105,Object[#103])
    same_frame(@118)
    full_frame(@148,{Object[#123],Object[#103],Integer},{Object[#123],Object[#103]})
    full_frame(@156,{Object[#123],Object[#103],Integer},{Object[#123],Object[#103]})
    same_locals_1_stack_item_frame(@161,Object[#103])
    full_frame(@162,{Object[#123],Object[#103],Integer},{Object[#123],Object[#103]})
    same_frame(@163)
    chop_frame(@187,1)

	at org.example.MainKt$main$1.invokeSuspend(Main.kt:16)
	at dev.reformator.stacktracedecoroutinator.common.internal.AwakenerKt.awake(awakener.kt:118)
	at dev.reformator.stacktracedecoroutinator.common.internal.Provider.awakeBaseContinuation(provider-impl.kt:43)
	at dev.reformator.stacktracedecoroutinator.provider.DecoroutinatorProviderApiKt.awakeBaseContinuation(provider-api.kt:47)
	at kotlin.coroutines.jvm.internal.BaseContinuationImpl.resumeWith(ContinuationImpl.kt)
	at kotlinx.coroutines.DispatchedTask.run(DispatchedTask.kt:100)
	at kotlinx.coroutines.EventLoopImplBase.processNextEvent(EventLoop.common.kt:263)
	at kotlinx.coroutines.BlockingCoroutine.joinBlocking(Builders.kt:95)
	at kotlinx.coroutines.BuildersKt__BuildersKt.runBlocking(Builders.kt:69)
	at kotlinx.coroutines.BuildersKt.runBlocking(Unknown Source)
	at kotlinx.coroutines.BuildersKt__BuildersKt.runBlocking$default(Builders.kt:47)
	at kotlinx.coroutines.BuildersKt.runBlocking$default(Unknown Source)
	at org.example.MainKt.main(Main.kt:9)
	at org.example.MainKt.main(Main.kt)
```
