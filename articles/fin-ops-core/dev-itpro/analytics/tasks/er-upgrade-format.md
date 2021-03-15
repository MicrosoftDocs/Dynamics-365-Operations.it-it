---
title: ER Aggiornare il formato adottandone una nuova versione di base
description: In questo argomento viene illustrato come mantenere una configurazione di formato per la creazione di report elettronici (ER).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionTable, ERSolutionCreateDropDialog, EROperationDesigner, ERComponentTypeDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b76fb09ff961a3100b6a4bf890c1b12e6a0a2771
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092568"
---
# <a name="er-upgrade-your-format-by-adopting-a-new-base-version-of-that-format"></a>ER Aggiornare il formato adottandone una nuova versione di base

[!include [banner](../../includes/banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può gestire una configurazione di formato per la creazione di report elettronici (ER). Questa procedura illustra come sia possibile creare una versione personalizzata di un formato in base al formato ricevuto da un provider di configurazione (CP). Illustra anche come adottare una nuova versione di base di quel formato.

Per completare questi passaggi, è necessario completare i passaggi delle procedure "Creare un provider di configurazione e contrassegnarlo come attivo" e "Utilizzare il formato creato per generare documenti elettronici per i pagamenti". Queste operazioni possono essere eseguite nella società GBSI.

## <a name="select-format-configuration-for-customization"></a>Selezionare la configurazione del formato per la personalizzazione
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.

    In questo esempio, la società campione Litware, Inc. (https://www.litware.com) fungerà da provider di configurazione che supporta le configurazioni dei formati per i pagamenti elettronici di un paese specifico.    La società campione Proseware, Inc. (http://www.proseware.com) fungerà da utente della configurazione del formato che Litware, Inc. ha fornito. Proseware, Inc. utilizza formati in determinate aree del paese.  
2. Fare clic su Configurazioni report.
3. Fare clic su Mostra filtri.
4. Applicare i filtri seguenti: immettere un valore di filtro "BACS (fittizio per il Regno Unito)" nel campo "Nome" utilizzando l'operatore di filtro "inizia con".
  
    La configurazione selezionata del formato BACS (fittizia per il Regno Unito) è posseduta dal provider Litware, Inc.  

5. Fare clic su Mostra filtri.
6. Nell'elenco trovare e selezionare il record desiderato.

    La versione del formato con stato Completato verrà utilizzata da Proseware, Inc. per la personalizzazione.  

## <a name="create-a-new-configuration-for-your-custom-format-of-electronic-document"></a>Creare una nuova configurazione per il formato personalizzato del documento elettronico
Proseware, Inc. ha ricevuto la versione 1.1 della configurazione BACS (fittizia per il Regno Unito) contenente il formato iniziale per generare i documenti di pagamento elettronico da Litware, Inc. in conformità alla sottoscrizione del servizio effettuata. Proseware, Inc. desidera iniziare a usare questa come standard per il paese, ma è necessaria una certa personalizzazione per supportare i requisiti regionali specifici. Proseware, Inc. desidera anche mantenere la possibilità di aggiornare un formato personalizzato non appena viene fornito da Litware, Inc. e desidera eseguire questo aggiornamento al costo più basso.  

A tale scopo, Proseware, Inc. deve creare una configurazione tramite la configurazione BACS (fittizia per il Regni Unito) di Litware, Inc.  

1. Chiudere la pagina.
2. Selezionare Proseware, Inc. per renderlo un provider attivo.
3. Fare clic su Imposta attivo.
4. Fare clic su Configurazioni report.
5. Nella struttura espandere "Pagamenti (modello semplificato)".
6. Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".

    Selezionare la configurazione BACS (fittizia per il Regno Unito) da Litware, Inc. Proseware, inc utilizzerà la versione 1.1 come base per la versione personalizzata.  

7. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .

    Ciò consente di creare una nuova configurazione per un formato di pagamento personalizzato.  

8. Nel campo Nuovo immettere "Derivare da nome: BACS (fittizia per regno Unito), Litware, Inc.".

    Selezionare l'opzione Deriva per confermare l'utilizzo di BACS (fittizia per il Regno Unito) come base per creare la versione personalizzata.  

9. Nel campo Nome digitare "BACS (personalizzata, fittizia per il Regno Unito)".
10. Nel campo Descrizione digitare 'Pagamento fornitore BACS (personalizzata, fittizia per il Regno Unito)'.

    Il provider di configurazione attivo (Proseware, Inc.) viene inserito automaticamente in questo punto. Tale provider potrà gestire la configurazione. Altri provider possono utilizzare la configurazione, ma non potranno gestirla.  

11. Fare clic su Crea configurazione.

## <a name="customize-your-format-for-the-electronic-document"></a>Personalizzare il formato per il documento elettronico
1. Fare clic su Progettazione.
2. Fare clic su Espandi/Comprimi.
3. Fare clic su Espandi/Comprimi.
4. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca'.
5. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
6. Nella struttura selezionare "XML\Elemento".
7. Nel campo nome digitare "IBAN".
8. Fare clic su OK.
9. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\IBAN'.
10. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
11. Nella struttura selezionare "Testo\Stringa".
12. Fare clic su OK.
13. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome\Stringa'.
14. Nel campo Lunghezza massima immettere "60".
15. Fare clic sulla scheda Mapping.
16. Nella struttura , espandere il "modello".
17. Nella struttura espandere "modello\Pagamenti".
18. Nella struttura espandere "modello\Pagamenti\Creditore".
19. Nella struttura espandere "modello\Pagamenti\Creditore\Conto".
20. Nella struttura selezionare 'modello\Pagamenti\Creditore\Conto\IBAN'.
21. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo = model.Payments\Fornitore\Banca\IBAN\Stringa'.
22. Fare clic su Associa.
23. Fare clic su Salva.

## <a name="validate-the-customized-format"></a>Convalidare il formato personalizzato
1. Fare clic su Convalida.

    Convalidare le modifiche personalizzate del layout del formato e del mapping dei dati per assicurarsi che tutte le associazioni siano giuste.  

2. Chiudere la pagina.

## <a name="change-the-status-of-the-current-version-of-the-custom-format-configuration"></a>Modificare lo stato della versione corrente della configurazione del formato personalizzato
Modificare lo stato della configurazione designata del formato da Bozza a Completato per renderla disponibile per la generazione del documento di pagamento.  

1. Fare clic su Cambia stato.

    La versione corrente della configurazione selezionata è nello stato Bozza.  

2. Fare clic su Completa.
3. Nel campo Descrizione digitare un valore.
4. Fare clic su OK.
5. Nell'elenco trovare e selezionare il record desiderato.

    Si noti che la configurazione creata viene salvata come versione completata 1.1.1. Ciò significa che è la versione 1 del formato BACS personalizzato (personalizzata, fittizia per il Regno Unito), basato sulla versione 1 del formato BACS (fittizia per il Regno Unito), che si basa sulla versione 1 del modello dati Pagamenti (modello semplificato).  

## <a name="test-the-customized-format-to-generate-payment-files"></a>Testare il formato personalizzato per generare file di pagamento
Completare i passaggi della procedura "Utilizzare il formato creato per generare documenti elettronici per i pagamenti" in una sessione parallela di Finance and Operations. Selezionare il formato BACS (personalizzata, fittizia per il Regno Unito) nei parametri del metodo di pagamento elettronico. Verificare che il file di pagamento creato contenga il nodo XML introdotto di recente che presenta il codice di IBAN in conformità ai requisiti regionali.  

## <a name="update-the-existing-country-specific-configuration"></a>Aggiornare la configurazione specifica di ciascun paese esistente
Litware, Inc. deve aggiornare la configurazione BACS (fittizia per il Regno Unito) e adottare nuovi requisiti per il paese per gestire il formato del documento elettronico. Successivamente, questo verrà accluso in una nuova versione della configurazione che verrà offerta per gli iscritti al servizio, inclusa Proseware, Inc.  

Nei processi reali correlati all'erogazione del servizio ogni nuova versione di BACS (fittizia per il Regno Unito) può essere importata da Proseware, Inc. dall'archivio LCS delle configurazioni di Litware, Inc. In questa procedura simuleremo questo processo aggiornando BACS (fittizia per il Regno Unito) per conto di un provider di servizi.  

1. Chiudere la pagina.
2. Selezionare Litware, Inc. .
3. Fare clic su Imposta attivo.
4. Fare clic su Configurazioni report.
5. Nella struttura espandere "Pagamenti (modello semplificato)".
6. Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".

    La versione bozza di proprietà del BACS (fittizia per il Regno Unito) del provider Litware, Inc. viene selezionata per apportare modifiche per supportare i nuovi requisiti specifici di ciascun paese.  

## <a name="localize-the-base-format-of-the-electronic-document"></a>Localizzare il formato di base del documento elettronico
Si supponga che siano presenti nuovi requisiti specifici del paese che Litware, Inc. deve supportare:  

- Un valore per il codice SWIFT della banca del creditore in ogni transazione di pagamento.
- Un limite di 100 caratteri per la lunghezza del testo per il nome del fornitore in un file di creazione.  
- Nuovi requisiti specifici del paese  
- Selezionare la versione bozza della configurazione desiderata per introdurre le modifiche necessarie.  


1. Fare clic su Progettazione.
2. Fare clic su Espandi/Comprimi.
3. Fare clic su Espandi/Comprimi.
4. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca'.
5. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
6. Nella struttura selezionare "XML\Elemento".
7. Nel campo Nome digitare "SWIFT".
8. Fare clic su OK.
9. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Banca\SWIFT'.
10. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
11. Nella struttura selezionare "Testo\Stringa".
12. Fare clic su OK.
13. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo\Fornitore\Nome\Stringa'.
14. Nel campo Lunghezza massima immettere "100".
15. Fare clic sulla scheda Mapping.
16. Nella struttura , espandere il "modello".
17. Nella struttura espandere "modello\Pagamenti".
18. Nella struttura espandere "modello\Pagamenti\Creditore".
19. Nella struttura espandere "modello\Pagamenti\Creditore\Agente".
20. Nella struttura selezionare 'modello\Pagamenti\Creditore\Agente\SWIFT'.
21. Nella struttura selezionare 'Xml\Messaggio\Pagamenti\Articolo = model.Payments\Fornitore\Banca\SWIFT\Stringa'.
22. Fare clic su Associa.
23. Fare clic su Salva.

## <a name="validate-the-localized-format"></a>Convalidare il formato localizzato
1. Fare clic su Convalida.
2. Chiudere la pagina.

## <a name="change-the-status-of-the-current-version-of-the-base-format-configuration"></a>Modificare lo stato della versione corrente della configurazione del formato di base
Modificare lo stato della configurazione aggiornata del formato di base da Bozza a Completato per renderla disponibile per la creazione di documenti di pagamento e di aggiornamenti delle configurazioni del formato che ne derivano.  

1. Fare clic su Cambia stato.

    La versione corrente della configurazione selezionata è nello stato Bozza.  

2. Fare clic su Completa.
3. Nel campo Descrizione digitare un valore.
4. Fare clic su OK.
5. Nell'elenco trovare e selezionare il record desiderato.

## <a name="change-the-base-version-for-the-custom-format-configuration"></a>Cambiare la versione di base per la configurazione del formato personalizzato

Proseware, Inc. è informata che una nuova versione 1.2 della configurazione BACS (fittizia per il Regno Unito) è disponibile per generare documenti di pagamento elettronici in conformità ai requisiti specifici del paese annunciati di recente. Proseware, Inc. desidera iniziare a usarla come standard per il paese.  

A questo scopo, Proseware, Inc. deve modificare la versione della configurazione di base con la configurazione personalizzata BACS (personalizzata fittizia per il Regno Unito). Anziché la versione 1.1 della BACS (fittizia per il Regno Unito), usare la nuova versione 1.2.  

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
2. Selezionare il provider Proseware, Inc. per renderlo un provider attivo.
3. Fare clic su Imposta attivo.
4. Fare clic su Configurazioni report.
5. Nella struttura espandere "Pagamenti (modello semplificato)".
6. Nella struttura espandere "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)".
7. Nella struttura selezionare "Pagamenti (modello semplificato)\BACS (fittizia per Regno Unito)\BACS (personalizzata, fittizia per Regno Unito)".

    Selezionare la configurazione BACS (personalizzata, fittizia per il Regno Unito), posseduta da Proseware, Inc.  

    Utilizzare la versione bozza della configurazione selezionata per introdurre le modifiche necessarie.  

8. Fare clic su Riassegna.

    Selezionare la nuova versione 1.2 della configurazione di base che dovrà essere applicata come nuova base per aggiornare la configurazione.  

9. Fare clic su OK.

    Alcuni conflitti sono stati individuati nella fusione della versione personalizzata e della nuova versione di base che rappresentano modifiche di formato che non possono essere unite automaticamente.  

## <a name="resolve-rebase-conflicts"></a>Risolvere conflitti di riassegnazione
1. Fare clic su Progettazione.
    
    Le modifiche al limite di lunghezza del testo del nome del fornitore non possono essere risolte automaticamente. Di conseguenza, questo viene presentato in un elenco di conflitti. Per ogni conflitto di tipo aggiornamento sono disponibili le seguenti opzioni: Applica valori di base precedenti (pulsante in alto nella griglia) per introdurre il valore di base della versione precedente (0 nel nostro caso).  - Applica un valore di base (pulsante in alto nella griglia) per introdurre il nuovo valore di base della versione (100 nel nostro caso).  - Mantiene il proprio valore personalizzato (60 nel nostro caso).  Fare clic su Applica valori di base per applicare un limite specifico per paese di 100 caratteri per la lunghezza del testo del nome del fornitore.  

    Proseware, Inc. e Litware, Inc. hanno versioni locali e personalizzate di questo formato utilizzando i codici SWIFT e IBAN con i relativi componenti che vengono automaticamente unite nel formato di gestione.  

2. Fare clic su Applica valori di base.

    Fare clic su Applica valori di base per applicare il limite specifico per paese di 100 caratteri per i nomi dei fornitori.  

3. Fare clic su Salva.

    Il salvataggio del formato rimuoverà i conflitti risolti dall'elenco dei conflitti.  

4. Chiudere la pagina.

## <a name="change-the-status-of-the-new-version-of-the-custom-format-configuration"></a>Modificare lo stato della versione nuova della configurazione del formato personalizzato
1. Fare clic su Cambia stato.

    Modificare lo stato della configurazione aggiornata e personalizzata del formato da Bozza a Completato. Questo renderà disponibile la configurazione del formato per la generazione dei documenti di pagamento. La versione corrente della configurazione selezionata è nello stato Bozza.  

2. Fare clic su Completa.
3. Nel campo Descrizione digitare un valore.
4. Fare clic su OK.

    La configurazione creata viene salvata come versione 1.2.2 completata: versione 2 del formato di base BACS (personalizzata, fittizia per il Regno Unito), basata sulla versione 2 del formato di base BACS (fittizia per il Regno Unito), basato sulla versione 1 del modello dati Pagamenti (modello semplificato).  

## <a name="test-the-customized-format-for-payment-files-generation"></a>Testare il formato personalizzato per la generazione di file di pagamento
Completare i passaggi della procedura "Utilizzare il formato creato per generare documenti elettronici per i pagamenti" in una sessione parallela di Finance and Operations. Selezionare il formato "BACS (personalizzata, fittizia per il Regno Unito)" creato nei parametri del metodo di pagamento elettronico. Verificare che il file di pagamento creato contenga il nodo XML introdotto di recente da Proseware, Inc. che presenta il codice conto IBAN in conformità ai requisiti regionali. Il file deve inoltre contenere il nodo XML introdotto di recente da Litware, Inc. che presenta il codice bancario SWIFT in conformità ai requisiti del paese.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]