
1.AndroidManifest中的第三方key在gradle中配置变种时，可以使用"EL表达式" :${}.

2.动态布局加载：

```java
 LinearLayout.LayoutParams lp = (LinearLayout.LayoutParams)view.getLayoutParams();
 lp.height = LinearLayout.LayoutParams.MATCH_PARENT;//相关动态操作
 view.setLayoutParams(lp);
```

3.HashMap和HashTable
hashmap是线程不安全的，若在多线程下要是用线程安全Collections.synchronizedMap()方法获取一个线程安全的集合；hashtable是线程安全的。
hashmap的key可以为null,且总在存储在table数组的第一个节点上
hashmap是对map接口的实现，hashtable实现了map接口和dictionary抽象类

## mvp
### 分离了视图逻辑和业务逻辑，降低了耦合

### Activity只处理生命周期的任务，代码变得更加简洁

### 视图逻辑和业务逻辑分别抽象到了View和Presenter的接口中去，提高代码的可阅读性

### Presenter被抽象成接口，可以有多种具体的实现，所以方便进行单元测试

### 把业务逻辑抽到Presenter中去，避免后台线程引用着Activity导致Activity的资源无法被系统回收从而引起内存泄露和OOM

![mvp](http://7xih5c.com1.z0.glb.clouddn.com/15-10-11/2114527.jpg)

5.EditText 实现TextWatcher

#### 不要再内部类里回调setText，因为afterTextChanged会自己回调一次setText，如果数据not changed,会发生反复递归 闪退;
