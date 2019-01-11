You can build button flows that use information like Global Positioning System (GPS) data, date information, or email. This information is available as *trigger tokens*. Trigger tokens are data points that are known and available to the device that a button flow is running on. These tokens change, based on factors like the current time or the current geographic location of the device.

For example, if you run a button flow on a phone, the phone probably knows the time at your current location, the date, and your current address. In other words, the time and date, and the address where the phone is located, are all determined when the button flow runs. They're automatically available for use in any button flows that are run on the device.

You can use these trigger tokens to build useful flows that minimize repetitive tasks like providing your location to someone or tracking how much time you spent on a particular job/service call.

### List of button trigger tokens

Here's the list of button trigger tokens that are available to you when you create button flows.

| Parameter | Description |
| --- | --- |
| City | The city where the device that's running the flow is located. |
| Country/Region | The country/region where the device that's running the flow is located.|
| Full address | The full address where the device that's running the flow is located. |
| Latitude | The latitude where the device that's running the flow is located. |
| Longitude | The longitude where the device that's running the flow is located. |
| PostalCode | The postal code where the device that's running the flow is located. |
| State | The state where the device that's running the flow is located. |
| Street | The street where the device that's running the flow is located. |
| Timestamp | The time in the area where the device that's running the flow is located. |
| Date | The date in the area where the device that's running the flow is located. |
| User name | The user name of the person who's signed in to the device that's running the flow. |
| User email | The email address of the person who's signed in to the device that's running the flow. |

## Create a button flow that uses trigger tokens

When you create a button, you can use trigger tokens to add rich functionality to it.

Let's create a button flow on a Google Android device. The button flow will use trigger tokens to send the date and your full address in a "Working from home" email to your boss.

Although the procedures in this unit show screenshots from an Android device, the experience is similar on Apple iOS and Windows Phone devices.

### Prerequisites

* A work or school email address, or a [Microsoft account](https://account.microsoft.com/about?refd=www.microsoft.com) that has access to Microsoft Flow
* The Microsoft Flow mobile app for [Android](https://aka.ms/flowmobiledocsandroid), [iOS](https://aka.ms/flowmobiledocsios), or [Windows Phone](https://aka.ms/flowmobilewindows)

### Create the button flow

1. Launch the Microsoft Flow mobile app and sign in using your organizational account.
1. Select **Browse**.

    ![Browse](../media/1.png)

1. Under the **Button** category, select the **Send a 'Working from home today' email to your manager** service.

    ![Send a 'Working from home today' email to your manager](../media/2.png)

1. Select **Use this template**.

    ![Use this template](../media/3.png)

1. On the **Send an email** card, select **Edit**.

    ![Edit](../media/3-5.png)

1. Select the **Subject** field, and enter *WFH today*. Notice that when you selected the **Subject** field, a list of tokens appeared. In the next step, you'll use one of these tokens to add the date to the subject of the email.

    ![Subject field](../media/4.png)

1. While the cursor is still in the **Subject** field, scroll through the list of tokens, and select **Date**. Notice that the date token now appears in the **Subject** field.

    ![Date token added to the Subject field](../media/6.png)

1. Scroll to the **Body** field, and select the default message so that you can add tokens there.

    ![Body field](../media/7.png)

1. Select the **Full address** token, and then select **Create**.

    ![Full address token added to the Body field](../media/8.png)

1. Select **Done**. Your button flow is now created.

    ![Done](../media/9.png)

## Run the button flow

> [!NOTE]
> This button flow will send your current location via email.

1. Select the **Buttons** tab at the bottom of the window. You'll see a list of the buttons that you have permissions to use. Select the button that represents the button flow that you just created:

    ![Button for the button flow](../media/10.png)

1. Select **Allow** to let the button flow access your device's location information.

    ![Allow](../media/11.png)

    In a few moments, you'll notice that the email was sent to your boss.

    ![Email was successfully sent](../media/12.png)

Congratulations! You just created a button flow that uses both the **Date** and **Full address** trigger tokens.
