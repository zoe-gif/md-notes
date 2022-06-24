https://www.bilibili.com/video/BV1oW411e7du?spm_id_from=333.337.search-card.all.click

excersize files to be downloaded

20220622

---

## Setting

- File - option - trust center - trust center setting - trusted location
- Navigation bar
	- Hide and unhide object
	- `F11` to show and hide navi bar
- Quick access tool bar
- Backup: file - save as
	- Access will move to backup file

## Basics

- Object
	- Table
		- Store data
	- Query
		- Record for analysis such as calculation and filter
	- Form
		- Interact with user to allow data entry
	- Report
		- Output table and query
	- Macro
		- Autpmate process
- Key
	- Connect tables
	- Primary key: 1st col for identification
	- Foreign key: 2nd or 3rd col
- Data type
	- Short text
	- Long text
	- Number
	- Date/Time
	- Currency
	- AutoNumber
	- Boolean
	- Attachment: hyperlink is better
	- Calculated filed and lookup wizard
- Database normalization
	- First Normal Form
		- Each cell of a tbale contains only a single value
	- Second Normal Form
		- Data not dependent on the primary key moved to a separate table
	- Third Normal Form
		- Data that can be derived from other fields should not be stored
- Import external data

## Table

 - Relationship
	- Database tool - relationship
	- Enforce referential intergrity
		- Disable orphan record with no parent relationship
	- Cascade update/delete
		- Change realted table when parent table change
	- Type
		- One to many
		- Many to many
			- By creating a junction table
		- One to one
			- If btoh are primary keys
			- Not common
- View
	- Datasheet view
	- Design view
- Control input format with mask
	- Design view - General - Input mask
	- <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220623093648.png" width="600" height="">
- Set defualt value
	- Design view - Default value
	- Field - Default value
- Validation rule
	- Design view - Validation rule & text
	- <img src="https://raw.githubusercontent.com/zoe-gif/images/master/20220625000151.png" width="650" height="">
- Create lookup field
	- Design view - Date type - Lookup wizard
	- Show list of value choices when inputting data in field
	- Limit to list: cannot enter value other than listed
- Properties of field
	- Field size
	- Required
	- Indexed: accelerate searching and sorting, more time for update
- Text formating
	- Change color of alternative rows
	- Design view - Long text - Text format - Rich text
		- Can change format of partial characters in a field
- Sort & Filter
- Search & Replace `Ctrl + F`

## Query
- Function
	- Ask quetions about data
	- Not store data, but reassemble data fields in tables
	- Update every time of run
	- Look and function like a data table

## Form


## Rerport 


## Maintain datebase



https://www.bilibili.com/video/BV1oW411e7du?p=34&vd_source=b5d7c4596d85c4178f7e5a439f1eba44