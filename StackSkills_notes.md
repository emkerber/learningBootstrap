# Downloading Bootstrap

Download a .zip file from the Bootstrap website, which includes:
- CSS
- Sass
- JavaScript
- documentation/setup

Put the Bootstrap folder in your project. Course narrator puts it within "htdocs" folder? He uses the example of the XAMPP server, and says you should be sure to create a folder within the htdocs folder.

Narrator's file structure:

- XAMPP_Install1
  - anonymous
  - other folders...
  - htdocs
    - bootstrap4
      - img
    - bootstrap-4.0.0-alpha.2
      - bootstrap-4.0.0-alpha.2
    - cgi-bin
    - other folders...

Once dowloaded, extract files by right-clicking and selecting "Extract files...". A new folder is then created within the htdocs called bootstrap-4.0.0-alpha.2, in addition to the bootstrap4 folder.

# Creating folders

The author suggests the file structure look like this:

- XAMPP_Install1
  - anonymous
  - other folders...
  - htdocs
    - bootstrap4
      - css
      - img
      - js
    - bootstrap-4.0.0-alpha.2
      - bootstrap-4.0.0-alpha.2
    - cgi-bin
    - other folders...

Move downloaded Bootstrap folders (those inside bootstrap-4.0.0-alpha.2) into the created Bootstrap folder (bootstrap4).

- The css file and the js file, both inside bootstrap-4.0.0-alpha.2 > dist, are the only files you really need to move, but there are also Sass files and such

If you're not using a personal server, the files can really go anywhere on your system. The files must be in the same folder, but that folder is automatically found by the editor (after right-clicking on it and selecting "Open with Atom" LOL).
