# Add basecalling
`./dorado-0.9.1-linux-x64/bin/dorado basecaller sup,4mC_5mC,6mA /mnt/d/SCRACH/pod5/FAX50596_f8847863_ffa87fb4_0.pod5 > calls_0.bam` 
we ignore 5hmC like this seems either that or 4mc 5mc to try later **TODO** 
[2025-01-29 21:41:05.187] [info] cuda:0 using chunk size 12288, batch size 32  
[2025-01-29 21:41:06.016] [info] cuda:0 using chunk size 6144, batch size 32  
[2025-01-29 22:35:45.017] [info] > Finished in (ms): 3277831  
[2025-01-29 22:35:45.020] [info] > Simplex reads basecalled: 27888  
[2025-01-29 22:35:45.020] [info] > Simplex reads filtered: 47  
[2025-01-29 22:35:45.020] [info] > Basecalled @ Samples/s: 3.543277e+05  
[2025-01-29 22:35:45.218] [info] > Finished  
`samtools fastq -T "*" calls_0.bam  > calls_0.fq`  
okidoki  
`seqtk seq -L 1000 calls_0.fq > calls_0_lt_1000.fq`  
`seqkit seq calls_0.fq -m 100 -Q 10  > calls_0_m1000_q10.fq`
`hifiasm --ont calls_0_lt_1000.fq -t 4 -o TP1`  
AHHH FCKKKKK  
 `./dorado-0.9.1-linux-x64/bin/dorado basecaller sup,4mC_5mC,6mA /mnt/d/SCRACH/pod5/FAX50596_f8847863_ffa87fb4_1.pod5 > calls_1.bam` 
 [2025-01-30 10:46:04.046] [info] cuda:0 using chunk size 12288, batch size 32  
[2025-01-30 10:46:04.227] [info] cuda:0 using chunk size 6144, batch size 32  
[2025-01-30 11:44:54.389] [info] > Finished in (ms): 3529976  
[2025-01-30 11:44:54.390] [info] > Simplex reads basecalled: 28654  
[2025-01-30 11:44:54.390] [info] > Simplex reads filtered: 26  
[2025-01-30 11:44:54.390] [info] > Basecalled @ Samples/s: 7.162525e+05  
[2025-01-30 11:44:54.471] [info] > Finished  
`samtools fastq -T "*" calls_1.bam  > calls_1.fq`  
`seqkit seq calls_1.fq -m 100 -Q 14  > calls_1_m100_q14.fq`






 
