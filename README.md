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



