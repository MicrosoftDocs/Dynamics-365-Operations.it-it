---
title: Impostare la riallocazione articolo per prelievo breve
description: In questo argomento viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti all'ubicazione a cui sono stati indirizzati.
author: ShylaThompson
ms.date: 06/29/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkException, WHSWorker, WHSLocationWithWorkException
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84cefe723cff9566ed3004e49f1e829020bc0d416cd0b29258c21222fbeb05ab
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6741886"
---
# <a name="set-up-short-picking-item-reallocation"></a>Impostare la riallocazione articolo per prelievo breve

[!include [banner](../../includes/banner.md)]

In questa procedura viene illustrato come consentire agli addetti al magazzino di individuare rapidamente le ubicazioni alternative se non è disponibile scorte sufficienti alla'ubicazione a cui sono stati indirizzati. 

Il processo di riallocazione è controllato da una **Eccezione di lavoro** e utilizzato dal **lavoratore** di magazzino.

È possibile utilizzare i processi di riallocazione automatici, manuali o entrambi:

- Riallocazione automatica: le direttive sull'ubicazione vengono utilizzate per determinare se le merci sono disponibili in un'altra ubicazione. Se possibile, il lavoro verrà aggiornato e l'utente del magazzino verrà indirizzato all'ubicazione alternativa.
- Riallocazione manuale: consente all'utente del magazzino di selezionare da una o più ubicazioni con quantità di merce senza prenotazione. 
- Automatico e manuale: se il sistema non è in grado di eseguire una riallocazione automatica e le ubicazioni sono disponibili con quantità non prenotate, all'utente verrà richiesto di selezionare un'ubicazione.

## <a name="set-up-work-exceptions"></a>Imposta eccezioni lavoro
È possibile definire più eccezioni lavoro con diversi criteri di riallocazione articolo per consentire all'addetto al magazzino di scegliere uno in base alle esigenze di spedizione in corso di elaborazione.

La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.

1. Nel **pannello di navigazione**, andare a **Gestione magazzino > Impostazione > Lavoro > Eccezioni lavoro**.
2. Fare clic su **Nuovo**. 
3. Nel campo **Codice di eccezione lavoro**, immettere un valore. Questo sarà il titolo di questa eccezione. Ad esempio, Prelievo manuale breve.
4. Digitare un valore nel campo **Descrizione** Questa sarà una breve descrizione dell'uso di questa eccezione. Ad esempio, Prelievo breve - articolo non disponibile.
5. Nel campo Tipo di **eccezione** seleziona **Prelievo in difetto**.
6. Selezionare la casella di controllo **Correggi magazzino**. Se selezionata, questa opzione indica che l'inventario verrà rettificato automaticamente su 0 all'ubicazione del prelievo breve.
7. Nel campo **Codice tipo correzione predefinito**, immettere o selezionare un valore. Ad esempio, in USMF è possibile selezionare **Remove Res Adj Out** . Ciascun codice del tipo di rettifica contiene quattro caratteristiche: nome, Descrizione, nome del giornale di inventario e **Rimuovi prenotazioni**. Se **Rimuovi prenotazioni** è abilitata, le prenotazioni della riga ordine di prelievo breve verranno rimosse.  
8. Nel campo **Riallocazione articolo**, seleziona un valore, ad esempio Manuale. Se si seleziona Manuale o Automatico e manuale, l'addetto al magazzino deve essere abilitato per utilizzare la riallocazione manuale.

## <a name="set-up-a-worker-to-use-manual-item-reallocation"></a>Impostare un lavoratore per utilizzare la riallocazione manuale degli articoli

La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura.

1. Chiudere la pagina.
2. Nel **pannello di navigazione**, andare a **Gestione magazzino > Impostazione > Lavoro > Lavoratore**.
3. Fare clic su **Modifica**.
4. Nell'elenco seleziona il lavoratore. Ad esempio, Julia Funderburk.
5. Espandi la Scheda dettaglio **Utenti**.
6. Nell'elenco, seleziona un **ID utente**. Ad esempio, 24.
7. Espandi la Scheda dettaglio **Lavoro**.
8. Selezionare **Sì** nel campo **Consenti riallocazione manuale articolo**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]