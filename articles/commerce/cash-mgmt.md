---
title: Miglioramenti della gestione di cassa
description: In questo argomento vengono descritti i miglioramenti della gestione di cassa in POS per Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 05/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 86cdd70919926243bbf2cb5cc2f26690accdac80
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993685"
---
# <a name="cash-management-improvements"></a>Miglioramenti della gestione di cassa

[!include [banner](includes/banner.md)]


La gestione di cassa è una funzione chiave per i rivenditori nei punti vendita fisici. I rivenditori desiderano disporre di sistemi che consentono di fornire tracciabilità e rendicontazione complete della cassa e dei relativi movimenti nei vari registratori di cassa di un punto vendita. Essi devono essere in grado di riconciliare tutte le differenze e determinare la rendicontazione.


Microsoft Dynamics 365 Commerce include funzionalità di gestione di cassa nella relativa applicazione POS. Tuttavia, nelle versioni di Retail antecedenti alla versione 10.0.3, la funzionalità di gestione di cassa non è in grado di fornire una tracciabilità completa dei movimenti di cassa nei punti vendita. Sebbene i rivenditori possano riconciliare la cassa di un punto vendita, non possono determinare in modo preciso la rendicontazione nel caso di una discrepanza di cassa.


In Retail versione 10.0.3 e successive, i rivenditori avranno a disposizione una migliore tracciabilità per la gestione di cassa. Nell'ambito di questa tracciabilità, i rivenditori potranno definire casseforti, effettuare transazioni in contanti fronte/retro e riconciliare transazioni di gestione di cassa.

## <a name="set-up-traceability-and-define-safes"></a>Impostare la tracciabilità e definire casseforti

Per impostare la nuova funzionalità di gestione di cassa, attenersi alla procedura seguente per configurare il profilo funzionalità per punti vendita.

1. Accedere a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili funzionalità** e selezionare un profilo funzionalità collegato ai punti vendita a cui applicare i miglioramenti della gestione di cassa.
2. Nella Scheda dettaglio **Funzioni** del profilo funzionalità, in **Gestione cassa avanzata**, impostare l'opzione **Abilità tracciabilità dei contanti** su **Sì**.
3. Per impostare casseforti, accedere a **Retail e Commerce \> Canali \> Punti vendita \> Tutti i punti vendita** e selezionare un punto vendita.
4. Nella pagina **Punti vendita**, nel riquadro azioni, nella scheda **Imposta**, nel gruppo **Imposta**, selezionare **Casseforti**. Con questa opzione, è possibile definire e gestire più casseforti per un punto vendita.
4. Prima di poter utilizzare la funzionalità, è necessario eseguire il processo di programmazione di distribuzione **1070 Configurazione canale** per sincronizzare tali configurazioni al database del canale.

## <a name="additional-cash-management-changes"></a>Ulteriori modifiche alla gestione di cassa

In Retail versione 10.0.3 e successive, vengono fornite anche le seguenti funzionalità correlate alle transazioni di cassa:

- Un utente a cui viene richiesto di "dichiarare l'importo iniziale" deve indicare l'origine del contante. L'utente può cercare le casseforti disponibili definite nel punto vendita e selezionare la cassaforte da cui viene prelevato il contante di modo che possa essere utilizzato nel registratore di cassa.
- A un utente che esegue un'operazione "rimozione metodo di pagamento" viene richiesto di selezionare, in un elenco di transazioni "fondo di cassa" aperte, la transazione per l'operazione. Se il fondo di cassa corrispondente non è presente nel sistema, l'utente può creare una transazione "rimozione del metodo di pagamento" non collegata.
- Un'operazione "fondo di cassa" richiede a un utente di selezionare, in un elenco di transazioni "rimozione del metodo di pagamento" aperte, la transazione per l'operazione fondo di cassa. Se la rimozione del metodo di pagamento corrispondente non è presente nel sistema, l'utente può creare una transazione "fondo di cassa" non collegata.
- A un utente che esegue un "deposito in cassaforte" viene richiesto di selezionare la cassaforte in cui il contante viene depositato.
- Per le casseforti definite in un punto vendita, gli utenti possono gestire operazioni come dichiarare l'importo iniziale, eseguire un fondo di cassa, eseguire una rimozione del metodo di pagamento ed effettuare un deposito bancario.
- Per gli utenti con privilegi appropriati, le operazioni "gestisci turni" mostrano i saldi di cassa di turni attivi, sospesi e con chiusura forzata.
- Per riconciliare le transazioni di cassa in un turno o tra turni, selezionare il turno da riconciliare e quindi **Riconcilia**. La visualizzazione che viene aperta mostra l'elenco delle transazioni riconciliate e non riconciliate in schede distinte. In questa visualizzazione, gli utenti possono selezionare le transazioni non riconciliate e riconciliarle, oppure annullare la riconciliazione delle transazioni riconciliate in precedenza.
- Durante la riconciliazione, se la transazione selezionata non è bilanciata, l'utente deve immettere una descrizione del motivo della riconciliazione non bilanciata. Gli utenti possono selezionare una singola transazione e riconciliarla con la relativa descrizione del motivo.
- Gli utenti possono continuare a riconciliare le transazioni e ad annullare la riconciliazione di quelle riconciliate fino alla chiusura del turno. Dopo la chiusura di un turno, non è possibile annullare la riconciliazione delle transazioni riconciliate.
- Quando un utente sceglie di chiudere un turno, Commerce conferma che non sono presenti transazioni di gestione di cassa non riconciliate nel turno. Gli utenti non possono chiudere un turno se sono presenti transazioni non riconciliate.
