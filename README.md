
# BankerBot-using-Amazon-Lex

SERVICES USED - Amazon Lex, AWS Lambda, 

Create an AWS Account

Creating the initial bot
  - After Logining into the AWS Console
    
  - Navigate to the Amazon Lex service, which can be done by typing Lex into the search bar
    
  - Select the Amazon Lex Service
    
  - Make sure that you are in the V2 console for Amazon Lex, which is indicated by the version number in the URL - in this example my current AWS Region is set to N.Virginia (us-east-1)
    V2 - https://console.aws.amazon.com/lexv2/home?region=us-east-1
  
  - Select the Create Bot button on the top-right corner
	 
    
  - Type the bot name as BankerBot
    
  - For IAM permissions select the "Create a role... option"
    
  - For "COPPA implications" select "No"
     
  - Leave the rest to default parameters
    
  - Next, Add a language to the bot
         
  
- Creating First Intent
         
  
- Scroll down and open the Sample utterances panel and add the following utterances as shown below
 

  - Scroll down to Closing responses and fill the following fields as shown below
 

  - Then Save the intent

  - Now Build the Bot and Test the bot as shown below
 
 

  - Try one similar to your utterances, such as "Help me" & phrase, such as "Good morning", the first utterance will be recognized and the second utterance will fail, resulting in a default Intent "FallbackIntent" as shown below.
    
 

-	Next Create custom slots like checking, Saving, and Credit.


 






















-	Next, Create another Intent named CheckBalance, with a description

  




-	Scroll down to Sample utterances and enter the following utterances
 
-	Scroll down until you can see the Slots pane and click on the Add slot button - for the Name enter accountType, and enter the following for the prompt:
 


-	This time we will use one of the built-in slot types. Name – dateOfBirth, 
Slot type - AMAZON.Date, Prompts - For verification purposes, what is your date of birth?
 

-	Then save, build and test the bot and let's try this out "I want to check my balance please". Amazon Lex will then prompt for the two pieces of information that it needs, that is, the account type and your date of birth. It does this using the prompts that you have defined in the intent slots
 

-	this time let’s try "What's the balance in my savings account?” This time Amazon Lex will only prompt you for your date of birth, as it already knows what the account type should be









 

-	Conversational FLow
 

-	Visual Builder
 

-	Creating the Lambda Function for the Bot
 

-	Select Author from scratch option, Function name as BankingBotEnglish, Runtime - Python 3.8 or a later version of Python3 if v3.8 is not available
 

-	scroll down to the Function code section double-click on lambda_function.py and include the code. 
 

-	Click on the Deploy button and the Lambda function will be ready to be invoked by Amazon Lex.
-	On the Amazon Lex console click on the BankerBot, then on the left-hand menu select the Aliases link, this will bring up aliases defined for the bot.

 


 

-	Select the TestBotAlias, this will bring up a dialogue that allows selecting the associated lambda function to this language. From the drop-down field, leave the Lambda function version or alias at the default $LATEST. Click the Save
 

-	Now click on the Intents, and click on CheckBalance Intent. 

 
-	Scroll down to the Fulfillment pane. In the successful fulfillment pane, click the advanced options. 
 

-	Go to the one marked Fulfillment Lambda code hook and click the checkbox to enable a fulfillment Lambda for this intent, then click on the Update

 

-	Then save, build and test the bot again, and ask for the balance for any of the accounts – and the result should display like below.
 

-	for CheckBalance Intent, scroll to the Contexts pane. Under the Output contexts drop-down control choose the New Context tag.

 

-	This will enable the ability to control the context. Now create a new context contextCheckBalance set the timeout to 5 turns or 90 sec and click ADD.
 

-	Then repeat the save/build/test cycle again and validate that the bot still does what it previously did -  the creation of an output context will not have any effect

-	Now create the new FollowupCheckBalance intent
 
-	In the description enter the following “Intent to allow a follow-up balance check request without authentication” and in the Contexts select “contextCheckBalance” as Input context.
 

-	Under Sample utterances enter the following
 
-	In Slots add a new slot called accountType, with a prompt of “For which account would you like your balance?” and a slot-type of accountType
 

-	Add another new slot called dateOfBirth, with a prompt of “For verification purposes, what is your date of birth?” and a slot-type AMAZON.Date

 

-	select the dateOfBirth slot, then click on the Advanced options button. scroll to the Default values pane and Enter the context “ #contextCheckBalance.dateOfBirth” and update slot.

 

-	Go to the Fulfillment Lambda code hook option and click the checkbox to enable a fulfillment Lambda for this intent, then click on the Update options button.
 

-	Then save, build and test the bot.

 
-	 Create a New Intent “TranferFunds” with a description “Help  user Transfer funds between account” 

-	Enter the following utterances.
 

-	Add three new slots namely- sourceAccountType, targetAccountType, transferAmount and fill the respective fields. 
 

-	In Confirmation prompts and decline responses open up the Prompts field, and enter as shown


-	 

-	Also, add the Closing responses as shown.
-	 
-	
-	 

-	Then save, build and test the bot.

-	 

-	Finally Cleanup All the resources to avoid charges.
![image](https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/4e2d085f-38e2-4298-9c56-7a3b36487b62)

