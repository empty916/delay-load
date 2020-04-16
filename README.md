# delay-load


## 懒加载组件延迟加载工具函数

- 主要用于骨架屏幕的使用场景
- 由于页面组件加载过快，导致骨架屏一闪而过，影响用户体验，所以在组件第一次懒加载时，设定最小懒加载时间，保证骨架屏不会一闪而过
  
## demo

````typescript
import React from 'react';
import loadabel from '@loadable/component';
import delayLoad from 'delay-load';
import Skeleton from 'your-skeleton-component'

const _loadabel = (c: () => Promise<any>, time: number = 700) => loadabel(() => delayLoad(c, time), {
	fallback: <Skeleton></Skeleton>,
});

// Page1至少加载1000ms
const Page1 = _loadabel(() => import('page1'), 1000);



````
