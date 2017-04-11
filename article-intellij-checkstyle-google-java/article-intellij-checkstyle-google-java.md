This article shows how to use the Google Java style guide with [IntelliJ IDE](https://www.jetbrains.com/idea/). The benefit of doing this is that it will be easier for you to adhere to your organisation's style guide by automatically highlighting deviations from it as you write code.

# Step 1: Download the Checkstyle plugin
[Download](https://plugins.jetbrains.com/plugin/1065) the latest Checkstyle plugin for IntelliJ.

# Step 2: Import the plugin into your settings
1. Opening IntelliJ settings varies per OS. For example, on macOS open *Preferences* -> *Plugins *.

2. Select "Install plugin from disk" and browse to the file you downloaded in step 1 above and click OK.

3. You should now see Checkstyle listed in the installed plugins list.

4. You will need to restart IntelliJ for the plugin installation to complete.

# Step 3: Download the Google Java style guide file
Get the style file from [Github](https://github.com/checkstyle/checkstyle/blob/master/src/main/resources/google_checks.xml).

# Step 4: Configure the Checkstyle plugin to use the style guide file
1. In the settings window (as in Step 2), search for "checkstyle " in the left-hand nav search bar and select *Checkstyle*.
2. Click the "+" button on the right-hand side of the settings window.
3. Enter a description for the checks, here we used "Google Java style checks".
4. Select "Use a local Checkstyle file".
5. Browse for the style file you downloaded in step 5.
6. Once the style file has been added, select the check box to the left to make the "Google Java Style" guide the default style checker.
7. Click OK and you're done.

Now you should see warnings in your code (as shown below) based on the style rules.
