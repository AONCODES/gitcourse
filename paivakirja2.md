# Oppimispäiväkirja: Hajautettu git

__Mikä osion tehtävissä oli vaikeaa ja mikä helppoa? Mikä auttoi minua oppimaan? Miten selvitin esteet, jotka vaikuttivat tehtävän suorittamiseen?__

# Hajautettu Git

Aloitin tehtävän lukemalla materiaalia etärepositorioista ja samalla tehden kokeiluja komentirivillä.


## Etärepositorio
### Sanasto
Repositorio = Paikallinen oma tietovarasto.
Etärepositorio = Muut repot, joihin paikallisella repolla on yhteys. Esim githubissa kopiona
origin = Etärepositorion oletusnimi.

### Toiminta
Etärepositoriosta voi hakea tietoja (fetch) ja myös sinne voi viedä tietoja (push). Git fetch origin hakee etärepon tiedot paikalliseen repoon. Se tallettaa ne erikseen eikä suoraan muokkaa paikallisen repon haaroja. Git merge yhdistää ne haaraan. Nämä kaksi komentoa pystyy myös yhdistämään ja käyttämään vain komentoa git pull origin.

Git push origin master taas synkronoi paikallisen repon tiedot etärepositorioon. Origin komennossa on se repositorion nimi mihin tietoja viedään ja master on vietävän haaran nimi.

## Git-Hosting
Git-hostingilla tarkoitetaan git-palvelujen ja repositoriotilan tarjoamista verkossa. Yksi tunnetuimmista ja käytetyimmistä palveluistaon GitHub. 
-> Mahdollisuus suorittaa pieniä tai suuria projekteja.

Githubissa olevia etärepositorioita (projekteja) voidaan jakaa muille halutuin oikeuksin. Muilta voi saada sitten takaisin etärepositorion muutoksien kera.

Markdown-kieltä käytetään projektien dokumentointiin.

## Harjoitus 5

Kirjauduin GitHubiin ja tein uuden repositorion, nimeä ei pystynyt jättämään tyhjäksi joten laitoin repositorion nimeksi gitcourse.

Repositorio ehdotti quick-setup ohjeita ja komentorivi ehdotuksia.

Menin terminaliin ja yritin konfiguroida uuden repositorion paikallisen repon etärepoksi.

Komennolla: git remote add remote https://github.com/AONCODES/gitcourse

loin uuden etärepositorion jonka jälkeen tarkistin git remote -v komennolla menikö se läpi. Ilmeisesti meni koska näytti nämä komennot: remote	https://github.com/AONCODES/gitcourse (fetch)
remote	https://github.com/AONCODES/gitcourse (push)

Yritin puskea seuraavaksi originia master haaraan, mutta tuli fatal erroria että ei ole oikeuksia.

Ongelma selvisi, olin laittanu origin vahingossa "remote". Puskin remoten master haaraan, jonka jälknee tuli ongelmia kirjautumisen kanssa ja jotain tokeneita pitää olla, että tämä onnistuu (?). Selvitin tätä ja loin tokenin, ei onnistu vieläkään. (remote: Permission to AONCODES/gitcourse.git denied to AONCODES.
fatal: unable to access 'https://github.com/AONCODES/gitcourse/': The requested URL returned error: 403) 

Tämä selvisi sillä, että kun loin tokenin, niin olin kyllä valinnut oikean repositorion, mutta en ollut myöstänyt read and write oikeuksia.

Tämän jälkeen vaihdoin nimen komennolla git remote rename remote origin.

Nyt menin ohjeiden mukaisesti githubin verkkosivulle ja siellä näkyi nyt kaikki kansiot yms mitä olin aikaisemmin komentorivillä luonut.

Githubissa näkyi vain master -haara mutta komentorivillä paikallisella repositoriossa näkyy myös testin, feast123 yms muut haarat.

Tein uuden tiedoston "githubissatehty" ja kävin tämän jälkeen komentorivillä katsomassa oliko tämä tullut sinne -> ei ollut, joten hain ne komennolla git fetch.

Tämän jälkeen menin git checkout origin/master komennolla tilaan jossa pystyin katselemaan muutoksia, eli nyt löytyi myös se "githubissatehty" tiedosto.

Palasin Master haaraan, ja nyt taas luomani tiedosto oli "kadonnut" koska en koskaan tuonut sitä paikalliseen repositorioon. git status komento näytti vain git-oppismipäiväkirjan muutoksista (ainakin mielestäni..)

git merge origin/master komennolla toin githubissatehty tiedoston ja tämän jälkeen kokeilin taas git statusta, mutta ei siinä kyllä mitään muutoksia ole, samalta näyttää kun aikaisemminkin.

Tämän jälkeen lisäsin tunnisteen harjoitus5 ja tehtävä oli tehty.

## Osiossa käyttämäni Git-komennot

| git remote add | Lisää uuden etärepositorion paikalliseen repositorioon. git remote add remote https://github.com/AONCODES/gitcourse |.
| git push origin master | puskea origin etärepon masteriin |.
| git remote rename remote origin | vaihdoin nimeä |.
| git switch master/ paivakirja1| vaihdoin haaraa masteriin tai paivakirja1 tai 2 yms|
| git merge origin/master | yhdistin githubin tiedoston masteriin |
