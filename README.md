# Azure-Service-Bus-Logic-App-to-Blob-Data-Lake
This article shows you how to send messages to Azure Service Bus and consume it in C#, Blob, and Data Lake Store (gen1).

We start from the blog: https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-dotnet-get-started-with-queues. After creating a Service Bus in Azure Portal, we build a message sender and receiver, so we can test the Service Bus/ Name Space and Queue working as desired.

Next, we create an Azure Storage Account for Blob usage. Then we create our first Logic App that has a trigger on the queue and two actions: Get Messages from the Queue and ForEach to save the message in the blob.

Once the blob writing successful, we create the Azure Data lake Store (Gen 1) and the second Logic App that has the same trigger and the first action. The last action is to Append a message to ADLS file sequentially. Before we run the Message Sender, we staged an empty file, test.txt at the location of ADLS /messages. Now we send the messages to the queue and in 3 minutes, we see the Logic App trigged and messages are written into the file.

