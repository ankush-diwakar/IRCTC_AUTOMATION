
# IRCTC Tatkal Cypress Automation !

### Now book your tatkal tickets under 1 min at ease by bypassing captcha and filling multiple passenger details at once. Let the script book it for you.



> [!NOTE] 
> ```
> This Cypress script for automating IRCTC ticket booking
> is created strictly for educational purposes. The code and its
> usage are intended to showcase Cypress testing capabilities and
> best practices. Any attempt to use this script for unauthorized
> access or activities that violate IRCTC terms of service or legal
> regulations is strictly prohibited. The author(s) and associated
> entities are not responsible for any misuse or legal consequences 
> resulting from the use of this script for any unauthorized 
> activities.
> ```


## Features it has right now?

-  ✓ Can book **Tatkal**, **Premium Tatkal** and **Normal Tickets** as well.
-  ✓ Can book tickets for you if you open even **2-3 minutes** before tatkal time.
-  ✓ Signing in with your **username** and **password**.
-  ✓ **Auto Upgradation Enabled**.
-  ✓ Filling Captchas and retrying untill success.
-  ✓ Support for **Food Choices**, **Seats Preferences**.
-  ✓ Will Book only if confirm berths are alloted.
-  ✓ **Multiple passengers** supported. 
-  ✓ Pre filling all your information.
-  ✓ **Payment Gateway Automation** (Paying With **UPI ID** OR **QR Code**).



## How to Make this work for you?

- Things you need in your system **NodeJS**, **Python**.
- Make relevant changes in file located at **cypress/fixtures/passenger_data.json**
> [!TIP]
> Filling Your **UPI ID** Will Initiate A Payment Request Directly.
> But it's a bit slow generally would take 2 or 3 sec to arrive request on your smartphone.
> If Your are not using this then you can scan and pay directly which would be much faster.



> [!NOTE] 
> ```
> At a time either Tatkal Or Premium Tatkal can be -> true <- not both.
> ```
```
{
  "TRAIN_NO": "22538",
  "TRAIN_COACH": "2A",
  "TRAVEL_DATE": "06/03/2025",
  "SOURCE_STATION": "LTT",
  "BOARDING_STATION": null,
  "DESTINATION_STATION": "PRYJ",
  "TATKAL": true,
  "PREMIUM_TATKAL": false,
  "UPI_ID_CONFIG": "",
  "PASSENGER_DETAILS": [
    {
      "NAME": "Ankush Diwakar",
      "AGE": 23,
      "GENDER": "Male",
      "SEAT": "No Preference",
      "FOOD": "No Food"
    }
  ],

}
```

- Below are the relevant values you can use for **TRAIN_COACH**, **GENDER** , **SEAT**

***
```
"__valid_coaches__": "SL | 2A | 3A | 3E | 1A | CC | EC | 2S", <---------- Please Use Only from these values.
"__valid_seats__": "Lower | Middle | Upper | Side Lower | Side Upper | Window Side | No Preference",   <---------- Please Use Only from these values.
"__valid_genders__": "Male | Female | Transgender", <---------- Please Use Only from these values.
"__valid_food_choices__": "Veg | Non Veg | No Food" <---------- Please Use Only from these values.

```
***


- You can add multiple passenger array of objects in `PASSENGER_DETAILS` as an example below
```
{
  "TRAIN_NO": "12318",
  "TRAIN_COACH": "3A",
  "TRAVEL_DATE": "12/09/2023",
  "SOURCE_STATION": "UMB",
  "BOARDING_STATION": null, <-- Change to full station name if required, else leave null
  "DESTINATION_STATION": "BSB",
  "TATKAL": true,
   "PREMIUM_TATKAL": false,
  "UPI_ID_CONFIG": "",
  "PASSENGER_DETAILS": [
    {
      "NAME": "Ankush Diwakar",
      "AGE": 23,
      "GENDER": "Male",
      "SEAT": "No Preference",
      "FOOD": "No Food"
    },
    {
      "NAME": "Poonam Panday",
      "AGE": 29,
      "GENDER": "Female",
      "SEAT": "Side Lower",
      "FOOD" "No Food"
    },
    {
      "NAME": "Passenger 3 Name",
      "AGE": 26,
      "GENDER": "Female",
      "SEAT": "Side Lower",
      "FOOD" "No Food"
    }
  ],

}
```



- You can configure your IRCTC `USERNAME` , `password` in `cypress.env.json`

> [!TIP]
> If you wish to enter **CAPTCHA** manually, then change `MANUAL_CAPTCHA` to `true` in `cypress.env.json`

```
{
    "USERNAME": "yourusername",
    "PASSWORD": "yourpassword",
    "MANUAL_CAPTCHA": false
}
```



### To Run...........

```
npm install # <---- Make Sure You Run This Command From Code Folder. 
npm run start-booking <---------- This will first bring up captha server then starts booking 
```

