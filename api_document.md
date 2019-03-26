Seems need to write a API document...<br>
I also not sure how to write that, so just a experiment version<br>

http://cccbd.top:8080/RESTHello
#### testapi
    @apiName testapi
    @api {get} /hello/{id}
    @apiParam {String} id id 
    @Produces("text/plain")
    @apiSuccess (200) {PlainText}
    @apiSuccessExample {PlainText} 
    hello id

#### login
    @apiName login
    @api {get/post} /login/send/
    @apiParam {String} username 
    @apiParam {String} password 
    @Produces("application/json")
    @apiSuccess (200) {int} status  status code
    @apiSuccess (200) {String} type  login type
    @apiSuccess (200) {String} username  login user name
    @apiSuccess (200) {String} message  appended text message.
    @apiSuccessExample {json} Success-Response:
    {
        "status": 200,
        "type": "success",
        "username": "myname",
        "message": "Login success"
    }
    @apiErrorExample {json} Error-Response:
    {
        "status": 403,
        "type": "fail",
        "username": "myname",
        "message": "Login fail"
    }

#### register
    @apiName register
    @api {get/post} /login/send/
    @apiParam {String} username 
    @apiParam {String} password 
    @apiParam {String} gender
    @apiParam {String} email  
    @Produces("plain/text")
    @apiSuccess (200) {list} account list
    @apiSuccessExample {PlainText} 
    Register success, your username is: username

#### get account list
    @apiName get account list
    @api {get} /account
    @apiParam {int} limit number limit 
    @Produces("application/json")
    @apiSuccessExample (200) {json} Success-Response:
    [
        {
            "name": "testname",
            "pass": "testpass",
            "id": "1",
            "gender": "male"
        },
        {
            "name": "chen",
            "pass": "123456",
            "id": "2",
            "gender": "female"
        }
    ]

<br><br><br>

###### todo
* change return value to json format
* test auto generate api document (fail)
* change framework to spring boot...?
* 邮件发送 (完成)
* 改写web.xml为autoscan模式