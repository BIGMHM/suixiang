<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="zh-CN">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=gb18030" />
<meta name="generator" content="Python script by program.think@gmail.com" />
<meta name="provider" content="program-think.blogspot.com" />
<link type="text/css" rel="stylesheet" href="../../css/program-think.css" />
<title>C++�Ŀ���ֲ�ԺͿ�ƽ̨����[3]���쳣���� - �������Ĳ���</title>
</head>
<body>
<div id="main" style="width:100%;">
<h1><a href="../../index.md" title="�ص���ҳ">C++�Ŀ���ֲ�ԺͿ�ƽ̨����[3]���쳣����</a></h1>
<div class="post-info"><span class="date-header">2009-01-30</span><a href="../../tags/E7BC96E7A88B.C.md" class="tag">���.C</a> <a href="../../tags/E7BC96E7A88B.md" class="tag">���</a> </div>
<hr>
<div class="post">
������һ�����ӡ�<a href="../../2009/01/cxx-cross-platform-develop-2-language.md">�﷨</a>������ƪ�����ޣ�û���ü����쳣�����ڰѺ��쳣��صĲ��ֵ����ó���˵һ�¡�<!--program-think--><br /><br />������<b>С��new�����ڴ�ʧ��</b><br />�������ڵ���ʽ���������ɵĴ��룬���newʧ�ܻ᷵�ؿ�ָ�롣�ҵ����õ�Borland C++ 3.1�ƺ����������ģ��������ֱ�����Ӧ�ò�����ˡ������Ŀǰ�õı���������������Ϊ������Ͳ��ˡ�����Կ�������new���������׳�bad_alloc�쳣�����ڽ����쳣����<br />������΢��ʽһ��ı��������Ͳ��ǽ������ؿ�ָ���ˡ���new�����������ڴ�漱�����ձ�׼�Ĺ涨���μ�C++ 03��׼18.4.2�½ڣ�����Ӧ��ȥ����new_handler������ԭ��Ϊtypedef void (*new_handler)();������׼����new_handler���������������£�1���跨ȥ�����ڴ�����2���׳�bad_alloc�쳣��3������abort()����exit()�˳����̡�����new_handler�����ǿ��Ա��������õģ�ͨ������set_new_handler����������������Ϊ���������С�<br />��������������new�����ڴ�ʧ�ܣ��п������ֿ��ܣ�1�����ؿ�ָ�룻2���׳��쳣��3������������ֹ�������ϣ����Ĵ�����нϺõ���ֲ�ԣ���͵ð���������������ǵ���<br /><br />������<b>�����쳣���</b><br />�����쳣������ҿ�������һ���ö��������ſ���ȥ����<a href="../../2009/01/cxx-coding-standards-101-rules.md">��C++ Coding Standards - 101 Rules, Guidelines &amp; Best Practices��</a>�ĵ�75��������������Щ�����Ժ�ר�ſ�һ��C++�쳣�ʹ�������������ģ��Թ����������ձ�׼���μ�03��׼18.6.2�½ڣ������һ�������׵�������쳣û�а����ڸú������쳣�淶�У���ôӦ�õ���unexcepted()�����ǲ������б��������ɵĴ��붼���ر�׼������ĳЩ�汾��VC������������������Ҫ֧�ֵı��������쳣�淶�ϵ���Ϊ��һ�£��Ǿ͵ÿ���ȥ���쳣�淶������<br /><br />������<b>��Ҫ��ģ���׳��쳣</b><br />�����˴�˵��ģ����ָ��̬�⡣�����ĳ�������ж����̬�⣬��Ҫ���쳣�׵�ģ��ĵ�������֮�⡣�Ͼ�����C++��û��ABI��׼�����ƽ���Ҳδ�ػ��У�����ģ���׳��쳣���кܶ಻��Ԥ�ϵ���Ϊ��<br /><br />������<b>��Ҫʹ�ýṹ���쳣����SEH��</b><br />������������û����˵��SEH���Ǿ͵���û˵��������Ρ��������ǰϰ������SEH���������д��ƽ̨����֮ǰ��Ҫ�ĵ����ϰ�ߡ�������SEH�Ĵ���ֻ����Windowsƽ̨�ϱ���ͨ�����϶��޷���ƽ̨�ġ�<br /><br />������<b>����catch(...)</b><br />��������˵��catch(...)���ֻ�ܹ�����C++���쳣���ͣ����ڷ���Υ���������ȷ�C++�쳣������Ϊ���ġ�����ĳЩ����£�����ĳЩVC�����������������Υ���������Ҳ���Ա�catch(...)�������ԣ������ϣ��������ֲ�Ժã��Ͳ����ڳ����߼�����������catch(...)����Ϊ��<br /><br />������һ�����ӣ�׼����һ�º͡�<a href="../../2009/01/cxx-cross-platform-develop-4-hardware.md">Ӳ���йصĿ�ƽ̨����</a>����<div class="blogger-post-footer">
</div>
<hr>
<div class="copyright">
<h4>��Ȩ����</h4>
���������е�ԭ�����£����߽Ա�����Ȩ��ת�ر�����������������ֱ������������Գ�������ʽע������<a href="mailto:program.think@gmail.com">�������</a>�ͱ���ԭʼ��ַ��<br>
<a href="/2009/01/cxx-cross-platform-develop-3-exception.md">2009/01/cxx-cross-platform-develop-3-exception.md</a>
</div>
</div>
</body>
</html>
