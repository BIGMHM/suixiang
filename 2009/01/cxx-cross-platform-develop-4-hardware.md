<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>C++�Ŀ���ֲ�ԺͿ�ƽ̨����[4]��Ӳ����ϵ��� - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">C++�Ŀ���ֲ�ԺͿ�ƽ̨����[4]��Ӳ����ϵ���</a></h1>
<div class="post-info"><span class="date-header">2009-01-31</span><a href="../../tags/E7BC96E7A88B.C.md" class="tag">���.C</a> <a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> </div>
<hr>
<div class="post">
��������ĵĻ�����Ҫ�Ǻ�Ӳ����ϵ�йصġ�������ĳ�����Ҫ֧�ֲ�ͬ���͵�CPU��x86��SPARC��PowerPC����������ͬ�����Ͳ�ͬ�ֳ���CPU������x86��x86-64������ʱ�������Ҫ����һ��Ӳ����ϵ�����⡣<!--program-think--><br /><br />������<b>�������͵Ĵ�С</b><br />����C++�л������͵Ĵ�С��ռ�õ��ֽ�����������CPU�ֳ��ı仯���仯�����ԣ�������Ҫ��ʾһ��intռ�õ��ֽ�����ǧ��Ҫֱ��д��<b>4</b>����˳��˵һ�£�ֱ��д��<b>4</b>��������Magic Number�Ĵ�ɣ����<a href="../../2009/02/defect-of-java-beginner-3-code-style.md#magic_number">����</a>������Ӧ��д��<b>sizeof(int)</b>�����������������Ҫ����һ����С<b>����</b>Ϊ4�ֽڵ��з���������Ҳ��Ҫֱ����int��Ҫ��Ԥ��typedef�õĶ������ͣ�����<a href="http://www.boost.org/" target="_blank" rel="nofollow">boost</a>���int32_t��<a href="http://www.cs.wustl.edu/%7Eschmidt/ACE.html" target="_blank" rel="nofollow">ACE</a>���ACE_INT32���ȣ���<br />����������ˣ�ָ��Ĵ�СҲ�����������⣬ҲҪС�ġ�<br /><br />������<b>�ֽ���</b><br />���������û��˵�����ֽ�������������뿴��<a href="http://en.wikipedia.org/wiki/Endianness" target="_blank" rel="nofollow">ά���ٿ�</a>����ͨ�׵ش���ȷ�����һ����β��Ļ�������һ��4�ֽڵ�����0x01020304��ͨ����������ļ�����һ̨Сβ��Ļ����Ͼͻ���0x04030201����˵����һ����β��Ļ�����������û�Ӵ�������������������0x02010403��<br />����������д��Ӧ�ó������漰����ͨѶ��һ��Ҫ�ڼǵý����������������ķ��룻����漰���������������ļ���ҲҪ�ǵý������Ƶ�ת����<br /><br />������<b>�ڴ����</b><br />��������㲻���á��ڴ���롱��ʲô�������뿴��<a href="http://en.wikipedia.org/wiki/Data_structure_alignment" target="_blank" rel="nofollow">ά���ٿ�</a>��������˵������CPU�����ϵ����ܿ��ǣ��ṹ���е����ݲ��ǽ����ŵģ�����Ҫ�տ�һЩ����������Ļ����ṹ����ÿ�����ݵĵ�ַ���ö���ĳ���ֳ�����������<br />��������C++��׼��û�ж����ڴ�����ϸ�ڣ���ˣ���Ĵ���Ҳ�������������ϸ�ڡ����Ǽ���ṹ���С�ĵط���������ʵʵд��sizeof()��<br />������Щ������֧��#pragma packԤ������䣨���������޸Ķ����ֳ��������������﷨�������б�������֧�֣�Ҫ���á�<br /><br />������<b>��λ����</b><br />���������з������������Ʋ�������ЩϵͳĬ��ʹ���������ƣ���ߵķ���λ���䣩����ЩĬ��ʹ���߼����ƣ���ߵķ���λ��0�������ԣ���Ҫ���з��������������Ʋ�����˳��˵һ�£���ʹû����ֲ�����⣬������Ҳ����������λ���������Щ<b>��ͼ</b>����λ������������ܵ�ͬѧ��Ҫע���ˣ���ô�ɲ����ɶ��Ժܲ���ҳ������ֺá�ֻҪ��̫���ǵı������������Զ�����㶨�����Ż����������Ա���ġ�<br /><br />������һ�����ӣ�׼����һ�¡�<a href="../../2009/02/cxx-cross-platform-develop-5-os.md">����ϵͳ��صĿ�ƽ̨����</a>����<div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/01/cxx-cross-platform-develop-4-hardware.md">2009/01/cxx-cross-platform-develop-4-hardware.md</a>
</div>
</div>
</body>
</html>
