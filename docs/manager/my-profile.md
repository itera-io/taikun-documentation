---
tags:
  - Manager
  - My-Profile
hide:
  - tags
---

# **My Profile**

You can access your profile and its settings by clicking![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/dashboard/my-profile.png){: .middle} in the right upper corner of the page.

## **My Information**

Here you can see your *User Name*, *Organization Name*, *Subscription End Date*, *E-mail* and *Role*.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/my-profile/my-information.png "My Informaion")
  <figcaption>Fig .1: My information</figcaption>
</figure>

## **Settings**

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/my-profile/settings.png "Settings")
  <figcaption>Fig .2: Settings</figcaption>
</figure>

In **Settings** section you can:

* Change your password
* Change your e-mail
* Enable e-mail notifications from Taikun
* Delete Account

### **Change E-mail**

You just need to type your new e-mail, which you want to use in the future.

<figure markdown>
  ![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/my-profile/change-mail.png "Change e-mail")
  <figcaption>Fig .3: Change e-mail</figcaption>
</figure>

Your e-mail address is changed but not confirmed, which is indicated with red cross :heavy_multiplication_x: next to your e-mail in *My Information*.

<figure markdown>
  ![Not confirmed e-mail](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/my-profile/not-confirmed-mail.png "Not confirmed e-mail")
  <figcaption>Fig .4: Not confirmed e-mail</figcaption>
</figure>

Clicking the *Confirm E-Mail* button will send the confirmation token to the e-mail address provided by you. Use the link in the mail to confirm your mail. If the link redirects you to homepage of Taikun, please login first and click the link in the e-mail again.

Token expires after 1 hour and then you need to send it with *Confirm E-mail* button again.

<figure markdown>
  ![Confirmed e-mail](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/my-profile/mail-verified.png "Verified e-mail")
  <figcaption>Fig .5: Confirmed e-mail</figcaption>
</figure>

???+ info
    You can't change e-mail address until your current one is confirmed.

### **Change Password**

To change your password, you have to insert your current password (old) and new (different) one.

Password should contain at least 1 uppercase, 1 lowercase, 1 number, 1 non alphanumeric and minimum length is 6 signs.

???+ warning
    If you receive an error during changing the password, please check that it meets the conditions.

<figure markdown>
  ![Change Password](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/my-profile/change-password.gif "Change Password")
  <figcaption>Fig .6: Change password</figcaption>
</figure>

???+ warning
    After confirming the password (by clicking the update button), you are logged off and need to log in with the new password.

### **Delete Account**

If you no longer wish to use Taikun, permanently delete your account. You will lose all access to Taikun.

## **Owners configurations**

???+ warning
    Next section is for **OWNERS** only.

### **Configure Keycloak**

Use [**Keycloak**](https://www.keycloak.org) login to enhance security.

<figure markdown>
  ![Keycloak](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/manager/my-profile/owner-keycloak.png "Keycloak")
  <figcaption>Fig .7: Keycloak</figcaption>
</figure>

Fill in *Name*, *Link*, *Realms* *Name*, *Client* *Id* and *Client* *Secret*. If all fields are filled in correctly, you can **Save** the configuration.

### **Enable Keycloak**

If you have saved configuration, you can enable it. If you want to switch to default Taikun login, disable the configuration.

???+ warning
    Please keep in mind:

    * Keycloak is for your whole organization
    * You can use either keycloak or Taikun login, not both

???+ warning
    Keycloak mail address should be **SAME** as Taikun mail address (so Taikun recognizes user, his role and organization).

![](https://cloud.tcpro.cz:30100/swift/v1/KEY_c5d050a1634d4ed1984f3844813f1a1d/doc-images/icons/delete.png){: .middle} Delete keycloak - you can disable keycloak or delete it if you no longer want to use it
