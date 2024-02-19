# Client Management Tool

## Overview
The Client Management Tool is an Excel-based solution designed to manage client information efficiently. It includes features such as generating random client data, tracking client status, and recording communication history. This README.md file provides an overview of the project and documents the formulas used in the implementation.

## Formulas Used
### On Sheet "Client_Information"
 - `Generating Random Names`
```
=INDEX({"John","Alice","Michael","Emily","David","Sarah","John Smith","Alex","Olivia","Daniel","Sophia"},RANDBETWEEN(1,11))
Generates random names for clients using the INDEX and RANDBETWEEN functions.
```
 - `Generating Random Company Text`
```
=IF(RAND()<0.5,"","Company " & RANDBETWEEN(1,9))
Generates random company names or leaves the cell blank for some entries using the IF and RANDBETWEEN functions.
```

 - `Generating Random Email Addresses`
```
=IF(B2<>"",CONCATENATE(LEFT(A2,1), ".", TRIM(LEFT(B2,7)), RIGHT(B2,1),"@example.com"),CONCATENATE(LEFT(A2,1),"@example.com"))
Generates random email addresses for clients using the CONCATENATE function and conditions based on existing data.
```

 - `Generating Random Telephone Numbers`
```
=TEXT(RANDBETWEEN(1000000000,9999999999),"000-000-0000")
Generates random telephone numbers for clients using the RANDBETWEEN function.
```

 - `Client Status Calculation`
```
=IF(E2<>"Completed","Active","Not in touch")
Calculates the client status based on the project status using the IF function.
```

`Conditional Formatting for Client Status`
```
=IF(E2<>"Completed","Active","Not in touch")
Applies conditional formatting to highlight active clients in green with white font and inactive clients in light red with red bold font.
```

 - `Dynamic Link to Communication History`
```
=HYPERLINK(CONCATENATE("#'Communication_History'!C", ROW() + 0), "View History")
Creates a dynamic link to the communication history sheet for each client using the HYPERLINK function.
```

## On Sheet "Communication_History"

 - `Generating Random Dates`
```
=RANDBETWEEN(DATE(2023,1,1), DATE(2024,12,31))
Generates random dates for communication history entries using the RANDBETWEEN function.
```

 - `Generating Random Type of Communication`
```
=INDEX({"Email","Call","Meeting"}, RANDBETWEEN(1,3))
Generates random types of communication for communication history entries using the INDEX and RANDBETWEEN functions.
```

`Setting Random Description`
```
=IF(B2<>"Meeting",INDEX({"Follow-up on client inquiry","Update on project status"},RANDBETWEEN(1,2)), "Discussion about Project X")
Sets random descriptions for communication history entries based on the type of communication using the IF and INDEX functions.
```

## Usage
1. Open the Excel workbook containing the Client Management Tool.
2. Navigate to the "Client_Information" sheet to view and manage client information.
3. Use the dropdown menus to select client status and view communication history for each client.
4. Navigate to the "Communication_History" sheet to view and manage communication history entries.
