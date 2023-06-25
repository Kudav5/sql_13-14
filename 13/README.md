## Latihan Praktikum
Buat query untuk menampilkan:
1. Departemen apa saja yang terlibat dalam tiap - tiap project

`select p.nama as perusahaan, d.nama as departemen, pr.nama as project from perusahaan p join departemen d on p.id_p = d.id_p join karyawan k on d.id_dept = k.id_dept join project_detail pd on k.nik = pd.nik join project pr on pd.id_proj = pr.id_proj order by pr.nama;`
![1](foto/1.png)

2. Jumlah karyawan tiap departemen yang bekerja pada tiap - tiap project

`select p.nama as perusahaan, d.nama as departemen, pr.nama as project, count(distinct k.nik) as jumlah_karyawan from perusahaan p join departemen d on p.id_p = d.id_p join karyawan k on d.id_dept = k.id_dept join project_detail pd on k.nik = pd.nik join project pr on pd.id_proj = pr.id_proj group by p.nama, d.nama, pr.nama order by pr.nama;`
![1](foto/2.png)

3. Ada berapa project yang sedang dikerjakan oleh departemen RnD ? (ket: project berjalan adalah yang status nya 1)

`select count(distinct pr.id_proj) as jumlah_project from project pr join project_detail pd on pr.id_proj = pd.id_proj join karyawan k on pd.nik = k.nik join departemen d on k.id_dept = d.id_dept where d.nama = 'RnD' and pr.status = 1;`
![1](foto/3.png)

4. Berapa banyak project yang sedang dikerjakan oleh Ari ?

`select count(distinct pr.id_proj) as jumlah_project from project pr join project_detail pd on pr.id_proj = pd.id_proj where pd.nik = 'N01' and pr.status = 1;`
![1](foto/4.png)

5. Siapa saja yang mengerjakan project B

`select k.nama from karyawan k join project_detail pd on k.nik = pd.nik join project pr on pd.id_proj = pr.id_proj where pr.nama = 'B';`
![1](foto/5.png)