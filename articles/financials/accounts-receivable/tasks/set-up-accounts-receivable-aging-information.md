--- 
title: "Registrare la fattura fornitore e associarla alla quantità ricevuta"
description: "Questa guida consentirà di impostare una definizione periodo di aging, i saldi con aging cliente e di visualizzare i saldi nell'elenco Saldo con aging e nella pagina Riscossioni."
author: mikefalkner
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2e9f393acaa47d485a583b99ace459474f30be6a
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Registrare la fattura fornitore e associarla alla quantità ricevuta

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa guida consentirà di impostare una definizione periodo di aging, i saldi con aging cliente e di visualizzare i saldi nell'elenco Saldo con aging e nella pagina Riscossioni. Questa registrazione utilizza la società dimostrativa USMF.


## <a name="create-an-aging-period-definition"></a>Creare una definizione di periodo di aging.
1. Andare a Crediti e riscossioni > Impostazioni > Definizioni periodo di aging.
2. Fare clic su Nuovo.
3. Nel campo Definizione periodo di aging, digitare un valore.
4. Digitare un valore nel campo Descrizione.
5. Fare clic su Aggiungi sotto per inserire un nuovo periodo di aging.
6. Nel campo Periodo, immettere la descrizione da visualizzare nei report di aging.
7. Immettere un numero nel campo Unità.
8. Selezionare un'opzione nel campo Intervallo.
    * Il periodo contabile corrisponde al periodo nel calendario di contabilità generale. Il giorno, la settimana, il mese, il trimestre e gli anni definiscono la dimensione dell'intervallo in base al tipo di data. Illimitato consente di selezionare tutte le transazioni prima o dopo il periodo precedente, a seconda che si tratti del primo o dell'ultimo periodo.  
9. Selezionare un'opzione nel campo Indicatore di aging.
10. Selezionare il periodo nella parte superiore della griglia. Aggiornare la descrizione per descrivere il periodo meno recente nella definizione del periodo di aging
11. Nel campo Periodo immettere la nuova descrizione del periodo di aging.
12. Chiudere la pagina.

## <a name="age-the-balances"></a>Aging dei saldi
1. Andare a Crediti e riscossioni > Attività periodiche > Saldi con aging cliente.
2. Nel campo Definizione periodo di aging selezionare il periodo di aging creato.
    * È possibile avere uno snapshot attivo per ogni definizione del periodo di aging.  
    * Per impostazione predefinita vengono elaborati tutti i clienti. È possibile utilizzare questa opzione per calcolare un singolo pool di riscossioni dei clienti.  
    * Selezionare la data della transazione che verrà utilizzata per l'aging.  
    * Selezionare una data "a partire da" per l'aging. L'impostazione predefinita è la data corrente, ma se si modifica il campo su Data selezionata, sarà possibile selezionare la data desiderata. Per l'elaborazione batch, utilizzare la data odierna.  
3. Espandere l'intervallo Società. È possibile selezionare le società che verranno incluse nello snapshot. Per impostazione predefinita viene selezionata la società corrente.
4. Fare clic su OK per elaborare lo snapshot. Questa operazione richiederà alcuni minuti, quindi aspettare che il dispositivo di scorrimento scompaia e controllare il centro messaggi per un messaggio.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>Visualizzare i saldi nell'elenco Saldi con aging e nella pagina Riscossione
1. Andare a Crediti e riscossioni > Riscossioni > Saldi con aging.
    * Nella pagina elenco vengono visualizzati i saldi per il cliente. Nell'icona di aging viene visualizzato il periodo di aging per la transazione meno recente.  
2. Selezionare un cliente con un saldo.
3. Espandere l'area riquadro Dettaglio informazioni aging per visualizzare i saldi con aging.
    * La definizione del periodo di aging per il riquadro Dettaglio informazioni viene ricavata dalla definizione del periodo di aging specificata nei parametri. È possibile modificarla mediante il menu Pagato a destinazione.  


