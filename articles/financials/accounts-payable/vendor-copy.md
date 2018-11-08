---
title: Copiare i fornitori mediante sequenze numeriche condivise
description: Questo argomento descrive come utilizzare sequenze numeriche condivise per copiare un fornitore in un'altra persona giuridica ma mantenendo lo stesso ID fornitore.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.1
ms.translationtype: HT
ms.sourcegitcommit: a8c033caa8a4c4cf579ec166dce7a9982408d816
ms.openlocfilehash: 0c492cd76fc9742aa4cff8fe588541cb2c6f1863
ms.contentlocale: it-it
ms.lasthandoff: 10/11/2018

---

# <a name="copy-vendors-by-using-shared-number-sequences"></a>Copiare i fornitori mediante sequenze numeriche condivise

[!include [banner](../includes/banner.md)]

È possibile utilizzare le sequenze numeriche condivise per assegnare ID fornitore. Le sequenze numeriche condivise consentono anche di copiare i fornitori da una persona giuridica a un'altra persona giuridica ma utilizzare gli stessi ID fornitore in entrambe le persone giuridiche.

## <a name="setup"></a>Impostazione

La funzionalità è attivata quando si utilizza una sequenza numerica condivisa per assegnare ID fornitore. È necessario utilizzare la stessa sequenza numerica in ogni persona giuridica nella quale si desidera copiare un fornitore. Modificare la sequenza numerica del fornitore nella pagina **Parametri contabilità fornitori** per ogni persona giuridica. Selezionare **Contabilità fornitori** \> **Imposta** \> **Parametri contabilità fornitori**e selezionare la scheda **Sequenze numeriche**.

È inoltre possibile impostare le sequenze numeriche fornitore per ogni gruppo fornitori. Queste sequenze numeriche devono anche essere condivise. La sequenza numerica per un gruppo fornitori viene utilizzata prima. Se non è definita alcuna sequenza numerica per un gruppo fornitori, viene utilizzata la sequenza numerica specificata nella pagina **Parametri contabilità fornitori**.

È inoltre possibile copiare fornitori tra persone giuridiche se si utilizzano ID fornitore manuali. Tuttavia, se si tenta di copiare un fornitore in una persona giuridica nella quale l'ID fornitore è già presente, il processo di copia non verrà avviato.

## <a name="copy-a-vendor"></a>Copiare un fornitore

Per copiare un fornitore, selezionare **Nuovo** nella pagina elenco **Tutti i fornitori** per aprire la pagina **Tutti i fornitori, nuovo record**. Notare che il nuovo ID fornitore non viene assegnato immediatamente. Questo comportamento è diverso dal comportamento nelle versioni precedenti di Microsoft Dynamics 365 for Finance and Operations. Poiché non è ancora stato selezionato il gruppo fornitori, il sistema non può determinare la sequenza numerica corretta da utilizzare. Inoltre, non può determinare se si sta cercando di creare un nuovo fornitore o copiare un fornitore. Di conseguenza, l'ID fornitore non è assegnato fino a quando si seleziona **Salva** nella parte inferiore della pagina.

Se si sta creando un nuovo fornitore, è possibile continuare a compilare tutti i campi come di solito. Una volta terminato e si seleziona **Salva**, si nota che l'ID fornitore è stato assegnato automaticamente. In alternativa, per le sequenze numeriche manuali, si nota che l'ID fornitore manuale è stato utilizzato.

Per copiare un fornitore, nel campo **Nome**, immettere uno o più caratteri che rappresentano il fornitore desiderato. Una finestra di dialogo di ricerca visualizza un elenco di parti che potrebbero rappresentare il fornitore che si sta cercando. Quando si seleziona una delle parti, vengono visualizzate informazioni aggiuntive a destra della finestra di dialogo:

- Sulla scheda **Generale** viene visualizzato il numero di telefono e l'indirizzo della parte.
- La scheda **Ruoli** indica i ruoli che la parte selezionata può avere e la persona giuridica dove ha ciascun ruolo.
- La scheda **Identificativo fiscale** illustra gli identificativi fiscali assegnati alla parte.

È possibile copiare una parte solo se ha un ruolo fornitore e se ha tale ruolo in una persona giuridica diversa dalla persona giuridica corrente. Quando si trova una parte che corrisponde a questi criteri, procedere come segue.

1. Viene visualizzata un'opzione **Copia fornitore**. Come impostazione predefinita, questa opzione è impostata su **No**. Per copiare il fornitore nella persona giuridica corrente, impostare l'opzione su **Sì**. 
2. Verrà visualizzato il campo **Persona giuridica**. Selezionare la persona giuridica dalla quale copiare il fornitore. Se il fornitore è presente in una sola persona giuridica, il campo è impostato su quella persona giuridica come impostazione predefinita.
3. Selezionare **Select**. Viene creato il nuovo fornitore.

## <a name="validation"></a>Convalida

Quando si copia un fornitore, il sistema cerca di salvare le informazioni del nuovo fornitore. Le convalide vengono eseguite per verificare che i dati che sono stati copiati vadano bene. Viene visualizzato un messaggio di errore per ogni convalida con esito negativo. I messaggi di errore spiegano quali informazioni devono essere aggiornate. La copia del fornitore non può essere salvata finché tutti gli errori di convalida non vengono risolti.

## <a name="copy-a-vendor-by-using-the-tax-exempt-number-search-feature"></a>Copiare un fornitore utilizzando la funzionalità di ricerca del numero di partita IVA

È inoltre possibile copiare i fornitori utilizzando la funzionalità di ricerca del numero di partita IVA del gruppo **Registrazione** sulla scheda **Fornitore** del riquadro azioni della pagina **Tutti i fornitori**. La finestra di dialogo **Ricerca partita IVA** che viene visualizzata mostra i numeri di partita IVA, l'ID fornitore, il nome del fornitore e la persona giuridica in cui viene utilizzata la partita IVA. È possibile copiare un fornitore solo se si trova in una persona giuridica diversa dalla persona giuridica corrente. Dopo avere selezionato un fornitore che corrisponde ai criteri, procedere come segue.

1. Viene visualizzata un'opzione **Copia fornitore**. Come impostazione predefinita, questa opzione è impostata su **No**. Per copiare il fornitore nella persona giuridica corrente, impostare l'opzione su **Sì**.
2. Selezionare **Select**. Viene creato il nuovo fornitore.

