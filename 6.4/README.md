gotest.go: 这个文件里面是创建了一个包，里面有一个函数实现了除法运算:
gotest_test.go: 这是我们的单元测试文件，但是记住下面的这些原则：
1文件名必须是 _test.go 结尾的，这样在执行 go test 的时候才会执行到相应的代码
2你必须 import testing 这个包
3所有的测试用例函数必须是 Test 开头
4测试用例会按照源代码中写的顺序依次执行
5测试函数 TestXxx() 的参数是 testing.T，我们可以使用该类型来记录错误或者是测试状态
6测试格式：func TestXxx (t *testing.T), Xxx 部分可以为任意的字母数字的组合，但是首字母不能是小写字母 [a-z]，例如 Testintdiv 是错误的函数名。
7函数中通过调用 testing.T 的 Error, Errorf, FailNow, Fatal, FatalIf 方法，说明测试不通过，调用 Log 方法用来记录测试的信息。



压力测试文件 webbench_test.go

执行命令 go test webbench_test.go -test.bench=".*"