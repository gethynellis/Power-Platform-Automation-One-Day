---
lab:
    title: 'Lab 9.1: Build a business process flow'
    module: 'Module 9: Build business process flows'
---

Module 9: Build business process flows
================================

## Lab 9.1: Practice Lab – Build a business process flow

### Important Notice (Effective November 2020):
Common Data Service has been renamed to Microsoft Dataverse. Some terminology in Microsoft Dataverse has been updated. For example, entity is now table and field is now column. 

While the application is in the process of updating its user experience, some references to terminology like the Common Data Service (now **Dataverse**), entity (now **table**), field (now **column**), and record (now **row**) may be out of date. Please keep this in mind as you work through the labs. We expect to have our content fully up to date very soon. 

For more information and for a complete list of affected terms, please visit [What is Microsoft Dataverse?](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/data-platform-intro#terminology-updates)

Scenario
--------

You have been building automations to support your client Fabrikam’s knowledge
assessment process. The client is concerned that their users won’t be able to
create new knowledge assessments without your help. You need to create a guided
process to interact with the user and support their configuration of new
assessments. In this lab, you will enable the knowledge assessment entity for
business process flows and then build a business process flow.

## Exercise 1 – Prepare the Solution

### Task 1 – Add Columns to Knowledge Assessment table

1.  Navigate to <https://make.powerapps.com>.

2.  Make sure you are in the **Practice** environment you created.

3.  Select **Solutions**.

4.  Click to open the **Knowledge Assessment Solution.**.

5.  Click to open the **Knowledge Assessment** table.

6.  Click **+ New Column**.

7.  Enter **Passing Score (%)** for **Display Name**, select **Whole Number**
    for **Data Type** and click **Done**.

8.  Click **+ New Column**.

9.  Enter **Create Questions** for **Display Name** and select **Yes/No** for
    **Data Type**.

10. Click **SAve**.


12. Navigate back to the solution.

13. Click **Publish all customizations**.

### Task 2 – Add Column to Knowledge Assessment Form

1.  Make sure you still have the **Knowledge Assessment** table selected.

2.  Select the **Forms** tab and click on the **Main** form.

3.  Add the **Passing Score (%)** column to the form.

4.  Click **Save**.

5.  Click **Publish**.

6.  Click the back button.

7.  Navigate back to the solution.

8.  Click **Publish all customizations**.

************************************************************************

### Task 3 – Add Field to Knowledge Question

1.  Navigate to <https://make.powerapps.com>.

2.  Select the **Practice** environment you created.

3.  Select **Solutions**.

4.  Click to open the **Knowledge Assessment Solution.**.

5.  Click to open the **Knowledge Question** table.

6.  Select the **Columns** tab and click **+ Add Column**.

7.  Enter **Question Points** for **Display Name** and select **Whole Number**
    for **Data Type**.

8.  Click **+ Add** next to **Calculation or Rollup** and select **+
    Calculation**.

9.  Click **Save**.

10. If you receive the **Set Question Points** popup >> click **+ Add Action**, else on the **Currently editing the calculated coulmn** popup message >> click **Done**. Then click the newly added column **Question Points** from the column list and in the property pane click the **Open Calculation** >> click **" Add Action**.

11. Type **answer1points** and select the suggested column from the drop-down list.

12. Type **+** , type **answer2points** and select the suggested column from the drop-down list.

13. Repeat it for **answer3points** and **answer4points**. You action will look
    like the snippet below but with your unique organizational prefix.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
cre7f_answer1points + cre7f_answer2points + cre7f_answer3points + cre7f_answer4points
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

14.  Save the action by clicking on the checkmark button.

15.  Click **Save and Close**.

16.  Click **Done**.

### Task 4 – Add column to Knowledge Question Form

1.  Make sure you still have the **Knowledge Question** table selected.

2.  Select the **Forms** tab and click to open the **Main** form.

3.  Drag the **Question Points** column from the **Table Column** and drop it below the **Knowledge
    Assessment** column on the form.

4.  Click **Save**.

5.  Click **Publish**.

6.  Click the back button.

7.  Click on the solution name located in the navigation breadcrumbs.

8.  Click **Publish all customizations.**

### Task 5 – Add Column to Knowledge Assessment

1.  Select **Solutions** >> click on the **Knowledge Assessment Solution.** >> Click to open the **Knowledge Assessment** table.

2.  Select the **Columns tab** and click **+ Add column**

3.  Enter **Total Points** for **Display Name** and select **Whole Number** for
    **Data Type**.

4.  Click **+ Add** next to **Calculation or Rollup** and select **+ Rollup**.

5.  Click **Save**.

6.  On the **Currently editing the calculated coulmn** popup message >> click **Done**. Then click the newly added column **Total Points** from the column list and in the property pane click the **Open Calculation** >> Click **+ Add Related Entity**.

7.  Select **Knowledge Questions(Knowledge Assessment)** for **Related** and click the checkmark.

8.  Click **+ Add Aggregation**.

9.  Select **SUM** for **Aggregation Function**, select **(Knowledge Questions)Question Points** for
    **Aggregated Related Entity Field**, and click the checkmark.

10. Click **Save and Close**.

11. Click **Done**.

12. Click on the solution name.

13. Click **Publish all customizations**.

### Task 6 – Add Column to Knowledge Assessment Form

1.  Click on the **Knowledge Assessment Solution.** and then Select the **Knowledge Assessment** table.

2.  Select the **Forms** tab and click on the Main form.

3.  Drag the **Total Points** column from the **Table Column** list and drop it below the **Difficulty** column
    on the form.

4.  Click **Save**.

5.  Click **Publish**.

6.  Click the back button.

7.  Click on the solution name located in the navigation breadcrumbs.

8.  Click **Publish all customizations**.

****************************************************************************************
## Exercise 2 – Create Business Process Flow

### Task 1 – Create Business Process Flow

1.  Navigate to <https://make.powerapps.com> and make
    sure you are in your **Practice** environment.

2.  Click **Flows.**

3.  Switch to the **Business process flows** tab.

4.  Click **+ New.**

5.  Enter **Assessment Process** for Flow Name and choose **Knowledge
    Assessment** for table.

6.  Click **Create.**

7.  Select the stage and on **Properties** tab, enter **Knowledge
    Assessment** for **Display Name** and click **Apply**.

8.  Click the **Details** on the **Knowledge Assessment** stage.

9.  Select **Data Step \#1**.

10. Select **Passing Score (%)** for **Data Field** and click **Apply**.

11. Click **+ Add** and select **Add Data Step**.

12. Click on the **+** below the **Passing Score (%)** step.

13. Select the **New Step**, select **Total Points** for **Data Field**, and
    click **Apply**.

14. Select the **Components** tab, drag **Data Step** from the **Components**
    tab, and drop it below the **Total Points** step.

15. Select **Notify Manager** for **Data Field** and click **Apply**.

16. Drag **Data Step** from the **Components** tab and place it below the
    **Notify Manager** step.

17. Select **Create Questions** for **Data Field**, check the **Required**
    checkbox, and click **Apply**.

18. Add a new stage to the right of the **Knowledge Assessment** stage by
    dragging from the components tab.

19. Select the new stage, go to the **Properties** tab, enter **Activate** for
    **Display Name**, and click **Apply**.

20. Click **Details** of the **Activate** stage.

21. Select the **Data Step** inside the **Activate** stage.

22. Select **Status** for **Data Field** and click **Apply**.

23. Select the **Components** tab, drag **Data Step** from the **Components**
    tab, and drop it below the **Status** step.

24. Select **Approval Status** for **Data Field** and click **Apply**.

25. Click **Save this process** to save the **Business Process Flow**.

26. Click **Activate**.

27. Confirm activation.

28. Close the process editor.

### Task 2 – Test Business Process Flow

1.  Navigate to <https://make.powerapps.com>.

2.  Make sure you are in your **Practice** environment.

3.  Select **Apps** and click to open the **Knowledge Admin** application.

4.  Navigate to **Knowledge Assessments** and open **Test Assessment Four**.

5.  Existing records will not pick up the Business Process Flow you created.
    Click **Process** on the command bar and select **Switch Process** (you may have to click the ellipses (**...**) to see this option).

6.  Select the **Assessment Process** you created and click **OK**.

7.  The **Assessment Process** should now be visible on the form.

8.  Click **+ New**.

9.  New rows should show the new Business Process Flow immediately.

10. Enter **BPF Test Assessment** for **Title** and click **Save**.

11. Select the **Questions** tab and click **+ New Knowledge Question**.

12. Select **Simple** for **Question Type**.

13. Enter **Process Test Question One** for **Question**.

14. Enter **Answer One** for **Answer 1** and **50** for **Answer 1 Points**.

15. Enter **Answer Two** for **Answer 2** and **80** for **Answer 2 Points**.

16. Enter **Answer Three** for **Answer 3** and **0** for **Answer 3 Points**.

17. Enter **Answer Four** for **Answer 4** and **0** for **Answer 4 Points**.

18. Click **Save**.

19. Click on the browser back button.

20. Click on the **Knowledge Assessment** stage of the Business Process Flow.
    The steps for this stage will come into view in a pop-up from the Business
    Process Flow bar.

21. In the window for the Knowledge Assessment stage, enter **80** for **Passing
    Score**.

22. Click on the **Total Points** calculator icon.

23. Click **Recalculate**.

24. The **Total Points** should get recalculated.

25. Select **Yes** for **Notify Manager**.

26. Select **Yes** for **Create Questions**. Then click **Next stage.**

27. The process should move to the **Activate** stage.

28. Start a new browser window and navigate to <https://flow.microsoft.com>.

29. Expand **Action Items** and select **Approvals**.

30. You should have one new approval waiting for you. Click on the approval.

31. The Approval pane will open. Select **Approve** in **Choose your response**.

32. Provide **Comments** and click **Confirm**.

33. Go back to **Knowledge Admin** application and click on the **Refresh**
    button.

34. Click on the **Activate** stage of the Business Process Flow.

35. The Approval Flow should complete the approval and set the **Approval
    Status** to **Approved**.
