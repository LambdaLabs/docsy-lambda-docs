---
title: "Creating additional user accounts"
type: docs
tags:
- Ubuntu
---

By having their own accounts, users can manage their own files, data sets,
and programs, as well as manage their own
[Python virtual environments]({{< relref "/linux/create-python-virtual-environment" >}}),
[conda virtual environments]({{< relref "/linux/create-conda-virtual-environment" >}}),
and [Docker containers]({{< relref "/linux/install-docker-run-container" >}}).

Also, by having additional accounts, you can assign system administrator
privileges to other users.

You can add user accounts from the **Users** panel in **GNOME Settings**:

1. Press the
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-windows" viewBox="0 0 16 16">
     <path d="M6.555 1.375 0 2.237v5.45h6.555V1.375zM0 13.795l6.555.933V8.313H0v5.482zm7.278-5.4.026 6.378L16 16V8.395H7.278zM16 0 7.33 1.244v6.414H16V0z"/>
   </svg> key on your keyboard to open the **Activities** overview. Then, type `users`.

   {{% alert title="Tip" color="success" %}}
   The
   <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-windows" viewBox="0 0 16 16">
     <path d="M6.555 1.375 0 2.237v5.45h6.555V1.375zM0 13.795l6.555.933V8.313H0v5.482zm7.278-5.4.026 6.378L16 16V8.395H7.278zM16 0 7.33 1.244v6.414H16V0z"/>
   </svg> key on your keyboard is located between the **Ctrl** and **Alt** keys.

   <img src="/lib/images/super-key.svg" width="203" height="108" alt="">
   {{% /alert %}}

1. Click **Users** to open the **Users** panel in **GNOME Settings**.

1. Click **Unlock** at the top of the panel, then click **Add User**.

1. For **Account Type**, choose either **Standard** or **Administrator**.

   - **Standard** account users can create, modify, and delete only their own
     files, not system files or other users' files. Standard account users
     also can change their own settings only, not system settings or other
     users' settings.

   - **Administrator** account users have the same privileges as standard
     account users. However, administrator account users can also create,
     modify, and delete system files and other users' files. Administrator
     account users can also change their system settings and other users'
     settings.

1. For **Full Name**, enter the user's full name, that is, their "real" name
   or name they use to identify themselves.

1. For **Username**, enter the name the user will use to log into the system.
   This name will also be the name of the user's home directory, for example,
   `/home/username`.

1. Under **Password**, choose either **Allow user to set a password when they
   next login**, or **Set a password now**.

   If you choose to set a password now, in the **Password** field, enter a
   custom password, or click the icon to automatically generate a password.

1. Click **Add** at the top of the dialog to add the user.
