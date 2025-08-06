# Dokumentasi Sistem CRM

## 1. CRM USERS (`esti.crm`, `hilda.crm`, `rania.crm`)

### **Dashboard Harian**
- **Akses:** Menu utama untuk CRM users  
- **Fungsi:** Monitoring performa harian berdasarkan data kemarin  
- **Konten:**  
  - Total orders yang di-assign kemarin  
  - Total revenue dari orders **TERKIRIM**  
  - Statistik follow-up yang sudah completed  
  - Filter berdasarkan CRM name masing-masing  
- **Tujuan:** Evaluasi kinerja harian dan target completion  

### **CRM Follow-up**
- **Akses:** Menu kerja utama untuk melakukan follow-up  
- **Fungsi:** Menampilkan orders yang perlu di-follow-up  
- **Konten:**  
  - Orders kemarin (**created_date = yesterday**)  
  - Orders **TERKIRIM** yang bisa di-follow-up  
  - 3 jenis follow-up: **FU RESI, FU TERKIRIM, FU RO**  
  - Tombol WhatsApp dengan pesan otomatis  
- **Tujuan:** Eksekusi follow-up customer sesuai timeline  

### **TERKIRIM**
- **Akses:** Menu khusus untuk orders yang sudah dikirim  
- **Fungsi:** Fokus pada orders dengan status **TERKIRIM**  
- **Konten:**  
  - List orders **TERKIRIM** yang perlu **FU TERKIRIM**  
  - Quick access untuk follow-up orders yang sudah sampai  
- **Tujuan:** Prioritas follow-up customer yang sudah menerima barang  

---

## 2. ADMIN (`admin`)

### **Dashboard**
- **Akses:** Dashboard utama untuk monitoring keseluruhan  
- **Fungsi:** Overview performa sistem dan revenue  
- **Konten:**  
  - Total orders semua CRM  
  - Total revenue keseluruhan  
  - Chart dan statistik komprehensif  
  - Filter date range  
- **Tujuan:** Monitoring performa bisnis secara keseluruhan  

### **Dashboard Harian**
- **Akses:** Sama seperti CRM users tapi mencakup semua CRM  
- **Fungsi:** Monitoring harian semua tim  
- **Konten:** Data kemarin untuk semua CRM  
- **Tujuan:** Evaluasi performa tim harian  

### **Data View**
- **Akses:** Melihat raw data orders  
- **Fungsi:** Browse dan search semua orders  
- **Konten:**  
  - Semua orders dengan pagination  
  - Filter by CRM, status, date range  
  - Export capabilities  
- **Tujuan:** Analisis data detail dan audit  

### **CRM Follow-up**
- **Akses:** Sama seperti CRM users tapi bisa lihat semua CRM  
- **Fungsi:** Monitoring follow-up activities  
- **Konten:** Follow-up dari semua CRM  
- **Tujuan:** Supervisi aktivitas follow-up tim  

### **TERKIRIM**
- **Akses:** Orders **TERKIRIM** dari semua CRM  
- **Fungsi:** Monitor orders yang sudah dikirim  
- **Konten:** Semua orders **TERKIRIM**  
- **Tujuan:** Supervisi delivery dan customer satisfaction  

### **Detail Follow-up**
- **Akses:** Menu khusus admin untuk monitoring follow-up  
- **Fungsi:** Analisis detail aktivitas follow-up  
- **Konten:**  
  - Follow-up records kemarin saja  
  - Filter by CRM dan jenis follow-up  
  - Statistik: Total dan Completed follow-ups  
  - Customer detail modal dengan timeline  
- **Tujuan:** Evaluasi efektivitas follow-up dan kinerja CRM  

---

## 3. SUPERADMIN (`superadmin`)

Semua Menu Admin **+ Fungsi Tambahan**:

1. **User Management** – Buat, edit, hapus user accounts  
2. **Database Management** – Reset, cleanup, backup operations  
3. **System Configuration** – Ubah settings dan parameters  
4. **Advanced Analytics** – Deep dive analysis semua data  
5. **Data Migration** – Import/export data management  

**Khusus Superadmin:**  
- Full Database Access: Bisa akses semua data tanpa filter  
- System Administration: Restart services, manage workflows  
- Security Management: Role assignments, access control  
- Audit Trails: Complete logging dan activity monitoring  

---

## Timeline Follow-up Rules

### 1. FU RESI (Orders PENDING)
- **Tersedia:** Untuk orders dengan status **PENDING**  
- **Disabled:** Setelah 1 hari dari **created_date**  
- **Pesan:**  

### 2. FU TERKIRIM (Orders TERKIRIM)
- **Tersedia:** Segera saat status menjadi **TERKIRIM**  
- **Disabled:** Setelah 1 hari dari **complete_date**  
- **Pesan:**  

### 3. FU RO (Repeat Order)
- **Tersedia:** ((QTY * 7) - 2) hari dari **complete_date**  
- **Disabled:** Setelah 2 hari dari tanggal tersedia  
- **Pesan:**
