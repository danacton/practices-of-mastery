This article shows how to use the Google Java style guide with [Eclipse IDE](http://www.eclipse.org). The benefit of doing this is that it will be easier for you to adhere to your organisation's style guide by automatically highlighting deviations from it as you write code.

# Step 1: Download the Google Java Style guide definition for Eclipse
The definition is [here](https://github.com/google/styleguide/blob/gh-pages/eclipse-java-google-style.xml).

# Step 2: Add the Google Style formatter to Eclipse
1. Opening Eclipse settings varies per OS. For example, on macOS open Eclipse -> Preferences.
2. In the search bar on the left, type "formatter", and select the Java -> Code Style -> Formatter menu item.
3. Click "Import" and browse to the XML file you downloaded in Step 1.
4. Ensure the "GoogleStyle" item is selected in the "Active profile" section.
5. Click "OK".

# Step 3: Configure save actions to automatically format your code when saving
This is a game-changer!

1. In the Preferences menu (same as in Step 2), type "save actions", and select Java -> Editor -> Save Actions.
2. Select "Perform the selected actions on save".
3. Select "Format source code".
4. Click the "Formatter" link and ensure the "GoogleStyle" formatter is selected as active.
5. Click OK.

Now, whenever you make changes to your code, you can use the format source code menu item, or just save the file and formatting will be applied automatically.

