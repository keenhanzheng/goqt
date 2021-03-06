GoQt
====

## Introduction

_GoQt is golang bindings to the Qt cross-platform application framework._

* Version: 0.1
* Author: [visualfc](mailto:visualfc@gmail.com)


## Experiment
GoQt project current is experiment.

## What is GoQt
GoQt is a GUI toolkit for the Go programming language. It allows Go programmers to create programs with a robust, highly functional graphical user interface, simply and easily. It is implemented as a Golang extension module (cgo code) that wraps the popular Qt cross platform GUI library, which is written in C++.

Like Golang and Qt, GoQt is Open Source. The Golang extension module(cgo code) under the BSD license. The C++ bindings library under the LGPL license. 

## Platforms

* Golang : 1.5.2

* GoQt is a cross-platform toolkit, But my test platforms are Microsoft Windows (x86) Qt4.8.5 and Qt5.5.1 toolkit and go1.5.2


## Install GoQt

### 1.get goqt
    > go get github.com/visualfc/goqt
### 2.build qtdrv, need install QtSDK
    > cd goqt/qtdrv
    > qmake "CONFIG+=release"
    > make
### 3.build rcc	
	> cd goqt/tools/rcc
	> qmake "CONFIG+=release"	
	> make
### 4.build ui, need CGO_ENABLED=1 and install gcc
    > cd goqt/ui
    > go install -v
### 5.build examples
    > cd goqt\examples\minimal
    > build.bat
    > ..\..\bin\minimal.exe

## Examples

		package main
		
		import (
			"fmt"
			"runtime"
		
			"github.com/visualfc/goqt/ui"
		)
		
		func main() {
			ui.Run(func() {
				info := fmt.Sprintf("Hello GoQt Version %v \ngo verison %v %v/%v", ui.Version(), runtime.Version(), runtime.GOOS, runtime.GOARCH)
		
				lable := ui.NewLabel()
				lable.SetText(info)
		
				hbox := ui.NewHBoxLayout()
				hbox.AddWidget(lable)
		
				widget := ui.NewWidget()
				widget.SetLayout(hbox)
				widget.Show()
			})
		}


### Website
 * Source code
  * https://github.com/visualfc/goqt
 * Examples
  * https://github.com/visualfc/goqt/tree/master/examples
 * LiteIDE
  * https://github.com/visualfc/liteide

