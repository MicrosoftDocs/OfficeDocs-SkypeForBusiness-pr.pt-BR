---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica. Os telefones de área comum não precisam estar conectados a um computador para fornecer a funcionalidade UC (comunicações unificadas) do Skype for Business Server. Após a migração de uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado. Usando o Shell de gerenciamento do Skype for Business Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comum herdados e, em seguida, moverá esses objetos para o pool do Skype for Business Server 2019.
ms.openlocfilehash: b9cf5a32614ac41ac3c82773af4f37907c16e6f2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752703"
---
# <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica. Os telefones de área comum não precisam estar conectados a um computador para fornecer a funcionalidade UC (comunicações unificadas) do Skype for Business Server. Após a migração de uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado. Usando o Shell de gerenciamento do Skype for Business Server, você primeiro recupera todos os objetos de contato associados aos telefones de área comum herdados e move esses objetos para o pool do Skype for Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

1. No servidor front-end do Skype for Business Server 2019, abra o Shell de gerenciamento do Skype for Business Server.
    
2. Na linha de comando, digite o seguinte:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para verificar se todos os objetos de contato foram movidos para o pool do Skype for Business Server 2019, no Shell de gerenciamento do Skype for Business Server, digite o seguinte:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verifique se todos os objetos de contato agora estão associados ao pool do Skype for Business Server 2019.
    

