<h1 align="center">Nina Gazzard SPMU & Beauty</h1>

[View the live project here.](https://sdthomas91.github.io/ng-spmu-milestone/)

The purpose of this document is to identify key testing stages and instances where decisions were made to change or keep certain features.

## Header

- ### Navigation

  - Standard navigation featured left aligned menu; amended this to ensure centre alignemnt for easy viewing.
  - Utilised bootstrap and css to ensure logo centered upon scaling down of screen size; this delivers a more appealing aesthetic with the hamburger icon
  - Included some interaction feedback with the navigation in the form of font colour change on hover. The font will change from a light grey to a dark grey to illustrate that it is a clickable link.

- ### Hero Image
        - Callout lays nicely on top of hero image with minimal distractions - site colours used to maintain a minimalist/clean look and feel to the website.
        - Added a larger border radius to the jumbotron to enhance the smooth/clean edge feel to the site.
        - Main image did not convert well across screen downsize so used CSS media query to change background image on smaller screens. Images below display before and after of smaller screen - note how the image looks better but still doesn't distract from the main content:
      <table border="0">
     <tr>
        <td><b style="font-size:30px">Large Screens</b></td>
        <td><b style="font-size:30px">Small Screen Before</b></td>
        <td><b style="font-size:30px">Small Screen After</b></td>
     </tr>
     <tr>
        <td><img src="/assets/images/lg-screen-hero-ss.png"></td>
        <td><img src="/assets/images/sml-screen-hero-ss-before.png"></td>
        <td><img src="/assets/images/sml-screen-hero-ss-after.png"></td>
     </tr>
  </table>

## About Us Section

- ### Multi-Column (About Tech)
  - Added heading and subheading, image and paragraph. From a UX/UI perspective it didn't sit nicely on a large screen and didn't scale well across medium screens. (images below)
    <table border="0">
   <tr>
      <td><b style="font-size:30px">Large Before</b></td>
      <td><b style="font-size:30px">Medium Before</b></td>
   </tr>
   <tr>
      <td><img src="/assets/images/lg-screen-about-before.png"></td>
      <td><img src="/assets/images/med-screen-about-before.png"></td>
   </tr>
  </table>
