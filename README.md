# hse_hw3_chromhmm

wgEncodeBroadHistoneNhaH2

wgEncodeBroadHistoneNhaH3k27me3

wgEncodeBroadHistoneNhaH3k36me3

wgEncodeBroadHistoneNhaH3k4me1

wgEncodeBroadHistoneNhaH3k04me2

wgEncodeBroadHistoneNhaH3k4me3

wgEncodeBroadHistoneNhaH3k79me2

wgEncodeBroadHistoneNhaH3k09ac

wgEncodeBroadHistoneNhaH3k09me3

wgEncodeBroadHistoneNhaH4k20me1

wgEncodeBroadHistoneNhaControl

Разбили геном на 10 сегментов.
Chromhmm основана на скрытых марковских цепях.

<p float="left">
 <img width="400" alt="Снимок экрана 2022-03-24 в 13 15 35" src="https://user-images.githubusercontent.com/91221560/160015329-044a8fe2-deae-4be5-bde6-b1ff375549eb.png">
 <img width="350" alt="Снимок экрана 2022-03-24 в 13 14 24" src="https://user-images.githubusercontent.com/91221560/160015275-0cbb0566-824e-4d9c-be62-98014390d557.png">
</p>

<table border="0">
<tr>
<td>Состояние 1</td>
<td> Есть переход в состояние 10. С наибольшой частотой гистоновая метка H3k27me3 и с наибольшей вероятностью (синий квадратик) это состояние находится в TES и в ядерной ламине. Можем предположить, что это гетерохроматин.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 2 </td>
<td> Есть переход в состояние 9. Для этого состояния нет характерных меток (все квадратики белые), однако видим, что как раз это состояние самое распростаненное в геноме и часто бывает в ядерной ламине. Так же скорее всего это гетерохроматин.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 3 </td>
<td> Характерная гистоновая метка - H3k9me3, это состояние чаще всего опять таки в ядерной ламине и  в TES, поэтому опять делаем вывод, что это гетерохроматин.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 4 </td>
<td> Есть переход в состояния 5, 7. Характерных нет как и в состоянии 2, это состояние чаще всего в генах и TES, возможно это ...</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 5 </td>
<td> Есть переход в состояния 4, 6, 9. Характерная гистоновая метка - H4k20me1, это состояние чаще всего в генах и TES, возможно это ...</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 6 </td>
<td> Есть переход в состояния 7, 8. Для этого состояния две характерные гистоновые метки - H4k20me1 и H3k79me2, чаще всего в генах, может быть это transcriptional transition.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 7 </td>
<td>Есть переход в состояния 5, 6. Характерная гистоновая метка - H3k79me2, чаще всего в генах, может быть это transcriptional transition.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 8 </td>
<td>Есть переход в состояние 10. Здесь много характерных гистновых меток - H4k20me1, H3k79me2, H3k4me1, H3k4me2, H3k9ac, H3k4me3; чаще всего в генах и TES  - предположительно энхансер.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 9 </td>
<td>Есть переход в состояния 2, 10. Характерны H3k4me1 и H3k4me2, а по расположению чаще всего в ядерной ламине, такие регионы обычно являются репрессированным гетерохроматином.</td>
</tr>
</table>

<table border="0">
<tr>
<td>Состояние 10 </td>
<td> Есть переход в состояния 2, 8. Характерны H3k4me2, H3k9ac, H3k4me3, H2az; данное состояние чаще всего на CpG-островках, экзонах и TSS (и то, которое 2kb), поэтому с уверенностью делаем вывод, что это активный промотер.</td>
</tr>
</table>
 
<img width="1000" alt="Снимок экрана 2022-03-24 в 23 15 20" src="https://user-images.githubusercontent.com/91221560/160011465-6a99e883-5ef3-4f07-a124-a0eabab21ab4.png">

<img width="1000" alt="Снимок экрана 2022-03-25 в 00 24 51" src="https://user-images.githubusercontent.com/91221560/160012920-08580e56-b34e-4920-9347-8907a940e1a5.png">

<img width="1000" alt="Снимок экрана 2022-03-25 в 00 51 18" src="https://user-images.githubusercontent.com/91221560/160016661-273a02d2-ce52-4622-896f-8ccf5b398a94.png">
