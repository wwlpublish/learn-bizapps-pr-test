Artificial Intelligence (AI) is computers thinking and acting in a way that simulates a human. AI is a technology that takes information from its environment and responds based on what it learns. The goal of AI is to create a machine that can mimic human behavior.

AI is more than learning, it is knowledge representation, reasoning, and abstract thinking. Machine Learning (ML) is the subset of AI that takes the approach of teaching computers to learn for themselves, rather than teaching computers all that they need to know. ML is the foundation for modern AI.  ML focuses on identifying and making sense from the patterns and structures in data.

Microsoft provides a number of Machine Learning services to enhance data.

## Dynamics 365 AI apps

The solution architect needs to be aware of the prebuilt insights available with Dynamics 365 apps including:

- Dynamics 365 Sales Insights
- Dynamics 365 Customer Service Insights
- Dynamics 365 Customer Insights
- Dynamics 365 Fraud Protection

## Azure Cognitive Services

Cognitive Services is a suite of prebuilt AI services that developers can use to build AI solutions. Cognitive Services meets common AI requirements and allow you to add AI to your apps quickly without expertise in ML. The Cognitive Services APIs cover:

- Computer Vision
- Natural Language Processing
- Speech
- Decision
- Web Search

Cognitive Services are available as a set of REST APIs that can easily be consumed by applications. Essentially, Cognitive Services are off-the-shelf services that help you develop an AI-based solution more quickly and with less specialist expertise.

Microsoft has created connectors for Azure Cognitive Services for Power Apps and Power Automate:

- Content Moderator
- Computer Vision
- Custom Vision
- Face
- LUIS (Language Understanding)
- Text Analytics (including Sentiment, Named Entity Recognition, Key Phrase Extraction)
- Translator

> [!NOTE]
> The Cognitive Service connectors are premium connectors.

![Actions for the Text Analytics connector.](../media/7-text-analytics.png)

These connectors can be used to enhance data and application functionality

## Azure Machine Learning

Azure provides many different services  to create your own machine learning models when Cognitive Services does not meet your needs. You can build ML models using many different tools, languages, and frameworks.

![Machine Learning Tools, Languages, and Frameworks.](../media/7-ml.png)

ML is beyond the scope of this course. However, solution architects should be aware that Azure Machine Learning can allow developers to implement enterprise grade machine learning for scenarios not met by AI Builder or Cognitive Services.

## AI Builder

AI Builder is a component of the Power Platform solution that allows you to easily add AI to predict outcomes to help improve business performance without writing code. You do not need to understand ML or learn Python to use AI Builder. Microsoft makes it easy both to create AI models and then to consume those models in the Power Platform.

AI Builder takes the concept of Cognitive Services further to enable anyone to use AI in their apps and flows and to build their own ML models without any expertise in machine learning or having to write code.

With AI Builder, you can either:

- Use one of the prebuilt AI models supplied with AI Builder.
- Build and train your own AI model using your own data.

AI Builder has five model types for prediction, vision, and language:

- Category classification: Performs Natural Language Processing (NLP) on text data and classifies into separate categories.
- Entity extraction: Recognizes specific data in text data. Entity extraction transforms unstructured text into structured data that can be used in apps and flows.
- Form processing: Reads and extracts information from documents such as invoices and purchase orders.
- Object detection: Finds objects within images.
- Prediction: Analyzes patterns in historical data to predict the outcome of new data.

![AI Builder model types.](../media/7-ai-builder-model-types.png)

AI Builder has the following pre-trained models:

- Category Classification: Classifies text into categories associated with customer feedback, such as compliments, issues, and pricing.
- Entity Extraction: Recognizes and extracts standard business objects in data
- Key Phrase Extraction: Identifies the main talking points from a piece of text
- Language Detection: Identifies the language used in a piece of text.
- Sentiment analysis: Detects whether the message in a piece of text has a positive or negative emotion.
- Text translation: Translates text from one language into another language.
- Business Card Reader: Extracts information from an image of a business card.
- Text Recognition: Extracts words from documents and images.
- Receipt Processing: Extracts details from pictures of printed and handwritten receipts.

![AI Builder Prebuilt models.](../media/7-ai-builder-prebuilt-models.png)

Canvas apps can use prebuilt models and custom models to enhance data. You could use an AI Builder model to analyze text that a user has entered. You can take a picture with a canvas app and use an AI Builder model to extract the text from the image or to detect objects in the image.

You can use AI Builder models in two ways with a canvas app:

- By adding AI Builder model controls to a screen
- By using AI Builder models through the formula bar

Power Automate can use all the prebuilt models and any custom models in AI Builder to enhance data. You can trigger a Power Automate flow when a record is created, or an image stored. There is an AI Builder connector that you add to a flow to access the models. For example, Power Automate can categorize a new record or predict what will happen to a newly created record.
