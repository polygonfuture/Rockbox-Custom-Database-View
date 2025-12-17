# Rockbox-Custom-Database-View
Custom database view using tagnavi_custom.config

This file gives you the ability to create custom menus within your database view.   

I've built my own to simplify the main database view and to add custom genre menu to match my library.
You will need to edit this file to match your library or in the way you want to organize your database view.

### Example of my database view ###

- Album Artist
- Album
- Artist
- Genre  `(custom genre menu)`
- Shuffle Songs
- Search

# How to use this file / Troubleshooting
*Word of warning:* 

Editing the tagnavi can be slow and frustrating.  You have to make edits, save it to the rockbox device and then restart the device to see the changes in the database.

### Save the **tagnavi_custom.config** file to your root `.rockbox` folder on your device. ###

If you make edits and your menu suddently doesnt work or is broken, it means you have a typo of some sort.  Either bad syntax or you've mispelled something.
Always try making small changes first, save to device and test.  Once you get a feel of editing the tagnavi then you can start to make larger changes.

**REMEMBER TO MAKE BACKUPS OF YOUR TAGNAVI AS YOU MAKE CHANGES.  IT WILL MAKE YOUR LIFE EASIER**


# Important Info / Custom Genre Menu
The "Genre" menu on the main menu is a custom menu built specifically for my music library and genre tagging styhle.  You need to edit this to fit your own library.  
Otherwise, it likely will **NOT** properly find your own tags.

# Editing the Genre Menu
The genre tagging on rockbox devices such as iPod are severely limited.  Multiple genres are often ignored and only the first is displayed.

I built this `tagnavi_custom.config` to simplify the Genre listings on my rockbox device and make genre navigation more functional and cleaner. 
Please feel free to edit to fit your own tags and genres.   

# Pattern Matching Genres
I use pattern matching of genres in order to combine or exclude genre keywords in my custom list.   

- `~` symbol means **contains**

- `!` symbol means **does not contain**

- `|` symbol means **OR**

---

**Example of pattern matching:**

`"Funk" -> albumartist ? genre ~ "Funk" -> album -> title = "fmt_gtitle"`

*A "Funk" submenu lists albumbartists whose genre contains "Funk" in the genre tag.   Selecting an artist shows you the album, then the title.*


`"Folk" -> albumartist ? genre ~ "Folk" & genre !~ "Indie Folk" & genre !~ "Folk Rock" & genre !~ "Folktronica" & genre !~ "Psychedelic Folk"& genre !~ "Classic Folk" -> album -> title = "fmt_gtitle"`

*The "folk" submenu lists albumartists whose genre contains "Folk", but does nto contain indie folk, folk rock, folktronica, so on and so forth.*


`"All" -> albumartist ? genre ~ "Dance" | genre ~ "Afrobeat" | genre ~ "Funk" | genre ~ "Disco" | genre ~ "Downtempo" | genre ~ "Worldbeat" | genre ~ "Dub" | genre ~ "Techno" | genre ~ "Trance" | genre ~ "IDM" | genre ~ "House" | genre ~ "Club" -> album -> title = "fmt_gtitle"`

*An "All" submenu (under dance genre menu) shows album artists that contain the word "Dance", OR "Afrobeat, or "Funk", or "Disco", etc etc etc.*




# Tagnavi_custom Editing guide
There is a great guide on editing the Tagnavi_custom.config file located on the rockbox wiki:
[Custom Tagnavi](https://www.rockbox.org/wiki/DataBase.html#tagnavi.config_v2.0_Syntax)

You can add or remove a comment symbol `#` in this tagnavi to hide or remove sections.    
