# パスワードを忘れた際のフォーム

次のコードを利用して、パスワードを忘れた際のフォームを作成できます。

```twig
<form method="post" accept-charset="UTF-8">
 {{ csrfInput() }}
 <input type="hidden" name="action" value="users/send-password-reset-email">
 {{ redirectInput('') }}

 <h3><label for="loginName">Username or email</label></h3>
 <input id="loginName" type="text" name="loginName"
 value="{% if loginName is defined %}{{ loginName }}{% else %}{{ craft.app.user.rememberedUsername }}{% endif %}">

 {% if errors is defined %}
 <ul class="errors">
 {% for error in errors %}
 <li>{{ error }}</li>
 {% endfor %}
 </ul>
 {% endif %}

 <input type="submit" value="Submit">
</form>
```

