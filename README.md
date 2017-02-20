# Welcome to Babator Implementation Guide

### 1. Deployment
  
**1.1 Babator Tag(s) setup**
  
  For the ongoing operation of Babator, the only thing that is needed is the Babator Tag. During the
  ramp-up period and going live with online recommendations, there is limited use of the Babator minitag,
  for manual selection of the places where recommendations should be displayed.

**1.2 Setup of the Babator Tag**

  Embed the following Babator tag in your site header, before any players' tag. If you’re video player
  is imbedded in an iframe, embed the Tag in the iframe as well, before any players' tag:

  ```
  <script type="application/javascript"
  src="http://eu-services.babator.com/tags?apiKey=075302b0-1069-11e6-98b3-21e382ad5859"
  async></script>
  ```

**1.3 How it Works**

   The Tag is downloaded from Babator’s CDN as a javascript file (SDK) that does all the interactions
   with the player for the Babator services. Babator CDN is implemented on top of Amazon S3 and
   CloudFront services to ensure 100% availability with content distribution to end users with low
   latency and high data transfer speeds.
     
### 2. Integration

**2.1 Catalog (Feed)**

  Babator will need* a link to the Catalog (meta-data) of videos of the website where it will be
  implemented. This is very important, because it ensures that Babator only recommend videos that are
  approved by website.
  Usually, it is a link to a web address that has the data, or a link to RSS. It could also be an API to that
  gives access to the relevant data.
  The format of the data can be in either XML or JSON. Babator will be able to handle any structure, as
  long as it is documented.

  *If a Feed is currently unavailable, an interim solution can be worked out.

**2.2 Contents of the Feed**

  The Feed should contain:
  * VideoId - unique identifier
  * URL - video url
  * Title - the video title
  * DurationSec - the video duration in seconds
  * ImageUrl - the video thumbnail image url
  * PublishDate - video publish date & time (timestamp)
  * Keywords – Tags (if existing)
  * Additional data specific to the media (e.g. TV series, episode, actors, etc.) – optional
    
### 3. Phased Implementation

**3.1 Phase I: Collect User Activity & Actions**

  Period: 2-4 Weeks.

  The phase includes transparent collection of real traffic data from the publisher site, and tuning of
  Babator’s system and algorithms to the specific site.
  In this Stage, Babator collects all user activity (video views) and actions (implicit & explicit behavior
  towards the video) for all the video views. The data collected is used to prepare the Babator system
  for providing online recommendations by training the Babator Engine.

**3.2 Phase II: Online Recommendations- Limited Deployment**

  Period: 2 Weeks.

  In the limited deployment, Babator is implemented to provide recommendations to a minimum rate
  of 1M views (on a monthly basis) or 10% (the larger of) of the customer’s real traffic, while collecting
  data from all the assets. This is usually achieved by fully deploying Babator on several sites in the
  network, that collectively reach the minimum traffic for the limited deployment.
  Babator’s online recommendations, are provided by Babator’s 2 products: InRead & InPlayer.

**3.3 Phase III: Monetization Pilot**

  Period: 4 Weeks.

  For the monetization pilot, Babator will be deployed on a minimum of 2M views (on a monthly basis)
  on the sites where it is operating, to ensure enough traffic for effective validation of the monetization
  model.
  During the Monetization Pilot, Babator will be monetizing all views initiated by Babator, by using its
  own monetization waterfall platform. Video views not initiated by Babator will not be affected, and will
  continue to be monetized by the sites’ own monetization methods.
  To optimize the monetization (increase overall revenue), the customer will need to provide:
  * Sites users demographics, and If available, by section.
  * Sites policies on ads (prohibited and restricted ad categories, etc.)
    
**3.4 Phase IV: Full Deployment**

