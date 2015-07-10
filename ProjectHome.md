AndroidMonkey is an Android Library. It is, in fact, a copy of the original Android Monkey Tool http://developer.android.com/guide/developing/tools/monkey.html and made as a library for testing and analysis (e.g. code coverage) purposes.

Tester/User can easily use the library to create random test cases to test android apps with GUI.


---

## Why this library: ##

**You can use this library to create random test cases for your application, with just few lines of code**

**You can add your assertions to access the state of the SUT (you can hardly do this with the Android Monkey Tool)**

**You can do Coverage analysis of random testing on Android Application, this is useful for Research Purpose (like what I'm doing)**


---

## Code example ##
```
public class ContactAdderTest extends
		ActivityInstrumentationTestCase2<ContactAdder> {

	private int NUM_EVENTS = 1000;

	public ContactAdderTest() {
		super("com.example.android.contactmanager", ContactAdder.class);
	}

	@Override
	protected void setUp() throws Exception {
		super.setUp();
		setActivityInitialTouchMode(false);

	}

	public void testMonkeyEvents() {
		Display display = getActivity().getWindowManager().getDefaultDisplay();
		Instrumentation inst = getInstrumentation();
		PackageManager pm = getActivity().getPackageManager();

		Monkey monkey = new Monkey(display,
				"com.example.android.contactmanager", inst, pm);

                // Generate and fire a random event. 
		for (int i = 0; i < NUM_EVENTS; i++) {
			monkey.nextRandomEvent();
		}

	}
}
```