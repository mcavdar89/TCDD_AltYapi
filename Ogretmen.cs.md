# using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace OgrenciBilgiSistemi
{
    public class Ogretmen : Kisi
    {
       
        public string SicilNo { get; set; }
        public string Brans { get; set; }
        public string Sifre { get; set; }


        public override void BilgiGir()
        {
            base.BilgiGir();

            Console.Write("SicilNo : ");
            SicilNo = Console.ReadLine();

            Console.Write("Branş : ");
            Brans = Console.ReadLine();

            Console.Write("Şifre : ");
            Sifre = Console.ReadLine();
        }      



    }
}
