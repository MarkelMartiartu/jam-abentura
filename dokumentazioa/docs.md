## Garapenerako ingurunea
IDE gisa **Visual Studio Code** erabili dugu, web garapen esperientzia hobea izateko **Prettier** testu formateatzaile gehigarria, **Live Server** eta **Markdown**-erako gehigarriak erabili ditugu.

Datu basea diseinatzeko **Microsoft Access** programa erabili dugu.

Webgunea desplegatzeko **Nginx** zerbitzaria aukeratu dugu.

Mapa interaktiboa **Google Maps**-en egin dugu eta irudiak **GIMP**-en editatu.

Azkenik, **Trello** plataforma erabili dugu gure artean organizatzeko eta bertsio kontrolerako **Git** softwarea, errepositorioa **GitHub**-en hosteatuz.

## Webgunea

### Egitura
- Hasierako orria
  - Aurkezpen testua
  - Aktibitate kartak
  - Mapa interaktiboa
- Aktibitateen orriak
  1. Jarduera
       - Azalpena
       - Arauak
       - Prezioa
       - Bideoa edo/eta argazkiak
  2. Jarduera
       - ...
- Dokumentazioa
  - (Ikus. horri honen indizea)

### Nabigazio barra
![nav bar-a](argazkiak/nav.png "Title")
Nabigazio barra orri guztietan erakusten da.
Bertan klikatuz (Ezkerretik eskubira) orri nagusira, kontaktua atalera eta aktibitateen atalera birbidaltzen zaitu.

    .nav {
        position: fixed;
        top: 0;
        width: 100%;
    }

Posizio finko bat duen div bat besterik ez da.\
Barruko elementuak *unordered list* baten barruan sartzen ditugu eta irudiko "bloke" itxura ematen diogu:

    ul {
        list-style-type: none;
        margin: 0;
        padding: 0;
        overflow: hidden;
        background-color: #393548;
    }

### Kartak
![](argazkiak/kartak.png)

Kartak CSS-ko *grid* baten barruan doazen elementu klikagarriak dira.\
Lehenik eta behin *grid* klase hori sortu behar dugu:

    .cards {
        display: grid;

        grid-template-columns: repeat(4, 1fr);

        grid-auto-rows: auto;

        grid-gap: 1rem;
    }
Lau zutabeko sare bat sortu dugu eta *grid-auto-rows* propietatearen bidez elementu gehiago sartuz gero beste lerro batean joango dira kokatzen.

![](argazkiak/karta.png)
```
<div class="card" onclick="location.href='aktibitateak/parkea'">
    <img class="image" src="argazkiak/hartzak.jpg" />

    <div class="card-text">
        <b>Hartz Parkea. Abentura eta dibertsioa</b>
        <p>
            Hartzak, marmotak, ahuntzak, sarrioak,
        </p>

        <div class="center">
            <button class="button">
            <span>Erreserbatu</span>
            </button>
        </div>
    </div>
</div>
```
*Card* klaseak padding eta border batzuk besterik ez ditu.\
Karta bakoitzari *onClick()* funtzioarekin beste orrialde batera berbideratzeko agindua ematen diogu.\
Botoia berriz klase korapilotsuagoa da, animazioa daukalako

    .button {
        width: 240px;
        background: #46ad84;
        text-align: center;
        line-height: 45px;
        border-radius: 12px;
        color: #fff;
        cursor: pointer;
        font-weight: bold;
        border: none;
    }

    .button:hover {
        animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both;
        transform: translate3d(0, 0, 0);
        perspective: 1000px;
        }

        @keyframes shake {
        10%,
        90% {
            transform: translate3d(-1px, 0, 0);
        }
        20%,
        80% {
            transform: translate3d(2px, 0, 0);
        }
        30%,
        50%,
        70% {
            transform: translate3d(-4px, 0, 0);
        }
        40%,
        60% {
            transform: translate3d(4px, 0, 0);
        }
    }
Sagua gainetik pasatzerakoan hainbat transformazio egiten ditu, hau da, mugitu egiten da.

## Footer-a
![](argazkiak/footer.png)
Footerrean datuak eta ikonoak berriro ere grid batekin alineatu ditugu.\
Emailaren helbidea klikatuz gero momentuan mail bat bialtzeko aukera ematen du "mailto:" formatua erabili dugulako.\
Sare sozialetako ikonoak *FontAwesome* letra-tipotik datoz.

