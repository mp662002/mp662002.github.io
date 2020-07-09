---
layout: post
title: MessageBox가변인수

---


***



~~~c++
#include <tchar.h>
void MyMessageBox(const TCHAR* pFormat, ...)
{
    TCHAR szData[500];
    va_list argptr;
    va_start(argptr, pFormat);
    _vstprintf(szData,_countof(szData), pFormat, argptr);
    va_end(argptr);
    MessageBox(NULL, szData, NULL, MB_OK);
}
void MyOutputDebugString(const TCHAR* pFormat, ...)
{
    TCHAR szData[500];
    va_list argptr;
    va_start(argptr, pFormat);
    _vstprintf(szData, _countof(szData), pFormat, argptr);
    va_end(argptr);
    OutputDebugString(szData);
}
~~~


