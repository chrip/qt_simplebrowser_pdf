This is a combination of [Qt's simplebrowser example](https://doc.qt.io/qt-5/qtwebengine-webenginewidgets-simplebrowser-example.html) and Mozillas [PDF.js PDF viewer](https://github.com/mozilla/pdf.js).
The simplebrowser automatically downloads a PDF file and displays it via viewer.html which is part of PDF.js. The key idea is to convert the PDF file to a base64 string and initialize a slightly modified version of viewer.js.

```c++
QFile file(pdfPath);
if (file.open(QIODevice::ReadOnly)) {
    QByteArray base64 = file.readAll().toBase64();
    page()->runJavaScript("DEFAULT_URL = 'data:application/pdf;base64," +
                        base64 + "';webViewerLoad();");
    file.close();
}
```
