## Python��hasattr() getattr() setattr() ����ʹ�÷������

### hasattr(object, name)
�ж�һ�����������Ƿ���name���Ի���name����������BOOLֵ����name���Է���True�� ���򷵻�False��
��Ҫע�����nameҪ������������

```
 1 >>> class test():
 2 ...     name="xiaohua"
 3 ...     def run(self):
 4 ...             return "HelloWord"
 5 ...
 6 >>> t=test()
 7 >>> hasattr(t, "name") #�ж϶�����name����
 8 True
 9 >>> hasattr(t, "run")  #�ж϶�����run����
10 True
11 >>>
```
### getattr(object, name[,default])
��ȡ����object�����Ի��߷�����������ڴ�ӡ��������������ڣ���ӡ��Ĭ��ֵ��Ĭ��ֵ��ѡ��
��Ҫע����ǣ�����Ƿ��صĶ���ķ��������ص��Ƿ������ڴ��ַ�������Ҫ�������������
�����ں������һ�����š�

```
 1 >>> class test():
 2 ...     name="xiaohua"
 3 ...     def run(self):
 4 ...             return "HelloWord"
 5 ...
 6 >>> t=test()
 7 >>> getattr(t, "name") #��ȡname���ԣ����ھʹ�ӡ������
 8 'xiaohua'
 9 >>> getattr(t, "run")  #��ȡrun���������ھʹ�ӡ���������ڴ��ַ��
10 <bound method test.run of <__main__.test instance at 0x0269C878>>
11 >>> getattr(t, "run")()  #��ȡrun��������������ſ��Խ�����������С�
12 'HelloWord'
13 >>> getattr(t, "age")  #��ȡһ�������ڵ����ԡ�
14 Traceback (most recent call last):
15   File "<stdin>", line 1, in <module>
16 AttributeError: test instance has no attribute 'age'
17 >>> getattr(t, "age","18")  #�����Բ����ڣ�����һ��Ĭ��ֵ��
18 '18'
19 >>>
```
 

### setattr(object, name, values)
����������Ը�ֵ�������Բ����ڣ��ȴ����ٸ�ֵ��

```
 1 >>> class test():
 2 ...     name="xiaohua"
 3 ...     def run(self):
 4 ...             return "HelloWord"
 5 ...
 6 >>> t=test()
 7 >>> hasattr(t, "age")   #�ж������Ƿ����
 8 False
 9 >>> setattr(t, "age", "18")   #Ϊ���ำֵ����û�з���ֵ
10 >>> hasattr(t, "age")    #���Դ�����
11 True
12 >>>
```
 

### һ���ۺϵ��÷��ǣ��ж�һ������������Ƿ���ڣ��������ھ���Ӹ����ԡ�

```
 1 >>> class test():
 2 ...     name="xiaohua"
 3 ...     def run(self):
 4 ...             return "HelloWord"
 5 ...
 6 >>> t=test()
 7 >>> getattr(t, "age")    #age���Բ�����
 8 Traceback (most recent call last):
 9   File "<stdin>", line 1, in <module>
10 AttributeError: test instance has no attribute 'age'
11 >>> getattr(t, "age", setattr(t, "age", "18")) #age���Բ�����ʱ�����ø�����
12 '18'
13 >>> getattr(t, "age")  #�ɼ�����óɹ�
14 '18'
15 >>>
```
