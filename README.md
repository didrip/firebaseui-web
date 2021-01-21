This is a fork of [`firebaseui`](https://github.com/firebase/firebaseui-web) which prevents self account creation when using email/password signin method.

fix was found by @sperochon https://github.com/firebase/firebaseui-web/issues/99#issuecomment-486873879s :

> 3b) Open the file javascript/widgets/handler/common.js and replace the content of first 'if' of function 'firebaseui.auth.widget.handler.common.handleSignInStart' with :
> 
> ```js
> if (firebaseui.auth.widget.handler.common.isPasswordProviderOnly(app)) {
>     firebaseui.auth.widget.handler.handle(
>         firebaseui.auth.widget.HandlerName.PASSWORD_SIGN_IN,
>         app,
>         container,
>         opt_email,
>         opt_infoBarMessage);
> } else ...
> ```

