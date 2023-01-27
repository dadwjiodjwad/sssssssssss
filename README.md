
NEED HELP w/ Photoshop Script problem

This script changes the color of the text in the active layer to black, exports it as a PNG file with the specified name, then it changes the color of the text in the active layer to white, and exports it again as a PNG file with the specified name, and it repeats the same process with different colors (pink, blue, green, red) and save them as PNG files with different names. 


It exports correctly the 6 files, BUT exports every file as the color black and not in the respective colors.

Tried adding =null before recoloring but activeLayer can't be equal to null or undefined.

Here's the code:

app.activeDocument.activeLayer.textItem.color = new SolidColor();
app.activeDocument.activeLayer.textItem.color.rgb.hexValue = "000000";

var textLayerName = app.activeDocument.activeLayer.name;

var newName = prompt("Enter a new name for the export", "black_" + textLayerName);

var exportOptions = new ExportOptionsSaveForWeb();
exportOptions.format = SaveDocumentType.PNG;
exportOptions.quality = 100;
var file = new File("black " + newName + ".png");
app.activeDocument.exportDocument(file, ExportType.SAVEFORWEB, exportOptions);

app.activeDocument.activeLayer.textItem.color = new SolidColor();
app.activeDocument.activeLayer.textItem.color.rgb.hexValue = "FFFFFF";


var file2 = new File("white " + newName + ".png");
app.activeDocument.exportDocument(file2, ExportType.SAVEFORWEB, exportOptions);

app.activeDocument.activeLayer.textItem.color = new SolidColor();
app.activeDocument.activeLayer.textItem.color.rgb.hexValue = "fc82d8";


var file3 = new File("pink " + newName + ".png");
app.activeDocument.exportDocument(file3, ExportType.SAVEFORWEB, exportOptions);

app.activeDocument.activeLayer.textItem.color = new SolidColor();
app.activeDocument.activeLayer.textItem.color.rgb.hexValue = "63a8e7";


var file4 = new File("blue " + newName + ".png");
app.activeDocument.exportDocument(file4, ExportType.SAVEFORWEB, exportOptions);

app.activeDocument.activeLayer.textItem.color = new SolidColor();
app.activeDocument.activeLayer.textItem.color.rgb.hexValue = "0c6a27";


var file5 = new File("green " + newName + ".png");
app.activeDocument.exportDocument(file5, ExportType.SAVEFORWEB, exportOptions);

app.activeDocument.activeLayer.textItem.color = new SolidColor();
app.activeDocument.activeLayer.textItem.color.rgb.hexValue = "a80000";


var file6 = new File("red " + newName + ".png");
app.activeDocument.exportDocument(file6, ExportType.SAVEFORWEB, exportOptions);
