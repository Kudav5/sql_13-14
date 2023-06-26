

`select*from karyawan where id_dept = (select id_dept from karyawan where nama = 'Dika');`

`select*from karyawan where gaji_pokok > (select avg(gaji_pokok) from karyawan) order by gaji_pokok descdesc;`

`select nik, nama from karyawan where id_dept in (select id_dept from karyawan where nama like '%k%');`

`select*from karyawan join departemen on karyawan.id_dept = departemen.id_dept where departemen.id_p = 'P01';`

`select distinct k1.nik, k1.nama from karyawan k1 join karyawan k2 on k1.id_dept = k2.id_dept where k1.gaji_pokok > (select avg(gaji_pokok) from karyawan where nama like '%k%');`