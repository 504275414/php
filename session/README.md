php session�����ܴ��롣

�����µ�˼·��

1.ͨ��session_set_save_handlerע��ص���������DBSession

2.�Լ�ʵ��start,get,set�ȷ�������FileSession,MemcacheSession

3.����1��2���ַ�����ϣ���CookieSession


##�÷�

1.�����÷�

$session = Session::factory ('cookie');

$session->start( );//���������ٵ���

session->sset('name','frogluo');

session->sget('name');


$session = Session::factory ('cookie');

session->sget('name');


��

$ss = new CookieSession ();

$ss->sset('uid',30);

$ss->sget('uid');



2. �����Ѿ����ڵ�sid��������ʹ��flesh����ϴ��ļ�ʱ��������Ҫָ��sid��

$session = Session::factory ();

$session->start($sid);

session->sset('name','frogluo');

session->sget('name');
