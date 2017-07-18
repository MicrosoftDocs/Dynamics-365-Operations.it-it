---
title: Regole di eliminazione
description: Questo argomento fornisce informazioni sulle regole di eliminazione e sulle varie opzioni per i report sulle eliminazioni.
author: RobinARH
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 76af350f37109260a757ccc0b93908637d0579dc
ms.contentlocale: it-it
ms.lasthandoff: 06/13/2017

---

# <a name="elimination-rules"></a>Regole di eliminazione

[!include[banner](../includes/banner.md)]


Questo argomento fornisce informazioni sulle regole di eliminazione e sulle varie opzioni per i report sulle eliminazioni.

Le transazioni di eliminazione sono necessarie quando una persona giuridica padre intrattiene rapporti commerciali con una o più persone giuridiche affiliate e utilizza report finanziari consolidati. I rendiconti finanziari consolidati devono includere solo le transazioni che si verificano tra l'organizzazione consolidata e altre entità all'esterno di tali organizzazioni. Di conseguenza, le transazioni tra le persone giuridiche che appartengono alla stessa organizzazione devono essere rimosse, o eliminate, dalla contabilità generale in modo che non compaiano nei report finanziari. Sono disponibili più modi per eseguire report sulle eliminazioni:

-   Una regola di eliminazione può essere creata ed elaborata in una società di eliminazione o di consolidamento.
-   I report finanziari possono essere utilizzati per visualizzare i conti e le dimensioni delle eliminazioni in una riga o in una colonna specifica.
-   Una persona giuridica separata può essere utilizzata per registrare le voci delle transazioni manuali per tenere traccia delle eliminazioni.

Questo argomento riguarda le regole di eliminazione che vengono elaborate in una società di eliminazione o di consolidamento. È possibile impostare regole di eliminazione per creare transazioni di eliminazione in una persona giuridica specificata come persona giuridica di destinazione per le eliminazioni. La persona giuridica di destinazione è conosciuta come persona giuridica di eliminazione. I giornali di registrazione eliminazioni possono essere generati durante il processo di consolidamento o tramite un'apposita proposta. Prima di impostare le regole di eliminazione, è consigliabile acquisire familiarità con i seguenti termini:

-   **Persona giuridica di origine**: la persona giuridica in cui sono stati registrati gli importi in fase di eliminazione.
-   **Persona giuridica di destinazione**: la persona giuridica in cui vengono registrate le regole di eliminazione.
-   **Persona giuridica di eliminazione**: la persona giuridica specificata come persona giuridica di destinazione per le eliminazioni.
-   **Persona giuridica consolidata**: la persona giuridica creata per il reporting dei risultati finanziari per un gruppo di persone giuridiche. I dati finanziari dalle persone giuridiche vengono consolidati in questa persona giuridica, quindi viene creato un report finanziario utilizzando i dati combinati.

Nella seguente tabella vengono visualizzati i tipi di transazioni che potrebbero dover essere eliminati.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo di transazione</th>
<th>Esempio</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Immissione ordine cliente e fatturazione (elaborazione centralizzata)</td>
<td>Viene venduto un prodotto a un cliente per conto di un'altra persona giuridica nell'organizzazione.</td>
</tr>
<tr class="even">
<td>Immissione ordine cliente (interaziendale/intrasocietario) e fatturazione</td>
<td>I prodotti vengono venduti tra le persone giuridiche dell'organizzazione.</td>
</tr>
<tr class="odd">
<td>Ordini fornitore (elaborazione centralizzata)</td>
<td>Vengono acquistati scorte, forniture, servizi, cespiti e altri prodotti da un fornitore per conto di un'altra persona giuridica dell'organizzazione.</td>
</tr>
<tr class="even">
<td>Gestione articoli (interaziendale/intrasocietario)</td>
<td><ul>
<li>Vengono trasferite le scorte di una persona giuridica ai cespiti di un'altra persona giuridica nell'organizzazione.</li>
<li>Vengono trasferite le scorte di una persona giuridica nelle scorte di un'altra persona giuridica nell'organizzazione.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Tracciabilità scorte in transito</td>
<td>Vengono trasferiti articoli tra magazzini nella stessa persona giuridica, ma in aree geografiche diverse.</td>
</tr>
<tr class="even">
<td>Elaborazione fatture centralizzata di contabilità fornitori</td>
<td>Viene registrata una fattura per conto di un'altra persona giuridica nell'organizzazione.</td>
</tr>
<tr class="odd">
<td>Elaborazione pagamenti centralizzata di contabilità fornitori</td>
<td>Viene pagata una fattura per conto di un'altra persona giuridica nell'organizzazione.</td>
</tr>
<tr class="even">
<td>Gestione di cassa e liquidità (elaborazione centralizzata)</td>
<td><ul>
<li>Vengono elaborati pagamenti di imposte, rimborsi di imposte, interessi, prestiti, anticipi, pagamenti di dividendi i e royalty o provvigioni prepagate.</li>
<li>Viene pagata una spesa per conto di un'altra persona giuridica nell'organizzazione. La fattura viene immessa nei libri della persona giuridica di destinazione ed è necessario eseguire una compensazione incrociata tra le persone giuridiche. Ad esempio, una persona giuridica paga una nota spese di un dipendente di un'altra persona giuridica. In questo caso, nella nota spese di un dipendente saranno riportate spese correlate a persona giuridica.</li>
<li>Vengono trasferiti contanti da una persona giuridica a un'altra nell'organizzazione.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Contabilità clienti (elaborazione centralizzata)</td>
<td>Si ricevono contanti per una fattura cliente di un'altra persona giuridica e l'assegno viene depositato sul conto bancario di tale persona giuridica.</td>
</tr>
<tr class="even">
<td>Retribuzioni (elaborazione centralizzata, interaziendale/intrasocietario)</td>
<td><ul>
<li>Viene pagata la retribuzione di un'altra persona giuridica. Ad esempio, una persona giuridica paga le retribuzioni dei propri dipendenti, ma addebita il lavoro svolto da un dipendente per un'altra persona giuridica durante l'elaborazione della retribuzione. In alternativa, ha lavorato mezza giornata per la persona giuridica A e l'altra mezza giornata per la persona giuridica B e i benefit sono distribuiti nell'intera retribuzione. In questi casi, la retribuzione dipendente include la retribuzione per entrambe le persone giuridiche. Vengono registrati non solo gli stipendi, ma anche le imposte, i benefit, le detrazioni e i ratei degli stipendi.</li>
<li>La manodopera viene trasferita da un reparto o da una divisione a un'altra.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Cespiti (interaziendale/intrasocietario)</td>
<td>Vengono trasferiti i cespiti ai cespiti o nel magazzino di un'altra persona giuridica.</td>
</tr>
<tr class="even">
<td>Allocazioni (interaziendale/intrasocietario)</td>
<td>Vengono elaborate le allocazioni aziendali. Le allocazioni sono attività su un conto qualsiasi allocato, indipendentemente dal modulo di origine.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>Esempio
La persona giuridica A vende congegni a un'altra persona giuridica nell'organizzazione, la persona giuridica B. Viene riportato di seguito un esempio di come potrebbe essere necessario eliminate le transazioni tra le due persone giuridiche:

-   La persona giuridica A vende un congegno che costa 10,00 alla persona giuridica B per un importo pari a 10,00.
-   La persona giuridica A vende un congegno da 10,00 alla persona giuridica B per un importo pari a 10,00, più altri 2,00 per i costi di spedizione effettivi.
-   La persona giuridica A vende un congegno da 10,00 alla persona giuridica B per un importo pari a 15,00 e riconosce un margine per la vendita.
-   La persona giuridica A vende un congegno da 10,00 alla persona giuridica B per un importo pari a 15,00 e riconosce metà del margine per la vendita. La persona giuridica B riconosce l'altra metà del margine per la vendita Di conseguenza, i ricavi sono suddivisi. In questo modo viene fornito un incentivo per effettuare l'ordine a un'altra persona giuridica dell'organizzazione anziché a un'organizzazione esterna.

Tutte queste transazioni daranno origine a transazioni interaziendali registrate in conti per importi da versare e da ricevere. In queste transazioni inoltre possono essere inclusi importi di ricarico e ribasso qualora l'importo delle vendite interaziendali non sia uguale al costo delle merci vendute.

## <a name="set-up-elimination-rules"></a>Impostare regole di eliminazione
Per impostare l'eliminazione di regole in Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, si consiglia di creare una dimensione finanziaria specificatamente per operazioni di eliminazione. La maggior parte dei clienti la definiscono Partner commerciale o simili. Se si decide di non utilizzare una dimensione finanziaria, assicurarsi di avere conti principali specifici solo per transazioni interaziendali. 

L'impostazione per le eliminazioni è disponibile nell'area Impostazioni del modulo Consolidamenti. Dopo aver immesso una descrizione per la regola, è necessario selezionare la società per cui il giornale di registrazione eliminazioni effettuerà la registrazione. Questa deve essere una società con l'opzione **Utilizza per processo di eliminazione finanziario** selezionata nell'impostazione Persona giuridica. 

È possibile impostare una data in cui la regola di eliminazione diventa valida e quando scade, se necessario. È necessario impostare **Attivo** su **Sì** se si desidera renderla disponibile nel processo di proposta di eliminazione. Selezionare un nome di giornale di registrazione con un tipo di **Eliminazione**.

Dopo avere definito le basi, è possibile definire le regole di elaborazione effettive facendo clic su **Righe**. Sono disponibili due opzioni per le eliminazioni: eliminando l'importo netto della modifica o definendo un importo fisso. 

Selezionare il conto di origine. È possibile utilizzare un asterisco (\*) come carattere jolly. Ad esempio, 1\* selezionerebbe tutti i conti che cominciano con 1 come origine di dati per l'allocazione. 

Dopo aver selezionato i conti di origine, la **Specifica conto** determina il conto della società di destinazione utilizzata. Selezionare **Origine** se si desidera utilizzare lo stesso conto principale definito nel conto **Origine**. Se si seleziona **Definito dall'utente**, è necessario specificare un conto di destinazione. 

La specifica della dimensione funziona nello stesso modo. Se si seleziona **Origine**, nella società di destinazione verranno utilizzate le stesse dimensioni della società di origine. Se si seleziona **Definito dall'utente**, sarà necessario specificare le dimensioni nella società di destinazione facendo clic sulla voce di menu **Dimensioni di destinazione**. 

Selezionare le dimensioni di origine e i valori e le dimensioni finanziarie utilizzati come origine dell'eliminazione.

## <a name="process-elimination-transactions"></a>Elaborare transazioni di eliminazione
Sono disponibili due modi per elaborare le transazioni di eliminazione: durante il processo di consolidamento online o creando un giornale di registrazione di eliminazione ed eseguendo il processo di proposta di eliminazione. Questa sezione descrive la creazione del giornale di registrazione e l'esecuzione del processo di eliminazione. 

In una società specificata come società di eliminazione, selezionare **Giornale di registrazione eliminazioni** nel modulo Consolidamenti. Dopo aver selezionato il nome del giornale di registrazione, fare clic su **Righe**. È possibile eseguire la proposta selezionando il menu **Proposte**, quindi selezionando **Proposta di eliminazione**.

Selezionare la società che rappresenta l'origine dei dati consolidati, quindi scegliere la regola da elaborare. Immettere una data di inizio per iniziare la ricerca degli importi di eliminazione e una data di fine per terminare la data di ricerca per gli importi di eliminazione. Il campo **Data registrazione CoGe** è la data utilizzata per registrare il giornale di registrazione nella contabilità generale. Dopo aver fatto clic su **OK**, è possibile esaminare gli importi e registrare il giornale di registrazione.




