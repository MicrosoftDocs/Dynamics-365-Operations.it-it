---
title: Creare il canale online e definire gli attributi del canale
description: In questa procedura vengono descritti i passaggi per creare un nuovo canale online e aggiungerlo alla gerarchia organizzativa.
author: jashanno
ms.date: 06/04/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSPOnlineStoreDetailPage, SysLookupMultiSelectGrid, DimensionLookup, OMHierarchyManager, HierarchyDesigner, OMNodeSelection, HierarchyPublishAndCloseForm
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e28e717dcf594c5079b4b6987331115356b6bdbc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798515"
---
# <a name="create-online-channel-and-define-channel-attributes"></a>Creare il canale online e definire gli attributi del canale

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per creare un nuovo canale online e aggiungerlo alla gerarchia organizzativa. Prima di creare un nuovo canale online è necessario creare la gerarchia organizzativa. Questa procedura utilizza la società di dati dimostrativi USRT.


## <a name="create-a-new-online-channel"></a>Creare un nuovo canale online
1. Passare a Retail e Commerce > Canali > Punti vendita online.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Magazzino immettere o selezionare un valore.
5. Selezionare un'opzione nel campo Fuso orario punto vendita.
6. Nel campo Cliente predefinito, immettere o selezionare un valore.
7. Nel campo Rubrica clienti, immettere o selezionare un valore.
8. Nel campo Termini di pagamento immettere o selezionare un valore.
9. Nel campo Metodo di pagamento immettere o selezionare un valore.
10. Nel campo Profilo di notifica tramite posta elettronica immettere o selezionare un valore.
11. Espandere la sezione Dimensioni finanziarie.
12. Nel campo Business Unit immettere o selezionare un valore.
    * In modo analogo, impostare il valore per tutte le altre dimensioni predefinite.  
13. Fare clic su Salva.

## <a name="add-the-online-channel-to-organization-hierarchy"></a>Aggiungere il canale online alla gerarchia organizzativa
1. Chiudere la pagina.
2. Andare ad Amministrazione organizzazione > Organizzazioni > Gerarchie organizzative.
3. Nell'elenco trovare e selezionare il record desiderato.
4. Fare clic su Visualizza.
5. Fare clic su Modifica.
    * È possibile selezionare qualsiasi nodo di gerarchia in cui si desidera inserire il nuovo canale.  
6. Fare clic su Inserisci.
7. Fai clic sul canale di Commerce.
8. Fare clic su OK.
9. Fare clic su Pubblica per aprire la finestra di dialogo a discesa.
10. Nel campo Data di validità immettere una data e un'ora.
11. Fare clic su Pubblica.

## <a name="configure-orders-for-near-real-time-notification"></a>Configurare ordini per la notifica quasi in tempo reale
1. Andare a Retail e Commerce > Impostazione sedi centrali > Parametri > Parametri di commercio.
2. Impostare Utilizza servizio in tempo reale per creazione di ordini di e-commerce su "Sì".
3. Eseguire la programmazione di distribuzione 1070 per sincronizzare le modifiche nel database del canale. 




[!INCLUDE[footer-include](../../includes/footer-banner.md)]