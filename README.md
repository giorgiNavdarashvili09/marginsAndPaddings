# მარჯინები და პადინგები
იმისათვის, რომ ვიჯეტები სხვა ვიჯეტებისაგან ან/და ეკრანის კიდეებისაგან დავაშოროთ შეგვიძლია გამოვიყენოთ Container ვიჯეტის margin და padding პარამეტრები

საწყისი კოდი ასე გამოიყურება

```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
        appBar: AppBar(
          title: Text("Margins and paddings"),
        ),
        body: Container(
          color: Colors.teal,
          child: Text(
            "Hello World",
            style: TextStyle(color: Colors.white),
          ),
        ),
      ),
    );
  }
}


```

კოდის გაშვების შემდეგ ვიღებთ შესაბამის ვიზუალს<br /><br />
<img src="/screenshots/starting.jpg" width=300>

## padding
იმისათვის, რომ Text ვიჯეტის კიდეებსა და Container ვიჯეტის კიდეებს შორის გავზარდოთ(ამჟამად 0_ია) ადგილი გამოვიყენებთ padding პარამეტრს <br />

Container ვიჯეტის კოდი padding პარამეტრის დამატების შემდეგ ასე გამოიყურება

```
        body: Container(
          padding: EdgeInsets.all(16),
          color: Colors.teal,
          child: Text(
            "Hello World",
            style: TextStyle(color: Colors.white),
          ),
        ),

```

EdgeInsets არის Flutter ის სინტაქსი რომლითაც შეგვიძლია მივუთითოთ padding ის ზომა სხვადასხვა გვერდებისათვის. ამ შემთხვევაში EdgeInsets.all(16) ოთხივე გვერდს აძლევს "16" პადინგს. <br />
ამ ცვლილების შემდეგ ჩვენი Container ვიჯეტი ასე გამოიყურება <br /><br />
<img src="/screenshots/padding-all.jpg" width=300><br /><br />

ასევე შეგვიძლია მივუთითოთ მხოლოდ ერთი გვერდი რომელსაც ექნება პადინგი EdgeInsets.only() _ის გამოყენებით. მაგალითად:

```
        body: Container(
          padding: EdgeInsets.only(left: 16),
          color: Colors.teal,
          child: Text(
            "Hello World",
            style: TextStyle(color: Colors.white),
          ),
        ),
```
რის შემდეგაც ჩვენი აპლიკაცია მიიღებს შესაბამის ვიზუალს.<br /><br />
<img src="/screenshots/padding-left.jpg" width=300><br /><br />
EdgeInsets.only()_ ის შეგვიძლია მივუთითოთ 4 სხვადასხვა გვერდი შესაბამისად(left, top, right, bottom - მარცხნივ, ზემოთ, მარჯვნივ, ქვემოთ).
მაგალითად EdgeInsets.only(left: 16,top: 32,) Container ვიჯეტს მიანიჭებს "16" პადინგს მარცხნივ, და "32" პადინგზს ზემოთ. <br /> <br />
Container ვიჯეტის სრული კოდი ასე გამოიყურება:

```
        body: Container(
          padding: EdgeInsets.only(left: 16,top: 32,),
          color: Colors.teal,
          child: Text(
            "Hello World",
            style: TextStyle(color: Colors.white),
          ),
        ),
```

ხოლო აპლიკაციის ვიზუალი ასე:<br /><br />
<img src="/screenshots/padding-left-top.jpg" width=300><br /><br />

## margin
padding_ის მსგავსად margin_იც გამოიყენება ვიჯეტისებსა და ეკრანის კიდეებს შორის დამატებითი ადგილის გამოსაყოფად. თუმცა მარჯინის შემთხვევაში ეს ადგილი ემატება ვიჯეტს გარეთ.
ჩვენი Container ვიჯეტის კოდი margin პარამეტრის დამატების შემდეგ ასე გამოიყურება:

```
        body: Container(
          margin: EdgeInsets.all(16),
          padding: EdgeInsets.all(16),
          color: Colors.teal,
          child: Text(
            "Hello World",
            style: TextStyle(color: Colors.white),
          ),
        ),
```

ყურადღება მივაქციოთ, რომ როგორც padding პარამეტრი ასევე margin პარამეტრი "ელოდება" EdgeInsets.

მოცემული კოდის გაშვების შემდეგ ჩვენი Container ვიჯეტი ასე გამოიყურება:<br /><br />
<img src="/screenshots/margin-left-top.jpg" width=300><br /><br />
ყურადღება მიაქციეთ რომ Container ვიჯეტი ეკრანის კიდეს დაშორდა მარცხნივ და ზემოთ. Container ვიჯეტს EdgeInsets.all(16) სინტაქსის გამოყენებით მარჯინი ასევე აქვს ქვემოთ და მარჯვნივ თუმცა რადგან სხვა ვიჯეტები არ გვაქვს ეს ვიზუალურად არ ჩანს<br /><br />

padding_ის მსგავსად margin პარამეტრიც შეგვიძლია მხოლოდ ჩვენთვის სასურველ გვერდებს გავუწეროთ.
მაგალითად:<br /><br />
```
        body: Container(
          margin: EdgeInsets.only(left: 16),
          padding: EdgeInsets.all(16),
          color: Colors.teal,
          child: Text(
            "Hello World",
            style: TextStyle(color: Colors.white),
          ),
        ),
```
<br /><br />
margin: EdgeInsets.only(left: 16) ის დახმარებით შეგვიძლია Container ვიჯეტს მარგინი გავუწეროთ მხოლოდ მარცხენა გვერდზე. რაც მოგვცემს შესაბამის ვიზუალს:<br /><br />
<img src="/screenshots/margin-left.jpg" width=300><br /><br />
როგორც შეამჩნიეთ Container ვიჯეტი მხოლოდ მარცხნიდან არის დაშორებული ეკრანს.

## SizedBox

ვიჯეტებს შორის ადგილის შესაქმნელად ან/და გასაზრდელად შეგვიძლია გამოვიყენოთ SizedBox ვიჯეტი

ჩვენი საწყისი კოდი ასე გამოიყურება:

```
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Scaffold(
          appBar: AppBar(
            title: Text("Margins and paddings"),
          ),
          body: Row(
            children: [
              Container(
                color: Colors.red,
                width: 100,
                height: 100,
              ),
              Container(
                color: Colors.amber,
                width: 100,
                height: 100,
              ),
            ],
          ),
        ),
    );
  }
}

```
ხოლო აპლიკაციის ვიზუალი ასე:<br /><br />
<img src="/screenshots/sizedbox-starter.jpg" width=300><br /><br />
იმისათვის, რომ ორ Container ვიჯეტს შორის გამოვყოთ ადგილი აქამდე ვიყენებდით Row ვიჯეტის პარამეტრ - mainAxisAlignment: MainAxisAlignment.spaceBetween
თუმცა ეს პარამეტრი ვიჯეტებს შესაბამისად ეკრანის მარცხნივ და მარჯვნივ ათავსებს.

```
        body: Row(
          mainAxisAlignment: MainAxisAlignment.spaceBetween,
          children: [
            Container(
              color: Colors.red,
              width: 100,
              height: 100,
            ),
            Container(
              color: Colors.amber,
              width: 100,
              height: 100,
            ),
          ],
        ),
```
<img src="/screenshots/row-space-between.jpg" width=300><br /><br />
ასეთი შედეგი შეიძლება ყოველთვის სასურველი არ იყოს. 

```
        body: Row(
          children: [
            Container(
              color: Colors.red,
              width: 100,
              height: 100,
            ),
            SizedBox(
              width: 64,
            ),
            Container(
              color: Colors.amber,
              width: 100,
              height: 100,
            ),
          ],
        ),
```
ზემოთ მოცემულ კოდში პირველ რიგში ამოვიღეთ mainAxisAlignment პარამეტრი და ჩავამატეთ SizedBox ვიჯეტი. SizedBox(width: 64) ის დახმარებით ორ Container ვიჯეტს შორის გაჩნდა 64 პიქსელი დაშორება რაც ჩვენს აპლიკაციაში ასე გამოიყურება.<br /><br />
<img src="/screenshots/sizedbox.jpg" width=300><br /><br />