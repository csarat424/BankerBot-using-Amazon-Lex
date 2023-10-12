BANKERBOT-USING-AMAZON-LEX

SERVICES USED - Amazon Lex, AWS Lambda, 

- Create an AWS Account

- Creating the initial bot

- After Logining into the AWS Console
    
- Navigate to the Amazon Lex service, which can be done by typing Lex into the search bar
    
- Select the Amazon Lex Service
    
- Make sure that you are in the V2 console for Amazon Lex, which is indicated by the version number in the URL - in this example my current AWS Region is set to N.Virginia (us-east-1)
    V2 - https://console.aws.amazon.com/lexv2/home?region=us-east-1
  
  - Select the Create Bot button on the top-right corner
![image](https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/ce8aca75-d8c9-45d3-89dd-91a77c8f7b9b)
- Type the bot name as BankerBot
    
  - For IAM permissions select the "Create a role... option"
    
  - For "COPPA implications" select "No"
    <img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/3afc4c1f-c5b7-43c0-b58b-716f8a704e0b">

  - Leave the rest to default parameters
    
  - Next, Add a language to the bot
![image](https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/30e7cbfd-49a6-472b-96d8-4ce19fc03e38)

- Creating First Intent
         
- Scroll down and open the Sample utterances panel and add the following utterances as shown below
![image](https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/7ec2e8ea-9c6c-4411-a2a6-de2bb03bb336)

  - Scroll down to Closing responses and fill the following fields as shown below
 
  - Then Save the intent

  - Now Build the Bot and Test the bot as shown below
![image](https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/52e47aef-842a-4e5c-b40b-5dd745a3376d)

- Try one similar to your utterances, such as "Help me" & phrase, such as "Good morning", the first utterance will be recognized and the second utterance will fail, resulting in a default Intent "FallbackIntent" as shown below.

  <img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/e4c48cbd-951d-4d72-b296-cb2ae06a60a3">
  
-	Next Create custom slots like checking, Saving, and Credit.

![image](https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/fae8e88e-5d92-4995-9fab-11c24b9c975c)

-	Next, Create another Intent named CheckBalance, with a description

  <img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/8829b6f3-f5a7-4009-80c4-436b83d81952">

  <img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/ed63c52d-cacd-4abf-a804-c41caa05a447">

  -	Scroll down to Sample utterances and enter the following utterances

  <img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/635ae0ca-8d2e-4e0d-9b7e-bd073c4e9557">
 
-	Scroll down until you can see the Slots pane and click on the Add slot button - for the Name enter accountType, and enter the following for the prompt:

  <img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/fb7a1d89-91cb-4902-bb1e-51ba2a654f94">

-	This time we will use one of the built-in slot types. Name – dateOfBirth, 
Slot type - AMAZON.Date, Prompts - For verification purposes, what is your date of birth?

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/47142cbe-09e3-426d-99fc-f0a48696b76f">

-	Then save, build and test the bot and let's try this out "I want to check my balance please". Amazon Lex will then prompt for the two pieces of information that it needs, that is, the account type and your date of birth. It does this using the prompts that you have defined in the intent slots
  
<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/08c03c4a-55e6-479d-adb8-777099d0a81b">

-	this time let’s try "What's the balance in my savings account?” This time Amazon Lex will only prompt you for your date of birth, as it already knows what the account type should be

-	this time let’s try "What's the balance in my savings account?” This time Amazon Lex will only prompt you for your date of birth, as it already knows what the account type should be

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/77a335b6-433e-42f1-995e-b7484b74b367">

-	Conversational FLow

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/48fd9399-43d6-4511-b239-567046be506f">

-	Visual Builder
    
<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/6d1fdf5e-7382-4829-a5ab-cee839abc1b2">

- Creating the Lambda Function for the Bot

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/f26e53b9-9f4b-40c3-bbb2-86798c33c8d9">

- Select Author from scratch option, Function name as BankingBotEnglish, Runtime -Python 3.8 or a later version of Python3 if v3.8 is not available
  
<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/1b26a04f-77d4-45e3-b5ca-217a0be89d4d">

-	scroll down to the Function code section double-click on lambda_function.py and include the code

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/b8d77ef6-96ba-476e-b5ec-c96da60cf01e">

-	Click on the Deploy button and the Lambda function will be ready to be invoked by Amazon Lex.
-	On the Amazon Lex console click on the BankerBot, then on the left-hand menu select the Aliases link, this will bring up aliases defined for the bot.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/3dda6790-c701-4f11-856d-4b95c82a3745">

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/b3afc401-53ba-4994-b4f3-23d2ba7d7fe5">

-	Select the TestBotAlias, this will bring up a dialogue that allows selecting the associated lambda function to this language. From the drop-down field, leave the Lambda function version or alias at the default $LATEST. Click the Save

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/b3856fa3-d6cf-43f4-9193-2dbd07b54bd0">

-	Now click on the Intents, and click on CheckBalance Intent.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/a8235d60-862f-4b6e-903c-3be4f51311a7">

-	Scroll down to the Fulfillment pane. In the successful fulfillment pane, click the advanced options.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/7848a835-689d-49e7-9996-0ee6e2b0f75b">

-	Go to the one marked Fulfillment Lambda code hook and click the checkbox to enable a fulfillment Lambda for this intent, then click on the Update

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/5be9f705-1020-4c27-b8b5-57f9569f3d36">

-	Then save, build and test the bot again, and ask for the balance for any of the accounts – and the result should display like below.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/f11031e8-b3bd-4713-b4f3-bef853300588">

-	for CheckBalance Intent, scroll to the Contexts pane. Under the Output contexts drop-down control choose the New Context tag.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/a99ac034-b18d-40e4-964b-39b790a527aa">

-	This will enable the ability to control the context. Now create a new context contextCheckBalance set the timeout to 5 turns or 90 sec and click ADD.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/2b407ebb-d122-4a5f-95bc-b0360ec07d94">

-	Then repeat the save/build/test cycle again and validate that the bot still does what it previously did -  the creation of an output context will not have any effect

-	Now create the new FollowupCheckBalance intent

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/0315720b-8cbd-42e5-8e09-d49323645d36">

-	In the description enter the following “Intent to allow a follow-up balance check request without authentication” and in the Contexts select “contextCheckBalance” as Input context.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/2e28a59c-240d-46e1-b823-3f80ec2f1456">

-	Under Sample utterances enter the following

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/fa72162a-dcb1-4a30-852c-bae1bec95425">

-	In Slots add a new slot called accountType, with a prompt of “For which account would you like your balance?” and a slot-type of accountType

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/8cb8e645-4390-4f52-8306-098b7e786754">

-	Add another new slot called dateOfBirth, with a prompt of “For verification purposes, what is your date of birth?” and a slot-type AMAZON.Date

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/fef73c5c-8e7a-4c69-9dd4-620fcb5ac2b5">

-	select the dateOfBirth slot, then click on the Advanced options button. scroll to the Default values pane and Enter the context “ #contextCheckBalance.dateOfBirth” and update slot.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/ecaf9e43-2088-4333-86f8-ca98fa851db3">

-	Go to the Fulfillment Lambda code hook option and click the checkbox to enable a fulfillment Lambda for this intent, then click on the Update options button.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/bb58b646-bc1e-4678-a5e6-0594774ab60d">

-	Then save, build and test the bot.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/59d67554-bca8-4762-9eba-3b5b145eb8d3">

- Create a New Intent “TranferFunds” with a description “Help  user Transfer funds between account”

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/83c828de-8ef7-4583-a570-bb86e28cc9a5">

-	Enter the following utterances.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/a0ef55ad-74fe-4356-b7d8-dbb67cff2b55">

-	Add three new slots namely- sourceAccountType, targetAccountType, transferAmount and fill the respective fields

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/f42bbf14-2297-4590-b276-0282cfcbd693">

-	In Confirmation prompts and decline responses open up the Prompts field, and enter as shown

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/1ec0d21a-1e32-4245-91ee-ab25da325f1c">

- Also, add the Closing responses as shown.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/61c72684-2f81-4b27-a9f0-671ca1b86b44">

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/83eaf2b5-3b8f-4339-b949-b918551c2e2a">

-	Then save, build and test the bot.

<img width="468" alt="image" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/951cdf02-c300-4dcf-a22c-69d84bbcaf4c">

-	Finally Cleanup All the resources to avoid charges. 



















































    


















