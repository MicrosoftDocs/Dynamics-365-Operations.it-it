---
title: Residuo liquidazione
description: È possibile liquidare l'importo residuo dall'attività di liquidazione applicando quell'importo a un conto CoGe.
author: mikefalkner
manager: aolson
ms.date: 10/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 408a36a7cf221463b38260bd8830b422e58ccb64
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "367204"
---
# <a name="settle-remainder"></a>Residuo liquidazione

[!include [banner](../includes/banner.md)]

È possibile liquidare l'importo residuo dall'attività di liquidazione applicando quell'importo a un conto CoGe o a un altro cliente. È possibile liquidare il residuo quando si liquidano importi immessi in un giornale di registrazione o soltanto transazioni aperte.

## <a name="setting-up-defaults"></a>Configurazione delle impostazioni predefinite 
Per utilizzare la funzionalità Residuo liquidazione, è necessario abilitarla e configurare le impostazioni predefinite.

1)  Fare clic su **Contabilità clienti > parametri > Liquidazioni** o **Contabilità fornitori > Parametri > Liquidazioni**
2)  Selezionare la scheda **Liquidazione** e fare clic su **Abilita residuo liquidazione**
3)  In **Codice motivo predefinito**, selezionare un codice motivo predefinito. I codici motivo devono essere già impostati in **Contabilità clienti > Impostazioni > Codici motivo annullamento cliente** o **Contabilità fornitori > Impostazioni > Codici motivo annullamento cliente**. Per impostazione predefinita, **Conto residuo liquidazione predefinito** sarà impostato sul conto assegnato al codice motivo annullamento.
3)  Aggiornare **Conto residuo liquidazione predefinito** come necessario.
4)  In **Nome giornale di registrazione predefinito**, selezionare un giornale di registrazione pagamenti se si intende crearne uno quando si liquidano soltanto transazioni aperte. Se si abilita la funzionalità Residuo liquidazione, è necessario aggiungere un nome di giornale di registrazione predefinito.

## <a name="settle-remainder-from-a-journal"></a>Liquidare il residuo da un giornale di registrazione
Se non si abilita la funzionalità **Residuo liquidazione**, è sempre possibile immettere una transazione in un giornale di registrazione e quindi liquidare le transazioni in base a tale giornale come in passato. Quando si fa clic sul pulsante **OK**, il saldo aperto sulla fattura viene ridotto dell'importo di cassa. Se i contanti non liquidano completamente la fattura, la fattura viene lasciata aperta con un importo residuo da liquidare in un secondo momento.

Quando la funzionalità **Residuo liquidazione** è abilitata, è possibile liquidare l'importo residuo in un conto CoGe. È inoltre possibile trasferire il residuo a un altro conto cliente (per le transazioni cliente) o un altro fornitore (per le transazioni fornitore) anziché lasciare le fatture aperte. 

Per liquidare il residuo dalla pagina **Liquidazione**, procedere come segue:

1)  Nella pagina **Liquidazione**, contrassegnare le fatture o le transazioni da liquidare.
2)  Fare clic sul pulsante **Residuo liquidazione**.
3)  Verrà visualizzata una finestra di dialogo che mostra l'importo che verrà liquidato a fronte di un conto CoGe, la data che verrà utilizzata per liquidare il residuo, il codice motivo predefinito e il conto predefinito. 
4)  Selezionare un nuovo motivo di liquidazione se si desidera modificare il motivo predefinito. Il conto di liquidazione verrà modificato nel conto associato al codice motivo.
5)  Modificare il conto di liquidazione per cambiarlo.
6)  Se si liquidano transazioni cliente e si desidera che il residuo sia spostato a un altro cliente, selezionare un cliente in **Residuo liquidazione rispetto a conto cliente**. Se si liquidano transazioni fornitore e si desidera che il residuo sia spostato a un altro fornitore, selezionare un fornitore in **Residuo liquidazione rispetto a conto fornitore**.
6)  Fare clic su **Residuo liquidazione**.
7)  Viene visualizzata la pagina **Giornale di registrazione**. Una riga supplementare verrà aggiunta al giornale di registrazione con l'importo residuo liquidazione come importo e con il conto residuo liquidazione come conto di contropartita. Se si è aggiunto un cliente o fornitore per spostare l'importo di liquidazione a un altro cliente o fornitore, una riga aggiuntiva verrà aggiunta al giornale di registrazione per spostare l'importo di liquidazione a quel cliente o fornitore.

Quando si registra il giornale di registrazione, la transazione aperta verrà liquidata completamente. 

## <a name="settle-remainder-when-you-are-only-settling-open-transactions"></a>Liquidare il residuo quando si liquidano solo transazioni aperte
È anche possibile liquidare il residuo quando si liquidano transazioni aperte senza un giornale di registrazione.

Per liquidare il residuo, procedere come segue:

1)  Nella pagina **Liquidazione**, contrassegnare le fatture o le transazioni da liquidare.
2)  Fare clic su **Residuo liquidazione**.
3)  Verrà visualizzata una finestra di dialogo che mostra l'importo che verrà liquidato a fronte di un conto CoGe, la data che verrà utilizzata per liquidare il residuo, il codice motivo predefinito e il conto predefinito. 
4)  Selezionare un nuovo motivo di liquidazione se si desidera modificare il motivo predefinito. Il conto di liquidazione verrà modificato nel conto associato al codice motivo.
5)  Modificare il **conto di liquidazione** per cambiarlo.
6)  Se si liquidano transazioni cliente e si desidera che il residuo sia spostato a un altro cliente, selezionare un cliente in **Residuo liquidazione rispetto a conto cliente**. Se si liquidano transazioni fornitore e si desidera che il residuo sia spostato a un altro fornitore, selezionare un fornitore in **Residuo liquidazione rispetto a conto fornitore**
7)  È inoltre possibile scegliere di creare un giornale di registrazione pagamenti con il residuo di liquidazione o soltanto registrarlo con un giornale di registrazione. Selezionare **Sì** per **Modifica in giornale di registrazione** per creare un giornale di registrazione pagamenti. Sarà possibile modificare il giornale di registrazione pagamenti creato.
8)  Fare clic su **Residuo liquidazione**. Se si sceglie di creare un giornale, il pulsante diventerà **Crea giornale di registrazione**. Fare clic su **Crea giornale di registrazione**.
9)  Se è stato creato un giornale di registrazione pagamenti, la pagina del giornale di registrazione verrà aperta dopo aver fatto clic su **Residuo liquidazione**. Una riga del giornale di registrazione verrà aggiunta con l'importo residuo liquidazione come importo e con il conto residuo liquidazione come conto di contropartita. Se si è aggiunto un cliente o fornitore per spostare l'importo di liquidazione a un altro cliente o fornitore, una riga aggiuntiva verrà aggiunta al giornale di registrazione per spostare l'importo di liquidazione a quel cliente o fornitore.
