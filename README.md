# Northcoders_be_my_serverless_valentine
A serverless app for the Northcoders serverless competition: find out if something is vegan or vegetarian by quickly scanning the barcode.

## Competition details

Valentine's Day in Paris. What's not to like? 

I'd like to set up a competition - "Best Serverless App" - open to all past and current students. Given that the prize will include tickets to both days of http://paris.serverlessconf.io/agenda.html for one person (so enlightened employers should let you go with the days paid) and flights and accommodation for up to 2 (so you can go with a +1 on such a romantic date) and £200 spending money it's worth a pop. 

I'd want at least 10 people to have a really good stab at this to run the competition, so if you're inclined please DM by 10am tomorrow at which point I'll let you know if it's running. Adjudicating will be on Monday 5th February between 6pm and 8.30pm where you'll need to demo your app, app architecture and code (10 minutes max). Everyone else is invited to come and if you do, you'll get to vote on your favourite app. I'll let everyone know tomorrow morning if it's on. Spread the word (someone please post on the Whatsapp channel).

Serverless is going to take off this year, is going to feature in our course from the next cohort, and I'd love to see what everyone builds with it. Appreciate it's a little late notice, so if we don't get enough interest I'll sadly have to cancel (and probably go myself...)

## App details 

### The problem

I'm vegan and I can't tell you how annoying and inconsistent vegan food labels are. The plan for this app is to save me some time reading labels for non-vegan ingredients, time which is obviously going to go back into coding.

### App structure

A simple React UI that communicates with a range of micro-services built using Google Cloud Functions. 

1) BarcodesForSmiles - the user triggers the camera, calls the barcode reader API (powered by https://serratus.github.io/quaggaJS/), returns the code
2) GimmeAllTheNutrients - this microservice use the barcode and passes it through to Open Food Facts https://en.wiki.openfoodfacts.org/API, returning nutritional information and ingredients
3) VeganFilter - takes the nutritional information and checks for non-vegan or veggie ingredients. If all ingredients are vegan or veggie it returns booleans

The will then update the UI using the booleans and will showcase the nutritional information from Open Food Facts.
