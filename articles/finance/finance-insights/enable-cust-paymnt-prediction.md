---
title: Abilitare le previsioni di pagamento del cliente
description: Questo articolo spiega come attivare e configurare la funzionalità Previsioni di pagamento del cliente in Finance Insights.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f04ee9db5efe3595dea30d641c5097d6b90c0d77
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898209"
---
# <a name="enable-customer-payment-predictions"></a>Abilitare le previsioni di pagamento del cliente

[!include [banner](../includes/banner.md)]

Questo articolo spiega come attivare e configurare la funzionalità Previsioni di pagamento del cliente in Finance Insights. Puoi attivare la funzionalità nell'area di lavoro **Gestione funzionalità** e immettere le impostazioni di configurazione nella pagina **Configurazione di Finance Insights**. Questo articolo include anche informazioni che possono aiutarti a utilizzare efficacemente la funzionalità.

> [!NOTE]
> Prima di completare i passaggi seguenti, assicurati di completare i passaggi prerequisiti nell'articolo [Configurare Finance Insights](configure-for-fin-insites.md).

1. Attiva la funzionalità Previsioni di pagamento del cliente:

    1. Aprire l'area di lavoro **Gestione funzionalità**.
    2. Selezionare **Controlla aggiornamenti**.
    3. Nella scheda **Tutto**, cerca **Previsioni di pagamento del cliente**. Se non trovi tale funzionalità, cerca **Previsioni di pagamento del cliente (anteprima)**. 
    4. Attiva la funzionalità.

    La funzione Previsioni di pagamento del cliente è ora attivata e pronta per essere configurata.

2. Configura la funzionalità Informazioni sui pagamenti del cliente:

    1. Vai a **Credito e riscossioni \> Imposta \> Finance Insights \> Previsioni di pagamento del cliente**.
    2. Nella pagina **Configurazione di Finance Insights**, nella scheda **Previsioni di pagamento del cliente**, seleziona il collegamento **Visualizza i campi dati utilizzati nel modello di previsione** per aprire la pagina **Campi dati per il modello di previsione**. Qui puoi visualizzare l'elenco predefinito dei campi utilizzati per creare il modello di previsione dell'intelligenza artificiale (AI) per le previsioni di pagamento dei clienti.

        Per utilizzare l'elenco di campi predefinito per creare il modello di previsione, chiudi la pagina **Campi dati per il modello di previsione**, quindi nella pagina **Configurazione di Finance Insights**, imposta l'opzione **Abilita funzionalità** su **Sì**.
        
   > [!NOTE]
   > La funzionalità **Previsioni di pagamento del cliente** richiede più di 100 transazioni nei sei-nove mesi precedenti. Le transazioni possono includere fatture a testo libero, ordini cliente e pagamenti dei clienti. Questi dati devono essere estesi alle impostazioni **Puntuale**, **In ritardo** e **Molto in ritardo**.    
     

    3. Specifica il periodo di transazione "molto in ritardo" per definire cosa significa il bucket di previsione **Molto tardi** per la tua azienda.

        Per ogni fattura aperta, il sistema prevede la probabilità di pagamento in tre bucket: **Puntuale**, **In ritardo** e **Molto in ritardo**.

        - **Puntuale**: questo bucket include i pagamenti che si prevede verranno pagati entro la data di scadenza della transazione.
        - **In ritardo**: questo bucket include i pagamenti che si prevede verranno pagati dopo la data di scadenza della transazione ma prima dell'inizio del periodo di transazione "molto in ritardo".
        - **Molto in ritardo**: questo bucket include i pagamenti che si prevede verranno pagati dopo l'inizio del periodo di transazione "molto in ritardo".

        > [!NOTE]
        > Se modifichi il periodo di transazione "molto in ritardo" e selezioni **Modifica la soglia di ritardo** dopo che il modello di previsione IA per i pagamenti dei clienti è stato creato, il modello di previsione esistente viene eliminato e viene creato un nuovo modello. Il nuovo modello di previsione sposterà le transazioni nel periodo "molto in ritardo" in base alle impostazioni immesse per definirlo.

    4. Dopo aver finito di definire il periodo di transazione "molto in ritardo", seleziona **Crea modello di previsione** per creare il modello di previsione. La sezione **Modello di previsione** nella pagina **Configurazione di Finance Insights** mostra lo stato del modello di previsione.

        > [!NOTE]
        > In qualsiasi momento durante la creazione del modello di previsione, puoi selezionare **Reimposta la creazione del modello** per riavviare il processo.

    La funzionalità è ora configurata è pronta per essere utilizzata.

Dopo che la funzionalità è stata attivata e configurata e il modello di previsione è stato creato e funziona, la sezione **Modello di previsione** della pagina **Parametri di Finance Insights** mostra la precisione del modello.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
