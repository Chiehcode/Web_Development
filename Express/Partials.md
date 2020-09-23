### Partials

在不同的 layout 中可能會有 `共同的網頁元件`，如 `header`、`footer`、`主選單`等。Partials 便是用來將這些共同的網頁元件整理成檔案，便於維護和再利用。

---

### Partials File Structure
Because partials are still templates, we are going to include them in the `views` folder, in their own sub-directory.

![image](https://ncoughlin.com/static/32a39dff02fb0f9d41dfa990a2d950b5/859af/3.png)

---

### Partials Samples

#### header.ejs
``` ejs
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>EJS App</title>
    <link rel="stylesheet" type="text/css" href="/app.css"
</head>
<body>
```
note that we have linked to our stylesheet here in the partials/header file, so we can now remove this from our other templates.

#### footer.ejs
```
</body>
</html>
```

---

### Linking Partials in Templates

```
<%- include("partials/header.ejs") %>
```

This command `include` is telling Express to pull the contents of the Partials and place it in place of this command.

---

Reference:
* https://ncoughlin.com/posts/express-ejs-styles-and-partials/
