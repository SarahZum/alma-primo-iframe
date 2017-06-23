# alma-primo-iframe

When using Alma with Primo, the data in the GetIt section of the full record is pulled into an iFrame via an openURL request to Alma.  In Alma, you can add a "Delivery Skin" (General Configuration menu > User Interface Settings > Delivery System Skins) and adjust the CSS of the HTML in the frame.  However, there are some things that we wished to adjust using Javascript, but could not because the Javascript that controls the rest of the Primo site cannot access the contents of an iFrame (for security reasons).

To hack this, we embedded a link to a JS file (on our local web server) within two label settings (Fulfillment Configuration menu > Discovery Interface Display Logic > Labels).  The labels accept HTML.  We used:

c.uresolver.GeneralElectronicServices <script src="https://www.stolaf.edu/library/bridge/primo/locationtab.js"></script>Additional services
c.uresolver.getit2.holding_list.location <script src="https://www.stolaf.edu/library/bridge/primo/locationtab.js"></script> Location & Call Number:

I wanted to use jQuery and I simply copied the library into my JS file so I wouldn't run into cross-domain issues.

