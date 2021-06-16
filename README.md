# 个人网站源代码

#### 问题
###### LoveIt主题主页头像问题：
修改文件`themes/LoveIt/layouts/partials/home/profile.html`中的`{{- $avatar = md5 . | printf "https://www.gravatar.com/avatar/%v?s=240&d=mp" -}}`改为`{{- $avatar = $profile.avatarURL -}}`

###### LoveIt主题评论系统问题：
修改文件`themes/LoveIt/layouts/conment.html`中的`{{- $comment := .Site.Params.page.comment -}}`改为`{{- $comment := .Site.Params.page.comment -}}`

###### LoveIt主题Gitalk`Error: Request failed with status code 403`问题
修改文件`themes/LoveIt/layouts/conment.html`中的
```
{{- $commentConfig = dict "id" .Date "title" .Title "clientID" $gitalk.clientId "clientSecret" $gitalk.clientSecret "repo" $gitalk.repo "owner" $gitalk.owner "admin" (slice $gitalk.owner) | dict "gitalk" | merge $commentConfig -}}
```
改为:(增加了proxy参数)
```
{{- $commentConfig = dict "id" .Date "title" .Title "clientID" $gitalk.clientId "clientSecret" $gitalk.clientSecret "repo" $gitalk.repo "owner" $gitalk.owner "proxy" $gitalk.proxy "admin" (slice $gitalk.owner) | dict "gitalk" | merge $commentConfig -}}
```
同时在config中添加gitalk中添加proxy="https://shielded-brushlands-08810.herokuapp.com/https://github.com/login/oauth/access_token"
目前我用的是这个proxy.
