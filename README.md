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
