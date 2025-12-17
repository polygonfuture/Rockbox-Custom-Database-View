# Rockbox-Custom-Database-View
Custom database view using tagnavi_custom.config

# Info

This file gives you the ability to create custom menus within your database view.   

I've built my own to simplify the main database view.   

***For example:**

Album Artist
Album
Artist
Genre
Shuffle Songs
Search

Feel free to copy and edit this menu for your own rockbox player.

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
