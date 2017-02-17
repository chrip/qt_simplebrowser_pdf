This is a combination of [Qt's simplebrowser example](https://doc.qt.io/qt-5/qtwebengine-webenginewidgets-simplebrowser-example.html) and Mozillas [PDF.js PDF viewer](https://github.com/mozilla/pdf.js).

The simplebrowser displays PDF files via viewer.html which is part of PDF.js. The key idea is to open the viewer.html as file:// and set QWebEngineSettings::LocalContentCanAccessRemoteUrls to true.

