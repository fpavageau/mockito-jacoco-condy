# Example of an incompatibility between Mockito's inline mocks and JaCoCo 0.8.4

## Prerequisites

- JDK 11

## Build

    ./gradlew build
    
The build should fail with:

    com.ekino.mockito.ATest > should_call_b() FAILED
        org.mockito.exceptions.base.MockitoException at ATest.java:25
            Caused by: org.mockito.exceptions.base.MockitoException at ATest.java:25
                Caused by: java.lang.IllegalStateException at ATest.java:25
                    Caused by: java.lang.UnsupportedOperationException at ATest.java:25
    
    1 test completed, 1 failed
    
The complete stacktrace available in the logs is:

    Mockito cannot mock this class: class com.ekino.mockito.B.
    
    If you're not sure why you're getting this error, please report to the mailing list.
    
    
    Java               : 11
    JVM vendor name    : AdoptOpenJDK
    JVM vendor version : 11.0.3+7
    JVM name           : OpenJDK 64-Bit Server VM
    JVM version        : 11.0.3+7
    JVM info           : mixed mode
    OS name            : Mac OS X
    OS version         : 10.14.5
    
    
    You are seeing this disclaimer because Mockito is configured to create inlined mocks.
    You can learn about inline mocks and their limitations under item #39 of the Mockito class javadoc.
    
    Underlying exception : org.mockito.exceptions.base.MockitoException: Could not modify all classes [class java.lang.Object, class com.ekino.mockito.B]
    org.mockito.exceptions.base.MockitoException: 
    Mockito cannot mock this class: class com.ekino.mockito.B.
    
    If you're not sure why you're getting this error, please report to the mailing list.
    
    
    Java               : 11
    JVM vendor name    : AdoptOpenJDK
    JVM vendor version : 11.0.3+7
    JVM name           : OpenJDK 64-Bit Server VM
    JVM version        : 11.0.3+7
    JVM info           : mixed mode
    OS name            : Mac OS X
    OS version         : 10.14.5
    
    
    You are seeing this disclaimer because Mockito is configured to create inlined mocks.
    You can learn about inline mocks and their limitations under item #39 of the Mockito class javadoc.
    
    Underlying exception : org.mockito.exceptions.base.MockitoException: Could not modify all classes [class java.lang.Object, class com.ekino.mockito.B]
    	at com.ekino.mockito.ATest.should_call_b(ATest.java:10)
    	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
    	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
    	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
    	at java.base/java.lang.reflect.Method.invoke(Method.java:566)
    	at org.junit.platform.commons.util.ReflectionUtils.invokeMethod(ReflectionUtils.java:628)
    	at org.junit.jupiter.engine.execution.ExecutableInvoker.invoke(ExecutableInvoker.java:117)
    	at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.lambda$invokeTestMethod$7(TestMethodTestDescriptor.java:184)
    	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
    	at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.invokeTestMethod(TestMethodTestDescriptor.java:180)
    	at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.execute(TestMethodTestDescriptor.java:127)
    	at org.junit.jupiter.engine.descriptor.TestMethodTestDescriptor.execute(TestMethodTestDescriptor.java:68)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$5(NodeTestTask.java:135)
    	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$7(NodeTestTask.java:125)
    	at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:135)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:123)
    	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:122)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:80)
    	at java.base/java.util.ArrayList.forEach(ArrayList.java:1540)
    	at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:38)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$5(NodeTestTask.java:139)
    	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$7(NodeTestTask.java:125)
    	at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:135)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:123)
    	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:122)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:80)
    	at java.base/java.util.ArrayList.forEach(ArrayList.java:1540)
    	at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.invokeAll(SameThreadHierarchicalTestExecutorService.java:38)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$5(NodeTestTask.java:139)
    	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$7(NodeTestTask.java:125)
    	at org.junit.platform.engine.support.hierarchical.Node.around(Node.java:135)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.lambda$executeRecursively$8(NodeTestTask.java:123)
    	at org.junit.platform.engine.support.hierarchical.ThrowableCollector.execute(ThrowableCollector.java:73)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.executeRecursively(NodeTestTask.java:122)
    	at org.junit.platform.engine.support.hierarchical.NodeTestTask.execute(NodeTestTask.java:80)
    	at org.junit.platform.engine.support.hierarchical.SameThreadHierarchicalTestExecutorService.submit(SameThreadHierarchicalTestExecutorService.java:32)
    	at org.junit.platform.engine.support.hierarchical.HierarchicalTestExecutor.execute(HierarchicalTestExecutor.java:57)
    	at org.junit.platform.engine.support.hierarchical.HierarchicalTestEngine.execute(HierarchicalTestEngine.java:51)
    	at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:220)
    	at org.junit.platform.launcher.core.DefaultLauncher.lambda$execute$6(DefaultLauncher.java:188)
    	at org.junit.platform.launcher.core.DefaultLauncher.withInterceptedStreams(DefaultLauncher.java:202)
    	at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:181)
    	at org.junit.platform.launcher.core.DefaultLauncher.execute(DefaultLauncher.java:128)
    	at org.gradle.api.internal.tasks.testing.junitplatform.JUnitPlatformTestClassProcessor$CollectAllTestClassesExecutor.processAllTestClasses(JUnitPlatformTestClassProcessor.java:102)
    	at org.gradle.api.internal.tasks.testing.junitplatform.JUnitPlatformTestClassProcessor$CollectAllTestClassesExecutor.access$000(JUnitPlatformTestClassProcessor.java:82)
    	at org.gradle.api.internal.tasks.testing.junitplatform.JUnitPlatformTestClassProcessor.stop(JUnitPlatformTestClassProcessor.java:78)
    	at org.gradle.api.internal.tasks.testing.SuiteTestClassProcessor.stop(SuiteTestClassProcessor.java:61)
    	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
    	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
    	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
    	at java.base/java.lang.reflect.Method.invoke(Method.java:566)
    	at org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
    	at org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
    	at org.gradle.internal.dispatch.ContextClassLoaderDispatch.dispatch(ContextClassLoaderDispatch.java:32)
    	at org.gradle.internal.dispatch.ProxyDispatchAdapter$DispatchingInvocationHandler.invoke(ProxyDispatchAdapter.java:93)
    	at com.sun.proxy.$Proxy5.stop(Unknown Source)
    	at org.gradle.api.internal.tasks.testing.worker.TestWorker.stop(TestWorker.java:132)
    	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
    	at java.base/jdk.internal.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
    	at java.base/jdk.internal.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
    	at java.base/java.lang.reflect.Method.invoke(Method.java:566)
    	at org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:35)
    	at org.gradle.internal.dispatch.ReflectionDispatch.dispatch(ReflectionDispatch.java:24)
    	at org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:175)
    	at org.gradle.internal.remote.internal.hub.MessageHubBackedObjectConnection$DispatchWrapper.dispatch(MessageHubBackedObjectConnection.java:157)
    	at org.gradle.internal.remote.internal.hub.MessageHub$Handler.run(MessageHub.java:404)
    	at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
    	at org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
    	at java.base/java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1128)
    	at java.base/java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:628)
    	at org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
    	at java.base/java.lang.Thread.run(Thread.java:834)
    Caused by: org.mockito.exceptions.base.MockitoException: Could not modify all classes [class java.lang.Object, class com.ekino.mockito.B]
    	at net.bytebuddy.TypeCache.findOrInsert(TypeCache.java:152)
    	at net.bytebuddy.TypeCache$WithInlineExpunction.findOrInsert(TypeCache.java:365)
    	at net.bytebuddy.TypeCache.findOrInsert(TypeCache.java:174)
    	at net.bytebuddy.TypeCache$WithInlineExpunction.findOrInsert(TypeCache.java:376)
    	... 77 more
    Caused by: java.lang.IllegalStateException: 
    Byte Buddy could not instrument all classes within the mock's type hierarchy
    
    This problem should never occur for javac-compiled classes. This problem has been observed for classes that are:
     - Compiled by older versions of scalac
     - Classes that are part of the Android distribution
    	at org.mockito.internal.creation.bytebuddy.InlineBytecodeGenerator.triggerRetransformation(InlineBytecodeGenerator.java:177)
    	at org.mockito.internal.creation.bytebuddy.InlineBytecodeGenerator.mockClass(InlineBytecodeGenerator.java:153)
    	at org.mockito.internal.creation.bytebuddy.TypeCachingBytecodeGenerator$1.call(TypeCachingBytecodeGenerator.java:37)
    	at org.mockito.internal.creation.bytebuddy.TypeCachingBytecodeGenerator$1.call(TypeCachingBytecodeGenerator.java:34)
    	at net.bytebuddy.TypeCache.findOrInsert(TypeCache.java:152)
    	at net.bytebuddy.TypeCache$WithInlineExpunction.findOrInsert(TypeCache.java:365)
    	at net.bytebuddy.TypeCache.findOrInsert(TypeCache.java:174)
    	at net.bytebuddy.TypeCache$WithInlineExpunction.findOrInsert(TypeCache.java:376)
    	at org.mockito.internal.creation.bytebuddy.TypeCachingBytecodeGenerator.mockClass(TypeCachingBytecodeGenerator.java:32)
    	at org.mockito.internal.creation.bytebuddy.InlineByteBuddyMockMaker.createMockType(InlineByteBuddyMockMaker.java:197)
    	at org.mockito.internal.creation.bytebuddy.InlineByteBuddyMockMaker.createMock(InlineByteBuddyMockMaker.java:178)
    	at org.mockito.internal.util.MockUtil.createMock(MockUtil.java:35)
    	at org.mockito.internal.MockitoCore.mock(MockitoCore.java:62)
    	at org.mockito.Mockito.mock(Mockito.java:1907)
    	at org.mockito.Mockito.mock(Mockito.java:1816)
    	... 77 more
    Caused by: java.lang.UnsupportedOperationException: This feature requires ASM7
    	at net.bytebuddy.jar.asm.MethodVisitor.visitLdcInsn(MethodVisitor.java:542)
    	at net.bytebuddy.jar.asm.ClassReader.readCode(ClassReader.java:2181)
    	at net.bytebuddy.jar.asm.ClassReader.readMethod(ClassReader.java:1275)
    	at net.bytebuddy.jar.asm.ClassReader.accept(ClassReader.java:679)
    	at net.bytebuddy.jar.asm.ClassReader.accept(ClassReader.java:391)
    	at net.bytebuddy.dynamic.scaffold.TypeWriter$Default$ForInlining.create(TypeWriter.java:3393)
    	at net.bytebuddy.dynamic.scaffold.TypeWriter$Default.make(TypeWriter.java:1930)
    	at net.bytebuddy.dynamic.scaffold.inline.RedefinitionDynamicTypeBuilder.make(RedefinitionDynamicTypeBuilder.java:217)
    	at net.bytebuddy.dynamic.scaffold.inline.AbstractInliningDynamicTypeBuilder.make(AbstractInliningDynamicTypeBuilder.java:120)
    	at net.bytebuddy.dynamic.DynamicType$Builder$AbstractBase.make(DynamicType.java:3396)
    	at org.mockito.internal.creation.bytebuddy.InlineBytecodeGenerator.transform(InlineBytecodeGenerator.java:254)
    	at java.instrument/java.lang.instrument.ClassFileTransformer.transform(ClassFileTransformer.java:246)
    	at java.instrument/sun.instrument.TransformerManager.transform(TransformerManager.java:188)
    	at java.instrument/sun.instrument.InstrumentationImpl.transform(InstrumentationImpl.java:563)
    	at java.instrument/sun.instrument.InstrumentationImpl.retransformClasses0(Native Method)
    	at java.instrument/sun.instrument.InstrumentationImpl.retransformClasses(InstrumentationImpl.java:167)
    	at org.mockito.internal.creation.bytebuddy.InlineBytecodeGenerator.triggerRetransformation(InlineBytecodeGenerator.java:174)
    	... 91 more


The same code runs with JaCoCo 0.8.3 (by modifying `build.gradle`).

## Issue

https://github.com/mockito/mockito/issues/1717
    
----

Licensed under the Apache License, Version 2.0
