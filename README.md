# Cupid API Whitepaper
An plug-in play API for the OkCupid: Free Dating Website.

### Python Libraries
- Beautiful Soup
- Peewee ORM

### OkCupid Match Python Class; Attributes:
- `Match.username`: Returns a match's username as a string.
- `Match.age`: Returns a match's age as a integer.
- `Match.percentage`: Returns an integer of the match's percentage.
- `Match.location`: Returns a match's location as a string.
- `Match.essays`: Returns a list containing each of a match's essays as a string.
- `Match.details`: Returns a string of a a match's details section.
- `Match.background`: Returns a string of a match's background section.
- `Match.misc_details`: Returns a string of a match's background section.
- `Match.looking_for`: Returns a string of a match's looking for section.
- `Match.topic_percentages`: Returns a list of tuples of a match's topic percentages for each section (Religon, Sex, Lifestyle, Ethics, etc). 
  * `(<topic_name>, <percentage_int>)`


### OkCupid Match Python Class; Hidden Methods:
- `Match.__init__`: Argument: `<match's_username>`. Appends username to 'https://www.okcupid.com/profile/' and uses BS4 to grab HTML.
- `Match.__repr__`: String of command used to create Python object
- `Match.__str__`: Username, Age, City, Match % 
- `Match.__get_details()`: Produces a string variable of the details section.
- `Match.__get_background()`: Produces a string variable of the background section.
- `Match.__get_misc_details()`: Produces a string variable of the misc details section
- `Match.__get_looking_for()`: Produces a string variable of the what there looking for section.
- `Match.__two_of_us_percentages()`: Produces a dictionary object with the question section name as the KEY, and the percentage as the VALUE (just the integer, no '%' sign)
- `Match.__get_essays_dict()`: Produces a dictionary object, with the essay titles as KEYS, and the essays themseleves as VALUES.

### OkCupid Match Python Class; Exposed Methods:
- `Match.essay_titles()`: Returns a list of essay titles
- `Match.get_essay(<essay_title>)`: Returns a string of the specified essay.
- `Match.create_db_entry()`: Creates a database entry based on the current attributes associated with the Python Match instance.
- `Match.update_db_entry(<match's_username>)`: Updates the specified database entry based on the current attributes associated with the Python Match instance this method is being called on.
