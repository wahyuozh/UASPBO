# UASPBO

# ANGGOTA KELOMPOK 
1. WAHYU OZORAH MANURUNG
2. PANDU RIZKI MULYANTO
3. REKSI HENDRA PRATAMA

# PENJELASAN SOURCODE
-----------------------------------------------------------------------------------------------
# IMPORT
Pada bagian ini merupakan bagian module untuk membuat tkinter, yang mana berisikan library deng mengimpor semua dari tkinter


    from tkinter import *  # Mengimpor semua dari modul tkinter
    from tkinter.filedialog import asksaveasfile, askopenfile # Mengimpor fungsi asksaveasfile() dan askopenfile() dari modul filedialog
    from tkinter import colorchooser # Mengimpor modul colorchooser dari tkinter
    from tkinter import font as tkfont #mengimpor font sesuai demgam jemis 
    from tkinter import simpledialog #mengimpor untuk font

#CLASS NOTEPAD 
Pada bagian ini merupakan kode untuk membuat class notepad yang mana pertama membuat untuk window dengn amenyimpan jendela utama. selanjutnya menetapkan judul pada note pada dengan judul "notepad" dengan ukuram window yaitu sebebsar 1200*600 piksel selanjutnya membuat row denga configure nya yaitu 0 sebagai tat letak nya. kemudian membuat area teks dalam menulis kata katanya serata ada fungsi untuk membuat menu-menu yang menjadi bagian pada notepad

      class Notepad:
          def __init__(self, window): #Fungsi untuk window
              self.window = window # Menyimpan objek jendela utama
              self.window.title("MyNotepad") # Menetapkan judul jendela menjadi "Notepad"
              self.window.geometry("1200x600")  # Menetapkan ukuran jendela menjadi 1200x600 piksel

              window.rowconfigure(0, weight=1) # Mengkonfigurasi tata letak baris untuk mengisi ruang yang tersedia
              window.columnconfigure(0, weight=1) # Mengkonfigurasi tata letak kolom untuk mengisi ruang yang tersedia

              self.text_area = Text(self.window, wrap=WORD) # Membuat area teks dalam jendela dengan pembungkus kata
              self.text_area.pack(expand=True, fill=BOTH) # Mengemas area teks agar memanfaatkan seluruh ruang yang tersedia dalam jendela dalam membuat teks

              self.create_menu() # Membuat menu
