---
title: Rubrica globale e parte
description: In questo articolo vengono descritte le funzionalità della parte e della rubrica globale della doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 08/02/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 7f06b6e69b76bf12092fdceca5b45a6750b52233
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228992"
---
# <a name="party-and-global-address-book"></a>Rubrica globale e parte

[!include [banner](../../includes/banner.md)]



*Parte* e *rubrica globale* sono concetti delle applicazioni di finanza e operazioni. Una parte può essere una persona o un'organizzazione. È conveniente archiviare e gestire globalmente le proprietà di una parte, come nome, lingua, contatti e indirizzi. Quindi, quando il valore di una proprietà viene cambiato in un punto, il cambiamento si riflette in tutti i punti in cui la parte è coinvolta.

## <a name="party"></a>Parte

Una parte è una persona o un'organizzazione coinvolta in un'azienda. Utilizzando il concetto di parte, una persona o un'organizzazione può svolgere più di un ruolo (ad esempio lavoratore, cliente, fornitore o contatto) in un'azienda. Il ruolo si basa sul contesto e sull'ambito. Di seguito sono riportati alcuni esempi di ruoli di due società fittizie, Contoso e Fabrikam:

+ **Lavoratore**: Un dipendente. Un esempio è un dipendente di Contoso.
+ **Fornitore**: un'organizzazione fornitore o un unico proprietario che fornisce beni o servizi a un'azienda. Ad esempio, se Fabrikam vende forniture a Contoso, Fabrikam è un fornitore di Contoso.
+ **Contatto**: Una persona da contattare. Ad esempio, se Contoso acquista forniture da Fabrikam, i dipendenti di Contoso contatteranno il contatto di Fabrikam.
+ **Cliente**: una persona o un'azienda che acquista cose da un'azienda. Ad esempio, se Contoso acquista forniture da Fabrikam, Contoso è un cliente di Fabrikam.

Il modello della parte viene spesso utilizzato per rappresentare relazioni da medie a complesse tra organizzazioni e persone, in particolare quando una parte svolge più di un ruolo. Di seguito sono riportati alcuni esempi comuni:

+ Una parte può essere sia un cliente che un fornitore. Ad esempio, in Nord America, Fabrikam vende cavi elettrici a Contoso e acquista altoparlanti assemblati da Contoso. In Europa, Fabrikam vende parti a Contoso, ma non acquista nulla da Contoso.
+ Una parte può essere sia un dipendente che un cliente. Ad esempio, un dipendente di Contoso acquista componenti elettronici da Contoso per uso personale.
+ Può esserci una relazione molti-a-molti (N:N) tra una persona e un'organizzazione. Ad esempio, Fabrikam fornisce specialisti del servizio e impiega un coordinatore per il posizionamento. Il coordinatore di posizionamento abbina gli specialisti del servizio alle richieste di lavoro di diversi clienti di Fabrikam. Contoso è uno dei clienti di Fabrikam. Quando Contoso ha bisogno di uno specialista del servizio, contatta il coordinatore di posizionamento, che soddisfa la richiesta. Poiché il coordinatore del posizionamento gestisce le richieste per tutti i clienti, è coinvolta una relazione N:N.

L'immagine seguente mostra il modello di dati per la parte.

![Modello di dati per la parte.](media/party-gab-image1.png)

> [!TIP]
> Quando tenti di creare un nuovo record di conto, utilizza il campo **Parte** per cercare il record in base al nome. In questo modo, se trovi il record, devi solo selezionarlo. Il sistema compila quindi automaticamente tutti i dati della parte. Non è necessario impostare manualmente tutti i campi obbligatori. Questo comportamento può essere trovato nelle pagine predefinite **Conto**, **Contatto** e **Fornitore**.

Non tutti i ruoli di parte delle app per la finanza e le operazioni sono supportati dalla doppia scrittura. Per un elenco completo dei ruoli della parte, vedi [Panoramica della rubrica globale](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Rubrica globale

La rubrica globale è un elenco di indirizzi postali ed elettronici delle organizzazioni e degli individui che fanno parte di un'azienda.

La rubrica globale memorizza e gestisce tutti gli indirizzi postali e elettronici in base alle esigenze. Ad esempio, Fabrikam dispone di distributori di benzina in 50 località. Ogni località ha un indirizzo postale, un indirizzo e-mail e un numero di telefono diversi. Tutti gli acquisti aziendali vengono fatturati alla stazione di servizio principale, ma spediti direttamente alla stazione di servizio specifica che ha richiesto l'acquisto. La rubrica globale memorizza la stazione di servizio principale come indirizzo di fatturazione per Fabrikam e ogni stazione di servizio come indirizzo di spedizione. Gli indirizzi possono essere memorizzati una volta e recuperati secondo necessità per offerte e ordini.

A seconda del contesto aziendale, una persona o un'organizzazione potrebbe svolgere più di un ruolo e lo stesso indirizzo postale e indirizzo elettronico potrebbe essere utilizzato per tutti i ruoli. In questo caso, un cambio di indirizzo in un ruolo deve apparire in tutti gli altri ruoli. La rubrica globale memorizza e gestisce gli indirizzi a livello globale.

Nella figura seguente è illustrato il modello di dati per la rubrica globale.

![Modello di dati per la rubrica globale.](media/party-gab-image2.png)

## <a name="contact"></a>Contatti

Nelle app Customer Engagement, un contatto è una persona. Tuttavia, la tabella **Contatto** è stata utilizzata per rappresentare una persona, un utente del portale, un cliente B2C o un fornitore. La rappresentazione è implicita e non è possibile capire la differenza senza esaminare le transazioni correlate. La tabella **Contatto** è stata limitata a una relazione uno-a-uno (1:1) con la tabella **Conto**. Come parte del modello parte e rubrica globale, la doppia scrittura introduce proprietà esplicite per la classificazione e consente relazioni N:N tra un contatto che è una persona e un'organizzazione (entità **Conto** o **Fornitore**).

Sono disponibili due tipi di righe **Contatto**:

+ **Contatto con striping**: riga **Contatto** dove il campo **Società** ha un valore obbligatorio.
+ **Contatto senza striping**: riga **Contatto** con il campo **Società** vuoto.

La tabella **Contatto** può memorizzare questi tipi di righe.

| Tipo di riga | descrizione |
|----------|-------------|
| Una persona che è un cliente, ad esempio un contatto vendibile o un cliente B2C. | Un record di contatto con striping in cui il campo **Società** non è vuoto e il campo **Cliente** è impostato su **Sì**. |
| Una persona che è un fornitore, ad esempio, un unico proprietario come fornitore. | Un record di contatto con striping in cui il campo **Società** non è vuoto e il campo **Fornitore** è impostato su **Sì**. |
| Una persona che è sia un cliente che un fornitore. | Un record di contatto con striping in cui il campo **Società** non è vuoto e il campo **Cliente** è impostato su **Sì** e il campo **Fornitore** è impostato su **Sì**. Una persona può essere sia produttore di un prodotto che consumatore di un altro prodotto. Le app per la finanza e le operazioni e la doppia scrittura supportano questa relazione. |
| Una persona che è un contatto per un'organizzazione, ma non è cliente né fornitore. | Un record di contatto senza striping in cui il campo **Società** è vuoto e il campo **Cliente** è impostato su **No** e il campo **Fornitore** è impostato su **No**. |

## <a name="contact-for-party-table"></a>Tabella Contatto per la parte

La tabella **Contatto per la parte** memorizza e gestisce relazioni N:N tra le righe **Conto** e le righe **Contatto**. Può filtrare le righe **Contatto** con striping da righe senza striping e associare solo le righe senza striping **Contatto** alle righe **Conto** o **Fornitore**.

Ad esempio, Natasha Jones e Miguel Reyes sono veterinari che si occupano di allevamenti nelle loro aree. Natasha serve l'area di Seattle e Miguel serve l'area del Kent. Nell'app Customer Engagement, gli allevamenti sono rappresentati come clienti e i veterinari sono rappresentati come contatti. Un unico record **Contatto** per Natasha è associato a tutti gli allevamenti con cui lavora Natasha. Analogamente, un unico record **Contatto** per Miguel è associato a tutti gli allevamenti con cui lavora Miguel.

Queste relazioni vengono archiviate nella tabella **Contatto per la parte**. Puoi trovare le informazioni nelle pagine predefinite **Conto**, **Contatto** e **Fornitore**.

+ Nella pagina **Conto** è possibile utilizzare la scheda **Contatti associati** per associare uno o più contatti alla riga **Conto**. In questo modo assegni le persone di contatto per un'organizzazione. È quindi possibile selezionare un contatto come contatto principale per il conto. Se usi la pagina **Creazione rapida** è possibile selezionare solo una persona di contatto. Il comportamento è lo stesso quando si utilizza la pagina **Fornitore** e il tipo di record è **Organizzazione**.
+ Nella pagina **Contatto**, quando la riga è un cliente, un fornitore o entrambi (un contatto con striping), puoi utilizzare la scheda **Contatti associati** per associare uno o più contatti. In questo modo assegni per persone di contatto un cliente o fornitore B2C. È quindi possibile selezionare un contatto come contatto principale. Se usi la pagina **Creazione rapida** è possibile selezionare solo una persona di contatto.
+ Nella pagina **Contatto**, quando la riga è una persona di contatto (contatto senza striping), puoi utilizzare la scheda **Organizzazioni associate** per associare uno o più clienti o fornitori. In questo modo assegni clienti o fornitori alla persona di contatto sottostante. Il cliente o il fornitore può essere un'organizzazione, una persona o entrambi. Puoi selezionare un valore solo in uno dei quattro campi alla volta.

    + Se selezioni un valore nel campo **ID parte**, il contatto sottostante viene assegnato a tutti i ruoli della parte scelta.
    + Se selezioni un valore nel campo **Contatto associato**, stai selezionando il contatto con striping del tipo **Persona**.
    + Se selezioni un valore nel campo **Conto associato** o **Fornitore associato**, stai selezionando un'organizzazione.

    ![Scheda Organizzazioni associate nella pagina Contatto.](media/party-gab-image3.png)

    Indipendentemente dalla tua scelta, l'associazione viene creata a livello di parte e applicabile a tutti i ruoli della parte e archiviata nell'entità **Contatto per la parte**.

> [!NOTE]
> Il nome visualizzato per la tabella **Contatto per la parte** nelle app Customer Engagement è **Contatto per cliente/fornitore**.

Quando apri una riga **Contatto** dove sia il campo **Cliente** che **Fornitore** sono impostati su **No**, la scheda **Organizzazioni associate** viene visualizzata. Utilizzare questa scheda per associare al contatto una o più organizzazioni di clienti o fornitori.

Quando apri una riga **Contatto** dove o il campo **Cliente** o **Fornitore** è impostato su **Sì**, la scheda **Contatti associati** viene visualizzata. Usa questa scheda per associare uno o più contatti.

## <a name="postal-addresses"></a>Indirizzi postali

Una nuova scheda **Indirizzi** è stata introdotta nelle pagine **Conto**, **Contatto** e **Fornitore**. Questa scheda supporta più indirizzi postali utilizzando una griglia, come mostrato nell'illustrazione seguente.

![Griglia per indirizzi postali.](media/party-gab-image4.png)

La griglia include le colonne seguenti:

+ **Ruoli indirizzo postale**: lo scopo dell'indirizzo postale.
+ **Primario** - Un valore che indica se l'indirizzo è l'indirizzo principale.
+ **Numero indirizzo** - L'ordine degli indirizzi.

Puoi usare il pulsante **Nuovo indirizzo** sopra la griglia per creare tutti gli indirizzi postali che desideri.

Nelle app di interazione con i clienti, quando un utente immette gli indirizzi nella scheda **Riepilogo** della pagina **Account**, i campi **Indirizzo 1** e **Indirizzo 2** corrispondono rispettivamente agli indirizzi **Consegna** e **Fattura**. Tuttavia, quando un utente crea un indirizzo postale nelle app per la finanza e le operazioni, i primi due indirizzi del record cliente verranno visualizzati nei campi **Indirizzo 1** e **Indirizzo 2** e l'utente avrà la possibilità di modificare lo scopo dell'indirizzo in **Consegna** e **Fattura**.

![Scheda Riepilogo per indirizzi postali.](media/party-gab-image5.png)

Analogamente, i campi **Indirizzo 1**, **Indirizzo 2** e **Indirizzo 3** della scheda **Riepilogo** della pagina **Contatto** corrispondono rispettivamente agli indirizzi **Azienda**, **Consegna** e **Fattura**.

## <a name="electronic-addresses"></a>Indirizzi elettronici

Una nuova scheda **Indirizzi elettronici** è stata introdotta nelle pagine **Conto**, **Contatto** e **Fornitore**. Questa scheda supporta più indirizzi elettronici utilizzando una griglia, come mostrato nell'illustrazione seguente.

![Griglia per indirizzi elettronici.](media/party-gab-image6.png)

La griglia include le colonne seguenti:

+ **Tipo** - Il tipo di indirizzo elettronico.
+ **Primario** - Un valore che indica se l'indirizzo è l'indirizzo principale.
+ **Scopo** - Lo scopo dell'indirizzo elettronico.

Puoi usare il pulsante **Nuovo indirizzo elettronico** sopra la griglia per creare tutti gli indirizzi postali che desideri.

Durante il processo di qualificazione dei lead puoi fornire sia un numero di telefono aziendale che un numero di cellulare. Il numero di telefono aziendale è considerato il numero di telefono principale se **IsMobile=No** e il numero di cellulare è considerato il numero di telefono secondario se **IsMobile=Sì**.

> [!TIP]
> Usa le schede **Indirizzi** e **Indirizzi elettronici** nei moduli **Account** e **Contatti** per gestire gli indirizzi postali ed elettronici. Questo assicura che i dati degli indirizzi si sincronizzino con le app per la finanza e le operazioni.

## <a name="setup"></a>Impostazione

1. Aprire l'ambiente dell'app Customer Engagement.

2. Installa tutte le soluzioni prerequisito, come descritto in [Pacchetto separato di orchestrazione dell'applicazione a doppia scrittura](separated-solutions.md).

3. Installa le [soluzioni di doppia scrittura per parte e rubrica globale](https://aka.ms/dual-write-gab).

4. Aprire l'app per finanza e operazioni. Passare al modulo Gestione dati e selezionare la scheda Doppia scrittura. Viene visualizzata la pagina di amministrazione della doppia scrittura.

5. Applicare entrambe le soluzioni installate nei passaggi 2 e 3 utilizzando la funzione [Applica soluzione](link-your-environment.md).

6. Interrompi le seguenti mappe, perché non sono più necessarie. Invece, esegui la mappa `Contacts V2 (msdyn_contactforparties)`.

    + Contatti CDS V2 e Contatti (si riferisce ai contatti del cliente)
    + Contatti CDS V2 e Contatti (si riferisce ai contatti del fornitore)

7. I seguenti mapping di entità vengono aggiornati per la funzionalità della parte, quindi l'ultima versione deve essere applicata a questi mapping.

    Mappa | Aggiorna a questa versione | Modifiche
    ---|---|---
    `CDS Parties (msdyn_parties)`| 1.0.0.2 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Contacts V2 (msdyn_contactforparties)`| 1.0.0.6 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Customers V3 (accounts)` | 1.0.0.5 |Rimossi i campi `PartyNumber` e altri campi relativi alla parte come nome, dettagli personali, indirizzo postale, e indirizzo elettronico di contatto.
    `Customer V3 (contacts)` | 1.0.0.5 | Rimossi i campi `PartyNumber` e altri campi relativi alla parte come nome, dettagli personali, indirizzo postale, e indirizzo elettronico di contatto.
    `Vendors V2 (msdyn_vendors)` | 1.0.0.6 | Rimossi i campi `PartyNumber` e altri campi relativi alla parte come nome, dettagli personali, indirizzo postale, e indirizzo elettronico di contatto.
    `CDS Sales quotation headers (quotes)` | 1.0.0.7 | Sostituita la persona di contatto con il riferimento `ContactforParty`.
    `Sales invoice headers V2 (invoices)` | 1.0.0.4 | Sostituita la persona di contatto con il riferimento `ContactforParty`.
    `CDS Sales order headers (salesorders)` | 1.0.0.5 | Sostituita la persona di contatto con il riferimento `ContactforParty`.
    `CDS Party postal address locations (msdyn_partypostaladdresses)` | 1.0.0.1  | Questa è una nuova mappa aggiunta come parte di questa versione.
    `CDS postal address history V2 (msdyn_postaladdresses)` | 1.0.0.2 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `CDS postal address locations (msdyn_postaladdresscollections)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Party Contacts V3 (msdyn_partyelectronicaddresses)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Complimentary Closings (msdyn_compliemntaryclosings)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Decision making roles (msdyn_decisionmakingroles)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Loyalty levels (msdyn_loyaltylevels)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Contact person titles (msdyn_salescontactpersontitles)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Personal character types (msdyn_personalcharactertypes)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Salutations (msdyn_salutations)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `Employment job functions (msdyn_employmentjobfunctions)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.
    `CDS Address roles (msdyn_addressroles)` | 1.0.0.0 | Questa è una nuova mappa aggiunta come parte di questa versione.

8. Prima di eseguire le mappe precedenti, è necessario aggiornare manualmente le chiavi di integrazione come descritto nei passaggi seguenti. Quindi selezionare **Salva**.

    | Mappa | Chiavi |
    |-----|------|
    | Conto |  accountnumber [Numero conto]<br>msdyn_company.cdm_companycode [Società (Codice società)] |
    | Contatto | msdyn_contactpersonid [Numero conto/ID persona contatto]<br>msdyn_company.cdm_companycode [Società (Codice società)] |
    | Contatto per cliente/fornitore | msdyn_contactforpartynumber [Contatto per numero parte]<br>msdyn_associatedcompanyid.cdm_companycode [Società associata (Codice società)] |
    | Fornitore | msdyn_vendoraccountnumber [Numero conto fornitore]<br>msdyn_company.cdm_companycode [Società (Codice società)]|

9. In Dataverse, i limiti di caratteri delle regole di rilevamento duplicati sono aumentati da 450 a 700 caratteri. Questo limite consente di aggiungere una o più chiavi alle regole di rilevamento dei duplicati. Espandere la regola di rilevamento duplicati per la tabella **Conti** impostando i seguenti campi.

    | Campo | Valore |
    |-------|-------|
    | Nome | Conti con lo stesso nome conto. |
    | descrizione | Rileva i record di conto che hanno lo stesso valore nell'attributo Nome conto. |
    | Tipo di record di base | Conto |
    | Tipo di record corrispondente | Conto |
    | Nome conto (campo) | Corrispondenza esatta |
    | Società (campo) | Corrispondenza esatta |
    | Tipo di relazione (campo) | Corrispondenza esatta |
    | ID parte (campo) | Corrispondenza esatta |
    | Seleziona (campo) | (vuoto) |

    ![Regola duplicati per i conti.](media/duplicate-rule-1.PNG)

10. Espandere la regola di rilevamento duplicati per la tabella **Contatti** impostando i seguenti campi.

    | Campo | Valore |
    |-------|-------|
    | Nome | Contatti con lo stesso nome e cognome. |
    | descrizione | Rileva i record di contatto che hanno gli stessi valori nei campi Nome e Cognome. |
    | Tipo di record di base | Contatto |
    | Tipo di record corrispondente | Contatto |
    | Nome (campo) | Corrispondenza esatta |
    | Cognome (campo) | Corrispondenza esatta |
    | Società (campo) | Corrispondenza esatta |
    | ID parte (campo) | Corrispondenza esatta |
    | Seleziona (campo) | (vuoto) |

    ![Regola duplicati per i contatti.](media/duplicate-rule-2.PNG)

11. Se sei già un utente con doppia scrittura, segui le istruzioni in [Eseguire l'aggiornamento al modello di parte e di rubrica globale](upgrade-party-gab.md) e aggiorna i tuoi dati. **Non procedere al passaggio 12 senza completare questo passaggio:** Se sei un nuovo utente con doppia scrittura, procedere al passaggio 12.

12. Se sei un utente esistente che usa la doppia scrittura, completa il passaggio 11, quindi esegui le mappe nel seguente ordine. Se sei un nuovo cliente con doppia scrittura, puoi procedere direttamente. Se viene visualizzato un messaggio di errore che indica "Convalida del progetto non riuscita. Campo destinazione mancante ...", apri la mappa e seleziona **Aggiorna tabelle**, quindi esegui la mappa.

    App per la finanza e le operazioni | App di interazione con i clienti  
    ----------------------------|------------------------
    [Parti CDS](mapping-reference.md#220) | msdyn_parties
    [Ubicazioni dell'indirizzo postale CDS](mapping-reference.md#234) | msdyn_postaladdresscollections
    [Storico indirizzo postale CDS V2](mapping-reference.md#235) | msdyn_postaladdresses
    [Ubicazioni dell'indirizzo postale della parte CDS](mapping-reference.md#233) | msdyn_partypostaladdresses
    [Contatti parte V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses
    [Clienti V3](mapping-reference.md#101) | conti
    [Clienti V3](mapping-reference.md#116) | contatti
    [Fornitori V2](mapping-reference.md#202) | msdyn_vendors
    [Titoli contatti](mapping-reference.md#223) | msdyn_salescontactpersontitles
    [Formule di chiusura](mapping-reference.md#222) | msdyn_complimentaryclosings
    [Formule di apertura](mapping-reference.md#228) | msdyn_salutations
    [Ruoli nel processo decisionale](mapping-reference.md#224) | msdyn_decisionmakingroles
    [Funzioni lavorative impiego](mapping-reference.md#225) | msdyn_employmentjobfunctions
    [Livelli fedeltà](mapping-reference.md#226) | msdyn_loyaltylevels
    [Tipi di carattere personale](mapping-reference.md#227) | msdyn_personalcharactertypes
    [Contatti V2](mapping-reference.md#221) | msdyn_contactforparties
    [Intestazione offerta di vendita CDS](mapping-reference.md#215) | offerte
    [Intestazioni ordine cliente CDS](mapping-reference.md#217) | salesorders
    [Intestazioni fattura di vendita V2](mapping-reference.md#118) | fatture
    [Ruoli indirizzo CDS](mapping-reference.md#301) | msdyn_addressroles

> [!NOTE]
> La mappa `CDS Contacts V2 (contacts)` è la mappa che hai interrotto nel passaggio 1. Quando si tenta di eseguire altre mappe, queste 2 mappe potrebbero essere visualizzate nell'elenco delle dipendenze. Non eseguire queste mappe.
>
> Se è installata la soluzione parte e rubrica globale, è necessario disabilitare il plugin denominato `Microsoft.Dynamics.SCMExtended.Plugins.Plugins.LeadPrimaryContactPostCreate: QualifyLead of lead`. Se è disinstallata la soluzione parte e rubrica globale, è necessario riabilitare il pluging .
>
> Il campo `msdyn_*partynumber` (un campo di testo a riga singola) incluso nelle tabelle **Conto**, **Contatto** e **Fornitore** non dovrebbero essere utilizzate in futuro. Il nome dell'etichetta ha il prefisso **(Deprecato)** per chiarezza. Utilizza invece il campo **msdyn_partyid**. Il campo è una ricerca nella tabella **msdyn_party**.
>
> Nome tabella | Vecchio campo | Nuovo campo
> --------|-------|--------
> Conto | `msdyn_partynumber` | `msdyn_partyid`
> Contatto | `msdyn_partynumber` | `msdyn_partyid`
> msdyn_vendor | `msdyn_vendorpartynumber` | `msdyn_partyid`

## <a name="templates"></a>Modelli

Una raccolta di mappe della tabella funziona in combinazione durante l'interazione con la parte e la rubrica globale, come illustrato nella seguente tabella.

| App per la finanza e le operazioni | App di interazione con i clienti | Description |
|----------------------------|-------------------------|-------------|
| [Titoli contatti](mapping-reference.md#223) | msdyn\_salescontactpersontitles |
| [Clienti V3](mapping-reference.md#101) | conti |
| [Clienti V3](mapping-reference.md#116) | contatti |
| [Parti CDS](mapping-reference.md#220) | msdyn\_parties |
| [Ubicazioni dell'indirizzo postale della parte CDS](mapping-reference.md#233) | msdyn\_partypostaladdresses |
| [Storico indirizzo postale CDS V2](mapping-reference.md#235) | msdyn\_postaladdresses |
| [Ubicazioni dell'indirizzo postale CDS](mapping-reference.md#234) | msdyn\_postaladdresscollections |
| [Intestazione offerta di vendita CDS](mapping-reference.md#215) | offerte |
| [Intestazioni ordine cliente CDS](mapping-reference.md#217) | salesorders |
| [Formule di chiusura](mapping-reference.md#222) | msdyn\_complimentaryclosings |
| [Contatti V2](mapping-reference.md#221) | msdyn\_contactforparties |
| [Ruoli nel processo decisionale](mapping-reference.md#224) | msdyn\_decisionmakingroles |
| [Funzioni lavorative impiego](mapping-reference.md#225) | msdyn\_employmentjobfunctions |
| [Livelli fedeltà](mapping-reference.md#226) | msdyn\_loyaltylevels |
| [Contatti parte V3](mapping-reference.md#236) | msdyn\_partyelectronicaddresses |
| [Tipi di carattere personale](mapping-reference.md#227) | msdyn\_personalcharactertypes |
| [Intestazioni fattura di vendita V2](mapping-reference.md#118) | fatture |
| [Formule di apertura](mapping-reference.md#228) | msdyn\_salutations |
| [Fornitori V2](mapping-reference.md#202) | msdyn\_vendors |
| [Ruoli indirizzo CDS](mapping-reference.md#301) |msdyn\_addressroles|

Per ulteriori informazioni, vedere [Riferimento per il mapping a doppia scrittura](mapping-reference.md).

## <a name="address-roles-as-a-multi-select-drop-down-list"></a>Ruoli indirizzo come un elenco a discesa a selezione multipla
Un indirizzo postale o un indirizzo elettronico può servire a più di uno scopo. Ad esempio, un indirizzo postale può fungere sia da indirizzo di fatturazione che da indirizzo di consegna. In questi casi, un utente può selezionare entrambi **Fattura** e **Consegna** nell'elenco a discesa, come mostrato nell'illustrazione seguente. 

![Elenco a discesa Scopo/ruolo.](media/purpose.png)

## <a name="known-issues-and-limitations"></a>Problemi noti e limitazioni

+ Nelle app per la finanza e le operazioni, quando crei un cliente insieme all'indirizzo e lo salvi, l'indirizzo potrebbe non sincronizzarsi nella tabella **Indirizzo**. Ciò è dovuto a un problema di sequenza della piattaforma a doppia scrittura. Come soluzione alternativa, crea prima il cliente e salvalo. Quindi aggiungi l'indirizzo.
+ Nelle app per la finanza e le operazioni, quando un record cliente ha un indirizzo principale e crei un nuovo contatto per quel cliente, il record del contatto eredita un indirizzo principale dal record cliente associato. Questo accade anche per il contatto del fornitore. Dataverse attualmente non supporta questo comportamento. Se la doppia scrittura è abilitata, un contatto cliente ereditato con un indirizzo principale dall'app per la finanza e le operazioni è sincronizzato con Dataverse insieme al suo indirizzo.
+ Nelle app per la finanza e le operazioni puoi creare un record di contatto dal modulo **Aggiungi contatto**. Quando si tenta di creare un nuovo contatto dal modulo **Visualizza contatto**, l'azione non riesce. Questo è un problema noto.

    ![Problema noto con Aggiungi contatto.](media/party-gab-contact-issue.png)

+ **Sincronizzazione iniziale** non supporta i campi di data/ora **Disponibile da** e **Disponibile fino a** in **ContactForParty**, perché DIXF converte il valore in una stringa anziché in un numero intero. La conversione attiva l'errore `Cannot convert the literal '<say 08:00:00>' to the expected type edm.int32`.
+ Non puoi immettere un indirizzo postale con validità postdatata utilizzando un'app per la finanza e le operazioni con doppia scrittura, perché Dataverse non supporta la validità della data. Se inserisci un indirizzo postale con data futura utilizzando un'app per la finanza e le operazioni, si sincronizza con Dataverse completamente e vedrai immediatamente l'indirizzo sull'interfaccia utente. Qualsiasi aggiornamento a questo record comporterà un errore poiché è postdatato e non è corrente nell'app per la finanza e le operazioni.
