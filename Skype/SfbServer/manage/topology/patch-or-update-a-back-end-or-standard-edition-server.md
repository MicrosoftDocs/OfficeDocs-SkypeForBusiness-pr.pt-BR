---
title: Patch ou atualização de um servidor Back-End ou servidor Standard Edition no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumo: Saiba como instalar uma atualização ou patch em um servidor Back-End no Skype para Business Server.'
ms.openlocfilehash: d00f740ef328abe7a58a61d831c4fcd0eae93fc8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911991"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Patch ou atualização de um servidor Back-End ou servidor Standard Edition no Skype para Business Server
 
**Resumo:** Saiba como instalar uma atualização ou patch em um servidor Back-End no Skype para Business Server.
  
Este tópico explica como instalar uma atualização em um servidor do Enterprise Edition Back End ou um servidor Standard Edition.
  
Se for um servidor Back-End para baixo pelo menos 30 minutos enquanto você estiver atualizando-la, os usuários, em seguida, podem entrar no modo de resiliência. Quando a atualização é concluída e os servidores Back-End conectou-se novamente com servidores Front-End do pool, os usuários são retornados para a funcionalidade total. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para atualizar um servidor Back End ou um servidor Standard Edition

1. Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.
    
2. Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.
    
3. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique **Skype para negócios**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**..
    
4. Pare Skype para serviços de Business Server. Na linha de comando, digite:
    
    ```
    Stop-CsWindowsService
    ```

5. Pare o serviço World Wide Web. Na linha de comando, digite:
    
    ```
    net stop w3svc
   ```

6. Feche todas as Skype para windows Business Server Management Shell.
    
7. Atualize a atualização.
    
8. Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique **Skype para negócios**e, em seguida, clique em **Skype do Shell de gerenciamento do servidor de negócios**.
    
9. Pare Skype para serviços de Business Server novamente para capturar assemblies -d do Cache de Assembly Global (GAC). Na linha de comando, digite:
    
    ```
    Stop-CsWindowsService
    ```

10. Reinicie o serviço World Wide Web. Na linha de comando, digite:
    
    ```
    net start w3svc
    ```

11. Aplique as alterações feitas nos bancos de dados SQL Server por meio de uma das seguintes ações:
    
    - Se este for um Enterprise Edition servidor Back-End e não existem bancos de dados colocados neste servidor, como o arquivamento ou bancos de dados de monitoramento, em seguida, digite o seguinte na linha de comando:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Se este for um Enterprise Edition servidor Back-End e existem bancos de dados colocados neste servidor, digite o seguinte na linha de comando:
    
    ```
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Caso se trate de um servidor Standard Edition, digite o seguinte na linha de comando:
    
    ```
    Install-CsDatabase -Update -LocalDatabases

    ```
