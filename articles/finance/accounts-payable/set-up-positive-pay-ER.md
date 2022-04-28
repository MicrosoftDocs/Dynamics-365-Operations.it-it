---
title: Impostare e generare file di pagamento sicuri utilizzando la creazione di report elettronici
description: In questo argomento viene descritto come impostare un pagamento sicuro usando la creazione di report elettronici.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 43dd1a9cba1fe8df5cff26fe76af7e2957a0d6a4
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544486"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Impostare file di pagamento sicuri utilizzando la creazione di report elettronici

Impostare il pagamento sicuro per generare l'elenco elettronico degli assegni che viene fornito alla banca. Quando si presenta un assegno alla banca, la banca lo confronta con l'elenco degli assegni. Se l'assegno corrisponde a uno presente nell'elenco, la banca lo liquida. Se l'assegno non corrisponde a un assegno nell'elenco, la banca lo trattiene per esaminarlo.

## <a name="set-up-the-electronic-reporting-configuration"></a>Impostare la creazione di report elettronici

1. Vai in **Aree di lavoro \> Creazione di report elettronici**.
2. Nel riquadro per il provider di configurazione **Microsoft**, seleziona **Archivi**.
3. Seleziona **Globale** e quindi seleziona **Apri**.
4. Se è necessario stabilire una connessione al repository, seleziona il collegamento blu nella finestra di dialogo.
5. Nell'elenco di configurazione, trova e seleziona **Modello di pagamento sicuro \> Formato di pagamento sicuro**.
6. Nella Scheda dettaglio **Versioni** seleziona la versione più recente, quindi selezionare **Importa**.

## <a name="set-up-a-positive-pay-format"></a>Impostare un formato pagamenti sicuri

1. Passa a **Gestione cassa e banche \> Impostazioni \> Formato di pagamento sicuro**.
2. Selezionare **Nuovo**.
3. Imposta i campi **Formato di pagamento** e **Descrizione**.
4. Seleziona la casella di controllo **Formato esportazione elettronica generica**.
5. Imposta il campo **Configurazione formato esportazione** su **Formato di pagamento sicuro**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Assegnare un formato pagamenti sicuri a un conto bancario

1. Passa a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.
2. Apri il conto bancario.
3. Nella Scheda dettaglio **Generale**, imposta il campo **Formato di pagamento sicuro** nel formato creato in precedenza.
4. Imposta il campo **Data di inizio pagamento sicuro** sulla data corrente.

## <a name="generate-a-positive-pay-file"></a>Genera un file pagamenti sicuri

1. Passa a **Gestione cassa e banche \> Conti bancari \> Conti bancari**.
2. Apri un conto bancario per il quale è impostato un pagamento sicuro.
3. Seleziona **Gestisci pagamenti \> Pagamento sicuro \> File di pagamento sicuro**.
4. Imposta il campo **Data limite**. Verranno inclusi gli assegni generati prima di questa data.

Il file XML risultante verrà scaricato.
