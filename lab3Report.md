# CSE 15L - Lab Report 3
## Researching the less command
To recap on what the `less` command allows us to do, it allows us to view the contents of a file by displaying a porition of the file on scrren and giving us the option to scroll using the up or down arrow keys. If we want to leave the view, we just hit q.

By doing some research and looking on the following websites: [https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/](https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/) and [https://linuxize.com/post/less-command-in-linux/](https://linuxize.com/post/less-command-in-linux/), we will talk about some of the `less` commands and use them on the `./written_2` directory from the skill demos:
- `less -N <file-name>` source: [https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/](https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/)
  - ```
    [cs15lwi23atn@ieng6-202]:skill-demo1-data:254$ less -N written_2/travel_guides/berlitz2/Bahamas-History.txt
      1
      2
      3
      4
      5 A Brief History
      6 Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the Luccucairi had settled in the Bahamas. Originally from South America, they had       6 e who called themselves the Luccucairi had settled in the Bahamas. Ord traveled up through the Caribbean t from sea and shore. Nothing in the experience of these gentle people       6 iginally from South America, they had traveled up through the Caribbeght from sea and shore. Nothing in tor on 12 October 1492. Columbus believed that he had reached the East I      6 an islands, surviving by cultivating modest crops and from what they  arrival of the Pinta, the Ni<C3>   e island and others in the Bahamas for his royal Spanish patrons, but n
      6 caught from sea and shore. Nothing in the experience of these gentle us believed that he had reached the Cuba.
      6 people could have prepared them for the arrival of the Pinta, the Ni today as the Lucayans. Columbus claileons frequently passed through the archipelago en route to and from th
      6 <C3><B1>a, and the Santa Maria at San Salvador on 12 October 1492. Cos, but not finding the gold and othe><A0><E2><80><94><C2><A0>at a spot now known as <E2><80><9C>Spanish Wel      6 lumbus believed that he had reached the East Indies and mistakenly catowards Cuba.                       s before they began the long journey back to Europe with their cargoes       6 lled these people Indians. We know them today as the Lucayans. Columb of shipwrecks attest that their gale removed from the Bahamas to work<C2><A0><E2><80><94><C2><A0>and die        6 us claimed the island and others in the Bahamas for his royal Spanishthe Caribbean, Florida, Bermuda, and Cuba, and elsewhere in the Caribbean.      6  patrons, but not finding the gold and other riches he was seeking, hC2><A0><E2><80><94><C2><A0>at a spoty. England<E2><80><99>s first formal move was on 30 October 1629, when       6 e stayed for only two weeks before sailing towards Cuba.             4><C2><A0>which was used to replenish. But nothing came of that, nor of a rival French move in 1633 when Ca
      7 The Spaniards never bothered to settle in the Bahamas, but the numberrney back to Europe with their cargo      7  of shipwrecks attest that their galleons frequently passed through tf them, perhaps some 30,000 people,       7 he archipelago en route to and from the Caribbean, Florida, Bermuda, die<C2><A0><E2><80><94><C2><A0>in Spablished the first permanent European settlement on the island they nam
      7 and their home ports. On Eleuthera the explorers dug a fresh-water wei), Cuba, and elsewhere in the Caribeutherian Adventurers, but life was very difficult and the colony never      7 ll<C2><A0><E2><80><94><C2><A0>at a spot now known as <E2><80><9C>Span                                    <99>s island) with a fine harbor was settled by Bermudians and renamed       7 ish Wells<E2><80><9D><C2><A0><E2><80><94><C2><A0>which was used to reamian islands during the 17th centur      7 plenish the supplies of water on their ships before they began the lon Charles I granted the Bahamas and 0 years their weak governors on New Providence either couldn<E2><80>         7 ng journey back to Europe with their cargoes of South American gold. lth. But nothing came of that, nor o countless raids against their ships, the Spanish dispatched a powerful
      7 As for the Lucayans, within 25 years all of them, perhaps some 30,000ry French statesman, tried claiming r Massachusetts, but didn<E2><80><99>t have much effect on the pirates.      7  people, were removed from the Bahamas to work<C2><A0><E2><80><94>                                       etter known as Blackbeard. Today you can visit a tower east of Nassau n
      7 <C2><A0>and die<C2><A0><E2><80><94><C2><A0>in Spanish gold mines and                                     dthirsty reputations and are still celebrated in the Bahamas. The pirat
      7 on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and elsewhee, sailed to Bahamian waters and esthy<C2><A0><E2><80><94><C2><A0>lives. Moreover, there was not always a c      7 re in the Caribbean.                                                 amed Eleutheria (now Eleuthera) afte plunder enemy ships during time of war. Anarchy and confusion reigned 
      8 English sea captains also came to know the beautiful but deserted BahEleutherian Adventurers, but life wa      8 amian islands during the 17th century. England<E2><80><99>s first forng honored for the effort. In 1666 a was named the first royal governor. Arriving in Nassau with a powerful      8 mal move was on 30 October 1629, when Charles I granted the Bahamas a was settled by Bermudians and renamtablishing some order. This incident inspired the national motto Expuls      8 nd a chunk of the American south to his Attorney General, Sir Robert  the Bahamas.                       mmerce Restored), which was retained until 1971.
      8 Health. But nothing came of that, nor of a rival French move in 1633 ands by Charles II, but for nearly 5ruptcy and debtor<E2><80><99>s prison in England. Before he died in Nas
      8 when Cardinal Richelieu, the 17th-century French statesman, tried cla
    ```  
  - ```
    [cs15lwi23atn@ieng6-202]:skill-demo1-data:255$ less -N written_2/travel_guides/berlitz2/Nepal-History.txt
      1
      2
      3
      4
      5 A Brief HistorY
      6 The early history of Nepal is a mixture of fact and myth; religious lore is associated with virtually every landmark and event. Actually, so intertwined are legend and history 
      6 that it is often impossible to determine where fact leaves off and legend begins. The prime example of this commingling of fact and fiction involves the origin of the Kathmandu      6  Valley.
      7 Legend holds that the Kathmandu Valley was once a vast lake, upon which floated a giant lotus flower, from which emanated the light of Swayambhu, the primordial Buddha. When th      7 e Tibetan god Manjushri came to view this light, he was unable to get close enough for a good look, so he took his great sword and slashed through the mountains surrounding the      7  valley to release the waters of the lake. (That is the myth. The fact, according to geologists, is that the Kathmandu Valley was indeed once a lake, though the valley<E2><80> 
      7 <99>s waters now drain through the narrow cleft of Chobar Gorge, which was most likely created by a large earthquake.)
      8 One side effect of Manjushri<E2><80><99>s draining of the lake was that the snake gods called Nagas, which lived in water, were left with no place to live. So, once again Manju      8 shri interceded and created a pond for them to live in. This pond still exists today not far from Chobar Gorge. However, elsewhere around Kathmandu, there are other stagnant po      8 nds from which rise statues of Nagas; these ponds, too, are dedicated to the snake gods.
      9 Unity and Fragmentation
     10 The Licchavi dynasty, of high-caste Hindu origin, ruled in the Kathmandu Valley from about a.d. 330 to 700. King Manadeva I (a.d. 462<E2><80><93>505) shook off the domination o     10 f the India Gupta emperors and extended his kingdom from the Kosi River in the east to the Gandaki River in the west and from the Terai to the Himalayan passes. A great king of     10  this line, Amsuvarna (609<E2><80><93>621), married his daughter Bhrikuti to the ruler of Tibet, Srongtsen Gampo. In 640, Bhrikuti and her Chinese co-wife converted Srongtsen G     10 ampo to Buddhism. Bhrikuti is venerated as the <E2><80><9C>Green Tara<E2><80><9D> and the Chinese wife as the <E2><80><9C>White Tara.<E2><80><9D> Their images are prominent in 
     10 Nepalese Buddhist art. Commercial and cultural links with Tibet, and through Tibet with China, were strengthened at this time.
     11 More reliable records come with the next major dynasty, the Malla, who were established in about 1200 by the strongman Ari Malla. The Malla came to Nepal in the first of severa     11 l waves of Hindu fugitives from the 11th-century Muslim invasion of northern India. Many of the refugees were nobles of the Chetri warrior caste from Rajasthan; forging new feu     11 dal states in Nepal, they were responsible for reinforcing Hinduism at the expense of Buddhism. The Kathmandu Valley itself was raided in 1336 by the Muslim Sultan of Bengal. I     11 n seven days he destroyed both Hindu and Buddhist temples and statues, including Swayambhunath and Pashupatinath. These great shrines were later rebuilt and expanded into their     11  present magnificence.
     12 The Malla period saw completion of Nepal<E2><80><99>s most important palaces, temples, and works of art. But Nepal and the Mallas became fragmented upon the death in 1482 of Ki     12 ng Yaksha Malla, who divided his lands amongst his heirs. For the next three centuries Nepal had three city-states side by side in the valley<C2><A0><E2><80><94><C2><A0>Kantipu     12 r (now known as Kathmandu), Lalitpur (now known as Patan), and Bhaktapur (also sometimes called Bhadgaon), along with their hinterlands.
     13 Unification
     14 Modern Nepalese history really begins with the arrival of a dynamic leader bent on unifying the country. Prithvi Narayan Shah, <E2><80><9C>The Great,<E2><80><9D> was born in 17     14 23, in the ninth generation of a line of Hindu princes of Gorkha, a hill town whose lands adjoined those of Kathmandu to the east. Like the Malla, the Shah princes had fled to 
     14 Nepal from Rajasthan rather than convert to Islam.
     15 Prithvi Narayan Shah captured Kathmandu and Patan in 1768 and Bhaktapur a year later. Before his death in 1775 he had brought under one rule all the territory from the Mahakali     15  River in the west to Sikkim and Darjeeling in the east. During the reign of his son, under a regent, the borders were pushed further north and west, provoking reactions from t     15 he Tibetans and Chinese as well as the British East India Company, the power to the south.
    ```
  - This command numbers each line of the file on the side when viewing the file. A line is determined by the seperation of a new line character so it is possible that one paragraph could be on one line number which is why you may see multiple of the same number on the side. The use of this command could be when wanting to refer to specific line numbers when working with others to communicate which parts of the file you are talking about.
- `less -p "search-term" <file-name>` source: [https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/](https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/)
  - ```
    [cs15lwi23atn@ieng6-202]:skill-demo1-data:266$ less -p "excluding wine" written_2/travel_guides/berlitz1/HandRIbiza.txt
        expect to pay for a three-course meal for two, excluding wine, tax and
        tip. Drinks will add considerably to the final bill.
        <E2><9C><AA>less than 5,000 ptas.
        <E2><9C><AA><E2><9C><AA>5,000<E2><80><93>8,000 ptas.
        <E2><9C><AA><E2><9C><AA><E2><9C><AA>more than 8,000 ptas.



    ``` 
  - ```
    [cs15lwi23atn@ieng6-202]:skill-demo1-data:268$ less -p "breakfast" written_2/travel_guides/berlitz1/HandRIstanbul.txt
        prices for a double room with bath, including breakfast:
        <E2><9D><81><E2><9D><81><E2><9D><81><E2><9D><81><E2><9D><81>over <C2><A3>130 ($200)
        <E2><9D><81><E2><9D><81><E2><9D><81><E2><9D><81><C2><A3>80<E2><80><93>130 ($120-200)
        <E2><9D><81><E2><9D><81><E2><9D><81><C2><A3>50<E2><80><93>80 ($75-120)
        <E2><9D><81><E2><9D><81><C2><A3>30<E2><80><93>50 ($45-75)
        <E2><9D><81>below <C2><A3>30 ($45



    ```
  - This command allows us to search a file for the given string and open up the file on the line that string is on. It will put you on the first instance of that string but will highlight all instances of the string within the file upon opening. This command can be useful in bookmarking where you left off in reading a file if you remeber a specific phrase or piece of text. It could also be useful in seeing where all the instances of a string could be in a file if you misspelled a word in the file and had to go search for all the misspellings.
- `less <file-name1> <file-name2>` source: [https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/](https://www.howtogeek.com/444233/how-to-use-the-less-command-on-linux/)
  - ```
    [cs15lwi23atn@ieng6-202]:skill-demo1-data:297$ less written_2/travel_guides/berlitz1/HandRIbiza.txt written_2/travel_guides/berlitz1/HandRIstanbul.txt
        Recommended Hotels
        The establishments listed below offer a cross-section of
        local restaurants, and should convince you that not everything on the
        island comes with chips (french fries).
        The star rating in brackets after each entry refers to the
        offfical government rating system.
        As a basic guide, the symbols we use indicate what you can
        expect to pay for a three-course meal for two, excluding wine, tax and
        tip. Drinks will add considerably to the final bill.
        <E2><9C><AA>less than 5,000 ptas.
        <E2><9C><AA><E2><9C><AA>5,000<E2><80><93>8,000 ptas.
        <E2><9C><AA><E2><9C><AA><E2><9C><AA>more than 8,000 ptas.



    written_2/travel_guides/berlitz1/HandRIbiza.txt (file 1 of 2) (END) - Next: written_2/travel_guides/berlitz1/HandRIstanbul.txt
    ```
  - Hitting `:n` on the previous example before
    ```
        Recommended Hotels
        Finding accommodation in Istanbul is rarely a problem, as
        the city has recently seen a boom in the hotel business. However, if        
        you want a room in a particular hotel, it is best to book, especially       
        during July and August. The main hotel areas are Laleli, Aksaray, and       
        Sultanahmet in the Old City, and around Taksim Square in Beyo<E2><80><98>lu.
        Intense competition among the middle-range hotels means that you can        
        often bargain for a lower rate, especially if you plan to stay for more     
        than two nights.
        As a basic guide we have used the symbols below to indicate
        prices for a double room with bath, including breakfast:
        <E2><9D><81><E2><9D><81><E2><9D><81><E2><9D><81><E2><9D><81>over <C2><A3>130 ($200)
        <E2><9D><81><E2><9D><81><E2><9D><81><E2><9D><81><C2><A3>80<E2><80><93>130 ($120-200)
        <E2><9D><81><E2><9D><81><E2><9D><81><C2><A3>50<E2><80><93>80 ($75-120)
        <E2><9D><81><E2><9D><81><C2><A3>30<E2><80><93>50 ($45-75)
        <E2><9D><81>below <C2><A3>30 ($45)



    ~
    ~
    ~
    ~
    ~
    ~
    ~
    ~
    ~
    ~
    ~
    ~
    written_2/travel_guides/berlitz1/HandRIstanbul.txt (file 2 of 2) (END)
    ```
  - You can open up multiple files with less using the above command. To go to the next file from the first use `:n` and to go back to the first file use `:p`. This can be useful when you want to quickly cross reference two files. Let's say you are writting a paper in one file and referring to facts in another file. By using less on both files you can quickly switch between them without having to exit and re-run less on the other file.
- `less -X <file-name>` source: [https://linuxize.com/post/less-command-in-linux/](https://linuxize.com/post/less-command-in-linux/)
  - ```
    [cs15lwi23atn@ieng6-202]:skill-demo1-data:304$ less -X  written_2/travel_guides/berlitz2/PuertoRico-History.txt
    A Brief history
    The First Puerto Ricans
    The island<E2><80><99>s earliest known inhabitants, Indians now called Arca<C3><AD>cos (<E2><80><9C>the ancients<E2><80><9D>), were primitive fishermen. More than 2,000 years ago they were conquered by another tribe called the Igneri who had mastered farming and potterymaking. The final stage of Indian advancement began while Europe was in the Middle Ages: the Ta<C3><AD>no Indians, a peaceful people native to Venezuela, traveled up through the chain of the Lesser Antilles and settled the island they called Borinqu<C3><A9>n. They lived in thatched houses, hunted and farmed, and worked ceramics and textiles with great skill. Several of their ceremonial <E2><80><9C>ball courts,<E2><80><9D> which were used for certain social or religious gatherings, have been discovered throughout Puerto Rico. The Ta<C3><AD>nos feared an evil spirit, Jurac<C3><A1>n, who was responsible for violent storms and gave his name to the tropical hurricanes of the West Indies. They also feared an earthly evil: the Carib Indians, who periodically raided their land for loot and captives. The Ta<C3><AD>nos<E2><80><99> fears were well founded. The word <E2><80><9C>cannibal<E2><80><9D> derives from Carib, a reminder of the way these marauders disposed of some prisoners.
    The Arrival of the Europeans
    On 19 November 1493, Columbus was lucky enough to be met by the kindly Ta<C3><AD>nos (in fact, the name Ta<C3><AD>no meant <E2><80><9C>friend<E2><80><9D> and was used by the Indians to enable the Europeans to distinguish between them and the not-so-friendly Caribs). The Ta<C3><AD>nos were the ones who introduced the Spanish to tobacco, corn on the cob, and that archetypal Caribbean mode of relaxation, the hammock.
    Columbus christened the island San Juan Bautista (honoring St. John the Baptist). It was the first colonist, Juan Ponce de Le<C3><B3>n, who, admiring a bay on the north coast, declared it Puerto Rico (<E2><80><9C>rich port<E2><80><9D>). Sixteenth-century mapmakers back in Spain mistakenly confused the names, so that in the end the port became San Juan and the whole island was called a <E2><80><9C>rich port<E2><80><9D>; once on the maps, the names stuck.
    A less innocent error was an American attempt to erase four centuries of Spanish history. After the conquest of 1898 the first US military governor ordered that the name be spelled Porto Rico. This semi-Italian corruption didn<E2><80><99>t last long. Today some nationalists still yearn for good old Borinqu<C3><A9>n, a name you<E2><80><99>ll see on many restaurants and bars.
    Ponce de Le<C3><B3>n had received permission to found a Spanish colony on the island in 1508. For reasons of security, he settled a few miles inland from what is now San Juan. The site was swampy and mosquito-ridden, and, after a number of outbreaks of disease, his fellow colonists abandoned him and moved to the future capital city. They immediately began work on the formidable fortifications for which the city is still famous. Ponce de Le<C3><B3>n also suffered another setback. He became involved in a power struggle with Columbus<E2><80><99>s son, Diego, who through his father<E2><80><99>s will had claims on the island. The small colony could not cope with the egos of two such powerful men. The Spanish crown solved the tense standoff by entrusting Ponce de Le<C3><B3>n with another voyage of exploration. His search resulted in the discovery of Florida. While on a second expedition to colonize Florida, in 1521, Ponce de Le<C3><B3>n was critically wounded during an attack by Indians; the explorer hoped to return Puerto Rico but lost his fight for life on the way back, in Havana, Cuba.
    Ponce de Le<C3><B3>n<E2><80><99>s successors imagined that the island was one big gold mine and set the Indians to work mining and panning. They were wrong, however: the gold soon ran out. The Spaniards then looked to agriculture to turn a profit and began growing sugar cane, which had been introduced to the Caribbean on Columbus<E2><80><99>s second journey. As the number of Ta<C3><AD>no and Carib laborers declined, due to disease and suicide, plantation owners eventually began importing slaves from West Africa.
    Puerto Rico quickly developed into a major port and trading post<C2><A0><E2><80><94><C2><A0>it was one of the last major ports Spanish galleons stopped in before sailing back to the motherland. San Juan also became the center for the Catholic Church<E2><80><99>s evangelization of the New World; numerous churches, convents, and monasteries were established throughout the island to aid in this effort.
    A Beleaguered Island
    To the pirates and privateers who sailed the Caribbean in the early 16th century, the fortress of El Morro at San Juan represented the might, and the wealth, of the Spanish Crown. Lured by the promise of treasure galleons and stores of ammunition, some pirates worked independently; others, however, were employed by the various European crowns, particularly the British, to help carry on their power struggles in the colonial world. Puerto Rico suffered from constant attacks. The most poignant, though not typical, case involved raids against the coastal hamlet of San Germ<C3><A1>n. Two French pirate ships first ravaged the village in 1528. It happened again in 1538 and three times in the following five years. After every attack the settlers put out the fires, buried the dead, and rebuilt San Germ<C3><A1>n. In 1554, after the sixth sacking, the settlers decided to move inland to the town<E2><80><99>s present hilltop location. With remarkable persistence the pirates 

    [cs15lwi23atn@ieng6-202]:skill-demo1-data:305$
    ```
  - ```
    [cs15lwi23atn@ieng6-202]:skill-demo1-data:310$ less -X  written_2/travel_guides/berlitz2/Cuba-History.txt
    A Brief History
    When Christopher Columbus disembarked on eastern Cuba on 27 October 1492, he quickly penned a note exclaiming that the land was <E2><80><9C>the most lovely that eyes have ever seen.<E2><80><9D> Indian tribes including the Siboney from Central and South America had lived on the island since at least 1000 b.c.
    In 1511 Diego de Vel<C3><A1>zquez sailed from neighboring Hispaniola with some 300 conquistadores (conquerors). Baracoa became the first of seven settlements across Cuba. Vel<C3><A1>zquez and his followers enslaved the native peoples and in the process exposed them to European diseases. Whole villages committed suicide, and by the mid-1500s the Indian population had declined from over 100,000 to 3,000.
    Piracy and Trade
    Until the end of the 16th century, Cuba remained a fairly insignificant Spanish colony. The port cities Havana and Santiago de Cuba were heavily fortified to defend against French and English pirate raids. Considerable contraband trade originated from bases around the island.
    In 1762 British forces captured Havana. They held it for only a year before returning it to Spain in exchange for Florida, but during this period trade was opened up to additional markets, notably the North American colonies. A lucrative tobacco industry had taken hold in Cuba, and after 1763 the sugar-cane business skyrocketed. Though settlers brought the first African slaves to Cuba in the early 1500s, hundreds of thousands of African laborers were imported in the late 18th century to meet the demands of the sugar industry.
    By the middle of the 19th century, Cuba produced a third of the world<E2><80><99>s sugar and was considered one of the most valuable colonies in the world. Half a million slaves<C2><A0><E2><80><94><C2><A0>nearly half the population<C2><A0><E2> 
    <80><94><C2><A0>worked the plantations, and at least 3,500 trading ships visited Cuba annually.
    The Road to Independence
    Spaniards born and raised in Cuba, known as criollos (creoles), managed the sugar-cane plantations but were not involved in the running of the country. During the 19th century some criollos (particularly in Oriente, the island<E2><80><99>s poorer, eastern region) became increasingly disenchanted and desired greater autonomy.
    On 10 October 1868 Carlos Manuel de C<C3><A9>spedes, a criollo plantation owner who had already had a brief role in uprisings in Spain, issued a call for independence and liberated slaves from his estate, La Demajagua. During the subsequent Ten Years<E2><80><99> War (1868<E2><80><93>78) 50,000 Cubans<C2><A0><E2><80><94><C2><A0>including C<C3><A9>spedes<C2><A0><E2><80><94><C2><A0>and more than 200,000 Spanish lost their lives. Cuba remained a colony of Spain, but the war contributed to the abolition of slavery on the island in 1886 and planted the seeds of a national consciousness.
    In 1895 Jos<C3><A9> Mart<C3><AD>, Cuba<E2><80><99>s most venerated patriot (who now has a street, square, or building named after him in every town), led the next and most important uprising against Spain. Born in 1853 and exiled at 18 for his 
    political views, Mart<C3><AD> became a journalist and poet. From exile in the United States he argued for Cuban independence. Mart<C3><AD> was killed in an ambush during the War of Independence, which began in 1895 and in which some 300,000 Cubans died.
    Throughout the 19th century, the United States, keenly interested in the island<E2><80><99>s strategic significance and its sugar market, had become increasingly involved in Cuban affairs. A US purchase of the island from Spain had long been on the agenda, even though Mart<C3><AD> had warned of becoming a satellite of the United States (<E2><80><9C>I know the Monster, because I have lived in its lair,<E2><80><9D> he wrote).
    In February 1898 the U.S.S. Maine was sunk in Havana<E2><80><99>s harbor, killing all 260 crew members. Although Spanish responsibility was never incontrovertibly established, the United States used the sinking as a pretext to declare war. US victory came swiftly, with Spain surrendering claim to the island by the end of the same year. A provisional military government lasted to 1902, when Cuba became an independent republic.
    False Independence
    For the next five decades the United States, the largest importer of Cuban sugar, dominated the island<E2><80><99>s economy and largely controlled its political processes. The period was rife with political corruption, violence, and terrorism. 
    After 1933 Fulgencio Batista, though only a sergeant, orchestrated the strings of power through a series of puppet presidents before winning the presidency outright in 1940. He retired in 1944 but returned by staging a military coup in 1952. His venal dictatorship made it possible for him to invest some $300 million abroad by 1959.

    [cs15lwi23atn@ieng6-202]:skill-demo1-data:311$
    ``` 
  - This command keeps leaves the last page displayed from the file on the screen after exiting `less`. This can be useful if you have certain terms or commands in the file you were looking at that you would then want to run in the command line. This helps if you forgot what file you were looking at or what the contents of the file were and need a specific reference right away. 
