# Compile Wt, C++ Web Toolkit, on Ubuntu 16.04 x64

The example shows how to compile the current github version of [Wt - C++ Web Toolkit](http://www.webtoolkit.eu/wt) on Ubuntu 16.04 x64.

## Dependencies
Before proceeding with the compilation, the following packages are required:

```bash
# update Ubuntu's repositories
sudo apt update

#install git to download latest Wt source code from github
sudo apt install git

# install dependencies to be able to compile Monero
sudo apt install build-essential cmake libboost-all-dev doxygen libgraphicsmagick++1-dev libssl-dev libpq-dev libssl-dev libfcgi-dev

# or git and all dependencies in one command
# sudo apt install git build-essential cmake libboost-all-dev doxygen libgraphicsmagick++1-dev libssl-dev libpq-dev libssl-dev libfcgi-dev
```

## Compilation

You can compile either latest version (3.3.5) of the source
code from [Wt github's page](https://github.com/kdeforche/wt), or tagged version.


```bash
# download the latest wt source code from github
git clone https://github.com/kdeforche/wt.git

# cd into wt folder
cd wt/

# select which version to checkout.
# For example, to checkout tag 3.3.5
git checkout -b 3.3.5  

#  and then make build/ folder and cd into it
mkdir build && cd ./build

# compile using c++11 and set install directory to “/opt/wt”:
# without c++11 mode, compilation fails.
cmake ../ -DWT_CPP_11_MODE:STRING="-std=c++11" -DCMAKE_INSTALL_PREFIX:PATH="/opt/wt"

# alternatively, with default install folder:
# cmake ../ -DWT_CPP_11_MODE:STRING="-std=c++11"

# alternatively, compile wt libraries as static (i.e. *.a):
# cmake ../ -DWT_CPP_11_MODE:STRING="-std=c++11" -DCMAKE_INSTALL_PREFIX:PATH="/opt/wt" -DSHARED_LIBS=0

# compile Wt
make # or make -j number_of_threads, e.g., make -j 2

# install into /opt/wt
sudo make install

# compile Wt examples while still being in the build/ folder
make -C examples/

```

## Installation
After successful compilation and installation, the Wt files should
be located in `/opt/wt` as shown below:

```bash
tree -L 3 /opt/wt/
/opt/wt/
├── include
│   └── Wt
│   	├── Auth
│   	├── Chart
│   	├── Dbo
│   	├── DomElement.h
│   	├── EscapeOStream.h
│   	├── Http
│   	├── Json
│   	├── Mail
│   	├── Payment
│   	├── Render
│   	├── Test
│   	├── Utils
│   	├── WAbstractArea
│   	├── WAbstractGLImplementation
│   	├── WAbstractItemDelegate
│   	├── WAbstractItemModel
│   	├── WAbstractItemView
│   	├── WAbstractListModel
│   	├── WAbstractMedia
│   	├── WAbstractProxyModel
│   	├── WAbstractSpinBox
│   	├── WAbstractTableModel
│   	├── WAbstractToggleButton
│   	├── WAccordionLayout
│   	├── WAggregateProxyModel
│   	├── WAnchor
│   	├── WAnimation
│   	├── WApplication
│   	├── WAudio
│   	├── WBatchEditProxyModel
│   	├── WBoostAny
│   	├── WBootstrapTheme
│   	├── WBorder
│   	├── WBorderLayout
│   	├── WBoxLayout
│   	├── WBreak
│   	├── WBrush
│   	├── WButtonGroup
│   	├── WCalendar
│   	├── WCanvasPaintDevice
│   	├── WCheckBox
│   	├── WCircleArea
│   	├── WClientGLWidget
│   	├── WColor
│   	├── WCombinedLocalizedStrings
│   	├── WComboBox
│   	├── WCompositeWidget
│   	├── WConfig.h
│   	├── WContainerWidget
│   	├── WCssDecorationStyle
│   	├── WCssStyleSheet
│   	├── WCssTheme
│   	├── WDate
│   	├── WDateEdit
│   	├── WDatePicker
│   	├── WDateTime
│   	├── WDateValidator
│   	├── WDefaultLayout
│   	├── WDefaultLoadingIndicator
│   	├── WDialog
│   	├── WDllDefs.h
│   	├── WDoubleSpinBox
│   	├── WDoubleValidator
│   	├── WEnvironment
│   	├── WEvent
│   	├── WException
│   	├── WFileResource
│   	├── WFileUpload
│   	├── WFitLayout
│   	├── WFlags
│   	├── WFlashObject
│   	├── WFont
│   	├── WFontMetrics
│   	├── WFormModel
│   	├── WFormWidget
│   	├── WGenericMatrix
│   	├── WGlobal
│   	├── WGLWidget
│   	├── WGoogleMap
│   	├── WGradient
│   	├── WGridLayout
│   	├── WGroupBox
│   	├── WHBoxLayout
│   	├── WHTML5Audio
│   	├── WHTML5Video
│   	├── WIcon
│   	├── WIconPair
│   	├── WIdentityProxyModel
│   	├── WImage
│   	├── WInPlaceEdit
│   	├── WInteractWidget
│   	├── WIntValidator
│   	├── WIOService
│   	├── WItemDelegate
│   	├── WItemSelectionModel
│   	├── WJavaScript
│   	├── WJavaScriptExposableObject
│   	├── WJavaScriptHandle
│   	├── WJavaScriptObjectStorage
│   	├── WJavaScriptPreamble
│   	├── WJavaScriptSlot
│   	├── WLabel
│   	├── WLayout
│   	├── WLayoutItem
│   	├── WLayoutItemImpl
│   	├── WLength
│   	├── WLengthValidator
│   	├── WLineEdit
│   	├── WLineF
│   	├── WLink
│   	├── WLoadingIndicator
│   	├── WLocalDateTime
│   	├── WLocale
│   	├── WLocalizedStrings
│   	├── WLogger
│   	├── WMatrix4x4
│   	├── WMeasurePaintDevice
│   	├── WMediaPlayer
│   	├── WMemoryResource
│   	├── WMenu
│   	├── WMenuItem
│   	├── WMessageBox
│   	├── WMessageResourceBundle
│   	├── WMessageResources
│   	├── WModelIndex
│   	├── WNavigationBar
│   	├── WObject
│   	├── WOverlayLoadingIndicator
│   	├── WPaintDevice
│   	├── WPaintedWidget
│   	├── WPainter
│   	├── WPainterPath
│   	├── WPanel
│   	├── WPdfImage
│   	├── WPen
│   	├── WPoint
│   	├── WPointF
│   	├── WPolygonArea
│   	├── WPopupMenu
│   	├── WPopupMenuItem
│   	├── WPopupWidget
│   	├── WProgressBar
│   	├── WPushButton
│   	├── WRadioButton
│   	├── WRandom
│   	├── WRasterImage
│   	├── WReadOnlyProxyModel
│   	├── WRectArea
│   	├── WRectF
│   	├── WRegExp
│   	├── WRegExpValidator
│   	├── WResource
│   	├── WScrollArea
│   	├── WScrollBar
│   	├── WSelectionBox
│   	├── WServer
│   	├── WServerGLWidget
│   	├── WShadow
│   	├── WSignal
│   	├── WSignalMapper
│   	├── WSlider
│   	├── WSocketNotifier
│   	├── WSortFilterProxyModel
│   	├── WSound
│   	├── WSpinBox
│   	├── WSplitButton
│   	├── WSslCertificate
│   	├── WSslInfo
│   	├── WStackedWidget
│   	├── WStandardItem
│   	├── WStandardItemModel
│   	├── WStatelessSlot
│   	├── WStreamResource
│   	├── WString
│   	├── WStringListModel
│   	├── WStringStream
│   	├── WStringUtil
│   	├── WSubMenuItem
│   	├── WSuggestionPopup
│   	├── WSvgImage
│   	├── WTable
│   	├── WTableCell
│   	├── WTableColumn
│   	├── WTableRow
│   	├── WTableView
│   	├── WTabWidget
│   	├── WTemplate
│   	├── WTemplateFormView
│   	├── WText
│   	├── WTextArea
│   	├── WTextEdit
│   	├── WTheme
│   	├── WTime
│   	├── WTimeEdit
│   	├── WTimePicker
│   	├── WTimer
│   	├── WTimerWidget
│   	├── WTimeValidator
│   	├── WToolBar
│   	├── WTransform
│   	├── WTree
│   	├── WTreeNode
│   	├── WTreeTable
│   	├── WTreeTableNode
│   	├── WTreeView
│   	├── WValidationStatus
│   	├── WValidator
│   	├── WVBoxLayout
│   	├── WVector3
│   	├── WVector4
│   	├── WVectorImage
│   	├── WVideo
│   	├── WViewWidget
│   	├── WVirtualImage
│   	├── WVmlImage
│   	├── WWebWidget
│   	├── WWidget
│   	└── WWidgetItem
├── lib
│   ├── libwtdbopostgres.so -> libwtdbopostgres.so.39
│   ├── libwtdbopostgres.so.3.3.5
│   ├── libwtdbopostgres.so.39 -> libwtdbopostgres.so.3.3.5
│   ├── libwtdbo.so -> libwtdbo.so.39
│   ├── libwtdbo.so.3.3.5
│   ├── libwtdbo.so.39 -> libwtdbo.so.3.3.5
│   ├── libwtdbosqlite3.so -> libwtdbosqlite3.so.39
│   ├── libwtdbosqlite3.so.3.3.5
│   ├── libwtdbosqlite3.so.39 -> libwtdbosqlite3.so.3.3.5
│   ├── libwtfcgi.so -> libwtfcgi.so.39
│   ├── libwtfcgi.so.3.3.5
│   ├── libwtfcgi.so.39 -> libwtfcgi.so.3.3.5
│   ├── libwthttp.so -> libwthttp.so.39
│   ├── libwthttp.so.3.3.5
│   ├── libwthttp.so.39 -> libwthttp.so.3.3.5
│   ├── libwt.so -> libwt.so.39
│   ├── libwt.so.3.3.5
│   ├── libwt.so.39 -> libwt.so.3.3.5
│   ├── libwttest.so -> libwttest.so.9
│   ├── libwttest.so.3.3.5
│   └── libwttest.so.9 -> libwttest.so.3.3.5
└── share
	└── Wt
    	└── resources
```

## Running some Wt examples

The examples where compiled in `wt/build/examples` as shown above, and the
examples binaries are in that folder. However, **the best way to run the examples
is from their source folders**, not the build folder. The reason is that
the source folders contain, except
the c++ source files, csv files, image files, template files, used in the examples.
If examples are run from their source folders, they can also find files located in
 `wt/resources/` which they use.

```bash
# go to wt/examples source code
# if still in build/ folder than this can be done as follows
cd ../examples

######################
# hello example
######################
cd hello/
../../build/examples/hello/hello.wt --http-port 8080 --http-addr 0.0.0.0 --docroot .


######################
# wt-homepage example
######################
cd wt-homepage/
../../build/examples/wt-homepage/home.wt --http-port 8080 --http-addr 0.0.0.0 --docroot .


######################
# wt-homepage example
######################
cd javascript/
../../build/examples/javascript/javascript.wt --http-port 8080 --http-addr 0.0.0.0 --docroot .


######################
# charts example
######################
cd charts/
../../build/examples/charts/charts.wt --http-port 8080 --http-addr 0.0.0.0 --docroot .

# ...
# and so forth for other examples
```

## Other repositories of mine
Other repositories can be found on  [github](https://github.com/moneroexamples?tab=repositories).
Please know that some of the examples/repositories are not
finished and may not work as intended.

## How can you help?

Constructive criticism, code and website edits are always good. They can be made through github.

Some Monero are also welcome:
```
48daf1rG3hE1Txapcsxh6WXNe9MLNKtu7W7tKTivtSoVLHErYzvdcpea2nSTgGkz66RFP4GKVAsTV14v6G3oddBTHfxP6tU
```
