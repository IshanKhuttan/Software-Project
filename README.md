# View Pager

## Introduction

The viewpager is the widget that helps us or allows the user to swipe right or left to see an entirely new screen. In other way, we can say that it is a great way to show the user multiple tabs. It has also the capability to strongly remove or add pages (tabs) anytime. We can think of an idea of grouping search results by certain classes, and showing each class in a separate list. With the use of viewpager, the user could swipe right or left to see the other categories lists or classes. For using the viewpager, it need some knowledge of both the Fragments and PageAdapters. In this case, the Fragments are the "pages". On each screen that the ViewPager let the user to scroll is a Fragment. With the use of Fragments instead of a view, there is much broad range of chances to show in each page. Then there is no limit to just list of items. There can be  any collections of views and widgets that we may need. We can believe of PageAdapters in the similar way of ListAdapters. The task of PageAdapters is to provide Fragments(instead of views) to the UI for drawing. So for working everything properly we need:
1. An Activity with a ViewPager on display as part of its main UI. 
2. A set of Fragments to be used as pages
3. A custom  FragmentPagerAdapter that returns the correct Fragment for each page number

 For implementing gestural navigation we need three components to work without fragments:
 
1.Viewpager => It is layout manager that displays the collection of views one at a time. It helps to detect the user swipe gesture nad navigate to left and right. 

2.Adapter => Adapter helps the Viewpager to pull the data from the adapter. It's jobs is to create the view that are displayed by the Viewpager. As the Viewpager dtects the gesture of user swipe, it will ask the adapter to give the right view to display.

3.Page Indicator => The Viewpager is sometimes used to display a large data(lots of image) . So to help the user to navigate the large data it is often accompained by the page indicator that display the string. The string could be the title of imageor a caption.



## History And Package

Viewpager was introduced by google in Android 4.0 and it was added to android.support.v4libraries and Fragment was introdduced in Android 3.0 (API level 11). Viewpager is mostly used with fragments. In the case of ViewPager we cannot avoid the using of the support library because ViewPager is not firstly supported even in the latest Android , Lollipop. Also as the support library does not work properly with Fragments, in order to solve that we have to use the support library Fragment services. And for making the support library to work we have to navigate the project structure to Gradle Scripts and open the file build.gradle(app). And at the end of the file we have to include a line to dependencies(compile "com.android.support:support-v4:21.0.+"). Furthermore we can change the 21.0 to any version we want to use. And the "+" at the last will make sure that we will use the most up to date subversion. The end of file will look something like this:
dependencies {
  complie fileTree(dir: 'libs', include: ['* .jar']}
  compile "com.android.support:support-v4:21.0.+"
  }
After synchronize the project in android studio, it will be ready to use classes that are in the support library and will automatically add the import statements.

## Classes and Methods
Viewpager requires classes and methods to work properly. For classes we have to create a fragment class  DcreenSlidePageFragment then it returns the layout by overriding on CreateView() method. And by creating inner classScreenSlidePageAdapter which extends FragmentStatePagerAdapterin the MainActivity. 

For Methods:

1. getItem(): It returns the instance of a fragment as new pager.

2. getCount(): It returns the number of pages.

The basic code used for Methods is:

@Override

   public Fragment getItem(int position) {
        
   retun new ScreenSlidePageFragment();
   
   }
   
   @Override
   
   public int getCount() {
   
   return NUM_PAGES;
   
   }

## References
1. https://developer.android.com/reference/android/support/v4/view/ViewPager 

2. https://docs.microsoft.com/en-us/xamarin/android/user-interface/controls/view-pager/

3. https://stackoverflow.com/questions/18413309/how-to-implement-a-viewpager-with-different-fragments-layouts

4. https://medium.com/@elifbon/fragments-on-viewpager-8ace8430a8e1

5. https://www.bignerdranch.com/blog/viewpager-without-fragments/
