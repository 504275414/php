php session�����ܴ��롣

�Լ�ʵ��session���������µ�˼·��

1.ͨ��session_set_save_handlerע��ص���������DBSession

2.�Լ�ʵ��start,get,set�ȷ�������FileSession,MemcacheSession

3.����1��2���ַ�����ϣ���CookieSession

��ò�Ҫֱ��ʹ��$_SESSION��������ɥʧ����Ȩ�����ڽ�һ���Ż���


##�÷�

1.�����÷�

$session = Session::factory ('cookie');

//Ҫʹ��session����start
//���������ٵ���
$session->start( );

session->set('name','frogluo');

session->get('name');


$session = Session::factory ('cookie');

session->get('name');


��

$ss = new CookieSession ();

$ss->set('uid',30);

$ss->get('uid');



2.�����Ѿ����ڵ�sid��������ʹ��flesh����ϴ��ļ�ʱ��������Ҫָ��sid��

$session = Session::factory ();

$session->start($sid);

session->set('name','frogluo');

session->get('name');
