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