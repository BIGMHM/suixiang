<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>C++��������ô���ģ�POSIX�̣߳�pthread��ƪ - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">C++��������ô���ģ�POSIX�̣߳�pthread��ƪ</a></h1>
<div class="post-info"><span class="date-header">2009-03-14</span><a href="../../tags/E7BC96E7A88B.C.md" class="tag">���.C</a> <a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> <a href="../../tags/E7BC96E7A88B.E5A49AE7BABFE7A88B.md" class="tag">���.���߳�</a> </div>
<hr>
<div class="post">
����<a href="../../2009/03/cxx-object-destroy-with-thread-win32.md">��һ������</a>������Win32�����º��߳��йص�C++�����������⣬�����˵һ˵POSIX���߳̿�pthread�ˡ�������pthread��̫�˽⣬�����ȿ���<a href="http://en.wikipedia.org/wiki/POSIX_Threads" target="_blank" rel="nofollow">ά���ٿ�</a>�Ľ��ܡ�<!--program-think--><br /><br />������<b>��������</b><br />�����ϻ���˵�������Ƚ�������������<br />����1����Ȼ����<br />����<a href="../../2009/03/cxx-object-destroy-with-thread-win32.md">��һ������</a>�Ѿ�������Win32�̵߳���Ȼ������pthread����Ȼ����������࣬Ҳ���̶߳�Ӧ���̺߳���ͨ��return���ء�<br />����2����ɱ<br />�������ڡ���ɱ����POSIXʹ��<b>pthread_exit</b>������ʵ�֡���һ�ַ�ʽ�����Win32����ɱ�򵥶��ˣ��˴�ʡȥ���ٿ�ˮ��<br />����3����ɱ<br />������Ȼpthread����ɱ�򵥣�������ɱ�ͱȽϸ����ˡ����ԣ��Ұѿ�ˮת�Ƶ�����ص�˵һ����ɱ�ķ�ʽ��<br />������pthread������Ҫʹ��<b>pthread_cancel</b>ɱ�̡߳���<b>pthread_cancel</b>ȡ���̻߳������������<b>�첽ȡ��</b>��PTHREAD_CANCEL_ASYNCHRONOUS����<b>�ӳ�ȡ��</b>��PTHREAD_CANCEL_DEFERRED�����첽ȡ�����൱�ֱ��ģ��������߶�ʮһ��ֱ�Ӱ��̸߳ɵ������ӳ�ȡ����Ƚ����ᣬ��ȡ�����̻߳��������ֱ������ĳ����ȡ���㡱����ֹ�����ڱ�������pthread������ɨä��������ʲô�ǡ�ȡ���㡱�Լ��߳�ȡ��������ϸ�ڣ���ο�pthread API�ֲᡣ<br />������ͬѧ���ܻ����ˣ�<b>pthread_kill</b>�ѵ�������������ɱ���ģ���ʵ<b>pthread_kill</b>ֻ�����Ǹ�ָ�����̷߳����źţ�signal�����ѡ���������Ҳ��֪�����ĸ��һ�����<b>pthread_kill</b>��������������˲���ͬѧ�����⣬ʹ��<b>pthread_kill</b>��һ��ҪС�ģ������Ӧ���߳�û��<b>����</b>�յ����źţ�����źſ��ܻ�Ӱ���߳����ڵ�<b>����</b>�����ܻᵼ�½�����ֹ���൱�ڽ�����ɱ����<br /><br />������<b>����������</b><br />����<a href="../../2009/03/cxx-object-destroy-with-thread-win32.md">��һ������</a>�Ѿ������������߳��йص�C++����Ҳ�������־ֲ������뿴�����ֶ����ڲ�ͬ�����ϣ��Ƿ������������<br />��������������������������������������������������<br />�������������������ֲ��Ǿ�̬���󡡡��ֲ���̬����<br />������Ȼ���������������ܡ�����������������<br />��������ɱ������������һ���ܡ�������������<br />������ɱ���ӳ٣�������һ���ܡ�������������<br />������ɱ���첽�����������ܡ���������������<br />��������������������������������������������������<br />���������������ձ��еġ���һ���ܡ�����Linuxƽ̨��������RHEL3��GCC 3.2.3�����ܹ�������������Cygwin��������Windows2003��GCC 3.4.4���в��ܣ�����ֻ����Ϊ�ǡ���һ������������<br />��������pthread�ڲ�ͬ�Ĳ���ϵͳ�ϵ�ʵ�ֿ����в��죬˵������ĳЩ�����£���ɱ����ɱ�ı��ֻ��������һ�¡������㷢���Լ�������ʵ����������������ϣ���ӭ��ͨ�����ۻ��ʼ������ң��һᲹ�䵽������ <b>:-)</b><br />��������������������첽��ɱ�����ȫ�ģ���Ȼ���������ȫ�ġ�������ɱ���ӳ���ɱ����Ҫ������Ļ����ˡ�<br /><br />������<b>�������߳�֮��</b><br />��������ɶ�����̣߳�<a href="../../2009/03/cxx-object-destroy-with-thread-win32.md">��һ������</a>�Ѿ����ܹ��ˣ����ٶ����¡���POSIXϵͳ����̵߳���Ȼ����Ҳ������<b>exit</b>�����ã��Ӷ����������̱߳�Ұ���ظɵ���������κ�Windowsϵͳ�����ƣ������ϣ�����߳��˳������½�����ɱ������ʹ��<b>pthread_exit</b>���������̣߳����������̼߳������С����������߳���ɱ��ĳЩ������Ҳ<b>����ȫ</b>���ҽ��黹�������߳�����˳��Ƚ����ס�<br /><br />����POSIXϵͳ�У��߳���صĶ����������⣬���ĵ����<div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/03/cxx-object-destroy-with-thread-posix.md">2009/03/cxx-object-destroy-with-thread-posix.html</a>
</div>
</div>
</body>
</html>
