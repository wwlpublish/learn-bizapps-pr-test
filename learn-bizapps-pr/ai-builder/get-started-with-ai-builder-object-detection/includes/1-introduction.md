Before following this course, we recommend to read the [Get Started with AI Builder]{.underline} module and read the documentation [What is AI Builder?](https://docs.microsoft.com/ai-builder/overview).

## Introduction to AI Builder Object detection

AI Builder Object detection is an AI model that you train to detect objects in pictures. AI models usually require providing sample of data to train before being able to perform predictions. Prebuilt models are pre-trained using a set of samples provided by Microsoft, so they are
right away ready to be used to predict.

When predicting, AI Builder Object detection will recognized the objects you submitted during the training phase thanks to [Azure Custom Vision Object detection](https://docs.microsoft.com/azure/cognitive-services/custom-vision-service/home) technology. Object detection can detect up to 500 different objects in a single model and support JPG, PNG, BMP image format or photo through the PowerApps control.

## What you can do with object detection

AI Builder Object detection provides object recognition capabilities to makers. Fully integrated with the rest of business platform, you can accelerate manual workflow and automate a wide range of scenarios only achieved with human intervention today.

### The first category of scenario is object counting.

Front-line audit workers take a picture of a set of products on shelves. Object detection provides the count for each product on the picture. This information can be used to update the inventory management software.

**Example:**

A consumer packaged goods company is sending auditors to takes pictures of their products on shelves for compliance detection. The auditor will take a picture which will be processed by AI Builder to extract the numbers of each products. Those numbers can be transmitted to the company in real-time to assess the super-market compliance.

### Brand logo recognition

A company wants to monitor the use of its logo and its brand on social media.

**Example:**

A company process images flagged with a specific hashtag and can detect the presence of their logo and see how it's being used. That process is run automatically through a flow.

### Object recognition in a learning scenario.

A field agent takes a picture of a product. The product is recognized, and the manual and additional information is automatically retrieved.

**Example:**

A company is sending technicians to repair industrial boilers. The technicians don't have to carry the manual and reference guides of all the boilers they might encountered. The technicians take a picture of the boiler and get access to the manual, expert in the company about this product.

## Summary

Now that you've learned about the basics behind the Object detection AI capability, you can create your first Object detection model.