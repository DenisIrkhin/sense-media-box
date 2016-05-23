# Media Box for Qlik Sense

> Include web pages, videos, images and much more into your Qlik Sense app.

***

<!-- toc -->

* [Purpose and Description](#purpose-and-description)
* [Screenshots](#screenshots)
* [Installation](#installation)
* [Configuration](#configuration)
* [Change Log](#change-log)
* [Contributing](#contributing)
* [Roadmap & Todos](#roadmap---todos)
* [Known Issues](#known-issues)
* [Author](#author)
* [License](#license)

_(Table of contents generated by [verb])_

<!-- tocstop -->

***

## Purpose and Description

The idea of this solution is to bundle the usage of several media-types into one Visualization Extension to be used within Qlik Sense.

As of now the following media types are currently supported:

* HTML (+CSS)
* Image from Url
* Image from Library
* Video
* Web sites

## Screenshots

### HTML

[![](https://raw.githubusercontent.com/stefanwalther/qsMediaBox/master/docs/images/qsMediaBox_Html.png)](#purpose-and-description)

### Image

[![](https://raw.githubusercontent.com/stefanwalther/qsMediaBox/master/docs/images/qsMediaBox_Image.png)](#screenshots)

### Video

[![](https://raw.githubusercontent.com/stefanwalther/qsMediaBox/master/docs/images/qsMediaBox_Video_MP4.png)](#installation)

### Website

[![](https://raw.githubusercontent.com/stefanwalther/qsMediaBox/master/docs/images/qsMediaBox_WebSite.png)](#configuration)

## Installation

1. Download the [latest version](https://github.com/stefanwalther/qsMediaBox/raw/master/build/sense-media-box_latest.zip)
2. Qlik Sense Desktop
  - To install, copy all files in the .zip file to folder "C:\Users%USERNAME%\Documents\Qlik\Sense\Extensions\sense-media-box"
* Qlik Sense Server
  - See instructions [how to import an extension on Qlik Sense Server](http://help.qlik.com/sense/en-US/online/#../Subsystems/Qlik_Management_Console_help/Content/QMC_Resources_Extensions_AddingExtensions.htm?Highlight=extension)

## Configuration

After installing the Visualization Extension and dropping it onto a sheet in Qlik Sense follow these steps:

### Define the media type

Depending on the selected media type you'll then see different options in the property panel:

#### Media type _Html_

* **HTML** - Define either inline HTML or reference to a field

Example:

`=only(HTML)`<br/>or<br/>`='<div style="font-weight:bold;">inline HTML</div>'`

_Example:_

```bash
Html:
LOAD * INLINE [
    HTML, HtmlAsset
    'This is some <b>bold</b> test', 'Some Html'
    'This is another test<br/><br/>with breaks<br/>and<br/>another break', 'Some Html with breaks'
    '<div style="font-weight:bold;color:red;">Inline style</div>', 'Some Html with inline style'
];
```

then use

```bash
=only(HTML)
```

#### Media type _Image_

* **Image Source (Url)** - Define the Url for the image to be embedded.
* **Vertical Alignment** - Vertical alignment of the image, defaults to "top".
* **Horizontal Alignment** - Horizontal alignment of the image, defaults to "left".
* **Image aspect ratio** - Either "keep size" or "best fit", which uses the maximum available width.

#### Media type _Video_

* **Video type** - Define the type of the video to be embedded, possible values: `MP4`
* **Video poster image** - Define the preview image for the video, possible values: any valid URL to a .png/.jpeg file
* **Video Url** - Url to the video

#### Media type _Website_
* **Web site (Url)** - Url of the website to be embedded, any valid website Url
* **Scrollbars** - Behavior of scrollbars, `Auto`, `Always On`
* **Interaction** - Define whether interaction with the website should be possible or not, defaults to `Off`

### Testing the visualization extension

Here are some samples how to test if the MediaBox works for you:

**Image:**

http://video-js.zencoder.com/oceans-clip.png

**Video:**

Video poster image: http://video-js.zencoder.com/oceans-clip.png

Video source: http://video-js.zencoder.com/oceans-clip.mp4

## Change Log

### 0.4.0

* Images can now also be selected from the media-library.

### 0.3.0
* Added horizontal & vertical alignment of images + aspect ratio

## Contributing

Pull requests and stars are always welcome. For bugs and feature requests, [please create an issue](https://github.com/stefanwalther/sense-media-box/issues).
The process for contributing is outlined below:

1. Create a fork of the project
2. Work on whatever bug or feature you wish
3. Create a pull request (PR)

I cannot guarantee that I will merge all PRs but I will evaluate them all.

## Roadmap & Todos

The following features are planned to be implemented:

**Media type _HTML_**

* [ ] Allow definition of an external style-sheet

**Media type _Website_**

* [ ] Allow the user to select the [security settings for the embedded website](http://www.w3schools.com/tags/att_iframe_sandbox.asp) (now hardcoded)
* [ ] Display an error if a website doesn't allow to be embedded, e.g. http://www.google.com

**Media type _Image_**

* [x] Settings to control the images' aspect ratio
* [x] Vertical alignment

**Media type _Video_**

* [ ] Support for a video type _YouTube_

* [ ] Support for a video type _Vimeo_

* [ ] Support for a video from the media library
* [X] Support for a preview image

Any further ideas, please let me know!

## Known Issues

* Video doesn't work in Qlik Sense Desktop but in local browser or Qlik Sense server.

## Author

**Stefan Walther**

+ [qliksite.io](http://qliksite.io)
* [twitter/waltherstefan](http://twitter.com/waltherstefan)
* [github.com/stefanwalther](http://github.com/stefanwalther)

## License

Copyright © 2016 Stefan Walther

Released under the MIT license.

***

_This file was generated by [verb-cli](https://github.com/assemble/verb-cli) on May 23, 2016._