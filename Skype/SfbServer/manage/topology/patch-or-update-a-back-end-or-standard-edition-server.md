---
title: Corrigir ou atualizar um servidor back-end ou servidor Standard Edition no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumo: Saiba como instalar uma atualização ou um patch em um Servidor Back End no Skype for Business Server.'
ms.openlocfilehash: 3e5e0cda1604f3144e853cfa3bf7bcc45e7d0c2f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826301"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Corrigir ou atualizar um servidor back-end ou servidor Standard Edition no Skype for Business Server
 
**Resumo:** Saiba como instalar uma atualização ou um patch em um servidor back-end no Skype for Business Server.
  
Este tópico explica como instalar uma atualização em um servidor Back End Enterprise Edition ou em um servidor Standard Edition.
  
Se o servidor Back End estiver inoperante por ao menos 30 minutos enquanto você o estiver atualizando, os usuários podem entrar em modo de resiliência. Quando a atualização for concluída e os servidores Back End tiver novamente se conectado aos servidores Front End no pool, os usuários são retornados à funcionalidade total. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para atualizar um servidor back-end ou um servidor Standard Edition

1. Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.
    
2. Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.
    
3. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** no **Skype for Business** e, em seguida, clique em Shell de Gerenciamento do Skype for Business **Server.**
    
4. Pare os serviços do Skype for Business Server. Na linha de comando, digite:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Pare o serviço World Wide Web. Na linha de comando, digite:
    
    ```PowerShell
    net stop w3svc
   ```

6. Feche todas as janelas do Shell de Gerenciamento do Skype for Business Server.
    
7. Instale a atualização.
    
8. Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business** e no Shell de Gerenciamento do Skype for Business **Server.**
    
9. Pare os serviços do Skype for Business Server novamente para capturar assemblies GAC (Cache de Assembly Global) -d. Na linha de comando, digite:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Reinicie o serviço World Wide Web. Na linha de comando, digite:
    
    ```PowerShell
    net start w3svc
    ```

11. Aplique as alterações feitas nos bancos de dados do SQL Server fazendo um dos seguintes:
    
    - Se for um Servidor de Back End Enterprise Edition e não houver bancos de dados alocados neste servidor, como os bancos de dados de Arquivamento ou monitoramento, digite o seguinte na linha de comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Se for um Servidor de Back End Enterprise Edition e houver bancos de dados alocados neste servidor, digite o seguinte na linha de comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Se for um servidor Standard Edition, digite o seguinte na linha de comando:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
