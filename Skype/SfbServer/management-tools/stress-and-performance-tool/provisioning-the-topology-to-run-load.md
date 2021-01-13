---
title: Provisionamento da topologia para executar a carga em cenários de Stress and Performance
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Alterações ou provisionamento da topologia do Skype for Business Server 2015 para permitir que os usuários executem com êxito a ferramenta Stress and Performance.
ms.openlocfilehash: 8d422497d11c9e56e4d5b205269a09f96dffc136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814931"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Provisionando a topologia para executar a carga em cenários de Stress and Performance
 
Alterações ou provisionamento da topologia do Skype for Business Server 2015 para permitir que os usuários executem com êxito a ferramenta Stress and Performance.
  
Dependendo das configurações existentes para sua implantação do Skype for Business Server 2015, talvez seja necessário fazer algumas alterações em seu ambiente. A seguir está uma lista dessas alterações:
  
1. Definir a política de execução do Windows PowerShell como Irrestrito. Se você não tiver certeza para o que ele está definido no momento, poderá abrir o Shell de Gerenciamento do Skype for Business Server e executar este comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Se o valor Irrestrito não for retornado, você precisará executar o seguinte:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Para configurar efetivamente o Skype for Business Server, você precisará:
    
    - Familiarizar-se com sua topologia do Skype for Business Server 2015 (como nomes de computador, instâncias de serviço, nomes de site e políticas).
    
    - Atribua alguns dos usuários criados a grupos, como grupos de busca do Grupo de Resposta (por exemplo, URIs SIP).
    
3. Para executar um script na linha de comando, você pode usar:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Normalmente, depois que você executar um script desse pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho de onde o script foi executado. Também há um formato de nomen por \<scriptname\> $h$m$s.txt. Portanto, se você tiver ArchivingPolicy.ps1 às 12h15, obterá um arquivo de log chamado ArchivingPolicy121500.txt.
    
5. Embora fornecemos esses exemplos para sua configuração de servidor, você pode modificar sua configuração e restaurá-los ou reverter depois que você terminar de executar o teste de carga.
    

