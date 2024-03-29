---
title: Configurare le ubicazioni in un magazzino abilitato WMS
description: La guida illustra come configurare l'ubicazione per un nuovo magazzino abilitato per WMS (un magazzino che utilizza i processi di gestione avanzata del magazzino (WMS)).
author: perlynne
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventLocation, WHSLocationFormat, WHSLocationType, WHSLocationProfile, WHSParameters, WHSZoneGroup, WHSZone, WHSLocationBuild, WHSLocation, WHSPackSizeCategory, WHSLocationLimit, WHSInventFixedLocation, WMSLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4cce7ea0c06938d2ce038853a262f843ec76fe4c
ms.sourcegitcommit: c98d55a4a6e27239ae6b317872332f01cbe8b875
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2022
ms.locfileid: "9219660"
---
# <a name="configure-locations-in-a-wms-enabled-warehouse"></a>Configurare le ubicazioni in un magazzino abilitato WMS

[!include [banner](../../includes/banner.md)]

La guida illustra come configurare l'ubicazione per un nuovo magazzino abilitato per WMS (un magazzino che utilizza i processi di gestione avanzata del magazzino (WMS)). Il processo è in genere eseguito da un amministratore di magazzino. È possibile eseguire questa guida nella società di dati dimostrativi USMF oppure sui propri dati. Una precondizione è che si abbia almeno un sito configurato.


## <a name="create-a-new-warehouse"></a>Creare un nuovo magazzino
1. Selezionare **Pannello di navigazione > Moduli > Gestione articoli > Impostazione > Attività periodiche > Suddivisione scorte > Magazzini**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Magazzino**.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Sito**, seleziona o digita un valore del sito esistente.
6. Espandere la sezione **Magazzino**.
7. Impostare l'opzione **Usa processi di gestione del magazzino** su Sì. Questa impostazione consente di eseguire i processi di gestione del magazzino (WMS) utilizzando dispositivi di lavoro e mobili del magazzino.
8. Chiudi la pagina.

## <a name="define-a-location-format"></a>Definire un formato ubicazione
1. Selezionare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Magazzino > Formati ubicazione**. I formati ubicazione sono un sistema di denominazione utilizzato per creare nomi univoci e coerenti per le diverse posizioni dei contenitori di ubicazione usate all'interno di un magazzino. Può essere utile utilizzare separatori come parte del formato di ubicazione per semplificare l'identificazione dei componenti dell'ubicazione, ad esempio il numero di sezione. In questo esempio verrà creato un nome con quattro componenti. Ad esempio, questi possono essere sezione, scaffale, ripiano e contenitore.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Formato ubicazione**.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Descrizione segmento** immettere un valore. Questo descrive ciò che rappresenta il primo componente del nome dell'ubicazione. Ad esempio, potrebbe essere "Sezione".
6. Immettere un numero nel campo **Lunghezza.** Questo determina il numero di caratteri che deve avere la parte del nome dell'ubicazione. Il totale di tutti i componenti nel nome, inclusi i separatori, non può superare i 10 caratteri.    
7. Digitare un valore nel campo **Separatore**. Questo determina quale carattere o simbolo viene utilizzato tra il primo e il secondo componente del nome.  
8. Nella sezione **Dettagli**, fare clic su **Nuovo**.
9. Nel campo **Descrizione segmento** immettere un valore.
10. Immettere un numero nel campo **Lunghezza.**
11. Digitare un valore nel campo **Separatore**.
12. Nella sezione **Dettagli**, fare clic su **Nuovo**.
13. Nel campo **Descrizione segmento** immettere un valore.
14. Immettere un numero nel campo **Lunghezza.**
15. Digitare un valore nel campo **Separatore**.
16. Nella sezione **Dettagli**, fare clic su **Nuovo**.
17. Nel campo **Descrizione segmento** immettere un valore.
18. Immettere un numero nel campo **Lunghezza.**
19. Fare clic su **Salva**.
20. Chiudere la pagina.

## <a name="define-location-types"></a>Definire tipi di ubicazione
1. Selezionare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Magazzino > Tipi di ubicazione**. I tipi di ubicazione possono essere utilizzati come opzioni di filtro per verificare i diversi processi di gestione del magazzino. Come minimo, è necessario creare tipi di ubicazione di gestione temporanea e spedizione finale per definire il processo in uscita di gestione magazzino. 
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Tipo di ubicazione**.
4. Digitare un valore nel campo **Descrizione**
5. Chiudere la pagina.

## <a name="define-location-profile"></a>Definire il profilo di ubicazione
1. Selezionare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Magazzino > Profili ubicazione**. La definizione dei profili di ubicazione è molto importante. La capacità di ubicazioni raggruppate può essere controllata qui così come i criteri relativi a quale inventario viene immagazzinato e a come viene immagazzinato. I profili di ubicazione possono essere utilizzati come opzioni di filtro per verificare i diversi processi di gestione del magazzino. Come minimo, è necessario creare un profilo di ubicazione per attivare WMS.
2. Fare clic su **Nuovo**.
3. Nel campo **ID profilo ubicazione** digitare un valore.
4. Digitare un valore nel campo **Nome**.
5. Nel campo **Formato ubicazione** fare clic sul pulsante a discesa per aprire la ricerca.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo **Tipo di ubicazione** fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco trovare e selezionare il record desiderato.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Selezionare o deselezionare la casella di controllo **Consenti stati inventario combinati**. Abilitare questa opzione per consentire la combinazione di valori di stato dell'inventario nelle ubicazioni che verranno raggruppate in base a questo profilo di ubicazione. 
12. Selezionare o deselezionare la casella di controllo **Ignora regole per giorni di batch**. Abilitare questa opzione per ignorare la regola di quanti giorni possono differire le date di scadenza del batch di magazzino, per consentire la combinazione dei batch di magazzino che non obbediscono a questa regola.  
13. Selezionare o deselezionare la casella di controllo **Consenti conteggio ciclo**. Abilitare questa opzione per consentire l'esecuzione di cicli di contabilità in tutte le ubicazioni che verranno raggruppate in base a questo profilo di ubicazione. 
14. Espandere o comprimere la sezione **Dimensioni**. La scheda Dimensioni consente di definire i parametri e i metodi per abilitare i calcoli precisi della capacità di carico all'interno di ciascuna ubicazione.  
15. Chiudere la pagina.

## <a name="enable-warehouse-management-parameters"></a>Attivare i parametri di gestione magazzino
1. Andare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Parametri di gestione magazzino**. Per poter elaborare il lavoro del magazzino, è necessario impostare i parametri per il profilo di ubicazione dell'utente, il tipo di ubicazione di gestione temporanea e il tipo di ubicazione della spedizione finale. Non appena il processo in uscita termina in corrispondenza del tipo di ubicazione di spedizione finale definito, le transazioni in uscita correlate verranno aggiornato a "Prelevate".
2. Espandere la sezione **Profili ubicazione**.
3. Nel campo **Ubicazione utente** fare clic sul pulsante a discesa per aprire la ricerca.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Espandere la sezione **Tipi di ubicazione**.
6. Nel campo **Tipo di ubicazione gestione temporanea** fare clic sul pulsante a discesa per aprire la ricerca.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo **Tipo di ubicazione di spedizione finale** fare clic sul pulsante a discesa per aprire la ricerca.
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
10. Chiudere la pagina.

## <a name="define-warehouse-zone-groups"></a>Definire i gruppi di zone magazzinaggio
1. Selezionare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Magazzino > Gruppi di zone magazzinaggio**. Le zone magazzinaggio possono essere utilizzate come opzioni di filtro per controllare i diversi processi di gestione del magazzino. È necessario creare un gruppo di zone prima di poter definire una zona.   
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **ID gruppo zone**.
4. Digitare un valore nel campo **Nome gruppo di zone**.
5. Chiudere la pagina.

## <a name="define-warehouse-zones"></a>Definire le zone magazzinaggio
1. Selezionare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Magazzino > Zone**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **ID zona**.
4. Digitare un valore nel campo **Nome zona**.
5. Nel campo **ID gruppo zone** fare clic sul pulsante a discesa per aprire la ricerca.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Chiudere la pagina.

## <a name="create-locations-using-the-location-setup-wizard"></a>Creare le ubicazioni utilizzando l'Impostazione guidata ubicazione
1. Selezionare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Magazzino > Impostazione guidata ubicazione**.
2. Nel campo **Magazzino** fare clic sul pulsante a discesa per aprire la ricerca.
3. Trovare e selezionare il record desiderato nell'elenco.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo **ID zona** fare clic sul pulsante a discesa per aprire la ricerca.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo **ID profilo ubicazione** fare clic sul pulsante a discesa per aprire la ricerca.
9. Trovare e selezionare il record desiderato nell'elenco.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Nell'elenco contrassegnare la riga selezionata.
12. Immettere un numero nel campo **Dal numero**. I campi Dal numero e Al numero definiscono quante ubicazioni verranno create. Ad esempio, se si imposta Da numero su 1 e Al numero su 3 per tutte e quattro le righe nel formato di ubicazione, verranno create 81 ubicazioni (3x3x3x3).   
13. Immettere un numero nel campo **Al numero**.
14. Nell'elenco trovare e selezionare il record desiderato.
15. Immettere un numero nel campo **Dal numero**.
16. Immettere un numero nel campo **Al numero**.
17. Trovare e selezionare il record desiderato nell'elenco.
18. Immettere un numero nel campo **Dal numero**.
19. Immettere un numero nel campo **Al numero**.
20. Trovare e selezionare il record desiderato nell'elenco.
21. Immettere un numero nel campo **Dal numero**.
22. Immettere un numero nel campo **Al numero**.
23. Fare clic su Crea.

## <a name="create-locations-manually"></a>Creare ubicazioni manualmente
1. Selezionare **Gestione magazzino > Impostazioni > Magazzino > Ubicazioni**. Manualmente la creazione delle ubicazioni all'interno di un magazzino può essere effettuata facilmente. Il nome dell'ubicazione e l'ID di profilo ubicazione sono valori obbligatori. 
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Magazzino**.
4. Digitare un valore nel campo **Ubicazione**. Si sta creando una nuova ubicazione in questo campo, pertanto è necessario immettere un nuovo nome univoco, anziché selezionarne uno esistente.
5. Nel campo **ID profilo ubicazione** digitare un valore.
6. Chiudere la pagina.

## <a name="define-pack-size-categories"></a>Definire le categorie dimensioni collo
1. Selezionare **Gestione magazzino > Impostazioni > Categorie dimensioni collo**. Le categorie di dimensione del collo possono essere utilizzate per raggruppare gli articoli del gruppo con dimensioni di imballaggio fisico simili. In questo esempio la categoria di dimensione del collo verrà utilizzata per verificare la capacità all'ubicazione di prelievo in una zona specifica del magazzino. L'ID categoria di dimensione del collo deve essere assegnato all'entità prodotto rilasciata per utilizzarlo nell'elaborazione dei limiti di stoccaggio.  
2. Fare clic su **Nuovo**.
3. Nel campo **ID categoria dimensioni collo** immettere un valore.
4. Nel campo **Nome categoria dimensioni collo** immettere un valore.
5. Chiudere la pagina.

## <a name="define-location-stocking-limits"></a>Definire i limiti stoccaggio ubicazione
1. Selezionare **Gestione magazzino > Impostazioni > Magazzino > Limiti stoccaggio ubicazione**. I limiti di stoccaggio dell'ubicazione consentono di garantire che il lavoro non venga creato per richiedere che l'inventario venga inserito in un'ubicazione che non ha la capacità fisica di contenerlo.  
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Magazzino**.
4. Nel campo **ID profilo ubicazione** digitare un valore.
5. Nel campo **ID categoria dimensioni collo** immettere un valore.
6. Nel campo **Quantità** immettere un numero.
7. Fare clic su **Salva**.
8. Chiudere la pagina.

## <a name="define-fixed-picking-locations"></a>Definire le ubicazioni di prelievo fisse
1. Selezionare **Gestione magazzino > Impostazioni > Magazzino > Ubicazioni fisse**. È possibile definire le ubicazioni da utilizzare per prodotto o per variante prodotto. È possibile creare più ubicazioni fisse per lo stesso prodotto nello stesso magazzino.     
2. Fare clic su **Nuovo**.
3. Nel campo **Numero articolo**, digitare un valore.
4. Digitare un valore nel campo **Magazzino**.
5. Nel campo **Ubicazione** fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
