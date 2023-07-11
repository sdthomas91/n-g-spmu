<h1 align="center">Nina Gazzard SPMU & Beauty</h1>

[View the live project here.](https://sdthomas91.github.io/ng-spmu-milestone/)

The purpose of this document is to identify key testing stages and instances where decisions were made to change or keep certain features.

## Bugs

1. White Space down right hand side of screen - only on smaller screens

- Systematically commented out each section and continued to refresh page. No section seemed responsible. Then commented out footer and white line disappeared. Added class of container-fluid and no-gutters to footer element and un-commented code and now working fine.

1. All fonts shrunk down to a tiny sizing and has thrown off entire web fonts

- Tried hard refresh of browser window but did not work - closed down codeanywhere and reopened project with full reset and site now responding fine with correct size fonts.

1. ID anchor link stopped working

- Anchor link for About Us section ceased functioning properly - had added Bootstrap class name "container-fluid" into the "id" instead of the "class". Removed and now works fine.

1. A new white space down the right hand side of the screen

![White space down side of smaller screens](/assets/images/white-line-mobile.png)

- Used google chrome developer tools to examine each element. It became clear that the first and second div of the "Services Section" were responsible.
- Attempted to utilise no gutters rule as this fixed the issue last time, but this time it was unsuccessful.
- Within google chrome developer tools I noticed that the bootstrap "row" class was administering a margin right and left of -15px.
  ![row Class issues](/assets/images/row-class-issue.png)
- Once removed, white space disappeared. So added rule of margin:0 to "services-container" class and issue was resolved
  ![white space resolution](/assets/images/white-space-resolution.png)

1. Whole first section has gone blank

- On large screen the whole first section is blank/white, yet when scaled down the section returns to normal.

  | Desktop view (larger than 992px)                             |              Smaller (less than 992px) view               |
  | ------------------------------------------------------------ | :-------------------------------------------------------: |
  | ![>992px view of issue](/assets/images/greater-than-992.png) | ![>992px view of issue](/assets/images/less-than-992.png) |

- Issue seems to be with overlays for blocks in services section. They had all stacked at 100%.

- Set overlay--light on blocks to only show on md screens and below and issue resolved itself

![resolved white block issue](/assets/images/resolved-whiteout.png)

1. Images not showing on deployment
   - when website is deployed to github pages some images appear and others do not.
   - Launched from codeanywhere and website shows up all images okay.

| Logo and hero not showing                 |                 Tech image present                 |                Services images present on large screen                 |                     no service images on small screen |
| ----------------------------------------- | :------------------------------------------------: | :--------------------------------------------------------------------: | ----------------------------------------------------: |
| ![No Logo](assets/images/img-issue-4.png) | ![Tech image shows](assets/images/img-issue-3.png) | ![Services images show on large screen](assets/images/img-issue-2.png) | ![Not on small screen](assets/images/img-issue-1.png) |

- Chrome dev tools used to identify any links between images that do show and images that do not
- Connection found - images showing source url started with "assets/" images not showing started with "/assets/"
- corrected syntax and images now showing okay

2. Mobile view issue found - technician section sitting over to the right
   - Full screen the balance is fine but on mobile view the content is off center
   - ![content off center](assets/images/tech-center-bug.jpeg)
   - used dev tools to check and the margin used to create balance in full screen is what throws it off
   - Added media query to remove margin on smaller screens
   - Issue resolved and content now centered nicely
   - ![content centered](assets/images/tech-issue-fix.jpeg)

# SECTION TESTING

## Header

- ### Logo

  - When resolving an issue with the hero image I also noticed the logo sits off center on mobile view.

  ![Logo off center](assets/images/logo-center-issue.jpeg)

  - Using chrome dev tools I identified that the logo was centering in its own element (link) but that element wouldn't center.

  - added a left padding to mobile view only of 50px and issue resolved nicely

  ![Logo now centered](assets/images/logo-centered.jpeg)

- ### Navigation

  - Standard navigation featured left aligned menu; amended this to ensure centre alignemnt for easy viewing.
  - Utilised bootstrap and css to ensure logo centered upon scaling down of screen size; this delivers a more appealing aesthetic with the hamburger icon
  - Included some interaction feedback with the navigation in the form of font colour change on hover. The font will change from a light grey to a dark grey to illustrate that it is a clickable link.

- ### Hero Image

1. Callout
   - Callout lays nicely on top of hero image with minimal distractions - site colours used to maintain a minimalist/clean look and feel to the website.
   - Added a larger border radius to the jumbotron to enhance the smooth/clean edge feel to the site.
1. Image
   - Main image did not convert well across screen downsize so used CSS media query to change background image on smaller screens. Images below display before and after of smaller screen - note how the image looks better but still doesn't distract from the main content:

| Large screen Before                                                    |                               Small Screen Before                               |                                                           Small Screen After |
| ---------------------------------------------------------------------- | :-----------------------------------------------------------------------------: | ---------------------------------------------------------------------------: |
| ![Before of site on large screen](assets/images/lg-screen-hero-ss.png) | ![Before of site on Small Screen](/assets/images/sml-screen-hero-ss-before.png) | ![After of site on Small screen](assets/images/sml-screen-hero-ss-after.png) |

I also added some white space below the hero image on mobile to ensure users know that it is scrollable

1. Fixed position image not working on iphone

- Upon testing deployment I noticed that on my iPhone 14 the mobile hero image was not displaying and instead just a colour block.

|                                       Mobile Image not showing |
| -------------------------------------------------------------: |
| ![mobile image not showing](assets/images/mobile-hero-bug.PNG) |

- Research suggests that parallax scrolling does not always work on mobile displays and so will provide a fallback image without fixed attribute and see if it resolves issue.

- Following testing, fallback image didn't work and caused page to load very slowly. Decided on this occasion to leave parallax effect on mobile screens as no fixed attribute has resolved the issue

|                                               Mobile Image Resolved |
| ------------------------------------------------------------------: |
| ![mobile image not showing](assets/images/mobile-hero-resolve.jpeg) |

## About Us Section

- ### Multi-Column (About Tech)

  - Added heading and subheading, image and paragraph. From a UX/UI perspective it didn't sit nicely on a large screen and didn't scale well across medium screens. (images below)

| Large Before                                                                 |                              Small Screen Before                              |
| ---------------------------------------------------------------------------- | :---------------------------------------------------------------------------: |
| ![Before of site on large screen](/assets/images/lg-screen-about-before.png) | ![Before of site on medium screen](assets/images/med-screen-about-before.png) |

Amended to remove heading and include inline with image for larger screens and have content stack on smaller screens (also some styling amendements such as borders and backgrounds) - as per images below:

| Large After                                                                 |                                 Medium After                                  |
| --------------------------------------------------------------------------- | :---------------------------------------------------------------------------: |
| ![Before of site on large screen](/assets/images/lg-screen-about-after.png) | ![Before of site on medium screen](/assets/images/med-screen-about-after.png) |

## Services Section

### Service blocks

#### Desktop view

- Decided on alternating side by side display for large screens and stacked view for smaller screens
- side by side originally block colours but decided a gradient on middle element provides a more modern and elegant feel to the site
- had to ensure text and backgrounds were contrasting correctly across each block

#### Mobile view

- Originally when going for stacked decided to use a light overlay with dark text for good contrast
- Used image as background instead of stacking image and text as would be too monotonous with the element above doing the same
- Even with overlay, the blocks were not presenting nicely and were not very reader friendly
  - ![Light blocks](assets/images/light-blocks.png)
- Decided to change to a dark overlay on image block, light (but not completely opaque) container for text and uniform text and "hr" elements
  - ![Dark blocks with box](assets/images/dark-blocks.png)
- Readability improved and screen contrast more in line with WebAIM recommendations

# ELEMENT TESTING

## Buttons (outside of standard buttons)

- ### Back to top button
  - Added a back to top button - had some issues with sizing and position. Used Stack Overflow article [here] (https://stackoverflow.com/questions/68627683/scroll-up-button-without-javascript#:~:text=Simply%20make%20a%20%3Ca%20href,on%20top%20of%20the%20page.&text=The%20link%20has%20the%20style,scrolls%20to%20the%20very%20top.) to help debug.
  - Added smooth scroll to CSS to ensure a smooth experience for users
  - Used empty href in order to ensure a complete top scroll - tried "ID" anchor link but was clunky and unreliable
  - Utilised interaction feedback to help users know it is a clickable button
  - Font awesome up arrow used to illustrate functionality
  - 'aria-hidden="true"' used as semantic icon - text alternative span used
