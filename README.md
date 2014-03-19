# Barcode Reader
This jQuery plugin handles the barcode scanner output when a DOM element is focused.
It will listen to all keyboard inputs inside de DOM element and it will fire the following events:


## Events

### Start of Text (STX)
#### Event:
start.mmp.barcodereader
#### Parameters:
- Event (eventObject)

#### Description:
This event is fired when the barcode scanner returns the STX prefix.

### End of Text (ETX)
#### Description:
This event is fired when the barcode scanner returns the ETX prefix.
#### Event:
end.mmp.barcodereader
#### Parameters:
- Event (eventObject)
- Output String (string)

### Char
#### Description:
This event is fired on every single char read by the barcode scanner.
#### Event:
char.mmp.barcodereader
#### Parameters:
- Event (eventObject)
- Character (string)


## Usage
```javascript
// Initialize the listener:
$(document).mmpBarcodeReader();
```


## Example
```javascript
// Listen to all inputs inside the document element
$(document).ready(function(){
    $(this).mmpBarcodeReader();
    $(this).bind('start.mmp.barcodereader', function(e){
        console.log('start', e);
    });
    $(this).bind('end.mmp.barcodereader', function(e, st){
        console.log('end', e, st);
    });
    $(this).bind('char.mmp.barcodereader', function(e, ch){
        console.log('char', e, ch);
    });
});
```


## Barcode Scanner Configuration
Configure your barcode scanner prefix and suffix. Chek the manufacturer's manual.
- **Prefix:** STX (Start of Text, Hex. 0x02)
- **Suffix:** ETX (End of Text, Hex. 0x03)


## Author

- Miguel Montes Porras - 2014
- http://mimopo.es
- [Twitter @mimopoweb](https://twitter.com/mimopoweb)
- [Github @mimopo](https://github.com/mimopo)


## License

You can do whatever you want with it ;)
