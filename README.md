# 03FragmentExample
## Android Fragment
* like a sub-Activity which allows modular design
* has:
		* layout (.xml)
		* behavior (.java)
		* life cycle
* can be added or removed while Activity is running
* An Activity can contain multiple Fragments
		note: only 1 Activity per screen, Fragments address this limitation
* to create:
	*	extend Fragment class (.java)
	*	insert into the Activity's layout (.xml) using the <fragement> tag

*Built on API 22 (Lollipop)*

[Generate FirstFrament .java and .xml files and insert into MainActivity](https://github.com/dltra/03FragmentExample/commit/a4a54850bb50e413e51bf8216696474657cbec7e)
### FirstFragment.java 
* R-click on java/packageFolder => **New** => **Java Class** => **FirstFragment**, Superclass: **Fragment**
* **alt + insert** to insert default constructor
	* Empty default constructor is required
* auto populate: **onCreateView()** override
	* ``return inflater.inflate(R.layout.fragment_first, container,false);``
* click on **fragment_first** and **alt + Enter** and select **Create layout resource file (fragment_first.xml)**
	* Note:  if **alt + Enter** doesn't offer this option, you may have to retype last letter of **fragment_first**
	* change the **Root element:** to **ConstraintLayout**

### fragment_first.xml
* add a button element to fragment's layout
### activity_main.xml
* replace the **TextView** element with your custom **fragment** element
### build.gradle
* verify the versions of the dependencies

*Test App*

[Add Toolbar and FloatingActionButton](https://github.com/dltra/03FragmentExample/commit/5d3da41ddace3af909157c93454b1f077b5d4cc0)
## Basic Fragment  
### AndroidManifest.xml
* set application label (App name)
* set activity label (Activity name)
* set activity theme to **AppTheme.NoActionBar** (to be made next)
* make app searchable
### styles.xml
* create three new app themes: 
	* **AppTheme.NoActionBar** 
	* **AppTheme.AppBarOverlay**
	* **AppTheme.PopupOverlay**
### strings.xml
* add main_activity_label
### dimens.xml
* in **values** folder, create a new file called **dimens.xml** to store our dimensions values
* add a <**dimen**> tag: ``<dimen  name="floating_action_button_margin">16dp</dimen>``
### build.gradle
* add dependency:  ``implementation 'com.google.android.material:material:1.0.0'``
### activity_main.xml
* add **AppBarLayout** and **FloatingActionButton**

*Test App*

[Make content layout to include fragment](https://github.com/dltra/03FragmentExample/commit/1cfcda97fcb61081e678d23ec727307ccdb500ac)
### content_main.xml 
* create layout with **FirstFragment**
### activity_main.xml
* include the **content_main.xml** layout

*Test App* 

[Assign toolbar to activity, pop up Snackbar message](https://github.com/dltra/03FragmentExample/commit/2ecf910833941ff2a65cec0814fe4e2d991621ca)
### MainActivity.java 
* assign toolbar to MainActivity
* set onClick listener to floating action button
  * display a Snackbar (like Toast)
  
*Test App*

[Add toolbar menu options](https://github.com/dltra/03FragmentExample/commit/c65b4b2c698320904a7866893128ebcc6f1467b9)
### menu_main.xml 
* R-click on res => **New** => **Android Resource Directory** => type "m" for menu
* make a new menu layout in the *menu* subdirectory
    * add an item

### strings.xml
* define action_settings string

### MainActiviity.java
* add an onCreate listener for menu options: ``onCreateOptionsMenu(Menu menu)``
    * inflate the menu_main.xml layout
* add responder for menu options selected: ``onOptionsItemSelected(MenuItem item)``

*Test App*

[Add DrawerLayout and NavigationView](https://github.com/dltra/03FragmentExample/commit/a027b71485111e7737e1e25c1213b3df2d68ec6f)
## Menu App 
### app_bar_main.xml
* move toolbar and floating action button from **activity_main.xml** to new layout **app_bar_main.xml**
### res/drawable/
* **side_nav_bar.xml**
    * R-click on **res/drawable** => **New** => **Drawable Resource File** => name **side_nav_bar**
    * add a rectangular gradient
*  add the other drawable .xml files (camera, gallery, manage, send, share, slideshow)
### dimens.xml
* set the dimensions for nav header
### strings.xml
* set the navigation drawer strings
### nav_header_main.xml
* create a vertical LinearLayout with an ImageView and 2 TextViews
    * utilize **dimens.xml**, **strings.xml**, and **nav_header_main.xml**
### res/menu/activity_main_drawer.xml
* make a new layout in the **res/menu** folder: **activity_main_drawer.xml**
* add the navigation drawables
### activity_main.xml
* convert to a DrawerLayout
    * include the **app_bar_main.xml** layout
    * add a NavigationView using the **nav_header_main.xml** layout
### build.gradle
* add dependency: ``implementation "androidx.drawerlayout:drawerlayout:1.0.0``

*Test App* (You shouldn't see any changes, but verify that the app runs.)

[Add ActionBarDrawerToggle and Implement Navigation Selection Listener](https://github.com/dltra/03FragmentExample/commit/8ba6cf048158cf0cc04699f874db4276a881a51b)
### MainActivity.java
* implement ``NavigationView.OnNavigationItemSelectedListener``
* add **ActionBarDrawerToggle**

*Test App*

[Implement onBackPressed to close drawer if open](https://github.com/dltra/03FragmentExample/commit/e06a08326e947da05f4410475900144306a934f2)
### MainActivity.java
* implement **onBackPressed()** event responder to close drawer if it is open