---
description: >-
  The local.properties file acts as a secure storage location for sensitive
  configuration details in Flutter projects.
---

# Updating local.properties

This guide details the steps involved in updating this file for your "Ecolab" Flutter project.

**Important Note:**

* The `local.properties` file should **never** be committed to a version control system (e.g., Git) due to its sensitive content.

**Updating `local.properties`:**

1. **Locate the File:** Within your "Ecolab" Flutter project directory, navigate to the `android` folder. You'll find the `local.properties` file there.

**2. Open the File:** Use a text editor that supports plain text files (e.g., Notepad++, Sublime Text, Visual Studio Code). Double-clicking the file might open it in a program not suitable for editing.

**3. Update Properties:** The file might contain existing properties like `sdk.dir` (pointing to the Flutter SDK location) or comments. Focus on the following properties for updating:

* **`flutter.versionName`:** This property sets the application's version name (visible to users). Update this value whenever you release a new version of your Ecolab app.
* **`flutter.versionCode`:** This property defines the application's version code (used internally for updates). It's generally an integer incremented with each release.

**4. Example Update:**

Suppose you're releasing version 1.2.0 of your Ecolab app. Here's an example update to the `local.properties` file:

```
# ... other properties (if any)

flutter.versionName=1.2.0
flutter.versionCode=12
```

**5. Save Changes:** Once you've made the necessary updates, save the `local.properties` file.

**\[Optional: Add an image highlighting the `local.properties` file location within the project directory]**

**Additional Considerations:**

* Remember to replace the example values (`1.2.0` and `12`) with your specific version details for the Ecolab app release.
* For detailed information on versioning strategies in Flutter, refer to the official documentation: [https://docs.flutter.dev/release/archive](https://docs.flutter.dev/release/archive)

By following these steps and adhering to security best practices, you can effectively update the `local.properties` file for your Ecolab Flutter project.
