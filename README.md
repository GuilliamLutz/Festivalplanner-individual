# Festivalplanner-individual
This reposiroty includes a markdown file in wich I note down my process of my project in year 1 period 3 of my education thecnical computing science

## Projectweek 2

**Situatie**

In week 2 moesten wij gaan beginnen aan het coderen van de agendamodule. We hebben in week 1 hiervoor een ontwerp gemaakt en een projectkeuze. We vonden het eerste ontwerp alleen niet van genoeg kwaliteit. Daarom hebben we besloten om het te verbeteren. Deze taak is gegeven aan Grant en mijzelf. 

**Keuzemogelijkheden**

Tijdens het ontwerpen van de agendamodule hadden Grant en ik al snel de vraag wat nou precies mooi is en gewild. En niet alleen voor onszelf maar ook de groep. We vroegen ons af of wij het met zijn 2e moesten ontwerpen of dat we de vraag stellen aan iedereen om een eigen ontwerp te maken en later alles ontwerpen samen te voegen zodat het van iedereen wat heeft. 

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
