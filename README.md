# epoch-odev
veri yapıları ve algoritmalar dersi ödevi

#include <stdio.h>
#include <time.h>

int main() {
    struct tm t1={0}, t2={0};  // İki tarih ve saat bilgisini saklayacak yapı
    time_t epoch1, epoch2;  // Epoch zamanlarını tutacak değişkenler
    
    int yil, ay, gun, saat, dakika, saniye;
    int yil2, ay2, gun2, saat2, dakika2, saniye2;
    
    printf("birinci tarihi gir (YYYY AA GG SS DD SS): ");
    scanf("%d %d %d %d %d %d",&yil,&ay,&gun,&saat,&dakika,&saniye);
    
    printf("ikinci tarihi gir (YYYY AA GG SS DD SS):");
    scanf("%d %d %d %d %d %d",&yil2,&ay2,&gun2,&saat2,&dakika2,&saniye2);
    
    t1.tm_year=yil;
    t1.tm_mon = ay;
    t1.tm_mday = gun;
    t1.tm_hour = saat;
    t1.tm_min = dakika;
    t1.tm_sec = saniye;

   t2.tm_year = yil2;
   t2.tm_mon = ay2;
   t2.tm_mday = gun2;
   t2.tm_hour = saat2;
   t2.tm_min = dakika2;
   t2.tm_sec = saniye2;

    yil -=1900;  // Yıl değerini tm_year formatına çevirmek için 1900 çıkarılır,Ay değeri 0'dan başladığı için 1 çıkarılır
    ay -=1;
    yil2 -=1900;
    ay2 -=1;
    
    epoch1 = mktime(&t1);  // Tarihleri epoch zamanına çevir
    epoch2 = mktime(&t2);
    
    printf("birinci tarih epoch; %ld\n ",epoch1);
    printf("ikinci tarih epoch; %ld\n ",epoch2);
    printf("iki tarih arasindaki fark ; %ld saniye\n",epoch2 - epoch1);
    
    
    
    
    
    return 0;
}
