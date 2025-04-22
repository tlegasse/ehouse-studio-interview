# General notes
I'm going to start with the Shopify Dawn theme, which I believe to have reasonable default sections, and generally feel like its approach to theme features primarily using vanilla Javascript and web components leads to maintainable themes over long maintenance. I also don't see anything in the Figma doc that stands out as difficult with Dawn.


I also see the Debut theme, which used to be a go-to theme before Dawn, and especially before OS2.0.


I start most projects by pulling theme files and setting up a repo, which is no different here.


## Global Theme Changes
### Color Schemes
- Color Scheme 1: Announcement bar
- Color Scheme 2: Header and general white background theme sections
- Color Scheme 3: Gray background "Value Prop" section


## Announcement bar
Dawn includes an image banner, so I'll be leveraging what we already have there.


## Header
The section padding settings are modified to allow for more vertical padding. A new maximum of 100 is provided for each padding range selector ("Top" and "Bottom")
The section is extended to include the following settings:
- `Display Inline Search Form` (`checkbox`): Replaces the search button to be a full, in-header, search form.
- `Promo Callout` (`header`)
- `Promo Text` (`text`): Promo text that displays as a link next to the main menu
- `Promo Destination` (`url`): Promo destination


## Sections
### Image Hero
The section is extended to include the following options:


The "Image banner" section's "Buttons" block is extended to include the following new options:
- `Button 3` (`heading`)
- `Label` (`text`)
- `Link` (`url`)
- `Outline style` (`checkbox`)


- `Button 4` (`heading`)
- `Label` (`text`)
- `Link` (`url`)
- `Outline style` (`checkbox`)


### Image with Text Side-by-side
The "Image with text" section is extended to include the following option:
- `Display content section border` (`checkbox`): Causes a border to display around the content section with additional section padding.


### New Arrivals, College Bound and Value Prop Callouts
The "Multicolumn section is extended to include the following options:
- `Display Mobile Gap` (`checkbox`)


The "Multicolumn" section's "Column" block is extended to include the following option:
- `Display content over image` (`checkbox`): Causes the content over the column's image.
- `Menu` (`link_list`): Displays selected menu on the column's content area below any text.
- `Content Padding` (`heading`)
- `Top Desktop` (`range`):
 - With a minimum value of `0`
 - With a default value of `46`
 - With a maximum value of `100`
- `Top Mobile` (`range`):
 - With a minimum value of `0`
 - With a default value of `46`
 - With a maximum value of `100`
- `Bottom Desktop` (`range`)
 - With a minimum value of `0`
 - With a default value of `51`
 - With a maximum value of `100`
- `Bottom Mobile` (`range`)
 - With a minimum value of `0`
 - With a default value of `51`
 - With a maximum value of `100`
