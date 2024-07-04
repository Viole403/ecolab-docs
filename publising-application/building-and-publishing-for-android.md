---
description: >-
  This detailed guide walks you through the process of building and publishing
  your Flutter app ("Ecolab") for the Android platform.
---

# Building and Publishing for Android

By following these steps, you'll prepare your app for distribution on the Google Play Store.

**Important Notes:**

* Ensure you've completed the development process for your Ecolab app.
* Have a valid Google Play developer account set up [Here](https://support.google.com/googleplay/android-developer/answer/6112435).
* Replace `"com.example.yourappname"` with your preferred package name throughout the guide.

### 1. Update Your Package Name (if necessary)

Before diving into the build and publishing process, it's crucial to update your app's package name if it differs from `"com.example.yourappname"`. Refer to the guide "[Changing Your Application Package Name in a Flutter Project](../project-setup/flutter-setup/changing-application-package-name.md)" for detailed instructions on manual editing or using the `package_rename_plus` package.

### 2. Generate Signed APKs

Signed APKs (Android Package Kits) are required for app distribution on Google Play. Here's how to generate them:

1.  **Create a Keystore:**

    * Open a terminal window.
    * Run the following command, replacing `keystore.jks` with your desired keystore name and providing a password:

    ```bash
    keytool -genkey -v -keystore keystore.jks -storepass your_store_password -keypass your_key_password -alias your_alias
    ```



    **Note:** Securely store your keystore file and passwords.
2.  **Build a Signed APK:**

    * Navigate to your project's root directory in the terminal.
    * Run the following command, replacing `keystore.jks` and passwords with the values you used in step 1a:

    ```bash
    flutter build apk --release --keystore keystore.jks --storepass=your_store_password --keypass=your_key_password --output-file=app-release.apk
    ```



    This command creates a signed APK named `app-release.apk` in your project's `build/app/outputs/apk/release` folder.

### 3. Create App Bundle (Optional, Recommended for Play Store)\*\*

An app bundle offers smaller app sizes and dynamic delivery features. Here's how to generate one:

1.  **Build an App Bundle:**

    * In your terminal, navigate to the project's root directory.
    * Run the following command:

    ```bash
    flutter build appbundle --release
    ```



    This creates an app bundle named `app-release.aab` in the same directory as the signed APK.

### 4. Configure Your Play Store Listing

1. **Log in to Google Play Console:**
   * Access the Google Play Console using your developer account credentials: \[invalid URL removed]
2. **Create a New App:**
   * Click "Create App" and follow the on-screen instructions to provide details about your Ecolab app.
3. **Upload App Assets:**
   * Go to the "Releases" section of your app's dashboard in the Play Console.
   * Click "Create new release" and upload either the signed APK (`app-release.apk`) or the app bundle (`app-release.aab`).
4. **Fill in App Details:**
   * Provide essential information like app title, description, screenshots, category, and content rating.
   * Ensure your app description adheres to Google Play's guidelines.
5. **Set Pricing and Distribution (Optional):**
   * If you plan to charge for your Ecolab app, determine the pricing strategy here.
   * Choose the target countries or regions for distribution.
6. **Review and Publish:**
   * Carefully review all app information before publishing.
   * Once satisfied, click "Publish" to make your Ecolab app available on the Google Play Store.

**Congratulations!** You've successfully built and published your Ecolab Flutter app for Android. It might take some time for your app to appear live on the Play Store after processing.

**Additional Notes:**

* Consider using screenshots and app previews that effectively showcase your Ecolab app's features and functionality.
* Regularly monitor your app's performance and reviews on the Play Console to identify areas for improvement.
* For in-depth details on app signing and Play Store
