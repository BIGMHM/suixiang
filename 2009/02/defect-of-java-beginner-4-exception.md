<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>Java���ֵ�ͨ��[4]���쳣����ʹ�ò��� - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">Java���ֵ�ͨ��[4]���쳣����ʹ�ò���</a></h1>
<div class="post-info"><span class="date-header">2009-02-12</span><a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> <a href="../../tags/E7BC96E7A88B.Java.md" class="tag">���.Java</a> </div>
<hr>
<div class="post">
������һ�����������ˡ�<a href="../../2009/02/defect-of-java-beginner-3-code-style.md">���ϰ�ߵ�����</a>�������������Ĺ����쳣����Ļ��⡣<!--program-think--><br /><br />������<b>��catch����</b><br />���������ִ�����˱Ƚ��٣�һ�㷢���ڸ�ѧ��Java���߸ղμӹ������õ������ϡ�<br />������ν����catch���顱������catch������û�ж��쳣���κ�log���������쳣��Ϣ����������һ����������ȷ���У����ڲ鲻���κ�log��Ϣ��ֻ�ô�ͷ�����룬��������bug��<br /><br />������<b>û��ʹ��finally</b><br />�����ܶ�����catch���֮��ʹ��finally��䡣������try����п��ܻ��漰��Դ��������ͷš��������Դ����֮����Դ�ͷ�֮ǰ�׳��쳣���ͻᷢ����Դй¶����Դй¶�������ԣ�<a href="../../2009/02/defect-of-java-beginner-3-code-style.md#gc">��һ������</a>�Ѿ��Ĺ��ˣ���<br /><br />������<b>��ͳ��catch����</b><br />������Щ��Ϊ��ʡ�£�ֻ���Լ�ģ������������һ��try���飬Ȼ��catch(Exception)�����ܲ���ʲô�쳣������ͳһlog���¡����������ȡ���catch���顱�Ժã������ڲ��ܶԾ�����쳣���о��崦����һЩ�ɻָ����쳣��������ᵽ����ɥʧ�˻ָ��Ļ��ᡣ����Ҳ���ܵ��������ᵽ����Դй¶�����⡣<br /><br />������<b>ʹ�ú�������ֵ���д�����</b><br />������Щ�˷���Java���쳣���Ʋ��ã����ú�������ֵ����ʾ�ɹ�/ʧ�ܣ����緵��true��ʾ�ɹ�������false��ʾʧ�ܣ�����ֱ�ǡ����Ž���Ҫ���������˸о�����Cת��Java���˱Ƚ������д�ë�������������ᵼ�����¼������⣺<br />��������ֵһ��������ֵ�򲼶�ֵ��ʾ�����ݵ���Ϣ���ڼ�ª��<br />����һ�������ߺ����˴��󷵻��룬�ͻᵼ�º͡���catch���顱���Ƶ����⣻<br />������ͬһ�������Ķദ���ã�����Ҫ�Է���ֵ�����ظ��жϣ����´������ࣨ��������Ļ�����<a href="../../2009/02/defect-of-java-beginner-3-code-style.md#copy_and_paste">��һ������</a>Ҳ�Ѿ��Ĺ��ˣ���<br /><br />������<b>�����Checked Exception��Runtime Exception������</b><br />�����������Ƚ��ձ飬�ҷ��ֺܶ�2������Java�������������δ��ȫ���������ߵ����𡣿�������������ϸ˵һ�¡�<br />��������Java����������������������쳣���Ǳ�������ġ����С�Checked Exception�����ڱ�ʾ�ɻָ����쳣��Ҳ�������������쳣��������Runtime Exception����ʾ���ɻָ����쳣��Ҳ��������ʱ�쳣����Ҫ�ǳ���bug������������<b>����Ҫ</b>��飩�������������������˺ܶ����飨�����ܶ�Java��ţ�������ڱ�������Ҫ������֣��Ժ���ר�������������Ļ��⡣<br />����Ϊ�˱�����⣬�����Ҿ�һ��������˵����������Ҫдһ��Download���������ݴ����URL��String���������ض�Ӧ��ҳ�������ı�����ʱ���������������Ҫ����<br />����1����������URL������null��������ú����ĵ����߳�bug�ˣ����������bug�Ǻ���������ʱ���һָ��ġ���ʱ��Download���������׳�Runtime Exception������Download�����ĵ�����<b>��Ӧ��</b>����ȥ��������쳣����������<b>����</b>��¶������������JVM�Լ���ֹ���У���<br />����2����������URL������null���������������ַ�������һ���Ϸ���URL��ʽ�����������û���������£�����ʱ��Download���������׳�Checked Exception������Download�����ĵ����߱��벶����쳣��������Ӧ�Ĵ���������ʾ�û���������URL����<br /><br />����������Ǽ��ֳ�����Java�쳣��������á���һ��������������һ�¡�<a href="../../2009/05/defect-of-java-beginner-5-jvm.md">���������JVM���˽ⲻ��</a>����<div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/02/defect-of-java-beginner-4-exception.md">2009/02/defect-of-java-beginner-4-exception.md</a>
</div>
</div>
</body>
</html>
