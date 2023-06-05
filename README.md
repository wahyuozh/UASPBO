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

# CLASS NOTEPAD 
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
 # Create Menu File
 Pada kode ini menjelaskan proses pembuatan menu file yang mana pada menu file terdapat sub menu yaitu new, open, save. yang mana new itu membuat dengan kertas/ area baru. sedangkan open untuk membuka file, save untuk menyimpan file dalam bentuk txt. adapun code nya sebagai berikut. 
 
         def create_menu(self):
                Daftar_menu = Menu(self.window) # Membuat objek menu utama

                file_menu = Menu(Daftar_menu, tearoff=0) # Membuat menu file dengan submenu
                file_menu.add_command(label="New", command=self.new_file) # Menambahkan perintah "New" ke submenu file
                file_menu.add_command(label="Open", command=self.open_file) # Menambahkan perintah "Open" ke submenu file
                file_menu.add_command(label="Save", command=self.save_file) # Menambahkan perintah "Save" ke submenu file
                file_menu.add_separator() # Menambahkan pemisah ke submenu file
                Daftar_menu.add_cascade(label="File", menu=file_menu) # Menambahkan submenu file ke menu utama
                
   # Create Menu Edit
   Pada kode ini menjelaskan proses pembuatan menu untuk edit file yang mana pada menu ini terdapat sub menu cut untuk memotong teks, copy untuk mengcopy teks serta pase untuk me pastekan text yang di copy. adapun code nya sebagai berikut. 
   
       edit_menu = Menu(Daftar_menu, tearoff=0) # Membuat menu edit dengan submenu
            edit_menu.add_command(label="Cut", command=self.cut_text) # Menambahkan perintah "Cut" ke submenu edit
            edit_menu.add_command(label="Copy", command=self.copy_text) # Menambahkan perintah "Copy" ke submenu edit
            edit_menu.add_command(label="Paste", command=self.paste_text) # Menambahkan perintah "Paste" ke submenu edit
            Daftar_menu.add_cascade(label="Edit", menu=edit_menu) # Menambahkan submenu edit ke menu utama
   
   # Create Menu format 
   Pada bagian ini menjelaskan menu untuk membuat format tulisan nya yang mana tulisannya bisa diubah menjadi sesuai font yang kita mau sedangkan size nya juga sesuai dengan yang kita mau. dengan memasukan jenis font maka font dari tulisan akan berubah dengan memasukan angka size untuk font maka size nya akan berubah juga. 
   
    format_menu = Menu(Daftar_menu, tearoff=0)
        format_menu.add_command(label="Font", command=self.change_font)
        format_menu.add_command(label="Font Size", command=self.change_font_size)
        Daftar_menu.add_cascade(label="Format", menu=format_menu)
        
   # Create Menu Color
   pada bagian ini untuk membuat calor dari area tulisan. yang mana user akan bebas mengganti warna dari yang akan digunakan sesuai dengan keinginannya dan warna kesukaannya. 
   
    color_menu = Menu(Daftar_menu, tearoff=0) # Membuat menu warna dengan submenu
        color_menu.add_command(label="Change Color", command=self.change_color) # Menambahkan perintah "Change Color" ke submenu warna
        Daftar_menu.add_cascade(label="Color", menu=color_menu) # Menambahkan submenu warna ke menu utama
        
    # Create Menu Exit 
    Pada bagian ini untuk membuat menu yang menghasilkan keluar atau menutup program nya ketika di klik adapun code nya sebagai berikut. 
    
     Daftar_menu.add_cascade(label="Exit", command=self.window.quit) # Menambahkan perintah "Exit" ke menu utama
        self.window.config(menu=Daftar_menu) # Mengonfigurasi menu jendela dengan daftar menu yang telah dibuat
    
   
   
             
