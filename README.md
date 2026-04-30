import re

print ("Merhaba! ben Türkgpt")
name = input("Peki ya senin ismin ne? ")
if name:
    print(f"Hoşgeldin {name}! Nasıl yardımcı olabilirim?")
    
    while True:
        user_input = input("Siz: ")
        
        # Veda mesajları
        if user_input.lower() in ["görüşürüz", "görüşmek üzere", "hoşça kal", "bye", "çıkış","bb", "exit","bay","bay bay","b" ]:
            print("Bot: Tamamdır dostum bidahakine göMÜŞELİM!")
            break
        
        # Durum soruları
        elif user_input.lower() in ["nasılsın", "naber", "ne haber", "ne var ne yok", "neler yapıyorsun", "ne yapıyorsun","iyimisin","","sen nasılsın" ]:
            print("Bot: İyiyim, teşekkür ederim! Sen nasılsın?")
        
        # İyi cevapları
        elif user_input.lower() in ["iyi", "çok iyi", "harika", "mükemmel", "süper", "güzel", "iyiyim", "iyi gidiyor","çok mutluyum","bende iyiyim"]:
            print("Bot: Ne güzel! Bana soracağın birşey var mı? mesela matematik işlemi yapabilirim.")
        
        # Diğer mesajlar
        else:
            matematik = re.findall(r"[0-9\+\-\*\/\.\(\)]+", user_input)

            if matematik:
                try:
                    ifade = "".join(matematik)
                    sonuc = eval (ifade)
                    print (f"Bot: sonuç = {sonuc}")
                except:
                     print ("Bot: okadar akıllı değilim pardon")
            else:
                print("Bot: Üzgünüm, okadar iyi bir bot değilim anlamadım.")


