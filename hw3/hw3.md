# Task –  Process – Thread
Task : Bir değer döndürmeyen ve genelde asenkron olarak çalışan tek bir işlem olarak tanımlayabiliriz, ayrıca bir Taskin aynı anda birden fazla process’i olabilir.
	Task<Result> … return result
Thread : Thread(iş parçacığı) bir scheduler tarafından yönetilebilen en küçük komut dizisidir.Thread işletim sisteminin inşası ile ilgili bir konudur. Threadlerin aynı anda tek bir görevi olabilir.
Thread ve Process’i şuna benzetebiliriz thread = kol, process = parmaklar

Thread
```
int result = 0;
Thread thread = new System.Threading.Thread(() => { 
    result = 1; 
});
thread.Start();
thread.Join(); //Thread sonlanıncaya kadar thread’in çağrılmasını engeller. 
Console.WriteLine(result); // 1
```

Task
```
int result = await Task.Run(() => {
    return 1; 
});
Console.WriteLine(result); // 1
```

# Extension Metod
Extension metodlar bize .Net içerisinde yer alan metodlara yeni özellikler eklememize imkan sağlayan bir yapıdır.Extension metodlar static class içerisinde static olarak tanımlanması gerekmektedir.

String bir değeri int tipe nasıl dönüştürebiliriz ?
```
public static class ExtensionClass{
	public static int IntTurn(this String value){
		Return Int32.Parse(value);
	}
}	
```