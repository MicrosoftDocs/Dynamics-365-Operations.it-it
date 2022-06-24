---
title: Creare un account di archiviazione di Azure nel portale di Azure
description: Questo articolo spiega come creare un account di Archiviazione di Azure per la fatturazione elettronica.
author: dkalyuzh
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkalyuzh
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 4380261140086bcb278162f8dc70b39eaa7078fe
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898020"
---
# <a name="create-an-azure-storage-account-in-the-azure-portal"></a>Creare un account di archiviazione di Azure nel portale di Azure

[!include [banner](../includes/banner.md)]

Tutti i file elettronici che vengono generati dal servizio di fatturazione elettronica o che passano al servizio durante l'elaborazione sono archiviati nei contenitori dell'account di archiviazione di Microsoft Azure. Per fare in modo che la fatturazione elettronica possa accedere a tali contenitori, è necessario fornire il token SAS (Shared Access Signature) dell'account di archiviazione al servizio di fatturazione elettronica. Inoltre, per fare in modo che il token sia archiviato in modo sicuro, non fornire direttamente il token SAS. Al contrario, archivialo in un Azure Key Vault e fornisci un segreto di Azure Key Vault.

1. Apri l'account di archiviazione che intendi utilizzare con il servizio per la fatturazione elettronica.
2. Vai a **Impostazioni** \> **Configurazione** e assicurati che il parametro **Consenti l'accesso pubblico al BLOB** sia impostato su **Abilitato**.
3. Passa ad **Archiviazione dati** \> **Contenitori** e crea un contenitore.
4. Immetti un nome per il contenitore e imposta il campo **Livello di accesso pubblico** su **Privato (nessun accesso anonimo)**.
5. Apri il nuovo contenitore e vai a **Impostazioni** \> **Criteri di accesso**.
6. Seleziona **Aggiungi criteri** per aggiungere un criterio di accesso archiviato.
7. Imposta il campo **Identificatore** a seconda dei casi.
8. Nel campo **Autorizzazioni** seleziona tutte le autorizzazioni.

    ![Tutte le autorizzazioni selezionate nel campo Autorizzazioni della finestra di dialogo Aggiungi criteri.](media/e-invoicing-azure-1.png)

9. Immettere le date di inizio e di fine. La data di fine dovrebbe essere nel futuro.
10. Seleziona **OK** per salvare i criteri, quindi salva le modifiche nel contenitore.
11. Passa a **Impostazioni** \> **Token di accesso condiviso** e imposta i valori del campo.
12. Immettere le date di inizio e di fine. La data di fine dovrebbe essere nel futuro.
13. Nel campo **Autorizzazioni**, seleziona le seguenti autorizzazioni:

    - Letto
    - Aggiungi
    - Crea
    - Scrittura
    - Elimina
    - Elenco

14. Selezionare **Genera URL e token SAS**.
15. Copiare e memorizzare il valore nel campo **URL SAS BLOB**. Questo valore verrà utilizzato in seguito nella procedura successiva e verrà indicato come *URI della firma di accesso condiviso*.
16. Apri l'Azure Key Vault che intendi utilizzare con la fatturazione elettronica.
17. Vai a **Impostazioni** \> **Segreti**, quindi seleziona **Genera/Importa** per creare un segreto.
18. Nella pagina **Crea un segreto**, nel campo **Opzioni di caricamento**, seleziona **Manuale**.
19. Immettere il nome del segreto. Questo nome verrà utilizzato durante la configurazione del servizio in Regulatory Configuration Service (RCS) e verrà indicato come *nome segreto di Azure Key Vault*. Per altre informazioni su come configurare RCS, vedi [Configurare Regulatory Configuration Services (RCS)](e-invoicing-set-up-rcs.md).
20. Nel campo **Valore**, immetti l'URI della firma di accesso condiviso che hai copiato in precedenza.
21. Selezionare **Crea**.
