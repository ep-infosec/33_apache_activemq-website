---
layout: default_md
title: NoClassDefFoundError - org.springframework.core.io.Resource 
title-class: page-title-activemq5
type: activemq5
---

 [FAQ](faq) > [Errors](errors) > [Exceptions](exceptions) > [NoClassDefFoundError - org.springframework.core.io.Resource](noclassdeffounderror-orgspringframeworkcoreioresource)


If you get an exception like this
```
java.lang.NoClassDefFoundError - org/springframework/core/io/Resource
```

### Cause

You were probably trying to use the [XML Configuration](xml-configuration) mechanism, which uses Spring, but without having the Spring jar on your classpath.

### Solution

Add the Spring jar to your classpath.

