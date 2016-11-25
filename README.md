# Lesson06-material

Σε αυτό το μάθημα θα αναλύσουμε τη λειτουργία των Βάσεων Δεδομένων και συγκεκριμένα της SQLite.

Το σύστημά μας θα αλλάξει αρκετά, καθώς θα προστεθούν πολλές νέες κλάσεις που σχετίζονται με τη ΒΔ. Πρώτα θα ορίσουμε τους πίνακες της ΒΔ, έπειτα θα γράψουμε κώδικα για να δημιουργούνται μέσω Java και έπειτα θα κάνουμε δοκιμαστικές εισαγωγές και ελέγχους δεδομένων απο και προς τη ΒΔ.
Επειδή η λειτουργικότητα των ΒΔ είναι δύσκολο να δοκιμαστεί σε κινητό λόγω του απαραίτητου User Interface, ο καλύτερος τρόπος είναι να γίνει μέσω Unit Testing. Θα πούμε 2 λόγιο για το Unit Testing στη συνέχεια.

Οι μονάδες που θα προστεθούν στο σύστημα φαίνονται στην παρακάτω εικόνα:

![](https://github.com/UomMobileDevelopment/Lesson06-material/blob/master/sunshine-db-overview.png)


## Data Storage in Android - Αποθήκευση δεδομένων

Για την αποθήκευση δεδομένων το Android μας παρέχει 2 βασικούς πυλώνες:

1. Το σύστημα αρχείων (File Storage) πχ εκεί αποθηκεύονται τα Shared Preferences 
2. Μια μίνι-έκδοση βάσης δεδομένων που λέγεται SQLite

Φυσικά το 2ο είναι πολύ πιο πολύπλοκο στην υλοποίηση, αλλά παρέχει σαφή και αποδοτική οργάνωση δεδομένων (+γρηγορη αναζήτηση)

![](https://github.com/UomMobileDevelopment/Lesson06-material/blob/master/sql-demo.PNG)


Με τη χρήση του SQLite μέσα απο τον κώδικα μπορούμε εύκολα να δημιουργήσουμε πίνακες, να εισάγουμε και να διαγράψουμε δεδομένα. 

### Αλλαγές Sunshine

Ξεκινάμε την εισαγωγή του WeatherContract [(DBContract)](https://developer.android.com/reference/android/provider/ContactsContract.html)

Πρόκειται για τη διασύνδεση των πινάκων με τον κώδικα. Μια κλάση contract περιλαμβάνει έναν σύνολο static final Strings καθένα απο τα οποία περιγράφει το όνομα ενός πίνακα και της μιας στήλης στη ΒΔ

![](https://github.com/UomMobileDevelopment/Lesson06-material/blob/master/db-contract.PNG)

```
public class WeatherContract {

    /*
        Inner class that defines the table contents of the location table
        Students: This is where you will add the strings.  (Similar to what has been
        done for WeatherEntry)
     */
    public static final class LocationEntry implements BaseColumns {
        public static final String TABLE_NAME = "location";

        public static final String COLUMN_LOCATION_SETTING = "location_setting";

        public static final String COLUMN_CITY_NAME = "city_name";

        public static final String COLUMN_COORD_LAT = "coord_lat";

        public static final String COLUMN_COORD_LONG = "coord_long";

    }
 }
```

Για να αποφασίσουμε τι δεδομένα πρέπει να κρατήσουμε, μελετούμε το wireframe για την πρόβλεψη μιας ημέρας:

![](https://github.com/UomMobileDevelopment/Lesson06-material/blob/master/sunshine-weather-wireframe.png)

αποφασίζουμε λοιπόν πως το πίνακας ``weather`` πρέπει να έχει τα εξής πεδία:

- Record ID
- Weather Condition ID 
- Min Temp
- Max Temp
- Wind speed
- Humidity
- Date
- Wind direction
- Pressure

### Κατανόηση Foreign Key και έννοιας ακεραιότητας αναφορών

Ο Weather Location θα πρέπει επίσης να περιλαμβάνει και την πληροφορία της τοποθεσίας

![](https://github.com/UomMobileDevelopment/Lesson06-material/blob/master/weather-location-key-foreign-key.PNG)

__Info: Επεξήγηση ακεραιότητας αναφορών__

### Επεξήγηση κλάσεων του πακέτου data (Weather Contract, WeatherDbHelper) 

Τί χρειάζονται αυτές οι κλάσεις; 

### Tests and Unit testing in general

κλάσεις: TestPractice και FullTestSuite

