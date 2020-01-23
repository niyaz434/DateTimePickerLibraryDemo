# DateTimePickerLibraryDemo
Integration and working of date and time picker. 

## About Date Time Picker Library
If you are looking for an date and time picker or (date or time picker alone) you are in the right zone. This is the library which will give you the date as well as the time in specified format. All you have to do is to add the maven repository url and the implementation into your project. It will give the result in the required and mentioned format. Hope you guys enjoy the library. Please give `STARS` if you like this library. Thanks folks....

# Implementation
1. In your project.gradle file just add the maven url file as mentioned below

````
allprojects {
    repositories {
        google()
        jcenter()
        maven {
            url  "https://niyaz434.bintray.com/DateTimePickerLibrary"
        }
    }
}
````
2. Add this line into your build.gradle dependencies of your project

`
implementation 'com.datetimepicker.datetimepickerlibrary:datetimepickerlibrary:0.0.4'
`

And you can able to use the date time picker now.

# Intialization

Intialize your date time picker library from the following code and you can able to see the picker

```
{

DateTimeConfig.Builder dateTimeConfigBuilder = new DateTimeConfig.Builder()     //intializing the builder
            .setDialogTitle("Pick a date")      //apply your title of the date time picker
            .setTimePickerTitle("Choose time also please")      //#Optional if your using time picker here
            .setDateTimePickerFeild(AppConstants.TIME_PICKER_ONLY)  //set what you want date or time or both pickers here
            .setPositiveButton("All Set Go")      //positive button text field here
            .setSpinnerOrDefaultMode(AppConstants.SPINNER_MODE)     //Mode want in the spinner mode or default mode
            .setNegativeButton("No I don't need it")      //Negative button text
            .setDateOrTimeFormat("hh/mm/ss");     //Important Set the correct format you want as a result
    DateTimeConfig dateTimeConfig = dateTimeConfigBuilder.build();
    DateTimePicker dateTimePicker = new DateTimePicker(dateTimeConfig);
    dateTimePicker.show(this,this);   // Starting the date time picker library

}
```        

# Result Callback

Here, you can able to get the result accordingly. If user select some date you can get result in dateTime Success and if user clicked cancel you will recieve the error code. Below mentioned the types and cause of the error code.

```
{
    @Override
    public void dateTimeSuccess(DateTimeResult dateTimeResult) {
        if (dateTimeResult != null) {
            Log.d("dateTimeResult", "dateTimeResult: " + dateTimeResult.toString());
            String dateTime = dateTimeResult.getDatetimeRequestedFormat();
            Log.d("dateTimeSuccess", "dateTimeSuccess: " + dateTime);
        }
    }

    @Override
    public void dateTimeFailure(int errorCode) {
        Log.d("dateTimeFailure", "dateTimeFailure: " + String.valueOf(errorCodes));
    }

}

```
