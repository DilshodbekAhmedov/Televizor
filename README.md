class Telivezor(object):
        """Virtual televizor """
        def __init__(self):
                print("telivizor o'chgan.")
		
        def power_button(self, power = "off"):
                if power == "off":
                        power = "on"
                        print("hozir tv yoqilgan.")
                else:
                        power = "off"
                        print("hozir yv o'chgan.")
	
        def volume_button(self, volume = 0):
                up_or_down = input("Ovoz balandligini oshirish yoki kamaytirishni xohlaysizmi? (up/down): ")
                if up_or_down == "up":
                        amount = int(input("qanchaga? (sonini kiriting): "))
                        volume += amount
                        if volume > 10:
                                volume = 10
                        print("hozir ovoz bzlandligi",volume)
                elif up_or_down == "down":
                        amount = int(input("qanchaga? (sonni kiriting): "))
                        volume += amount
                        if volume < 0:
                                volume = 0
                        print("hozirda ovoz balandligi",volume)
                else:
                        print("Bu to'g'ri tanlov emas.")
	
        def channel_button(self, channel = 1):
                new_channel = int(input("qaysi kanalni ko'rishni xoxlaysiz? (kanal sonnini kiriting 1 va 10.): "))
                if new_channel < 1 or new_channel > 10:
                        print("Bu haqiqiy kanal emas!")
                else:
                        channel = new_channel
                        print("hozirgi kanalingiz",channel)


def main():
        tv = Telivezor()

        choice = None
        while choice != "0":
                print \
                ("""
                Telivizor
	
                0 - chiqish
                1 - Televizorni yoqish yoki o'chirish
                2 - Ovoz balandligini o'zgartirish
                3 - kanalni o'zgartirish'
                """)
	
                choice = input("Tanlang: ")
                print()
	
                #exit
                if choice == "0":
                        print("Xayr!")
		
                
                elif choice == "1":
                        tv.power_button()
	
                
                elif choice == "2":
                        tv.volume_button()
	
                
                elif choice == "3":
                        tv.channel_button()
		
                else:
                        print("\nXato tanlov!")

main()
