---
title: Provisionando a topologia para executar carga em cenários de carga e desempenho
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 12/17/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: O Skype for Business Server 2015 altera ou provisionamento de topologia para permitir que os usuários executem com êxito a ferramenta de stress e desempenho.
ms.openlocfilehash: e58bfce5e618c6e62f272c0acb0b415cbb471d40
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992488"
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Provisionando a topologia para executar carga em cenários de carga e desempenho
 
O Skype for Business Server 2015 altera ou provisionamento de topologia para permitir que os usuários executem com êxito a ferramenta de stress e desempenho.
  
Dependendo das configurações existentes e da configuração da sua implantação do Skype for Business Server 2015, talvez seja necessário fazer algumas alterações no ambiente. Veja a seguir uma lista dessas alterações:
  
1. Defina a política de execução do Windows PowerShell como Irrestrito. Se não tiver certeza de que ele está definido no momento, você pode abrir o Shell de gerenciamento do Skype for Business Server e executar este comando:
    
   ```PowerShell
   Get-ExecutionPolicy
   ```

   Se o valor irrestrito não for retornado, você precisará executar o seguinte:
    
   ```PowerShell
   Set-ExecutionPolicy -Unrestricted
   ```

2. Para configurar efetivamente o Skype for Business Server, você precisará:
    
    - Familiarize-se com sua topologia do Skype for Business Server 2015 (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).
    
    - Atribua alguns dos usuários criados a grupos, como os números coletivos de grupos de resposta (por exemplo, URIs SIP).
    
3. Para executar um script a partir da linha de comando, você pode usar:
    
   ```PowerShell
   PowerShell.exe -file <path to the file>
   ```

4. Geralmente, depois que você executar um script deste pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho a partir do local em que o script foi executado. Também há um formato de nomenclatura, \<scriptname\>$h $ m $ s. txt. Portanto, se você executou o ArchivingPolicy. ps1 em 12:15 PM, obterá um arquivo de log chamado ArchivingPolicy121500. txt.
    
5. Embora tenhamos fornecido esses exemplos para a configuração do seu servidor, você pode modificar a configuração e restaurá-la ou recarregá-la após concluir a execução do teste de carga.
    

