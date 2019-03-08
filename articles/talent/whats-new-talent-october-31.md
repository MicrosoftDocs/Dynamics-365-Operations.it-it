---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (31 ottobre 2018)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 10/31/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: Talent
ms.openlocfilehash: c5acd09e25ecd5fefa637342f83d0ee0f1891402
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "305012"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-october-31-2018"></a>Novità o modifiche in Dynamics 365 for Talent Core HR (31 ottobre 2018)

[!include [banner](includes/banner.md)]

**Build 8.1.2031**

Questo argomento descrive le funzionalità nuove o modificate di Core HR.

## <a name="create-links-from-talent-to-finance-and-operations"></a>Creare collegamenti da Talent a Finance and Operations
Questa nuova funzionalità di navigazione consente di selezionare il collegamento da Talent a Finance and Operations, permettendo la navigazione diretta alle pagine Finance and Operations. Quando i collegamenti vengono configurati, è possibile specificare il nome e il gruppo del collegamento, dove il collegamento deve emergere in Talent e la pagina di destinazione da aprire in Finance and Operations.

#### <a name="coming-soon"></a>Presto disponibili
Il contesto del campo verrà aggiunto in futuro per consentire la navigazione diretta ai record corrispondenti in Finance and Operations. Ad esempio, è possibile utilizzare **Collegamento a campo** per immettere il contesto per navigare direttamente a un dipendente o a un percorso specifico in Finance and Operations.

### <a name="configure-target-systems"></a>Configurare i sistemi di destinazione

In Talent gli amministratori di sistema possono definire i collegamenti che saranno disponibili tramite l'area di lavoro Amministrazione sistema. Parte della configurazione avviene negli ambienti Finance and Operations ai quali si desidera navigare in quanto "destinazione" del collegamento. È possibile effettuare questa operazione assegnando al sistema di destinazione un nome e fornendo l'URL dell'ambiente Finance and Operations. Di seguito è riportato un esempio di URL Finance and Operations che verrà fornito: https://devax00124aos.cloud.test.dynamics.com/. Dopo aver configurato i sistemi di destinazione, è possibile definire i collegamenti.

### <a name="configure-links"></a>Configura collegamenti

Ogni collegamento creato conterrà le seguenti informazioni definite.

- Collegamento - Nome del collegamento, utilizzato solo per l'identificazione.

- Abilitare questo collegamento - Impostare su **Sì** se si desidera visualizzare il collegamento agli utenti di Talent.

- Nome visualizzato - Definire il nome che apparirà come collegamento a Finance and Operations. Questi dati non sono attualmente convertiti.

- Collegamento area nel modulo - Scegliere su quale pagina visualizzare il collegamento.

- Gruppo - I gruppi non sono obbligatori, ma se si desidera organizzare i collegamenti utilizzando i gruppi, selezionare un gruppo esistente o crearne uno nuovo utilizzando il campo **Gruppo**.

- Sistema di destinazione - Selezionare il sistema di destinazione che è stato creato utilizzano l'opzione **Configura sistema di destinazione**. Sarà l'ambiente Finance and Operations che verrà utilizzato per navigare usando il collegamento.

- Usa società corrente dell'utente - Selezionare **Sì** per utilizzare il contesto della società corrente dell'utente quando naviga a Finance and Operations. Se si seleziona **No**, è possibile scegliere la società da utilizzare.

- Voce di menu di destinazione - Immettere la voce di menu di Finance and Operation che il collegamento dovrebbe utilizzare durante la navigazione. Sono disponibili voci di menu sulle quali è possibile spostarsi direttamente. Per trovare la voce di menu richiesta, aprire Finance and Operations, quindi la pagina che corrisponde all'obiettivo di navigazione. Copiare la voce di menu dall'URL. Ad esempio, se si desidera che il collegamento porti all'elenco dei dipendenti in Finance and Operations, immettere il valore visualizzato dopo "&mi" nell'URL. https://devax00124aos.cloud.test.dynamics.com/?p=USMF&mi=HcmWorkerListPage_Employees. La voce di menu per navigare alla pagina con l'elenco dei dipendenti in questo esempio è: HcmWorkerListPage_Employees.

- Collegamento a origine dati - Selezionare l'origine dei dati alla quale si riferisce il collegamento. Le origini più comuni come **Lavoratore** e **Posizione** sono disponibili.

- Collegamento a campo - (Presto disponibile) Questa selezione del campo consentirà la navigazione diretta da un unico record in Talent a un unico record in Finance and Operations.

### <a name="access-to-links"></a>Accedere ai collegamenti

Gli amministratori di sistema vedranno i collegamenti appena creati nelle pagine definite anche se l'opzione **Abilitare questo collegamento** è impostata su **No**. Ciò può essere utilizzato per verificare i collegamenti prima di renderli disponibili ad altri dipendenti. Tutti gli altri ruoli vedranno soltanto i collegamenti configurati dopo che l'opzione **Abilitare questo collegamento** sarà stata impostata su **Sì**. I dipendenti che hanno accesso alle pagine in cui i collegamenti vengono resi disponibili potranno accedere ad essi.

Gli utenti possono anche avere diritti di protezione all'interno di Finance and Operations impostati per accedere alle pagine di Finance and Operations. In caso contrario, viene visualizzata una finestra di dialogo di protezione quando si utilizza il collegamento.


## <a name="other-changesfixes"></a>Altre modifiche/correzioni

### <a name="positions-with-a-future-start-date-cannot-be-assigned-to-a-new-employee"></a>Le posizioni con una data di inizio futura non possono essere assegnate a un nuovo dipendente

Le modifiche sono state apportate per consentire le assegnazioni di dipendenti alle posizioni con date future. Le posizioni con una data di inizio futura possono essere selezionate e l'assegnazione di un dipendente verrà eseguita in fase di salvataggio o di completamento del flusso di lavoro (se il flusso di lavoro è abilitato).

### <a name="new-employee-cannot-be-assigned-existing-position"></a>Al nuovo dipendente non può essere assegnata la posizione esistente

Le modifiche sono state apportate in modo che una nuova assegnazione del dipendente potrà essere assegnata alle posizioni esistenti.

### <a name="seniority-dateoffice-location-disappears-when-the-employment-start-date-is-in-the-past-and-the-record-is-saved"></a>Data di anzianità/Ubicazione ufficio non sarà più disponibile quando la data di inizio impiego è trascorsa e il record è salvato

Le modifiche sono state apportate per correggere la visibiltà di **Data di anzianità** e **Ubicazione ufficio** durante il salvataggio delle modifiche per i dipendenti passati.

### <a name="cant-enter-data-for-future-dated-employments-on-the-worker-page"></a>Non è possibile immettere i dati delle occupazioni con date future nella pagina del lavoratore

I dati di impiego per le occupazioni con date future sono stati disattivati nella pagina principale del lavoratore. I dati di impiego possono essere immessi nelle pagine **Responsabile data**. Le modifiche aggiuntive verranno effettuate nelle versioni future per consentire l'immissione di dati di impiego direttamente durante il processo del flusso di lavoro.

### <a name="add-validfrom-and-validto-to-hcmpersonalcontactpersonentity"></a>Aggiungere ValidFrom e ValidTo a HcmPersonalContactPersonEntity

L'entità HcmPersonalContactPersonEntity di Data Management Framework (DMF) è stata aggiornata per includere le date "valida da "e "valida fino a" e consentire determinati scenari di integrazione di benefit. 

## <a name="known-issue"></a>Problema noto
- **Problema**: quando si aggiunge un nuovo allegato a un lavoratore, i pulsanti **Nuovo** e **Modifica** sono inattivi. 
- **Soluzione alternativa:** prima di aprire la pagina dell'allegato, verificare che le schede dettaglio della pagina **Lavoratore** siano chiuse. Se i riquadri Dettaglio informazioni sono chiusi quando la pagina **Lavoratore** viene caricata, i pulsanti degli allegati saranno abilitati. Questo problema verrà risolto nel prossimo aggiornamento della piattaforma.
