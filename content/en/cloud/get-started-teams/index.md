---
title: "How do I get started using the Team feature?"
type: docs
tags:
- Team
- billing
- SSH
---

## Create a team

1. In the dashboard, click **Team** at the bottom-left of the dashboard. Then,
   click **Invite** at the top-right of the Team dashboard.

1. Enter the email address of the person you want to invite to your team.
   Select their role in the team, either an **Admin** or a **Member**. Then,
   click **Send invitation**.

   {{% alert title="Warning" color="warning" %}}
   **Be sure to invite only trusted persons to your team!**

   Currently, the only differences between the _Admin_ and _Member_ roles are
   that an _Admin_ can:

   - Invite others to the team.
   - Remove others from the team.
   - Modify payment information.
   - Change the team name.

   This means that a person with a _Member_ role can, for example:

   - Launch instances that will incur charges.
   - Terminate instances that should continue to run.
   {{% /alert %}}

   {{% alert title="Note" color="info" %}}
   You can't send an invitation to an email address already associated with a
   Lambda Cloud account. If you try to, you'll be presented with a message
   that says there is already a Lambda Cloud account associated with the email
   address you're trying to send an invitation to.

   {{< imgproc cannot-invite-user Resize "400x">}}{{< /imgproc >}}

   The person you're inviting to your team must first close their existing
   Lambda Cloud account before they can be invited to your team.
   {{% /alert %}}

1. The person you invited to your team will receive an email letting them know
   that they've been invited to a team on Lambda Cloud.

   In that email, they should click **Join the Team**.

   {{% alert title="Note" color="info" %}}
   Until the person you invited to your team accepts their invitation, they
   will be listed in the Team dashboard as **Invitation pending**.

   You can delete the invitation while it's pending by clicking **⋮** where
   the person is listed in your Team dashboard, then choosing **Delete
   invitation**.
   {{% /alert %}}

   {{% alert title="Note" color="info" %}}
   If the person you invited to your team doesn't receive their invitation,
   you have to delete their invitation then invite them again.
   {{% /alert %}}

In the Team dashboard of the person you invited to your team, the person will
see that they are on your team. In your Team dashboard, you'll see the person
you invited listed.

## Change a teammate's role

To change the role of a person on your team from _Member_ to _Admin_, click
**⋮** where the person is listed in your Team dashboard, then choose **Change
to Admin**.

Conversely, to change the role of a person on your team from _Admin_ to
_Member_, click **⋮** where the person is listed in your Team dashboard, then
choose **Change to Member**.

## Close a teammate's account

To close a teammate's account, click the **⋮** where your teammate is listed
in your Team dashboard. Then, choose **Deactivate user**.

{{% alert title="Warning" color="warning" %}}
**Carefully review the information in the dialog box that pops up.**
{{% /alert %}}

## Change team name

To change the name of your team, click **Settings** at the bottom-left of the
dashboard, then click **Edit team name**. Enter a new name for your team, then
click **Update team name**.
