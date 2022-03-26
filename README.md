# hse_hw3_chromhmm

google colab: https://colab.research.google.com/drive/1hqAUsNBc0UD-PclQM4ocM1dLX9kc7p9o?usp=sharing

<table border="0">
<tr>
<td>H2AFZ</td>
<td>wgEncodeBroadHistoneNhaH2azAlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k27me3</td>
<td>wgEncodeBroadHistoneNhaH3k27me3StdAlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k36me3</td>
<td>wgEncodeBroadHistoneNhaH3k36me3StdAlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k4me1</td>
<td>wgEncodeBroadHistoneNhaH3k4me1StdAlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k04me2</td>
<td>wgEncodeBroadHistoneNhaH3k04me2AlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k4me3</td>
<td>wgEncodeBroadHistoneNhaH3k4me3StdAlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k79me2</td>
<td>wgEncodeBroadHistoneNhaH3k79me2AlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k09ac</td>
<td>wgEncodeBroadHistoneNhaH3k09acAlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H3k09me3</td>
<td>wgEncodeBroadHistoneNhaH3k09me3AlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>H4k20me1</td>
<td>wgEncodeBroadHistoneNhaH4k20me1AlnRep1.bam</td>
</tr>
</table>

<table border="0">
<tr>
<td>Control</td>
<td>wgEncodeBroadHistoneNhaControlStdAlnRep1.bam</td>
</tr>
</table>

Код для создания файла cellmarkfiletable.txt:

<img width="911" alt="Снимок экрана 2022-03-26 в 04 12 00" src="https://user-images.githubusercontent.com/91221560/160218774-f563eae6-8620-47c4-98b3-230c24800fe2.png">

ChromHMM с опцией LearnModel: 

!java -mx5000M -jar /content/ChromHMM/ChromHMM.jar LearnModel -b 200 /content/binarizedData/ /content/learnData 10 hg19

Разбили геном на 10 состояний.

Chromhmm основана на скрытых марковских цепях.

<p float="left">
 <img width="400" alt="Снимок экрана 2022-03-24 в 13 15 35" src="https://user-images.githubusercontent.com/91221560/160015329-044a8fe2-deae-4be5-bde6-b1ff375549eb.png">
 <img width="350" alt="Снимок экрана 2022-03-24 в 13 14 24" src="https://user-images.githubusercontent.com/91221560/160015275-0cbb0566-824e-4d9c-be62-98014390d557.png">
</p>

<table border="0">
<tr>
<td>Состояние 1</td>
<td> С наибольшой частотой гистоновая метка H3k27me3 и с наибольшей вероятностью (синий квадратик) это состояние находится в TES и в ядерной ламине. Можем предположить, что это гетерохроматин. По геномному браузеру видим, что есть переход в состояния 2 и 10.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 2 </td>
<td> Для этого состояния нет характерных меток (все квадратики белые), однако видим, что как раз это состояние самое распростаненное в геноме и часто бывает в ядерной ламине. Так же скорее всего это гетерохроматин. По геномному браузеру видим, что есть переход в состояние 9.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 3 </td>
<td> Характерная гистоновая метка - H3k9me3, это состояние чаще всего опять таки в ядерной ламине и в TES, поэтому опять делаем вывод, что это гетерохроматин.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 4 </td>
<td> Характерных меток нет как и в состоянии 2, это состояние чаще всего в генах и TES, может быть это transcriptional transition. По геномному браузеру видим, что есть переход в состояния 5, 7.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 5 </td>
<td> Характерная гистоновая метка - H4k20me1, это состояние чаще всего в генах (экзонах), TES. В статье Nature по chromhmm такому состоянию с большей вероятностью приписывается название Spliced exons. По геномному браузеру видим, что есть переход в состояния 4, 6, 9.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 6 </td>
<td> Для этого состояния две характерные гистоновые метки - H4k20me1 и H3k79me2, чаще всего в генах. В статье Nature по chromhmm такому состоянию с большей вероятностью приписывается название Transcribed. Из геномного браузера: есть переход в состояния 7, 8.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 7 </td>
<td>Характерная гистоновая метка - H3k79me2, чаще всего в генах. В статье Nature по chromhmm такому состоянию с большей вероятностью приписывается название Transcribed. Из геномного браузера: Есть переход в состояния 5, 6.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 8 </td>
<td>Здесь много характерных гистоновых меток - H4k20me1, H3k79me2, H3k4me1, H3k4me2, H3k9ac, H3k4me3; чаще всего в генах и TSS2kb  - скорее всего это промотор. По геномному браузеру видим, что это состояние как раз приходится на начало гена, что свидетельствует о том, что это действительно промотор. Есть переход в состояние 10. По таблице в статье Nature про chromhmm это вероятнее transcribed promotor.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 9 </td>
<td> Характерны H3k4me1 и H3k4me2, а по расположению чаще всего в ядерной ламине, такие регионы обычно являются репрессированным гетерохроматином. Есть переход в состояния 2, 10.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 10 </td>
<td> Характерны H3k4me2, H3k9ac, H3k4me3, H2az; данное состояние чаще всего на CpG-островках, экзонах и TSS (и то, которое 2kb), поэтому делаем вывод, что это активный промотор. По геномному браузеру видим, что это состояние приходится на начало гена. Есть переход в состояния 2, 8.</td>
</tr>
</table>
 
<img width="1000" alt="Снимок экрана 2022-03-24 в 23 15 20" src="https://user-images.githubusercontent.com/91221560/160011465-6a99e883-5ef3-4f07-a124-a0eabab21ab4.png">

<img width="1000" alt="Снимок экрана 2022-03-25 в 00 24 51" src="https://user-images.githubusercontent.com/91221560/160012920-08580e56-b34e-4920-9347-8907a940e1a5.png">

<img width="1000" alt="Снимок экрана 2022-03-25 в 00 51 18" src="https://user-images.githubusercontent.com/91221560/160016661-273a02d2-ce52-4622-896f-8ccf5b398a94.png">

# Бонус
<img width="1168" alt="Снимок экрана 2022-03-26 в 03 47 36" src="https://user-images.githubusercontent.com/91221560/160218033-399d6a4c-8372-4819-ba68-b8826cd15937.png">


<img width="825" alt="Снимок экрана 2022-03-26 в 03 50 16" src="https://user-images.githubusercontent.com/91221560/160218015-4089241a-ef96-41b3-ba1b-73540e7031c2.png">

