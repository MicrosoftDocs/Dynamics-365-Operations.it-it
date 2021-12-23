---
title: Proporre acquisizioni di cespiti
description: Questa argomento descrive come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti.
author: moaamer
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 70347009ede494760cd7f51b46db04b434b9fbcc
ms.sourcegitcommit: 62ca651c94e61aaa69cfa59e861f263f89d01c4a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2021
ms.locfileid: "7883822"
---
# <a name="propose-fixed-asset-acquisitions"></a>Proporre acquisizioni di cespiti

[!include [banner](../../includes/banner.md)]

Questa argomento descrive come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti. Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF. Per acquisire un cespite tramite un giornale di proposte cespite, è necessario innanzitutto creare il record cespite, quindi definire il prezzo di acquisizione nel libro patrimoniale.

## <a name="create-an-asset-acquisition-proposal"></a>Creare una proposta di acquisizione cespite

Completa i seguenti passaggi per creare una proposta di acquisizione di cespite. 

1. Nel pannello di navigazione, andare a **Moduli > Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti**.
2. Selezionare **Nuovo**.
3. Nel campo **Nome** immettere o selezionare un valore.
4. Nel riquadro azioni selezionare **Righe**.
5. Selezione **Proposte**.
6. Selezionare **Proposta di acquisizione**.
7. Seleziona **Filtro**. Seleziona **Reimposta** per cancellare i valori precedenti.
8. Selezionare la riga **Numero cespite**.
9. Nel campo **Criteri** immettere o selezionare un valore. Impostare i criteri rimanenti per i cespiti che si desidera acquisire con la proposta.  
10. Selezionare due volte **OK** per uscire dal riquadro.
- Verifica che le righe transazione siano create.  
- Solo i cespiti con la data di acquisizione e il prezzo di acquisizione impostati sul libro verranno inclusi nella proposta di acquisizione.  
11. Nella pagina, selezionare la scheda **Libri**.
12. Selezionare **Registra**.

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a>Includere dimensioni finanziarie predefinite in una proposta di acquisizione

La transazione di acquisizione può essere creata utilizzando componenti aggiuntivi di Excel, andando a **Cespiti > Scritture contabili > Giornale di registrazione cespiti**. Crea un nuovo giornale di registrazione e passa alla sezione **Righe** nella pagina e seleziona l'icona di Excel, quindi seleziona una riga del giornale di registrazione cespiti. Il sistema creerà e aprirà un modello Excel che rappresenta le righe del giornale di registrazione. Puoi aggiungere dati per le righe del giornale di registrazione che stai aggiungendo al modello e quindi pubblicare nuovamente le informazioni nel sistema. 

Se le dimensioni predefinite sono state impostate per il libro cespiti selezionato e i cespiti corrispondenti immessi nel modello Excel, le dimensioni finanziarie predefinite verranno richiamate dai dati master del libro cespiti quando il giornale di registrazione viene pubblicato da Excel nel sistema. Per includere automaticamente le dimensioni finanziarie in un libro cespiti durante la pubblicazione del giornale di registrazione cespiti dal componente aggiuntivo di Excel, le dimensioni predefinite devono essere impostate in anticipo.  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
