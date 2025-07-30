Langkah-Langkah Simulasi Git:

a. Kloning Repository:
git clone git remote add origin https://github.com/mamsky/operasi-dasar-Git-Konflik-Merge.git
cd nama-repo

b. Menambahkan Perubahan:
echo "Ini adalah konten awal dari sample.txt" > sample.txt
git add sample.txt

c. Commit Perubahan:
git commit -m "Menambahkan file sample.txt dengan konten awal"

d. Push Perubahan:
git checkout -b master
git push origin master

e. Simulasi Konflik Merge:

# Di branch A:

git checkout -b branchA
echo "Branch A: Konten awal yang diedit oleh Branch A" > conflict.txt
git add conflict.txt
git commit -m "Edit conflict.txt di branch A"

# Di branch B:

git checkout master
git checkout -b branchB
echo "Branch B: Konten berbeda yang diedit oleh Branch B" > conflict.txt
git add conflict.txt
git commit -m "Edit conflict.txt di branch B"

# Merge dan muncul konflik:

git checkout branchA
git merge branchB

# Edit manual conflict.txt untuk menyelesaikan konflik

git add conflict.txt
git commit -m "Menyelesaikan konflik merge antara branchA dan branchB"
