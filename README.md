[![Build Status](https://travis-ci.org/Kaufland/andksnackbar.svg?branch=develop)](https://travis-ci.org/Kaufland/andksnackbar)
[![codecov](https://codecov.io/gh/Kaufland/andksnackbar/branch/develop/graph/badge.svg)](https://codecov.io/gh/Kaufland/andksnackbar)
[![KIS](https://img.shields.io/badge/KIS-awesome-red.svg)](http://www.spannende-it.de)

# andksnackbar
is an Android library for creating highly customisable Snackbars which persist among Activity changes. It provides possibility of managing multiple or single Snackbar(s) at a time.

## Demo


## Features 


## Implementation


1. Add it in your root build.gradle at the end of repositories:

	 ```
	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
	```

2. Add gradle dependency

    ```
    compile 'com.github.Kaufland:andksnackbar:0.0.1'
    ```
    
3. Configure SnackbarManager in your Application's onCreate method

    ``` java
    SnackbarManager.init(getApplicationContext(),SnackbarConfiguration.configure(new SnackbarConfiguration.Builder()
                   .gravity(SnackbarConfiguration.Gravity.GRAVITY_TOP)
                   .type(SnackbarConfiguration.SnackbarType.SINGLE_SNACKBAR)));     
    ```
    
4. Create Snackbars whenever you need them

    ``` java
    SnackbarManager.showSnackbar(new ActionSnackbarView.Builder()
                        .withBackgroundColor(R.color.colorGreen)
                        .withTitle("Example default title")
                        .withTitleColor(R.color.colorWhite)
                        .withBoldTitleStyle()
                        .withMessage("Example default message")
                        .withMessageColor(R.color.colorWhite)
                        .withBoldMessageStyle()
                        .withActionDrawable(R.mipmap.ic_launcher)
                        .withActionListener(new ActionListener() {
                            @Override
                            public boolean onAction() {
                                //dismiss snackbar view
                                return true;
                            }
                        })
                        .withMarginsAroundTitle(16,16,16,0)
                        .withMarginsAroundMessage(16,16,16,16)
                        .withMarginsAroundActionButton(10,10,10,10)
                        .build());    
	```

