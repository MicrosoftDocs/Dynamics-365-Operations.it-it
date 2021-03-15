---
title: Impostare la riscossione
description: In questo articolo viene descritto come impostare le funzionalità di riscossione.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustCollectionsActivitiesListPage
audience: Application User
ms.reviewer: roschlom
ms.custom: 14031
ms.assetid: dcc6da2f-9af5-4f1d-abaa-b72967b66979
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 732b9ba95e6a3fdbb8bdd3e6aa745c26cd3904b1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971680"
---
# <a name="set-up-collections"></a>Impostare la riscossione

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come impostare le funzionalità di riscossione. È necessario completare alcuni passaggi di configurazione quando si utilizza la funzionalità Riscossioni. Sono disponibili anche alcune funzionalità facoltative, tra cui pool di clienti e team di riscossioni. 

- Definizioni periodo di aging
- Snapshot di aging
- Nomi giornale di registrazione
- Codici causale per transazioni di annullamento
- Agenti di riscossione
- Conto di annullamento
- Informazioni NSF (senza copertura)
- Impostazioni di Outlook per gli utenti che utilizzano la pagina **Riscossioni**
- Indirizzi di posta elettronica

Questi punti sono discussi in maggior dettaglio nel resto di questo argomento. 

<a name="set-up-aging-period-definitions"></a>Imposta le definizioni di periodi di aging
-------------------------------

Imposta una definizione di periodo di aging. Impostare una definizione del periodo di aging, ovvero definire le colonne da visualizzare nelle pagine elenco **Saldi con aging**, **Attività di riscossione** e **Casi di riscossione**. Consente inoltre di definire i periodi visualizzati nella pagina **Riscossioni**. Se è stato impostato un pool di clienti, verrà utilizzata la definizione del periodo di aging per il pool. Se non è stato impostato alcun pool di clienti, verrà utilizzata la definizione del periodo di aging predefinita specificata nella pagina **Parametri contabilità clienti**. Se non è stata specificata alcuna definizione del periodo di aging predefinita, viene utilizzata la prima definizione del periodo di aging della pagina **Definizioni periodo di aging**.

## <a name="create-an-aging-snapshot"></a>Creare uno snapshot di aging
Creare record snapshot di aging per tutti i clienti o per i clienti di un pool di clienti. Le informazioni dello snapshot di aging vengono visualizzate nella pagina elenco **Saldi con aging** e nella pagina **Riscossioni**. Per poter utilizzare la pagina elenco, è innanzitutto necessario creare uno snapshot di aging. Nella pagina elenco vengono visualizzate solo le informazioni sui clienti per i quali è stato creato uno snapshot di aging.

## <a name="optional-set-up-customer-pools"></a>Impostare i pool di clienti (facoltativo)
È possibile impostare i pool di clienti per rappresentare dei gruppi di clienti. I pool di clienti possono essere utilizzati quando si creano gli snapshot di aging oppure come filtri per informazioni relative al cliente visualizzate nelle pagine elenco **Riscossioni** nella pagina **Riscossioni**.

## <a name="optional-create-a-collections-team"></a>Creare un team di recupero crediti (facoltativo)
Se nell'organizzazione le attività di riscossione vengono svolte da più persone, è possibile impostare un team di riscossione. È possibile selezionare il team nella pagina **Parametri di contabilità clienti**. Se non si crea un team di riscossione, quando si impostano gli agenti di riscossione nela pagina **Agente di recupero crediti** verrà creato automaticamente un team.

## <a name="set-up-a-collections-case-category"></a>Impostare una categoria di casi di riscossione
Per organizzare le riscossioni tramite i casi, impostare una categoria di casi con il tipo di categoria **Riscossioni**. Ciò è necessario solo se si desidera utilizzare la funzionalità caso nella pagina **Riscossioni**.

## <a name="set-up-journal-names-settlement-writeoff-and-nsf"></a>Impostare i nomi di giornali di registrazione: liquidazione, annullamento e NSF, Non Sufficient Funds (senza copertura)
Impostare i nomi di giornale di registrazione utilizzati quando le transazioni vengono elaborate nella pagina **Riscossioni**. Questa elaborazione include la liquidazione e l'annullamento di transazioni nonché l'elaborazione di pagamenti senza copertura (NSF).

| Descrizione | Tipo giornale di registrazione     |
|-------------|------------------|
| Insediamento  | Pagamento cliente |
| Eliminazione   | Giornaliera            |
| NSF, Non Sufficient Funds (senza copertura)         | Pagamento cliente |

## <a name="set-up-a-reason-code-for-writeoff-transactions"></a>Impostare un codice motivo per le transazioni di annullamento
Impostare il codice motivo predefinito utilizzato quando le transazioni vengono ammortizzate nella pagina **Riscossioni**. È possibile modificare il codice durante il processo di annullamento.

## <a name="set-up-a-folder-for-email-attachments-and-create-email-templates"></a>Impostare una cartella per gli allegati di posta elettronica e creare modelli di messaggio di posta elettronica
Se si inviano messaggi di posta elettronica nella pagina **Riscossioni** con allegati di Microsoft Excel, è possibile creare modelli di messaggio di posta elettronica facoltativi per i messaggi.

## <a name="set-up-accounts-receivable-parameters-for-collections"></a>Impostare i parametri di contabilità clienti per le riscossioni
Impostare i parametri di contabilità clienti correlati alle riscossioni visualizzat nella scheda **Riscossioni**.

## <a name="optional-set-up-collections-agents"></a>Impostare gli agenti di recupero crediti (facoltativo)
Se nell'organizzazione le attività di riscossione vengono svolte da più persone, è possibile impostare degli agenti di riscossione. Un agente di riscossione è un lavoratore impostato come utente nel modulo **Relazioni utenti**. Per agevolare l'organizzazione del lavoro, è possibile assegnare agli agenti di riscossione dei pool di clienti, ovvero delle query relative ai clienti. Gli agenti di riscossione vengono aggiunti al team selezionato nella pagina **Parametri contabilità clienti**. Se nel modulo non è selezionato alcun team, verrà creato automaticamente un nuovo team denominato **Riscossioni** e gli agenti di riscossione verranno aggiunti a tale team.

## <a name="set-up-a-writeoff-account"></a>Impostare un conto di annullamento
Impostare un conto di annullamento da utilizzare per l'inserimento di annullamento in contabilità generale quando una transazione viene annullata. Questo conto viene archiviato nel profilo di registrazione cliente.

## <a name="set-up-nsf-information-for-bank-accounts"></a>Impostare le informazioni NSF per i conti bancari
Aggiornare i conti bancari in modo che abbiano il giornale di registrazione corretto quando i pagamenti NSF vengono identificati nella pagina **Riscossioni**. Nella scheda **Gestione della valuta**, nel campo **Giornale di registrazione pagamenti NSF**, selezionare un giornale di registrazione pagamenti.

## <a name="set-up-outlook-settings-for-users-of-the-collections-page"></a>Configurare le impostazioni di Outlook per gli utenti della pagina Riscossioni
Prima che i lavoratori possano creare attività o inviare messaggi di posta elettronica tramite la pagina **Riscossioni**, è necessario verificare che la chiave di configurazione **Sincronizzazione di Microsoft Outlook** sia selezionata e che per i lavoratori sia impostata la sincronizzazione di Outlook.

## <a name="set-up-email-and-addresses"></a>Impostare messaggi e indirizzi di posta elettronica
È possibile utilizzare la posta elettronica per comunicare con clienti e venditori su problemi di riscossione e per inviare messaggi di posta elettronica dalla pagina **Riscossioni**. 

### <a name="set-up-email-and-address-settings-for-collections-customer-contacts"></a>Configurare le impostazioni di posta elettronica e gli indirizzi per i contatti per la riscossione del cliente
Per inviare messaggi di posta elettronica ai contatti tramite la pagina **Riscossioni**, impostare gli indirizzi di posta elettronica per i contatti del cliente. Il contatto per la riscossione viene utilizzato come contatto predefinito nella pagina **Riscossioni**. Se sui rendiconti deve essere indicato un indirizzo diverso da quello principale, è possibile impostare un indirizzo del rendiconto per il cliente. 

Nella scheda dettaglio **Crediti e riscossioni** per un cliente, nel campo **Contatto riscossioni**, selezionare la persona dell'organizzazione del cliente che lavora con l'agente di riscossione. Questa persona verrà utilizzata come contatto predefinito nella pagina **Riscossioni** e corrisponderà al destinatario dei messaggi di posta elettronica inviati. 

> [!NOTE] 
> Se per un cliente non è stato specificato un contatto per la riscossione, verrà utilizzato il contatto principale per il cliente. Se non è stato specificato un contatto principale, i messaggi di posta elettronica verranno inviati al primo indirizzo elencato nella pagina **Contatti**.

### <a name="set-up-email-settings-for-salespeople"></a>Configurare le impostazioni di posta elettronica per i venditori
Per inviare messaggi di posta elettronica ai venditori tramite la pagina **Riscossioni**, impostare gli indirizzi di posta elettronica per i venditori. Impostare un indirizzo di posta elettronica per ogni rappresentante in ogni gruppo vendite con provvigione. Il rappresentante per il quale è selezionata l'opzione **Contatto** corrisponde al venditore predefinito destinatario dei messaggi di posta elettronica inviati. 

Se non è stato specificato un rappresentante, verrà utilizzato il venditore principale per l'organizzazione del cliente. Se non è stato specificato un venditore principale, i messaggi di posta elettronica verranno inviati al primo venditore elencato nel modulo.


Per ulteriori informazioni, vedere i seguenti argomenti:

 - [Creare una sequenza di lettere di sollecito](tasks/create-collection-letter-sequence.md)

 - [Elaborare lettere di sollecito](tasks/process-collection-letters.md)

 - [Esaminare le informazioni sulla riscossione](tasks/review-collections-information.md)



[!INCLUDE[footer-include](../../includes/footer-banner.md)]