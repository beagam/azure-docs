---
title: 'Tutorial: Azure Active Directory integration with Kantega SSO for Bamboo | Microsoft Docs'
description: Learn how to configure single sign-on between Azure Active Directory and Kantega SSO for Bamboo.
services: active-directory
author: jeevansd
manager: CelesteDG
ms.reviewer: celested
ms.service: active-directory
ms.subservice: saas-app-tutorial
ms.workload: identity
ms.topic: tutorial
ms.date: 03/25/2019
ms.author: jeedes
---
# Tutorial: Azure Active Directory integration with Kantega SSO for Bamboo

In this tutorial, you learn how to integrate Kantega SSO for Bamboo with Azure Active Directory (Azure AD).
Integrating Kantega SSO for Bamboo with Azure AD provides you with the following benefits:

* You can control in Azure AD who has access to Kantega SSO for Bamboo.
* You can enable your users to be automatically signed-in to Kantega SSO for Bamboo (Single Sign-On) with their Azure AD accounts.
* You can manage your accounts in one central location - the Azure portal.

If you want to know more details about SaaS app integration with Azure AD, see [What is application access and single sign-on with Azure Active Directory](../manage-apps/what-is-single-sign-on.md).
If you don't have an Azure subscription, [create a free account](https://azure.microsoft.com/free/) before you begin.

## Prerequisites

To configure Azure AD integration with Kantega SSO for Bamboo, you need the following items:

* An Azure AD subscription. If you don't have an Azure AD environment, you can get a [free account](https://azure.microsoft.com/free/)
* Kantega SSO for Bamboo single sign-on enabled subscription

## Scenario description

In this tutorial, you configure and test Azure AD single sign-on in a test environment.

* Kantega SSO for Bamboo supports **SP and IDP** initiated SSO

## Adding Kantega SSO for Bamboo from the gallery

To configure the integration of Kantega SSO for Bamboo into Azure AD, you need to add Kantega SSO for Bamboo from the gallery to your list of managed SaaS apps.

**To add Kantega SSO for Bamboo from the gallery, perform the following steps:**

1. In the **[Azure portal](https://portal.azure.com)**, on the left navigation panel, click **Azure Active Directory** icon.

	![The Azure Active Directory button](common/select-azuread.png)

2. Navigate to **Enterprise Applications** and then select the **All Applications** option.

	![The Enterprise applications blade](common/enterprise-applications.png)

3. To add new application, click **New application** button on the top of dialog.

	![The New application button](common/add-new-app.png)

4. In the search box, type **Kantega SSO for Bamboo**, select **Kantega SSO for Bamboo** from result panel then click **Add** button to add the application.

	![Kantega SSO for Bamboo in the results list](common/search-new-app.png)

## Configure and test Azure AD single sign-on

In this section, you configure and test Azure AD single sign-on with Kantega SSO for Bamboo based on a test user called **Britta Simon**.
For single sign-on to work, a link relationship between an Azure AD user and the related user in Kantega SSO for Bamboo needs to be established.

To configure and test Azure AD single sign-on with Kantega SSO for Bamboo, you need to complete the following building blocks:

1. **[Configure Azure AD Single Sign-On](#configure-azure-ad-single-sign-on)** - to enable your users to use this feature.
2. **[Configure Kantega SSO for Bamboo Single Sign-On](#configure-kantega-sso-for-bamboo-single-sign-on)** - to configure the Single Sign-On settings on application side.
3. **[Create an Azure AD test user](#create-an-azure-ad-test-user)** - to test Azure AD single sign-on with Britta Simon.
4. **[Assign the Azure AD test user](#assign-the-azure-ad-test-user)** - to enable Britta Simon to use Azure AD single sign-on.
5. **[Create Kantega SSO for Bamboo test user](#create-kantega-sso-for-bamboo-test-user)** - to have a counterpart of Britta Simon in Kantega SSO for Bamboo that is linked to the Azure AD representation of user.
6. **[Test single sign-on](#test-single-sign-on)** - to verify whether the configuration works.

### Configure Azure AD single sign-on

In this section, you enable Azure AD single sign-on in the Azure portal.

To configure Azure AD single sign-on with Kantega SSO for Bamboo, perform the following steps:

1. In the [Azure portal](https://portal.azure.com/), on the **Kantega SSO for Bamboo** application integration page, select **Single sign-on**.

    ![Configure single sign-on link](common/select-sso.png)

2. On the **Select a Single sign-on method** dialog, select **SAML/WS-Fed** mode to enable single sign-on.

    ![Single sign-on select mode](common/select-saml-option.png)

3. On the **Set up Single Sign-On with SAML** page, click **Edit** icon to open **Basic SAML Configuration** dialog.

	![Edit Basic SAML Configuration](common/edit-urls.png)

4. On the **Basic SAML Configuration** section, if you wish to configure the application in **IDP** initiated mode, perform the following steps:

    ![Screenshot shows the Basic SAML Configuration, where you can enter Identifier, Reply U R L, and select Save.](common/idp-intiated.png)

    a. In the **Identifier** text box, type a URL using the following pattern:
    `https://<server-base-url>/plugins/servlet/no.kantega.saml/sp/<uniqueid>/login`

    b. In the **Reply URL** text box, type a URL using the following pattern:
    `https://<server-base-url>/plugins/servlet/no.kantega.saml/sp/<uniqueid>/login`

5. Click **Set additional URLs** and perform the following step if you wish to configure the application in **SP** initiated mode:

    ![Screenshot shows Set additional U R Ls where you can enter a Sign on U R L.](common/metadata-upload-additional-signon.png)

    In the **Sign-on URL** text box, type a URL using the following pattern:
    `https://<server-base-url>/plugins/servlet/no.kantega.saml/sp/<uniqueid>/login`

	> [!NOTE]
	> These values are not real. Update these values with the actual Identifier, Reply URL, and Sign-On URL. These values are received during the configuration of Bamboo plugin which is explained later in the tutorial.

6. On the **Set up Single Sign-On with SAML** page, in the **SAML Signing Certificate** section, click **Download** to download the **Federation Metadata XML** from the given options as per your requirement and save it on your computer.

	![The Certificate download link](common/metadataxml.png)

7. On the **Set up Kantega SSO for Bamboo** section, copy the appropriate URL(s) as per your requirement.

	![Copy configuration URLs](common/copy-configuration-urls.png)

	a. Login URL

	b. Azure AD Identifier

	c. Logout URL

### Configure Kantega SSO for Bamboo Single Sign-On

1. In a different web browser window, sign in to your Bamboo  on-premises server as an administrator.

1. Hover on cog and click the **Add-ons**.

	![Screenshot shows Add-ons selected from the Settings menu.](./media/kantegassoforbamboo-tutorial/addon1.png)

1. Under Add-ons tab section, click **Find new add-ons**. Search **Kantega SSO for Bamboo (SAML & Kerberos)** and click **Install** button to install the new SAML plugin.

	![Screenshot shows Bamboo Administration with Kantega S S O for Bamboo selected.](./media/kantegassoforbamboo-tutorial/addon2.png)

1. The plugin installation will start.

	![Screenshot shows Installing progress for Kantega S S O for Bamboo.](./media/kantegassoforbamboo-tutorial/addon21.png)

1. Once the installation is complete. Click **Close**.

	![Screenshot shows the Close button.](./media/kantegassoforbamboo-tutorial/addon33.png)

1. Click **Manage**.

	![Screenshot shows the Manage button.](./media/kantegassoforbamboo-tutorial/addon34.png)

1. Click **Configure** to configure the new plugin.

	![Screenshot shows User-installed add-ons with Configure selected.](./media/kantegassoforbamboo-tutorial/addon3.png)

1. In the **SAML** section. Select **Azure Active Directory (Azure AD)** from the **Add identity provider** dropdown.

	![Screenshot shows Kantega Single Sign-On with Azure A D selected as the identity provider.](./media/kantegassoforbamboo-tutorial/addon4.png)

1. Select subscription level as **Basic**.

	![Screenshot shows Prepare Azure A D with Basic selected.](./media/kantegassoforbamboo-tutorial/addon5.png)

1. On the **App properties** section, perform following steps:

	![Screenshot shows the App properties section where you can provide the information in this step.](./media/kantegassoforbamboo-tutorial/addon6.png)

	a. Copy the **App ID URI** value and use it as **Identifier, Reply URL, and Sign-On URL** on the **Basic SAML Configuration** section in Azure portal.

	b. Click **Next**.

1. On the **Metadata import** section, perform following steps:

	![Screenshot shows the Metadata import section where you can browse to a metadata file.](./media/kantegassoforbamboo-tutorial/addon7.png)

	a. Select **Metadata file on my computer**, and upload metadata file, which you have downloaded from Azure portal.

	b. Click **Next**.

1. On the **Name and SSO location** section, perform following steps:

	![Screenshot shows the Name and S S O location where Azure A D is the identity provider name.](./media/kantegassoforbamboo-tutorial/addon8.png)

	a. Add Name of the Identity Provider in **Identity provider name** textbox (e.g Azure AD).

	b. Click **Next**.

1. Verify the Signing certificate and click **Next**.

	![Screenshot shows Signature verification.](./media/kantegassoforbamboo-tutorial/addon9.png)

1. On the **Bamboo user accounts** section, perform following steps:

	![Screenshot shows Bamboo user accounts where you have the option to create users.](./media/kantegassoforbamboo-tutorial/addon10.png)

	a. Select **Create users in Bamboo's internal Directory if needed** and enter the appropriate name of the group for users (can be multiple no. of groups separated by comma).

	b. Click **Next**.

1. Click **Finish**.

	![Screenshot shows the Summary page.](./media/kantegassoforbamboo-tutorial/addon11.png)

1. On the **Known domains for Azure AD** section, perform following steps:

	![Screenshot shows the Known domains for Azure A D where you can perform these steps.](./media/kantegassoforbamboo-tutorial/addon12.png)

	a. Select **Known domains** from the left panel of the page.

	b. Enter domain name in the **Known domains** textbox.

	c. Click **Save**.

### Create an Azure AD test user

The objective of this section is to create a test user in the Azure portal called Britta Simon.

1. In the Azure portal, in the left pane, select **Azure Active Directory**, select **Users**, and then select **All users**.

    ![The "Users and groups" and "All users" links](common/users.png)

2. Select **New user** at the top of the screen.

    ![New user Button](common/new-user.png)

3. In the User properties, perform the following steps.

    ![The User dialog box](common/user-properties.png)

    a. In the **Name** field enter **BrittaSimon**.
  
    b. In the **User name** field type `brittasimon@yourcompanydomain.extension`  
    For example, BrittaSimon@contoso.com

    c. Select **Show password** check box, and then write down the value that's displayed in the Password box.

    d. Click **Create**.

### Assign the Azure AD test user

In this section, you enable Britta Simon to use Azure single sign-on by granting access to Kantega SSO for Bamboo.

1. In the Azure portal, select **Enterprise Applications**, select **All applications**, then select **Kantega SSO for Bamboo**.

	![Enterprise applications blade](common/enterprise-applications.png)

2. In the applications list, select **Kantega SSO for Bamboo**.

	![The Kantega SSO for Bamboo link in the Applications list](common/all-applications.png)

3. In the menu on the left, select **Users and groups**.

    ![The "Users and groups" link](common/users-groups-blade.png)

4. Click the **Add user** button, then select **Users and groups** in the **Add Assignment** dialog.

    ![The Add Assignment pane](common/add-assign-user.png)

5. In the **Users and groups** dialog select **Britta Simon** in the Users list, then click the **Select** button at the bottom of the screen.

6. If you are expecting any role value in the SAML assertion then in the **Select Role** dialog select the appropriate role for the user from the list, then click the **Select** button at the bottom of the screen.

7. In the **Add Assignment** dialog click the **Assign** button.

### Create Kantega SSO for Bamboo test user

To enable Azure AD users to sign in to Bamboo, they must be provisioned into Bamboo. In case of Kantega SSO for Bamboo, provisioning is a manual task.

**To provision a user account, perform the following steps:**

1. Sign in to your Bamboo on-premises server as an administrator.

1. Hover on cog and click the **User management**.

    ![Screenshot shows User Management selected from the Settings menu.](./media/kantegassoforbamboo-tutorial/user1.png)

1. Click **Users**. Under the **Add user** section, Perform following steps:

	![Screenshot shows the Add user pane where you can perform these steps.](./media/kantegassoforbamboo-tutorial/user2.png)

	a. In the **Username** textbox, type the email of user like Brittasimon@contoso.com.

	b. In the **Password** textbox, type the password of user.

	c. In the **Confirm Password** textbox, reenter the password of user.

	d. In the **Full Name** textbox, type full name of the user like Britta Simon.

	e. In the **Email** textbox, type the email address of user like Brittasimon@contoso.com.

	f. Click **Save**.

### Test single sign-on

In this section, you test your Azure AD single sign-on configuration using the Access Panel.

When you click the Kantega SSO for Bamboo tile in the Access Panel, you should be automatically signed in to the Kantega SSO for Bamboo for which you set up SSO. For more information about the Access Panel, see [Introduction to the Access Panel](https://support.microsoft.com/account-billing/sign-in-and-start-apps-from-the-my-apps-portal-2f3b1bae-0e5a-4a86-a33e-876fbd2a4510).

## Additional Resources

- [List of Tutorials on How to Integrate SaaS Apps with Azure Active Directory](./tutorial-list.md)

- [What is application access and single sign-on with Azure Active Directory?](../manage-apps/what-is-single-sign-on.md)

- [What is Conditional Access in Azure Active Directory?](../conditional-access/overview.md)