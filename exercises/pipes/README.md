# File Size Pipe

Formats a filesize for readability. The input is passed in bytes (B).
The set of input file sizes is 10, 100, 1000, 10000, 100000, 10000000, 10000000000, 10^15
The result should like as shown in gif below

![](./pipe-exercise.gif)

Quick reference:

- 1024^0 Bytes = 1 Byte (B)
- 1024^1 Bytes = 1 Kilobyte (KB)
- 1024^2 Bytes = 1 Megabyte (MB)
- 1024^3 Bytes = 1 Gigabyte (GB)
- 1024^4 Bytes = 1 Terabyte (TB)
- 1024^5 Bytes = 1 Perabyte (PB)
...

File size is: {{ 1024^4 | fileSize }}
=
File size is: 1.00 TB

Next, try adding an aditional boolean parameter where, if true, writes the unit in long form

File size is: {{ 1024^4 | fileSize: true }}
=
File size is: 1.00 Terabytes

## Step 1

Using the `angular-cli` create a new project called `pipes` inside of the `training` folder.

## Step 2

Modify the `app.component.ts` file with an array property `fileSizes = [10, 100, 1000, 10000, 100000, 10000000, 10000000000];` and another property `largeFileSize = Math.pow(10, 15)`.

## Step 3

Modify the `app.component.html` file to create a template that uses `NgFor` (`*ngFor`) to display the `fileSizes` array in a column of `<p>` elements and the `largeFileSize` in another `<p>` below.

## Step 4

Using the `angular-cli` create a new pipe called `format-file-size` (the file created by the CLI should be named `format-file-size.pipe.ts`.  Notice that `app.module.ts` is automatically updated to import `FormatFileSizePipe` from the appropriate auto-generated file and it is included in the module `declarations`.

## Step 5

Add some constants to `format-file-size.pipe.ts` as shown in the code below:

```js
const FILE_SIZE_UNITS = ['B', 'KB', 'MB', 'GB', 'TB', 'PB', 'EB', 'ZB', 'YB'];
const FILE_SIZE_UNITS_LONG = ['Bytes', 'Kilobytes', 'Megabytes', 'Gigabytes', 'Pettabytes', 'Exabytes', 'Zettabytes', 'Yottabytes'];
```

## Step 6

Modify the arguments and body of the `transform()` method of the `FormatFileSizePipe` class to perform the calculation and string manipulation to display the file sizes with units appropriately.  Hint: you may find the functions `Math.round()`, `Math.min()`, `Math.power()`, and `Math.log()` useful.


