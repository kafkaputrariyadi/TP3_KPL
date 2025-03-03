using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace tpmodul3_2311104041
{
    using System;
    using System.Collections.Generic;

    namespace InformasiKelurahan
    {
        using System;
        using System.Collections.Generic;

        class KodePos
        {
            // Dictionary untuk menyimpan pasangan Kelurahan dan Kode Pos
            private static readonly Dictionary<string, string> dataKodePos = new Dictionary<string, string>
    {
        { "Batununggal", "40266" },
        { "Kujangsari", "40287" },
        { "Mengger", "40267" },
        { "Wates", "40256" },
        { "Cijaura", "40287" },
        { "Jatisari", "40286" },
        { "Margasari", "40286" },
        { "Sekejati", "40286" },
        { "Kebonwaru", "40272" },
        { "Maleer", "40274" },
        { "Samoja", "40273" }
    };

            // Method untuk mendapatkan kode pos berdasarkan nama kelurahan
            public static string GetKodePos(string kelurahan)
            {
                if (dataKodePos.TryGetValue(kelurahan, out string kodePos))
                {
                    return kodePos;
                }
                else
                {
                    return "Kode Pos tidak ditemukan";
                }
            }
        }

        // Class utama (Main)
        class Program
        {
            static void Main()
            {
                // Contoh pemanggilan method GetKodePos
                Console.WriteLine("Kode Pos Batununggal: " + KodePos.GetKodePos("Batununggal"));
                Console.WriteLine("Kode Pos Cijaura: " + KodePos.GetKodePos("Cijaura"));

                Console.WriteLine("Kode Pos Sekejati: " + KodePos.GetKodePos("Sekejati"));
                Console.WriteLine("Kode Pos Tidak Terdaftar: " + KodePos.GetKodePos("Kelurahan Fiktif"));
            }
        }
    }
}
