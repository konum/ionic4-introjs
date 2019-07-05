# ionic4-introjs
Ionic4 example with Intro.js.

The key to make introJs work with Ionic 4 is to star it like this.

 introJs(document.querySelector('app-home')).start(); 

Where app-home is the selector of your component. This way introJs div's are created at component root, not at body root.

On some ionic components (like ion-list) css property content: none must be set. Otherwise the component's children whont show over the tooltip overlay.


Help number css must be modified so it doesnt go beyond screen edge. Set it in app.scss

.introjs-helperNumberLayer {
        left: 12px !important; 
}
