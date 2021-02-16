# RPKG Tool
Download: [https://notex.app/rpkg](https://notex.app/rpkg)

## Introduction
RPKG is a tool that can be used to work with HITMAN™ Trilogy RPKG archives, supporting both GKPRv1 (HITMAN™ 1/2) and GKPRv2 (HITMAN™ 3)

## Basic Usage

### Extracting Archives
To extract an archive with the RPKG Tool you'll need to execute the following command:
```
-extract_from_rpkg <path to rpkg file>
```
The extracted files will be placed inside the same folder the command was executed from,
This can be changed by adding an output path:
```
-output_path <output path>
```

##### Filters
It is also possible to filter the files to be extacted. This filter can be a file extension or file hash:
```
-filter <filter>
```
It is possible to filter more than 1 thing. By using a comma to separate the filter:
```
-filter <filter>,<filter>,<filter>
```

To filter on a specific thing inside a file you can use the search commands:
```
-hex_search <hex string>
-regex_search <regex>
-text_search <text string>
```
to use the search commands you'll need to specify an archive to search in, this can be done with:
```
-search_rpkg <path to rpkg file>
```

### viewing dependencies
Dependencies can be viewed with:
```
-filter <file hash> -hash_depends <path to runtime folder>
```


**example of search command:**
this command will search for files with an ORES or JSON extension that contain the word *brick*.
```
rpkg.exe -filter ORES,JSON -regex_search "brick" -search_rpkg "C:\Program Files\Epic Games\HITMAN3\Runtime\chunk0.rpkg"
```
### Generating Archives
//todo




## Advanced Usage
### Game Localisation
Hitman 2 and 3 store their localization files inside LOCR, DLGE and RTLV files, these can be extracted and unpacked with the following commands:
```
-extract_dlge_to_json_from <path to folder containing RPKG files>
-extract_locr_to_json_from <path to folder containing RPKG files>
-extract_rtlv_to_json_from <path to folder containing RPKG files>
```
After editing the files they have to be converted to the original file type before use, to do this:
```
-rebuild_dlge_from_json_from <path to folder containing JSON (DLGE) files>
-rebuild_locr_from_json_from <path to folder containing JSON (LOCR) files>
-rebuild_rtlv_from_json_from <path to folder containing JSON (RTLV) files>
```

Now that all the files are edited and changed to their correct file type they can repacked into a RPKG file.
this can be done with:
```
-generate_rpkg_from <path to folder to generate rpkg from>
```

### Game Audio
//todo
