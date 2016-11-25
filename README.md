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

Ξεκινάμε την εισαγωγή του WeatherContract (DBContract). [DBContract lesson](https://developer.android.com/reference/android/provider/ContactsContract.html)

Tests and Unit testing in general

DB tests

DB versioning


