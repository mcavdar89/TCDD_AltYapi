using System;
using System.Collections.Generic;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace OgrenciBilgiSistemi
{
    public abstract class Kisi
    {
        public string Ad { get; set; }
        public string Soyad { get; set; }
        public long TCKN { get; set; }


        public virtual void BilgiGir()
        {
            Console.Write("Ad : ");
            Ad = Console.ReadLine();
            Console.Write("Soyad : ");
            Soyad = Console.ReadLine();
            Console.Write("TCKn : ");
            TCKN = Convert.ToInt64(Console.ReadLine());


        }
        public void BilgiYazKisisel()
        {
            Console.WriteLine("* {0} {1} {2}",Ad,Soyad,TCKN);
        }
        public virtual void BilgiYaz()
        {
            Console.Write("* {0} {1} {2}", Ad, Soyad, TCKN);
        }

    }
}
