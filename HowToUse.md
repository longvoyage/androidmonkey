# Introduction #

Here's how to use the library:

# Details #

## Create an android test project ##

An Android Test project should be created first, using Android ADT [http://developer.android.com/sdk/eclipse-adt.html]

Refer the the AndroidMonkey library (jar or project)

## Create a test class ##

Create a normal ActivityInstrumentationTestCase2 test class, and add the following test case:

> public void testMonkeyEvents(){
> Display display = getActivity().getWindowManager().getDefaultDisplay();
> Instrumentation inst = getInstrumentation();
> PackageManager pm = getActivity().getPackageManager();

> Monkey monkey = new Monkey(display, packageToTest, inst, pm);

> for (int i = 0; i < NUM\_EVENTS; i++){
> > monkey.nextRandomEvent();

> }

> }


Download the entire test class in the Downloads tab.