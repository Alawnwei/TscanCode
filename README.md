# **TscanCode** 

![Release version](https://img.shields.io/badge/version-2.11.27-blue.svg)

## A fast and accurate static analysis solution for C/C++, C#, Lua codes

Tencent is pleased to support the open source community by making TscanCode available.

Copyright (C) 2017 THL A29 Limited, a Tencent company, and TscanCode Team. All rights reserved.

##Introduction

TscanCode is devoted to help programmers to find out code defects at the very beginning.  
* TscanCode supports multi-language: `C/C++`, `C#` and `Lua` codes;
* TscanCode is `fast` and `accurate`, The performance can be 200K lines per minute and  the accuracy rate is about 90%;   
* TscanCode is `easy to use`, It doesn't require strict compiling enviroment and one single command can make it work; 
* TscanCode is `extensible`, you can implement your own checks with TscanCode.

#Highlights in v2.11.27 (2017-12-01)
* Add new check `CS_UnityMessgeSpellWrong`, check typo errors of Unity message functions;
* Add new check `lua_VarSpellWrongError` and `lua_KeywordSpellWrongError`, check typo errors of Lua variable and keyword;

For other changes please refer to [change log](CHANGELOG.md).

## Compiling

Any C++11 compiler should work. For compilers with partial C++11 support it may work. If your compiler has the C++11 features that are available in Visual Studio 2015 then it will work. If nullptr is not supported by your compiler then this can be emulated using the header lib/cxx11emu.h.

There are multiple compilation choices:
* Windows: Visual Studio (Visual Studio 2015 and above)
* Linux: g++ 4.6 (or later)
* Mac: clang++

### Visual Studio

Use the tsancode.sln file. The file is configured for Visual Studio 2015, but the platform toolset can be changed easily to older or newer versions. The solution contains platform targets for both x86 and x64.

Select option `Release` to build release version.

### g++ or clang++

Simple build (no dependencies):

```shell
make
```

## Usage at a glance

This simple example contains a potential null pointer defect. Checking if p is null indicates that p might be null, so dereferencing p `*p` is not safe outside the `if-scope`.

~~~~~~~~~~cpp
void func(int* p) {
	if(p == NULL) {
		printf("p is null!");
	}

	printf("p is %d", *p);
}
~~~~~~~~~~





