![alt text](https://filestack.com/themes/filestack/assets/images/press-articles/color.svg "Filestack Logo")

# Filestack Viewer Custom Styling
Changing Filestack Viewer appearance is extremely easy with included [SASS files](https://example.com). To manipulate colors or to re-size, all you have to do is alter initial variables stored in `_initial-variables.sass` file. Here you'll find described keys:

![alt text](https://assets.filestack.com/viewer-assets/filestack-viewer-variables-min.png "Filestack Viewer Variables reference")
[Open bigger image](https://assets.filestack.com/viewer-assets/filestack-viewer-variables-min.png)

## Generate CSS file
There are several ways to generate CSS file from SASS files. If you have node.js installed already you can simply use NODE-SASS watching script to compile SASS into CSS:
First run:
```
$ npm install
```
And then:
```
$ npm run sass
```
If you prefer to use an application instead, you can try [CodeKit App](https://codekitapp.com/). There is plenty of options.

## Remove elements from the Interface
If you want to remove any button from the interface, you need to use browser's inspector to find assigned `ID`.  At the bottom of `viewer.sass` file add the additional declaration with style `display: none`. In this example, you can turn-off sidebar toggling button:

```sass
#sidebarToggle
  display: none
```

### Navigation Elements

**Top Navigation**

| ID or Class               | Description                                      |
| ------------------------- | ------------------------------------------------ |
| `#sidebarToggle`          | **Sidebar button** toggling sidebar visibility   |
| `#viewFind`               | **Search button** toggling search pane           |
| `#previous`               | **Arrow up button** navigating to previous page  |
| `#next`                   | **Arrow down button** navigating to next page    |
| `#indicatorWrapper`       | **Page number input** navitating to chosen page  |
| `#numPages`               | **Total page** displaing number of total pages   |
| `#zoomOut`                | **Minus button** zooming out page view           |
| `#zoomIn`                 | **Plus button** zooming in page view             |
| `#scaleSelectContainer`   | **Actual size select** dropdown with page scale  |
| `#download`               | **Download button** downloading current document |
| `#viewBookmark`           | **Bookmark button** setting actual page in url   |
| `#secondaryToolbarToggle` | **More button** toggling secondary menu          |


**Secondary Navigation**

| ID or Class               | Description                                          |
| ------------------------- | ---------------------------------------------------- |
| `#presentationMode`       | **Fullscreen button** switching to presentation mode |
| `#firstPage`              | **Double arrow up button** jumping to first page     |
| `#lastPage`               | **Double arrow down button** jumping to last page    |
| `#pageRotateCw`           | **Rotate right button** rotating clockwise           |
| `#pageRotateCcw`          | **Rotate left button** rotating counterclockwise     |
| `#cursorSelectTool`       | **Cursor button** selecting text                     |
| `#cursorHandTool`         | **Hand button** moving pages                         |
| `#openFile`               | **Upload button** opening local document             |
| `#print`                  | **Printer button** printing current document         |



## Implement Custom Styling
To implement custom styling into a Filestack Viewer, you need to upload generated `viewer.css` file to Filestack, and get Filehandle of this file. Then to implement custom css into your implementation, construct viewer link like this:

```
https://cdn.filestackcontent.com/preview=css:"https://cdn.filestackcontent.com/CSS_FILEHANDLE"/DOCUMENT_FILEHANDLE
```
