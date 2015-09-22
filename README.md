# VRpportunity
##### Using the Oculus Rift to manipulate Salesforce objects inside Virtual Reality

This is the Unity code for the full stage demo of VRpportunity as presented at the Dreamforce'15 Developer Zone. For the optimal experience, you will need the following:

* Unity 5 Free (compiled with 5.1.2f1)
* Blender (for initial import of 3D assets into your Library)
* Oculus Rift with Runtime 0.6.0.1
* Xbox Controller (either 360 or One)

## Salesforce Org Setup

Create a free Developer Edition org. This will create the same sample data we used in our stage demo.

1. Create the following fields on the following Standard Objects:
   * Opportunity: `Urgent__c` Number(18,0)
   * Account: `Priority__c` Number(18,0)
   * Campaign: `Priority__c` Number(18,0)
   * Contract: `Priority__c` Number(18,0)
   * Opportunity Product: `Priority__c` Number(18,0)
2. Check the FLS on Opportunity to make sure that these sub-object lookups are available for queries.
3. Enable Chatter on Account, Campaign, Contract, and Opportunity Product.
4. Create an Approval Process somewhere. (Our Stage Demo used a simple one on Contract.)
5. Populate the Urgent and Priority fields you created with numbers between 1 and 100. This affects the colors and speed of the rings and associated blocks.
6. Create a Connected App with OAuth settings on and Full Access.

## Unity Project Setup

Open up the project in Unity and make sure that the `Core.Unity` scene is loaded.

1. Open `Assets/Scripts/Salesforce/Salesforce.cs` in MonoDevelop and modify the `clientSecret` and `clientId` variables on lines 26 and 27 to your Connected App settings.
2. Go to the CoreClient object in Unity and modify the Username, Password, and Security Token settings in the Inspector pane to the login credentials to your org.

## Xbox Controller Button Configuration

* Left Thumbstick - Move around
* Right Thumbstick - Turn (same as turning your head)
* LB/RB - Comfort Mode Turn
* LT/RT - Lowers and Raises rings
* A Button - Expand ring/open sub-object/select UI elements
* B Button - Reset all rings to start position
* Back Button - Reset UI Windows (in case player gets stuck)

