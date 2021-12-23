---
title: Impostare i gruppi di imposte articoli
description: Questo argomento spiega come impostare i gruppi di imposte articoli nel servizio Calcolo imposte.
author: wangchen
ms.date: 11/30/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: TaxTable, TaxData
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-10-26
ms.dyn365.ops.version: Version 10.0.21
ms.openlocfilehash: 88dd8e2fd9d4d4e5172dcc7b1bd27a70a2f59f03
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883863"
---
# <a name="set-up-item-tax-groups"></a>Impostare i gruppi di imposte articoli

[!include [banner](../includes/banner.md)]

Questo argomento spiega come impostare i gruppi di imposte articoli nel servizio Calcolo imposte. Spiega inoltre come impostare la matrice della regola di applicabilità del gruppo imposte articoli e configurare le righe nella matrice.

Il concetto di gruppi di imposte articoli nel servizio Calcolo imposte è simile al concetto di fasce IVA articoli in Microsoft Dynamics 365 Finance. Sono gruppi di codici imposte. Il servizio Calcolo imposte utilizza l'intersezione di un gruppo di imposte e un gruppo di imposte articoli per determinare i codici imposta.

> [!IMPORTANT]
> L'impostazione dei gruppi di imposte articoli nel servizio Calcolo imposte è indipendente dalla persona giuridica. È possibile completare questa configurazione in Regulatory Configuration Service (RCS) solo una volta. Quando abiliti il servizio di calcolo delle imposte in Finance, i gruppi di imposte degli articoli vengono sincronizzati automaticamente per la persona giuridica selezionata.

## <a name="set-up-an-item-tax-group"></a>Impostare un gruppo di imposte articoli 

Per impostare un gruppo di imposte articoli effettua le seguenti operazioni.

1. Accedi a [Regulatory Configuration Service](https://marketing.configure.global.dynamics.com/).
2. Vai a **Aree di lavoro** \> **Funzionalità di globalizzazione** \> **Calcolo imposte**.
3. Seleziona la funzionalità e la versione che vuoi impostare, quindi seleziona **Modifica**.
4. Nella scheda **Generale** seleziona **Versione configurazione**.
5. Nella scheda **Gruppo di imposte articoli**, seleziona **Gestisci colonna**. Se stai impostando un gruppo di imposte articoli per la prima volta, i campi nella finestra di dialogo **Gestisci colonna** vengono impostati automaticamente.
6. Nell'elenco a sinistra, espandi il nodo **Righe** e seleziona la casella di controllo per **Gruppo di imposte articoli**.

    ![Gruppo di imposte articoli selezionato nel nodo Righe nella finestra di dialogo Gestisci colonne.](media/select-item-tax-group.png)

7. Seleziona il pulsante freccia destra per aggiungere **Gruppo di imposte articoli** all'elenco **Colonne selezionate** sulla destra.

    ![Gruppo di imposte articoli aggiunto all'elenco Colonne selezionate.](media/add-item-tax-group.png)

8. Seleziona **OK**.

## <a name="configure-an-item-tax-group"></a>Configurare un gruppo di imposte articoli

Dopo aver impostato un gruppo di imposte articoli viene creata la matrice della regola di applicabilità. È possibile aggiungere righe alla matrice per configurare il gruppo di imposte articoli.

1. Nella scheda **Gruppo di imposte articoli**, seleziona **Aggiungi**.
2. Nel campo **Gruppo di imposte articoli** immetti il nome del gruppo di imposte articoli.

    > [!IMPORTANT]
    > Si consiglia di limitare il nome del gruppo di imposte articoli a 10 caratteri. Questo nome è sincronizzato con Finance, che ha un limite di 10 caratteri per i nomi delle fasce IVA articoli.

3. Nel campo **Codici imposta** seleziona la casella di controllo per ogni codice imposta che vuoi includere nel gruppo di imposte articoli. Puoi includere più codici imposta in un gruppo di imposte articoli.

    ![Più codici imposta selezionati nel campo Codici imposta.](media/multiple-tax-codes-selection.png)

4. Per aggiungere ulteriori gruppi di imposte articoli ripeti i passaggi da 1 a 3.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
