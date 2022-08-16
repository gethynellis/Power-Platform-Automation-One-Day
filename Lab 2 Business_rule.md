---
lab:
    title: 'Lab 2 Configure a new business rule'
    module: 'Module 6: Introduction to automation'
---

Module 6: Introduction to automation
========================

## Lab 6.3: Practice Lab – Configure a new business rule

### Important Notice (Effective November 2020):
Common Data Service has been renamed to Microsoft Dataverse. Some terminology in Microsoft Dataverse has been updated. For example, entity is now table and field is now column. 

While the application is in the process of updating its user experience, some references to terminology like the Common Data Service (now **Dataverse**), entity (now **table**), field (now **column**), and record (now **row**) may be out of date. Please keep this in mind as you work through the labs. We expect to have our content fully up to date very soon. 

For more information and for a complete list of affected terms, please visit [What is Microsoft Dataverse?](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/data-platform-intro#terminology-updates)

Scenario
--------

You are a functional consultant for your organization Contoso. You are assigned
to work on a model-driven Knowledge Admin app for your client Fabrikam. In this
lab, you will create columns and use business rules to control visibility of the
columns without needing custom code.

## ALL EXERCISES ARE TO BE COMPLETED IN THE VIRTUAL MACHINE PROVIDED BY SKILLABLE (OR OTHER HOSTING PROVIDER)

## Exercise 1 - Prepare the solution

### Task 1 – Add Columns to Knowledge Question

1.  Navigate to <https://make.powerapps.com>.

2.  Make sure you are in the **Practice** environment you created. You will find the enviornment in the top right-hand corner of the screen.

3.  Select **Solutions** from the left-hand menu. Its the last option in the list

4.  Click to open the **Knowledge Assessment Solution.**

5.  Click tables from the Object list and click to open the **Knowledge Question** table.

5. Under the **Schema** section click on **Columns**

6.  Click **+ New Column**.

7.  Enter **Question Type** for **Display Name** and select **Choice** for
    **Data Type**.

8.  Click on the **Choice** from the data type dropdown dropdown and click **Choice** from the drop-downlist menu

10.  Under **Sync with global choice?** choose **No** 

12. Under the **Choice** section, enter  **Simple** under label and click **+ New Choice**.

13. Enter **Scenario** as the second label

11. From the **Required** dropdown, select **Business Required.**

12. Click **Save.** and wait for you changes to be saved

13. Click **+ Add Column**.

14. Enter **Scenario Description** for **Display Name**, select **Text Area**
    for **Data Type**, and click **Save**.

15. Click **Save Table**.

### Task 2 – Add Columns to Knowledge Question Form

1.  Make sure you still have the **Knowledge Question** table selected.

2.  Select the **Forms** option from the left hand Objects menu and click to open the **Main** form type. It can be consuing becuase all forms are called Information. Click on the information for the **Main** form type

3. Click on **+ Form field** at the top of the screen. This will list all fields in the **Knowledge Question** we can the add our newly created columns to the main form.

Note: You can adjust the screen using the screen size slider at the bottom of the screen

3.  Drag the **Question Type** column from the **Table columns** and drop it
    above the **Question** column on the form.

4.  Drag the **Scenario Description** column and drop it below the **Question
    Type** column.

5.  With **Scenario Description** selected, check **Hide.** from the properties menu on the left hand-side menu

6.  Uncheck **Show only unused table columns** and drag the **Knowledge
    Assessment** column and drop it below the **Owner** column on the form.

7.  Click **Save**. (Top right-hand side of the screen)

8.  Click **Publish**. (Top right-hand side of the screen)

9.  Click **Back.** (Top left-hand side of the screen)

10. Click **Back to solutions** to return to the solution page


11. Click **Publish all customizations.** Be patient with this it can take a while.

## Exercise 2 – Create Business Rule

### Task 1 – Create Question Type Business Rule

1.  Navigate to <https://make.powerapps.com>.

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions.**

4.  Click to open the **Knowledge Assessment Solution**

5.  Click to open the **Knowledge Question** table.

6.  Under the **Customizations** section Select the **Business Rules** tab and click **Add business rule**.

7.  Next to **New business rule** name at the top of the screen, select the
    dropdown carrot.

8.  Enter **Question Type Rule** for **Business Rule Name**. You can select the dropdown carrot again to collapse this section.

9.  Select the **Condition** and enter **Check Question Type** for **Display
    Name.**

10. Go to the **Rules** section, select **Question Type** for **Field**, select
    **Equals** for **Operator**, select **Value** for **Type**, and select
    **Scenario** for **Value**.

11. Click **Apply**.

12. Select the **Components** tab.

13. Drag **Set Visibility** action and place it on the **True** side (on the
    right side) of the condition.

14. Enter **Show Scenario Description** for **Display Name**, select **Scenario
    Description** for **Field**, select **Yes** for **Visible** and click
    **Apply**.

15. Select the **Components** tab.

16. Drag **Set Business Required** action and place it after the **Show Scenario
    Description** action.

17. Select the new action, enter **Make Scenario Required** for **Display
    Name**, select **Scenario Description** for **Field**, select **Business
    Required** for **Status** and click **Apply**.

18. Select the **Components** tab. Drag **Set Visibility** action and place it on the **False** side (below) of
    the condition.

19. Enter **Hide Scenario Description** for **Display Name**, select **Scenario
    Description** for **Field**, select **No** for **Visible** and click
    **Apply**.

20. Select the **Components** tab.

21. Drag **Set Business Required** action and place it after the **Hide Scenario
    Description** action.

22. Select the new action, enter **Remove Scenario Requirement** for **Display
    Name**, select **Scenario Description** for **Field**, select **Not Business
    Required** for **Status** and click **Apply**.

23. Select the **Components** tab.

24. Drag **Set Field Value** action and place it after the **Remove Scenario
    Requirement** action.

25. Select the new action, enter **Clear Field** for **Display Name**, select
    **Scenario Description** for **Field**, select **Clear** for **Type** and
    click **Apply**.

26. Change the **Scope** to **All Forms**. You can find the Scope icon in the command
    bar. By default, this is set to **Entity**. Select **All Forms** from the drop-down.

27. Click **Save the Rule**.

28. Click **Activate the Rule**.

29. On the Confirm activation message pane click **Activate** button.

30. Close the business rule designer page by clicking the **X** button on the top right of the browser.

31. Click **Done**.

### Task 2 – Test Business Rule

1.  Navigate to <https://make.powerapps.com> and make
    sure you are in your **Practice** environment.

2.  Select **Apps** and click on the **Knowledge Admin** Model-Driven
    application.

3.  Navigate to **Knowledge Assessments** >> Click **Play** button. Change the area to **Assessments** from the bottom left of the screen and click **+ New**.

4.  Enter **Test Assessment Four** for **Title**, select today’s date for
    **Start Date**, a month from today for **End Date**, and click **Save**.

5.  Select the **Questions** tab.

6.  Click **+ New Knowledge Question**.

7.  Type **Test Question** for **Question**.

8.  Select **Scenario** for **Question Type**. The **Scenario** column will come
    to view, and it will be required.

9.  Type **This is a test Scenario** in the **Scenario Description**.

10. Change the **Question Type** to **Simple**. The Scenario column will
    disappear.

11. Change the **Question Type** back to **Scenario**. The **Scenario
    Description** will come to view again and the text you entered will no
    longer be there.

12. Type **This is a test Scenario** for **Scenario Description**.

13. In the **Answers** section, enter **Test Answer One** for
    **Answer 1**, enter **20** for **Answer 1 Points.**

14. Click **Save**. You can close the model-driven app.
