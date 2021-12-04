# hse21_hw1
 Создание директории и ссылок на файлы
 
     mkdir homework1
  
     cd homework1
  
     ln -s /usr/share/data-minor-bioinf/assembly/oil_R1.fastq
  
     ln -s /usr/share/data-minor-bioinf/assembly/oil_R2.fastq
  
     ln -s /usr/share/data-minor-bioinf/assembly/oilMP_S4_L001_R1_001.fastq
  
     ln -s /usr/share/data-minor-bioinf/assembly/oilMP_S4_L001_R2_001.fastq
  
 Случайные чтения

     seqtk sample -s725 oil_R1.fastq 5000000 > R1_sub.fastq

     seqtk sample -s725 oil_R2.fastq 5000000 > R2_sub.fastq

     seqtk sample -s725 oilMP_S4_L001_R1_001.fastq 1500000 > MP1_sub.fastq

     seqtk sample -s725 oilMP_S4_L001_R2_001.fastq 1500000 > MP2_sub.fastq

 Оценка качества исходных чтений
 
     mkdir fastqc

     ls *.fastq | xargs -P 4 -tI{} fastqc -o fastqc {}

     mkdir multiqc

     multiqc -o multiqc fastqc 

  ![mugteaff](https://user-images.githubusercontent.com/91056319/144723700-9d1ba8ff-2f85-489d-9a71-983757cb9d60.JPG)
  ![g,nioqrg,eiofrv](https://user-images.githubusercontent.com/91056319/144723738-dd203f86-85ef-4b65-ba98-696f551ed22c.JPG)
  ![likryutdukmjhn](https://user-images.githubusercontent.com/91056319/144723739-2af67ea2-32fe-45bb-b36c-5e7c8bfd8cd1.JPG)



Оценка platanusом

     platanus_trim R1_sub.fastq R2_sub.fastq 

     platanus_internal_trim MP1_sub.fastq MP2_sub.fastq
 
 ![reqsec](https://user-images.githubusercontent.com/91056319/144723403-b4d2cb0f-f261-4133-aa39-bae202c6c8db.JPG)

 ![reqsec2](https://user-images.githubusercontent.com/91056319/144723414-f812b5d5-1ad7-4493-8e63-a8f84f4e4093.JPG)


Удаление ненужных файлов/ссылок

     rm R1_sub.fastq

     rm R2_sub.fastq

     rm MP1_sub.fastq

     rm MP2_sub.fastq

     rm -r oil_R1.fastq

     rm -r oil_R2.fastq

     rm -r oilMP_S4_L001_R1_001.fastq

     rm -r oilMP_S4_L001_R2_001.fastq

Сборка контигов
     
     platanus assemble -f oil_R1_rnd.fastq.trimmed oil_R2_rnd.fastq.trimmed
![111111](https://user-images.githubusercontent.com/91056319/139144323-e7f02f18-717b-4e15-916b-c377a1cb4e34.JPG)
![2222222](https://user-images.githubusercontent.com/91056319/139144329-16f71c96-f4cf-4fe8-92c0-e56f3739c5fa.JPG)
![333333](https://user-images.githubusercontent.com/91056319/139144332-6dd7da80-7805-4e0a-87c1-24e0819252ce.JPG)





