# BankerBot-using-Amazon-Lex

SERVICES USED - Amazon Lex, AWS Lambda, 

Create an AWS Account

Creating the initial bot
  - After Logining into the AWS Console
    
  - Navigate to the Amazon Lex service, which can be done by typing Lex into the search bar
    
  - Select the Amazon Lex Service
    
  - Make sure that you are in the V2 console for Amazon Lex, which is indicated by the version number in the URL - in this example my current AWS Region is set to N.Virginia (us-east-1)
    V2 - https://console.aws.amazon.com/lexv2/home?region=us-east-1
  
  - Select the Create bot button on the top-right corner
    <img width="1437" alt="Image1" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/8a534b55-830a-4636-b3b5-49b6f3a2d22c">
    
  - Type the bot name as BankerBot
    
  - For you IAM permissions select the "Create a role... option"
    
  - For "COPPA implications" select "No"
    <img width="1440" alt="Image2" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/727cb729-9d93-4fc3-836d-4a2fe6cfd294">
    
  - Leave the rest to default parameters
    
  - Next Add a language to the bot
    <img width="1438" alt="Image3" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/261bd006-895f-4c3f-bc9c-992c9cf9858d">
    
  - Creating First Intent
    <img width="1437" alt="Image4" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/f2093678-019f-4887-b145-3ccc7aec04c0">
    
  - Scroll down and open the Sample utterances panel and add the following utterences as shown in the fig below
    <img width="1439" alt="Image5" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/f2b2fa4d-171d-4801-9044-699ab4c929aa">

  - Scroll down to Closing reponses and fill the following feilds as shown in the fig below
    <img width="1435" alt="Image6" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/a84beae0-9fdb-46d6-b839-58f0a1b53049">

  - Then Save the intent

  - Now Build the Bot and Test the bot as shown below
    <img width="1436" alt="Image7" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/7615c886-02b5-44ef-b4ba-937f34d9907f">

  - Try one similar to your utterances, such as "Help me" & phrase, such as "Good morning", the first utterance will be recognized and the second utterance will will fail, resulting in a default Intent "FallbackIntent" as shown below.
    <img width="1440" alt="Image8" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/88617a63-e527-4b42-9ef4-4d6baa13fa6d">

  - <img width="1437" alt="Image10" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/887ebca1-cbf0-46a4-bc39-b591152e3437">

<img width="1440" alt="Image11" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/d45ab446-09fb-448f-ba51-139aea5165b1">


<img width="1435" alt="Image12" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/6c53df4c-263e-4535-933d-e792cadea00a">

<img width="1433" alt="Image13" src="https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/5f8a540c-b6bf-4b50-83c8-84e6f245aaf2">

![image](https://github.com/csarat424/BankerBot-using-Amazon-Lex/assets/22951307/ba1fba02-687c-42c7-a2a7-286bf75c8067)

