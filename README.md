# Questions
## What is your workflow like?

### Discovery
I start projects, both large and small, by performing a discovery phase.


I go through the mockups and compare them to the base theme.


I call out, per-section, any differences that I see, and describe the section, block or theme level changes that I expect to see to control the various display states.


I usually find most of the differences as I work through theme options to attempt to get it as close to the mocks as possible. Of course, there's always the potential for net-new sections to be created, so I might throw a placeholder section in its spot to mark where work should go. This phase has a lot of benefits, even for really simple setups.


After documenting changes thoroughly enough to dispel any potential questions, I prepare the development environment.


Each unique body of work will generally get its own task in whatever project management system is used.




### Development Environment and Theme Setup
This generally looks like the following.
- Run a `git init` in a new directory.
- Add a `README.md` that touches on some of the unique aspects of the theme and the development setup instructions. All projects are unique, so I generally end up including quite a few items therein.
- I generally create multiple branches that each represent environments to keep changes organized, and to best collaborate with my colleagues.
- I usually set up github (as often as possible for the Shopify integrations) with a `main` and `staging` theme branch, of which, each will be imported as `Production` and `Staging` respectively.




### Dev begins
Development can (in most cases asynchronously, sometimes with others) proceed by tickets/tasks being pulled into my work queue.


Work will proceed with section, block or theme options being incorporated.


After the options are properly incorporated, I'll implement either class names, generated CSS or perhaps JS/JSON features being implemented.


In the case of data driven user interfaces, I like to incorporate JSON objects to communicate with the component. I'll pull them in with a try/catch block wrapping the de-serialization.


General styling, HTML templating features and other work will proceed.


After the development cycle, each section is assigned a corresponding QA task, and will go through as many QA cycles as is needed to succeed and move on.


### Tools
My workflow is keyboard centric and portable. I use a terminal emulator + Tmux and Neovim. I keep one terminal session open with Shopify CLI running watch, and edit files in another.


---

## What was challenging / what wasn’t? (Please be honest here. If something is challenging, that’s ok and it will just help us see where our strengths and weaknesses might fit with yours and vice versa.)


Overall, I found this coding test to be most challenging in terms of scope of work, rather than any specific change that tripped me up.


Related to section development, I found modifying the `Multicolumn` section to be most challenging. The `New Arrivals` and `Value Prop Callouts` were _just_ similar enough to lead me to extending the section rather than building a new, custom, section.


## Any general decisions you make along the way.


I decided to add the "Sale" as an optional link, and keep it out of any menu. If it were part of a menu, some sort of metafield options would be necessary to reliably display the link, and additional admin training would be required.


## What would you discuss with a designer through the process?


 - I notice the header has a "My Account" heading, but it doesn't resemble a link (no underline). Do we want to link that to the account page after the user is logged in?
 - If this were a full theme build, I'd ask what content types should be search-able from the header.
 - I noticed that the Hero Image section is titled "50% off hero slider", but I see no slider controls. Can I assume that this will always be a one slide "Hero Image" section, or should I plan to implement a slider library like Flickity?
 - Does the announcement bar link to a shipping FAQ?
 - Do you have an expectation that the header menu and the new arrivals menu items link to the same page and will always match?
 - On the mobile mockups, I'm seeing a 10px horizontal gap on the right side of the "Vaca This Way" section's content area. Is this intentional? If so, will we ever need to accommodate a right aligned content section? Any other diversity of section settings I should plan for related to mobile placement?
 - I notice that the header search input has a low contrast ratio. This may present usability issues for users with visual impairments, should we tweak that or keep as is?
 - On mobile, I see that the cart bubble indicator has no quantity listed as on desktop. Do we want that to just display as is, like a "you have items" indicator?


## What are a few code decisions you made and why?


 - To expedite development, I embedded nested media queries into styles where needed. There are potential tradeoffs with this, like pre-processing performance hits and potential legacy support issues.
 - I duplicated the functionality of the header search icon, and modified it to display inline and removed any modal functionality. This ended up expediting rich feature implementation, though will need some additional CSS polish.
 - I implemented classnames in the [BEM format](https://getbem.com/), which, to me, generally makes naming a much simpler affair, and leads to more maintainable code over time.
 - I implemented `rem` absolute unit sizing rather than `px`, thereby matching Dawn's conventions and ensuring site scaling relative to a base font size.


# Conclusion

The coding task took me around the alotted 8 hours. I was able to complete the primary objectives with minimal tablet styling. The code can be reviewed at any time on the main branch of the repo. I'll be looking forward to any feedback!

---






# General notes and planning from implementation
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


# Sections
## Image Hero
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


## Image with Text Side-by-side
The "Image with text" section is extended to include the following option:
- `Display content section border` (`checkbox`): Causes a border to display around the content section with additional section padding.


## New Arrivals, College Bound and Value Prop Callouts
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
