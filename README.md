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

Оценка platanusом

     platanus_trim sub_R1.fq sub_R2.fq 

     platanus_internal_trim mp_R1.fq mp_R2.fq
![rqecec](https://user-images.githubusercontent.com/91056319/139139694-bc4f9e6d-93f2-420e-9729-2c7530cd02f1.JPG)

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





