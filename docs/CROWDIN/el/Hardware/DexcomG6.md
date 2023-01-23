# Dexcom G6

## Πρώτα τα βασικά

- Follow general CGM hygiene and setting sensor recommendation [here](../Hardware/GeneralCGMRecommendation.md).
- Για πομπούς G6 που κατασκευάζονται μετά το πέρας / τέλος του 2018, βεβαιωθείτε ότι έχετε χρησιμοποιήσει μία από τις πιο πρόσφατες εκδόσεις xDrip + \<<https://github.com/NightscoutFoundation/xDrip/releases>> _ \_. Αυτοί οι πομποί έχουν ένα νέο firmware και η τελευταία σταθερή έκδοση του xDrip + (2019/01/10) δεν μπορεί να το αντιμετωπίσει.

## Γενικές συμβουλές για το κύκλωμα με το G6

Αυτό που είναι σαφές είναι ότι η χρήση του G6 είναι ίσως λίγο πιο πολύπλοκη από ό, τι φαίνεται. Για να το χρησιμοποιήσετε με ασφάλεια, υπάρχουν μερικά σημεία που πρέπει να γνωρίζετε:

- If you are using the native data with the calibration code in xDrip+ or Spike, the safest thing to do is not allow preemptive restarts of the sensor.
- Αν πρέπει να χρησιμοποιήσετε την προληπτική επανεκκίνηση, βεβαιωθείτε ότι εισάγετε μια ώρα της ημέρας όπου μπορείτε να παρατηρήσετε την αλλαγή και να βαθμονομήσετε εάν είναι απαραίτητο.
- Αν κάνετε επανεκκίνηση των αισθητήρων, καταρχήν κάντε το χωρίς την εργοστασιακή βαθμονόμηση για ασφαλέστερα αποτελέσματα στις ημέρες 11 και 12, και βεβαιωθείτε ότι είστε έτοιμοι να βαθμονομήσετε και να παρακολουθήσετε την παραλλαγή.
- Η προ-εμβάπτιση του G6 με εργοστασιακή βαθμονόμηση είναι πιθανό να προκαλέσει διακύμανση στα αποτελέσματα. Αν κάνετε προ-εμβάπτιση, τότε για να έχετε τα καλύτερα αποτελέσματα, πιθανόν να χρειαστεί να βαθμονομήσετε τον αισθητήρα.
- Αν δεν είστε προσεκτικοί σχετικά με τις αλλαγές που ενδεχομένως να πραγματοποιηθούν, ίσως είναι καλύτερο να επιστρέψετε στη μη βαθμονομημένη από το εργοστάσιο λειτουργία και να χρησιμοποιήσετε το σύστημα όπως το G5.

To learn more about the details and reasons for these recommendations read the [complete article](https://www.diabettech.com/artificial-pancreas/diy-looping-and-cgm/) published by Tim Street at [www.diabettech.com](https://www.diabettech.com).

## If using G6 with xDrip+

- The Dexcom G6 transmitter can simultaneously be connected to the Dexcom receiver (or alternatively the t:slim pump) and one app on your phone.
- When using xDrip+ as receiver uninstall Dexcom app first. **You cannot connect xDrip+ and Dexcom app with the transmitter at the same time!**
- If you need Clarity and want to profit from xDrip+ alarms use the [BYODA](../Hardware/DexcomG6.md#if-using-g6-with-build-your-own-dexcom-app) with local broadcast to xDrip+.
- If not already set up then download [xDrip+](https://github.com/NightscoutFoundation/xDrip) and follow instructions on [xDrip+ settings page](../Configuration/xdrip.md).
- Select xDrip+ in ConfigBuilder (setting in AndroidAPS).
- Adjust settings in xDrip+ according to [xDrip+ settings page](../Configuration/xdrip.md)
- If AAPS does not receive BG values when phone is in airplane mode use 'Identify receiver' as describe on [xDrip+ settings page](../Configuration/xdrip.md).

## If using G6 with Build Your Own Dexcom App

- As of December 2020 [Build Your Own Dexcom App](https://docs.google.com/forms/d/e/1FAIpQLScD76G0Y-BlL4tZljaFkjlwuqhT83QlFM5v6ZEfO7gCU98iJQ/viewform?fbzx=2196386787609383750&fbclid=IwAR2aL8Cps1s6W8apUVK-gOqgGpA-McMPJj9Y8emf_P0-_gAsmJs6QwAY-o0) (BYODA) also supports local broadcast to AAPS and/or xDrip+ (not for G5 sensors!)
- This app lets you use your Dexcom G6 with any Android smartphone.
- Uninstall the original Dexcom app or patched Dexcom app if you used one of those previously.
- Εγκαταστήστε το κατεβασμένο apk
- Enter sensor code and transmitter serial no. in patched app.
- In phone settings go to apps > Dexcom G6 > permissions > additional permissions and press 'Access Dexcom app'.
- After short time BYODA should pick-up transmitter signal. (If not you will have to stop sensor and start new one.)

### Settings for AndroidAPS

- Select 'Dexcom App (patched)' in config builder.
- If you don't receive any values select any other data source, then re-select 'Dexcom App (patched)' to trigger the demand for permissions to establish the connection between AAPS and BYODA-broadcast.

### Settings for xDrip+

- Select '640G/Eversense' as data source.
- Command 'start sensor' must be performed in xDrip+ in order to receive values. This will not affect your current sensor controlled by Build Your Own Dexcom App.

## Αντιμετώπιση προβλημάτων G6

### Dexcom G6 αντιμετώπιση συγκεκριμένων προβλημάτων

- Πομποί με σειριακό αριθμό. starting with 80 or 81 need at least last stable xDrip+ version from May 2019 or a newer nightly build.

- Πομποί με σειριακό αριθμό. ξεκινώντας με 8G πρέπει τουλάχιστον να έχετε nightly build από 25 Ιουλίου, του 2019 ή νεότερη έκδοση.

- xDrip+ and Dexcom app cannot be connected with the transmitter at the same time.

- Περιμένετε τουλάχιστον 15 λεπτά. μεταξύ παύση και η έναρξη ενός αισθητήρα.

- Μην το πας πίσω το χρόνο της εισαγωγής. Απάντηση ερώτηση "Μήπως το βάλατε σήμερα;" πάντα με "Ναι, σήμερα".

- Μην ενεργοποιήσετε την επιλογή "επανεκκίνηση αισθητήρα'', ενώ ρυθμίζετε νέο αισθητήρα

- Do not start new sensor before the following information is shown in Classic Status Page -> G5/G6 status -> PhoneServiceState:

  - Πομπός με σειριακό αριθμό που ξεκινάει με 80 ή 81: "Έχεις δεδομένα ώρες: λεπτά" (δηλ. "Τα δεδομένα 19:04")
  - Transmitter serial starting with 8G or 8H: "Got glucose hh:mm" (i.e. "Got glucose 19:04") or "Got no raw hh:mm" (i.e. "Got now raw 19:04")

```{eval-rst}
.. εικόνα:: ../images/xDrip_Dexcom_PhoneServiceState.png
  :alt: xDrip+ PhoneServiceState
```

### General troubleshooting

General Troubleshoothing for CGMs can be found [here](./GeneralCGMRecommendation.html#troubleshooting).

### Νέος πομπός με αισθητήρα λειτουργίας που λειτουργούσε

Εάν συμβεί να αλλάξετε τον πομπό κατά τη διάρκεια μιας περιόδου λειτουργίας του αισθητήρα, μπορεί να προσπαθήσετε να αφαιρέσετε τον πομπό χωρίς να καταστρέψετε τη βάση του αισθητήρα. A video can be found at [https://youtu.be/tx-kTsrkNUM](https://youtu.be/tx-kTsrkNUM).