---
title: Impostare parametri TDS in Contabilità fornitori e Contabilità clienti
description: In questo argomento viene illustrato come impostare parametri in Contabilità fornitori e Contabilità clienti per supportare le detrazioni dell'imposta dedotta all'origine (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: d2cb434346dbbe5487522fe9f7110716c3a8c761
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725151"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>Impostare parametri TDS in Contabilità fornitori e Contabilità clienti

[!include [banner](../includes/banner.md)]

In questo argomento viene illustrato come impostare parametri in Contabilità fornitori e Contabilità clienti per supportare le detrazioni dell'imposta dedotta all'origine (TDS).

1. Vai a **Imposta \> Impostazione \> Parametri \> Parametri contabilità clienti**.
2. Nella scheda **Aggiornamenti**, seleziona **Aggiorna righe ordine** per aprire la finestra di dialogo **Aggiorna righe ordine**.
3. Nella sezione **Gruppo TDS**, nel campo **Aggiornamento gruppo TDS**, specifica il metodo da utilizzare per aggiornare il gruppo TDS a livello di riga. Questa impostazione viene utilizzata quando il gruppo TDS viene aggiornato in un'intestazione dell'ordine. Di seguito vengono illustrate le opzioni disponibili.

    - **Mai** - Il gruppo TDS non viene aggiornato nelle righe dell'ordine quando viene aggiornato nell'intestazione dell'ordine.
    - **Sempre** - Il gruppo TDS viene aggiornato automaticamente nelle righe dell'ordine quando viene aggiornato nell'intestazione dell'ordine.
    - **Richiesta** - Gli utenti ricevono un messaggio che richiede loro di aggiornare il gruppo TDS nelle righe ordine.
4. Selezionare **OK**.

    [![Finestra di dialogo Aggiorna righe ordine.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. Vai a **Imposta \> Impostazione \> Parametri \> Parametri contabilità fornitori**.
6. Nella scheda **Generale**, nella Scheda dettaglio **Dividi in base alle informazioni di consegna**, imposta l'opzione **Entrata prodotti** su **Sì** per registrare e dividere un'entrata prodotti che ha diversi indirizzi di consegna e numeri di conto imposta (TAN). Se questa opzione è impostata su **No**, non è possibile registrare un documento di trasporto di acquisto che ha differenti indirizzi di consegna e TAN.
7. Imposta l'opzione **Fattura** su **Sì** per registrare e dividere una fattura di acquisto che ha diversi indirizzi di consegna e TAN.

    [![Scheda dettaglio Dividi in base alle informazioni di consegna.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. Chiudere la pagina.
