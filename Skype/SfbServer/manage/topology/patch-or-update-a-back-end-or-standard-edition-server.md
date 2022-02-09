---
title: Corrigir ou atualizar um servidor back-end ou Edição Standard no Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
description: 'Resumo: saiba como instalar uma atualização ou patch em um Servidor Back-End em Skype for Business Server.'
ms.openlocfilehash: 69c597aae05950d38b78c8e84d46165a68fd8959
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397655"
---
# <a name="patch-or-update-a-back-end-server-or-standard-edition-server-in-skype-for-business-server"></a>Corrigir ou atualizar um servidor back-end ou Edição Standard no Skype for Business Server
 
**Resumo:** Saiba como instalar uma atualização ou patch em um Servidor Back-End Skype for Business Server.
  
Este tópico explica como instalar uma atualização em um servidor Edição Enterprise Back-End ou um Edição Standard servidor.
  
Se o servidor Back End estiver inoperante por ao menos 30 minutos enquanto você o estiver atualizando, os usuários podem entrar em modo de resiliência. Quando a atualização for concluída e os servidores Back End tiver novamente se conectado aos servidores Front End no pool, os usuários são retornados à funcionalidade total. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.
  
### <a name="to-update-a-back-end-server-or-standard-edition-server"></a>Para atualizar um servidor back-end ou Edição Standard servidor

1. Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.
    
2. Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.
    
3. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, Skype for Business** e clique Skype for Business Server **Shell de Gerenciamento**..
    
4. Pare Skype for Business Server serviços. Na linha de comando, digite:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

5. Pare o serviço World Wide Web. Na linha de comando, digite:
    
    ```PowerShell
    net stop w3svc
   ```

6. Feche todas as Skype for Business Server do Shell de Gerenciamento.
    
7. Instale a atualização.
    
8. Inicie o shell Skype for Business Server gerenciamento: clique em **Iniciar, em** Todos os **Programas, Skype for Business** e clique Skype for Business Server **Shell de Gerenciamento**.
    
9. Pare Skype for Business Server serviços novamente para capturar assemblies gac (Cache de Assembly Global) -d. Na linha de comando, digite:
    
    ```PowerShell
    Stop-CsWindowsService
    ```

10. Reinicie o serviço World Wide Web. Na linha de comando, digite:
    
    ```PowerShell
    net start w3svc
    ```

11. Aplique as alterações feitas nos bancos de dados SQL Server, fazendo um dos seguintes:
    
    - Se esse for um servidor Edição Enterprise back-end e não houver bancos de dados alocados neste servidor, como bancos de dados de Arquivamento ou Monitoramento, digite o seguinte em uma linha de comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    ```

    - Se esse for um servidor Edição Enterprise back-end e houver bancos de dados alocados neste servidor, digite o seguinte em uma linha de comando:
    
    ```PowerShell
    Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    ```

    - Se for um servidor Edição Standard, digite o seguinte em uma linha de comando:
    
    ```PowerShell
    Install-CsDatabase -Update -LocalDatabases

    ```
