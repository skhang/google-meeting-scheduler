# Introduction #

The following guide will walk you through the steps to configure your own instance of Meeting Scheduler.

This guide assumes general knowledge of Java and Android development, and is not recommended for beginners. For those just starting with Android, [install the SDK](http://developer.android.com/sdk/installing.html) and follow the getting started guides available in the [Android developers site](http://developer.android.com) such as the [Hello World tutorial](http://developer.android.com/resources/tutorials/hello-world.html).

# Setting up an Android Virtual Device #

The project is intended to run on Android 2.2 and later versions. If you don't already have one, please create an Android Virtual Device configured with the target platform `Google APIs (Google Inc.) - API Level 8`.

# Getting the code #

Start by downloading a copy of the Meeting Scheduler [source](http://code.google.com/p/google-meeting-scheduler/source/checkout) from this project's mercurial repository. This will create a directory on your local file system containing all of the files required by Meeting Scheduler.

Meeting Scheduler currently uses the [Google APIs Java client library 1.6.0-beta](http://code.google.com/p/google-api-java-client/downloads/detail?name=google-api-java-client-1.6.0-beta.zip&can=2&q=) which required jars are already in the repository.

# Importing the code into Eclipse #

In Eclipse, go to **File** **>** **Import...** **>** **General** **>** **Existing project into workspace** and point to the freshly checked out source directory.
If everything goes fine, the project should appear in your Eclipse workspace.

# Configuration #

## Creating a project in the Google APIs console ##

Meeting Scheduler uses Google Calendar API v3 which is enabled and configured via the [Google APIs Console](https://code.google.com/apis/console). Visit the console and create a new project.

Once the project is created, click on the **Services** link in the left navigation. On the list of APIs that displays, enable the Google Calendar API.

## Adding your API key ##

In the [APIs Console](https://code.google.com/apis/console) window, and click on **API Access** in the left navigation. Copy the project's API key and put it in [CalendarServiceBulder.java](https://code.google.com/p/google-meeting-scheduler/source/browse/src/com/google/samples/meetingscheduler/util/CalendarServiceBuilder.java#42) in place of:

```
  calendarRequest.setKey("<INPUT_YOUR_API_KEY>");
```

# Running the project #

Now that the project is fully configured, you can hit the **Run** button in Eclipse. On the first run, the project will need to be configured as an **Android Application**.
Check out this [tutorial](http://code.google.com/apis/calendar/articles/meeting_scheduler.html) for more details about the implementation.