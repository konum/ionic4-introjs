# ionic4-introjs
Ionic4 example with Intro.js.

## Run demo

Just run `ng serve` and go to localhost:4200. Click Show Introjs button to display some tooltips.

## FIles modified 
* src/app/home/home.page.ts
* src/app/home/home.page.html
* src/app/app.scss

## Adding intro.js to your current project
Run npm install intro.js @types/intro.js — save

In your componet add:
    import * as introJs from ‘intro.js/intro.js’;
    
    ....
    ionViewWillEnter(){

    introJs(document.querySelector(‘app-home’)).start();

    }


## Notes on making Intro.js working with ionic4
The example is in home.page component.

The key to make introJs work with Ionic 4 is to start it like this.

 `introJs(document.querySelector('app-home')).start();`

Where app-home is the selector of your component. This way introJs div's are created at component root, not at body root.

On some ionic components (like ion-list) css property content: none must be set. Otherwise the component's children whont show over the tooltip overlay.

Help number css must be modified so it doesnt go beyond screen edge. Set it in app.scss

.introjs-helperNumberLayer {
        left: 12px !important; 
}
