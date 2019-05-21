---
title: Patch ou atualização de um servidor back-end do servidor ou da edição Standard no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumo: saiba como instalar uma atualização ou um patch em um servidor back-end no Skype for Business Server.'
ms.openlocfilehash: b8a0280577147e37c52ab11aa3061541bae27610
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275119"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Patch ou atualização de um servidor back-end do servidor ou da edição Standard no Skype for Business Server
 
**Resumo:** Saiba como instalar uma atualização ou patch em um servidor back-end no Skype for Business Server.
  
Este tópico explica como instalar uma atualização em um servidor back-end da edição Enterprise ou um servidor Standard Edition.
  
Se um servidor back-end estiver inoperante durante pelo menos 30 minutos enquanto você estiver atualizando, os usuários poderão entrar no modo de resiliência. Quando a atualização estiver concluída e os servidores back-end novamente conectados com os servidores de front-end do pool, os usuários retornarão à funcionalidade completa. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para atualizar um servidor Back End ou um servidor Standard Edition

1. Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.
    
2. Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.
    
3. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**...
    
4. Interrompa os serviços do Skype for Business Server. Na linha de comando, digite:
    
    ```
    Stop-CsWindowsService
    ```

5. Pare o serviço World Wide Web. Na linha de comando, digite:
    
    ```
    net stop w3svc
   ```

6. Feche todas as janelas do Shell de gerenciamento do Skype for Business Server.
    
7. Atualize a atualização.
    
8. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, clique em **todos os programas**, clique em **Skype for Business**e, em seguida, clique em **Shell de gerenciamento do Skype for Business Server**.
    
9. Pare os serviços do Skype for Business Server novamente para capturar assemblies global assembly cache (GAC)-d. Na linha de comando, digite:
    
    ```
    Stop-CsWindowsService
    ```

10. Reinicie o serviço World Wide Web. Na linha de comando, digite:
    
    ```
    net start w3svc
    ```

11. Aplique as alterações feitas nos bancos de dados SQL Server por meio de uma das seguintes ações:
    
    - Se este for um servidor back-end da edição Enterprise e não houver bancos de dados posicionados neste servidor, como arquivar ou monitorar bancos de dados, digite o seguinte na linha de comando:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Se este for um servidor back-end do Enterprise Edition e houver bancos de dados posicionados neste servidor, digite o seguinte em uma linha de comando:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Se esse for um servidor Standard Edition, digite o seguinte em uma linha de comando:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
