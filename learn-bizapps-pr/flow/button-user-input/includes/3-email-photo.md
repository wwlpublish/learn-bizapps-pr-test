Let's build a flow triggered by a button that will email your manager
your current location along with a photo of the vehicle you are using.

1.  [Sign in](https://flow.microsoft.com/?azure-portal=true). 

1.  On the left vertical menu click on **+ Create**.

1.  On the top, you will see **Three ways to make a flow**. The first way is **Start from blank**. In that, you will see **Instant flow**. Click on it.

1.  Add **Notify Your Manager** as your flow Name and select **Manually trigger a flow** option to choose from.

1.  You then click **Create** to start building the flow.

1.  You will now be in the flow studio with the title and the Manually trigger a flow trigger already added.

    ![Notify manager trigger](../media/notify-manager-trigger.jpg)

1.  Click on **Manually trigger a flow** trigger and click on **+ Add an input**.

1.  Select File and rename **File Content** to **Image**.

1.  Click on **+ New step** and search for **Office 365 Users**. Under **Actions,** you should see **Get manager (V2)**, select it.

1. Click in **User (UPN)** and from the **Dynamic content** select **User email**.

    ![Get manager](../media/get-manager-v2.jpg)

1. Click on **+ New step** and search for Outlook. Under **Actions** you should see **Send an email (V2)**, select it.

1. Click in **To** and in **Dynamic content** under **Get manager (V2)** select **Mail**. You may have to click on **See more** to find **Mail**.

	![mail](../media/mail.jpg)

1. Click in **Subject** and type in ```My current location and vehicle I am using```.

1. In **Body** type in the below:

	```Hi
	
	I have arrived at my current location and attached is a picture of the vehicle I am currently using.
	
	Address:
	```

1. In the **Body**, after Hi, select **Display Name** which is available in the **Dynamic content** under **Get manager (V2)**.

1. In the **Body**, below Address: select **Full address** which is available in the **Dynamic content** under **Manually trigger a flow**. You might have to scroll down a bit to find it. Here is a screenshot of what the Send an email (V2) action looks like.

    ![Send an email body](../media/send-email-body.jpg)

1. Click on **Flow checker,** which is available on the top right. If you have 0 errors and warnings, then click on the **X**. Next, click on **Save**.

1. You can now test the button using your smartphone. Open the app and click on the **Buttons** option on the bottom horizontal menu. You will now see the **Notify Your Manager** button. Click on it. For Image click on the **paper clip icon** and add an image by either taking a new picture of the camera or using an existing image from the photo library.

1. Your manager will get an email with an image attached.
