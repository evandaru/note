# Script Google App

Status Learn: Not started
type: Rest API

[Doc from chat gpt](Script%20Google%20App%20d9d8298cac65498b99b601a7c2e6820d/Doc%20from%20chat%20gpt%205e964621a84e445c91072704afaa2e54.md)

<aside>
🐟 call spreatsheet

</aside>

```php
SpreadsheetApp.getActive();
```

create ama read

```jsx
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