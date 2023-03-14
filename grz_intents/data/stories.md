## case bankomatkarte lost
* card_lost{"cardtype": "bankomatkarte", "verlustart": "verlust"}
  - utter_case_kartensperre

## case kreditkarte lost
* card_lost{"cardtype": "kreditkarte", "verlustart": "verlust"}
  - utter_case_kartensperre

## case karte lost - identify cardtype
* card_lost{"cardtype": "karte", "verlustart": "verlust"}
  - utter_which_cardtype

## case bankomatkarte stolen
* card_stolen{"cardtype": "bankomatkarte", "verlustart": "diebstahl"}
  - utter_case_kartensperre

## case kreditkarte stolen
* card_stolen{"cardtype": "kreditkarte", "verlustart": "diebstahl"}
  - utter_case_kartensperre

## case karte stolen - identify cardtype
* card_stolen{"cardtype": "karte", "verlustart": "diebstahl"}
  - utter_which_cardtype

## case kartensperre bankomatkarte
* kartensperre{"cardtype": "bankomatkarte", "verlustart": "None"}
  - utter_which_verlustart
  - utter_case_kartensperre

## case kartensperre kreditkarte
* kartensperre{"cardtype": "kreditkarte", "verlustart": "None"}
  - utter_which_verlustart
  - utter_case_kartensperre

## case kartensperre - identify cardtype and verlustart
* kartensperre{"cardtype": "karte", "verlustart" : "None"}
  - utter_which_verlustart
  - utter_which_cardtype
  - utter_case_kartensperre

## affirm
* affirm
  - utter_anything_else
  - action_restart

## deny
* deny
  - utter_what_a_pity
  - utter_anything_else
  - action_restart

## say greet
* greet
  - utter_greet
  - utter_what_can_i_do

## say goodbye
* goodbye
  - utter_goodbye
  - action_restart

## bot challenge
* bot_challenge
  - utter_iamabot
  - action_restart

## fallback story
* out_of_scope
  - action_default_fallback
