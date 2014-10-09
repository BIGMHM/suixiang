<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>C/C++��һ���򵥵�enum�ַ�(idiom) - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">C/C++��һ���򵥵�enum�ַ�(idiom)</a></h1>
<div class="post-info"><span class="date-header">2009-04-18</span><a href="../../tags/E7BC96E7A88B.C.md" class="tag">���.C</a> <a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> </div>
<hr>
<div class="post">
��������д�����ʱ�����õ����idiom�ˣ�����˳�������������idiom���򵥵ģ����ƺܶ��˶��ù���������Ҫ�������������ֲο��������Ǿͱ·�ʱ�������ˣ���<!--program-think--><br />����Ϊ��˵������ַ������զ�ã��۾�һ���򵥵�������˵�¶����ȷ�˵Ҫ����һ���������������Ҫͳ�Ƹ�������Э������ݰ�������<br /><br />������<b>�汾1</b><br />��������һ��ʼֻ��Ҫ����HTTP��FTP����Э�顣��Щͬѧ����˼������������������������������ͳ�ƣ�<br /><font face="Courier New"><br />int nCntHttp = 0;<br />int nCntFtp = 0;<br /></font><br />������һ�����ƺ�ûɶ���⡣���ǣ�����������������Ҫ��������Э�飺SMTP��SSH��Ȼ�󣬸�ͬѧ�������չ�������룬��Ϊ���£�<br /><font face="Courier New"><br />int nCntHttp = 0;<br />int nCntFtp = 0;<br />int nCntSmtp = 0;<br />int nCntSsh = 0;<br /></font><br />������ʱ�����⿪ʼ��¶�����ˡ��ȷ�˵Ҫ��ӡ����4ͳ��ֵ���͵�д4��printf���ټ���Ҫ�ö���ȷ������ͳ��ֵ�����㣬Ҳ��д4��assert���ⶼ��ͦ���˵��¶�������Ȼ������Щͬѧ���4�������Ĵ�ӡд��һ��printf�У�������һ�����ˣ�<br /><br />������<b>�汾2</b><br />�������զ����ĳЩͬѧ�����һ���������������޸�Ϊ������ʽ��������4��ͳ��ֵ<b>����</b>���������С��������£�<br /><font face="Courier New"><br />int nCntProto[4];<br />/* ��0����HTTP����1����FTP����2����SMTP����3����SSH */<br /></font><br />���������������Ǵ�ӡ���Ƕ��ԣ���������forѭ���㶨��ò��ͦ����ġ�����ôһ������������һ�����⡣�������ڳ�����Ҫ�õ�SMTP��ͳ�����֣��͵���ôд���룺nCntProto[<b><font color="red">2</font></b>]���������˺ܲ��Ź۵ġ�<a href="http://en.wikipedia.org/wiki/Magic_number_(programming)#Unnamed_numerical_constant" target="_blank" rel="nofollow">Magic Number</a>����Ҫ֪����Magic Number���Ǵ���ĳ�ζ֮һ������׶��ڡ�<a href="../../2009/02/defect-of-java-beginner-3-code-style.html#magic_number" target="_blank">����</a>���������ܹ�������һ�����������еĴ��˳�����仯���Ǿ��군�ˣ��ö��õ�Magic Number�Ĵ��붼�ø��Ÿġ�һ��©��ĳ��������Bug������<br /><br />������<b>�汾3</b><br />����Ϊ������Magic Number�����Ӵ���ɶ��ԺͿ�ά���ԣ���Щͬѧ��ʼ����enum�����⡣�ڴ�����������һ��enum���������£�<br /><pre><font face="Courier New">enum PROTO<br />{<br />  PROTO_HTTP,<br />  PROTO_FTP,<br />  PROTO_SMTP,<br />  PROTO_SSH,<br />};<br /><br />int nCntProto[4];</font></pre><br />�����������������Ҫ�õ�SMTP��ͳ�����֣��ҾͲ���дnCntProto[2]������дnCntProto[PROTO_SMTP]���������ɶ������Ժö��ˡ���ʹ���������еĴ��˳�����仯��Ҳû��ϵ��ֻ����΢����enum�г�����˳�򼴿ɣ��������벻�ö���<br /><br />������<b>�汾4</b><br />�������ǣ�������һ����ˬ�ĵط����������������õ��ˡ�4�����Magic Number����һ������������������������Э�飬��������ֻ��ò��ϵ�������ˬ��<br />������ʱ���ռ��汾¡�صǳ����뿴���´��룺<br /><pre><font face="Courier New">enum PROTO<br />{<br />  PROTO_HTTP,<br />  PROTO_FTP,<br />  PROTO_SMTP,<br />  PROTO_SSH,<br /><br />  PROTO_NUM /* ��ʾЭ������ */<br />};<br /><br />int nCntProto[PROTO_NUM];</font></pre><br />��������д���ĺô����ڣ�<b>û���κ�һ��</b>Magic Number������������ĳ��ͳ��ֵ����ѭ���������飬��ʹ�õ��Ƕ���õĳ�����<br />����������������Ҫ�����µ�Э�飬ֻҪ��enum��������Ӧ��enum�������ɣ���Ҫ�ǵñ�֤PROTO_NUMλ��enum�����ĩβ��������PROTO_NUM���Զ��������������������Ĵ��뼸�������ܵ�Ӱ�졣<br /><br />������<b>C++�Ĳ���˵��</b><br />������������ͬʱ������C��C++������������ĳЩC++����Ա����������ԭʼ���飬����STL�������࿴�����Ƚ�˳�ۡ���Ҳûɶ���ϵ��ֻҪ��������������������޸�Ϊ���£������Ĵ�������վɡ�<br /><font face="Courier New"><br />std::vector&lt;int&gt; vctCntProto(PROTO_NUM);<br /></font><div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/04/c-cxx-enum-idiom.md">2009/04/c-cxx-enum-idiom.html</a>
</div>
</div>
</body>
</html>
