# Working with CSV data

## Set up

To load CSV file data into p5js, we will start with [this example code](https://p5js.org/reference/#/p5/loadTable) frok p5js website.

```js
// Given the following CSV file called "mammals.csv"
// located in the project's "assets" folder:
//
// id,species,name
// 0,Capra hircus,Goat
// 1,Panthera pardus,Leopard
// 2,Equus zebra,Zebra

var table;

function preload() {
  //my table is comma separated value "csv"
  //and has a header specifying the columns labels
  table = loadTable("assets/mammals.csv", "csv", "header");
  //the file can be remote
  //table = loadTable("http://p5js.org/reference/assets/mammals.csv",
  //                  "csv", "header");
}

function setup() {
  //count the columns
  print(table.getRowCount() + " total rows in table");
  print(table.getColumnCount() + " total columns in table");

  print(table.getColumn("name"));
  //["Goat", "Leopard", "Zebra"]

  //cycle through the table
  for (var r = 0; r < table.getRowCount(); r++)
    for (var c = 0; c < table.getColumnCount(); c++) {
      print(table.getString(r, c));
    }
}
```

As it says on the top comments, create a blank text file in TextEdit(Mac) and paste the data. Before you save, go to `Format > Make Plain Text`. This will remove any formatting and make the text as plain as possible. Now, save with a file extension of `.csv` instead of `.txt`. The CSV file in the example above must be saved in `assets` folder, which should sits right next to your `sketch.js` file.

JavaScript is asynchronous and we cannot predict which data will be loaded first, the sketch may run before it loads the CSV file. That will result in an error. To avoid, p5js has a special function called `preload()`. This will ensure that anything you add into this function will be loaded before the main sketch runs.

```js
function preload() {
  table = loadTable("assets/mammals.csv", "csv", "header");
}
```

## loadTable function
`loadTable()` function is used to load tabular type of data. The data loaded in is now stored in an object called `table`. This object name is not important. You may name it any way you want. Once the object is initialized, we can call many functions on it using the dot notation. Here is [the full reference](https://p5js.org/reference/#/p5.Table).




- how to access row/colum
- how to display

- all at once (for loop)
- one each time (index-based)

