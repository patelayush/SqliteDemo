# SqliteDemo
In this assignment you will develop “iTunes Top Paid Apps” app, which displays the list
of top paid apps from “iTunes Top Paid Apps” rss feed. In addition to displaying the top
paid apps, the app allows the user to filter specific apps and store them in a SQLite
database.
(a) Loading Dialog. (b) Sorting, default is Ascending. (c) ListView sorted descending
(d) Long Click on item (e) Added to Filtered Apps list. (f) Click on Trash icon.
iTunes Top Paid Apps
Loading...
iTunes Top Paid Apps
Filtered Apps:
Descending
Image
Minecraft: Pocket
Edition
Price: USD 6.99
Facetune Image Price: USD 3.99
HotSchedules Image Price: USD 2.99
Monument Valley Image Price: USD 1.99
Earn to Die - Not Doppler Image Price: USD 0.99
Image
Plague Inc.
Price: USD 0.99
iTunes Top Paid Apps
Minecraft: Pocket Edition Image Price: USD 6.99
Facetune Image Price: USD 3.99
HotSchedules Image Price: USD 2.99
Monument Valley Image Price: USD 1.99
Filtered Apps:
There is no filtered apps to display.
Descending
iTunes Top Paid Apps
Filtered Apps:
Descending
Image
Minecraft: Pocket
Edition
Price: USD 6.99
Facetune Image Price: USD 3.99
HotSchedules Image Price: USD 2.99
Monument Valley Image Price: USD 1.99
Plague Inc. Image Price: USD 0.99
iTunes Top Paid Apps
Heads Up! Image Price: USD 0.99
Earn to Die - Not Doppler Image Price: USD 0.99
Plague Inc. Image Price: USD 0.99
Monument Valley Image Price: USD 1.99
Filtered Apps:
There is no filtered app to display.
Ascending
iTunes Top Paid Apps
Minecraft: Pocket Edition Image Price: USD 6.99
Facetune Image Price: USD 3.99
HotSchedules Image Price: USD 2.99
Monument Valley Image Price: USD 1.99
Filtered Apps:
There is no filtered apps to display.
Descending
Page 2 of 5
Main Activity (100 points):
This assignment has only one activity, MainActivity (Figure 1). This activity contains a
top ListView of apps and a bottom RecyclerView of filtered apps. The API to be used for
this assignment is: https://itunes.apple.com/us/rss/toppaidapplications/limit=25/json.
The top ListView is a list of apps retrieved from the API and should not include any of
the apps that have been filtered by the user. The bottom RecyclerViewer displays the
apps that have been filtered by the user. The requirements are as follows:
Part 1:
8. When the app starts, it should call the API to retrieve the list of apps, parse the
retrieved items and display the top ListView and bottom RecyclerView. While the API
is being accessed display a progress dialog as shown in Figure 1(a). Use a thread
pool or AsyncTask to access the API and parse the result using JSON parser.
9. On top of the activity there is a refresh button, and a sorting Switch. By default the
Switch should be set to ascending state, which is sorting the list in ascending order
by the app price. Note that the Switch label indicates “ascending” to reflect the state
of the Switch. The other state of the sorting switch is descending, which should sort
the list in descending order. The label of the Switch should be changed to reflect the
sorting state.
10. When the sorting Switch is toggled the list should be refreshed to reflect the updated
sorting state.
11. The retrieved items should be displayed in top ListView/RecyclerView as shown in
Figure 1(b). The top list should be created using a customized ListView, or
RecyclerView. Each item should contain the app thumbnail, app name, app price
and the dollar image according to the app price. The app price images should be
displayed according to the following:
i) One dollar icon, for apps with prices from $0 to $1.99.
(g) Item deleted from filtered list. (h) Click on Refresh button. (i) Refreshed and Filtered list.
Figure 1, App Wireframe
iTunes Top Paid Apps
Filtered Apps:
Descending
Image
Minecraft: Pocket
Edition
Price: USD 6.99
Facetune Image Price: USD 3.99
HotSchedules Image Price: USD 2.99
Monument Valley Image Price: USD 1.99
Plague Inc. Image Price: USD 0.99
iTunes Top Paid Apps
Filtered Apps:
Descending
Image
Minecraft: Pocket
Edition
Price: USD 6.99
Facetune Image Price: USD 3.99
HotSchedules Image Price: USD 2.99
Monument Valley Image Price: USD 1.99
Plague Inc. Image Price: USD 0.99
iTunes Top Paid Apps
Filtered Apps:
Descending
Image
Minecraft: Pocket
Edition
Price: USD 6.99
Facetune Image Price: USD 3.99
HotSchedules Image Price: USD 2.99
Monument Valley Image Price: USD 1.99
Plague Inc. Image Price: USD 0.99
Page 3 of 5
ii) Two dollar icon, for apps with prices from $2.00 to $5.99.
iii) Three dollar icon, for apps with prices greater than or equal to $6.00.
12. In the top list, the apps should be displayed in sorted order based on the sorting
order set by the sorting Switch at the top of the activity.
13. This app has a feature which allows the user to filter apps and store them in a
SQLite database locally. The filtered apps should not be displayed in the top
ListView. Create the SQLite database with table called Filter having columns: name,
price, thumb_url. This table will be used to save the filtered apps.
14. When displaying the top ListView, the apps included in the Filter table should not
be displayed in the top ListView.
Part 2:
1. The bottom ListView/RecyclerView should display the apps present in the Filter
table, which are the apps that have been filtered by the user. When the Filter table is
empty, display a message, “There is no filtered apps to display.”
2. A long click on any item in the top ListView (Figure 1(d)), should:
i) Add the selected item to the SQLite Filter table.
ii) Remove the selected item from the top ListView, because it is now filtered.
The top ListView should be refreshed to display only the items that are not
filtered.
iii) The bottom ListView/RecyclerView should be refreshed to display the
updated list of items in the Filter table. See Figure 1(e).
3. The bottom list should be displayed as a horizontal List/RecyclerView as shown in
Figure 1(e). The bottom RecyclerView should show all the apps present in the Filter
table.
4. Each item in the bottom List/RecyclerView should include the app thumbnail, name,
price and the dollar sign icon. A trash icon should be displayed on the bottom right
corner of each item as shown in Figure 1(e).
5. Clicking on the trash icon should perform the following operations:
i) Delete the selected item from Filter table.
ii) Refresh the upper list to display all the apps that retrieved from the API that
are not present in the Filter table.
iii) Refresh the bottom list to display the apps in the Filter table.
6. The apps should be sorted based on the sorting order indicated by the Switch.
7. Clicking on the Refresh icon should perform the following tasks:
i) Call the API to retrieve an updated list of apps.
ii) Refresh the upper ListView to display all the apps that retrieved from the API
that are not present in the Filter table.
iii) Refresh the bottom RecyclerView to display the apps in the Filter table.
8. Use can use the Picasso library to load images. 
