# beego-study

# Objective
Help me to manage to beego useful resouce

# Sample code
```go
// @router / [get]
func (c *MainController) Home() {
	c.Data["Website"] = "beego.me"
	c.Data["Email"] = "astaxie@gmail.com"
	c.TplName = "index.html"
}

// @router /login [get]
func (c *MainController) Login() {
	c.TplName = "login/index.html"
}

// @router /api0/:name/:message [get]
func (c *MainController) Api0(name, message string) {
	r := map[string]string{
		"hello":   name,
		"message": message,
	}
	c.Data["json"] = r
	c.Ctx.Output.Status = http.StatusAccepted
	c.ServeJSON()
}

// @router /api1/:name [get]
func (c *MainController) Api1(name string) {
	r := map[string]string{
		"hello": name,
	}
	c.Ctx.Output.Status = http.StatusAccepted
	c.Ctx.Output.JSON(r, false, false)
}

```

# How to get the params in request
https://beego.me/docs/mvc/controller/params.md#how-does-it-work%3F

# How to set response
https://beego.me/docs/mvc/controller/params.md#retrieving-data-from-request-body

# How to setup auto route
https://beego.me/docs/mvc/controller/router.md#annotations

# How to setup http tmplate
https://beego.me/docs/mvc/view/view.md

# How to setup error page
https://beego.me/docs/mvc/controller/errors.md

# How to setup login filter
https://beego.me/docs/mvc/controller/filter.md

# How to generate api document
https://beego.me/docs/advantage/docs.md#generate-document-automatically
