using OgrenciBilgiSistemi;

public class Program
{
    public static void Main(string[] args)
    {
        /*
        0554 335 16 63 
            Ömer Kurt
        */

        List<Ogretmen> ogretmenList = new List<Ogretmen>();
        List<Ogrenci> ogrenciList = new ();
        OgretmenGetir(ogretmenList);
        OgrenciGetir(ogrenciList);

        int islem = 0;

        //kullanıcı 0 tuşuna basmadığı sürece sürekli işlemlerde dönecek
        do
        {
            Console.WriteLine("******İşlemler********");
            Console.WriteLine("1 Öğretmen Gir");
            Console.WriteLine("2 Öğreci Gir");
            Console.WriteLine("3 Öğretmen Girişi");

            Console.Write("İşlem Seç :");
            islem = Convert.ToInt32(Console.ReadLine());

    
            switch (islem)
            {
                case 1:
                    Ogretmen ogretmen = new Ogretmen();
                    ogretmen.BilgiGir();
                    ogretmenList.Add(ogretmen);
                    Console.Clear();
                    Console.WriteLine("Ekeleme başarılı");
                    break;

                case 2:
                    Ogrenci ogrenci = new Ogrenci();
                    ogrenci.BilgiGir();
                    ogrenciList.Add(ogrenci);
                    Console.Clear();
                    Console.WriteLine("Ekeleme başarılı");
                    break;

                case 3:
                    Console.Write("Sicil No : ");
                    string sicilNo = Console.ReadLine();
                    Console.Write("Şifre : ");
                    string sifre = Console.ReadLine();

                    Ogretmen girisYapanOgretmen = ogretmenList.FirstOrDefault(d => d.SicilNo == sicilNo && d.Sifre == sifre);

                    if(girisYapanOgretmen != null)
                    {
                        Console.Clear();
                        Console.WriteLine("Giriş başarılı");

                        int islem2 = 4;

                        do
                        {
                            Console.WriteLine("******Öğretmen İşlemleri********");
                            Console.WriteLine("1 Öğrenci Bul");
                            Console.WriteLine("2 Öğreci Not Gir");
                            Console.WriteLine("3 Sınıf Listele");
                            Console.WriteLine("4 Ana Menüye geri dön");

                            Console.Write("İşlem Seç :");
                            islem2 = Convert.ToInt32(Console.ReadLine());
                            switch (islem2)
                            {
                                case 1:
                                    Console.Write("Ad & Soyad : ");
                                    string deger = Console.ReadLine();

                                    var bulunaOgrenciList = ogrenciList.Where(d => d.Ad.Contains(deger) || d.Soyad.Contains(deger)).ToList();

                                    foreach (var item in bulunaOgrenciList)
                                    {
                                        item.BilgiYaz();
                                    }

                                    break;

                                default:
                                    break;
                            }

                        } while (islem2 != 4);



                    }
                    else
                    {
                        Console.Clear();
                        Console.WriteLine("Sicil No veya şifreniz hatalı");
                    }

                    break;
                default:
                    break;
            }





        } while (islem != 0);



    }


    public static void OgretmenGetir(List<Ogretmen> list)
    {
        Ogretmen ogretmen1 = new Ogretmen()
        {
            Ad = "Mustafa",
            Soyad = "Çavdaroğlu",
            Brans="Matematik",
            SicilNo="1",
            TCKN = 1,
            Sifre="12345"
            

        };
        list.Add(ogretmen1);

        Ogretmen ogretmen2 = new Ogretmen();
        ogretmen2.Ad = "Mehmet";
        ogretmen2.Soyad = "Çalışkan";
        ogretmen2.Brans = "Fizik";
        ogretmen2.SicilNo = "2";
        ogretmen2.TCKN = 2;
        ogretmen2.Sifre = "1234";
        list.Add(ogretmen2);

        list.Add(new Ogretmen() {Ad="Emel",Soyad="Tarık",Brans="Türkçe",SicilNo="3",Sifre="1234",TCKN=3});
    }


    public static void OgrenciGetir(List<Ogrenci> list)
    {
        list.Add(new Ogrenci("Öğrenci 1", "soyad 1", 1, "1", 4));
        list.Add(new Ogrenci("Öğrenci 2", "soyad 2", 2, "2", 4));
        list.Add(new Ogrenci("Öğrenci 3", "soyad 3", 3, "3", 4));
        list.Add(new Ogrenci("Öğrenci 4", "soyad 4", 4, "4", 4));
        list.Add(new Ogrenci("Öğrenci 5", "soyad 5", 5, "5", 4));
        list.Add(new Ogrenci("Öğrenci 6", "soyad 6", 6, "6", 4));
        list.Add(new Ogrenci("Öğrenci 7", "soyad 7", 7, "7", 4));
        list.Add(new Ogrenci("Öğrenci 1", "soyad 1", 1, "1", 5));
        list.Add(new Ogrenci("Öğrenci 2", "soyad 2", 2, "2", 5));
        list.Add(new Ogrenci("Öğrenci 3", "soyad 3", 3, "3", 5));
        list.Add(new Ogrenci("Öğrenci 4", "soyad 4", 4, "4", 5));
        list.Add(new Ogrenci("Öğrenci 5", "soyad 5", 5, "5", 5));
        list.Add(new Ogrenci("Öğrenci 6", "soyad 6", 6, "6", 5));
        list.Add(new Ogrenci("Öğrenci 7", "soyad 7", 7, "7", 5));


    }

}
