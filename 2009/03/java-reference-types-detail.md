<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>Java���ֽ��ף�ϸ˵�������� - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">Java���ֽ��ף�ϸ˵��������</a></h1>
<div class="post-info"><span class="date-header">2009-03-20</span><a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> <a href="../../tags/E7BC96E7A88B.Java.md" class="tag">���.Java</a> </div>
<hr>
<div class="post">
��ǰ��������ӡ�<a href="../../2009/03/java-performance-tuning-1-two-types.md" target="_blank">Java�����Ż�[1]���������� vs ��������</a>�����Ž������������ͺͻ��������ڴ洢�ϵ���������������������������˵���������ͱ������������õĶ���û������������׻��������Խ���ר����˵һ���������͵����ϸ�ڡ�<!--program-think-->���⣬Ҳ��<a href="../../2009/03/java-performance-tuning-1-two-types.md">ԭ�ȵ�����</a>�У����ڡ��������͵Ĵ洢��ʽ������޸���һ�£��ӵ��ͼ�������ڴ�������⡣<br />������ʵ���������͵ı����ǳ�������C/C++��ָ�롣Ϊ�����������ҲΪ�˴��ַ��㣬���ĺ�������ݣ����ѡ��������͵ı�������Ϊ<b>ָ��</b>�����ԣ������ԭ����C/C++���������콲�����ݶ�����˵Ӧ�úܺ���⣻����Ļ�������Ҫ����ĥ��ĥ�ˡ�<br /><br /><h2>�ﴴ������</h2><br />��������������<b>������</b>д����������򵥵���䣺<br /><font face="Courier New">StringBuffer str = new StringBuffer("Hello world");</font><br />��������򵥣���ʵ�����������������裺<br />�������ȣ�<u><font face="Courier New">new StringBuffer("Hello world")</font></u>��<b>��</b>��������һ���ڴ棬�Ѵ����õ�StringBuffer����Ž�ȥ��<br />������Σ�<u><font face="Courier New">StringBuffer str</font></u>������һ��ָ�롣���ָ�뱾���Ǵ洢��<b>ջ</b>�ϵģ���Ϊ���д��<b>������</b>������������ָ��ĳ��StringBuffer���͵Ķ��󡣻��߻�һ��˵�������ָ�������������ĳ��StringBuffer����ĵ�ַ��<br />������󣬵������<b>���ں�</b>����ֵ���ţ������߹���������Ҳ���ǰѸ��������һ���ڴ�ĵ�ַ�����str��ֵ��<br />������<a href="../../2009/03/java-performance-tuning-1-two-types.md">�ϴ�����</a>��ͼƬ���ó�����һ�£�<br /><center><img src="../../images/2009/03/OgAAADfJvtKaB8finO0otLgLKBqGUQ2lYJGlzQAZCE1qUybiJ9XKK8TrbaBfFVYT1g5DbqIza3sKbsWm2MjeZM4mWoEA15jOjE1kRvoUZjXROWyVUiJ7dUWGWSBV" width="480" alt="����ͼ���뷭ǽ" /></center><br /><br /><h2>�����ö���֮��ĸ�ֵ�������</h2><br />����ͨ��������ͼ�⣬����Ӧ������ָ������͸�ָ�����ָ���<b>����</b>��һ��ʲô��ϵ�˰ɡ�<br />�������ǽ��Ÿղŵ����ӣ���������ֵ�����⡣����������䣺<br />����<font face="Courier New">StringBuffer str2 = str;</font><br />���������ֵ�����ɶ��˼��ʵ���Ͼ��ǰ�str�ĵ�ַ���Ƹ�str2����ס���ǵ�ַ�ĸ��ƣ�StringBuffer������û�и��ơ���������ָ��ָ�����ͬһ��������<br />�����ٸ�һ��ʾ��ͼ�����£����컭��Щͼ�����ۻ��ˣ���<br /><center><img src="../../images/2009/03/OgAAAFBhvdXRlvyvQDGIx1SIbKQN0SJeETiM6NSzPxyDPhxj7ogBnwnANh3FbZuzWEQPOGL2adM1l8nNYxbDd9ZdU9AA15jOjNeEMKZWr7_YDfanK_l5_FgAwQH2" width="480" alt="����ͼ���뷭ǽ" /></center><br /><br />���������˸�ֵ���ж���ȵ����⣨����==��������Ҳ�ͼ��ˡ�������д������䡰<font face="Courier New">if(str2 == str)</font>��ʱ��ֻ���ж�����ָ���<b>ֵ</b>��Ҳ���Ƕ���ĵ�ַ���Ƿ���ȣ��������ж�<b>��ָ��Ķ���</b>�Ƿ�������ͬ��<br />����ʵ��������ָ���ֵ��ͬ����϶���ָ��ͬһ���������Զ������ݱض���ͬ������������������ͬ�Ķ������ǵĵ�ַ���ܲ�һ���������¡�����Ķ������֮�䣬��ַ�Ͳ�ͬ����<br /><br /><h2>��final����������</h2><br />��������������ͱ�����final���η�Ҳ�Ǻܶ��˸�����ĵط���ʵ����finalֻ������ָ���ֵ��Ҳ�����޶�ָ�뱣��ĵ�ַ���ܱ䣩�����ڸ�ָ��ָ��Ķ��������Ƿ��ܱ䣬�Ǿ͹ܲ����ˡ����ԣ�����������䣺<br />����<font face="Courier New">final StringBuffer strConst = new StringBuffer();</font><br />����������޸���ָ��Ķ�������ݣ����磺<br />����<font face="Courier New">strConst.append(" ");</font><br />��������<b>����</b>�޸�����ֵ�����磺<br />����<font face="Courier New">strConst = null;</font><br /><br /><h2>�ﴫ�ε�����</h2><br />�����������ͣ��ں��������У��Ĵ������⣬��һ���൱�������⡣��Щ����˵�Ǵ�ֵ����Щ����˵�Ǵ����á����Java����Ա������񾭷����ˡ����ԣ����������̸һ�¡��������Ͳ������ݡ������⡣<br />���������øղŵ����ӣ���������Ҫ�ѸղŴ�������һ���ַ�����ӡ���������ǻ�ʹ��������䣺<br /><font face="Courier New">System.out.println(str);</font><br />����������ʲô��˼����ʱ�����˵�ˡ�<br />������һ����⣺<br />������Ϊ������������str���ָ�룬ָ��˵���˾���һ����ַ��ֵ��˵���ٰ�һ�㣬���Ǹ�����������������⣬���Ǵ�ֵ�ķ�ʽ��Ҳ����˵���������ݵ���ָ�뱾�������Ǵ�ֵ�ġ�<br />�����ڶ�����⣺<br />������Ϊ����ȥ����StringBuffer���󣬰���������⣬���Ǵ����÷�ʽ�ˡ���Ϊ����ȷʵ�ǰѶ���ĵ�ַ��Ҳ�������ã������˽�ȥ��<br />����������ô���ˮ����ʵ������<b>������</b>����<b>��ֵ</b>�������Խ���ͨ���ؼ�ȡ��������<b>��ο���</b>���������ݵ�<b>����</b>����ͺñ�������ѧ�С���Ĳ��������ԡ�������������ӵķ�ʽȥ���������������������ӣ�������Բ����ķ�ʽȥ�۲��������������񲨶��������㲻̫��������ѧ��ǰ���⻰����û˵ <b>:-)</b><div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/03/java-reference-types-detail.md">2009/03/java-reference-types-detail.html</a>
</div>
</div>
</body>
</html>
