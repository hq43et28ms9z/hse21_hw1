# hse21_hw1
 Создание директории и создание ссылок на файлы
 
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

mkdir fastqc

ls *.fq | xargs -P 4 -tI{} fastqc -o fastqc {}

mkdir multiqc

multiqc -o multiqc fastqc 

Оценка platanusом

platanus_trim sub_R1.fq sub_R2.fq 

platanus_internal_trim mp_R1.fq mp_R2.fq

Удаление ненужных файлов/ссылок

rm R1_sub.fastq

rm R2_sub.fastq

rm MP1_sub.fastq

rm MP2_sub.fastq

rm -r oil_R1.fastq

rm -r oil_R2.fastq

rm -r oilMP_S4_L001_R1_001.fastq

rm -r oilMP_S4_L001_R2_001.fastq










