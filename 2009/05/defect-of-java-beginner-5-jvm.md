<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>Java���ֵ�ͨ��[5]�����˽�JVM - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">Java���ֵ�ͨ��[5]�����˽�JVM</a></h1>
<div class="post-info"><span class="date-header">2009-05-22</span><a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> <a href="../../tags/E7BC96E7A88B.Java.md" class="tag">���.Java</a> </div>
<hr>
<div class="post">
����<a href="../../2009/02/defect-of-java-beginner-4-exception.md">�ϴε�����</a>������Java�쳣���Ƶļ������ã�����������˵˵JVM���Լ�Java����������صĻ��⡣ΪɶҪ��JVM����Ϊ�кܶ�Java����Ա�����ڶ�JVMȱ���˽⣬������ĳЩ��������ʱ�޴����֣����⣬����ȱ����JVM���˽⣬���ܵ���д�����Ĵ������ܾ޲���������ص�Bug�����԰���֮ǰ�����ӡ�<a href="../../2009/02/study-technology-in-three-steps.md" target="_blank">ѧϰ��������������WHAT��HOW��WHY</a>���У�ǿ���������ڲ����Ƶ���Ҫ�ԡ�����һ��Java����Ա��˵���㲻һ��Ҫ�ǳ����JVM��ϸ�ڣ����Ƕ���һЩ�ؼ����������ƣ�����Ҫ���մ��µĸ��<!--program-think--><br /><br />�������ձ�ϵ�еĹ����������ʼ�����JVM��ص����⣬���������Щ���ⲻ�Ǻ����ף��ǵÿ��ǻ���ʱ��ȥ�˽�һ���ˡ����⣬����������������<a href="../../2009/01/defect-of-java-beginner-0-overview.md" target="_blank">��ϵ��</a>�����ӣ������ë����������ҩ������˵�ú�����Ҳ���пϣ��������������������⣬дһЩ���������<br /><br />������<b>���ڻ������ͺ���������</b><br />�����ܶ����ֲ����Java�Ļ������ͺ����������ڱ�������ʲô�����뿴���µ����⣺<br />�������������������ڴ�洢����ʲô����<br />��������������������������ʲô����<br />���������������Ͷ���GC��ʲô����<br />��������ǰ�������⣬�뿴֮ǰ�����ӡ�<a href="../../2009/03/java-performance-tuning-1-two-types.md" target="_blank">Java�����Ż�[1]���������� vs ��������</a>����<br /><br />������<b>�����������գ�Garbage Collection��</b><br />�����ܶ����ֲ����GC��ʵ�ֻ��ơ��뿴���µ����⣺<br />������GC������ж���Щ�����Ѿ�ʧЧ��<br />������GC�����ܻ�����ЩӰ�죿<br />���������ͨ��JVM�Ĳ�������GC�����ܣ�<br />��������GC�����⣬���Բμ�֮ǰ�����ӡ�<a href="../../2009/04/java-performance-tuning-3-gc.md" target="_blank">Java�����Ż�[3]�������������գ�GC��</a>����<br /><br />������<b>�����ַ���</b><br />��������Java�ṩ��String��StringBuilder����غܶ��˶�֪����String���ڳ����ַ�����StringBuilder���ڿɱ��ַ�������Java����ΪʲôҪ���������Ϊɶ����һ������ͳһ�㶨��<br /><br />������<b>���ڷ��ͣ�Generic Programming��</b><br />������JDK 1.5��ʼ��Java������һ�����������﷨�����͡������󣬺ܶ����ֽ���֪�����͵�Ƥë�������ںܶ౾�ʵĶ����������˽⡣<br />������GP���ڱ���ʱʵ�ֵĻ���������ʱʵ�ֵģ�ΪʲôҪ��ôʵ�֣�<br />������GP�����Ͳ���������զ���£���ɶ�ŵ�/ȱ�㣿<br />������ʹ�÷�������������ڴ�ͳ����������������ɶӰ�죿Ϊʲô��<br /><br />������<b>���ڶ��߳�</b><br />�������⣬���߳�Ҳ�Ǵ󲿷�Java���ֵĶ̰塣���԰���������Ἰ�����ڶ��̵߳����⡣<br />������synchronized�ؼ�������ô�����õΣ�<br />������synchronized�Ŀ����ȣ�����˵��������Σ������ĳ���໹�����ĳ�������ʵ����<br />������synchronized��������û��Ӱ�죿Ϊʲô��<br />������volatile�ؼ���������ɶ�õΣ�ɶʱ����Ҫ������ؼ�����<div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/05/defect-of-java-beginner-5-jvm.md">2009/05/defect-of-java-beginner-5-jvm.md</a>
</div>
</div>
</body>
</html>
