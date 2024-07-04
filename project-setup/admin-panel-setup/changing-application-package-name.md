---
description: >-
  This guide details two methods for modifying 'Ecolab' application package
  name: manually editing project files or using the package_rename_plus Dart
  package.
---

# Changing Application Package Name

#### Option 1: Manual Editing (For Users Comfortable with Project Structure)

**1. Update `pubspec.yaml`:**

* Open the `pubspec.yaml` file located at the root of your project.
* Locate the `application_name` property and update its value with your desired app name. This doesn't directly change the package name, but it reflects in the displayed app name.

**2. Update Android Manifest:**

* Navigate to the `android/app/src/main/AndroidManifest.xml` file.
* Find the `<manifest>` tag and update the `package` attribute with your new package name (e.g., `com.eccono.ecolab`).

**3. Update MainActivity:**

* Go to the `android/app/src/main/kotlin/com.eccono.ecolab` folder (replace `com.eccono.ecolab` with your current package name).
* Rename this folder to match your new package name (e.g., `com.example.yourappname`).
* Inside this renamed folder, open the `MainActivity.java` file.
* Update any references to the old package name with your new package name.

**4. Update Gradle Files (Optional):**

* In rare cases, you might need to modify references in Gradle files (`build.gradle` or project-level Gradle files). Search for the old package name and replace it with the new one.

**5. Update iOS Bundle Identifier (For Users with Xcode):**

* Open your project in Xcode.
* Go to your project settings (usually under the target name in the project navigator).
* Under the "General" tab, locate the "Bundle Identifier" field and update it with your new package name (e.g., `com.example.yourappname`).

**Note:** Manually editing can be error-prone. Ensure you update all relevant references consistently.

#### Option 2: Using `package_rename_plus` (Recommended)

**1. Add the Package:**

* Open your terminal and navigate to your project's root directory.
* Run the following command to add the `package_rename_plus` package to your project:

Bash

```bash
$ dart pub add package_rename_plus
```

**2. Create a Configuration File (Optional):**

* While the package works with configurations in `pubspec.yaml`, you can create a dedicated configuration file (`package_rename_config.yaml`) at the project root for better organization.

**3. Configure the Package Name (Using `pubspec.yaml` or Configuration File):**

*   **In `pubspec.yaml`:**

    Add the following under the `dev_dependencies` section:

    ```yaml
    dev_dependencies:
      package_rename_plus: ^2.0.2  # Replace with the latest version
    ```



    Then, add a `package_rename_config` key with your desired package name configuration:

    ```yaml
    package_rename_config:
      android:
        package_name: com.example.yourappname
      ios:
        bundle_name: com.example.yourappname
    ```
*   **In `package_rename_config.yaml`:**

    Create the file at the project root and add the same configuration as above.

**4. Run the Package Rename Tool:**

* Execute the following command in your terminal:

```bash
$ dart run package_rename_plus
```

Use code with caution.content\_copy

* If you used a custom configuration file path, add the `--path` flag:

```bash
$ dart run package_rename_plus --path="path/to/package_rename_config.yaml"
```

**Benefits of `package_rename_plus`:**

* Automates package name changes across the project.
* Reduces the risk of errors.
* Supports platform-specific configurations (Android, iOS).

**Important Notes:**

* Changing the package name is a significant step. Ensure you understand the implications before proceeding, especially if your project is already deployed or integrated with other services.
* Back up your project before making any changes,
