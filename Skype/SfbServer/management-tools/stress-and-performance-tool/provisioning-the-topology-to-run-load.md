---
title: Provisionamento a topologia para executar a carga em cenários de Stress e desempenho
ms.author: heidip
author: microsoftheidi
ms.date: 12/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 143cf9bd-b935-494d-817c-a8b0ccc61eb8
description: Skype para alterações de topologia Business Server 2015 ou provisionamento para permitir que usuários com êxito, execute a ferramenta de Stress e desempenho.
ms.openlocfilehash: 825dd56a7f2cb343eddd8cbed7e811cdc5154b9c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-the-topology-to-run-load-in-stress-and-performance-scenarios"></a>Provisionamento a topologia para executar a carga em cenários de Stress e desempenho
 
Skype para alterações de topologia Business Server 2015 ou provisionamento para permitir que usuários com êxito, execute a ferramenta de Stress e desempenho.
  
Dependendo as configurações existentes e a configuração de sua implantação do Skype para Business Server 2015, você pode precisar fazer algumas alterações em seu ambiente. A seguir está uma lista dessas alterações:
  
1. Defina a diretiva de execução do Windows PowerShell como irrestrito. Se você não tiver certeza de qual é definido como atualmente, pode abrir o Skype para Business Server Management Shell e execute este comando:
    
  ```
  Get-ExecutionPolicy
  ```

  Se o valor Unrestricted não for retornado, você precisará executar nesse Avançar:
    
  ```
  Set-ExecutionPolicy -Unrestricted
  ```

2. Para configurar efetivamente Skype para Business Server, você precisará:
    
    - Estar familiarizado com seu Skype para Business Server 2015 topologia (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).
    
    - Atribua alguns dos usuários que são criados para grupos, como o grupo de resposta (por exemplo, URIs de SIP) de grupos de busca.
    
3. Para executar um script de linha de comando, você pode usar:
    
  ```
  PowerShell.exe -file <path to the file>
  ```

4. Normalmente, depois de executar um script deste pacote, os rastreamentos resultantes serão armazenados em um arquivo no mesmo caminho em que o script foi executado. Há também um formato de nomeação \<scriptname\>$h$m$s.txt. Portanto, se você executou o ArchivingPolicy.ps1 às 12:15:00, você obterá um arquivo de log chamado ArchivingPolicy121500.txt.
    
5. Enquanto fornecemos estes exemplos para a configuração do servidor, cabe a você modificar sua configuração e restaurar ou revertê-la depois de terminar a execução do teste de carga.
    

