<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>C++��������ô���ģ�ΪʲôҪд���ϵ�У� - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">C++��������ô���ģ�ΪʲôҪд���ϵ�У�</a></h1>
<div class="post-info"><span class="date-header">2009-02-26</span><a href="../../tags/E7BC96E7A88B.C.md" class="tag">���.C</a> <a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> </div>
<hr>
<div class="post">
����Ҫ˵C++��������ô���ģ����ȴ�C++����������˵������������ұ��˺�ϲ����һ���������ԣ���ϧ�кü�������û�����Ƶ������������Ͳ������ˣ����������ˮս�������ǿ�������C++�Ĺ����������������ʵ��Guardģʽ��д���Ƚ��������������쳣��ȫ�Ĵ��롣����Guardģʽ��C++����������ͦ�࣬���Ա�֤<b>���ж�������</b>����һ������Ҫ����������⡣<!--program-think--><br />�������⣬�ҷ��ֺܶ�C++����Աֻ�����ڴ�й¶���⣬�����ģ����������Դй¶���⣨�����������ڡ�<a href="../../2009/02/defect-of-java-beginner-3-code-style.html#gc" target="_blank">Java����ͨ��[3]</a>���ᵽ�����󣩡���������ġ�<a href="../../2009/02/cxx-object-destroy-with-process.md" target="_blank">C++��������ô���ģ�����ƪ</a>�������󣬾���ͬѧ���ˣ������������ˣ�����û��������ʲô��ϵ����ʵ���й�ϵ������Ȼ����ϵͳ���ڽ������������ʬ��Ҳ���ǰ�ĳЩ��Դ�������ڴ���л��գ����������õ����ڴ�й¶�����⡣���Ǳ����ˣ������ڴ���Դ�������п��ܻ�����������ҵ��������Դ������Щ��Դ������ϵͳ�ǲ�������Զ����յġ�������Ҫ�ن���һ�Σ�<b>��Դй¶�������ڴ�й¶Ҫ���صöడ</b>��������֮��Ϊ�˼���ӡ���پ�����һ�����ӡ�<br />��������ĳҵ���߼�Foo��Ҫ������������ʱ�ļ�������ĳ��̬���ɵ���ʱĿ¼�У���Ϊ�˱�֤��ҵ���߼������󣨿���������������Ҳ������;�׳��쳣��������ʱĿ¼���Ǳ�ɾ��������ʹ�����µ�Guardģʽ��<br /><pre>class CTempDirGuard<br />{<br />public:<br />  CTempDirGuard(const string&amp; sFolderName)<br />  {<br />    // ����ĳ��ʱĿ¼<br />  }<br />  virtual ~CTempDirGuard()<br />  {<br />    // �Ѹ���ʱĿ¼������ɾ��<br />  }<br />};<br /><br />void Foo()<br />{<br />  CTempDirGuard guard(xxx);  // ����guard����<br />  // ����ʱĿ¼�Ŷ���<br />  // �����ǳ���return��仹�����쳣�׳���guard���ᱻ�����������xxxĿ¼�ᱻɾ��<br /><br />  // �����������ִ�е��˴���ȴ�������̵�<b>��</b>��Ȼ������<br />  // ����������£���guard����<b>����</b>����������˻�����һ������Ŀ¼���˷���Ӳ����Դ<br />}</pre><br />��������������˵������ԭ��������һֱ��дһ���ⷽ������ӡ�����ǰ����д���������ۡ�<a href="../../2009/02/multi-process-vs-multi-thread.md" target="_blank">�ܹ���ƵĶ��������</a>����֮��;�˳��д��һ�����ӣ���C++��������ô���ģ�����������һ�����ڽ��̲�ͬ��������C++����������Ӱ�졣��д��֮��ͻȻ�뵽�����˽�����ֹ��������ܵ���C++�����<b>��</b>���������������̵߳���������Ҳ���ܻ���C++����<b>��</b>�������������Ըɴ�͸��˸������С�C++ ��������ô���ģ��� :-)<br /><br />�������⣬Ϊ�˷����Ķ����ѱ�ϵ�����ӵ�Ŀ¼�������£�<br />����1��<a href="../../2009/02/cxx-object-destroy-with-process.md">����ƪ</a><br />����2��<a href="../../2009/02/cxx-object-destroy-with-io-stream.md">�Ա�׼����������Ľ�һ��̽��</a><br />����3��<a href="../../2009/03/cxx-object-destroy-with-thread-win32.md">Win32�߳�ƪ</a><br />����4��<a href="../../2009/03/cxx-object-destroy-with-thread-posix.md">POSIX�̣߳�pthread��ƪ</a><br />����5��......<div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/02/cxx-object-destroy-overview.md">2009/02/cxx-object-destroy-overview.html</a>
</div>
</div>
</body>
</html>
