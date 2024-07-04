---
description: >-
  This detailed guide equips you with the steps to build and publish your Ecolab
  Flutter app on the Apple App Store. Ensure your app development is complete
  before following these steps.
---

# Building and Publishing for iOS

By following these steps, you'll prepare for distribution on the App Store.

**Important Notes:**

* Replace `"com.example.yourappname"` with your preferred package name throughout the guide.
* Possess a valid Apple developer account with a configured Xcode project and a valid distribution certificate ([https://developer.apple.com/programs/](https://developer.apple.com/programs/)).
* Basic familiarity with Xcode and macOS is assumed.

## 1. Update Your Package Name (if necessary)

Before diving into the build process, it's crucial to update your app's package name if it differs from `"com.example.yourappname"`. Refer to the section "[Changing Your Application Package Name in a Flutter Project](../project-setup/flutter-setup/changing-application-package-name.md)" for detailed instructions on manual editing or using the `package_rename_plus` package.

## 2. Register Your App-on-App Store Connect

**Manage Your App's Life Cycle:** App Store Connect (formerly iTunes Connect) allows you to manage your app's name, description, screenshots, pricing, releases to the App Store and TestFlight, and more. Registering your app involves two steps: creating a unique Bundle ID and registering an application record on App Store Connect ([https://docs.flutter.dev/deployment/ios](https://docs.flutter.dev/deployment/ios)).

**Register a Bundle ID:**

1. Open the [App IDs](https://developer.apple.com/account/ios/identifier/bundle) page of your developer account.
2. Click "+" to create a new Bundle ID.
3. Enter an app name, select Explicit App ID, and enter your desired ID.
4. Select the services your app uses, then click Continue.
5. Confirm details and click Register to complete registration.

**Create an Application Record:**

1. Open [App Store Connect](https://appstoreconnect.apple.com/) in your browser.
2. Click My Apps on the landing page.
3. Click "+" in the top-left corner, then select New App.
4. Fill out the app details form. Ensure iOS is checked under Platforms (Flutter doesn't currently support tvOS). Click Create.
5. Navigate to your app's application details and select App Information from the sidebar.
6. In the General Information section, select the Bundle ID you registered earlier.

### 3. Generate Xcode Project

1. **Navigate to Project Root:** Open a terminal window and navigate to your project's root directory.
2.  **Generate Xcode Project:** Run the following command, replacing `"com.example.yourappname"` with your package name:

    ```bash
    flutter build ios-framework --release --no-cocoa-pods --package-name="com.example.yourappname"
    ```



    This creates an Xcode project named `Runner.xcodeproj` in the `build/ios-framework` folder.

### 4. Configure Xcode Project

1. **Open Xcode Project:** Double-click the `Runner.xcodeproj` file to launch Xcode.
2. **Team Selection:** In Xcode, ensure you've selected the appropriate development team from the project settings (top-left corner).
3. **Signing & Capabilities:** Under project settings, navigate to "Signing & Capabilities" and configure your signing certificates and provisioning profiles. Refer to Apple's documentation for detailed instructions: [https://developer.apple.com/programs/](https://developer.apple.com/programs/)
4. **Bundle Identifier:** Verify that the Bundle Identifier under "General" settings matches your package name (`com.example.yourappname`).

### 5. Build and Archive for App Store Connect

1. **Connect iPhone/iPad:** Connect a physical device or a simulator matching your target deployment device.
2. **Product Menu:** In Xcode, select "Product" from the menu bar.
3. **Archive:** Choose "Archive" from the "Product" menu. This process might take some time.
4. **Organizer Window:** Once archived, locate the "Organizer" window (usually on the right side of Xcode).
5. **Archives Tab:** Select the "Archives" tab in the Organizer window.
6. **Share Button:** Click the "Share" button next to your archived Ecolab app.
7. **Export Option:** Choose "Save for App Store Connect" from the export options.
8. **Export Location:** Select a suitable location to save the exported archive file (`.ipa` format).

### 6. Submit App to App Store Connect

1. **App Store Connect:** Access App Store Connect using your Apple developer account credentials: [https://developer.apple.com/app-store-connect/](https://developer.apple.com/app-store-connect/)
2. **New App:** Click "My Apps" and then the "+" button to create a new app.
3. **App Information:** Provide essential details like app name, identifier (package name), primary category, etc.
4. **App Version:** Select "New Version" and upload the exported archive file (`.ipa`) you created in step 4.8.
5. **Build Details, Screenshots, & Preview:** Fill in build details, upload screenshots and a preview video (optional), and configure pricing and distribution settings.
6. **Review and Submit:** Carefully review all app information before submitting for App Store review.

**Congratulations!** You've successfully built and submitted your Ecolab Flutter app for review on the Apple App Store. The review process might take some time.

**Additional Notes:**

* Consider using high-quality screenshots and app previews that effectively showcase your Ecolab app's features and functionality.
* Thoroughly test your app on various iOS devices and simulators to ensure a smooth user experience.
* Refer to Apple's documentation for detailed information on app development, signing, and App Store Connect: [https://developer.apple.com/documentation/](https://developer.apple.com/documentation/)
* **Detailed Guide:** For a comprehensive overview of App Store Connect, refer to the App Store Connect guide: [https://developer.apple.com/app-store-connect/](https://developer.apple.com/app-store-connect/)
