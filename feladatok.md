1. Az adott témának megfelelő SQL adatbázis megtervezése (legalább 5 tábla, minimum 3NF-ben legyen)

Az adatbazis egy autoiskola adatait tarolja,
Ez tartalmazza a diakok, oktatok es autok adatait es a vizsgak (gyakorlat es elso segely) reszleteit

    Logikai modell


    Fizikai modell
```js

CREATE TABLE [dbo].[Oktatok](
	[Oktaz] [nvarchar](255) PRIMARY KEY,
	[Nev] [nvarchar](255) NOT NUll, 
	[Email] [nvarchar](255) NOT NULL,
	[Kezd_Cim] [nvarchar](255) NOT NUll, 
	[Rendszam] [nvarchar](9) NOT NULL,
	[Oraber] [int] NOT NULL
 )
 
```








```js

CREATE TABLE [dbo].[Tanulok](
	[Tanaz] [nvarchar](255) PRIMARY KEY,
	[Nev] [nvarchar](255) NOT NUll, 
	[Email] [nvarchar](255) NOT NULL,
	[Telefonszam] [nvarchar](255) NOT NUll, 
	
	[Oktaz] [nvarchar](255) NOT NULL
 )
 

```







```js

CREATE TABLE [dbo].[Autok](
	[Rendszam] [nvarchar](9) PRIMARY KEY,
	[Tipus] [nvarchar](255) NOT NUll, 
	[Valto] [nvarchar](255) NOT NULL,
	[Vasarlas_Datuma] [date] NOT NUll, 
	[Megtett_út_(km)] [INT] NOT NULL
)
 
```










```js

CREATE TABLE [dbo].[Vizsga](
	[Vizsga_idopont] [date] PRIMARY Key,
	[Tanulo] [nvarchar](255) NOT NUll, 
	[Vizsga_tipus] [nvarchar](255) NOT NULL,
	[Valto] [nvarchar](255) NOT NUll, 
	[Utvonal] [int] NOT NULL,
	[Vizsgabiztos] [nvarchar](255) NOT NULL
 )
 

```





```js

CREATE TABLE [dbo].[Elso_Segely](
  	[KurzusAz] [int] PRIMARY KEy,
	[Terem] [nvarchar](255) NOT NULL,
	[Tanaz] [nvarchar](255) NOT NUll, 
	[Idopont] [date] NOT NULL,
	[Kurzus_Vizsga?] [nvarchar](4) NOT NUll
 )

```

Adat bevitel


```js

INSERT [dbo].[Oktatok] ([Oktaz], [Nev], [Email], [Kezd_Cim], [Rendszam], [Oraber]) VALUES (N'06104897818',	N'Ányos Jedlik ',	N'AJedlik1@gmail.com',	N'Vigadó tér 2, 1051 Budapest',	N'AAA  001', 7000)
INSERT [dbo].[Oktatok] ([Oktaz], [Nev], [Email], [Kezd_Cim], [Rendszam], [Oraber]) VALUES (N'06200300062', N'Kimi Schumacher ',	N'KSchumacher2000@freemail.com',	N'Hungaroring út 10., 2146 Mogyoród',	N'POX 777', 38000)
INSERT [dbo].[Oktatok] ([Oktaz], [Nev], [Email], [Kezd_Cim], [Rendszam], [Oraber]) VALUES (N'06302932268',	N'Termetes Titánia',	N'TerTi1986@gmail.com',	N'Fő u. 23, 1011 Budapest',	N'DF AW 154', 26000)
INSERT [dbo].[Oktatok] ([Oktaz], [Nev], [Email], [Kezd_Cim], [Rendszam], [Oraber]) VALUES (N'06509992227',	N'Buz Blurr ',	N'Colossusofroads@gmail.com',	N'Kerepesi út 2-4, 1087 Budapest',	N'SW AW 575', 10000)
INSERT [dbo].[Oktatok] ([Oktaz], [Nev], [Email], [Kezd_Cim], [Rendszam], [Oraber]) VALUES (N'06709643329',	N'Csiga Csenge ',	N'CsiCse@yahoomail.com',	N'Szépvölgyi út 15, 1037 Budapest',	N'GIF 988', 12500)


INSERT [dbo].[Autok] ([rendszam], [tipus], [valto], [vasarlas_datuma], [Megtett_út_(km)]) VALUES (N'AAA  001',	N'Doble Model E ',	N'Manualis',	'1950-01-13' ,100453)
INSERT [dbo].[Autok] ([rendszam], [tipus], [valto], [vasarlas_datuma], [Megtett_út_(km)]) VALUES (N'POX 777',	N'SF90 Stradale ',	N'Automata',    '2025-04-12' ,26)
INSERT [dbo].[Autok] ([rendszam], [tipus], [valto], [vasarlas_datuma], [Megtett_út_(km)]) VALUES (N'DF AW 154',	N'SCANIA Super',	N'Automata',    '2016-06-23' ,184811)
INSERT [dbo].[Autok] ([rendszam], [tipus], [valto], [vasarlas_datuma], [Megtett_út_(km)]) VALUES (N'SW AW 575',	N'FORD Escape ',	N'Manualis',    '2002-09-30' ,144811)
INSERT [dbo].[Autok] ([rendszam], [tipus], [valto], [vasarlas_datuma], [Megtett_út_(km)]) VALUES (N'GIF 988',	N'Skoda Kodiak ',	N'Manualis',    '2023-07-03' ,1524)

INSERT [dbo].[Tanulok] ([Tanaz], [Nev], [Email], [Telefonszam], [Oktaz]) VALUES (66153416,	N'Nagy Andras',	N'Nandras@gmail.com',    N'06102336651' , N'06200300062' )
INSERT [dbo].[Tanulok] ([Tanaz], [Nev], [Email], [Telefonszam], [Oktaz]) VALUES (61341661,	N'Kis Benedek',	N'Kbende@gmail.com',    N'06501534337 ' , N'06104897818' )
INSERT [dbo].[Tanulok] ([Tanaz], [Nev], [Email], [Telefonszam], [Oktaz]) VALUES (12131213,	N'Közepes Csilla',	N'Kozcsi@gmail.com',    N'06305509339 ' , N'06302932268' )
INSERT [dbo].[Tanulok] ([Tanaz], [Nev], [Email], [Telefonszam], [Oktaz]) VALUES (86112362,	N'Fék Dénes',	N'Denfekes@gmail.com',    N'06706689265 ' , N'06509992227 ' )
INSERT [dbo].[Tanulok] ([Tanaz], [Nev], [Email], [Telefonszam], [Oktaz]) VALUES (52436131,	N'Kuplung Éva',	N'kukueva@gmail.com',    N'06700239853 ' , N'06709643329' )

INSERT [dbo].[Vizsga] ([Vizsga_idopont], [Tanulo], [Vizsga_tipus], [Valto], [Utvonal], [vizsgabiztos]) VALUES ('2025-09-15', 66153416	,	N'B',    N'Manualis ' , 1, N'06302932268')
INSERT [dbo].[Vizsga] ([Vizsga_idopont], [Tanulo], [Vizsga_tipus], [Valto], [Utvonal], [vizsgabiztos]) VALUES ('2025-09-19', 61341661	,	N'B',    N'Automata ' , 5, N'06509992227 ')
INSERT [dbo].[Vizsga] ([Vizsga_idopont], [Tanulo], [Vizsga_tipus], [Valto], [Utvonal], [vizsgabiztos]) VALUES ('2025-09-23', 12131213	,	N'C1E',    N'Automata ' , 4, N'06709643329')
INSERT [dbo].[Vizsga] ([Vizsga_idopont], [Tanulo], [Vizsga_tipus], [Valto], [Utvonal], [vizsgabiztos]) VALUES ('2025-09-12', 86112362	,	N'BE',    N'Manualis ' , 9, N'06104897818')
INSERT [dbo].[Vizsga] ([Vizsga_idopont], [Tanulo], [Vizsga_tipus], [Valto], [Utvonal], [vizsgabiztos]) VALUES ('2025-09-02', 52436131	,	N'B',    N'Manualis ' , 7, N'06200300062 ')
INSERT [dbo].[Vizsga] ([Vizsga_idopont], [Tanulo], [Vizsga_tipus], [Valto], [Utvonal], [vizsgabiztos]) VALUES ('2025-05-14', 66153416	,	N'B',    N'Manualis ' , 4, N'06104897818')

INSERT [dbo].[Elso_Segely] ([KurzusAz], [Terem], [Tanaz], [Idopont], [Kurzus_Vizsga?]) VALUES (4561569, N'A1'	,52436131	,    '2025-08-12 ' , N'Igen')
INSERT [dbo].[Elso_Segely] ([KurzusAz], [Terem], [Tanaz], [Idopont], [Kurzus_Vizsga?]) VALUES (1523561, N'A2'	,66153416	,    '2025-08-02 ' , N'Nem')
INSERT [dbo].[Elso_Segely] ([KurzusAz], [Terem], [Tanaz], [Idopont], [Kurzus_Vizsga?]) VALUES (4561545, N'C1'	,86112362	,    '2025-08-27 ' , N'Igen')
INSERT [dbo].[Elso_Segely] ([KurzusAz], [Terem], [Tanaz], [Idopont], [Kurzus_Vizsga?]) VALUES (8744515, N'D1'	,61341661	,    '2025-08-19 ' , N'Igen')
INSERT [dbo].[Elso_Segely] ([KurzusAz], [Terem], [Tanaz], [Idopont], [Kurzus_Vizsga?]) VALUES (1516856, N'A3'	,12131213	,    '2025-08-05 ' , N'Nem')


```


    Az adatbázis feltöltése tesztadatokkal vagy adatok importálása


    Hasznos lekérdezések elkészítése, amelyek kihasználják a tanultakat (5-6 db)

Minden Tanulo es oktatojuknak az email cime

```js

SELECT t.Nev AS TanuloNev,
    t.Email AS TanuloEmail,
    o.Nev AS OktatoNev,
    o.Email AS OktatoEmail
FROM 
    Tanulok t
JOIN 
    Oktatok o ON t.Oktaz = o.Oktaz

```

Hany viszgat teljesitettek a tanulok

```js

SELECT t.Nev AS Tanulo_Nev,
    v.Vizsga_idopont,
    COUNT(*) OVER (PARTITION BY v.Tanulo) AS Vizsgak_szama,
	ROW_NUMBER() OVER (PARTITION BY v.Tanulo ORDER BY v.Vizsga_idopont) AS Hanyadik_vizsga
FROM Vizsga v
JOIN Tanulok t ON v.Tanulo = t.Tanaz
ORDER BY t.Nev, v.Vizsga_idopont


```

Ha a megtett ut tobb mint 11000 allitsak vissza az orat 11000re

```js

SELECT Rendszam,
    Tipus,
    [Megtett_út_(km)]
FROM 
    Autok 
UPDATE Autok SET [Megtett_út_(km)] = 11000
WHERE
	 [Megtett_út_(km)] > 11000




```

Melyik diakok teljesitettek az elso segelyt es hol?

```js

SELECT t.Nev AS TanuloNev,
    t.Email,
    e.Idopont,
    left(e.Terem, 1) as Emelet,
    right(e.Terem, 1) as Szoba
FROM 
    Tanulok t
JOIN 
    Elso_Segely e ON t.Tanaz = e.Tanaz
WHERE 
    e.[Kurzus_Vizsga?] = 'igen'

```

A vizsga elotti napon ertesitik a vizsgazot a vizsga korulmenyekrol


```js
SELECT DATEADD(DAY, -1, v.Vizsga_idopont) AS Vizsga_elotti_nap,
    t.Email,
    t.nev As Vizsgazo_neve,
    x.oktnev As Oktato_neve,
    x.Kezd_Cim as Vizsga_helyszine,
    x.Tipus as Vizsga_auto,
    v.Vizsga_tipus 
FROM 
    Tanulok t
JOIN 
    Vizsga v ON t.Tanaz = v.Tanulo
JOIN 
    (
        SELECT 
            t.Tanaz,
            t.Nev as tannev ,
            o.Nev As oktnev,
            o.Kezd_Cim,
            a.Rendszam,
            a.Tipus
        FROM 
            Tanulok t
        JOIN 
            Oktatok o ON t.Oktaz = o.Oktaz
        JOIN 
            Autok a ON a.Rendszam = o.Rendszam
    ) x 
    ON x.Tanaz = t.Tanaz
```

    Választható témák: személyi kölcsönök nyilvántartása, telefon előfizetések nyilvántartása, háziorvosi rendelő adatbázisa, labdarúgó bajnokság mérkőzéseinek nyilvántartása, autósiskola adatbázisa, többfordulós tehetségkutató verseny adatbázisa, fodrászüzlet adatbázisa, autókereskedő adatbázisa
    Beadandó: a modellek, az adatbázis leírása + az adatbázis és a lekérdezések kódja (.sql) GitHub repository-ba feltöltve (elég a repository linkjét megadni) + readme fájlban a csoporttagok neve
