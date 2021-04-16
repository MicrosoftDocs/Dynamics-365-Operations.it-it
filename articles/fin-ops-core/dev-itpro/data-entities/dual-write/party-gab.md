---
title: Rubrica globale e parte
description: In questo argomento vengono descritte le funzionalità della parte e della rubrica globale della doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 02/22/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: e7bec58f8094a1448017822e7d8840368cc482b8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750790"
---
# <a name="party-and-global-address-book"></a>Rubrica globale e parte

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Parte e rubrica globale sono concetti delle applicazioni Finance and Operations. Una parte può essere una persona o un'organizzazione. È conveniente archiviare e gestire globalmente le proprietà di una **parte**, come nome, lingua, contatti e indirizzi. Quando il valore di una proprietà cambia in un punto, si riflette in tutti i punti in cui la **parte** è coinvolta.

## <a name="party"></a>Parte

Una *parte* è una persona o un'organizzazione coinvolta nell'azienda. Utilizzando il concetto di parte, una persona o un'organizzazione può svolgere più di un ruolo (lavoratore, cliente, fornitore o contatto) in un'azienda. Il ruolo si basa sul contesto e sull'ambito. Di seguito sono riportati alcuni esempi di due società fittizie, Contoso e Fabrikam.

+ **Lavoratore**: Un dipendente. Ad esempio, un dipendente di Contoso.
+ **Fornitore**: un'organizzazione fornitore o un unico proprietario che fornisce beni o servizi a un'azienda. Ad esempio, se Fabrikam vende forniture a Contoso, Fabrikam ricopre il ruolo di fornitore.
+ **Contatto**: Una persona da contattare. Ad esempio, se Contoso acquista forniture da Fabrikam, un dipendente di Contoso contatterà il contatto di Fabrikam.
+ **Cliente**: Un cliente è una persona o un'azienda che acquista cose da un'azienda. Ad esempio, se Contoso acquista forniture da Fabrikam, Contoso è un cliente di Fabrikam.

Il modello della parte viene spesso utilizzato per rappresentare relazioni di media complessità tra organizzazioni e persone, in particolare quando una parte svolge più di un ruolo. Di seguito sono riportati alcuni esempi comuni:

+ Una parte può essere sia un cliente che un fornitore. Ad esempio, in Nord America, Fabrikam vende cavi elettrici a Contoso e acquista altoparlanti assemblati da Contoso. In Europa, Fabrikam vende parti a Contoso, ma non acquista nulla da Contoso.
+ Una parte può essere sia un dipendente che un cliente. Ad esempio, un dipendente di Contoso acquista componenti elettronici da Contoso per uso personale.
+ Può esserci una relazione molti-a-molti tra una persona e un'organizzazione. Ad esempio, Fabrikam fornisce specialisti del servizio e impiega un coordinatore per il posizionamento. Il coordinatore abbina gli specialisti del servizio alle richieste di lavoro di diversi clienti di Fabrikam. Contoso è uno degli account cliente. Quando Contoso ha bisogno di uno specialista, Contoso contatta il coordinatore, che quindi facilita la richiesta. Il coordinatore gestisce le richieste per tutti i clienti, creando una relazione molti a molti.

L'immagine seguente mostra il modello di dati per la parte:

![Modello di dati per parte](media/party-gab-image1.png)

> [!Tip]
> Quando tenti di creare un nuovo record di account, utilizza il campo "Parte" per cercare il record in base al nome. Nel caso in cui trovi il record, devi solo selezionarlo. Il sistema inserisce automaticamente tutti i dati della parte. Non è necessario inserire manualmente tutti i campi obbligatori. Questo comportamento può essere trovato nei moduli Conto, Contatto e Fornitore forniti per impostazione predefinita.

Non tutti i ruoli di parte delle app Finance and Operations sono supportati dalla doppia scrittura. Per un elenco completo dei ruoli della parte, vedi [Panoramica della rubrica globale](../../../fin-ops/organization-administration/overview-global-address-book.md).

### <a name="global-address-book"></a>Rubrica globale

La rubrica globale è un elenco di indirizzi postali ed elettronici delle organizzazioni e degli individui che fanno parte di un'azienda.

La rubrica globale memorizza e gestisce tutti gli indirizzi postali e elettronici necessari. Supponiamo, ad esempio, che Fabrikam disponga di distributori di benzina in 50 località. Ogni località ha un indirizzo postale, un'e-mail e un numero di telefono diversi. Tutti gli acquisti aziendali vengono fatturati alla stazione di servizio principale, ma gli acquisti vengono spediti direttamente alla stazione di servizio specifica che ha richiesto l'acquisto. La rubrica globale memorizza la stazione di servizio principale come indirizzo di fatturazione e ogni stazione di servizio come indirizzo di spedizione per Fabrikam. Gli indirizzi possono essere memorizzati una volta e recuperati secondo necessità per offerte e ordini.

Una persona o un'organizzazione può svolgere più di un ruolo in base al contesto aziendale. In tal caso, i loro indirizzi postali ed elettronici potrebbero essere gli stessi. Quindi, un cambio di indirizzo in un ruolo deve apparire nell'altro ruolo e viceversa. La rubrica globale memorizza e gestisce gli indirizzi a livello globale.

![Modello di dati per la rubrica globale](media/party-gab-image2.png)

## <a name="contacts"></a>Contatti

Nelle app Customer Engagement, un *Contatto* è una persona. La tabella **Contatto** è stata utilizzata per rappresentare una persona, un utente del portale, un cliente B2C o un fornitore. La rappresentazione è implicita e non è possibile capire la differenza senza esaminare le transazioni correlate. La tabella **Contatto** è stata limitata per avere una relazione 1:1 con la tabella **Conto**. Come parte del modello parte e rubrica globale, la doppia scrittura introduce proprietà esplicite per la classificazione e la doppia scrittura consente relazioni N:N tra un **Contatto** e un'organizzazione (entità conto o entità fornitore).

Sono disponibili due tipi di righe **Contatto**:

+ Contatto con striping: riga di contatto con un valore obbligatorio nel campo **Società**.
+ Contatto senza striping: riga di contatto con il campo **Società** vuoto.

La tabella **Contatto** può memorizzare questi tipi di righe:

Tipo di riga | descrizione
---|---
Una persona che è un cliente, ad esempio un contatto vendibile o un cliente B2C. | Un record di contatto con striping in cui il campo **Società** non è vuoto e il campo **Cliente** è impostato su **Sì**.
Una persona che è un fornitore, ad esempio, un unico proprietario come fornitore. | Un record di contatto con striping in cui il campo **Società** non è vuoto e il campo **Fornitore** è impostato su **Sì**.
Una persona che è sia un cliente che un fornitore. | Un record di contatto con striping in cui il campo **Società** non è vuoto e il campo **Cliente** è impostato su **Sì** e il campo **Fornitore** è impostato su **Sì**. Una persona può essere sia produttore di un prodotto che consumatore di un altro prodotto. Le app Finance and Operations e la doppia scrittura supportano questa relazione.
Una persona che è un contatto per un'organizzazione, ma non è cliente né fornitore. | Un record di contatto senza striping in cui il campo **Società** è vuoto e il campo **Cliente** è impostato su **No** e il campo **Fornitore** è impostato su **No**.

## <a name="contact-for-party"></a>Contatto per la parte

**Contatto per la parte** memorizza e gestisce relazioni N:N tra le righe **Conto** e le righe **Contatto**. Può filtrare le righe **Contatto** con striping da righe senza striping e associare solo le righe senza striping **Contatto** alle righe **Conto** o **Fornitore**.

Ad esempio, Natasha Jones e Miguel Reyes sono veterinari che si occupano di allevamenti nelle loro aree. Natasha serve l'area di Seattle e Miguel serve l'area del Kent. Nell'app Customer Engagement, gli allevamenti sono rappresentati come clienti e i veterinari sono i contatti. Un unico record **Contatto** per Natasha è associato a tutti gli allevamenti con cui lavora Natasha. Analogamente, un unico record **Contatto** per Miguel è associato a tutti gli allevamenti con cui lavora Miguel.

Queste relazioni vengono archiviate nella tabella **Contatto per la parte**. Puoi trovare le informazioni nei moduli predefiniti:

+ Quando sei nel modulo **Conto**, c'è una scheda denominata **Contatti associati**. Usa questa scheda per associare uno o più contatti alla riga **Conto**. In questo modulo assegni un contatto per un'organizzazione. Dopo aver assegnato i contatti, puoi sceglierne uno come contatto principale per quel conto. Usando il modulo **Creazione rapida** puoi solo scegliere un contatto. Il comportamento è lo stesso quando si utilizza il modulo **Fornitore** e il tipo di record è **Organizzazione**.
+ Quando sei nel modulo **Contatto** e la riga è un cliente o un fornitore o entrambi (un contatto con striping), c'è una scheda denominata **Contatti associati**. Usa questa scheda per associare uno o più contatti. In questo modulo assegni un contatto per il cliente o il fornitore B2C. Dopo aver assegnato i contatti, puoi sceglierne uno come contatto principale. Usando il modulo **Creazione rapida** puoi solo scegliere un contatto.
+ Quando sei nel modulo **Contatto** e la riga è un contatto (un contatto senza striping), c'è una scheda denominata **Organizzazioni associate**. Usa questa scheda per associare uno o più clienti o fornitori. In questo modulo assegni un cliente o un fornitore al contatto sottostante. Il cliente o il fornitore può essere un'organizzazione, una persona o entrambi. Puoi scegliere un solo valore alla volta dai quattro campi.

    ![Scheda Organizzazioni associate](media/party-gab-image3.png)

    + Se scegli **ID parte**, il contatto sottostante viene assegnato a tutti i ruoli della parte scelta.
    + Se scegli **Contatto associato**, stai selezionando il contatto con striping che è di tipo persona.
    + Se scegli **Conto associato** o **Fornitore**, stai selezionando un'organizzazione.

    Indipendentemente dalla tua scelta, l'associazione viene creata a livello di parte e applicabile a tutti i ruoli della parte e archiviata nell'entità "Contatto per la parte".

> [!Note]
> Il nome visualizzato per la tabella **Contatto per la parte** nell'app Customer Engagement è **Contatto per cliente/fornitore**.

Quando apri una riga **Contatto** dove **Cliente** è **No** e **Fornitore** è **No**, vedrai la scheda **Organizzazioni associate**. Utilizza questa scheda per associare al contatto una o più organizzazioni cliente o fornitore.

Quando apri una riga **Contatto** dove **Cliente** è **Sì** o **Fornitore** è **Sì**, vedrai la scheda **Contatti associati**. Utilizza questa scheda per associare uno o più contatti.

## <a name="postal-address"></a>Indirizzo postale

Una nuova scheda denominata **Indirizzi** è stata introdotta nel modulo **Conto**, **Contatto**, e **Fornitore**. La scheda **Indirizzi** supporta N indirizzi utilizzando una griglia, come mostrato in questa immagine:

![Griglia per indirizzo postale](media/party-gab-image4.png)

+ La colonna **Ruoli indirizzo postale** elenca l'ambito dell'indirizzo.
+ La colonna **Primario** elenca l'indirizzo principale.
+ La colonna **Numero indirizzo** elenca l'ordine degli indirizzi.
+ Il pulsante **+ Nuovo indirizzo** consente di creare un nuovo indirizzo. È possibile creare tutti gli indirizzi desiderati.

I campi **Indirizzo 1** e **Indirizzo 2** della scheda **Riepilogo** del modulo **Conto** corrispondono agli indirizzi di **Consegna** e **Fatturazione** rispettivamente.

![Scheda Riepilogo per indirizzo postale](media/party-gab-image5.png)

I campi **Indirizzo 1**, **Indirizzo 2** e **Indirizzo 3** della scheda **Riepilogo** del modulo **Contatto** corrispondono agli indirizzi di **Azienda**, **Consegna** e **Fatturazione** rispettivamente.

## <a name="electronic-address"></a>Indirizzo elettronico

Una nuova scheda denominata **Indirizzi elettronici** è stata introdotta nel modulo **Conto**, **Contatto**, e **Fornitore**. La scheda **Indirizzi** supporta N indirizzi utilizzando una griglia, come mostrato in questa immagine:

![Griglia per indirizzo elettronico](media/party-gab-image6.png)

+ La colonna **Tipo** elenca il tipo di indirizzo.
+ La colonna **Primario** elenca l'indirizzo principale.
+ La colonna **Ambito** elenca l'ambito dell'indirizzo elettronico.
+ Il pulsante **+ Nuovo indirizzo elettronico** consente di creare un nuovo indirizzo. È possibile creare tutti gli indirizzi desiderati.

Gli indirizzi elettronici sono disponibili solo su questa griglia. Nelle versioni future, tutti i campi degli indirizzi elettronici e postali verranno rimossi da altre schede, ad esempio le schede **Riepilogo** e **Dettagli**.

## <a name="setup-instructions"></a>Istruzioni di impostazione

Se sei un cliente esistente che usa la doppia scrittura, sono necessarie le seguenti istruzioni di configurazione. Altrimenti puoi saltare questa sezione.

1. Interrompi le seguenti mappe, perché non sono più necessarie. Esegui invece la mappa dei contatti V2 (msdyn_contactforparties).

    + Contatti CDS V2 e Contatti (si riferisce ai contatti del cliente)
    + Contatti CDS V2 e Contatti (si riferisce ai contatti del fornitore)

2. I seguenti mapping di entità vengono aggiornati per la funzionalità della parte, quindi l'ultima versione deve essere applicata a questi mapping.

Mappa | Aggiorna a questa versione | Modifiche
---|---|---
Clienti V3 (conti) | 1.0.0.5 |Rimossi i campi Numero parte e altri campi relativi alla parte come nome, dettagli personali, indirizzo postale, indirizzo elettronico di contatto ecc.
Cliente V3 (contatti) | 1.0.0.5 | Rimossi i campi Numero parte e altri campi relativi alla parte come nome, dettagli personali, indirizzo postale, indirizzo elettronico di contatto ecc.
Fornitori V2 (msdyn_vendors) | 1.0.0.6 | Rimossi i campi Numero parte e altri campi relativi alla parte come nome, dettagli personali, indirizzo postale, indirizzo elettronico di contatto ecc.
Intestazione offerta di vendita CDS (offerte) | 1.0.0.6 | Ha sostituito il contatto con il riferimento ContactforParty.
Intestazioni fattura di vendita V2 (fatture) | 1.0.0.4 | Ha sostituito il contatto con il riferimento ContactforParty.
Intestazioni degli ordini cliente CDS (ordini cliente) | 1.0.0.5 | Ha sostituito il contatto con il riferimento ContactforParty.
Contatti V2 (msdyn_contactforparties) | 1.0.0.2 | Questa è una nuova mappa. Se disponi di una versione precedente della soluzione per la parte, assicurati di aggiornare questa mappa all'ultima versione come indicato.
Posizioni indirizzi postali parte CDS (msdyn_partypostaladdresses) | 1.0.0.1  | Questa è una nuova mappa aggiunta come parte della versione precedente dell'anteprima della parte.
Cronologia indirizzi postali CDS V2 (msdyn_postaladdresses) | | Questa è una nuova mappa aggiunta come parte della versione precedente dell'anteprima della parte.
Posizioni indirizzi postali CDS (msdyn_postaladdresscollections) | | Questa è una nuova mappa aggiunta come parte della versione precedente dell'anteprima della parte.
Contatti della parte V3 (msdyn_partyelectronicaddresses) | | Questa è una nuova mappa aggiunta come parte di questa versione.

## <a name="templates"></a>Modelli

Una raccolta di mappe della tabella funziona in combinazione durante l'interazione con la parte e la rubrica globale, come illustrato nella seguente tabella.

App Finance and Operations | App di interazione con i clienti     | descrizione
----------------------------|-----------------------------|------------
[Titoli contatti](mapping-reference.md#223) | msdyn_salescontactpersontitles |
[Clienti V3](mapping-reference.md#101) | conti |
[Clienti V3](mapping-reference.md#116) | contatti |
[Parti CDS](mapping-reference.md#220) | msdyn_parties |
[Ubicazioni dell'indirizzo postale della parte CDS](mapping-reference.md#233) | msdyn_partypostaladdresses |
[Storico indirizzo postale CDS V2](mapping-reference.md#235) | msdyn_postaladdresses |
[Ubicazioni dell'indirizzo postale CDS](mapping-reference.md#234) | msdyn_postaladdresscollections |
[Intestazione offerta di vendita CDS](mapping-reference.md#215) | offerte |
[Intestazioni ordine cliente CDS](mapping-reference.md#217) | salesorders |
[Formule di chiusura](mapping-reference.md#222) | msdyn_complimentaryclosings |
[Contatti V2](mapping-reference.md#221) | msdyn_contactforparties |
[Ruoli nel processo decisionale](mapping-reference.md#224) | msdyn_decisionmakingroles |
[Funzioni lavorative impiego](mapping-reference.md#225) | msdyn_employmentjobfunctions |
[Livelli fedeltà](mapping-reference.md#226) | msdyn_loyaltylevels |
[Contatti parte V3](mapping-reference.md#236) | msdyn_partyelectronicaddresses |
[Tipi di carattere personale](mapping-reference.md#227) | msdyn_personalcharactertypes |
[Intestazioni fattura di vendita V2](mapping-reference.md#118) | fatture |
[Formule di apertura](mapping-reference.md#228) | msdyn_salutations |
[Fornitori V2](mapping-reference.md#202) | msdyn_vendors |

Per ulteriori informazioni, vedere [Riferimento per il mapping a doppia scrittura](mapping-reference.md).
