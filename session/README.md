php session�����ܴ��롣

�Լ�ʵ��session���������µ�˼·��

1.ͨ��session_set_save_handlerע��ص���������DBSession

2.��ԭ�����ƽ��з�װ��ʵ��start,get,set�ȷ�������FileSession,MemcacheSession

3.����1��2���ַ�����ϣ���CookieSession

4.CookieSessionHandler.php��ͨ��ʵ��SessionHandlerInterface�ӿڣ�PHP5.4��֧�֡�

��ò�Ҫֱ��ʹ��$_SESSION��������ɥʧ����Ȩ�����ڽ�һ���Ż���

���ڰ�session�洢��cookie���ر�Ҫע�⣬ҳ��buffer�Ѿ��رյ�����£����������header��Ϣ��

 Cannot modify header information - headers already sent


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
