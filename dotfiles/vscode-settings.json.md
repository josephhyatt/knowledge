# VSCode

## settings.json

```javascript
{
  /*** disabling vscode extra bloat stuff ***/
  "telemetry.enableTelemetry": false,
  "workbench.statusBar.feedback.visible": false,
  "editor.fontFamily": "Hasklig",
  "workbench.colorTheme": "Kimbie Dark",
  "editor.fontSize": 16,
  "editor.fontLigatures": true,
  "editor.multiCursorModifier": "ctrlCmd",
  "terminal.integrated.fontFamily": "Hasklig",
  "workbench.sideBar.location": "right",
  "editor.renderWhitespace": "none",
  "editor.tabSize": 2,
  "editor.insertSpaces": true,
  "editor.detectIndentation": true,
  "editor.wordWrap": "on",
  "editor.cursorBlinking": "smooth",
  "terminal.integrated.cursorStyle": "line",
  "editor.wordWrapColumn": 120,
  "editor.minimap.enabled": false,
  // fixing UI issues / no need to click confirm boxes
  "explorer.confirmDragAndDrop": false,
  "git.confirmSync": false,
  "git.autofetch": true,
  // no need to confirm imports when filename changes
  "javascript.updateImportsOnFileMove.enabled": "always",
  "javascript.implicitProjectConfig.experimentalDecorators": true, // stops errors using decorators
  // emmet and suggestions
  "editor.acceptSuggestionOnEnter": "off", // use tab for suggestions, so you can press enter to newline
  "editor.quickSuggestions": {
    "comments": false // no suggestions inside comments
  },
  "emmet.showSuggestionsAsSnippets": true,
  "emmet.triggerExpansionOnTab": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact",
    "HTML (Eex)": "html"
  },
  "emmet.syntaxProfiles": {
    "javascript": "jsx",
    "erb": "erb"
  },
  /*** general formatting ***/
  // toggle to false and enable [javascript] & [javascriptreact] when not using eslint
  "ruby.format": false,
  "ruby.codeCompletion": false,
  "solargraph.hover": true,
  "solargraph.completion": true,
  "solargraph.rename": false,
  "solargraph.diagnostics": true,
  //CSS
  // No unit for zero needed
  "css.lint.zeroUnits": "warning",
  "css.lint.idSelector": "warning",
  //SCSS
  // No unit for zero needed
  "scss.lint.zeroUnits": "warning",
  "scss.lint.idSelector": "warning",
  //intellisense plugin setting
  "path-intellisense.extensionOnImport": true,
  "path-intellisense.showHiddenFiles": true,
  "path-intellisense.autoSlashAfterDirectory": true,
  "workbench.colorCustomizations": {
    "tab.activeBackground": "#232833",
    "activityBar.background": "#282c34",
    "sideBar.background": "#282c34"
  },
  "window.zoomLevel": 0,
  // Allows to display errors.
  "scss.showErrors": false,
  // Add vendor prefixes to CSS when you save a file.
  "liveServer.settings.donotShowInfoMsg": true,
  "workbench.startupEditor": "newUntitledFile",
  "editor.tabCompletion": "on",
  "breadcrumbs.enabled": true,
  "sync.gist": "4f53f0100634a4ad5376ab6a49fe446a",
  "editor.suggestSelection": "first",
  "vsintellicode.modify.editor.suggestSelection": "automaticallyOverrodeDefaultValue",
  "code-runner.runInTerminal": true,
  "code-runner.saveFileBeforeRun": true,
  "code-runner.executorMap": {
    "cpp": "cd $dir && g++ -std=c++14 $fileName -o $fileNameWithoutExt && $dir$fileNameWithoutExt"
  }
}
```

## cpp.json

```cpp
{
	"author": {
		"prefix": "info",
		"body": [
			"/*=============================================================================",
			"#  Author:          ${1: josephhyatt - https://github.com/josephhyatt/}",
			"#  Email:           ${2: josephnhyatt@gmail.com}",
			"#  FileName:        ${3: test.cpp}",
			"#  Description:     ${4: /}",
			"#  Version:         ${5: 0.0.1}",
			"#  History:         $6",
			"=============================================================================*/",
			"$7"
		],
		"description": "File information for file."
	},
	"cpp": {
		"prefix": "cpp",
		"body": [
			"#include <iostream>",
			"",
			"int main()",
			"{",
			"\t${1:CODE}",
			"\treturn 0;",
			"}"
		],
		"description": "C++ default template"
	},
	"class": {
		"prefix": "class",
		"body": [
			"class ${1:Class_name} {",
			"\tpublic:",
			"\t\t$2",
			"\tprivate:",
			"\t\t$3",
			"}"
		],
		"description": "C++ class template"
	},
	"for": {
		"prefix": "for",
		"body": [
			"for (int ${i} = ${1:length}; i ${2|>,>=,<=,<|} ${3:testExpression}; ${4:updateStatement};){",
			"  ${5:/* code */}",
			"}"
		],
		"description": "basic 'for' loop"
	},
	"forr": {
		"prefix": "forr",
		"body": [
			"for (int ${i} = ${1:length} - 1; ${i} >= ${2:0}; ${i}--)",
			"{",
			"\t$3",
			"}"
		],
		"description": "reverse 'for' loop"
	},
	"foreach": {
		"prefix": "foreach",
		"body": [
			"for(auto ${1:range_name} : ${2:range_expression})",
			"{",
			"\t${3:CODE}",
			"}"
		],
		"description": "range-based 'for loop' statement where 'range_expression' is the variable from a 'vector'"
	},
	"do": {
		"prefix": "do",
		"body": [
			"do",
			"{",
			"\t$1",
			"} while($2);"
		],
		"description": "do...while loop"
	},
	"while": {
		"prefix": "while",
		"body": [
			"while ($1)",
			"{",
			"\t$2",
			"}"
		],
		"description": ""
	},
	"if": {
		"prefix": "if",
		"body": [
			"if ($1)",
			"{",
			"\t$2",
			"}"
		],
		"description": "if statementsss"
	},
	"else": {
		"prefix": "else",
		"body": [
			"else",
			"{",
			"\t$1",
			"}"
		],
		"description": "else statement"
	},
	"else if": {
		"prefix": "else if",
		"body": [
			"else if ($1)",
			"{",
			"\t$2",
			"}"
		],
		"description": "else-if statement"
	},
	"enum": {
		"prefix": "enum",
		"body": [
			"enum ${MyEnum}",
			"{",
			"\t$1",
			"};"
		],
		"description": "enum"
	},
	"enum class": {
		"prefix": "enum class",
		"body": [
			"enum class ${MyClass} { };"
		],
		"description": "enum class (c++11)"
	},
	"namespace": {
		"prefix": "namespace",
		"body": [
			"namespace ${MyNamespace}",
			"{",
			"\t$1",
			"}"
		]
	},
	"#ifdef": {
		"prefix": "ifdef",
		"body": [
			"#ifdef ${DEBUG}",
			"\t$1",
			"#endif // ${DEBUG}"
		],
		"description": "#ifdef allows that a section of a program is compiled only if the defined constant that is specified as the parameter has been defined, independently of its value."
	},
	"#ifndef": {
		"prefix": "ifndef",
		"body": [
			"#ifndef ${1:1}",
			"\t$2",
			"#endif // !$1"
		],
		"description": "the code between the #ifndef directive and the #endif directive is only compiled if the constant name that is specified has not been defined previously."
	},
	"header file": {
		"prefix": "headerfile",
		"body": [
			"#ifndef __${1:FILENAME}_H // include guard",
			"#define __${1:FILENAME}_H",
			"",
			"\t${2:CODE}",
			"",
			"#endif /* __${1:FILENAME}_H */"
		],
		"description": "header file outline"
	},
	"struct": {
		"prefix": "struct",
		"body": [
			"\nstruct ${1:MyStruct}",
			"{",
			"\t",
			"}\n",
		],
		"description" : "A data structure (struct) is a group of data elements grouped together under one name. These data elements, known as members, can have different types and different lengths. Data structures can be declared in C++ using the following syntax"
	},
	"switch": {
		"prefix": "switch",
		"body": [
			"\nswitch (${1:value})",
			"{",
			"\t${2:/*cases*/}",
			"\tdefault:",
			"\t{",
			" \t\t ${3:/* default execution statement */} " ,
			"\t\tbreak;",
			"\t}",
			"}\n"
		],
		"description" : "A switch statement allows a variable to be tested for equality against a list of values. Each value is called a case, and the variable being switched on is checked for each case."
	},
	"cout": {
		"prefix": "cout",
		"body": [
			"std::cout << \"${1:/* message */}\" << std::endl;"
		],
		"description": "standard output stream"
	},
	"cin": {
		"prefix": "cin",
		"body": [
			"std::cin >> ${1:variable_name};"
		],
		"description": "standard user input stream"
	},
	"#inc": {
		"prefix": "#inc",
		"body": [
			"#include \"$1\""
		],
		"description": "#include \" \""
	},
	"#inc<": {
		"prefix": "#inc<",
		"body": [
			"#include <$1>"
		],
		"description": "#include \" \""
	},
	"#def": {
		"prefix": "#def",
		"body": [
			"#define \"$1\" \"$2\" "
		],
		"description": "#define \" \""
	},
	/*********************************/
		  /** Custom Snippets **/
	/********************************/
	"A pointer is a variable that holds a memory address where a value lives.": {
		"prefix": "pointer",
		"body": [
			"${1|int,double,char,std::string|} *${2:pointer_name} = &${3:variable_name};"
		],
		"description": "A pointer is a variable that holds a memory address where a value lives."
	},
	"A reference variable is an alias, that is, another name for an already existing variable. A reference, like a pointer is also implemented by storing the address of an object. A reference can be thought of as a constant pointer (not to be confused with a pointer to a constant value!) with automatic indirection, i.e the compiler will apply the * operator for you.": {
		"prefix": "reference",
		"body": [
			"${1|int,double,char,std::string|} &${2:reference_name} = ${3:variable_name};"
		],
		"description": "A reference variable is an alias, that is, another name for an already existing variable. A reference, like a pointer is also implemented by storing the address of an object. A reference can be thought of as a constant pointer (not to be confused with a pointer to a constant value!) with automatic indirection, i.e the compiler will apply the * operator for you."
	},
	"A container that can store elements, but its size can change dynamically.": {
		"prefix": "vector",
		"body": [
			"/*",
			"#include <vector>",
			"*/",
			"std::vector<${1|int, double, std::string|}> ${2:vectorName};"
		],
		"description": "A container that can store elements, but its size can change dynamically."
	},
	"#bubble sort algorithm": {
		"prefix": "bubblesort",
		"body": [
			"/* ",
			"** The bubble sort Algorithm simply compares adjacent elements and exchanges them if they are out of order.",
			"** bubble sort using array in ascending order.",
			"*/",
			"",
			"#include <iostream>",
			"",
			"void PrintArray(int *array, int n) {",
			"  for (int i = 0; i < n; ++i)",
			"    std::cout << array[i] << \" \" << std::flush;",
			"  std::cout << std::endl;",
			"}",
			"",
			"void BubbleSort(int *array, int n) {",
			"  bool swapped = true;",
			"  int j = 0;",
			"  int temp;",
			"",
			"  while (swapped) {",
			"    swapped = false;",
			"    j++;",
			"    for (int i = 0; i < n - j; ++i) {",
			"      if (array[i] > array[i + 1]) {",
			"        temp = array[i];",
			"        array[i] = array[i + 1];",
			"        array[i + 1] = temp;",
			"        swapped = true;",
			"      }",
			"    }",
			"  }",
			"}",
			"",
			"int main() {",
			"  int array[] = {${1:enter integers}, ${2: next integer}};",
			"  int n = sizeof(array)/sizeof(array[0]);",
			"",
			"  std::cout << \"Before Bubble Sort: \" << std::endl;",
			"",
			"  PrintArray(array, n);",
			"  BubbleSort(array, n);",
			"",
			"  std::cout << \"After Bubble Sort: \" << std::endl;",
			"  PrintArray(array, n);",
			"  return (0);",
			"}"
		],
		"description": "bubble sort algorithm simply compares adjacent elements and exchanges them if they are out of order"
	},
	"List odd integers": {
		"prefix": "list_odd_integers",
		"body": [
			"// surrounding function will return a list of odd numbers",
			"// function that receives and returns false if the list value is odd",
			"/*",
			"#include <cstdlib>",
			"#include <iostream>",
			"#include <string>",
			"#include <vector>",
			"#include <ctime>",
			"#include <numeric>",
			"#include <cmath>",
			"#include <functional>",
			"#include <sstream>",
			"*/",
			"// check if value is odd or not",
			"bool IsItOdd(int num)",
			"{",
			"    if(num % 2 == 0) ",
			"    {",
			"        return false;",
			"    } else {",
			"        return true;",
			"    }",
			"}",
			"",
			"std::vector<int> ChangeList(std::vector<int> list, ",
			"                            std::function<bool(int)> func)",
			"{",
			"    std::vector<int> oddList;",
			"    for(auto i : list)",
			"    {",
			"        if(func(i))",
			"        {",
			"            oddList.push_back(i);",
			"        }",
			"    }",
			"    return oddList;",
			"}",
			"",
			"int main() ",
			"{",
			"   // creating a vector list of integer values",
			"   std::vector<int> listOfNums {${1:int}, ${2:int}, ${3: int}};",
			"   // vector containing integer values that calls ChangeList function that receives a vector of numbers ListOfNums, and also recieves function IsItOdd.",
			"   std::vector<int> oddList = ChangeList(listOfNums, IsItOdd);",
			"   // print to the console.",
			"   std::cout << \"List odd integers: \" << std::endl;",
			"   // iterate through oddList",
			"   for(auto i : oddList)",
			"   {",
			"       // print oddList to console",
			"       std::cout << i << std::endl;",
			"   }",
			"",
			"   return 0;",
			"}"
		],
		"description": "List odd integers"
	},
	"convert string to vector and print individual strings per line": {
		"prefix": "convert_string_to_vector",
		"body": [
			"// convert string to vector and print individual strings per line",
			"/*",
			"#include <cstdlib>",
			"#include <iostream>",
			"#include <string>",
			"#include <vector>",
			"#include <numeric>",
			"#include <sstream>",
			"*/",
			"// vector function prototype StringToVector that receives theString and char separator ",
			"std::vector<std::string> StringToVector(std::string theString, char separator);",
			"",
			"int main()",
			"{",
			"   ",
			"    std::vector<std::string> vec = StringToVector(\"${1:enter text}\", ' '); ",
			"    // cycle through each index in the vector and print out",
			"    for(int i = 0; i < vec.size(); ++i)",
			"    {",
			"        std::cout << vec[i] << std::endl;",
			"    }",
			"    return 0;",
			"}",
			"",
			"// vector function prototype StringToVector that receives theString and char separator ",
			"std::vector<std::string> StringToVector(std::string theString, char separator)",
			"{",
			"    // returns a vector",
			"    std::vector<std::string> vecsWords;",
			"    // using stringstream object that receives a string and outputs all the words by what separates those words in the string",
			"    std::stringstream ss(theString);",
			"    // store individual strings",
			"    std::string sIndivStr;",
			"    // iterate through and get strings out main of main string as long as they exist",
			"    // get ss (stringstream), than temporarly get sIndivStr (individual string), and pass in the separator to separate each of the strings",
			"    while(getline(ss, sIndivStr, separator))",
			"    {",
			"        // push individual strings into vector",
			"        vecsWords.push_back(sIndivStr);",
			"    }",
			"    // return vector",
			"    return vecsWords;",
			"}"
		],
		"description": "convert string to vector and print individual strings per line"
	},
	"sort array of points according to X coordinate": {
		"prefix": "sort_x_coordinate",
		"body": [
			"/* ",
			" * sort array of points according to X coordinate",
			" * #include <iostream>",
			" * #include <cfloat>",
			" * #include <cstdlib>",
			" * #include <cmath> ",
			" */",
			"int compareX(const void* a, const void* b)",
			"{",
			"    Point *p1 = (Point *)a, *p2 = (Point *)b;",
			"    return (p1->x - p2->x);",
			"}"
		],
		"description": "sort array of points according to X coordinate"
	}
}
```

