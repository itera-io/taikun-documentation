---
tags:
  - Manager
  - Users
hide:
  - tags
---

# **Users**

In **Users** tab is list of users for your organization. If you want change your settings, visit [**My Profile**](../my-profile).

For each user you can preview following:

* Id
* User Name
* Display Name
* E-mail
* Role
* Approved
* Partner
* Creation Name
* Projects
* Actions

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/users/users.png "Users")
  <figcaption>Fig .1: Users</figcaption>
</figure>

**Find User**

To find user easier you can sort the list by *User Name*, *Display Name*, *Role*, *Approved*, *Partner* and *Creation Date* or use the *Search* bar above the list.

## **Add User**

If you want to add a new user use![](https://cloud.tcpro.cz:30100/swift/v1/KEY*c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/users/add-user-btn.png)button in the upper right corner.

???+ warning
    You can create a new user with **User** or **Manager** role.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/users/add-user.png "Add New User")
  <figcaption>Fig .2: Add User</figcaption>
</figure>

*User Name* - only alphanumeric characters and dash allowed

*Display Name* - name displayed in upper right corner (upper/lowecase and spaces allowed), optional

*E-mail* - new user's e-mail address

???+ warning
    Token will be sent to the provided e-mail address and it expires in **3 hours**.

Token redirects the user to the page, where a [new password will be set](../login).

*Role* - choose between *Manager* and *User* role


## **Edit assigned Projects**

Use pencil :pencil2: in *Projects* column to assign user a project and update your changes.

???+ warning
    You can assign a project to user with **User** role only.

???+ info
    You can also assign the project to the user in [**Projects**](../projects/#assigned-users).

## **Actions**

### **Edit User**

*User Name* - change user's name

*Display Name* - change name displayed in upper right corner (upper/lowecase and spaces allowed)

*E-mail* - change user's e-mail address. User will then use this e-mail to login and can [confirm the e-mail](../my-profile#change-e-mail) in *My Profile*

*Role* - change role from *user* to *manager*. The change cannot be undone because you can't change manager's role

*Force User to Reset Password* - user will be automatically logged out and receive e-mail with reset password request

*User Disabled* - logout and lock the user

### **Delete User**

If you want to delete some user, use the bin icon![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle}.

???+ warning
    You can delete a user only with **User** role only.
