=== Google Pagespeed Insights ===
Contributors: mattkeys
Donate link: http://mattkeys.me/
Tags: SEO, seo, performance, speed, google, search engine optimization, pagespeed, google page speed, page speed, pagespeed insights, google pagespeed insights
Requires at least: 3.6
Tested up to: 4.8
Stable tag: trunk
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Use Google Pagespeed Insights to increase your sites performance, your search engine ranking, and your visitors browsing experience.

== Description ==

Google Pagespeed Insights is a tool that empowers you to make decisions that increase the performance of your website. Recommendations from Google Pagespeed are based upon current industry best practices for desktop and mobile web performance.

Through the addition of advanced data visualization, tagging, filtering, and snapshot technology, Google Pagespeed Insights for Wordpress provides a comprehensive solution for any webmaster looking to increase their site performance, their search engine ranking, and their visitors browsing experience.

= Additional Languages =

* (v1.x translation) Russian Translation provided by: Ivanka from [coupofy.com](http://coupofy.com)
* (v1.x translation) Spanish Translation provided by: Ogi Djuraskovic from [firstsiteguide.com](http://firstsiteguide.com)
* (v1.x translation) Serbian Translation provided by: Ogi Djuraskovic from [firstsiteguide.com](http://firstsiteguide.com)

= Detailed Page Reporting =

Sort your page reports by their Page Speed Score to prioritize the largest areas of opportunity on your site. Page reports utilize easy to read visualizations that allow you to quickly focus in on the most important data to improve your sites performance.

= Report Summaries =

Report Summaries are a powerful and exclusive feature of Google Pagespeed Insights for WordPress. Summaries display your average Page Score, largest areas for improvement across ALL reports, as well as best and lowest performing pages. Report summaries can be filtered to narrow results by: Pages, Posts, Categories, Custom URLs, and Custom Post Types.

Using Report Summaries allows you to ‘zoom out’ from the page-level and better understand the big picture of your sites performance.

= Desktop and Mobile Page Reports =

Best practices for site performance differ greatly between Desktop and Mobile device usage. Configure Google Pagespeed Insights for WordPress to generate Desktop reports, Mobile reports, or both!

Toggle back and forth between report types to see specific suggestions for improving the performance and experience on each platform.

== Installation ==

1. Login to your Wordpress Admin page (usually http://yourdomain.com/wp-admin)
2. Navigate to the Plugins screen and then click the "Add New" button
3. Click on the "Upload" link near the top of the page and browse for the Google Pagespeed Insights for Wordpress zip file
4. Upload the file, and click "Activate Plugin" after the installation completes
5. Congratulations, installation is complete; proceed to configuration.

= Configuration =

An extended version of the folliowing instructions as well as other documentation are included in the "documentation" folder of this plugin.

Google Pagespeed Insights requires a Google API Key. Keys are free and can be obtained from Google. In order to get a key, you will need a Google account such as a GMail account. If you do not already have a Google account you can create one here: https://accounts.google.com/SignUp.

1. Navigate to https://code.google.com/apis/console
2. Login with your Google Account (Create a Google account if you do not have one)
3. Create a new API Key and enable the Google Pagespeed Insights API* (see note about restrictions)
4. Paste your API Key into the Options page of Google Pagespeed Insights for Wordpress

* Try first creating the API key without any 'restrictions'. In my testing there seems to be a bug with using restricitons with the Pagespeed API.

= Requirements =

* Google API Key [https://code.google.com/apis/console/](https://code.google.com/apis/console/)
* WordPress 3.6 or Newer

== Troubleshooting ==

**Please find the below list of potential issues that you may encounter, and the recommended next steps.**

= I entered my API Key and saved the Options, but no Reports are showing up in the Report List. =

- Google Pagespeed needs to be able to load each page to create its report. Make sure that your pages are publicly accessible over the internet.
- Ensure that your API key is entered correctly, and that you have enabled the "PageSpeed Insights API" from the Google API Console.
- In the Options page, under "Advanced Configuration" there is a checkbox called "Log API Exceptions". Any API exception that is not caught and handled automatically will be stored for up to 7 days. This log information can be very helpful when diagnosing issues.

= Page report checks never finish all of the way, I have to press "Start Reporting" again and again to get it to finish checking all of my pages. =

- If the reports seem to always run for a certain length of time before stopping unexpectedly, you may be exceeding your servers Max Execution time. Try increasing the value in Options->Advanced Configuration "Maximum Execution Time".
- Some web hosting providers do not allow the Maximum Execution Time to be overridden or increased. In that case you can try setting the Maximum Script Run Time. This will make the script run for the set period of time, then stop and spawn a new script, to get around timeout issues. Start with a low value, and test. Increase the value one step at a time until you find the largest value that allows your scans to finish successfully.

= An error was reported while trying to check one of my pages, and it has been added to the Ignored Pages section. =

- Navigate to the Ignored Pages tab, find the page, and click "reactivate" to try it again.
- If the page fails again, ensure that the page is publicly accessible from the internet. Non-public pages cannot be checked.
- In some rare cases, pages are not able to be scanned by the Pagespeed API. Try checking your page manually here: https://developers.google.com/speed/pagespeed/insights/. If the page fails to be checked, report the issue to Google so that they can diagnose further.

= I received a Javascript or PHP error. =

- If the error appeared while Google Pagespeed was checking pages, you may have loaded the page while it was storing data. Refresh the page in a couple seconds to see if the issue has gone away.
- If issues persist please report the problem with as much information as you can gather, including: What page you were on, the exact text of the error, or a screenshot of the error.
- In the Options page, under "Advanced Configuration" there is a checkbox called "Log API Exceptions". Any API exception that is not caught and handled automatically will be logged for up to 7 days. This log information can be very helpful when diagnosing issues

= My Page Scores seem really low. When I click "Recheck Results" when viewing Report Details, the score jumps up dramatically. =

- Your server may have been responding slowly when the first report was generated. A slow server response time can have a large impact on your Page Speed Score. If these problems happen frequently you may want to talk with your hosting provider about the problem, or look into alternative hosting providers.

= I want to clear out all of the current page reports and start over. =

1. Navigate to the "Options" tab
2. Expand the "Advanced Configuration" section.
3. Find the "Delete Data" Dropdown
4. Select "Delete Reports Only" to remove all Page Reports
5. Or Select "Delete EVERYTHING" to remove all Page Reports, Custom URLs, Snapshots, and Ignored Pages

== Screenshots ==

1. Filter reports by Pages, Posts, Category Indexes, or Custom Post Types. Sort Report Lists by Page Score to see your highest and lowest performing pages.
2. Seperate reports for Desktop and Mobile page reports. Check each report to receive platform specific recommendations to increase your sites performance.
3. Configure Google Report Language, Report Types, and choose which Wordpress URLs to run reports on.
4. View in-depth report details for recommendations on increasing your sites performance.

== Changelog ==

= 2.0.1 =
* Removed phpseclib unit tests from Google PHP API library to avoid false-positive with WordFence

= 2.0 =
* Major rewrite for better compatibility and performance
* Updated to the latest Google Pagespeed Insights API verison and library
* Fixed issues with bulk installers not generating DB tables
* Consolidated scan methods to a single more reliable method inspired by WP cron
* Better identify, communicate, and resolve issues with environments that have difficulties with scanning pages or API errors
* Improved API error logging
* Added 'abort scan' functionality to cancel an in-progress scan
* Added 'Maximum Script Run Time' option to advanced configuration to allow scans to run in shorter intervals for web hosts which have script timeouts that cannot be overridden
* Update the codebase to adhere better to WordPress coding standards and best practices

= 1.0.6 =
* Fixed error with WP_List_Table introduced with WordPress 4.3
* Added Russian translation. Thank you Ivanka from [coupofy.com](http://coupofy.com)

= 1.0.5 =
* Fixed problem with temp directory used by Google API which was not writable on many shared hosting environments, and prevented the plugin from working properly. Replaced sys_get_temp_dir function with WordPress get_temp_dir function to resolve.
* Added Spanish and Serbian translations. Thank you Ogi Djuraskovic from [firstsiteguide.com](http://firstsiteguide.com) for providing these.

= 1.0.4 =
* Added auto-update capability

= 1.0.3 =
* Tweaked interactions with WPDB so that it will properly get the table prefix for WordPress multisite installations.

= 1.0.2 =
* Tweaked styles to look better in the new WordPress 3.8 admin theme.
* Fixed accidental use of some php shorttags (<? instead of <?php) that was causing activation errors for some. (Thank you bekar09 for first finding this error)
* Tweaked ajax.js for better performance (Thanks to Pippin for the suggestion)
* Tweaked use of get_pages() for better performance (Thanks to Pippin for the suggestion)
* Fixed a number of php notices

= 1.0.1 =
* Fixed a potential conflict with other plugins that also utilize the Google API PHP library. The API is now only included if the Google_Client class does not already exist.
* Added additional checking during plugin activation to fail fast if the server does not meet the minimum plugin requirements.

= 1.0.0 =
* Initial Release

== Upgrade Notice ==

= 2.0.1 =
* Removed phpseclib unit tests from Google PHP API library to avoid false-positive with WordFence

= 2.0 =
* Major rewrite for better compatibility and performance
* Updated to the latest Google Pagespeed Insights API verison and library
* Fixed issues with bulk installers not generating DB tables
* Consolidated scan methods to a single more reliable method inspired by WP cron
* Better identify, communicate, and resolve issues with environments that have difficulties with scanning pages or API errors
* Improved API error logging
* Added 'abort scan' functionality to cancel an in-progress scan
* Added 'Maximum Script Run Time' option to advanced configuration to allow scans to run in shorter intervals for web hosts which have script timeouts that cannot be overridden
* Update the codebase to adhere better to WordPress coding standards and best practices
