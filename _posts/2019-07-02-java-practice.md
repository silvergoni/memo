---
title: "java practice"
date: 2019-07-02 14:55:28 -0400
categories: java
---


### 삼항연산자
```
아래와 같은 경우, 
if (a == null) {		
    this.count = 0;			
} else {	
    this.count = a.get();	
}
이렇게 바꾸면
ObjectUtils.isEmpty(a) || ObjectUtils.isEmpty(a.get()) ? 0 : a.get();
좋은거 같다.
```
