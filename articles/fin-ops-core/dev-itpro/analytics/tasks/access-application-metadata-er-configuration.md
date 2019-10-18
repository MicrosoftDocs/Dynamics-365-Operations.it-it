---
title: Accedere ai metadati dell'applicazione utilizzando una configurazione ER
description: I passaggi in questo argomento descrivono come un utente di Regulatory Configuration Service (RCS) può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati in Finance and Operations.
author: NickSelin
manager: AnnBe
ms.date: 06/28/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-06-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2bfe007995c894d6cc86d07ef2b52da65e32e950
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182740"
---
# <a name="access-application-metadata-by-using-er-configuration"></a>Accedere ai metadati dell'applicazione utilizzando una configurazione ER

[!include [task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente di Regulatory Configuration Service (RCS) con ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare un nuovo mapping di modello per la creazione di report elettronici (ER) utilizzando i metadati dell'applicazione. Sarà possibile accedere ai metadati dell'applicazione utilizzando la configurazione dei metadati ER contenente un set di metadati di esempio per accedere alle transazioni del commercio estero. Per completare questi passaggi, in RCS è necessario dapprima completare i passaggi dell'argomento [Creare provider di configurazione e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). Quindi, completare i passaggi nell'argomento [(ER) Preparare i metadati dell'applicazione da utilizzare in RCS](prepare-application-metadata-rcs.md).

## <a name="prerequisites"></a>Prerequisiti
1. Andare a **Tutte le aree di lavoro** > **Creazione di report elettronici**. 
2. Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come **attivo**. Se questo provider di configurazione non è visualizzato, completare i passaggi nella procedura [Creare provider di configurazioni e contrassegnarli come attivi](er-configuration-provider-mark-it-active-2016-11.md). 

## <a name="import-metadata-configuration"></a>Importare una configurazione dei metadati 
1. Fare clic su **Configurazioni dei metadati**. 
2. Importare la configurazione dei metadati ER che contiene i metadati configurati per generare documenti elettronici per il dominio aziendale per il commercio estero. Questa configurazione dei metadati ER è stata esportata come file XML durante il completamento dei passaggi della procedura [(ER) Preparare i metadati dell'applicazione da utilizzare in RCS](prepare-application-metadata-rcs.md). 
3. Fare clic su **Scambia**. 
4. Fare clic su **Carica da file XML**. 
5. Fare clic su **Sfoglia** e selezionare il file "Metadati del commercio estero.xml". 
6. Fare clic su **OK**. 
7. Chiudere la pagina. 

## <a name="create-data-model-configuration"></a>Creare una nuova configurazione del modello di dati
1. Fare clic su **Configurazioni report**. 
2. Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa. 
3. Nel campo **Nome**, digitare "Modello del commercio estero". 
4. Fare clic su **Crea configurazione**. 
5. Fare clic su **Progettazione**. 
6. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa. 
7. Digitare "Radice" nel campo **Nome**. 
8. Scegliere **Aggiungi**. 
9. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa. 
10. Nel campo **Nome** digitare "Transazione". 
11. Nel campo **Tipo di articolo** selezionare **Elenco di record**. 
12. Scegliere **Aggiungi**. 
13. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa. 
14. Nel campo **Nome** digitare "Codice voce doganale". 
15. Nel campo **Tipo di articolo** selezionare **Stringa**. 
16. Scegliere **Aggiungi**. 
17. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa. 
18. Nel campo **Nome** digitare "Importo fatturato". 
19. Nel campo **Tipo di articolo** selezionare **Reale**. 
20. Scegliere **Aggiungi**. 
21. Fare clic su **Nuovo** per aprire la finestra di dialogo a discesa. 
22. Digitare "Data" nel campo **Nome**. 
23. Nel campo **Tipo di articolo** selezionare **Data**. 
24. Scegliere **Aggiungi**. 
25. Fare clic su **Riferimento radice**. 
26. Fare clic su **OK**. 
27. Fare clic su **Salva**. 
28. Chiudere la pagina. 
29. Fare clic su **Cambia stato**. 
30. Fare clic su **Completa**. 
31. Fare clic su **OK**. 

## <a name="create-model-mapping-configuration"></a>Creare una configurazione del mapping di modello 
1. Fare clic su **Crea configurazione** per aprire la finestra di dialogo a discesa. 
2. Nel campo **Nuovo** immettere "Mapping di modello basato sul modello di dati Modello del commercio estero". 
3. Nel campo **Nome**, digitare "Mapping del commercio estero". 
4. Fare clic su **Crea configurazione**. 
5. Espandere la sezione **Prerequisiti**. 
6. Fare clic su **Modifica**. 
7. Fare clic su **Nuovo**. 
8. Nell'elenco contrassegnare la riga selezionata. 
9. Nel campo **Tipo di componente prerequisito**, selezionare **Configurazione**. 
10. Selezionare la configurazione **Metadati del commercio estero**. 
11. Fare clic su **Salva**. 
12. Abbiamo aggiunto il riferimento alla versione 1 della configurazione "Metadati del commercio estero". I metadati dell'applicazione di questa configurazione saranno disponibili durante la progettazione di questo mapping di modello. 
13. Chiudere la pagina. 
14. Fare clic su **Progettazione**. 
15. Fare clic su **Progettazione**. 
16. Nella struttura selezionare **Dynamics 365 for Operations'\Record di tabella**. 
17. Fare clic su **Aggiungi radice**. 
18. Digitare "Intrastat" nel campo **Nome**. 
19. Selezionare i record di tabella **Intrastat**. 
20. Fare clic su **OK**. 

> [!NOTE]
> Solo 2 tabelle erano disponibili poiché solo 2 tabelle sono state aggiunte al set di metadati attualmente utilizzati. 

21. Fare clic su **Associa**. 
22. Nella struttura espandere **Intrastat**. 
23. Nella struttura selezionare **Intrastat\AmountMST**. 
24. Nella struttura espandere **Transazione = Intrastat**. 
25. Nella struttura selezionare **Transazione = Intrastat\Importo fatturato**. 
26. Fare clic su **Associa**. 
27. Nella struttura selezionare **Intrastat\TransDate**. 
28. Nella struttura selezionare **Transazione = Intrastat\Data**. 
29. Fare clic su **Associa**. 
30. Nella struttura espandere **Intrastat\>Relazioni**. 
31. Nella struttura espandere **Intrastat\>Relazioni\IntrastatCommodity**. 
32. Nella struttura selezionare **Intrastat\>Relazioni\IntrastatCommodity\Codice**. 
33. Nella struttura selezionare **Transazione = Intrastat\Codice voce doganale**. 
34. Fare clic su **Associa**. 
35. Fare clic su **Convalida**. 

> [!NOTE]
> Abbiamo associato gli elementi del modello di dati ad articoli delle origini dati descritte utilizzando i dettagli dei metadati dell'applicazione nella configurazione dei metadati ER a cui si fa riferimento. 
36. Fare clic su **Salva**. 
37. Chiudere la pagina. 
38. Chiudere la pagina. 
39. Se necessario, è possibile estendere il set esistente di metadati e quindi esportare la nuova versione completata della configurazione dei metadati di ER. È quindi possibile importarla in RCS e aggiornare i prerequisiti della configurazione del mapping di modello configurato che fa riferimento a una nuova versione della configurazione dei metadati importata. 

> [!NOTE]
> Questo modo di ottenere informazioni sui metadati dell'applicazione è l'unico disponibile per le applicazioni distribuite localmente (quando un modello di distribuzione di dati aziendali locali o on-premises è utilizzato).
        
