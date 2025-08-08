# map-creator

I want a single html file that will display a map as the background image. The image of the map is a floorplan of a building. A circle button in certain rooms on the image. clicking a circle button will open a popup which will display content such as images, video, or documents (downloadable by clicking the link to the document). each circle button displays a different set of media based on the room in which it denotes.

The top of the page will be a floating top bar with controls for the user. One button to add another circle button.

Circle buttons can be click dragged around the map where they will stay in place. Each circle button is tied to it's own popup dialog.

In the dialog opened by clicking a circle button, there is an add file button that allows the user to add a file to this popup's gallery. 

The second control button is a save button. This will create a "rendered" html page with the same functionality but static, without the map editing controls. It will retain the number and locations of the circle button as they were placed by the user. It will also retain the files that were added to each location. The save button will provide an option to the user on whether to inline all file uploads in base64.
