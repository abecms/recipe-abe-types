# recipe-abe-types
This recipe demonstrates how to use basic types of Abe

# Installation

- git clone https://github.com/Abejs/recipe-abetypes.git
- cd recipe-abetypes
- abe serve -i
- Enjoy

# Description

In this recipe, you'll see how to use th basic types of Abe:
- text
- textarea
- rich
- link
- image
- file

# file
Create a content based on the template file.html

![Screenshot](/site/screenshot_file.png?raw=true)

You can chose what types of content you can upload in your abe blog. To authorize a content type, you'll have to edit you abe.json config and update the upload section.
```
"upload": {
  "document": "my_documents",
  "extensions":[".gif", ".jpg", ".jpeg", ".png", ".svg", ".mp4", ".pdf"],
  "mimetypes": ["image/gif", "image/jpeg", "image/png", "image/svg+xml", "video/mp4", "application/pdf"]
}
```
In this example, we've configured the directory "my_documents" which will host the uploaded documents (those which are not images nor movies nor sound).

And we've put the authorized extensions and authorized mimetypes.
This section of the configuration file is what you'll have to update if you want to add a new authorized file type.

The template itself is quite self-explanatory:

```
<!DOCTYPE html>
<html>
<head>
  <title>File type</title>
</head>
<body>
{{abe type='file' key='file_key' desc='Upload your file' reload='true' visible='false'}}

{{#if file_key}}
  This file has been uploaded : {{file_key}}
{{/if}}
</body>
</html>
```

We hide the type='file' (visible='false') and reload it (reload='true') once the contributor has uploaded her file. 
Line 48, if a file has been succesfully uploaded, we display the sentence "This file has been ..."

> A future release will add a new attribute "filetypes" that will give you more power: You'll be able to choose which extension you want to authorize tag by tag.
