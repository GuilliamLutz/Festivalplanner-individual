# Festivalplanner-individual
This reposiroty includes a markdown file in wich I note down my process of my project in year 1 period 3 of my education thecnical computing science

## Projectweek 2

**Situatie**

In week 2 moesten wij gaan beginnen aan het coderen van de agendamodule. We hebben in week 1 hiervoor een ontwerp gemaakt en een projectkeuze. We vonden het eerste ontwerp alleen niet van genoeg kwaliteit. Daarom hebben we besloten om het te verbeteren. Deze taak hebben Grant en ik op ons genomen. 

**Keuzemogelijkheden**

Tijdens het ontwerpen van de agendamodule hadden Grant en ik al snel de vraag wat nou precies mooi is en gewild. En niet alleen voor onszelf maar ook de groep. We vroegen ons af of wij het met zijn 2e moesten ontwerpen of dat we de vraag stellen aan iedereen om een eigen ontwerp te maken en later alles ontwerpen samen te voegen zodat het van iedereen wat heeft. 

Keuze 1: Met 2 man het hele ontwerp maken voor de groep.
Keuze 2: Iedereen een eigen ontwerp laten maken en later een gezamenlijk ontwerp maken.

**Mijn keuze**

Op het moment zelf heb ik er voor gekozen om de vraag aan de groep te stellen om allen zelf een ontwerp te maken en die later samen te voegen.

**Keuzemotivatie**

Ik vond dit zelf een betere keuze op dat moment. Grant en ik hadden namelijk een hele andere gedachten merkte we al snel en daardoor dacht ik dat dit ook bij de andere voor zou komen. Ik vond het dus beter om allemaal een eigen "visie" te creëren en die dan bij een te leggen en zo een gezamelijk design te maken.

### Mijn bijdrage

Ik heb in week 2 van het project in samenwerking met Grant een design gemaakt voor de GUI. Wij zijn samen gaan zitten via Discord en hebben scherm gedeeld via Grant. Toen hebben we wat ideeën met elkaar uitgewisseld, al gauw kwamen we op de gedachte om een modern design te maken voor de applicatie. We hebben hiervoor dus enige voorbeelden op internet opgezocht en aan de hand daarvan een deel van het ontwerp gecreëerd. We bedachten ons alleen of het niet misschien leuk is als iedereen een ontwerp maakt. Daardoor hebben we aan de groep gevraagd dus om zelf een ontwerp te creëren. Vervolgens ben ik dus ook een ontwerp gaan creëren zoals ik het voor me zag.

![Artist Design](https://i.gyazo.com/8f103a1a4a85baef67c3754ff6b2ddab.png)

![Stage Design](https://i.gyazo.com/70087955aba04048ca69701e1678a28e.png)

![Main view](https://i.gyazo.com/f076ea007effae572c73a082be8c36d9.png)

## Projectweek 3

**Situatie** 

In de 3e projectweek zijn wij als groep aan de slag geweest met het coderen van de agendamodule. We hadden hier verschillende taken in 2 man was verantwoordelijk voor het programmeren van de logica, 2 man voor de planningview die met 2D-Graphics werd gemaakt en 2 man die de algehele GUI ging maken dus alle knoppen en velden. Deze taak was opgegeven aan Davy en mij. In eerste instantie zijn Davy en ik de GUI gaan maken met scenebuilder, dit deden we omdat Davy hiermee wist te werken en het naar onze mening sneller en beter kon via dit systeem. Later werd alleen door een paar leden bevonden dat ze toch liever op de standaard JavaFX manier de GUI wouden opbouwen.

**Keuzemogelijkheden**

Na de opmerking van de leden die aangaven dat ze liever JavaFX gebruikte hadden Davy en ik de keuze om door te gaan met scenebuilder of om na overleg over te stappen naar JavaFX en op die manier de GUi te maken. 

**Mijn keuze**

Ik heb er voor besloten om aan iedereen van de groep te vragen wat zij het liefst zouden zien dat gebruikt wordt om de GUI te maken.

**Keuzemotivatie**

Ik vond dit de meest verstandige optie om 2 redenen. Ten eerste omdat dit eerlijker is naar mijn mening, ik vind het eerlijker om de groep te laten beslissen als dat ik dit zelf doe. Daarom vond ik het verstandiger om het gezamenlijk te bepalen. De tweede reden is aangezien ik denk dat het efficiënter was voor de groep. Davy en ik begrepen scenebuilder wel maar de rest niet. En dit is opzich niet moeilijk om te begrijpen maar het kost wel tijd. En het is handiger om dan iets te gebruiken waar de gehele groep al kennis van heeft en mee weet om te gaan. 

### Mijn bijdrage

In deze week heb ik samen met Davy het gehele skelet van de GUI gemaakt voor de agendamodule. We hebben alle textfields, textarea's, buttons, labels en scene's toegevoegd en op de juiste plekken gezet. Daarnaast hebben we ook wat logica geschreven voor de buttons. Voor sommige dat ze je bijvoorbeeld naar een nieuwe scene sturen en andere dat er nieuwe objecten worden aangemaakt of verwijderd aan de hand van de parameters meegegeven in de verschillende textfields en -area's. Daarnaast heb ik zelf de logica geschreven voor de linkedList's zodat wij de objecten van artiesten en stage's kunnen obslaan in een lijst en meteen weergegeven kunnen worden in de listview's aanwezig in de GUI. Naast dit heb ik ook wat logica geschreven zodat je niet 2 keer dezelfde artist kan aanmaken.

``` 
   private String name;
    private int age;
    private String genre;
    private String description;
    private String artistPhoto;

    public Artist(String name, int age, String genre, String description) {
        this.name = name;
        this.age = age;
        this.genre = genre;
        this.description = description;
    }

    public Artist(String name, int age, String genre, String description, String artistPhoto) {
        this.name = name;
        this.age = age;
        this.genre = genre;
        this.description = description;
        this.artistPhoto = artistPhoto;
    }

    public void setArtistPhoto(String artistPhoto) {
        this.artistPhoto = artistPhoto;
    }
    public void setName(String name) {
        this.name = name;
    }

    public void setAge(int age) {
        this.age = age;
    }

    public void setGenre(String genre) {
        this.genre = genre;
    }

    public void setDescription(String description) {
        this.description = description;
    }

    public String getName() {
        return name;
    }

    @Override
    public String toString() {
        return this.name;
    }

    public String getArtistPhoto() {
        return artistPhoto;
    }

    public int getAge(){
        return this.age;
    }

    public String getGenre(){
        return this.genre;
    }

    public String getDescription(){
        return this.description;
    }
```
```
 private SceneHandler sceneHandler;
    private MainView mainView;
    private  ArtistViewController controller;
    private EventView eventView;
    private ObservableList<Artist> artists;
    private Data data;



    public ArtistView(SceneHandler sceneHandler, EventView eventView, Data data) {
        this.sceneHandler = sceneHandler;
        this.mainView = mainView;
        this.eventView = eventView;
        this.artists = FXCollections.observableArrayList();
        this.data = data;


        setWidth(1280);
        setHeight(800);
        setStyle("-fx-background-color: #35477D;");
        getChildren().add(createStackPane());
    }


    public StackPane createStackPane() {

        StackPane stackPane = new StackPane(); //deze stackpane kun je in bouwen
        stackPane.setMinSize(800, 570);
        stackPane.setMaxSize(800, 570);

        stackPane.setStyle("-fx-background-color: #FFFFFF;" +
                "-fx-background-radius: 30; " +
                "-fx-effect: dropshadow( three-pass-box , rgba(0,0,0,0.6) , 20, 0.0 , 2 , 2 );"
        );

        Button BackButton = new FPButton("X", 30, 30);
        stackPane.getChildren().add(BackButton);
        BackButton.setOnAction(event -> {
            try {
                this.sceneHandler.toMainView();
            } catch (SQLException e) {
                e.printStackTrace();
            }
        });

        BackButton.setLayoutX(370);
        BackButton.setLayoutY(-255);
        BackButton.setTranslateX(370);
        BackButton.setTranslateY(-255);

        //labels
        
DynamicTitle title = new DynamicTitle("Artist", 40);
        place(title,-300,-220);

        DynamicTitle secondTitle = new DynamicTitle("Add Artist", 21);
        place(secondTitle,-300,-150);

        DynamicTitle thirdTitle = new DynamicTitle("All Artists", 21);
        place(thirdTitle,110,-150);

        DynamicTitle artistName = new DynamicTitle("Artist Name", 17);
        place(artistName,-302,-90);

        DynamicTitle Age = new DynamicTitle("Age",17);
        place(Age,-334,-30);

        DynamicTitle Genre = new DynamicTitle("Genre", 17);
        place(Genre,-328,30);

        DynamicTitle profileImage = new DynamicTitle("Profile Image", 17);
        place(profileImage,-297,90);

        DynamicTitle biography = new DynamicTitle("Biography", 17);
        place(biography,-311,155);

        //Fields

        TextField artistNameField = new FPTextField("Artist Name");
        place(artistNameField,-153,-90);

        TextField ageField = new FPTextField("Age",80,40);
        place(ageField,-187,-30);

        TextField genreField = new FPTextField("Genre");
        place(genreField,-153,30);

        ListView<Artist> fpListView = new ListView();

        fpListView.setStyle("-fx-background-color: #FFFFFF; " +
                "-fx-text-fill: #B76F88; " +
                "-fx-font-size: 15; " +
                "-fx-font-family: Helvetica; ");

        fpListView.setItems(data.getArtists());
        place(fpListView,200,50);

        TextField open = new FPTextField("Picture URL");
        place(open,-153,90);
        fpListView.setMinSize(200,320);
        fpListView.setMaxSize(200,320);

        FPButton show = new FPButton("Edit", 90, 35);
        place(show, 190, 230);

        open.setOnAction(event -> this.controller.uploadPhoto()
        );

        TextArea biographyField = new FPTextArea("Biography",160,80);
        place(biographyField,-149,165);

        FPButton addArtist = new FPButton("Add ", 90, 35);
        place(addArtist,-61,230);

        FPButton clearButton = new FPButton("Clear All ", 90, 35);
        place(clearButton,-181,230);

        clearButton.setOnAction(event -> {
            artistNameField.clear();
            ageField.clear();
            biographyField.clear();
            genreField.clear();
        });

        FPButton removeArtist = new FPButton("Remove ", 90, 35);
        place(removeArtist,310,230);


        stackPane.getChildren().addAll(title,secondTitle,thirdTitle,artistName,artistNameField,Age,fpListView,ageField,Genre,genreField,profileImage,show,biography,biographyField,open,addArtist,clearButton,removeArtist,makeLine(),makeLine2());

        removeArtist.setOnAction(event -> {
            data.removeArtist(fpListView.getSelectionModel().getSelectedItem());
        });


        /**
         * this part checks for doubles or and adds an artist
         */
        addArtist.setOnAction(event -> {

            int age = 0;

            try {
                age = Integer.parseInt(ageField.getText());

                Artist artist = new Artist(artistNameField.getText(),
                        age,
                        genreField.getText(),
                        biographyField.getText(),
                        open.getText());

                if(data.getArtists().size() != 0) {
                    int alreadyExist = 0;
                    int place = 0;
                    for (int i = 0; i < data.getArtists().size(); i++) {
                        if (data.getArtists().get(i).getName().equals(artist.getName())) {
                            alreadyExist = 1;
                            place = i;
                        }
                    }

                    if (alreadyExist == 1) {

                        data.getArtists().get(place).setName(artist.getName());
                        data.getArtists().get(place).setAge(artist.getAge());
                        data.getArtists().get(place).setGenre(artist.getGenre());
                        data.getArtists().get(place).setDescription(artist.getDescription());
                        data.getArtists().get(place).setArtistPhoto(artist.getArtistPhoto());
                    }
                    else this.data.addToArtists(artist);
                }
                else {this.data.addToArtists(artist);}

                }
            catch(Exception e) {
                ageField.setText("Error");
            }
            artistNameField.setText("");
            ageField.setText("");
            genreField.setText("");
            biographyField.setText("");
            open.setText("");


        });

        clearButton.setOnAction(event -> {
            artistNameField.setText("");
            ageField.setText("");
            biographyField.setText("");
            genreField.setText("");
            open.setText("");

        });

        show.setOnAction(event -> {

            Artist selected = fpListView.getSelectionModel().getSelectedItem();

            artistNameField.setText(selected.getName());
            ageField.setText(String.valueOf(selected.getAge()));
            genreField.setText(selected.getGenre());
            biographyField.setText(selected.getDescription());
            open.setText(selected.getArtistPhoto());


        });



        return stackPane;
    }
```


## Projectweek 4

**Situatie**

Aan het einde van week 4 moesten we de agendamodule opleveren. Hiervoor moesten we de laatste puntjes op de I zetten en de fouten uit de code halen en tevens het PVA vernieuwen. We liepen een beetje achter op de planning en dit zorgde dus voor een beetje stress. We hebben het wel op tijd af kunnen krijgen gelukkig.

Na de oplevering hebben we nog gewerkt aan de taken voor die week zoals het ontwerpen van een map voor het festivalterrein en deze vervolgens proberen in te laden. We hadden hier wel enige moeite mee en liepen vast. We hadden namelijk een map gemaakt met meerdere spritesheets waaronder een paar zeer grote. Hierdoor wisten we niet wat het beste was alles inladen of een eigen spritesheet creëren.

**Keuzemogelijkheden**

Voor het inladen van de map hadden wij neit de kennis om de gecreëerde Tiled map te gebruiken. We wouden us zelf de map gaan creëren door de tiles gebruikt in de map zelf te plaatsten. Dit ging alleen moeilijk omdat we meerdere hele uitgebreidde tilesets hebben gebruikt voor de map. We hadden dus de keuze om de gehele spritesheets in te laden en zelf die sprites die we nodig hebben te gebruiken. Of om van die desbetreffende sprites een eigen spritesheet te maken. zodat we alleen de nuttige sprites hebben.

**Mijn Keuze**

Ik vond het zelf handiger om een eigen spritesheet te maken van de gebruikte sprites. 

**Keuzemotivatie**

Ik vond dit een makkelijkere methode als dat we van elke sprite die we gebruiken op de map de spritesheet in gaan laden en dan moeten zoeken welke coördinaten overeenkomen met die sprite. Natuurlijk ben je veel tijd kwijt aan het creëren van een eigen spritesheet maar het werkt overzichtelijker vind ik. 

### Mijn bijdrage

Ik heb zelf een groot deen van het PVA aangepast en vernieuwd. Natuurlijk heb ik ook sturing gegeven aan de groep om te zorgen dat de taken af kwamen en duidelijk was wat we nog moesten doen. Daarnaast heb ik samen met Davy gewerkt aan het ontwerp voor de festival map en geprobeerd deze in te laden. Hier hadden we wel veel moeite mee. We wisten niet hoe we het het beste konden doen of hoe we het überhaupt moeten doen.

![PVA Testplan](https://i.gyazo.com/3ac912c8aa0af3946f6d2bcc08728b0b.png)
	
![PVA Kwaliteit](https://i.gyazo.com/354c90812a289b81b7bc6bc6f624f9a9.png)


![PVA Projectactiviteiten1](https://i.gyazo.com/b5c40d3102565e2ec24dec153ca7964f.png)

![Projectactiviteiten2](https://i.gyazo.com/600a4110cf92abee10b600c5c7658eac.png)

## Projectweek 5

**Situatie**
In week 5 van het project kwam het begin van de simulatiemodule. De taak voor het maken en het inladen van de map hebben Davy en ik op ons genomen. Het was best ingewikkeld om dit te doen aangezien we voor het eerst met het inladen van een Tiled map gingen werken wat wennen en moeilijk was. We liepen ook vast op een gegeven moment.

**Keuzemogelijkheden**
Het moment dat we vastliepen kwam doordat wij nog niet goed wisten hoe je het beste een map kon inladen. We kwamen op 2 mogelijkheden. Inladen zoals de docenten het voordeden dus met de tiled applicatie. De andere manier had Davy bedacht en gebruikt in een eigen project. Dit was het handmatig inladen van elke tile en ook een eigen tileset maken.

Keuze 1: Map inladen met behulp van de Tiled Applicatie.
Keuze 2: Een eigen tileset maken en handmatig de map inprogrammeren

**Mijn Keuze**
Ik heb gekozen voor de manier voor de docenten keuze 1 dus.

**Keuzemotivatie**
Mijn motivatie voor het maken van deze keuze was ten eerste dat ik het handiger vond aangezien dit de manier van de docenten was dus als je vragen had kon je bij de docenten terecht. De 2e motivatie was het feit dat als je een map via Tiled inlaad dat je hem makkelijk aan kan passen in de Tiled applicatie en hij wordt dat gelijk in het project aangepast wat dubbele moeite scheelt.

### Mijn bijdrage
Ik heb deze week veel onderzoek gedaan naar hoe men een map via Tiled in moet laden en hoe je Json bestanden uit moet lezen en gebruiken. Ook heb ik contact met de docenten opgezocht om de kennis die ik via het internet vergaard had en toegepast in het project te verbeteren aangezien er af en toe toch wat kleine foutjes in zaten.

## Projectweek 6

**Situatie**
In week 6 hadden wij helaas nog niet het inladen van de map compleet afgerond. Ik heb in de week daarvoor al wel veel kennis vergaard over het inladen en extra uitleg gehad en zo dus een goede basis gemaakt. Ik moest vervolgens alleen Johan vragen om een klein foutje op te lossen. Nadat dit opgelost was zijn wij een definitieve map gaan maken in Tiled. Deze zou gebruikt worden in het project. Hiervoor gebruikte wij een manier in tiled om terreinen aan te maken zodat je makkelijk paden kan maken. Hierbij liepen wij helaas tegen een probleem aan want het inladen werkte niet goed met de tereinnen aangezien dit een extra onderdeel voor de Json werdt maar dit zat niet in de code en was nog onbekend voor ons.

**Keuzemogelijkheden**
Doordat de map was gemaakt met terreinen maar het inladen van de terreinen onbekend voor ons was moesten wij een keuze maken. Het uitzoeken hoe de terreinen werken en de map met terreinen kunnen maken, of de map handmatig tekenen wat meer tijd zou kosten maar dan zou er niks aan de code voor het uitlezen en tekenen van de map moeten veranderen.

Keuze 1: Uitzoeken hoe je terreinen in Tiled kan uitlezen en tekenen in Java.
Keuze 2: De map maken in Tiled zonder terreinen te gebruiken.

**Mijn Keuze**
Ik heb gekozen de map te tekenen zonder het gebruiken van terreinen. Ik heb dus de code voor het inladen en tekeken hetzelfde gehouden en de map handmatig getekend. 

**Keuzemotivatie**
Ik heb voor deze keuze gekozen aangezien ik al veel tijd had besteed aan het uitzoeken hoe je een Tiled map in moet laden in Java. Dit wel zonder het gebruik van terreinen. Ik heb toen een overweging gemaakt, ik besteed een kwartier meer tijd aan het maken van de map of ik ga onderzoek doen naar het inladen van een terrein waarvan ik niet weet hoe lang dit zal duren. Ik heb zelf toen gekozen voor de voorspelbare optie en ben gegaan voor het zelf tekenen. Dit omdat ik zeker wist dat dit zou werken en ik wist dat het relatief snel afgemaakt kon worden. Ik koos voor de zekerheid aangezien er nog veel moest gebeuren en dat af zou hangen van het inladen van de map. 

Om deze reden vond ik het te risicovol om iets te proberen waarvan ik niet zeker wist of het gelijk zou werken en daardoor het inladen van de map langer zou duren als nodig.

### Mijn bijdrage
Ik heb deze week de code volledig opgezet voor het inladen van de map en ik heb er voor gezorgd dat de map dynamisch aangepast kan worden via Tiled. Zodat wij binnen ons project altijd de juiste map zouden hebben.

## Projectweek 7

**Situatie**
In week 7 werd het hele onderwijs waaronder de proftaak omgegooid door de overheidsmaatregelen voor het coronavirus. Wij moesten namelijk vanuit thuis werken. De school was gesloten en er was veel onduidelijkheid. Wij moesten dus een manier vinden om toch effectief en efficient te werk te gaan thuis om het project optijd af te krijgen. 

**Keuzemogelijkheden**
Voor het creeëren van een toch stabiele en efficiente werkrelatie tijdens het thuiswerken moesten er duidelijke afspraken gemaakt worden. Dit om structuur en continuiteit aan te brengen. Ik kon hierbij 2 kanten kiezen. Een soepele of een meer directere afspraak maken. Dus zou ik al projectleider afspraken maken van welke tijden wij zouden werken en wat de afspraken waren. Of zou ik de groep zelf laten beslissen en het lot zijn gang laten gaan.

Keuze 1: Als projectleider duidelijke afspraken maken waar aan gehouden moet worden.
Keuze 2: Iedereen zijn gang laten gaan en kijken waar het schip strand.

**Mijn Keuze**
Ik heb de keuze gemaakt als projectleider op te treden en duidelijke regels en afspraken te maken.

**Keuzemotivatie**
Ik heb voor deze optie gekozen omdat ik van mening was dat dit het beste voor de voorgang en kwaliteit van het project zou zijn. Als iedereen zijn eigen gang zou gaan zouden er namelijk geen duidelijke samenwerking meer zijn minder goeie communicatie en gewoon chaos. En dat zou ten kostte gaan van het project wat niet zou mogen gebeuren.

### Mijn bijdrage
Ik heb op de eerste dag van de week de groep bij elkaar gehaald en samen met de groep duidelijke afspraken gemaakt over hoe we vanaf nu gaan samen werken en hoe we het aan gaan pakken. Dit zorgde voor duidelijkheid en structuur wat ten goede kwam van het project merkte ik in de loop van de week.

## Projectweek 8

**Situatie**
In week 8 van het project zijn wij bezig geweest met het afronden van het project. De laatste puntjes moesten op de I gezet worden en er moest gedebugged en gecontroleerd worden. Daarnaast moest ook het plan van aanpak veranderd worden om aan de criteria te voldoen van P&OC.

**Keuzemogelijkheden**
In de afronding van het project is het belangrijk om te testen of het project werkt en of het project voldoet aan de eisen. Hiervoor is het belangrijk het product te testen met de requirementslist ernaast. Dit om te kijken of de benodigde zaken aanwezig zijn. Ik kon kiezen dit op mijzelf te nemen of dit uit handen te laten en iemand anders het te laten controleren.

Keuze 1: Zelf het product testen aan de hand van de requirementslist.
Keuze 2: Een ander groepslid het product testen aan de hand van de requirementslist.

**Mijn Keuze**
Ik heb gekozen zelf het product te testen en te debuggen en het product te controleren op zijn requirements.

**Keuzemotivatie**
Ik heb voor deze optie gekozen aangezien ik een pietje precies ben qua projecten en zeker wou weten dat ik iets goeds zou leveren. Daarnaast vond ik ook dat ik deze taak op mij moest nemen als projectleider aangezien het de taak is van de projectleider om de kwaliteti van het product te controleren en waar te borgen.

### Mijn bijdrage
Ik heb mij deze week bezig gehouden met het controleren, debuggen en testen van het eindproduct. Ik heb gekeken of het voldoet aan de eisen en of het kwalitatief in orde is. Naast dit heb ik ook een taakverdeling gemaakt voor het verbeteren van het plan van aanpak en heb ik zelf ook enkele onderdelen hiervan aangepast en verbeterd. Op het einde heb ik het plan van aanpak zelf ook nog gecontroleerd of het voldeed aan de eisen en de opmerkingen en feedback die gegeven was hierop verwerkt zijn. Vervolgens heb ik het aan de secretaris gegeven en is het opnieuw ingezonden.

## Projectweek 9

**Situatie**
In de laatste week van het project was het product zelf afgerond. De agenda en simulatiemodule werkte zoals we verwacht hadden. We hebben de buggs eruit gehaald en zijn ons gaan voorbereiden op de presentatie. Hiervoor moest uiteraard een presentatie met een taakverdeling gemaakt worden wie wat zou presenteren.

**Keuzemogelijkheden**
In de presentatie komen vele verschillende onderwerpen aan bod maar wij wouden als groep wel allemaal iets vertellen over het product waar we zo trots op zijn. Hierdoor moest ik een selectie maken welke onderwerpen ik wou presenteren en hoe ik die in zou vullen.

**Mijn Keuze**
Ik heb gekozen om de opening met daarbij de inleiding van het project te doen. En daarnaast heb ik gekozen ook het onderwerp, wat is simulatiesoftware, te nemen.

**Keuzemotivatie**
Ik heb gekozen voor de opening en de inleiding aangezien ik van mening ben dat ik een makkelijke prater ben en redelijk kan presenteren. Ik heb ook gehoord van kennissen dat ik goed ben in het openen van een presentatie en daarmee de aandacht te trekken. Om die reden heb ik het begin van de presentatie gekozen.
Het uitleggen wat simulatiesoftware is heb ik gekozen om het feit dat ik goed weet wat er verwacht wordt van de simulatiesoftware en wat het nut er van is. Daardoor was ik van mening dat ik dit duidelijke en correct zou kunnen vertellen en om die reden het mij een verstandige keuze leek deze op mij te nemen.

### Mijn bijdrage
Ik heb deze week de gekozen onderwerpen voor de presentatie voorbereid en ingevuld zodat ik deze correct uit zou kunnen leggen op de presentatie. Ik heb een verdeling gemaakt wat wel en wat niet te vertellen en een goede aantrekkelijke opening bedacht voor de presentatie. Daarnaaast heb ik samen met de groep een proefpresentatie georganiseerd zodat wij allen redelijk op elkaar ingespeeld zouden zijn voor de echte presentatie.

## Stellingsreflectie: “In het bedrijfsleven wordt steeds meer in software gesimuleerd”

Ik heb voor dit onderzoek geprobeerd concrete bronnen te vinden of het meer gebruikt wordt. Helaas heb ik hier geen succes in gehad aangezien ik er niet in geslaagd ben veel informatie hierover te vinden. Wel heb ik voordelen en nadelen van het simuleren kunnen vinden. Daarom zal ik met de kennis die ik heb gevonden eerder een betoog schrijven over wat ik denk dat de waarschijnlijke uitkomst zal zijn. Ik zal hieronder de voor en nadelen van het gebruiken van simulatiesoftware beschrijven, vervolgens zal ik een overweging geven dus de voordelen tegen de nadelen afwegen. Tenslotte zal ik een mening geven over het gebruik hiervan. De voor en nadelen die ik beschrijf zijn afkomstig van informatie die ik opzoek op internet. 

### Voordelen
Aan het gebruik van simulatiesoftware zitten verschillende voordelen wat het gebruik hiervan interessant maakt. Een van de eerste die naar boven komt is dat het een risicoloze manier van testen is. Je kan hiermee grote evenementen of ingewikkelde producten simuleren zonder een echt risico te lopen. Als het bijvoorbeeld niet goed werkt of als er te veel mensen zijn kan je dit ontdekken zonder dat de dure machine kapot gaat. Of in een groot evenement met veel mensen kan je zien waar knelpunten zitten zonder het risico te lopen dat hier mensen gewond bij zullen raken. Dit is natuurlijk een groot voordeel wat ook leid tot een ander voordeel, het is namelijk kostentechnisch ook beter.

Dit komt door het feit dat als er iets kapot zou gaan in een machine je in het echt dit zou moeten vervangen. Daarvoor moet je de materiaalkosten en de arbeidsuren om het te herstellen betalen. Als je het simuleert gaat er niet echt iets kapot wat scheelt in materiaalkosten en in arbeidskosten. Daarnaast is het ook tijdsefficiënter. Een simulatie kan je namelijk makkelijk doorspoelen. Hierdoor kan je een grotere periode als het ware testen in een kortere tijd. Hiermee is gemakkelijker te zeggen hoe lang iets vol houd hoe lan iets werkend blijft. 

Naast dit zijn er nog meer voordelen op te noemen. Je kan bijvoorbeeld inschatten voor een magazijn wat de bezetting van dit magazijn zal zijn op verschillende momenten zo kan er goed worden ingeschat hoe groot het magazijn moet zijn voor het bedrijf. Hiermee kan voorkomen worden dat een te klein of te groot magazijn gecreerd wordt wat weer kosten kan voorkomen.

### Nadelen
Het creëren van een goede simulatiesoftware is heel prijzig en kost veel tijd. Een dergelijk programma moet namelijk heel flexibel zijn en heel uitbrijdbaar om op allerlij verschillende manieren te testen. Om dit te creëren kost het veel tijd aangezien dit vrij ingewikkeld is. Daarnaast kost dit natuurlijk veel geld want tijd is geld. Ook zijn er krachtige onderdelen voor nodig. Aangezien het zo veel dingen tegelijk moet berekenen moet de computer de simulatie wel aankunnen wat om krachtige componenten vraagt.

Naast dit is het heel lastig een perfecte simulatie te maken. Voor het maken van een perfecte simulatie moet je een goed begrip hebben en exact weten wat je product allemaal kan. En precies weten hoe dit verloopt. Daarnaast moet je ook elk mogelijke risico kunnen bedenken om het hier op te testen wat vrijwel onmogelijk is want er kunnen altijd onverwachtse dingen gebeuren. Om deze reden is het heel moeilijk om een simulatie precies alles te laten testen zoals in werkelijkheid zal gebeuren. 

### Overweging 
Als ik mijn mening zou moeten geven zou ik zelf zeggen dat de voordelen groter zijn als de nadelen. Daarom zou ik zeggen dat het gebruik van simulatiesoftware positief is. Een van de nadelen is bijvoorbeeld dat het lastig is om het perfect te simuleren zoals het in het echt zou zijn. Daar ben ik het zeker mee eens, maar met een simulatie kan je wel de meeste situaties simuleren. Daardoor kan je al heel veel verschillende dingen testen en heel veel risicos vinden en voorkomen. Dit zorgt er voor dat je dan al een beter getest systeem kan leveren. Als je dit product dan maakt en uitvoert dan heb je in ieder geval die risicos al voorkomen. Dan kan je nog verder testen of er meer zijn die in de simulatie niet aan bod kwamen. 
Natuurlijk kan het dan kapot gaan maar je zal verder zijn zonder enige kosten dan dat je niet zou simuleren. Daardoor bespaar je alsnog kosten. Die kosten kunnen verkend worden met de kosten voor het ontwikkelen van de simulatiesoftware. Dan heb je daartegen nog het voordeel dat je met het simuleren de risicos vermeid zoals bijvoorbeeld met een evenement dat jezonder gevaar de risicozones kan vinden.

### Conclusie

Als als ik kijk naar de voordelen en de nadelen zou ik zeggen dat er meer voordelen als nadelen zijn en ook dat de voordelen sterker wegen als de nadelen. Om die reden is het in mijn ogen positief om simulatiesoftware te gebruiken. Daarmee denk ik ook dat bedrijven dit inzien en ook zeker positief denken over het gebruiken van simulatiesoftware. Deze software wordt ook verder ontwikkeld en steeds beter waardoor het nog antrekkelijker wordt. Om deze redenen denk ik dat er meer gebruik wordt gemaakt van simulatiesoftware als voorheen.

[Bron 1](https://www.anylogic.com/use-of-simulation/)
[Bron 2](https://www.bbc.co.uk/bitesize/guides/zvxp34j/revision/3)


## Applicaties die Json gebruiken:
1. GitKraken
2. Minecraft
3. Visual Studio
4. Microsoft Teams
