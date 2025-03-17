def intro():
    print("Dedektiflik Ofisine Hoş Geldiniz!")
    print("Bir cinayet işlendi. Suç mahallindeki ipuçlarını kullanarak katili bulmanız gerekiyor.")
    print("Soru sorabilir, ipuçlarını inceleyebilir ve suçluyu suçlayabilirsiniz.")
    print("Ama dikkatli olun! Yanlış suçlama yaparsanız dava kapanır.\n")

def get_clue():
    clues = [
        "Bir fincan kahve masada soğumamış halde duruyor.",
        "Zemin üzerinde kanlı bir ayakkabı izi var.",
        "Katilin saati, olay yerine düşmüş gibi görünüyor.",
        "Kurbandan gelen bir kısa not bulunmuş: 'O biliyor...'"
    ]
    return clues

def interrogation():
    suspects = {
        "Ahmet": "Kurbandan borç almıştı ama borcunu ödeyeli çok oldu.",
        "Mehmet": "Olay sırasında şehir dışındaydı.",
        "Zeynep": "Kurbandan ayrılmıştı ama hala ona mektuplar yazıyordu.",
        "Leyla": "Kurbanın iş arkadaşıydı ve onun terfiini kıskanıyordu."
    }
    return suspects

def play_game():
    intro()
    
    clues = get_clue()
    suspects = interrogation()

    print("İpuçları:")
    for clue in clues:
        print(f"- {clue}")
    print("\nŞüpheliler:")
    for suspect, info in suspects.items():
        print(f"{suspect}: {info}")
    
    print("\nKimi suçlamalısınız?")
    choice = input("Şüpheli ismi girin: ").strip()
    
    if choice.lower() == "leyla":
        print("\nDoğru! Leyla suçluydu çünkü terfiyi kıskanıyordu ve olay yerinde onun saatine rastlandı.")
    else:
        print("\nYanlış tahmin! Dava kapandı.")
    
    print("Teşekkürler Dedektif, bir başka davada görüşmek üzere!")

play_game()
