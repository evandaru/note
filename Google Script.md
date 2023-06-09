# Google Script snippet
---
## Skeleton Code

```js
const wbook = SpreadsheetApp.openByUrl("https://docs.google.com/spreadsheets/d/1cWmuM3IcPC6qg2HMrhIgXSA_yxvA0sffIUDv-73o6HM/edit?usp=sharing");
const sheet = wbook.getSheetByName("binatang");

function doGet() {
  let data = [];
  const lastRow = sheet.getLastRow();
  const lastColumn = sheet.getLastColumn();

  const row = sheet.getRange(1, 1, lastRow, lastColumn).getValues()

  for (let i = 0; i < row.length; i++) {
    const dataRow = row[i];
    let record = {};
    for (let j = 0; j < lastColumn; j++) {
      record[row[0][j]] = dataRow[j];
    }
    if (i > 0) {
      data.push(record)
    }
  }
  const response = {
    data
  };

  // console.log(response);
  return ContentService.createTextOutput(JSON.stringify(response)).setMimeType(ContentService.MimeType.JSON);

}

function doPost(request) {
  const action = request.parameter.action;
  const data = JSON.parse(request.postData.contents);
    sheet.appendRow([
      data.id,
      data.nama,
      data.skill,
      data.pekerjaan,
    ]);
  let response = {
    "success": true,
    "message": "yey", 
    "data": request
  }
  return ContentService.createTextOutput(JSON.stringify(response)).setMimeType(ContentService.MimeType.JSON);
}
```



Sure, here is a Google Script cheatsheet with examples:

| **Function**        | **Description**                                                                                                              | **Example**                                                   |     |     |     |     |     |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- | --- | --- | --- | --- | --- |
| `alert()`           | Displays an alert box with the specified message.                                                                            | `alert("Hello, world!");`                                     |     |     |     |     |     |
| `confirm()`         | Displays a confirmation box with the specified message and returns a value indicating whether the user clicked OK or Cancel. | `var result = confirm("Do you want to continue?");`           |     |     |     |     |     |
| `prompt()`          | Displays a prompt box with the specified message and returns the user's input.                                               | `var name = prompt("What is your name?");`                    |     |     |     |     |     |
| `log()`             | Writes a message to the console.                                                                                             | `log("Hello, world!");`                                       |     |     |     |     |     |
| `setInterval()`     | Executes a function repeatedly at a specified interval.                                                                      | `setInterval(function() { alert("Hello, world!"); }, 1000);`  |     |     |     |     |     |
| `setTimeout()`      | Executes a function once after a specified delay.                                                                            | `setTimeout(function() { alert("Hello, world!"); }, 2000);`   |     |     |     |     |     |
| `today()`           | Returns the current date.                                                                                                    | `var today = new Date();`                                     |     |     |     |     |     |
| `now()`             | Returns the current time.                                                                                                    | `var now = new Date();`                                       |     |     |     |     |     |
| `random()`          | Returns a random number between 0 and 1.                                                                                     | `var randomNumber = Math.random();`                           |     |     |     |     |     |
| `min()`             | Returns the minimum value in an array.                                                                                       | `var minValue = Math.min(array);`                             |     |     |     |     |     |
| `max()`             | Returns the maximum value in an array.                                                                                       | `var maxValue = Math.max(array);`                             |     |     |     |     |     |
| `sum()`             | Returns the sum of the values in an array.                                                                                   | `var sum = Math.sum(array);`                                  |     |     |     |     |     |
| `average()`         | Returns the average of the values in an array.                                                                               | `var average = Math.average(array);`                          |     |     |     |     |     |
| `sort()`            | Sorts an array in ascending order.                                                                                           | `array.sort();`                                               |     |     |     |     |     |
| `reverse()`         | Reverses the order of an array.                                                                                              | `array.reverse();`                                            |     |     |     |     |     |
| `join()`            | Joins the elements of an array into a string.                                                                                | `var string = array.join(", ");`                              |     |     |     |     |     |
| `split()`           | Splits a string into an array.                                                                                               | `var array = string.split(", ");`                             |     |     |     |     |     |
| `trim()`            | Removes whitespace from the beginning and end of a string.                                                                   | `var trimmedString = string.trim();`                          |     |     |     |     |     |
| `replace()`         | Replaces all occurrences of a substring with another substring.                                                              | `var replacedString = string.replace("old", "new");`          |     |     |     |     |     |
| `substring()`       | Returns a substring of a string.                                                                                             | `var substring = string.substring(start, end);`               |     |     |     |     |     |
| `charAt()`          | Returns the character at a specified index in a string.                                                                      | `var character = string.charAt(index);`                       |     |     |     |     |     |
| `indexOf()`         | Returns the index of the first occurrence of a substring in a string.                                                        | `var index = string.indexOf("substring");`                    |     |     |     |     |     |
| `lastIndexOf()`     | Returns the index of the last occurrence of a substring in a string.                                                         | `var index = string.lastIndexOf("substring");`                |     |     |     |     |     |
| `slice()`           | Returns a new string that is a copy of a portion of the original string.                                                     | `var newString = string.slice(start, end);`                   |     |     |     |     |     |
| `toLowerCase()`     | Converts a string to lowercase.                                                                                              | `var lowercaseString = string.toLowerCase();`                 |     |     |     |     |     |
| `toUpperCase()`     | Converts a string to uppercase.                                                                                              | `var uppercaseString = string.toUpperCase();`                 |     |     |     |     |     |
| `length()`          | Returns the length of a string.                                                                                              | `var length = string.length;`                                 |     |     |     |     |     |
| `empty()`           | Returns true if a string is empty.                                                                                           | `var isEmpty = string.empty();`                               |     |     |     |     |     |
| `contains()`        | Returns true if a string contains a substring.                                                                               | `var contains = string.contains("substring");`                |     |     |     |     |     |
| `startsWith()`      | Returns true if a string starts with a substring.                                                                            | `var startsWith = string.startsWith("substring");`            |     |     |     |     |     |
| `endsWith()`        | Returns true if a string ends with a substring.                                                                              | `var endsWith = string.endsWith("substring");`                |     |     |     |     |     |
| `replaceAll()`      | Replaces all occurrences of a substring with another substring.                                                              | `var replacedString = string.replaceAll("old", "new");`       |     |     |     |     |     |
| `splitBy()`         | Splits a string by a delimiter and returns an array of the resulting substrings.                                             | `var array = string.splitBy(", ");`                           |     |     |     |     |     |
| `match()`           | Returns an array of matches for a regular expression in a string.                                                            | `var matches = string.match(/regex/);`                        |     |     |     |     |     |
| `replaceFirst()`    | Replaces the first occurrence of a substring with another                                                                    |                                                               |     |     |     |     |     |
| `replaceFirst()`    | Replaces the first occurrence of a substring with another substring.                                                         | `var replacedString = string.replaceFirst("old", "new");`     |     |     |     |     |     |
| `padStart()`        | Pads a string with a specified character to a specified length.                                                              | `var paddedString = string.padStart(length, "character");`    |     |     |     |     |     |
| `padEnd()`          | Pads a string with a specified character to a specified length.                                                              | `var paddedString = string.padEnd(length, "character");`      |     |     |     |     |     |
| `trimLeft()`        | Removes whitespace from the beginning of a string.                                                                           | `var trimmedString = string.trimLeft();`                      |     |     |     |     |     |
| `trimRight()`       | Removes whitespace from the end of a string.                                                                                 | `var trimmedString = string.trimRight();`                     |     |     |     |     |     |
| `toNumber()`        | Converts a string to a number.                                                                                               | `var number = string.toNumber();`                             |     |     |     |     |     |
| `toBoolean()`       | Converts a string to a boolean.                                                                                              | `var boolean = string.toBoolean();`                           |     |     |     |     |     |
| `toDate()`          | Converts a string to a date.                                                                                                 | `var date = string.toDate();`                                 |     |     |     |     |     |
| `toTime()`          | Converts a string to a time.                                                                                                 | `var time = string.toTime();`                                 |     |     |     |     |     |
| `toDateTime()`      | Converts a string to a date and time.                                                                                        | `var dateTime = string.toDateTime();`                         |     |     |     |     |     |
| `toObject()`        | Converts a string to an object.                                                                                              | `var object = string.toObject();`                             |     |     |     |     |     |
| `toUrl()`           | Converts a string to a URL.                                                                                                  | `var url = string.toUrl();`                                   |     |     |     |     |     |
| `toBlob()`          | Converts a string to a blob.                                                                                                 | `var blob = string.toBlob();`                                 |     |     |     |     |     |
| `toImage()`         | Converts a string to an image.                                                                                               | `var image = string.toImage();`                               |     |     |     |     |     |
| `toAudio()`         | Converts a string to an audio file.                                                                                          | `var audio = string.toAudio();`                               |     |     |     |     |     |
| `toVideo()`         | Converts a string to a video file.                                                                                           | `var video = string.toVideo();`                               |     |     |     |     |     |
| `toDocument()`      | Converts a string to a document.                                                                                             | `var document = string.toDocument();`                         |     |     |     |     |     |
| `toSpreadsheet()`   | Converts a string to a spreadsheet.                                                                                          | `var spreadsheet = string.toSpreadsheet();`                   |     |     |     |     |     |
| `toPresentation()`  | Converts a string to a presentation.                                                                                         | `var presentation = string.toPresentation();`                 |     |     |     |     |     |
| `toForm()`          | Converts a string to a form.                                                                                                 | `var form = string.toForm();`                                 |     |     |     |     |     |
| `toAPI()`           | Converts a string to an API.                                                                                                 | `var api = string.toAPI();`                                   |     |     |     |     |     |
| `toWebApp()`        | Converts a string to a web app.                                                                                              | `var webApp = string.toWebApp();`                             |     |     |     |     |     |
| `toEmail()`         | Converts a string to an email address.                                                                                       | `var email = string.toEmail();`                               |     |     |     |     |     |
| `toPhone()`         | Converts a string to a phone number.                                                                                         | `var phone = string.toPhone();`                               |     |     |     |     |     |
| `toPostalCode()`    | Converts a string to a postal code.                                                                                          | `var postalCode = string.toPostalCode();`                     |     |     |     |     |     |
| `toCurrency()`      | Converts a string to a currency.                                                                                             | `var currency = string.toCurrency();`                         |     |     |     |     |     |
| `toDatetime()`      | Converts a string to a date and time.                                                                                        | `var dateTime = string.toDatetime();`                         |     |     |     |     |     |
| `toDateTimeLocal()` | Converts a string to a date and time in local time.                                                                          | `var dateTimeLocal = string.toDateTimeLocal();`               |     |     |     |     |     |
| `toTime()`          | Converts a string to a time.                                                                                                 | `var time = string.toTime();`                                 |     |     |     |     |     |
| `toDate()`          | Converts a string to a date.                                                                                                 | `var date = string.toDate();`                                 |     |     |     |     |     |
| `toYear()`          | Converts a string to a year.                                                                                                 | `var year = string.toYear();`                                 |     |     |     |     |     |
| `toMonth()`         | Converts a string to a month.                                                                                                | `var month = string.toMonth();`                               |     |     |     |     |     |
| `toDay()`           | Converts a string to a day.                                                                                                  | `var day = string.toDay();`                                   |     |     |     |     |     |
| `toHour()`          | Converts a string to an hour.                                                                                                | `var hour = string.toHour();`                                 |     |     |     |     |     |
| `toMinute()`        | Converts a string to a minute.                                                                                               | `var minute = string.toMinute();`                             |     |     |     |     |     |
| `toSecond()`        | Converts a string to a second.                                                                                               | `var second = string.toSecond();`                             |     |     |     |     |     |
| `toMillisecond()`   | Converts a string to a millisecond.                                                                                          | `var millisecond = string.toMillisecond();`                   |     |     |     |     |     |
| `toMicrosecond()`   | Converts a string to a microsecond.                                                                                          | `var microsecond = string.toMicrosecond();                    |     |     |     |     |     |
| `toNanosecond()`    | Converts a string to a nanosecond.                                                                                           | `var nanosecond = string.toNanosecond();`                     |     |     |     |     |     |
| `toUTC()`           | Converts a string to a UTC date and time.                                                                                    | `var dateTime = string.toUTC();`                              |     |     |     |     |     |
| `toLocal()`         | Converts a string to a local date and time.                                                                                  | `var dateTime = string.toLocal();`                            |     |     |     |     |     |
| `toGMT()`           | Converts a string to a GMT date and time.                                                                                    | `var dateTime = string.toGMT();`                              |     |     |     |     |     |
| `toISO8601()`       | Converts a string to an ISO 8601 date and time.                                                                              | `var dateTime = string.toISO8601();`                          |     |     |     |     |     |
| `toJSON()`          | Converts a string to a JSON object.                                                                                          | `var object = string.toJSON();`                               |     |     |     |     |     |
| `toXML()`           | Converts a string to an XML object.                                                                                          | `var object = string.toXML();`                                |     |     |     |     |     |
| `toCSV()`           | Converts a string to a CSV string.                                                                                           | `var csvString = string.toCSV();`                             |     |     |     |     |     |
| `toHTML()`          | Converts a string to an HTML string.                                                                                         | `var htmlString = string.toHTML();`                           |     |     |     |     |     |
| `toText()`          | Converts a string to a text string.                                                                                          | `var textString = string.toText();`                           |     |     |     |     |     |
| `toBase64()`        | Converts a string to a base64 string.                                                                                        | `var base64String = string.toBase64();`                       |     |     |     |     |     |
| `fromBase64()`      | Converts a base64 string to a string.                                                                                        | `var string = base64String.fromBase64();`                     |     |     |     |     |     |
| `encrypt()`         | Encrypts a string using the specified algorithm.                                                                             | `var encryptedString = string.encrypt("algorithm");`          |     |     |     |     |     |
| `decrypt()`         | Decrypts a string using the specified algorithm.                                                                             | `var decryptedString = encryptedString.decrypt("algorithm");` |     |     |     |     |     |
| `sign()`            | Signs a string using the specified algorithm.                                                                                | `var signedString = string.sign("algorithm");`                |     |     |     |     |     |
| `verify()`          | Verifies a signed string using the specified algorithm.                                                                      | `var verified = signedString.verify("algorithm");`            |     |     |     |     |     |
| `zip()`             | Zips a file or directory.                                                                                                    | `var zippedFile = zip("file.zip", "directory");`              |     |     |     |     |     |
| `unzip()`           | Unzips a file or directory.                                                                                                  | `var unzippedDirectory = unzip("file.zip");`                  |     |     |     |     |     |
| `uploadFile()`      | Uploads a file to Google Drive.                                                                                              | `var fileId = uploadFile("file.txt");`                        |     |     |     |     |     |
| `downloadFile()`    | Downloads a file from Google Drive.                                                                                          | `downloadFile("fileId", "file.txt");`                         |     |     |     |     |     |
| `createFolder()`    | Creates a folder in Google Drive.                                                                                            | `var folderId = createFolder("folderName");`                  |     |     |     |     |     |
| `deleteFile()`      | Deletes a file from Google Drive.                                                                                            | `deleteFile("fileId");`                                       |     |     |     |     |     |
| `deleteFolder()`    | Deletes a folder from Google Drive.`                                                                                         |                                                               |     |     |     |     |     |
|                     |                                                                                                                              |                                                               |     |     |     |     |     |




