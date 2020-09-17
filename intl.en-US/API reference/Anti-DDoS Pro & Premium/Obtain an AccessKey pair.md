# Obtain an AccessKey pair

This topic describes how to create an AccessKey pair for your Alibaba Cloud account or RAM user. When you call the Anti-DDoS Pro or Anti-DDoS Premium API, you must use the AccessKey pair to complete identity verification.

An AccessKey pair consists of an AccessKey ID and an AccessKey secret.

-   The AccessKey ID is used to verify the identity of the user.
-   The AccessKey secret is used to encrypt and verify the signature string. You must keep your AccessKey secret strictly confidential.

**Warning:** If the AccessKey pair of your Alibaba Cloud account is disclosed, the security of your resources are at risk. We recommend that you use a RAM user to call API operations. This minimizes the possibility of disclosing the AccessKey pair of your Alibaba Cloud account.

1.  Log on to the [Alibaba Cloud Management Console](https://home.console.aliyun.com) by using your Alibaba Cloud account.

2.  Move the pointer over your profile picture in the upper-right corner and click **AccessKey**.

3.  Obtain the AccessKey pair of an account.

    You can obtain the AccessKey pair of the Alibaba Cloud account or RAM user.

    -   Obtain the AccessKey pair of the Alibaba Cloud account.
        1.  In the **Security Tips** dialog box, click **Continue to manage AccessKey**.
        2.  On the Security Management page, click **Create AccessKey**.
        3.  In the Phone Verification dialog box, obtain the verification code, complete the verification process, and then click **OK**.
        4.  In the Create User AccessKey dialog box, expand **AccessKey Details** to view the **AccessKey ID** and **AccessKey secret**. You can click **Save AccessKey Information** to download the AccessKey pair.

            ![Create an AccessKey pair](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6415559951/p48003.png)

    -   Obtain the AccessKey pair of a RAM user.
        1.  In the **Security Tips** dialog box, click **Continue to manage AccessKey**.
        2.  On the [RAM console](https://ram.console.aliyun.com/users/new), create a RAM user on the Create User page. Skip this step if you want to obtain the AccessKey pair of an existing RAM user.
        3.  In the left-side navigation pane of the [RAM console](https://ram.console.aliyun.com/users/new), choose **Identities** \> **Users**.
        4.  Find the target RAM user and click the **user logon name**. You are navigated to the Authentication tab. In the User AccessKeys section, click **Create AccessKey**.
        5.  In the Phone Verification dialog box, obtain the verification code, complete the verification process, and then click **OK**.
        6.  In the Create AccessKey dialog box, view the **AccessKey ID** and **AccessKey secret**. You can also click **Download CSV File** or **Copy** to download or copy the AccessKey pair.

            ![Create an AccessKey pair](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/6415559951/p48004.png)


