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
  "editor.snippetSuggestions": "top",
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
  },
  "C_Cpp.default.cppStandard": "c++14",
  "C_Cpp.default.cStandard": "c11",
  "C_Cpp.updateChannel": "Insiders",
}
```

## cpp.json

```cpp
{
	"AUTHOR_INFO": {
		"prefix": "AUTHOR_INFO",
		"body": [
			"/*=============================================================================",
			"#  Author:          ${1: josephhyatt - https://github.com/josephhyatt/}",
			"#  Email:           ${2: josephnhyatt@gmail.com}",
			"#  FileName:        ${3: test.cpp}",
			"#  Description:     ${4: /}",
			"=============================================================================*/",
			"$5"
		],
		"description": "File information for file."
	},
	"CPP": {
		"prefix": "CPP",
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
	"CLASS": {
		"prefix": "CLASS",
		"body": [
			"class ${1:ClassName} {",
			"\tpublic:",
			"\t\t$2",
			"\tprivate:",
			"\t\t$3",
			"}"
		],
		"description": "Classes are a blueprint for creating individual objects that contain the general characteristics of a defined object type."
	},
	"FUNCTION": {
		"prefix": "FUNCTION",
		"body": [
			"${1|bool,char,double,float,int,void|} ${2:functionName} (${3:methodParameters}) {",
			"\t${4:/*CODE*/}",
			"}",
			" ",
			"//function call within the class:",
			"${2:functionName}(); "
		],
		"description": "A function is a block of code that can be called from another location in the program or class. It is used to reduce the repetition of multiple lines of code. The return statement concludes the execution of the block of code. The function can either return a value (of dataType, declared in the function header), or return nothing (use the 'void' dataType)."
	},
	"FRIEND_FUNCTION": {
		"prefix": "FRIEND_FUNCTION",
		"body": [
			"class ${1:ClassName}",
			"{",
			"\tfriend ${2:data_type} ${3:function_name}(${4:arguments});",
			"};"
		],
		"description": "Friend functions can access private and protected members of a class object passed into the function."
	},
	"INHERITANCE": {
		"prefix": "INHERITANCE",
		"body": [
			"class ${1:derivedClass} : ${2|public:,private:|} ${3:baseClass} {",
			"\t${4:CODE}",
			"};"
		],
		"description": "Inheritance is used to inherit another class' members, including fields and methods. A derived class inherits a base class' members"
	},
	"DESTRUCTOR": {
		"prefix": "DESTRUCTOR",
		"body": [
			"~${1:ClassName}(void) {",
			"\t${2:code to run on object deletion}",
			"}"
		],
		"description": "The destructor is a method called when the object is destroyed."
	},
	"FOR_LOOP": {
		"prefix": "FOR_LOOP",
		"body": [
			"int ${i};",
			"for (int ${i} = ${1:length}; i ${2|>,>=,<=,<|} ${3:testExpression}; ${4:updateStatement};) {",
			"\t${5:/* code */}",
			"}"
		],
		"description": "The for loop is used to use a control structure that executes a block of code a specified number of times."
	},
	"FOR_LOOP_AUTO": {
		"prefix": "FOR_LOOP_AUTO",
		"body": [
			"for (auto i = m.begin(); i != m.end(); ++i)",
			"{",
			"\t${1:CODE}",
			"}"
		],
		"description": "For loop that uses the 'auto data type' "
	},
	"FOR_REVERSE": {
		"prefix": "FOR_REVERSE",
		"body": [
			"for (int ${i} = ${1:length} - 1; ${i} >= ${2:0}; ${i}--)",
			"{",
			"\t$3",
			"}"
		],
		"description": "reverse 'for' loop"
	},
	"FOR_EACH": {
		"prefix": "FOR_EACH",
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
			"\t${1:CODE}",
			"} while(${2:booleanExpression});"
		],
		"description": "The do-while loop executes a block of code while a boolean expression evaluates to true. It checks the boolean expression after each iteration. It terminates as soon as the expression evaluates to false."
	},
	"WHILE_LOOP": {
		"prefix": "WHILE_LOOP",
		"body": [
			"while (${1:booleanExpression})",
			"{",
			"\t${2:CODE}",
			"}"
		],
		"description": "The while loop executes a block of code while a boolean expression evaluates to true. It terminates as soon as the expression evaluates to false. The boolean expression is evaluated before each iteration."
	},
	"IF": {
		"prefix": "IF",
		"body": [
			"if(${1:booleanExpression1}) { ",
			"\t${2:Executes when booleanExpression1 holds true}",
			"} ",
			"else if(${3:booleanExpression2}) { ",
			"\t${4:Executes when booleanExpression2 holds true}",
			"} ",
			"else { ",
			"\t${5:Executes when neither booleanExpression1 nor booleanExpression2 are true}",
			"}"
		],
		"description": "The if else block controls decision making by checking true/false statements resulting in different executions of code, depending on if the result is true and if the result is false."
	},
	"ELSE": {
		"prefix": "ELSE",
		"body": [
			"else",
			"{",
			"\t${1:CODE}",
			"}"
		],
		"description": "else statement block"
	},
	"ELSE_IF": {
		"prefix": "ELSE_IF",
		"body": [
			"else if (${1:booleanExpression1})",
			"{",
			"\t{$2:CODE}",
			"}"
		],
		"description": "else-if statement block"
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
	"ifdef": {
		"prefix": "ifdef",
		"body": [
			"#ifdef ${DEBUG}",
			"\t${1:CODE}",
			"#endif // ${DEBUG}"
		],
		"description": "#ifdef allows that a section of a program is compiled only if the defined constant that is specified as the parameter has been defined, independently of its value."
	},
	"IFNDEF": {
		"prefix": "IFNDEF",
		"body": [
			"#ifndef ${1:1}",
			"\t$2",
			"#endif // !$1"
		],
		"description": "the code between the #ifndef directive and the #endif directive is only compiled if the constant name that is specified has not been defined previously."
	},
	"HEADER_FILE": {
		"prefix": "HEADER_FILE",
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
	"PRAGMA_ONCE": {
		"prefix": "PRAGMA_ONCE",
		"body": [
			"#pragma once"
		],
		"description": "#pragma once is a non-standard but widely supported preprocessor directive designed to cause the current source file to be included only once in a single compilation."
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
	"COUT_ENDL": {
		"prefix": "COUT_ENDL",
		"body": [
			"std::cout << \"${1:message}\" << std::endl;"
		],
		"description": "standard output stream"
	},
	"CIN": {
		"prefix": "CIN",
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
	"STD::": {
		"prefix": "STD::",
		"body": [
			"std::"
		],
		"description": "std::"
	},
	/**** ALGORITHMS ****/
	"BINARY_SEARCH": {
		"prefix": "BINARY_SEARCH",
		"body": [
			"binary_search(${1:startaddress}, ${2:endaddress}, ${3:valuetofind})"
		],
		"description": "*The main idea behind this algorithm is to keep dividing the array in half (divide and conquer) until the element is found, or all the elements are exhausted.\n**startaddress: the address of the first element of the array\n**endaddress: the address of the last element of the array\n**valuetofind: the target value which we have to search for."
	},

	/**** VECTORS START ****/
  "VECTOR_CAPACITY": {
		"prefix": "VECTOR_CAPACITY",
		"body": [
			".${1|capacity();,size();,max_size();|}"
		],
    "description": "**capacity() – Returns the size of the storage space currently allocated to the vector expressed as number of elements.\n**size() – Returns the number of elements in the vector.\n**max_size() – Returns the maximum number of elements that the vector can hold."
	},
	"VECTOR_ELEMENT_ACCESS": {
		"prefix": "VECTOR_ELEMENT_ACCESS",
		"body": [
			".${1|front();,back();|}"
		],
    "description": "**front() – Returns a reference to the first element in the vector\n**back() – Returns a reference to the last element in the vector"
  },
	"VECTOR_ITERATORS": {
		"prefix": "VECTOR_ITERATORS",
		"body": [
			".${1|begin();,end();|}"
		],
		"description": "**front() – Returns a reference to the first element in the vector\n**back() – Returns a reference to the last element in the vector"
		},
		"VECTOR_MODIFIERS": {
			"prefix": "VECTOR_MODIFIERS",
			"body": [
				".${1|assign(//size . //value);,at(//position);,clear();,emplace(//position . //element_to_insert);,emplace_back(//value);,end();,pop_back();,push_back(//value);,swap(//vectorName2);|}"
			],
			"description": "**assign() – It assigns new value to the vector elements by replacing old ones\n**at() function is used reference the element present at the position given as the parameter to the function\n**clear() – It is used to remove all the elements of the vector container\n**emplace() – It extends the container by inserting new element at position\n**emplace_back() – It is used to insert a new element into the vector container, the new element is added to the end of the vector\n**pop_back() – It is used to pop or remove elements from a vector from the back.\n**push_back() – It push the elements into a vector from the back\n**swap() – It is used to swap the contents of one vector with another vector of same type. Sizes may differ."
		},
/**** VECTORS END ****/
"STRUCT": {
  "prefix": "STRUCT",
  "body": [
    "struct ${1:Struct_Name}",
    "{",
    "\t${2|char,double,int,std::string|}",
  	"};"
  	],
  	"description": "A structure is a collection of variables of different data types under a single name."
	},
	"SORT_ARRAY": {
		"prefix": "SORT_ARRAY",
		"body": [
			"sort(${1:Name_of_Array}, ${1:Name_of_Array} + ${2:Size_of_Array})"
		],
		"description": "Sorting a array"
	},
	"SORT_VECTOR": {
		"prefix": "SORT_VECTOR",
		"body": [
			"sort(${1:Name_of_Vector}.begin(), ${1:Name_of_Vector}.end()"
		],
		"description": "Sorting a vector"
	},
	"ITERATE_VECTOR": {
		"prefix": "ITERATE_VECTOR",
		"body": [
			"std::vector<${1|int,char,double,std::string|}> ${2:v};",
			"${2:v} = {1, 2, 3, 4};",
			"for (auto i : ${2:v})",
			"\tstd::cout << i << ' ';",
			"std::cout << '\n';",
			"// prints \"1 2 3 4\""
		],
		"description": "Iterate a vector using for loop"
	},
	"INCLUDE": {
		"prefix": "INCLUDE",
		"body": [
			"#include <${1|algorithm,array,bits/stdc++.h,boost,cmath,iterator,iostream,list,map,memory,sstream,string,tuple,vector|}>"
		],
		"description": "include"
	},
	"POINTER": {
		"prefix": "POINTER",
		"body": [
			"${1|char,double,int,std::string|} *${2:pointer_name} = &${3:variable_name};"
		],
		"description": "A pointer is a variable whose value is the address of another variable."
	},
	"REFERENCE": {
		"prefix": "REFERENCE",
		"body": [
			"${1|char,double,int,std::string|} &${2:reference_name} = ${3:variable_name};"
		],
		"description": "A reference variable is an alias, that is, another name for an already existing variable. A reference, like a pointer is also implemented by storing the address of an object. A reference can be thought of as a constant pointer (not to be confused with a pointer to a constant value!) with automatic indirection, i.e the compiler will apply the * operator for you."
	},
	"VECTOR": {
		"prefix": "VECTOR",
		"body": [
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
	},
	"SELECT_SORT": {
		"prefix": "SELECT_SORT",
		"body": [
			"/*********************************/",
			"     /*** Print Vector ***/",
			"/********************************/",
			"// Print a vector to std::cout.",
			"void PrintVector(std::vector<int> &a, std::string sortname)",
			"{",
			"\tstd::cout << \"Printing \" << sortname << \": \";",
			"\t// Add a tab to make it look more presentable.",
			"\tif(sortname != \"Selection sort\" && sortname != \"Insertion sort\") ",
			"  { ",
			"    std::cout << \"\\t\";",
			"  }",
			"\tfor(int i = 0; i < a.size(); i++)",
			"\t{",
			"\t\tstd::cout << a[i] << \" \";",
			"\t}",
			"\tstd::cout << std::endl;",
			"}",
			"",
			"/*********************************/",
			"     /*** Selection Sort ***/",
			"/********************************/",
			"// Running time: O(N^2). Space Required: O(1) Stable: No.",
			"void SelectionSort(std::vector<int> a)",
			"{",
			"\t// Go through each element of the vector.",
			"\tfor(int i = 0; i < a.size(); i++)",
			"\t\t{",
			"      int currNum = a[i];",
			"      int currIndex = i;",
			"      ",
			"      // Search for the minimum element in the rest of the array.",
			"      int minNum = a[i]; // Default it to the current element being min.",
			"      int minIndex = i; ",
			"      ",
			"      for(int j = i + 1; j < a.size(); j++) // Every element after the current.",
			"      {",
			"        int num = a[j];",
			"        int index = j;",
			"        // If this element is smaller than the minimum so far, update the min variable.",
			"        if(num < minNum)",
			"        {",
			"          minNum = num;",
			"          minIndex = index;",
			"        }",
			"      }",
			"      // We found the minimum number. Perform the swap.",
			"      // (It's fine if the current element is the minimum.)",
			"      int temp = currNum;",
			"      a[currIndex] = minNum;",
			"      a[minIndex] = temp;",
			"\t}",
			"\t// Output the sorted vector.",
			"\tPrintVector(a, \"Selection sort\");",
			"}",
			"",
			"int main() ",
			"{",
			"\tstd::cout << \"Program started.\" << std::endl;",
			"\t// Let's create an unsorted array (vector).",
			"\tstd::vector<int> a = {3, 5, 1, 3, 4, 8, 1, 7, 11, 9, 2, 5, 6, 1};",
			"\t// Print our unsorted vector out.",
			"\tPrintVector(a, \"Unsorted\");",
			"\t// Call each of our sorting algorithms (function) on our vector.",
			"\tSelectionSort(a);",
			"\tstd::cout << \"Program ended.\" << std::endl;",
			"\treturn 0;",
			"}",
			""
		],
		"description": "select_sort"
	},
	"INSERTION_SORT": {
		"prefix": "INSERTION_SORT",
		"body": [
			"/*********************************/",
			"      /*** Print Vector ***/",
			"/********************************/",
			"// Print a vector to std::cout.",
			"void PrintVector(std::vector<int> &a, std::string sortname)",
			"{",
			"  std::cout << \"Printing \" << sortname << \": \";",
			"  // Add a tab to make it look more presentable.",
			"  if(sortname != \"Selection sort\" && sortname != \"Insertion sort\") ",
			"  { ",
			"    std::cout << \"\\t\";",
			"  }",
			"  for(int i = 0; i < a.size(); i++)",
			"  {",
			"    std::cout << a[i] << \" \";",
			"  }",
			"  std::cout << std::endl;",
			"}",
			"",
			"/*********************************/",
			"     /*** Insertion Sort ***/",
			"/********************************/",
			"// Running time: O(N^2). Space Required: O(1). Stable: Yes.",
			"void InsertionSort(std::vector<int> a)",
			"{",
			"\t// Go through each element of the array (we don't need to check the first).",
			"\tfor(int i = 1; i < a.size(); i++)",
			"\t{",
			"\t\tint currNum = a[i];",
			"\t\tint currIndex = i;",
			"",
			"\t// If the current element is smaller than the element to it's left (and a left element exists)...",
			"\twhile(currNum < a[currIndex-1] && currIndex > 0)",
			"\t{",
			"\t\tint leftIndex = currIndex-1;",
			"\t\tint leftNum = a[leftIndex];",
			"",
			"\t// Swap the current number and it's left number.",
			"\ta[leftIndex] = currNum;",
			"\ta[currIndex] = leftNum;",
			"",
			"\t// Update the currIndex for the next iteration of this while loop.",
			"\tcurrIndex = leftIndex;",
			"\t}",
			"}",
			"",
			"\t// Output the sorted vector.",
			"\tPrintVector(a, \"Insertion sort\");",
			"}",
			"",
			"int main() ",
			"{",
			"  std::cout << \"Program started.\" << std::endl;",
			"  // Let's create an unsorted array (vector).",
			"  std::vector<int> a = {3, 5, 1, 3, 4, 8, 1, 7, 11, 9, 2, 5, 6, 1};",
			"  // Print our unsorted vector out.",
			"  PrintVector(a, \"Unsorted\");",
			"  // Call each of our sorting algorithms (function) on our vector.",
			"  InsertionSort(a);",
			"  std::cout << \"Program ended.\" << std::endl;",
			"  return 0;",
			"}",
			""
		],
		"description": "insertion_sort"
	},
	"MERGE_SORT": {
		"prefix": "MERGE_SORT",
		"body": [
			"/*********************************/",
			"      /*** Print Vector ***/",
			"/********************************/",
			"// Print a vector to std::cout.",
			"void PrintVector(std::vector<int> &a, std::string sortname)",
			"{",
			"  std::cout << \"Printing \" << sortname << \": \";",
			"  // Add a tab to make it look more presentable.",
			"  if(sortname != \"Selection sort\" && sortname != \"Insertion sort\") ",
			"  { ",
			"    std::cout << \"\\t\";",
			"  }",
			"  for(int i = 0; i < a.size(); i++)",
			"  {",
			"    std::cout << a[i] << \" \";",
			"  }",
			"  std::cout << std::endl;",
			"}",
			"",
			"/*********************************/",
			"    /*** Merge Sort ***/",
			"/********************************/",
			"// Running time: O(NlogN). Space Required: O(N) Stable: Yes.std::",
			"void Merge(std::vector<int> &a, int startIndex, int middleIndex, int endIndex)",
			"{",
			"\t// Size of the two sub-arrays.",
			"\tint n1 = middleIndex - startIndex + 1;",
			"\tint n2 = endIndex - middleIndex; ",
			"",
			"\t// Create temporary vectors.",
			"\tstd::vector<int> L(n1);",
			"\tstd::vector<int> R(n2);",
			"",
			"\t// Copy the data in a to our temp vectors.",
			"\tfor(int i = 0; i < n1; i++)",
			"\t{ ",
			"\t\tL[i] = a[startIndex + i]; ",
			"\t}",
			"\tfor(int i = 0; i < n2; i++)",
			"\t{ ",
			"\t\tR[i] = a[middleIndex + 1 + i]; ",
			"\t}",
			"",
			"\t// Merge the temp vectors back into a.",
			"\tint leftIndex = 0;            // Initial index of the first sub-array.",
			"\tint rightIndex = 0;           // Initial index of the second sub-array.",
			"\tint mergedIndex = startIndex; // Initial index of the merged array.",
			"",
			"\t// Selectively choose the smallest element from the sub-arrays to put into the merged array. ",
			"\twhile(leftIndex < n1 && rightIndex < n2)",
			"\t{",
			"\t\tint leftNum = L[leftIndex];",
			"\t\tint rightNum = R[rightIndex];",
			"",
			"\t\t// The left number is smaller, so put it in the merged array.",
			"\t\t// And increment the index.",
			"\t\tif(leftNum <= rightNum)",
			"\t\t{",
			"\t\t\ta[mergedIndex] = leftNum;",
			"\t\t\tleftIndex++;",
			"\t\t}",
			"\t\t// The right number is smaller, so put it in the merged array.",
			"\t\telse",
			"\t\t{",
			"\t\t\ta[mergedIndex] = rightNum;",
			"\t\t\trightIndex++;",
			"\t\t}",
			"\t\tmergedIndex++;",
			"\t}",
			"",
			"\t// Copy any remaining elements in the left and right sub-arrays, if there are any.",
			"\twhile(leftIndex < n1)",
			"\t{",
			"\t\ta[mergedIndex] = L[leftIndex];",
			"\t\tleftIndex++;",
			"\t\tmergedIndex++;",
			"\t}",
			"\twhile(rightIndex < n2)",
			"\t{",
			"\t\ta[mergedIndex] = R[rightIndex];",
			"\t\trightIndex++;",
			"\t\tmergedIndex++;",
			"\t}",
			"}",
			"",
			"void Divide(std::vector<int> &a, int startIndex, int endIndex)",
			"{",
			"\t// This (sub)array is bigger than 2 elements, so divide it.",
			"\tif(startIndex < endIndex) ",
			"\t{",
			"\t\tint middleIndex = (startIndex + endIndex)/2;",
			"\t\t// Recursively divide the two sub-arrays we can form from this.",
			"\t\tDivide(a, startIndex, middleIndex);",
			"\t\tDivide(a, middleIndex + 1, endIndex);",
			"\t\t// Now merge these two sub-arrays together.",
			"\t\tMerge(a, startIndex, middleIndex, endIndex);",
			"\t}",
			"}",
			"",
			"void MergeSort(std::vector<int> a)",
			"{",
			"\t// Divide needs to be called recursively.",
			"\t// We begin by dividing a from the first index to the last.",
			"\tDivide(a, 0, a.size() - 1);",
			"\t// Output the sorted vector.",
			"\tPrintVector(a, \"Merge sort\");",
			"}",
			"",
			"int main() ",
			"{",
			"  std::cout << \"Program started.\" << std::endl;",
			"  // Let's create an unsorted array (vector).",
			"  std::vector<int> a = {3, 5, 1, 3, 4, 8, 1, 7, 11, 9, 2, 5, 6, 1};",
			"  // Print our unsorted vector out.",
			"  PrintVector(a, \"Unsorted\");",
			"  // Call each of our sorting algorithms (function) on our vector.",
			"  MergeSort(a);",
			"  std::cout << \"Program ended.\" << std::endl;",
			"  return 0;",
			"}",
			""
		],
		"description": "merge_sort"
	},
	"QUICK_SORT": {
		"prefix": "QUICK_SORT",
		"body": [
			"/*********************************/",
			"      /*** Print Vector ***/",
			"/********************************/",
			"// Print a vector to std::cout.",
			"void PrintVector(std::vector<int> &a, std::string sortname)",
			"{",
			"  std::cout << \"Printing \" << sortname << \": \";",
			"  // Add a tab to make it look more presentable.",
			"  if(sortname != \"Selection sort\" && sortname != \"Insertion sort\") ",
			"  { ",
			"    std::cout << \"\t\";",
			"  }",
			"  for(int i = 0; i < a.size(); i++)",
			"  {",
			"    std::cout << a[i] << \" \";",
			"  }",
			"  std::cout << std::endl;",
			"}",
			"/*********************************************/",
			"",
			"/*********************************/",
			"    /*** Quick Sort ***/",
			"/********************************/",
			"// Running time: O(NlogN). Space Required: O(N) Stable: Yes.",
			"int Partition(std::vector<int> &a, int startIndex, int endIndex)",
			"{",
			"\t// Choose our pivot as the last element in the array.",
			"\tint pivotNum = a[endIndex];",
			"\tint pivotIndex = endIndex;",
			"",
			"\t// The index of our \"wall\".",
			"\t// Left of the wall means smaller elements than the pivot.",
			"\t// Right of the wall means bigger elements than the pivot.",
			"\tint wallIndex = startIndex - 1;",
			"\t// Go through each element in this sub-array.",
			"\tfor(int i = startIndex; i <= endIndex - 1; i++)",
			"\t{",
			"\t\tint currNum = a[i];",
			"\t\tint currIndex = i;",
			"\t\t// If the current element is smaller than (or equal to) the pivot...",
			"\t\tif(currNum <= pivotNum)",
			"\t\t{",
			"\t\t\t// Increment our wallIndex. (Move our wall to the right.)",
			"\t\t\twallIndex++;",
			"\t\t\t// The number at the wall.",
			"\t\t\tint wallNum = a[wallIndex];",
			"\t\t\t// Swap the current element and whatever is right of the wall (which is at the new wallIndex).",
			"\t\t\ta[wallIndex] = currNum;",
			"\t\t\ta[currIndex] = wallNum;",
			"\t\t}",
			"\t}",
			"\t// Finally, move our pivot number to the right of the wall (in between the sub-arrays).",
			"\twallIndex++;",
			"\tint wallNum = a[wallIndex];",
			"\ta[wallIndex] = pivotNum;",
			"\ta[pivotIndex] = wallNum;",
			"",
			"\t// Return the index of the pivot (which is now the wallIndex.",
			"\treturn wallIndex;",
			"}",
			"",
			"void QDivide(std::vector<int> &a, int startIndex, int endIndex)",
			"{",
			"\t// If the sub-array is bigger than one element in size...",
			"\tif(startIndex < endIndex)",
			"\t{",
			"\t\t// Partition the array.",
			"\t\tint pivotIndex = Partition(a, startIndex, endIndex);",
			"\t\t// Recursively divide and partition the two sub-arrays.",
			"\t\tQDivide(a, startIndex, pivotIndex - 1);",
			"\t\tQDivide(a, pivotIndex + 1, endIndex);",
			"\t}",
			"}",
			"",
			"void QuickSort(std::vector<int> a)",
			"{",
			"\t// Recursively divide the vector. Start from the beginning and the end.",
			"\tQDivide(a, 0, a.size() - 1);",
			"\t// Output the sorted vector.",
			"\tPrintVector(a, \"Quick sort\");",
			"}",
			"/*********************************************/",
			"",
			"int main() ",
			"{",
			"  std::cout << \"Program started.\" << std::endl;",
			"  // Let's create an unsorted array (vector).",
			"  std::vector<int> a = {3, 5, 1, 3, 4, 8, 1, 7, 11, 9, 2, 5, 6, 1};",
			"  // Print our unsorted vector out.",
			"  PrintVector(a, \"Unsorted\");",
			"  // Call each of our sorting algorithms (function) on our vector.",
			"  QuickSort(a);",
			"  std::cout << \"Program ended.\" << std::endl;",
			"  return 0;",
			"}",
			""
		],
		"description": "quick_sort"
	}
}
```

