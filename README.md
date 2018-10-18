# adsorptionview

[![pub package](https://img.shields.io/pub/v/adsorptionview_flutter.svg)](https://pub.dartlang.org/packages/adsorptionview_flutter)

ListView adsorption ceiling layout, support Equally high items and Unequally high items.

ListView的吸顶布局，现在支持等高和非等高的Item。

HomePage：[https://github.com/baoolong/Adsorptionview](https://github.com/baoolong/Adsorptionview)

MoreWidght：[https://github.com/OpenFlutter/PullToRefresh](https://github.com/OpenFlutter/PullToRefresh)

<img width="38%" height="38%" src="https://raw.githubusercontent.com/OpenFlutter/PullToRefresh/master/demonstrationgif/20180912_100745.gif"/>

## Usage

Add this to your package's pubspec.yaml file:

	dependencies:
	  adsorptionview_flutter: ^0.1.2
	  
Add it to your dart file:

    import 'package:adsorptionview_flutter/adsorptionview_flutter.dart';
    
And ListView dataBin must extends AdsorptionData ,Add it to your dataBin file
    
    import 'package:adsorptionview_flutter/adsorptiondatabin.dart';

## Example

#### 	Bin

    import 'package:adsorptionview_flutter/adsorptiondatabin.dart';
   
    class AdsorptionListBin extends AdsorptionData{
      AdsorptionListBin( this.headerName);
   
      String headerName;
   
      @override
      String toString() {
        return 'AdsorptionListBin{headerName: $headerName}';
      }
   
    }
   
   
#### 	Demo
    import 'package:flutter/material.dart';
    import 'package:flutter/rendering.dart';
    import 'package:flutterapp/bin/adsorptionlistbin.dart';
    import 'package:adsorptionview_flutter/adsorptionview_flutter.dart';
    
    class AdsorptionViewDemo extends StatefulWidget{
      @override
      State<StatefulWidget> createState() {
        List<AdsorptionListBin> adsorptionDatas=new List();
        AdsorptionListBin adsorptionData;
    
        adsorptionData=new AdsorptionListBin("A");
        adsorptionData.isHeader=true;
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("阿杜");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("阿宝");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("艾夫杰尼");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("阿牛");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("安苏羽");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("阿勒长青");
        adsorptionDatas.add(adsorptionData);
    
    
        adsorptionData=new AdsorptionListBin("B");
        adsorptionData.isHeader=true;
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("白小白");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("白羽毛");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("Bridge");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("斑马");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("白一阳");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("白举纲");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("暴林");
        adsorptionDatas.add(adsorptionData);
    
    
        adsorptionData=new AdsorptionListBin("C");
        adsorptionData.isHeader=true;
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("陈奕迅");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("陈小春");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("成龙");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("陈百强");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("迟志强");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("崔健");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("陈晓东");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("陈学冬");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("蔡国庆");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("陈冠希");
        adsorptionDatas.add(adsorptionData);
    
        adsorptionData=new AdsorptionListBin("陈琳");
        adsorptionDatas.add(adsorptionData);
        return new AdsorptionViewState(adsorptionDatas);
      }
    }
    
    ///此控件适用于固定高度的ListView
    class AdsorptionViewState extends State<AdsorptionViewDemo>{
    
      AdsorptionViewState(this.adsorptionDatas);
    
      List<AdsorptionListBin> adsorptionDatas;
      double itemHeight=50.0;
    
    
      @override
      Widget build(BuildContext context) {
        return new Scaffold(
          appBar: new AppBar(
            title: new Text("吸附布局"),
          ),
          body:new AdsorptionView(
            isEqualHeightItem: true,
            adsorptionDatas: adsorptionDatas,
            generalItemChild: (AdsorptionListBin bin) {
              return new Container(
                alignment: Alignment.centerLeft,
                margin: EdgeInsets.fromLTRB(15.0, 0.0, 0.0, 0.0),
                child: new Text(
                  bin.headerName,
                  style: new TextStyle(fontSize: 18.0, color: Colors.grey),
                ),
              );
            },
            headChild: (AdsorptionListBin bin) {
              return new Container(
                color: Colors.grey,
                alignment: Alignment.centerLeft,
                padding: EdgeInsets.fromLTRB(15.0, 0.0, 0.0, 0.0),
                child: new Text(
                  bin.headerName,
                  style: new TextStyle( fontSize: 20.0,color: Colors.black),
                ),
              );
            },
          ),
        );
      }
    }

## Notice

吸顶布局不能使用类似苹果的弹簧布局，以后可能会支持；目前等高的支持比较好，非等高的有点问题，后续会改进

Adsorptionview ceiling layout can not use the spring layout of Apple, may be supported in the future; the current support of the equally hight items better, the  unequally hight items  has a problem, the follow-up will improve

## LICENSE
    MIT License

	Copyright (c) 2018 baoolong
	
	Permission is hereby granted, free of charge, to any person obtaining a copy
	of this software and associated documentation files (the "Software"), to deal
	in the Software without restriction, including without limitation the rights
	to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
	copies of the Software, and to permit persons to whom the Software is
	furnished to do so, subject to the following conditions:
	
	The above copyright notice and this permission notice shall be included in all
	copies or substantial portions of the Software.
	
	THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
	IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
	FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
	AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
	LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
	OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
	SOFTWARE.
