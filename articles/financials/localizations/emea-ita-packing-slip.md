---
title: Registrare e stampare un documento di trasporto con dettagli di consegna di trasporto per l'Italia
description: In questo argomento viene descritto come impostare i dettagli di consegna di trasporto e registrare un documento di trasporto per l'Italia.
author: ShylaThompson
manager: AnnBe
ms.date: 04/06/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4da59573e07fe33823e317863885e548115790db
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1852467"
---
# <a name="post-and-print-a-packing-slip-with-transportation-delivery-details-for-italy"></a>Registrare e stampare un documento di trasporto con dettagli di consegna di trasporto per l'Italia

[!include[banner](../includes/banner.md)]

Quando si spediscono merci ai clienti, la spedizione deve includere una bolla di accompagnamento e consegna. La bolla di accompagnamento e consegna include informazioni sul cliente e le varie parti coinvolte nella spedizione, ad esempio il terzista della spedizione, il proprietario delle merci e il caricatore della spedizione. Prima di poter stampare un documento di trasporto con i dettagli di consegna di trasporto, è necessario impostare tali dettagli.

## <a name="set-up-transportation-delivery-details"></a>Impostare i dettagli di consegna di trasporto

Per stampare la bolla di accompagnamento e consegna e le informazioni di consegna nel documento di trasporto, è necessario impostare i dettagli di consegna di trasporto nelle pagine **Parametri contabilità clienti** e **Impostazione moduli**.

1. Nella pagina **Parametri contabilità clienti**, nella scheda **Spedizioni**, nel campo **Nome vettore** selezionare il nome del vettore per la spedizione al cliente.
2. Impostare l'opzione **Utilizza informazioni bolla di accompagnamento su documento di trasporto** su **Sì** per visualizzare i dettagli di consegna di trasporto nel documento di trasporto all'atto della registrazione.
3. Chiudere la pagina per salvare le modifiche.
4. Selezionare **Contabilità clienti** &gt; **Impostazione** &gt; **Moduli** &gt; **Impostazione moduli**.
5. Nella scheda **Documento di trasporto**, selezionare la casella di controllo **Dettagli spedizione** per stampare le informazioni di spedizione nel documento di trasporto. Le informazioni di spedizione includono i dettagli del vettore.
6. Selezionare la casella di controllo **Bolla di accompagnamento** per stampare le informazioni della bolla nel documento di trasporto.

    > [!NOTE]
    > La casella di controllo **Bolla di accompagnamento** è disponibile solo se l'opzione **Utilizza informazioni bolla di accompagnamento su documento di trasporto** è impostata su **Sì** nella pagina **Parametri contabilità clienti**.

7. Chiudere la pagina per salvare le modifiche.

## <a name="post-and-print-a-packing-slip-that-includes-transportation-delivery-details"></a>Registrare e stampare un documento di trasporto con i dettagli di consegna di trasporto

È possibile registrare e stampare un documento di trasporto con una bolla di accompagnamento e consegna per una spedizione cliente. La bolla di accompagnamento e consegna contiene le informazioni riportate di seguito:

- Nome e indirizzo principale del terzista della spedizione
- Nome e indirizzo principale del caricatore della spedizione
- Nome e indirizzo principale del proprietario delle merci
- Tutte le dichiarazioni, note o istruzioni aggiuntive
- Nome della persona che ha creato il documento di trasporto (vale a dire il compilatore)

Se nella pagina **Registrazione documento di trasporto** non sono impostati i dettagli relativi a terzista, caricatore, proprietario e compilatore, nel documento di trasporto vengono stampati il nome e l'indirizzo della persona giuridica.

1. Selezionare **Vendite e marketing** &gt; **Comune** &gt; **Ordini cliente** &gt; **Tutti gli ordini cliente**.
2. Selezionare un ordine cliente aperto, quindi nel riquadro azioni, nella scheda **Preleva e imballa**, selezionare **Documento di trasporto** per aprire la finestra di dialogo **Registrazione documento di trasporto**.
3. Nella Scheda dettaglio **Parametri**, nel campo **Quantità**, selezionare **Tutto**.
4. Impostare l'opzione **Registrazione** su **Sì** per registrare il documento di trasporto.
5. Impostare l'opzione **Stampa documento di trasporto** su **Sì** per stampare il documento di trasporto una volta registrato.
6. Nel campo **Nome vettore** selezionare il nome del vettore.
7. Nel campo **Compilatore**, applicare il filtro per ordinare i nomi dei compilatori, quindi selezionare il nome della persona che ha creato il documento di trasporto.
8. Nei campi **Terzista**, **Caricatore** e **Proprietario**, selezionare il tipo di parte per filtrar la parte del trasporto, quindi selezionare il nome di ogni parte.
9. Nei campi **Dichiarazioni aggiuntive**, **Note aggiuntive** e **Istruzioni aggiuntive** immettere tutte le informazioni aggiuntive da stampare nel documento di trasporto.
10. Fare clic su **OK** per registrare e stampare il documento di trasporto con le informazioni correlate.
11. Chiudere la pagina per salvare le modifiche.
