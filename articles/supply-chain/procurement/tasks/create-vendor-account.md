---
title: Creare un conto fornitore
description: Questa procedura mostra come creare un conto fornitore e come aggiungere un indirizzo e informazioni di contatto.
author: mkirknel
manager: tfehr
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddressGrid, DirPartyLookup, LogisticsPostalAddress, SysLookupMultiSelectGrid, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd8cd2bb7b03c0415a5c5656f0e3ffada961973e
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431578"
---
# <a name="create-a-vendor-account"></a>Creare un conto fornitore

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come creare un conto fornitore e come aggiungere un indirizzo e informazioni di contatto. La procedura non illustra come popolare tutti i campi per scopi finanziari e di acquisto. Per ulteriori informazioni su questi campi, leggere le descrizioni dei campi. È possibile utilizzare questa procedura nella società di dati dimostrativi USMF oppure nei propri dati. I conti fornitore in genere vengono creati da un responsabile degli approvvigionamenti o dal personale addetto alla contabilità clienti.


## <a name="create-a-vendor-account"></a>Creare un conto fornitore
1. Andare a **Pannello di navigazione > Moduli > Approvvigionamento > Fornitori > Tutti i fornitori**.
2. Fare clic su **Nuovo**.
3. Nel campo **Conto fornitore**, digitare un valore.
    - Il valore può essere immesso automaticamente. In tal caso, è possibile ignorare questo passaggio.  
    - È possibile creare conti fornitore per una persona o un'organizzazione. Ciò interesserà i campi disponibili. In questo esempio verrà creato un conto fornitore per un'organizzazione.   
4. Nel campo **Nome** immettere o selezionare un valore. Se il fornitore è già una parte registrata nel sistema, è possibile utilizzare il menu a discesa e selezionarlo in questo campo. Il nuovo conto fornitore erediterà l'indirizzo e le informazioni di contatto già registrate.
5. Nel campo **Gruppo** immettere o selezionare un valore. Il gruppo di fornitori viene utilizzato per raggruppare i fornitori con uno dei seguenti parametri in comune: termini di pagamento, periodo di liquidazione, conti CoGe di registrazione magazzino, inclusi fascia IVA, conti CoGe predefiniti, codici di filtro prodotti o configurazione di previsione dell'offerta.
6. Nel campo **Numero di dipendenti** immettere un numero.
7. Digitare un valore nel campo **Numero organizzazione**.

## <a name="add-an-address"></a>Aggiungere un indirizzo
1. Espandere la sezione **Indirizzi**.
2. Scegliere **Aggiungi**.
3. Nel campo **Scopo** immettere o selezionare un valore. È possibile selezionare uno o più scopi. Questi vengono utilizzati per selezionare l'indirizzo corretto per uno scopo specifico. Ad esempio, se lo scopo è "Fattura", tale indirizzo verrà utilizzato per l'invio di fatture.
4. Digitare un valore nel campo **Nome o descrizione**.
5. Nel campo **Paese**, immettere o selezionare un valore. Immettere i dettagli dell'indirizzo. Il paese selezionato determinerà i campi visualizzati, corrispondenti al formato di indirizzo per il paese. 
6. Fare clic su **OK**.

## <a name="add-contact-information"></a>Aggiungere informazioni contatto
1. Espandere la sezione **Informazioni sul contatto**.
2. Scegliere **Aggiungi**.
3. Digitare un valore nel campo **Descrizione**
4. Selezionare un'opzione nel campo **Tipo**.
5. Digitare un valore nel campo **Numero/indirizzo contatto**. È possibile selezionare la casella di controllo Primario se è il contatto principale.  
6. Fare clic su **Salva**.
7. Chiudere la pagina.
8. Chiudere la pagina.

