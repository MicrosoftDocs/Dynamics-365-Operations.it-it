---
title: Aggiungere campi dati nelle configurazioni imposte
description: Questo argomento spiega come personalizzare le configurazioni imposte aggiungendo campi dati.
author: kailiang
ms.date: 04/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: wangchen
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: ebb186a4cb9ca61399909625233b579acd2c0ec5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022789"
---
# <a name="add-data-fields-in-tax-configurations"></a>Aggiungere campi dati nelle configurazioni imposte

[!include [banner](../includes/banner.md)]

Questo argomento spiega come personalizzare le configurazioni imposte utilizzando i [campi di dati aggiunti nell'integrazione fiscale](tax-service-add-data-fields-tax-integration-by-extension.md).

## <a name="customize-the-tax-data-model"></a>Personalizzare il modello di dati fiscali

1. In Microsoft Dynamics 365 Finance, vai a **Creazione di report elettronici** \> **Configurazioni imposte**.
2. Nell'albero di configurazione seleziona **Modello di dati fiscali - Europa**. Nel riquadro azioni, seleziona **Crea configurazione**.
3. Nella casella di dialogo a discesa, seleziona l'opzione **Modello di documento imponibile derivato da Nome: Modello di dati fiscali - Europa, Microsoft**, immetti un nome per il nuovo modello di dati fiscali, quindi seleziona **Crea configurazione**.
4. Seleziona il modello di dati fiscali appena creato e quindi, nel riquadro azioni, seleziona **Progettazione**.
5. Espandi l'albero del modello di dati, seleziona **Righe** e quindi seleziona **Nuovo**.
6. Nella finestra di dialogo **Crea nodo** immetti un nome, specifica il tipo di elemento e quindi seleziona **Aggiungi**.
7. Aggiungi eventuali colonne richieste.
8. Nel riquadro azioni seleziona **Salva** e quindi **Completa**.
9. Chiudi la pagina e visualizza la versione completa del tuo modello di dati fiscali.

## <a name="customize-the-tax-configuration"></a>Personalizzare la configurazione imposte

1. In Finance , vai a **Creazione di report elettronici** \> **Configurazioni imposte**.
2. Nell'albero di configurazione seleziona **Configurazione imposte - Europa**. Nel riquadro azioni, seleziona **Crea configurazione**.
3. Nella casella di dialogo a discesa, seleziona l'opzione **Configurazione del servizio per le imposte derivata da Nome: Modello di dati fiscali - Europa, Microsoft**, immetti un nome per la nuova configurazione imposte, quindi seleziona **Crea configurazione**.
4. Seleziona la configurazione imposte appena creata e quindi, nel riquadro azioni, seleziona **Progettazione**.
5. Nella sezione **Proprietà** nel campo **Modello di dati** seleziona il modello di dati fiscali personalizzato creato in precedenza.
6. Nel campo **Versione modello di dati** seleziona la versione completa del modello di dati fiscali.
7. Seleziona **Aggiungi** e aggiungi le misure fiscali richieste.
8. Nel riquadro azioni seleziona **Salva** e quindi **Completa**.
9. Chiudi la pagina e visualizza la versione completa della tua configurazione imposte.

## <a name="implement-tax-features-in-the-customized-tax-configuration"></a>Implementare le funzioni fiscali nella configurazione imposte personalizzata

1. In Regulatory Configuration Services (RCS) vai a **Funzionalità di globalizzazione** \> **Imposte**.
2. Seleziona **Aggiungi**, inserisci le informazioni sulla nuova funzione, quindi seleziona **Crea funzionalità**.
3. Nella scheda **Versioni** seleziona la funzionalità e quindi seleziona **Modifica**.
4. Nella scheda **Generale** nel campo **Versione di configurazione** seleziona la versione e la configurazione imposte personalizzata.
5. Nella finestra di dialogo **Gestisci colonne** seleziona le colonne di intestazione e riga che vuoi includere nella misura fiscale personalizzata, quindi seleziona il pulsante freccia destra per aggiungerle all'elenco **Colonne selezionate**.
