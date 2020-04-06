---
title: "JVM打印所有XX参数及值"
date: 2020-04-06T15:36:24+08:00
lastmod: 2020-04-06T15:36:24+08:00
draft: false
keywords: []
description: ""
tags: ["java" ]
categories: ["java"]
---

JVM打印所有XX参数及值主要有如下的参数：PrintCommandLineFlags, PrintFlagsInitial, PrintFlagsFinal.

<!--more-->

## PrintCommandLineFlags
```bash
$ java -XX:+PrintCommandLineFlags -version
-XX:InitialHeapSize=536870912 -XX:MaxHeapSize=8589934592 -XX:+PrintCommandLineFlags -XX:+UseCompressedClassPointers -XX:+UseCompressedOops -XX:+UseParallelGC
openjdk version "1.8.0_242"
OpenJDK Runtime Environment (AdoptOpenJDK)(build 1.8.0_242-b08)
OpenJDK 64-Bit Server VM (AdoptOpenJDK)(build 25.242-b08, mixed mode)
```

## PrintFlagsInitial

```bash
$ java -XX:+PrintFlagsInitial -version |grep -i BiasedLock
     intx BiasedLockingBulkRebiasThreshold          = 20                                  {product}
     intx BiasedLockingBulkRevokeThreshold          = 40                                  {product}
     intx BiasedLockingDecayTime                    = 25000                               {product}
     intx BiasedLockingStartupDelay                 = 4000                                {product}
     bool TraceBiasedLocking                        = false                               {product}
     bool UseBiasedLocking                          = true                                {product}

```

## PrintFlagsFinal

```bash
java -XX:+PrintFlagsFinal -XX:BiasedLockingStartupDelay=0 -version |grep -i BiasedLock
     intx BiasedLockingBulkRebiasThreshold          = 20                                  {product}
     intx BiasedLockingBulkRevokeThreshold          = 40                                  {product}
     intx BiasedLockingDecayTime                    = 25000                               {product}
     intx BiasedLockingStartupDelay                := 0                                   {product}
     bool TraceBiasedLocking                        = false                               {product}
     bool UseBiasedLocking                          = true                                {product}
openjdk version "1.8.0_242"
OpenJDK Runtime Environment (AdoptOpenJDK)(build 1.8.0_242-b08)
OpenJDK 64-Bit Server VM (AdoptOpenJDK)(build 25.242-b08, mixed mode)

```