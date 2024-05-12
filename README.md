# PDF Viewer App Source Code In-Android-Studio

# Presenting brand new Article:
 In this article you will learn how to create bottom sheet dialog App in Android Studio. Just follow the steps in the Article.
More article about Android Application Development will uploaded so get in touch with the channel. So you are no more far. You can be 
developer. 

## Step 1: Creating a new project

- Open a new project.
- We will be working on Empty Views Activity with language as Java. Leave all other options unchanged.
- You can change the name of the project at your convenience.
- There will be two default files named activity_main.xml and MainActivity.java.

## Step 2: Navigate to Build scripts > build.gradle(Module) file and add the following dependency to it and Syne Now
```js
implementation 'com.github.barteksc:android-pdf-viewer:3.2.0-beta.1'
```

## Step 3: Navigate to Build scripts > settings.gradle(Project Settings) file and add the following dependency to it and Syne Now
```js
 maven {url('https://jcenter.bintray.com')}
```

## Step 4: Open res -> layout ->activity_main.xml (or) main.xml and add following code:

In this step we open an XML file and add the code :-
```xml
   <com.github.barteksc.pdfviewer.PDFView
        android:id="@+id/pdfView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"/>
```
## Step 5: Open Java -> package – > MainActivity.Java and add following code:

In this step we open an Java file and add the code :-
```java
pdfView.fromAsset(String)
.load();
```
## You can use a combination of the following settings to get scroll and fling behaviour similar to a ViewPager:
```java
    .swipeHorizontal(true)
    .pageSnap(true)
    .autoSpacing(true)
    .pageFling(true)
```
## All available options with default values:
```java
pdfView.fromUri(Uri)
or
pdfView.fromFile(File)
or
pdfView.fromBytes(byte[])
or
pdfView.fromStream(InputStream) // stream is written to bytearray - native code cannot use Java Streams
or
pdfView.fromSource(DocumentSource)
or
pdfView.fromAsset(String)
    .pages(0, 2, 1, 3, 3, 3) // all pages are displayed by default
    .enableSwipe(true) // allows to block changing pages using swipe
    .swipeHorizontal(false)
    .enableDoubletap(true)
    .defaultPage(0)
    // allows to draw something on the current page, usually visible in the middle of the screen
    .onDraw(onDrawListener)
    // allows to draw something on all pages, separately for every page. Called only for visible pages
    .onDrawAll(onDrawListener)
    .onLoad(onLoadCompleteListener) // called after document is loaded and starts to be rendered
    .onPageChange(onPageChangeListener)
    .onPageScroll(onPageScrollListener)
    .onError(onErrorListener)
    .onPageError(onPageErrorListener)
    .onRender(onRenderListener) // called after document is rendered for the first time
    // called on single tap, return true if handled, false to toggle scroll handle visibility
    .onTap(onTapListener)
    .onLongPress(onLongPressListener)
    .enableAnnotationRendering(false) // render annotations (such as comments, colors or forms)
    .password(null)
    .scrollHandle(null)
    .enableAntialiasing(true) // improve rendering a little bit on low-res screens
    // spacing between pages in dp. To define spacing color, set view background
    .spacing(0)
    .autoSpacing(false) // add dynamic spacing to fit each page on its own on the screen
    .linkHandler(DefaultLinkHandler)
    .pageFitPolicy(FitPolicy.WIDTH) // mode to fit pages in the view
    .fitEachPage(false) // fit each page to the view, else smaller pages are scaled relative to largest page.
    .pageSnap(false) // snap pages to screen boundaries
    .pageFling(false) // make a fling change only a single page like ViewPager
    .nightMode(false) // toggle night mode
    .load();
```
