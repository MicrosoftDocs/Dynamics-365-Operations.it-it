---
title: Definire la dipendenza delle configurazioni ER in altri componenti
description: Questo articolo descrive come progettare una configurazione di creazione di report elettronici (ER) e specificarne la dipendenza da altri componenti software.
author: kfend
ms.date: 07/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ff9d1edab13de49ae676708865ebe02a82db34e0
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291266"
---
# <a name="define-the-dependency-of-er-configurations-on-other-components"></a>Definire la dipendenza delle configurazioni ER in altri componenti

[!include [banner](../../includes/banner.md)]

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività ER Gestire configurazioni di mapping di modelli ed è necessario disporre dell'accesso a Microsoft Dynamics Lifecycle Services (LCS).

Questa procedura descrive come progettare una configurazione ER e come specificarne la dipendenza da altri componenti software, in modo da garantire che la configurazione venga scaricata correttamente in una versione specifica di Finanza e operazioni. In questo esempio verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. 

Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici. Queste operazioni possono essere eseguite in qualsiasi società perché le configurazioni ER sono condivise tra tutte le società. 

1. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
    * Verificare che la struttura delle configurazioni contenga la configurazione "Modello dati di esempio" e gli elementi secondari. In caso contrario, completare i passaggi nella guida attività descritti in ER Gestire configurazioni di mapping di modelli, quindi avviare nuovamente la guida.   

## <a name="define-the-dependency-of-er-configurations-from-other-components"></a>Definire la dipendenza delle configurazioni ER da altri componenti
1. Nella struttura espandere "Sample data model".
2. Nella struttura selezionare "Sample data model\Sample mapping".
    * È stata selezionata la versione bozza della configurazione di mapping del modello "Mapping di esempio". Verrà ora definita la dipendenza relativa da altri componenti software. Questo passaggio è considerato un prerequisito per il controllo del download di questa versione della configurazione da un archivio ER e di altri ulteriori usi della versione.   
3. Espandere la sezione Prerequisiti.
    * Si noti che il gruppo di prerequisiti "Implementazioni" è stato aggiunto automaticamente in questa fase. Questo gruppo include il componente di prerequisiti che fa riferimento alla configurazione del modello dati con il flag di implementazione attivato. Il flag indica che la configurazione di mapping "Mapping di esempio" viene considerata l'implementazione del modello dati "Modello dati di esempio". Questo componente comporterà il download da parte di ER della configurazione di mapping di esempio da un archivio ER tutte le volte che viene scaricata la configurazione del modello dati di esempio.   
4. Fare clic su Modifica.
    * È possibile specificare una singola dipendenza della versione corrente di una configurazione da un componente software tramite la definizione del tipo di componente e della versione o di un intervallo di versioni del componente.  
    * Le dipendenze desiderate possono essere raggruppate tra loro. Quando si seleziona il tipo di raggruppamento "Tutti", la condizione di dipendenza del gruppo viene considerato soddisfatta quando ogni condizione di dipendenza dal gruppo o dal gruppo secondario è soddisfatta. Quando si seleziona il tipo di raggruppamento "Uno di", la condizione di dipendenza del gruppo viene considerato soddisfatta quando almeno una condizione di dipendenza dal gruppo è soddisfatta.   
5. Fare clic su Nuovo.
6. Selezionare il componente prerequisito del prodotto.
7. Selezionare Microsoft Dynamics 365 for Operations (1611).
8. Nel campo Versione digitare "[7.1.1541.3036,8]".
    * [7.1.1541.3036,8]  
    * Le dipendenze immesse vengono valutate quando la configurazione viene scaricata da un archivio ER. Questa versione di configurazione viene scaricata dall'archivio ER quando la versione 1 della configurazione "Modello dati di esempio" è già impostata o scaricata in anticipo. Se scaricata in anticipo, deve essere completata in Finanza e operazioni versione 7.1.1541.3036 o successiva, ma comunque inferiore alla versione principale 8.   
9. Fare clic su Salva.
10. Chiudere la pagina.
11. Fare clic su Cambia stato.
12. Fare clic su Completa.
13. Fare clic su OK.
14. Nella struttura selezionare "Sample data model\Sample mapping (alternative)".
15. Fare clic su Modifica.
16. Fare clic su Nuovo.
17. Selezionare il componente prerequisito del prodotto.
18. Selezionare Microsoft Dynamics AX 7.0 RTW.
19. Nel campo Versione digitare "[7.0.1265.3015,7.1]".
    * [7.0.1265.3015,7.1]  
    * Le dipendenze verranno valutate quando la configurazione viene scaricata da un archivio ER. Questa versione di configurazione viene scaricata dall'archivio ER quando la versione 1 della configurazione "Modello dati di esempio" è già impostata o scaricata in anticipo. Se scaricata in anticipo, deve essere completata in Microsoft Dynamics 365 Finance, Enterprise Edition, versione 7.0.1265.3015 o successiva, ma comunque inferiore alla versione principale 1.   
20. Fare clic su Salva.
21. Chiudere la pagina.
22. Fare clic su Cambia stato.
23. Fare clic su Completa.
24. Fare clic su OK.

## <a name="configure-the-er-repository"></a>Configurare l'archivio ER
1. Chiudere la pagina.
2. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Aprire l'elenco degli archivi ER per il provider ER corrente, Litware, Inc.  
3. Nell'elenco contrassegnare la riga selezionata.
4. Fare clic su Archivi.
5. Fare clic su Mostra filtri.
6. Immettere un valore di filtro "LCS" nel campo Nome utilizzando l'operatore di filtro "contiene".
    * Se l'archivio LCS è già registrato per il provider ER corrente, è possibile ignorare i passaggi rimanenti in questa attività secondaria. Se l'archivio LCS non è già registrato, completare i passaggi rimanenti.   
7. Fare clic su Aggiungi per aprire la finestra di dialogo a discesa.
8. Nel campo Tipo di archivio di configurazioni immettere "LCS".
9. Fare clic su Crea archivio.
10. Nel campo Progetto immettere o selezionare un valore.
    * Selezionare il progetto LCS desiderato nell'area di ricerca del campo "Progetto".  
11. Fare clic su OK.
12. Chiudere la pagina.

## <a name="upload-configurations-to-lcs"></a>Caricare le configurazione in LCS
1. Fare clic su Configurazioni report.
2. Nella struttura selezionare "Sample data model".
3. Selezionare la versione completata di questa configurazione.
4. Fare clic su Cambia stato.
5. Fare clic su Condividi.
6. Fare clic su OK.
    * La versione 1 di questa configurazione di modello è stata caricata in LCS utilizzando il progetto LCS per l'archivio ER configurato in precedenza.   
7. Nella struttura espandere "Sample data model".
8. Nella struttura selezionare "Sample data model\Sample mapping".
9. Selezionare la versione completata di questa configurazione.
10. Fare clic su Cambia stato.
11. Fare clic su Condividi.
12. Fare clic su OK.
    * La versione 1.1 di questa configurazione di mapping di modello è stata caricata in LCS utilizzando il progetto LCS per l'archivio ER configurato in precedenza.   
13. Nella struttura selezionare "Sample data model\Sample mapping (alternative)".
14. Selezionare la versione completata di questa configurazione.
15. Fare clic su Cambia stato.
16. Fare clic su Condividi.
17. Fare clic su OK.
    * La versione 1.1 di questa configurazione di mapping di modello è stata caricata in LCS utilizzando il progetto LCS per l'archivio ER configurato in precedenza.   

## <a name="evaluate-er-configuration-dependencies"></a>Valutare le dipendenze di configurazione ER
Le configurazioni create dal sistema verranno eliminate e scaricate nuovamente dall'archivio LCS.  
1. Nella struttura selezionare "Sample data model\Sample mapping".
2. Fare clic su Elimina.
3. Fare clic su Sì.
4. Nella struttura selezionare "Sample data model\Sample mapping (alternative)".
5. Fare clic su Elimina.
6. Fare clic su Sì.
7. Nella struttura selezionare "Sample data model\Sample format".
8. Fare clic su Elimina.
9. Fare clic su Sì.
10. Nella struttura selezionare "Sample data model".
11. Fare clic su Elimina.
12. Fare clic su Sì.
13. Chiudere la pagina.
    * Aprire l'elenco degli archivi ER per il provider ER corrente, Litware, Inc.  
14. Fare clic su Archivi.
15. Fare clic su Mostra filtri.
16. Immettere un valore di filtro "LCS" nel campo Nome utilizzando l'operatore di filtro "contiene".
17. Fare clic su Apri.
18. Nella struttura selezionare "Sample data model".
    * Si noti che è possibile visualizzare una valutazione per conoscere se le condizioni preliminari sono state soddisfatte per ogni versione delle configurazioni ER per l'archivio corrente. Per visualizzare la valutazione, fare clic su Controlla prerequisiti.   
19. Fare clic su Controlla prerequisiti.
20. Fare clic su Importa.
21. Fare clic su Sì.
22. Chiudere la pagina.
23. Chiudere la pagina.
24. Chiudere la pagina.
25. Passare a Amministrazione organizzazione > Reporting elettronico > Configurazioni.
26. Nella struttura espandere "Sample data model".
    * Si noti che la configurazione di mapping "Mapping di esempio" del modello è stata scaricata con la configurazione del modello dati selezionato. I due file verranno scaricati insieme perché il mapping di esempio è stato definito come implementazione del modello dati selezionato e perché è applicabile per l'applicazione. La configurazione "Mapping di esempio (alternativo)" non è stata scaricata perché la condizione per versione dell'applicazione non è soddisfatta.   
    * Se accedi alle app per la finanza e le operazioni, registri lo stesso provider, accedi allo stesso progetto LCS e scarichi la stessa configurazione del modello dati, verrà scaricata la configurazione "Mapping di esempio (alternativo)", mentre la configurazione "Mapping di esempio" verrà ignorata.  

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestire il ciclo di vita della configurazione per la creazione di report elettronici](../general-electronic-reporting-manage-configuration-lifecycle.md)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

