# Data Exporter
This is a utility script that will help packaging and readying the Excel data for further user, such as saving it to a MySQL database.

## Installation
To start exporting Excel data include the `Xporter.php` file in you code. This file has utility functions that supports exporting data from excel files. Such methods are :point_down:
- asArray()
- asjson()

## Get array data
To get excel data as array call `asArray()` function, supplying the `path_to_excel_file` as an argument to the function. You can further-use this returned array in your code. Code snippet below will return exported data as ab array and store that array in a `$arr_data` variable :point_down:
```
$arr_data = Xporter::asArray("{$path_to_excel_file}");

echo "<pre>";
print_r($arr_data);
echo "</pre>";
```

## Get json data
To get excel data as json call `asJson()` function, supplying the `path_to_excel_file` as an argument to the function. You can further-use this returned json in your code. Code snippet below will return exported data in json format and store that json string in a `$json_data` variable :point_down:
```
$json_data = Xporter::asJson("{$path_to_excel_file}");

echo "<pre>";
print_r($json_data);
echo "</pre>";
```

## Checking and handling errors
The functions above will return `false` in case there was a problem in parsing the excell file, so it is recommended that you check the returned data before proceeding. Code snippet below checks the returned value before proceeding :point_down:
```
$arr_data = Xporter::asArray("{$_404_path_to_excel_file}");

// Check if false
if ($arr_data === false) {
	// Parsing error detected
	// Handle this accordingly
	echo "Error parsing {$_404_path_to_excel_file}";
	exit;
}

// To this point it means no error detected
// You can safely use $arr_data in your code
echo "<pre>";
print_r($arr_data);
echo "</pre>";
```

## Cautious
Ensure the value entered in the excel cells are of the correct data type as the script may not be able to cover edge case for the data type in the excel cells.
> For instance dates data types.
> Make sure dates are correctly formatted.

### Developer
In case of further assistance using this script, hit me up via contacts below :point_down:
> Livingstone
- +255 687 949 808
- lividavi19@gmail.com