Validator
=========

用于校验的php工具类

require_once('./Validator.class.php');
$data = array('nickname' => 'heno' ,
        'realname' => 'steven',
        'age' => 25,
        'mobile' => '1521060426');

$validator = new Validator($data);

$validator->setRule('nickname', 'required');
//$validator->setRule('testrequired', 'required');
$validator->setRule('realname', array('length' => array(1,6), 'required'));
$validator->setRule('age', array('required', 'digit'));
$validator->setRule('mobile', array('mobile'));
$result = $validator->validate();

var_dump($result);
var_dump($validator->getResultInfo());
