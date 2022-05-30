# **Users**

In **Users** tab is list of users for each organization. If you want change your settings, visit [**My Profile**](../my-profile).

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
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/users/users.png "Users")
  <figcaption>Figure.1: Users</figcaption>
</figure>

#### **Find User**

To find user easier you can sort the list by *User Name*, *Role* and *Organization Name* or use the *Search* bar above the list. To preview users from one organization, use *Select organization* button above left.


## **Add User**

If you want to add a new user use the![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/users/add-user-btn.png){: .middle} in the upper right corner.

???+ warning
    You can create a new user with **User** or **Manager** role.

<figure markdown>
  ![Add User](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/users/add-user.png "Add User")
  <figcaption>Figure.2: Add User</figcaption>
</figure>

*User Name* - only alphanumeric characters and dash allowed

*Display Name* - name displayed in upper right corner (upper/lowecase and spaces allowed), optional

*E-mail* - new user's e-mail address

*Organization* - enable button if you want to specify user's organization

*Role* - enable button if you want to specify user's role

???+ danger
    Token will be sent to the provided e-mail address and it expires in **3 hours**.

Token redirects the user to the page, where [a new password will be set](../login).

## **Projects**

## **Edit assigned** Projects

Use pencil :pencil2: in *Projects* column to assign user a project and update your changes.

<figure markdown>
  ![Assign](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/partner/users/assign.png "Assign")
  <figcaption>Figure.3: Assign</figcaption>
</figure>

???+ warning
    You can assign a project to a user with **User** role only**.**

???+ info
    You can also assign the project to the user in [Projects](../projects).


## **Actions**

### **Edit User**

*User Name* - change user's name

*Display Name* - change name displayed in upper right corner (upper/lowecase and spaces allowed)

*E-mail* - change user's e-mail address. User will then use this e-mail to login and can [confirm the e-mail](../my-profile#settings) in *My Profile*

*Role* - switch role between *user* and *manager*

*Force User to Reset Password* - user will be automatically logged out and receive mail with reset password request

*User Disabled* - logout and lock the user

*Approved by Partner* - if new user is not approved by partner, he won't be able to login

### **Delete User**

If you want to delete some user, use the bin icon![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png "Delete"){: .middle}.

???+ warning
    You can delete a user with **User** or **Manager** role.
