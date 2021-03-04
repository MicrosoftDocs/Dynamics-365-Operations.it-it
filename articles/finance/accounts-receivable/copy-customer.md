---
title: Copiare i clienti mediante sequenze numeriche condivise
description: Questo argomento descrive come utilizzare sequenze numeriche condivise per copiare un cliente in un'altra persona giuridica ma mantenendo lo stesso ID cliente.
author: mikefalkner
manager: aolson
ms.date: 08/31/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: ab2beb9ca1b7cd8a4bdbb84c46ed223f58ce377d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4991145"
---
# <a name="copy-customers-by-using-shared-number-sequences"></a>Copiare i clienti mediante sequenze numeriche condivise

[!include [banner](../includes/banner.md)]

È possibile utilizzare le sequenze numeriche condivise per assegnare ID cliente. Le sequenze numeriche condivise consentono anche di copiare i clienti da una persona giuridica a un'altra persona giuridica ma utilizzare gli stessi ID cliente in entrambe le persone giuridiche.

## <a name="setup"></a>Impostazione

La funzionalità è attivata quando si utilizza una sequenza numerica condivisa per assegnare ID cliente. È necessario utilizzare la stessa sequenza numerica in ogni persona giuridica nella quale si desidera copiare un cliente. Modificare la sequenza numerica del cliente nella pagina **Parametri contabilità clienti** per ogni persona giuridica. Selezionare **Contabilità clienti** \> **Parametri**, quindi fare clic sulla scheda **Sequenze numeriche**.

È inoltre possibile impostare le sequenze numeriche cliente per ogni gruppo clienti. Queste sequenze numeriche devono anche essere condivise. La sequenza numerica per un gruppo clienti viene utilizzata prima. Se non è definita alcuna sequenza numerica per un gruppo clienti, viene utilizzata la sequenza numerica specificata nella pagina **Parametri contabilità clienti**.

È inoltre possibile copiare clienti tra persone giuridiche se si utilizzano ID cliente manuali. Tuttavia, se si tenta di copiare un cliente in una persona giuridica nella quale l'ID cliente è già presente, il processo di copia non verrà avviato.

## <a name="copy-a-customer"></a>Copiare un cliente

Per copiare un cliente, selezionare **Nuovo** nella pagina elenco **Tutti i clienti** per aprire la finestra di dialogo **Crea cliente**. Notare che il nuovo ID cliente non viene assegnato immediatamente. Questo comportamento è diverso da quello delle versioni precedenti. Poiché non è ancora stato selezionato il gruppo clienti, il sistema non può determinare la sequenza numerica corretta da utilizzare. Inoltre, non può determinare se si sta cercando di creare un nuovo cliente o copiare un cliente. Di conseguenza, l'ID cliente non è assegnato fino a quando si seleziona **Salva** nella parte inferiore della finestra di dialogo.

Se si sta creando un nuovo cliente, è possibile continuare a compilare tutti i campi come di solito. Una volta terminato e si seleziona **Salva**, si nota che l'ID cliente è stato assegnato automaticamente. In alternativa, per le sequenze numeriche manuali, vedrete che l'ID cliente manuale è stato utilizzato.

Per copiare un cliente, nel campo **Nome**, immettere uno o più caratteri che rappresentano il cliente desiderato. Una finestra di dialogo di ricerca visualizza un elenco di parti che potrebbero rappresentare il cliente che si sta cercando. Quando si seleziona una delle parti, vengono visualizzate informazioni aggiuntive a destra della finestra di dialogo:

- Sulla scheda **Generale** viene visualizzato il numero di telefono e l'indirizzo della parte.
- La scheda **Ruoli** indica i ruoli che la parte selezionata può avere e la persona giuridica dove ha ciascun ruolo.
- La scheda **Identificativo fiscale** illustra gli identificativi fiscali assegnati alla parte.

È possibile copiare una parte solo se ha un ruolo cliente e se ha tale ruolo in una persona giuridica diversa dalla persona giuridica corrente. Quando si trova una parte che corrisponde a questi criteri, procedere come segue.

1. Viene visualizzata un'opzione **Copia cliente**. Come impostazione predefinita, questa opzione è impostata su **No**. Per copiare il cliente nella persona giuridica corrente, impostare l'opzione su **Sì**. 
2. Verrà visualizzato il campo **Persona giuridica**. Selezionare la persona giuridica dalla quale copiare il cliente. Se il cliente è presente in una sola persona giuridica, il campo è impostato su quella persona giuridica come impostazione predefinita.
3. Selezionare **Select**. Il nuovo cliente viene creato.

## <a name="validation"></a>Convalida

Quando si copia un cliente, il sistema cerca di salvare le informazioni del nuovo cliente. Le convalide vengono eseguite per verificare che i dati che sono stati copiati vadano bene. Viene visualizzato un messaggio di errore per ogni convalida con esito negativo. I messaggi di errore spiegano quali informazioni devono essere aggiornate. La copia del cliente non può essere salvata finché tutti gli errori di convalida non vengono risolti.

## <a name="copy-a-customer-by-using-tax-exempt-number-search-feature"></a>Copiare un cliente utilizzando la funzionalità di ricerca del numero di partita IVA

È inoltre possibile copiare i clienti utilizzando la funzionalità di ricerca del numero di partita IVA del gruppo **Registrazione** sulla scheda **Cliente** del riquadro Azioni della pagina **Tutti i clienti**. La finestra di dialogo **Ricerca partita IVA** che viene visualizzata mostra i numeri di partita IVA, l'ID cliente, il nome del cliente e la persona giuridica in cui viene utilizzata la partita IVA. È possibile copiare un cliente solo se si trova in una persona giuridica diversa dalla persona giuridica corrente. Dopo avere selezionato un cliente che corrisponde ai criteri, procedere come segue.

1. Viene visualizzata un'opzione **Copia cliente**. Come impostazione predefinita, questa opzione è impostata su **No**. Per copiare il cliente nella persona giuridica corrente, impostare l'opzione su **Sì**. 
2. Selezionare **Select**. Il nuovo cliente viene creato.
