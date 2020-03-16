---
title: Implementare campi personalizzati per l'app per dispositivi mobili Microsoft Dynamics 365 Project Timesheet in IOS e Android
description: In questo argomento vengono forniti modelli comuni per l'utilizzo di estensioni con cui implementare campi personalizzati.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 48854c15e429d51dcf30ea804eb636dee7965443
ms.sourcegitcommit: a356299be9a593990d9948b3a6b754bd058a5b3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "3080774"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a>Implementare campi personalizzati per l'app per dispositivi mobili Microsoft Dynamics 365 Project Timesheet in IOS e Android

[!include [banner](../includes/banner.md)]

In questo argomento vengono forniti modelli comuni per l'utilizzo di estensioni con cui implementare campi personalizzati. Sono trattati i seguenti argomenti:

- I vari tipi di dati supportati dal framework dei campi personalizzati
- Il modo in cui visualizzare campi modificabili o di sola lettura nelle voci del foglio presenze e salvare i valori forniti dall'utente nel database
- Il modo in cui visualizzare campi di sola lettura nell'intestazione del foglio presenze
- Il modo in cui integrare altra logica di business per immettere valori predefiniti nei campi ed effettuare una convalida aggiuntiva

## <a name="audience"></a>Destinatari

Questo argomento è destinato agli sviluppatori che eseguono l'integrazione dei relativi campi personalizzati nell'applicazione per dispositivi mobili Microsoft Dynamics 365 Project Timesheet disponibile per Apple iOS e Google Android. Si presuppone che i lettori abbiano familiarità con lo sviluppo X++ e la funzionalità del foglio presenze progetto.

## <a name="data-contract--tstimesheetcustomfield-x-class"></a>Contratto dati – Classe X++ TSTimesheetCustomField

La classe **TSTimesheetCustomField** è la classe di contratto dati X++ che rappresenta le informazioni su un campo personalizzato per la funzionalità del foglio presenze. Gli elenchi di oggetti di campi personalizzati vengono passati al contratto dati TSTimesheetDetails e al contratto dati TSTimesheetEntry per visualizzare campi personalizzati nell'app per dispositivi mobili.

- **TSTimesheetDetails** - Il contratto dell'intestazione del foglio presenze.
- **TSTimesheetEntry** - Il contratto della transazione del foglio presenze. Gruppi di questi oggetti che hanno le stesse informazioni sul progetto e il valore **timesheetLineRecId** costituiscono una riga.

### <a name="fieldbasetype-types"></a>fieldBaseType (tipi)

La proprietà **FieldBaseType** nell'oggetto **TsTimesheetCustom** determina il tipo del campo visualizzato nell'app. Sono supportati i seguenti valori **Tipi**.

| Valore Tipi | Tipo              | Note |
|-------------|-------------------|-------|
| 0           | String (e Enum) | Il campo è visualizzato come campo di testo. |
| 1           | Intero           | Il valore è visualizzato come numero senza posizioni decimali. |
| 2           | Reale              | Il valore è visualizzato come numero con posizioni decimali.<p>Per visualizzare il valore real come valuta nell'app, utilizzare la proprietà **fieldExtenededType**. È possibile utilizzare la proprietà **numberOfDecimals** per impostare il numero di posizioni decimali visualizzate.</p> |
| 3           | Data              | I formati data sono determinati dall'impostazione **Formato data, ora e numeri** specificata sotto **Preferenze di lingua e paese** in **Opzioni utente**. |
| 4           | Booleano           | |
| 15          | GUID              | |
| 16          | Int64             | |

- Se la proprietà **stringOptions** non viene fornita nell'oggetto **TSTimesheetCustomField**, all'utente viene fornito un campo a testo libero.

    La proprietà **stringLength** può essere utilizzata per impostare la lunghezza di stringa massima che gli utenti possono immettere.

- Se la proprietà **stringOptions** viene fornita nell'oggetto **TSTimesheetCustomField**, tali elementi dell'elenco sono i soli valori che gli utenti possono selezionare utilizzando i pulsanti di opzione (pulsanti di scelta).

    In questo caso, il campo string può essere un valore enum per l'immissione dell'utente. Per salvare il valore nel database come enum, mappare di nuovo manualmente il valore string al valore enum prima del salvataggio utilizzando la catena di comando (vedere la sezione "Utilizzare la catena di comando nella classe di servizio TSTimesheetEntryService per salvare una voce del foglio presenze" in seguito in questo argomento per un esempio).

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a>fieldExtendedType (TSCustomFieldExtendedType)

È possibile utilizzare questa proprietà per formattare valori real come valuta. Questo approccio è applicabile solo quando il valore **fieldBaseType** è **Real**.

- **TSCustomFieldExtendedType:None** – Non viene applicata alcuna formattazione.
- **TSCustomFieldExtendedType::Currency** – Formatta il valore come valuta.

    Quando la formattazione della valuta è attiva, il campo **stringValue** può essere utilizzato per passare il codice valuta da visualizzare nell'app. Il valore è un valore di sola lettura.

    Il campo **realValue** contiene l'importo di denaro che deve essere salvato nel database.

### <a name="fieldsection-tscustomfieldsection"></a>fieldSection (TSCustomFieldSection)

È possibile utilizzare questa proprietà per specificare dove il campo personalizzato deve essere visualizzato nell'app.

- **TSCustomFieldSection::Header** - Il campo verrà visualizzato nella sezione **Visualizza ulteriori dettagli** nell'app. Questi campi sono sempre di sola lettura.
- **TSCustomFieldSection::Line** - Il campo verrà visualizzato dopo tutti i campi riga predefiniti nelle voci del foglio presenze. Questi campi possono essere modificabili o di sola lettura.

### <a name="fieldname-fieldnameshort"></a>fieldName (FieldNameShort)

Questa proprietà identifica il campo quando i valori che l'app fornisce vengono salvati di nuovo nel database.

### <a name="tablename-tablenameshort"></a>tableName (TableNameShort)

Questa proprietà identifica il campo quando i valori che l'app fornisce vengono salvati di nuovo nel database.

### <a name="iseditable-noyes"></a>isEditable (NoYes)

Impostare questa proprietà su **Sì** per specificare che il campo nella sezione delle voci del foglio presenze può essere modificato dagli utenti. Impostare la proprietà su **No** per rendere il campo di sola lettura.

### <a name="ismandatory-noyes"></a>isMandatory (NoYes)

Impostare questa proprietà su **Sì** per specificare che il campo nella sezione delle voci del foglio presenze deve essere obbligatorio.

### <a name="label-str"></a>label (str)

Questa proprietà specifica l'etichetta visualizzata accanto al campo nell'app.

### <a name="stringoptions-list-of-strings"></a>stringOptions (List of Strings)

Questa proprietà è applicabile solo quando **fieldBaseType** è impostata su **String**. Se **stringOptions** è impostata, i valori stringa disponibili per la selezione mediante i pulsanti di opzione (pulsanti di scelta) vengono specificati dalle stringhe nell'elenco. Se non si specificano stringhe, la voce a testo libero nel campo string è consentita (vedere la sezione "Utilizzare la catena di comando nella classe di servizio TSTimesheetEntryService per salvare una voce del foglio presenze" in seguito in questo argomento per un esempio).

### <a name="stringlength-int"></a>stringLength (int)

Questa proprietà specifica la lunghezza massima di un campo string. È applicabile solo quando **fieldBaseType** è impostata su **String**.

### <a name="numberofdecimals-int"></a>numberOfDecimals (int)

Questa proprietà specifica il numero di posizioni decimali visualizzato per un campo real. È applicabile solo quando **fieldBaseType** è impostata su **Real**.

### <a name="ordersequence-int"></a>orderSequence (int)

Questa proprietà controlla l'ordine in cui i campi personalizzati vengono visualizzati nell'app quando si specificano più campi personalizzati. I campi con numeri più bassi sono visualizzati per primi.

### <a name="booleanvalue-boolean"></a>booleanValue (boolean)

Per i campi di tipo **Boolean**, questa proprietà passa il valore Boolean del campo tra il server e l'app.

### <a name="guidvalue-guid"></a>guidValue (guid)

Per i campi di tipo **GUID**, questa proprietà passa il valore GUID del campo tra il server e l'app.

### <a name="int64value-int64"></a>int64Value (int64)

Per i campi di tipo **Int64**, questa proprietà passa il valore int64 del campo tra il server e l'app.

### <a name="intvalue-int"></a>intValue (int)

Per i campi di tipo **Int**, questa proprietà passa il valore int del campo tra il server e l'app.

### <a name="realvalue-real"></a>realValue (real)

Per i campi di tipo **Real**, questa proprietà passa il valore real del campo tra il server e l'app.

### <a name="stringvalue-str"></a>stringValue (str)

Per i campi di tipo **String**, questa proprietà passa il valore string del campo tra il server e l'app. È inoltre utilizzato per i campi di tipo **Real** formattati come valuta. Per tali campi, la proprietà viene utilizzata per passare il codice valuta all'app.

### <a name="datevalue-date"></a>dateValue (date)

Per i campi di tipo **Date**, questa proprietà passa il valore date del campo tra il server e l'app.

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a>Visualizzare e salvare un campo personalizzato nella sezione delle voci del foglio presenze

Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra la creazione di una voce del foglio presenze. Questa schermata mostra i campi predefiniti e un campo personalizzato nella sezione "Inserimento ore" denominata "Stringa di prova" con un valore enum "Seconda opzione" già impostato.

![Campo predefinito Stringa di prova nell'app](media/timesheet-entry.jpg)



Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra la selezione di una delle opzioni di enumerazione disponibili per il campo personalizzato "Stringa di prova".  Le due opzioni sono "Prima opzione "e "Seconda opzione" visualizzate come pulsanti di scelta. L'opzione Seconda opzione è quella selezionata.

![Pulsanti di opzione (pulsanti di scelta) per il campo personalizzato Stringa di prova](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a>Estendere la tabella TSTimesheetLine affinché abbia un campo personalizzato

Negli scenari comuni, è probabile che i dati per un campo personalizzato nella sezione delle voci del foglio presenze verranno salvati nella tabella TSTimesheetLine. Tuttavia, è possibile utilizzare altre tabelle se i dati possono essere recuperati in base al record TSTimesheetTrans fornito o se non hanno un contesto record specifico (ad esempio se il campo è di sola lettura nei parametri del progetto).

Si noti che i campi personalizzati non devono avere alcun record di database di supporto. I campi possono essere generati in modo dinamico in base alla logica X++. Tale approccio può risultare utile negli scenari di sola lettura (vedere la sezione "Utilizzare la catena di comando nel metodo buildCustomFieldListForHeader della classe TSTimesheetDetails per specificare i dettagli del foglio presenze" per un esempio di valori di campi personalizzati generati in modo dinamico).

Di seguito è riportata una schermata di Visual Studio che illustra la struttura a oggetti applicativi. La schermata raffigura un'estensione della tabella TSTimesheetLine con il campo TestLineString aggiunto come campo personalizzato.

![Stringa riga](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a>Utilizzare la catena di comando nel metodo buildCustomFieldList della classe TSTimesheetSettings per visualizzare un campo nella sezione delle voci del foglio presenze

Questo codice controlla le impostazioni di visualizzazione del campo nell'app. Ad esempio, controlla il tipo di campo, l'etichetta, se il campo è obbligatorio e la sezione in cui il campo viene visualizzato.

L'esempio seguente illustra un campo string nelle voci relative alle ore. Questo campo ha due opzioni, **Prima opzione** e **Seconda opzione**, disponibili tramite pulsanti di opzione (pulsanti di scelta). Il campo nell'app è associato al campo **TestLineString** che viene aggiunto alla tabella TSTimesheetLine.

Da notare l'utilizzo del metodo **TSTimesheetCustomField::newFromMetatdata()** per semplificare l'inizializzazione delle proprietà dei campi personalizzati: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** e **numberOfDecimals**. È anche possibile impostare tali parametri manualmente.

```xpp
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a>Utilizzare la catena di comando nel metodo buildCustomFieldListForEntry della classe TSTimesheetEntry per immettere valori in una voce del foglio presenze

Il metodo **buildCustomFieldListForEntry** viene utilizzato per immettere valori nelle righe del foglio presenze salvato nell'app per dispositivi mobili. Utilizza il record TSTimesheetTrans come parametro. I campi di quel record possono essere utilizzati per immettere il valore dei campi personalizzati nell'app.

```xpp
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a>Utilizzare la catena di comando nella classe TSTimesheetEntryService per salvare una voce del foglio presenze dall'app nel database

Per salvare di nuovo un campo personalizzato in un utilizzo tipico, è necessario estendere più metodi:

- Il metodo **timesheetLineNeedsUpdating** viene utilizzato per determinare se il record della riga è stato modificato dall'utente nell'app e deve essere salvato nel database. Se le prestazioni non sono una priorità, questo metodo può essere semplificato di modo che restituisca sempre **true**.
- I metodi **populateTimesheetLineFromEntryDuringCreate** e **populateTimesheetLineFromEntryDuringUpdate** possono essere estesi in modo che dei valori siano immessi nel record di database TSTimesheetLine dal record del contratto dati TSTimesheetEntry fornito. Nell'esempio riportato di seguito, notare come il mapping tra il campo del database e il campo di immissione viene eseguito manualmente tramite il codice X++.
- Il metodo **populateTimesheetWeekFromEntry** può anche essere esteso se il campo personalizzato mappato all'oggetto **TSTimesheetEntry** deve eseguire il writeback nella tabella di database TSTimesheetLineweek.

> [!NOTE]
> L'esempio seguente salva il valore **secondOption** o **firstOption** che l'utente seleziona per il database come valore string non elaborato. Se il campo del database è un campo di tipo **Enum**, questi valori possono essere mappati manualmente a un valore enum e quindi salvati in un campo enum nella tabella di database.

```xpp
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a>Visualizzare un campo personalizzato nella sezione dell'intestazione del foglio presenze

Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra un utente che visualizza un foglio presenze. Il pulsante "Ulteriori informazioni" è stato selezionato nell'angolo superiore destro per visualizzare l'opzione "Visualizza altri dettagli".  

![Comando Visualizza altri dettagli](media/show-more.png)

Di seguito è riportata una schermata dell'app per dispositivi mobili che illustra la sezione "Altro" di un foglio presenze. Un campo personalizzato denominato "Tasso di utilizzo di questo foglio presenze (campo personalizzato calcolato)" è stato aggiunto alla sezione dell'intestazione del foglio presenze. Il valore di sola lettura "0.667 "è impostato nel campo personalizzato.

![Sezione Altro](media/more-section.jpg)

### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a>Estendere la tabella TSTimesheetLine affinché abbia un campo personalizzato

Negli scenari comuni, è probabile che i dati per un campo personalizzato nella sezione dell'intestazione saranno acquisiti dalla tabella TSTimesheetHeader . Tuttavia, è possibile utilizzare altre tabelle se i dati possono essere recuperati in base al record TSTimesheetTable fornito o se non hanno un contesto record specifico (ad esempio se il campo è di sola lettura nei parametri del progetto).

Si noti che i campi personalizzati non devono avere alcun record di database di supporto. I campi possono essere generati in modo dinamico in base alla logica X++. Nell'esempio riportato di seguito mostra questo approccio.

I campi nella sezione dell'intestazione sono sempre di sola lettura nell'app.

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a>Utilizzare la catena di comando nel metodo buildCustomFieldList della classe TSTimesheetSettings per visualizzare un campo nella sezione dell'intestazione

Questo codice controlla le impostazioni di visualizzazione del campo nell'app. Ad esempio, controlla il tipo di campo, l'etichetta, se il campo è obbligatorio e la sezione in cui il campo viene visualizzato.

Nel seguente esempio viene illustrato un valore calcolato nella sezione dell'intestazione nell'app.

```xpp
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a>Utilizzare la catena di comando nel metodo buildCustomFieldListForHeader della classe TSTimesheetDetails per immettere i dettagli del foglio presenze

Il metodo **buildCustomFieldListForHeader** viene utilizzato per immettere dettagli dell'intestazione del foglio presenze nell'app per dispositivi mobili. Utilizza il record TSTimesheetTable come parametro. I campi di quel record possono essere utilizzati per immettere il valore dei campi personalizzati nell'app. Nel seguente esempio nessun valore viene letto dal database. Viene invece utilizzata la logica X++ per generare un valore calcolato che viene visualizzato nell'app.


```xpp
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a>Altre opportunità di configurabilità/estendibilità

### <a name="adding-additional-validation-for-the-app"></a>Aggiunta di convalida aggiuntiva per l'app

La logica esistente per la funzionalità del foglio presenze a livello del database continuerà a funzionerà come previsto. Per interrompere il completamento delle operazioni di salvataggio o invio e visualizzare uno specifico messaggio di errore, è possibile aggiungere **throw error("message to user")** al codice tramite l'estensione di una catena di comando. Di seguito sono riportati tre esempi di metodi estendibili utili:

- Se **validateWrite** nella tabella TSTimesheetLine restituisce **false** durante un'operazione di salvataggio per una riga del foglio presenze, viene visualizzato un messaggio di errore nell'app.
- Se **validateSubmit** nella tabella TSTimesheetTable restituisce **false** durante l'invio del foglio presenze nell'app, viene visualizzato un messaggio di errore.
- La logica che compila i campi (ad esempio **Proprietà riga**) durante il metodo **insert** nella tabella TSTimesheetLine verrà ancora eseguita.

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a>Nascondere e contrassegnare campi predefiniti come campi di sola lettura mediante la configurazione

A partire dai parametri di progetto, è possibile impostare i campi predefiniti come campi di sola lettura o nasconderli nell'app. Impostare le opzioni nella sezione **Fogli presenze per dispositivi mobili** della scheda **Foglio presenze** nella pagina **Parametri Gestione progetti e contabilità**.

![Parametri progetto](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a>Modifica delle attività selezionabili tramite le estensioni

Le attività selezionabili per un progetto vengono immesse mediante i metodi **getActivitiesForProject()** and **getActivityQuery()** nella classe **TsTimesheetProjectService**. È possibile utilizzare la catena di comando per modificare questo comportamento e associare lo scenario aziendale alle attività selezionabili per un progetto specifico.

### <a name="entering-a-default-project-category-on-timesheet-entries"></a>Immissione di una categoria di progetto predefinita nelle voci del foglio presenze

L'immissione di una categoria di progetto predefinita nelle voci del foglio presenze si verifica su tre livelli. È possibile utilizzare la catena di comando per estendere il comportamento a uno di questi livelli o a tutti per ottenere il comportamento desiderato. Viene utilizzata la gerarchia seguente:

1. L'app tenta di inserire la categoria predefinita dalla risorsa di progetto. Questa categoria predefinita viene impostata nei metodi **getCurrentUserResource** e **getDelegatedResourcesForCurrentUser** della classe **TSTimesheetSettingsService**.
2. Se la categoria predefinita non viene specificata a livello di risorsa del progetto, l'app tenta di acquisirla dall'attività di progetto. Questa categoria predefinita viene impostata nel metodo **getActivitiesForProject** della classe **TSTimesheetProjectService**.
3. Se la categoria predefinita non viene specificata a livello di attività del progetto, viene acquisita dai parametri del progetto. Questa categoria predefinita viene impostata nel metodo **getProjectDetailsbyRule** della classe **TSTimesheetProjectService**.
