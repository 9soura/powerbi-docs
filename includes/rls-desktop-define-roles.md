## Define roles and rules within Power BI Desktop

You can define roles and rules within Power BI Desktop. When you publish to Power BI, it will also publish the role definitions.

If you want to take advantage of dynamic security, you will need to enable the preview switch Enable cross filtering in both directions for DirectQuery. This will allow the ability to cross filter and apply the security filter in both directions.

![](./media/rls-desktop-define-roles/powerbi-desktop-preview-bi-directional-directquery.png)

To define security roles, you can do the following.

1.	Import data into your Power BI Desktop report, or configure a DirectQuery connection.

    > **Note:** You cannot define roles within Power BI Desktop for Analysis Services live connections. You will need to do that within the Analysis Services model.

2.	Select the **Modeling** tab.

3.	Select **Manage Roles**.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security.png)

4.	Select **Create**.

	![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-role.png)

5.	Provide a name for the role. 
6.	Select the table that you want to apply a DAX rule.
7.	Enter the DAX expressions. This expression should return a true or false. For example: [Entity ID] = “Value”.

    > **Note:** You can use *username()* or *userprincipalname()* within this expression. It is recommended to use *userprincipalname()* as that is more likely to match the login for Power BI. *Username()* will have the format of *DOMAIN\username* within Power BI Desktop.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-create-rule.png)

8.	After you have created the DAX expression, you can select the check above the expression box to validate the expression.

    ![](./media/rls-desktop-define-roles/powerbi-desktop-security-validate-dax.png)

9.	Select **Save**.

You cannot assign users to a role within Power BI Desktop. This is done within the Power BI service. You can enable dynamic security within Power BI Desktop by making use of the *username()* or *userprincipalname()* DAX functions and having the proper relationships configured.