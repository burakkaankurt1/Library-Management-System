import time
class library:
    def __init__(self):
        self.file=open("books.txt", "a+")

        
    def list_books(self):
        self.file.seek(0)
        books = self.file.read().splitlines()
        for book in books:
            book_info = book.split(",")
            print(f"Kitap Adı: {book_info[0]}, Yazar Adı: {book_info[1]}")
        print("\n\n")
        time.sleep(2)
        return menu()  

    def add_book(self):
        book_title = input ("Kitap Ismi: ")
        book_author = input ("Yazar Ismi: ")
        first_release_year = input ("Yayınlanma Tarihi: ")
        number_of_pages = input ("Sayfa Sayisi: ")
        book_info = f"{book_title}, {book_author} , {first_release_year},{number_of_pages}\n"
        self.file.write(book_info)
        print(f"'{book_title}' isimli kitap arşive kaydedilmiştir.\n\n")
        time.sleep(2)
        return menu() 
    
    def remove_book(self):
        book_title = input("Silmek istediğini kitap ismi: ")
        self.file.seek(0)
        books = self.file.readlines()
        new_books = [book for book in books if book_title not in book]
        self.file.seek(0)
        self.file.truncate()
        self.file.writelines(new_books)
        print(f"'{book_title}' isimli kitap basari ile kutuphaneden kaldirilmistir.\n\n")
        time.sleep(2)
        return menu() 
    
library= library()



def menu():
    while True:
        print("Kitap eklemek için 1\nKitap silmek için 2\nTüm arşivi görmek için 3\nÇıkış yapmak için 4 tuşuna basınız")
        secim= input("Seçim: ")
        if int(secim) == 1:
            library.add_book()
        elif int(secim) == 2:
            library.remove_book()
        elif int(secim) == 3:
            library.list_books()
        elif int(secim) == 4:
            print("program kapatldı.")
            break
        else:
            print("Lütfen var olan değerler üzerinden bir seçim yapın\n\n")
            


menu()


