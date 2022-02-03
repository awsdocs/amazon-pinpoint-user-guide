# Using message template helpers<a name="message-template-helpers"></a>

With Pinpoint templates, customers can create reusable message templates based on the Handlebars\.js language\. Helpers provide a variety of features like formatting a price to a specific Region's currency or adding a time zone\-based location\. A helper can use a specific string or integer for the value or a specific Amazon Pinpoint message variable\.

These are the categories of helpers, described in the following sections:

## Default helpers<a name="defaulthelpers"></a>

This section describes the **built\-in** helpers provided by Handlebars\. For the full list see [Built\-in Helpers](https://handlebarsjs.com/guide/builtin-helpers.html) at [handlebarsjs\.com](https://handlebarsjs.com)\. These are the built\-in helpers:
+ `each` – Iterates a list\.
+ `if` – Evaluates a statement\.

*each*  
Iterates a list\. This helper uses only a block statement\. You can optionally   
+ Pass `@index` in the request to reference the current loop index\.
+ Use the `this` helper to reference the current element being iterated\.
+ Return the helper response in a list, using the `<li>` tag\.
**Usage**  
`{{#each value}}`  
Value at position `{{@index}}` is `{{this}}`\.  
`{{else}}`  
Condition is false\.  
`{{/each}}`  
`each` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/each}}` in the block statement\.  
**Example**  
In this example, `each` is used to return a list of a user's favorite colors\. For a `false`, an `else` statement is returned\. If the request is this  
`{{#each User.UserAttributes.FavoriteColors}}`  
`<li>{{this}}</li>`  
`{{else}}`  
*You have no favorite colors\.*  
`{{/each}}` returns  
+ *red*
+ *blue*
+ *yellow*
for a true statement\.

*if*  
Evaluates whether something is true and returns a response based on the evaluation\.   
**Usage**  
`{{#if value}}`  
Value is not undefined  
`{{else}}`  
Value is undefined  
`{{/if}}`  
`if` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/if}}` in the block statement\.  
**Example**  
In this example, the `if` helper is used to evaluate whether a user's first name\. If the name is found, a greeting is returned that passes the user's first name in the response\. Otherwise, the `else` statement returns an alternative greeting\.  
`{{#if User.UserAttributes.FirstName.[0]}}`  
`Hello {{User.UserAttributes.FirstName.[0]}},`  
`{{else}}`  
*Hello,*  
`{{/if}}`  
returns *Hello, Jane* if the `if` helper is true\.

## Conditional helpers<a name="conditionhelpers"></a>

This section describes the **conditional** helpers\. 

Conditional helpers can be used on either a single line or in a block statement\. You can customize the response regardless of which helper method you use\. You can pass additional conditional helpers within both single line and block statements\. The following conditional helpers show usage first for a single line and then a block statement using an optional `else` clause\. These are the conditional helpers:
+ `and` – Compares whether or not all passed elements are equal\.
+ `eq` – Tests whether two elements are equal\.
+ `gt` – Tests whether one element is greater than another\.
+ `gte` – Tests whether one element is greater than or equal to another\.
+ `if` – Evalutes whether something is true\.
+ `lt` – Tests whether one element is less than another\.
+ `lte` – Tests whether one element is less than or equal to another\.
+ `neq` – Evaluates whether two elements are not equal\.
+ `not` – Intverts the response of a boolean operation\.
+ `or` – Compares whether any of the elements in the argument are equal\.

*and*  
Compares whether *all* elements passed in an argument are equal, and then returns the response based on the result\. This helper can be used for non\-Boolean values\. You must pass at least two elements for the condition\.  
**Usage**  
+ `{{and valuea valueb valuec valued yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#and valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/and}}`

  `and` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/and}}` in the block statement\.
**Example**  
In this example, `eq` is used within the `and` block statement to determine whether both strings passed for the `Location.City `and `Location.Country` attributes are true\. If both conditions are equal, then a true statement is returned\. If either of those attributes are false, then an `else` statement is returned\.  
`{{#and (eq Location.City "Los Angeles") (eq Location.Country "US")}}`  
*You live in Los Angeles and the US\.*  
`{{else}}`  
*You don’t live in Los Angeles and the US\.*  
`{{/and}}`

*eq*  
Tests whether two elements are equal or if the value of one element is equal to a passed string\.  
**Usage**  
+ `{{eq valuea valueb yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#eq valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/eq}}`

  `eq` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/eq}}` in the block statement\.
**Example**  
In this example, `eq` is used to evaluate whether the value of `User.UserAttributes.FavoriteColors.[0]` is *Red*\. If the response is `true`, a true statement is returned\. If the response is `false`, then an `else` statement is returned\.  
`{{#eq User.UserAttributes.FavoriteColors.[0] "red"}}`  
*Your favorite color is red\.*  
`{{else}}`  
*You don't like red\.*  
`{{/eq}}`

*gt*  
Tests whether the value of one element is greater than another\.   
**Usage**  
+ `{{gt valuea valueb yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#gt valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/gt}}`

  `gt` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/gt}}` in the block statement\.
**Example**  
In this example, the helper compares the value of `User.UserAttributes.UserAge.[0]` attribute against a string, *17*, to verify whether the user's age is greater than 17\. If the response is `true`, a true statement is returned\. If the response is `false`, then an `else` statement is returned\.  
`{{#gt User.UserAttributes.UserAge.[0] "17"}}`  
*You are old enough to rent a car\.*  
`{{else}}`  
*You are not old enough to rent a car\.*  
`{{/gt}}`

*gte*  
Tests whether the value of one element is greater than or equal to another\.  
`Usage`  
+ `{{gte valuea valueb yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#gte valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/gte}}`

  `get` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/gte}}` in the block statement\.
**Example**  
In this example, the helper compares the `User.UserAttributes.UserAge.[0]` attribute against a string, *18*, to verify whether the user's age is greater than or equal to 18\. If the response is `true`, a true statement is returned\. If the response is `false`, then an `else` statement is returned\.  
`{{#gte User.UserAttributes.UserAge.[0] "18"}}`  
*You are old enough to rent a car\.*  
`{{else}}`  
*You are not old enough to rent a car\.*  
`{{/gte}}`

*if*  
Evaluates whether something is true and returns a response based on the evaluation\.  
**Usage**  
+ `{{#if value}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#if value}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/if}}`

  `if` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/if}}` in the block statement\.
**Example**  
In this example, the if helper is used to evaluate whether a user's first name\. If the name is found, a greeting is returned that passes the user's first name in the response\. Otherwise, the else statement returns an alternative greeting\.  
`{{#if User.UserAttributes.FirstName.[0]}}`  
*Hello* `{{User.UserAttributes.FirstName.[0]}}`*,*  
`{{else}}`  
*Hello,*  
`{{/if}}`  
returns *Hello Jane,* if the if helper is true\.

*lt*  
Tests whether the value of one element is less than the value of another\.  
**Usage**  
+ `{{lt valuea valueb yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#lt valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/lt}}`

  `lt` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/lt}}` in the block statement\.
**Example**  
In this example, the helper compares the `User.UserAttributes.UserAge.[0]` attribute against a string, *18* , to verify whether the user's age is less than 18\. If the response is `true`, a true statement is returned\. If the response is `false`, then an `else` statement is returned\.  
`{{#lt User.UserAttributes.UserAge.[0] "18"}}`  
*You are not old enough to rent a car\.*  
`{{else}}`  
*You are old enough to rent a car\.*  
`{{/lt}}`

*lte*  
Tests whether the value of an element is less than or equal to another\.  
**Usage**  
+ `{{lte valuea valueb yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#lte valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/lte}}`

  `lte` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/lte}}` in the block statement\.
**Example**  
In this block statement, the helper compares the `User.UserAttributes.UserAge.[0]` attribute against a string, *17*, to verify whether the user's age is equal to 17 or younger\. If the response is `true`, a true statement is returned\. If the response is `false`, then an `else` statement is returned\.  
`{{#lte User.UserAttributes.Age.[0] "17"}}`  
*You are not old enough to rent a car\.*  
`{{else}}`  
*You are old enough to rent a car\.*  
`{{/lte}}`

*neq*  
Test whether two elements are *not* equal\.  
**Usage**  
+ `{{neq valuea valueb yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#neq valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/neq}}`

  `neq` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/neq}}` in the block statement\.
**Example**  
In this block statement, the `User.UserAttributes.FavoriteColors.[0]` attribute is checked against a string, `Red`\. If the response is `true`, a true statement is returned\. If the response is `false`, then an `else` statement is returned\.  
`{{#neq User.UserAttributes.Favorite.Colors.[0] "red"}}`  
*You do not like red\.*  
`{{else}}`  
*You like red\.*  
`{{/neq}}`

*not*  
Inverts the response of a Boolean operation, so that if `not` is a positive comparison, then a `true` statement is returned\. If the response is false, then an else statement is returned\.   
**Usage**  
+ `{{not value yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\.
+ `{{#not value}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/not}}`

  `not` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/not}}` in the block statement\.
**Example**  
In this block statement, the `User.UerAttributes.FavoriteColors.[0]` attribute is checked against a string, *red*, using the `eq` helper\. The `not` helper then returns the opposite of the `eq` helper\. If the response returns any color other than *red*, a `true` a statement is returned\. If the response returns *red*, then an `else` statement is returned indicating a false statement\.  
`{{#not (eq User.UserAttributes.Favorite.Colors.[0] "red")}}`  
*You do not like red\.*  
`{{else}}`  
*You like red\.*  
`{{/not}}`  
**Example**  
In this example,   
`{{not (eq User.UserAttributes.FavoriteColors.[0] "red")}}`  
returns false if `User.UserAttributes.FavoriteColors.[0]` is *red*\.

*or*  
Compares whether *any* of the elements in the argument are equal, and then returns a response based on the result\. This helper can be used for non\-Boolean values\.  
**Usage**  
+ `{{or valuea valueb valuec valued yes='y' no='n'}}`

  You can replace *y* and *n* with other values, such as *yes* and *no*, or any other string you want returned, depending on the condition\. You must pass at least two elements for the condition\.
+ `{{#or valuea valueb}}`

  Condition is true\.

  `{{else}}`

  Condition is false\.

  `{{/or}}`

  `or` must be prefaced with a pound sign \(`#`\) and conclude with a closing `{{/or}}` in the block statement\.
**Example**  
In this `or` block statement, two strings for the `Location.City` attribute are compared additionally using the `eq` helper\. If either of the attributes are `true`, then a true statement is returned\. If one or more of the responses are `false`, then an `else` statement is returned\.  
`{{#or (eq Location.City "Los Angeles") (eq Location.City "Seattle")}}`  
*You live on the West Coast of the United States\.*  
`{{else}}`  
*You do not live on the West Coast of the United States\.*  
`{{/or}}`

## String helpers<a name="stringhelpers"></a>

This section describes the following **string **helpers:
+ `abbreviate` – Truncates a value\.
+ `capitalize` – Capitalizes each word between white spaces\.
+ `capitalizeFirst` – Capitalizes the first character of a value\.
+ `center` – Centers a value\.
+ `cut` – Cuts a value\.
+ `dateFormat` – Sets the date style\.
+ `inflect` – Returns a singular or plural string based on the count\.
+ `join` – Joins an array, iterator, or an iterable object\.
+ `ljust` – Justifies a value to the left margin\.
+ `lower` – Converts a value to lower case\.
+ `now` – Prints the current date\.
+ `ordinalize` – Ordinalizes a numeric value\.
+ `replace` – Replaces one string with another\.
+ `rjust` – Justifies a value to the right margin\.
+ `slugify` – Converts a value to lower case and removes non\-word characters, converts spaces to hyphens, and removes trailing white space\.
+ `stripTags` – Strips \[X\]HTML tags from a value\.
+ `substring` – Returns a new string as a substring of a passed value\.
+ `upper` – Converts the passed value to upper case\.
+ `yesno` – Replaces true, false, and no with Yes, No, and Maybe\.

*abbreviate*  
Truncates a value if the value exceeds the number specified\. White spaces are included in the length count\. An ellipsis displays in the response to indicate a truncated value\. The ellipsis counts towards the truncated value in the response\. This type of helper is useful if you have a large table and minimal space\. Truncating values in a cell allows you to have a more uniform look to the table\.  
**Usage**  
 `{{abbreviate value X}}`, replacing *X* with a numeric value indicating the number of characters to keep\. Negative numbers are not supported\.  
**Example**  
In this example, `abbreviate` is used to truncate `User.UserAttributes.LastName.[0]` to six \(6\) characters\. The response includes an ellipsis, the dots of which count towards the six\-character total\.  
`{{abbreviate User.UserAttributes.LastName.[0] 6}}` returns  
*Ale\.\.\.* if *Alejandro* is the value of `[0]`\.

*capitalize*  
Capitalizes each word between white spaces\.  
**Usage**  
 `{{capitalize value}}`  
**Example**  
In this example, initial capitalization is applied to each word for the `Attributes.description.[0]` entry\.  
`{{capitalize Attributes.description.[0]}}`  
If `Attributes.description.[0]` returns   
 *My First Post*, if the value of `Attributes.description.[0]` is *my first post*\.

*capitalizeFirst*  
Capitalizes the first character in a value\.  
**Usage**  
`{{capitalizeFirst value}}`  
**Example**  
In this example, capitalization is applied to the first character of the first word of the `Attributes.description.[0]` entry\.  
`{{capitalizeFirst Attributes.description.[0]}}` returns  
 *My first post*, if the value of `Attributes.description.[0]` is *my first post*\.  
**Example**

*center*  
Centers the value in a field of a given width by the number specified\. You can optionally pass a character to display for the padding or leave the field blank\. If no character is passed a white space is used\.  
**Usage**  
 `{{center value size=X [pad=" "}}` , replacing *X* with a numeric value\.  
If `pad` is kept blank, white space is used as the padding in the response\. If you pass a character, that character displays in each space of the padding\. Negative numbers are not supported\.  
**Example**  
In this example, the value of `Location.City `is centered with a size of *19*\.  
`{{center Location.City size=19}}` returns   
*" Los Angeles "* If `Location.City` is *Los Angeles*\. Note that the quotes displayed in the example output are provided for emphasis only\.

*cut*  
Removes the specified value from a string\.   
**Usage**  
 `{{cut value [" "]}}`, replacing the space within the quotes parameter with the value to cut\. If no parameter value is passed, a white space is used\.   
**Example**  
This example removes the letter *e* from the `Location.City` attribute\.  
`{{cut Location.City "e"}}` returns  
*Los Angls* if `[Location.City` is *Los Angeles*\.

*dateFormat*  
Sets the default date style for the date in any response\. For a list of the time zone IDs, see [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)\.  
**Usage**  
`{{dateFormat date [inputFormat="format1"] [outputFormat="format2"][tz=timeZoneId]}}`  
The `format` parameter must be one of:  
+ "`full`": full date format\. For example: *Tuesday, September 19, 2020*
+ "`long`": long date format\. For example: *September 19, 2020*
+ "`medium`": medium date format\. For example: *Sept 19, 2020*
+ "`short`": short date format\. For example: *9/19/20*
+ "`pattern`": uses a custom date pattern format\. For more information about date patterns, see [https://docs.oracle.com/javase/8/docs/api/java/text/SimpleDateFormat.html](https://docs.oracle.com/javase/8/docs/api/java/text/SimpleDateFormat.html)\.
If a format is passed, then `medium` is used by default\.   
**Example**  
In this example, a message is sent to a user using the `full` date format based on the *America/Los\_Angeles* time zone and a date of **09/19/2020**\.  
`We can meet with you any time on ``{{dateFormat date inputFormat="19/09/2020" outputFormat="full" tz=America/Los_Angeles}}.` returns  
*We can meet with you any time on Tuesday, September 19, 2020\.*

*inflect*  
Returns a singular or plural string based on the count value\.  
**Usage**  
 `{{inflect count singular plural [includeCount=false]}}`  
+ Enter the singular and plural forms of the string you want to pass in the argument\.
+ If `includeCount` is set to `false`, no count is returned in the response\. If set to `true`, the `count` is included in the response\.
**Example**  
The following examples show the inflection for a purchase of apples, with and without `includeCount`\.  
`Thank you for your purchase of {{inflect 3 apple apples includeCount=false}}.` returns:  
*Thank you for your purchase of apples\.*  
If `includeCount` is set to `true`, then the response is  
*Thank you for your purchase of 3 apples\.*

*join*  
Joins an array, iterator, or an iterable object\. The response returns a list, with each value in the list concatenated by the character you pass in the `join`\. For example, you might separate values using a comma \(`,`\)\. The value in this helper must be a list without an attribute position index\. For example, this might be `Attributes.custom_attribute`\.  
**Usage**  
`{{join value " // " [prefix=""] [suffix=""]}}`  
**Example**  
In this example, a list of colors is returned, with the list separated by a comma and a space \(`", "`\):  
`{{join Attributes.favorite_colors ", "}}` returns   
*blue, red, green* if `Attributes.favorite_colors` is the list *blue,red,green*\.

*ljust*  
Justifies the value to the left margin and adds space to the right so that the length of the value matches the number\. Negative numbers are not supported\.  
You can optionally pass a character to display for the `pad` or leave the field blank\. If you leave the `pad` value blank, the default value is a white space\.  
**Usage**  
`{{ljust value X [pad=" "]}}`, where *X* is the total length of the value, including white space\.   
**Example**  
In this example, a left justification value of *15 *is applied to the Location\.City\.  
`{{ljust Location.City 15}}` returns  
*"Los Angeles "* if the value of `Location.City` is *Los Angeles*\. Note that the quotes displayed in the example output are provided for emphasis only\.

*lower*  
Converts a value to all lower case\.  
**Usage**  
`{{lower value}}`  
**Example**  
In this example, the `[0] `entry for `User.UserAttributes.LastName.[0]` is changed to lower case\.  
`{{lower User.UserAttributes.LastName.[0]}}` returns  
*santos* if *Santos* is the value of `[0]`\.

*now*  
Prints out the current date based on the passed time zone ID\. For a list of the time zone IDs, see [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)\.  
**Usage**  
`{{now ["format"] [tz=timeZoneId]}}`  
The `format` parameter must be one of:  
+ "`full`": full date format\. For example: *Tuesday, September 19, 2020*
+ "`long`": long date format\. For example: *September 19, 2020*
+ "`medium`": medium date format\. For example: Sept 19, 2020
+ "`short`": short date format\. For example: 9/19/20
+ "`pattern`": a date pattern\. For more information about date patterns, see [https://docs.oracle.com/javase/8/docs/api/java/text/SimpleDateFormat.html](https://docs.oracle.com/javase/8/docs/api/java/text/SimpleDateFormat.html)\. 
If a format is not passed, then `medium` is used by default\.  
**Example**  
In this example, the current date in Los Angeles is returned with a `medium` format\.  
`{{now "medium" tz=America/Los_Angeles}}` returns   
*Sept 19, 2020*\.

*ordinalize*  
Ordinalizes the numeric value passed in the argument\. For example, *1* is ordinalized as *1st*, *2* as *2nd*, etc\. Only numeric values are supported\.  
**Usage**  
`{{ordinalize [number]}} `  
**Example**  
In this example, the `[0]` entry of `User.UserAttributes.UserAge` is ordinalized and returned, along with a message\.   
`Congratulations on your {{ordinalize User.UserAttributes.UserAge.[0]}} birthday!` returns *22* ordinalized as *22nd*\.  
*Congratulations on your 22nd birthday\!*

*replace*  
Replaces one string with another string\. A string or numeric value must be literal\. Wildcard characters are not supported\.  
**Usage**  
`{{replace stringToReplace replacementValue}}`  
**Example**  
In this example, an underscore \(\_\) replaces a white space\.  
`{{replace Location.City " " "_"}}` returns  
*Los\_Angeles* if the `Location.City `is *Los Angeles*\.

*rjust*  
Justifies the value to the right margin and adds space to the left so that the length of the value matches the number\. Negative numbers are not supported\.  
You can optionally pass a character to display for the `pad` or keep the field blank\. If you keep the `pad` value blank, the default value is a white space\.  
**Usage**  
`{{rjust value X [pad=" "]}}`, where *X* is the total length of the value, including white space\.   
**Example**  
In this example, a right justification value of *15* is applied to the `Location.City` attribute\.  
`{{rjust Location.City 15}}` returns  
*" Los Angeles" *\. if the `Location.City` is *Los Angeles*\. Note that the quotes displayed in the output are provided for emphasis only\.

*slugify*  
Converts the passed value to lowercase, removes non\-word characters \(alphanumeric and underscore\), converts spaces to hyphens, and removes any leading or trailing white space\.  
**Usage**  
`{{slugify value}}`  
**Example**  
In this example, slugify is performed for the `Location.City` attribute\.   
`{{slugify Location.City}}` returns  
*los\-angeles* if `Location.City` is *Los Angeles*\.

*stripTags*  
Strips \[X\]HTML tags from a value\.  
**Usage**  
 `{{stripTags value}}`  
**Example**  
In this example, the HTML tags for the User\.UserAttributes\.interest\.\[0\] are removed\.   
`{{stripTags User.UserAttributes.interests.[0]}}` returns  
*Art*, if `User.UserAttributes.interests.[0]` is `<h1>Art</h1>`\.

*substring*  
Returns a new string as a substring of the passed value\. The length and position are determined by the `startOffset` and `endOffset` parameters, which must be integers\. Negative numbers are not supported\. If an `endOffset` is not passed, the substring uses the original ending value of the string\.  
**Usage**  
`{{substring value startOffset [endOffset]}}`  
**Example**  
In this example, an offset of 4 and endOffset of 9 are applied to the Location\.City attribute\.   
`{{substring Location.City 4 9}} `returns  
`Angel` if Los Angeles is the value of `Location.City` is *Los Angeles*\.

*upper*  
Converts the passed value to upper case\.  
**Usage**  
`{{upper value}}`  
**Example**  
In this example, the `[0] `entry for the `User.UserAttributes.LastName` attribute is converted to all upper case\.  
`{{upper User.UserAttributes.LastName.[0]}}`returns  
*ROE* if the `User.UserAttributes.LastName.[0]` value is *Roe*\.

*yesno*  
Replaces `true`, `false`, and `NULL` with `Yes`, `No`, and `Maybe`\.  
**Usage**  
`{{yesno value [yes="yes"] [no="no"] maybe=["maybe"]}}`  
**Example**  
In this example, the `IsUserSubscribed` attribute returns whether a user is subscribed to a particular list\.  
`{{yesno Attributes.IsUserSubscribed}}` returns   
*yes* if `Attributes.IsUserSubscribed` is *true*\.

## Math and encoding helpers<a name="mathhelpers"></a>

This section describes the **math and encoding** helpers\.
+ `add` – Returns the sum of two numbers\.
+ `ceiling` – Capitalizes each word between white spaces\.
+ `decode64` – Decodes a Base64encoded value to a string\.
+ `divide` – Returns the quotient of two numbers\.
+ `encode64` – Encodes a string using Base64\.
+ `floor` – Rounds an integer to its mathematical floor\.
+ `md5` – Hashes a passed string using the MD5 algorithm\.
+ `modulo` – Returns the remainder of two numbers using floaing points\.
+ `multiply` – Returns the product of two numbers\.
+ `round` – Rounds a decimal to the nearest whole number\.
+ `sha256` – Hashes a passed string using SHA\-256\.
+ `sha512` – Hashes a passed string using SHA\-512\.
+ `subtract` – Returns the difference of two numbers\.
+ `uuid` – Randomly generates a UUID in a 128\-bit format\.

*add*  
Returns the sum of two numbers along with floating points\.  
**Usage**  
`{{add arg1 arg2}}`  
**Example**  
`{{add 5 2.3}} `returns  
*7\.3*

*ceiling*  
Rounds an integer to its mathematical ceiling, which is the highest whole number closest to the passed value\.  
**Usage**  
`{{ceiling value}}`  
**Example**  
`{{ceiling 5.23}}` returns  
*6*

*decode64*  
Decodes a Base64 encoded value to a string\.  
**Usage**  
`{{decode64 "string"}}`  
**Example**  
`{{encode64 "SGVsbG8gd29ybGQ="}}` returns  
*Hello World*

*divide*  
Returns the quotient of two numbers, including floating points\.  
**Usage**  
 `{{divide arg1 arg2}}`  
**Example**  
`{{divide 5 2.3}}` returns  
*2\.17391304*

*encode64*  
Encodes the string passed in the argument using Base64\.  
**Usage**  
`{{encode64 "string"}}`  
**Example**  
`{{encode64 "Hello World"}}`  
*SGVsbG8gd29ybGQ=*

*floor*  
Rounds an integer to its mathematical floor, which is the lowest whole number closes to the passed value\.  
**Usage**  
`{{floor value}}`  
**Example**  
`{{floor 5.23}}` returns  
*5*

*md5*  
Hashes a passed string using the MD5 algorithm\.  
**Usage**  
`{{md5 "string"}}`  
**Example**  
`{{md5 "Hello World"}}`  
*3e25960a79dbc69b674cd4ec67a72c62*

*modulo*  
Returns the remainder of two numbers using floating points\.  
**Usage**  
`{{modulo arg1 arg2}}`  
**Example**  
`{{modulo 7 2}}` returns  
*1*

*multiply*  
Returns the product of two numbers, with any floating points\.  
**Usage**  
`{{multiply arg1 arg2}}`  
**Example**  
`{{multiply 5 2.3}}` returns  
*11\.5*

*round*  
Rounds a decimal place up or down to the nearest whole number\.  
**Usage**  
`{{round value}}`  
**Example**  
`You spent an average of {{round 19.21}} minutes on our website each day.` returns:  
*You spent an average of 19 minutes on our website each day\.*

*sha256*  
Hashes a passed string using SHA\-256 cryptographic security\.  
**Usage**  
`{{sha256 "string"}}`  
**Example**  
`{{sha256 "Hello World"}}` returns  
*a591a6d40bf420404a011733cfb7b190d62c65bf0bcda32b57b277d9ad9f146e*

*sha512*  
Hashes a passed string using SHA\-512 cryptographic security\.  
**Usage**  
`{{sha512 "string"}}`  
**Example**  
`{{sha512 "Hello World"}}` returns  
*2c74fd17edafd80e8447b0d46741ee243b7eb74dd2149a0ab1b9246fb30382f27e853d8585719e0e67cbda0daa8f51671064615d645ae27acb15bfb1447f459b*

*subtract*  
Returns the difference of two numbers, with any floating points\.  
**Usage**  
`{{subtract arg1 arg2}}`  
**Example**  
`{{subtract 5 2.3}} ` returns  
*2\.7*

*uuid*  
Randomly generates a UUID in a standard 128\-bit format\. No value needs to be passed in the argument\.  
**Usage**  
`{{uuid}}`  
**Example**  
`{{uuid}} ` returns  
**95f36680\-152c\-4052\-99ec\-cc3cdf7ca594**

## Inline partials<a name="inlinepartials"></a>

While technically not a helper, inline partials are Handlebars way to simplify templates that include repeated strings, allowing for easier reuse\. For more information see [Inline partials](https://handlebarsjs.com/guide/partials.html#inline-partials) at [handlebarsjs\.com](https://handlebarsjs.com)\. 

**Usage**

`{{#* inline "inlineName"}}Content to reuse{{/inline}}`

To reference the content of the inline partial elsewhere, use:

` {{> inlineName}}`

**Example**

The following example creates an inline partial that includes the recipient's first name, and, if it is available, last name, by adding the following code to the beginning of the template:

`{{#* inline "fullName"}}`

`{{User.UserAttributes.FirstName.[0]}} {{#if User.UserAttributes.LastName.[0]}} {{User.UserAttributes.LastName.[0]}} {{/if}}`

`{{/inline}}`

After creating the `fullName` partial, you can include it anywhere in your template by preceding the name of the partial with a `>` \(greater than\) symbol, followed by a space, as in the following example: `{{> fullName}}`\.

*` Hello {{> fullName}}`*

returns the user's first and last name if true – for example, *Hello Jane Doe*\. Otherwise, if no last name is found, *Hello Jane* is returned\.

Handlebars includes additional features beyond those documented here\. For more information, see [handlebarsjs\.com](https://handlebarsjs.com/)\.

## Using variables with message template helpers<a name="template-helpers-variables"></a>

Pinpoint custom attributes, such as `User.UserAttributes.LastName`, are stored as a list, regardless of whether there's a single item or multiple items\. When passing a list in a helper that expects a string, you must specify the attribute index value along with the attribute name\. This attribute index value indicates the position of a value from the attribute list: `.[0]` for the first entry in the list, `.[1]` for the second, `.[2]` for the third, and so on\. For example, let's say you're using the `upper` helper to convert the first \(`[0]`\) entry of `User.UserAttributes.LastName` to all upper case\. The helper usage is `{{upper value}}`, and the attribute formatted as `User.UserAttributes.LastName`\. Replace *value* with the attribute name and attribute index value `.[0]` as follows: `{{upper User.UserAttributes.LastName.[0]}}`\. The response then returns the `[0]` entry from the list, formatted in all upper case\. For example, if the value of `[0]` is *Santos*, the response returns *SANTOS*\. 

## Using nested helpers<a name="template-helpers-nesting"></a>

 You can nest multiple message template helpers within each other\. The following example shows how to format two helpers: `{{ first helper (second helper)}}`\. The second helper is processed first, followed by the first helper\. Remember that the first helper always determines the output\. Subsequent helpers must be nested within the previous helper as follows: `{{ first helper (second helper (third helper) )}}`\.

The following example shows how to nest two helpers to change **JANE** to **Jane**: `{{capitalizeFirst (lower "JANE")}}`\. `lower` first converts **JANE** to **jane**\. Then `capitalizeFirst` converts **jane** to **Jane**\.