---
title: Provisionando a topologia para executar a carga em cenários de Estresse e Desempenho
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype for Business Server ou provisionamento de topologia 2015 para permitir que os usuários executem com êxito a ferramenta Stress and Performance.
ms.openlocfilehash: 50bd77dd7b3531a150e1e62f6192d32666fa5ba7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854255"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Provisionando a topologia para executar a carga em cenários de Estresse e Desempenho
 
Skype for Business Server ou provisionamento de topologia 2015 para permitir que os usuários executem com êxito a ferramenta Stress and Performance.
  
Dependendo das configurações e configurações existentes para sua implantação do Skype for Business Server 2015, talvez seja necessário fazer algumas alterações em seu ambiente. Veja a seguir uma lista dessas alterações:
  
1. De definir a Windows PowerShell de execução como Irrestrita. Se você não tiver certeza do que está definido no momento, poderá abrir o Shell de Gerenciamento Skype for Business Server e executar este comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Se o valor Irrestrito não for retornado, você precisará executar este seguinte:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Para configurar o Skype for Business Server, você precisará:
    
    - Familiarizar-se com sua topologia Skype for Business Server 2015 (como nomes de computador, instâncias de serviço, nomes de site e políticas).
    
    - Atribua alguns dos usuários criados a grupos, como grupos de busca do Grupo de Resposta (por exemplo, URIs SIP).
    
3. Para executar um script da linha de comando, você pode usar:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Normalmente, depois de executar um script deste pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho de onde o script foi executado. Há um formato de nomen por \<scriptname\> $h$m$s.txt. Portanto, se você tiver ArchivingPolicy.ps1 às 12:15, você obterá um arquivo de log chamado ArchivingPolicy121500.txt.
    
5. Embora nós fornecemos esses exemplos para a configuração do seu servidor, você deve modificar sua configuração e restaurá-la ou reverter após terminar de executar o teste de carga.
    

