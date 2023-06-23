# promise

Promise 对象用于表示一个异步操作的最终完成（或失败）及其结果值。


## 安装
### npm

下载扩展库
``` bash
npm i @aardiolib/promise
```

复制扩展库到用户库
``` bash
robocopy .\node_modules\@aardiolib\ .\lib\ /E
```

## 示例

简单示例
```js
import console;
import promise;
import win.ui;
/*DSG{{*/
mainForm = win.form(text="aardio form";right=973;bottom=619)
mainForm.add()
/*}}*/

mainForm.show();


var myFirstPromise = promise(function(resolve,reject){
	// 执行异步操作，最终调用以下任一项：
  	//
  	//   resolve(someValue)        // fulfilled
  	// or
  	//   reject("failure reason")  // rejected
	
	//当异步操作成功时，我们调用 resolve()，当异步操作失败时调用 reject()
	//在本例中，我们使用 setTimeout() 来模拟异步代码。
	mainForm.setTimeout(function(){
	    resolve("成功")
	},1)
})


myFirstPromise.then(function(successMessage){
	// successMessage 是我们在上面的 resolve() 函数中传递的任何内容。
  	console.log("Yay! " + successMessage)
},function(err){
	// err 是我们在上面的 reject() 函数中传递的任何内容。
	//或者是抛出的错误信息
  	console.log(err)
})


return win.loopMessage(); 
```

[更多示例](./example/)