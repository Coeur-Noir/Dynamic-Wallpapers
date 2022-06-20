# Dynamic-Wallpapers
Resources and how-to intended for my memory, mostly.\
Animated ( well… rather slow transitionning ) backgrounds for Gnome desktop environment in my « pro » machines.\
I only show here personal, non branded material, free for any usage.\
Tested on Ubuntu 22.04.\
<img src="trianglify/trianglify.gif"> <img src="wood-clock-spot/wood-clock-spot.gif">
## Roles of files and folders
Gnome Control Center ( settings ) looks into\
**/usr/share/gnome-background-properties** ( system side for all users )\
and\
**$HOME/.local/share/gnome-background-properties** ( user's side only )\
for a « pointer » *.xml* file in order to offer its referenced slideshow(s).

This « pointer »
- can be named whatever you like but must be into a **gnome-background-properties** folder 
- contains amongst other things the path to the « description » of the slideshows and eventually the list of pictures for a slideshow ( not mandatory )
- may list many slideshows,
- is a rather short file ( if you don't list all the pictures in it. )

The « description » *.xml* file targeted by the « pointer »
- can be named and located however you like - as long as it's referenced accordingly into the « pointer »
- contains the full *scenario* for your slideswhow, paths to the needed pictures, durations for static picture and transitions from a picture to another
- gives the whole duration of the slideshow ( sum of *all* durations, static + transition )
- sets a start time, synchronized with your system time so slideshows can act ± as clocks or **match day and night**, or seasons or events…
- may be a long file ( depending on how many pictures involved in the slideshow. )

## Other helpful notes
Regarding elements involved in a slideshow ( both *.xml* files + pictures )
- if saved only system side for all users to access, they must bear read right for others - owned by *root:root* with *644* on files, *755* on parent directories
- if saved only one user's side - owned by *$USER:$USER* with *640* on files and *750* on parent directories should be enough
- therefore if a « pointer » and/or a « description » are saved system side targeting elements saved user's side, those latter elements and parent directories should bear read right for others ( while owned by $USER ).

Regarding *marks* in *.xml* files
- paths to files \<filename> \<file> \<from> \<to> are absolute, full letters typed, no $HOME nor ~ nor ../ there and no need for escaping *space* character in paths ( no " nor ' nor \\ there )
- absence of \<static> crashes gnome-shell but
- absence of \<transition> seems ok, so carefully prefer keeping all marks while setting 0.0 values
- **launch *gnome-control-center* from terminal** to check your *.xml* files, it will spot issues ;-)

## Beware the future of these slideswhows in Gnome may be uncertain
they still work this way in Ubuntu 22.04 though,\
where you have the ability to set a still ( or animated ) background ***per* style of theme**, one for light and one for dark.
