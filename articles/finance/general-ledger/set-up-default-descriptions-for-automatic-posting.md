---
title: Impostare descrizioni predefinite per la registrazione automatica
description: Questo argomento spiega come impostare il testo predefinito utilizzato per descrivere le voci contabili registrate automaticamente nella contabilità generale. È possibile impostare il testo di descrizione predefinito utilizzando il testo libero o selezionando variabili fisse.
author: aprilolson
manager: AnnBe
ms.date: 07/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 222564
ms.assetid: ''
ms.search.region: global
ms.author: aolson
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5955b796cbc7917eb5500b96c879d1b0819d2edc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5204860"
---
# <a name="set-up-default-descriptions-for-automatic-posting"></a>Impostare descrizioni predefinite per la registrazione automatica

[!include [banner](../includes/banner.md)]

Questo argomento spiega come impostare il testo predefinito utilizzato per descrivere le voci contabili registrate automaticamente nella contabilità generale. È possibile impostare il testo di descrizione predefinito utilizzando il testo libero o selezionando variabili fisse.

> [!NOTE]
> Per alcuni tipi di transazioni, in alcuni paesi, è possibile includere anche il testo presente nei campi del database Microsoft Dynamics AX correlati a tali tipi di transazioni. Per un elenco dei tipi di transazione, dei paesi e delle aree geografiche, vedere la sezione [Facoltativo: Aggiungere altro testo alle descrizioni predefinite](#optional-add-other-text-to-default-descriptions) più avanti in questo argomento.

## <a name="set-up-default-descriptions"></a>Impostare descrizioni predefinite

1. Passare ad **Amministrazione organizzazione** \> **Impostazioni** \> **Descrizioni predefinite**.
2. Nel Riquadro azioni selezionare **Nuovo**.
3. Nel campo **Descrizione** selezionare il tipo di transazione per il quale creare una descrizione predefinita.
4. Nel campo **Lingua** selezionare la lingua a cui si applica la descrizione.
5. Nel campo **Testo** immettere la descrizione predefinita. È possibile immettere il testo nel campo oppure utilizzare una o più delle variabili di testo libero riportate di seguito:

    - **%1** - Aggiunge la data della transazione.
    - **%2** - Aggiunge un identificatore corrispondente al tipo di documento in fase di registrazione nella contabilità generale. Ad esempio, per i tipi di transazioni correlati alle fatture, la variabile **%2** aggiunge il numero della fattura.
    - **%3** - Aggiunge un identificatore corrispondente al tipo di documento in fase di registrazione nella contabilità generale. Ad esempio, per i tipi di transazioni correlati alle fatture, la variabile **%3** aggiunge il numero di conto del cliente.

## <a name="optional-add-other-text-to-default-descriptions"></a>Facoltativo: Aggiungere altro testo alle descrizioni predefinite

Per alcuni tipi di transazioni, in alcuni paesi o aree geografiche, è possibile includere il testo nelle descrizioni predefinite presenti nei campi dei dati correlati a tali tipi di transazioni. Negli elenchi seguenti vengono illustrati i tipi di transazione e i paesi e le aree geografiche per cui questa opzione è disponibile.

**Tipi di transazione**

È possibile aggiungere un altro testo alle descrizioni predefinite per i tipi di transazione correlati ai seguenti tipi di documento:

- Fatture cliente
- note di accredito cliente
- pagamenti in contanti cliente
- Pagamenti fornitore
- Ordini cliente
- Ordine fornitore
- Giornali di registrazione magazzino
- pianificazione generale (MRP)
- Cespiti

**Paesi**

Questa opzione è disponibile per i seguenti paesi e le aree geografiche:

- Brasile
- Cina
- Repubblica Ceca
- Europa orientale
- Ungheria
- India
- Giappone
- Lituania
- Lettonia
- Polonia
- Russia

### <a name="add-text-to-default-descriptions"></a>Aggiungere del testo alle descrizioni predefinite

Dopo aver completato i passaggi descritti precedentemente in questo argomento nella sezione [Impostare descrizioni predefinite](#set-up-default-descriptions), seguire questi passaggi per aggiungere altro testo alle descrizioni predefinite.

1. Nella Scheda dettaglio **Parametri** selezionare **Aggiungi**.
2. Nel campo **Tabella riferimenti** selezionare la tabella del database da cui aggiungere i dati dei parametri alla descrizione.
3. Nel campo **Campo riferimento** selezionare il campo da cui aggiungere i dati dei parametri alla descrizione.
4. Ripetere i passaggi da 1 a 3 per aggiungere ulteriori parametri.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]