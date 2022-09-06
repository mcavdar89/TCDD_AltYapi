using System;
using System.Collections.Generic;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace OgrenciBilgiSistemi
{
    public class Ogrenci : Kisi
    {
        public Ogrenci()
        {

        }
        public Ogrenci(string ad,string soyad,long tckn,string ogrenciNo,int sinif)
        {
            this.Ad = ad;
            this.Soyad = soyad;
            this.OgrenciNo = ogrenciNo;
            this.Sinif = sinif;
            this.TCKN = tckn;
        }
        public string OgrenciNo { get; set; }
        public int Sinif { get; set; }
        public int MatematikNot { get; set; }
        public int FizikNot { get; set; }
        public int TurkceNot { get; set; }


        public override void BilgiGir()
        {
            base.BilgiGir();
            Console.Write("Öğrenci No : ");
            OgrenciNo = Console.ReadLine();
            Console.Write("Sınıf : ");
            Sinif = Convert.ToInt32(Console.ReadLine());

        }
        public override void BilgiYaz()
        {
            base.BilgiYaz();
            Console.WriteLine("Öğ No: {0} Sınıf : {1}", OgrenciNo,Sinif);
        }

    }
}
