phpģ������

## tmd_tpl.php
	һ��������Դ��PHPģ�����棬�򵥸�Ч��Ҳ�ʺ�ѧϰ����졣
	��Դ��http://www.tmdphp.com/
	
## tmd_tpl1.php
	����tmd_tpl�޸ģ����ӹ����������£�
	1.����assignObj($obj)����������������controller/action��������ȥ���Ͳ���Ҫÿ��������assign����
	$name = 'frogluo';
	$age = 32;
	$uid = 123456;
	$is_admin = 0;
	$this->view->assign('name',$name);
	$this->view->assign('age',$age);
	$this->view->assign('uid',$uid);
	$this->view->assign('is_admin',$is_admin);
	
	�ĳɣ�
	$this->name = 'frogluo';
	$this->age = 32;
	$this->uid = 123456;
	$this->is_admin = 0;
	$this->display();
	
	/**
	* �����ȷ�װһ��������������displayʱ�ų�ʼ����ͼ
	*/
	protected function display($tpl = '') {
		$this->view = new tmd_tpl ();
		$this->view->tpl_dir = PATH_PAGE_VIEW;
		$this->view->cache_dir = PATH_PAGE_CACHE;
		$this->view->cache_time = TPL_CACHE_TIME;
		$this->view->my_rep = array (
				'~__ROOT__~' => URL_HOST,
				'~__JSPATH__~' => URL_JS,
				'~__CSSPATH__~' => URL_CSS,
				'~__PLUGINPATH__~' => URL_PLUGIN,
				'~__IMAGEPATH__~' => URL_IMAGE,
				'~__VERSION__~' => UPDATE_TIME 
		);
		$this->view->assignobj ( $this );
		
		if ($tpl) {
			$this->view->display ( $tpl );
		} else {
			if (! $this->page_tpl) {
				$this->page_tpl = 'index.html';
			}
			$this->view->display ( $this->page_frame );
		}
		exit ();
	}
	
	2.�����õ�include/require��ģ���ļ��ϲ������ļ��
	���磬mail.tpl�����header.tpl,content.tpl,footer.tpl��
	���ɻ����ʱ����mail.tplһ���ļ�������header.tpl,content.tpl,footer.tpl�����ݡ�
	������������һЩ���ܣ��ر���ҳ��ֵñȽ������ʱ��