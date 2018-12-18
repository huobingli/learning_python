# python�ֵ�����߼����ɣ�http://www.jb51.net/Special/670.htm
# python�ֵ����������http://www.jb51.net/article/66995.htm
### dict ����

dict�û����ţ�����ʾ��Ȼ���� key: value, д�������ɡ����һ�� key: value �Ķ��ſ���ʡ�ԡ�

#### dict�Ĳ����ٶȿ�
����dict��10��Ԫ�ػ���10���Ԫ�أ������ٶȶ�һ������list�Ĳ����ٶ�����Ԫ�����Ӷ����½���
dict��ȱ����ռ���ڴ�󣬻����˷Ѻܶ����ݣ�list�����෴��ռ���ڴ�С�����ǲ����ٶ���

#### dict ͨ��key ������ value
���key �����ظ�����value���ظ�

#### dict�����"key:value"�������
����������������Ƭ�ȡ�

Python�Ļ����������ַ��������������������ǲ��ɱ�ģ���������Ϊ key������list�ǿɱ�ģ��Ͳ�����Ϊ key��

### �� dict ��ʾ�����֡�-���ɼ����Ĳ��ұ����£�
```
 d = {
 'Adam': 95, #key : value
 'Lisa': 85,
 'Bart': 59
 }
```
���ǰ����ֳ�Ϊkey����Ӧ�ĳɼ���Ϊvalue��dict����ͨ�� key ������ value��

### ���� dict

����һ��dict�����ڱ�ʾ���ֺͳɼ��Ķ�Ӧ��ϵ��
```
 d = {
 'Adam': 95,
 'Lisa': 85,
 'Bart': 59
 }
```
ʹ�� d[key] ����ʽ�����Ҷ�Ӧ�� value����� list ���񣬲�֮ͬ���ǣ�list ����ʹ���������ض�Ӧ��Ԫ�أ���dictʹ��key���ض�Ӧ��val��

ע��: ͨ�� key ���� dict ��value��ֻҪ key ���ڣ�dict�ͷ��ض�Ӧ��value�����key�����ڣ���ֱ�ӱ���KeyError��

### Ҫ���� KeyError �������������취��

#### ���ж�һ�� key �Ƿ���ڣ��� in ��������
```
 if 'Paul' in d:
	print d['Paul']
```
��� 'Paul' �����ڣ�if����ж�ΪFalse����Ȼ����ִ�� print d['Paul'] ���Ӷ������˴���

#### ʹ��dict�����ṩ��һ��get����dict.get(key, default=None)
��Key�����ڵ�ʱ�򣬷���Ĭ��ֵNone��
```
 >>> print d.get('Bart')
 59
 >>> print d.get('Paul')
 None
```
 ### ���� dict 
dict�ǿɱ�ģ�������ʱ��dict������µ� key-value����������dict��
```
 d = {
 'Adam': 95,
 'Lisa': 85,
 'Bart': 59
 }
```
 Ҫ����ͬѧ'Paul'�ĳɼ� 72 �ӽ�ȥ���ø�ֵ��䣺
```
 >>> d['Paul'] = 72 
```
 �ٿ���dict�����ݣ�
```
 >>> print d
 {'Lisa': 85, 'Paul': 72, 'Adam': 95, 'Bart': 59}
```
 ��� key �Ѿ����ڣ���ֵ�����µ� value �滻��ԭ���� value��
```
 >>> d['Bart'] = 60
 >>> print d

 {'Lisa': 85, 'Paul': 72, 'Adam': 95, 'Bart': 60��
```
### ɾ��dictԪ�ػ����dict
��ʹ��pop����: 
dict.pop(key[,default])��ͨ��keyֵɾ��dict��Ԫ�أ������ر�ɾ��key��Ӧ��value��
��key�����ڣ���defaultֵδ���ã��򷵻�KeyError�쳣��
```
>>> a
{1: 'abc', 2: 'efg', 3: 'hij'}
>>> a.pop(1)
'abc'
>>> a
{2: 'efg', 3: 'hij'}
>>> 
>>> a
{2: 'efg', 3: 'hij'}
>>> a.pop(1,False)
False
>>>
```
��ʹ��clear����dict.clear()���dict

### ����/���� dict 

#### forѭ������
����dictҲ��һ�����ϣ����ԣ�����dict�ͱ���list���ƣ�������ͨ�� for ѭ��ʵ�֡� 
```
>>> d = { 'Adam': 95, 'Lisa': 85, 'Bart': 59 }4
>>> for key in d:
print key,'-',d[key]
Lisa - 85
Adam - 95
Bart - 59
```

#### values() / itervalues() ����������dict ��valueֵ 

values()�������� dict ת�����˰��� value ��list 
```
>>> d = { 'Adam': 95, 'Lisa': 85, 'Bart': 59 }
>>> print d.values()
[85, 95, 59]
>>> for v in d.values():
print v
85
95
59
```
 �� itervalues() ������� values() ����������Ч����ȫһ����
 �� itervalues() ��������ת���������ڵ������������δ� dict ��ȡ�� value������ itervalues() ������ values() ������ʡ������ list ������ڴ档
 
#### items() / iteritems() ����������dict ��key��value 
 
dict ����� items() �������ص�ֵ��
```
 >>> d = { 'Adam': 95, 'Lisa': 85, 'Bart': 59 } >>> print d.items() [('Lisa', 85), ('Adam', 95), ('Bart', 59)]
```
���Կ�����items()������dict����ת�����˰���tuple��list��
�����list���е���������ͬʱ���key��value��
```
>>> for key, value in d.items(): ... print key, ':', value ... Lisa : 85 Adam : 95 Bart : 59
```
�� values() ��һ�� itervalues() ���ƣ� 
items() Ҳ��һ����Ӧ�� iteritems()��iteritems() ����dictת����list�������ڵ��������в��ϸ��� tuple�����ԣ�iteritems() ��ռ�ö�����ڴ档