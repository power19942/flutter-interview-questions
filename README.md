# Yanıtlarıyla birlikte Flutter mülakat soruları 

bu dosya, yanıtlarıyla birlikte flutter mülakat sorularının bir listesini içerir

### not ###

bu sorular ve cevaplar, stackoverflow, medium ve diğer github depoları gibi internetteki farklı kaynaklardan toplanır.

---
 Flutter Soruları ve Cevapları
---

1. Flutter'da `StatelessWidget` ile `StatefulWidget` arasındaki fark nedir?

Stateless Widget
StatelessWidget, bir uygulamanın çalışma zamanı sırasında durumunu değiştiremez, bu da uygulama çalışırken kendini yeniden çizemeyeceği anlamına gelir. StatelessWidget'lar değişmezdir.

Stateful Widget
StatefulWidget, uygulama çalışırken kendisini birden çok kez yeniden çizebilir, bu da durumunun değişken olduğu anlamına gelir. Örneğin, bir butona basıldığında widget'ın durumu değişir.

---

2.`Stateful Widget Lifecycle(Yaşam Döngüsü)`'ı açıklayınız?

Lifecycle(Yaşam Döngüsü) aşağıdaki basitleştirilmiş adımlara sahiptir:
createState()
mounted == true
initState()
didChangeDependencies()
build()
didUpdateWidget()
setState()
deactivate()
dispose()
mounted == false

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/life_cycle.png' alt="life cycle"/>

---

3.`tree shaking` (flutter web) nedir?

Bir Flutter web uygulamasını derlerken, JavaScript paketi dart2js derleyicisi tarafından oluşturulur. Sürüm derlemesi, kodunuzu tree shaking de dahil olmak üzere en yüksek optimizasyon düzeyine sahiptir.
Tree shaking, yalnızca yürütülmesi garanti edilen kodu dahil ederek ölü kodu(dead code) ortadan kaldırma işlemidir. Bu, kullanılmayan sınıflar veya işlevler derlenmiş JavaScript paketinin dışında tutulduğu için uygulamanızın içerdiği kitaplıkların boyutu hakkında endişelenmenize gerek olmadığı anlamına gelir.

---

4.`Spacer` widget'ı nedir?

Spacer, flex container(esnek kapsayıcı) ile widget'lar arasındaki boş alanı yönetir. Row ve Column MainAxis alignment ile eşit olarak alanı da yönetebiliriz

---

5.`hot restart` ve `hot reload` arasındaki fark nedir?


Flutter'da Hot Reload nedir?:

Flutter çalışırken hot reload özellikleri, komut isteminde(command prompt) veya Terminal'de küçük r tuşu kombinasyonu ile çalışır. Hot reload özelliği dosyamıza yeni eklenen kodu hızlı bir şekilde derler ve kodu Dart Virtual Machine'e gönderir. Code Dart Virtual Machine, uygulama kullanıcı arayüzünü widget'larla günceller. Hot Reload, Hot Restart'a göre daha az zaman alır. Hot Reload'da da bir dezavantaj vardır, uygulamanızda States(durumlar) kullanıyorsanız, Hot Reload States'i korur, böylece Hot Reload'da set'imizi varsayılan değerlerine güncellemezler.


Flutter'da Hot Restart nedir?:

Hot Restart, Hot Reload'dan çok farklıdır. Hot Restart, korunmuş State değerini yok eder ve bunları varsayılan değerlerine ayarlar. Bu nedenle, uygulamanızda States değerini kullanıyorsanız, her Hot Restart'ın ardından geliştirici tamamen derlenmiş bir uygulama alır ve tüm durumlar varsayılanlarına ayarlanır. Uygulama widget tree, yeni yazılan kodla tamamen yeniden oluşturulur. Hot Restart, Hot Reload'dan çok daha uzun sürer

---


6.`InheritedWidget` nedir?

https://www.youtube.com/watch?v=Zbm3hjPjQMk

---

7.build() yöntemi neden State'te ve StatefulWidget'ta değil?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/stateful_build.png' alt="stateful_build"/>
-- fotoğrafın türkçeye çevirilmiş hali --
StatefulWidget'in ayrı bir State sınıfı kullanması ve kendi bünyesinde build metoduna sahip olmamasının nedeni, bir Widget içindeki tüm alanların değişmez olması ve bunun tüm alt sınıflarını içermesidir.

StatelessWidget'ın kendi yapısına ve içinde tanımlanmış diğer ilişkili yöntemlere sahip olduğunu fark etmiş olabilirsiniz, ancak bu, StatelessWidget'ın tamamen sağlanan bilgiler kullanılarak oluşturulan ve State'inde gelecekte herhangi bir değişiklik beklemeyen doğası nedeniyle mümkün olmuştur.

StatefulWidget söz konusu olduğunda, State bilgisi uygulama sırasında ara sıra değişir (veya değişmesi beklenir), bu nedenle bu bilgi, Widget sınıf koşullarını (tüm alanlar sabittir) karşılamak için son bir alanda (derleme) depolamaya uygun değildir. Bu nedenle State sınıfı tanıtıldı. Tanımlı Durumunuzu StatefulWidget'ınıza eklemek için createState işlevini geçersiz kılmanız(override) ve tüm bu değişikliğin ayrı bir sınıfta olmasına izin vermeniz yeterlidir.

---

8.Dart'da `pubspec` dosyası nedir?

Pubspec dosyası, bir Flutter uygulaması için varlıkları(assets) ve bağımlılıkları(dependencies) yönetir.

---

9.Flutter nasıl yereldir(native)?

Flutter, yalnızca yerel platformun tuvalini kullanır ve kullanıcı arayüzünü ve tüm bileşenleri sıfırdan çizer. Tüm UI öğeleri, yerel öğelerle aynı görünür. Bu, temel olarak bazı dilleri yerel dile dönüştürmek için harcanan zamanı azaltır ve kullanıcı arabirimi oluşturma süresini hızlandırır. Sonuç olarak, UI performansı oldukça yüksektir.

---

10.Flutter'da `Navigator` ve `Routes` nedir?

Navigasyon(navigation) ve yönlendirme(routing), kullanıcının farklı sayfalar arasında hareket etmesine izin veren tüm mobil uygulamaların temel kavramlarından bazılarıdır. Her mobil uygulamanın farklı bilgi türlerini görüntülemek için birkaç ekran içerdiğini biliyoruz. Örneğin, bir uygulamanın çeşitli ürünleri içeren bir ekranı olabilir. Kullanıcı o ürüne dokunduğunda, hemen o ürünle ilgili ayrıntılı bilgileri görüntüler.

---

11.`PageRoute` nedir?

Rotaya animasyon geçişi eklememize izin verir
https://github.com/divyanshub024/Flutter-route-transition

---


12.`async`, `await` ve `Future` terimlerini açıklayın?


Async, bu işlevin eşzamansız(asynchronous) olduğu ve sonucunu almak için biraz beklemeniz gerekebileceği anlamına gelir.
Await kelimenin tam anlamıyla - bu işlev bitene kadar burada bekleyin ve dönüş değerini alacaksınız.
Future is a type that ‘comes from the future’ and returns value from your asynchronous function. It can complete with success(.then) or with
an error(.catchError)
Future, 'gelecekten gelen'(comes from the future) bir türdür ve eşzamansız(asynchronous) işlevinizden değer döndürür. success(.then) veya bir error(.catchError) ile tamamlanabilir

https://www.youtube.com/watch?v=SmTCmDMi4BY

---

13.bir listview'i dinamik olarak nasıl güncelleyebilirsiniz?

listview öğesi kaynağını güncellemek ve kullanıcı arayüzünü yeniden oluşturmak için setState kullanarak 

---

14.`Stream` nedir?

Stream bir boru(pipe) gibidir, bir uca bir değer koyarsınız ve diğer uçta bir dinleyici(listener) varsa o dinleyici o değeri alır. Bir Stream birden çok dinleyicisi olabilir ve bu dinleyicilerin tümü, boru hattına konulduğunda aynı değeri alır. Bir Stream'e değer koymanın yolu, bir StreamController kullanmaktır.

---

15.Flutter'da `keys` nedir ve ne zaman kullanmalıyız?

Çoğu zaman keys kullanmanıza gerek yoktur, çerçeve(framework) bunu sizin yerinize halleder ve widget'lar arasında ayrım yapmak için bunları dahili olarak kullanır. Yine de bunları kullanmanız gerekebilecek birkaç durum vardır.

Widget'ları caselere göre ayırmanız gerekirse, ObjectKey ve ValueKey, widget'ların nasıl farklılaştırılacağını tanımlamak için yararlı olabilir.

Başka bir örnek, bir ebeveynden erişmek istediğiniz bir çocuğunuz varsa, ebeveynde bir GlobalKey oluşturabilir ve bunu çocuğun yapıcısına(constructor) iletebilirsiniz. Ardından, çocuğun state'ini almak için globalKey.state yapabilirsiniz (örneğin, callback bir düğmeye basın). Bunu aşmanın genellikle daha iyi yolları olduğundan, bunun aşırı kullanılmaması gerektiğini unutmayın.

https://www.youtube.com/watch?v=kn0EOS-ZiIc&feature=emb_title

---

16.`GlobalKeys` nedir?

GlobalKey'lerin iki kullanımı vardır: widget'ların uygulamanızın herhangi bir yerinde state'lerini kaybetmeden ebeveynlerini değiştirmelerine izin verirler veya widget ağacının tamamen farklı bir bölümündeki başka bir widget hakkındaki bilgilere erişmek için kullanılabilirler. İlk senaryonun bir örneği, aynı widget'ı iki farklı ekranda göstermek isteyip istemediğinizi, ancak aynı state'i koruyarak bir GlobalKey kullanmak isteyip istemediğinizi gösterebilir.

---

17.mainAxisAlignment ve crossAxisAlignment ne zaman kullanmalısınız?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/mainAxisAlignment.png' alt="mainAxisAlignment"/>

---

18.`double.INFINITY`'yi ne zaman kullanabilirsiniz?

Widget'ın ana widget'ın izin verdiği kadar büyük olmasını istediğinizde

---

19.`Ticker`, `Tween` ve `AnimationController` nedir?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/ticker.png' alt="ticker"/>
-- fotoğrafın türkçesi -- 
AnimationController: Bu, "Animation" yönetir. İşlenen her kare için yeni bir değer üretir, animasyon durumunu takip eder ve bir animasyonu oynatma (ileri), geri alma veya durdurma işlevselliğini ortaya çıkarır.
Animation/ Tween: Bu, bir eğri boyunca baştan sona nasıl hareket edileceği ile birlikte başlangıç ve bitiş değerlerini tanımlar. Bu nesne, tuttuğu değer değiştiğinde, ValueListenable protokolü aracılığıyla denetleyiciye(controller) bildirimde bulunacaktır.
Ticker: Bir ticker, frameCallback'i dinleyen ve tick geçerli çerçeve ile son çerçeve arasındaki geçen süreyi ticker listner'a ileten bir işlevi çağıran bir sınıftır. Bizim durumumuzda controller.

Animation Sequences(Animasyon dizileri)
sequence animation elde etmek için, her yeni animasyon değeri hesaplandığında widget'ınızı bir oluşturucu işlevi aracılığıyla yeniden oluşturmanıza izin veren AnimatedBuilder adlı animasyon kodunun azaltılmasına da yardımcı olan yeni bir Widget sunacağız.

---

20.`ephemeral` state nedir?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/ephemeral.png' alt="ephemeral"/>
-- fotoğrafın türkçesi --
Ephemeral state (bazen UI state veya local state olarak adlandırılır ), tek bir widget'da düzgün bir şekilde içerebileceğiniz durumdur.

Bu kasıtlı olarak belirsiz bir tanımdır, bu yüzden işte birkaç örnek.

geçerli sayfa bir PageView
karmaşık bir animasyonun mevcut ilerlemesi
geçerli seçili sekme BottomNavigationBar

---

21.Bir `AspectRatio` widget ne için kullanılır?

AspectRatio Widget, düzen kısıtlamalarına uyarken en boy oranını korumak için en iyi boyutu bulmaya çalışır. AspectRatio Widget'ı, uygulamanızdaki widget'ların en boy oranını ayarlamak için kullanılabilir

---

22.State'den `StatefulWidget` özelliklerine nasıl erişirsiniz?

widget property(özelliklerini) kullanarak

---

23.Bir `Future` kullanmanızı veya dönüştürmenizi gerektirecek iki veya daha fazla işlemden bahsedin

	1. API'yi http kullanarak çağırma
	2. Geolocator paketinden sonuç(result) alma
	3. FutureBuilder widget'ı ile

---

24.`SafeArea`'nın amacı nedir?

SafeArea, temel olarak yüceltilmiş bir Dolgu(Padding) widget'ıdır. Başka bir widget'ı SafeArea ile sararsanız, widget'ınızın sistem durum çubuğu(system status bar), çentikler(notches), delikler(holes), yuvarlatılmış köşeler(rounded corners) ve üreticilerin(manufactures) diğer "yaratıcı(creative)" özellikleri tarafından engellenmesini önlemek için gereken tüm gerekli dolguyu ekler.

---

25.`mainAxisSize` ne zaman kullanılır?

Column veya Row'da MainAxisSize kullandığınızda, ana eksen(main axis) boyunca Column veya Row boyutunu, yani Column için yüksekliği ve Row için genişliği belirlerler.

https://itnext.io/flutter-mainaxissize-max-vs-min-d9095d8f7914

---

26.`SizedBox` VS `Container`?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/sized.png' alt="sized"/>

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/sized2.png' alt="sized2"/>

---


27.Flutter'daki `Visibility` widget'larını ve farklarını listeleyin?

	1. Visibility
	2. Opacity
	3. Offstage
	
https://medium.com/@danle.sdev/widget-hide-and-seek-a-guide-to-managing-flutter-widgets-visibility-d7977cbaf444

---

28.Container'da `Color` ve `Decoration` property'sini(özelliğini) aynı anda kullanabilir miyiz?

Hayır

color özelliği, bir renk alanıyla bir BoxDecoration oluşturmak için bir kısayoldur. Bir BoxDecoration ekliyorsanız, rengi BoxDecoration'a yerleştirmeniz yeterlidir.

---

29.`CrossAxisAlignment.baseline`'ın çalışması için ayarlamamız gereken başka bir özellik nedir?

crossAxisAlignment: CrossAxisAlignment.baseline
textBaseline: TextBaseline.ideographic,

---

30.ne zaman `resizeToAvoidBottomInset` kullanmalıyız?

true ise, body ve scaffold'ın kayan(floating) widget'ları, yüksekliği ortam MediaQuery'nin MediaQueryData.viewInsets bottom özelliği tarafından tanımlanan ekran klavyesinden kaçınmak için kendilerini boyutlandırmalıdır.

For example, if there is an onscreen keyboard displayed above the scaffold, the body can be resized to avoid overlapping the keyboard, which prevents widgets inside the body from being obscured by the keyboard
Örneğin, Scaffold'ın üzerinde görüntülenen bir ekran klavyesi varsa, klavyenin üst üste binmesini önlemek için body yeniden boyutlandırılabilir, bu da body içindeki widget'ların klavye tarafından gizlenmesini önler.

`With resizeToAvoidBottomInset`
https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/316760/7da984e6-ec32-7989-174c-0e104e4c5557.gif

`without resizeToAvoidBottomInset`
https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/316760/0c933d45-82a2-4401-836c-d1c6f5abc2db.gif

---

31.Bir import ifadesinde `as`,`show` ve `hide` arasındaki farklar nelerdir?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/as.png' alt="as"/>
-- fotoğrafın türkçesi --
as ile içe aktarılan kitaplığa bir ad veriyorsunuz. Genellikle, bir kitaplığın(library) çok sayıda küresel işlevi(global functions) varsa, namespace'inizi kirletmesini önlemek için yapılır. as kullanıyorsanız, söz konusu kitaplığın tüm işlevlerine ve sınıflarına örneğinizde yaptığınız gibi erişerek erişebilirsiniz: GoogleMap.LatLng.

show (ve hide) ile, uygulamanızda görünür olmasını istediğiniz belirli sınıfları seçebilirsiniz.

---

32.Bir `TextEditingController`'ın önemi nedir?

Kullanıcı, ilişkili bir TextEditingController ile bir metin alanını(text field) her değiştirdiğinde, metin alanı değeri günceller ve denetleyici(controller), dinleyicilerini(listeners) bilgilendirir. Dinleyiciler, kullanıcının ne yazdığını veya seçimin nasıl güncellendiğini öğrenmek için metin(text) ve seçim(selection) özelliklerini okuyabilir.

---

33.Neden `Listview`'da reverse(ters) özelliğini kullanıyoruz?

List<String> animals = ['cat', 'dog', 'duck'];
List<String> reversedAnimals = animals.reversed.toList();

---

34.Bir örnekle Modal ve Persistent BottomSheet arasındaki fark?

---

35.`Inherited Widget`'ın `Provider`'dan farkı nedir?

Provider temel olarak InheritedWidgets mantığını alır, ancak ortak metni kesin minimuma indirir

---

36.`UnmodifiableListView` nedir?

Liste öğeleri(list items) ekleyerek veya çıkararak değiştirilemez

https://github.com/filiph/state_experiments/issues/5

---

37.`??` ve `?.` işleçleri arasındaki fark

`??` 
expr1 ?? expr2
expr1 boş değilse, değerini döndürür; aksi halde expr2'nin değerini değerlendirir ve döndürür.

`?.` gibi. ancak en soldaki işlenen boş olabilir; örnek: foo?.bar, foo null olmadığı sürece foo ifadesinden özellik çubuğunu seçer (bu durumda foo?.bar'ın değeri null olur)


https://dart.dev/guides/language/language-tour

---

38.What is the purpose of `ModalRoute.of()`?

 ModalRoute.of() method. This method returns the current route with the arguments


`final args = ModalRoute.of(context).settings.arguments;`

---

39.Difference between a `Navigator.pushNamed` and `Navigator.pushReplacementNamed`?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/pushNamed.png' alt="pushNamed"/>

---

40.Difference between a Single Instance and Scoped Instance ?

https://codewithandrea.com/articles/2019-06-10-global-access-vs-scoped-access/

---

41.Difference between getDocuments() vs snapshots()?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/getDocuments.png' alt="getDocuments"/>

---

42.What is a `vsync`?

Vsync basically keeps the track of screen, so that Flutter does not renders the animation when the screen is not being displayed

---

43.When does the animation reach `completed` or `dismissed` status?

animations that progress from 0.0 to 1.0 will be dismissed when their value is 0.0. An animation might then run forward (from 0.0 to 1.0) or perhaps in reverse (from 1.0 to 0.0). Eventually, if the animation reaches the end of its range (1.0), the animation reaches the completed status.

---

44.Difference between `AnimationController` and `Animation`?

AnimationController is for how long the animation would be and how to control from time, upper and lower boundary, how to control data with time, length, sequence, etc. while AnimationTween is for the range of animation with time, colour, range, sequence, etc as long the animation would be while

---

45.When to use a SingleTickerProviderStateMixin and TickerProviderStateMixin?

---

46.Define a `TweenAnimation` ?

Short for in-betweening. In a tween animation, the beginning and ending points are defined, as well as a timeline, and a curve that defines the timing and speed of the transition. The framework calculates how to transition from the beginning point to the end point

---

47.State the importance of a `Ticker` ?

Ticker is the refresh rate of our animations. This is what we want to pause when our clock is hidden.

A bonus for using Ticker is that this allows the dev-tool to “slow” our animation.
If we use “Slow animations”, then our clock is slowed by 50%. This is a good sign, as it means it will be a lot easier to test our clock!

---


48.Why do we need a `mixins` ?

Mixins are very helpful when we want to share a behavior across multiple classes that don’t share the same class hierarchy, or when it doesn’t make sense to implement such a behavior in a superclass

---

49.When do you use the `WidgetsBindingObserver`?

To check when the system puts the app in the background or returns the app to the foreground

---

50.Why does the `first` flutter app take a very long developing time?

When you are going to build the Flutter app for the first time, it takes a very long time than usual because Flutter builds a device-specific IPA or APK file. In this process, the Xcode and Gradle are used to build a file, which usually takes a long time

---

51.Define what is an `App State`?


The App State is also called an application state or shared state. The app state can be distributed across multiple areas of your app and the same is maintained with user sessions.

Following are the examples of App State:

Login info
User preferences
The shopping cart of an e-commerce application

---

52.What are the two types of `Streams` available in Flutter?


Single subscription streams:

It is a popular and common type of stream.
It consists of a series of events that are parts of a large whole. Here all events have to be delivered in a defined order without even missing a single event.
It is a type of stream that you get when you get a web request or receive a file.
This stream can only be listed once. Listing it, again and again, means missing initial values and overall stream makes no sense at all.
When the listing starts in this stream the data gets fetched and provided in chunks.


Broadcast streams:

This stream is meant for the individual messages that can be handled one at a time. These types of streams are commonly used for mouse events in a browser.
You can list this type of stream at any time.
Multiple listeners can listen at a time and also you have a chance to listen after the cancellation of the previous subscription

---

53.What do you know about Dart `Isolates`?

To gain concurrency Dart makes use of the Isolates method which works on its own without sharing memory but uses passing or message communication.

---

54.What is a `Flutter inspector`?

Flutter inspector is a tool that helps in visualizing and exploring the widget trees. It helps in understanding the present layout and diagnoses various layout issues

---

55.`Stream` vs `Future`?

The difference is that Futures are about one-shot request/response (I ask, there is a delay, I get a notification that my Future is ready to collect, and I'm done!) whereas Streams are a continuous series of responses to a single request (I ask, there is a delay, then I keep getting responses until the stream dries up or I decide to close it and walk away) 

---

56.How to compare two dates that are constructed differently in Dart?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/date.png' alt="date"/>

---

57.What's the difference between `async` and `async*` in Dart?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/async.png' alt="async"/>

---

58.`Debug` vs `Profile` mode?

In debug mode, the app is set up for debugging on the physical device, emulator, or simulator.

Debug 

Assertions are enabled.
Service extensions are enabled.
Compilation is optimized for fast development and run cycles (but not for execution speed, binary size, or deployment).
Debugging is enabled, and tools supporting source level debugging (such as DevTools) can connect to the process.


Profile
In profile mode, some debugging ability is maintained—enough to profile your app’s performance. Profile mode is disabled on the emulator and simulator, because their behavior is not representative of real performance. On mobile, profile mode is similar to release mode, with the following differences:

Some service extensions, such as the one that enables the performance overlay, are enabled.
Tracing is enabled, and tools supporting source-level debugging (such as DevTools) can connect to the process.


---

59.How to convert a `List` into a `Map` in Dart?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/list.png' alt="list"/>


---

60.What does `non-nullable` by default mean?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/no_null.png' alt="no_null"/>

---

61.`Expanded` vs `Flexible`?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/flex1.png' alt="flex1"/>

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/flex2.png' alt="flex2"/>


---

62.Why is `exit(0)` not preferred for closing an app?

<img src='https://github.com/power19942/flutter-interview-questions/blob/main/img/exit0.png' alt="exit0"/>

---

63.What is the difference between `main` function and the `runApp()` function in Flutter?

In Dart, main() acts as the entry point for the program whereas runApp() attaches the given widget to the screen.


---

64.What is `Dart` and why does Flutter use it?


Dart is AOT (Ahead Of Time) compiled to fast, predictable, native code, which allows almost all of Flutter to be written in Dart. This not only makes Flutter fast, virtually everything (including all the widgets) can be customized.

Dart can also be JIT (Just In Time) compiled for exceptionally fast development cycles and game-changing workflow (including Flutter’s popular sub-second stateful hot reload).

Dart makes it easier to create smooth animations and transitions that run at 60fps. Dart can do object allocation and garbage collection without locks. And like JavaScript, Dart avoids preemptive scheduling and shared memory (and thus locks). Because Flutter apps are compiled to native code, they do not require a slow bridge between realms (e.g., JavaScript to native). They also start up much faster.

Dart allows Flutter to avoid the need for a separate declarative layout language like JSX or XML, or separate visual interface builders, because Dart’s declarative, programmatic layout is easy to read and visualize. And with all the layout in one language and in one place, it is easy for Flutter to provide advanced tooling that makes layout a snap.

Developers have found that Dart is particularly easy to learn because it has features that are familiar to users of both static and dynamic languages

---

65.Where are the `layout` files? Why doesn’t Flutter have layout files?

In the Android framework, we separate an activity into layout and code. Because of this, we need to get references to views to work on them in Java. (Of course Kotlin lets you avoid that.) The layout file itself would be written in XML and consist of Views and ViewGroups.

Flutter uses a completely new approach where instead of Views, you use widgets. A View in Android was mostly an element of the layout, but in Flutter, a Widget is pretty much everything. Everything from a button to a layout structure is a widget. The advantage here is in customisability. Imagine a button in Android. It has attributes like text which lets you add text to the button. But a button in Flutter does not take a title as a string, but another widget. Meaning inside a button you can have text, an image, an icon and pretty much anything you can imagine without breaking layout constraints. This also lets you make customised widgets pretty easily whereas in Android making customised views is a rather difficult thing to do

---

66.What is the difference between `final` and `const` in Flutter?

`final` means single-assignment: A final variable or field must have an initializer. Once assigned a value, a final variable's value cannot be changed. final modifies variables.

`const` has a meaning that's a bit more complex and subtle in Dart. const modifies values. You can use it when creating collections, like const [1, 2, 3], and when constructing objects (instead of new) like const Point(2, 3). Here, const means that the object's entire deep state can be determined entirely at compile time and that the object will be frozen and completely immutable.

Const objects have a couple of interesting properties and restrictions:

They must be created from data that can be calculated at compile time. A const object does not have access to anything you would need to calculate at runtime. 1 + 2 is a valid const expression, but new DateTime.now() is not.

They are deeply, transitively immutable. If you have a final field containing a collection, that collection can still be mutable. If you have a const collection, everything in it must also be const, recursively.

They are canonicalized. This is sort of like string interning: for any given const value, a single const object will be created and re-used no matter how many times the const expression(s) are evaluated.

https://news.dartlang.org/2012/06/const-static-final-oh-my.html
