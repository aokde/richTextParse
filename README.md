## ΢��С�����ı����� - richTextParse��
�����󵽵�HTML����ת��Ϊ[rich-text��ǩ](https://mp.weixin.qq.com/debug/wxadoc/dev/component/rich-text.html)��nodes����֧�ֵ�JSON��ʽ���Ӷ�ʵ����΢��С�����еĿ��ӻ�����Ϊ�Ǹ������Լ�������ȥ���ģ�����Ŀǰ���ܱȽϼ򵥡�

�ڴ��Ƽ���[wxParse](https://github.com/icindy/wxParse)����������ܱȽ�ȫ������ΪwxParse����pre��ǩ�е����⣬���ԲŶ���д��richTextParse��

richTextParse��˼·���ǽ�HTML�������ΪDOM���ͽṹ���ǳ�����⡣��Ҳ������Ŀǰ����Ļ����Ͻ��и���ı�ǩ��֤��Ŀǰ��ֻ��֤��ͼ���ǩ����ͼ���ǩ�м���src�����ԣ����ḻ���빦�ܡ�����һ�ж������뿪΢��С�����е�[rich-text��ǩ](https://mp.weixin.qq.com/debug/wxadoc/dev/component/rich-text.html)֧�֡�

### Ч��
![Ч��ͼ](utils/richTextParse/effect.png)

֧��Html�ĵ��г��õı�ǩ��

### ʹ��
��Ҫʹ�õ����ļ�����������richText.js���͡�richText.wxss�������Ǵ���ڣ���utils/richTextParse���ļ����¡�

�ں��ʵ�λ��������ʽ�����硰app.wxss��(����)����������Ҫʹ�õ�λ�ã����ġ�*.wxss���С�

�����������ֻ��һ���õ�������ֱ������Ҫʹ�õ�λ������JS�ļ����ɡ�
#### �����ļ�
```
//��ʹ�õ�View(pages/article/index.js)������
var richTextParse = require('../../utils/richTextParse/richText.js');
```
```
//�ڡ�app.wxss��������
@import 'utils/richTextParse/richText.wxss';
```
�ڽӿڻ�ȡhtml��λ�ã�ʹ�á�richTextParse.go()��������ȡ�������Ľ���������ҵģ�
#### ����html����
```
success:function(rs){
  that.setData({
    ...
    bodyHtml: richTextParse.go(rs.data.body),
    ...
  })
}
```
#### ģ����ʹ��
����wxml��ʹ��rice-text���ɣ�
```
<rich-text nodes='{{bodyHtml}}'></rich-text>
```
------
����������жദ��Ҫ�õ���һ���ܣ������JS�ڡ�app.js�������룬���ҹ���App�£�
```
var richTextParse = require('utils/richTextParse/richText.js');
App({
    ...
    richTextParse : richTextParse.go,
    ...
})
```
����Ҫʹ�õ�λ��ʹ��ȫ��richTextParse�������ɣ�
```
var app = getApp();
Page({
    ......
             bodyHtml: app.richTextParse(rs.data.body),
    ......
})
```

### ��β
�������ܿ���ʹ�ã���Ϊ�Ѿ��������Լ��������ˣ�����Ӧ�ò��᳣���¡������С�����ʹ�õ�ʱ����Ҫ��ʲô���ܵĻ�ϣ�����Ը������Ż������~