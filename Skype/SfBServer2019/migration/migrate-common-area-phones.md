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
ms.localizationpriority: medium
description: Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica. Os Telefones de Área Comum não precisam estar conectados a um computador para fornecer Skype for Business Server UC (Comunicações Unificadas). Depois de migrar uma implantação para Skype for Business Server 2019, você também deve migrar os objetos de contato associados à área comum herdada Telefone. Usando Skype for Business Server Shell de Gerenciamento, você primeiro recuperará todos os objetos de contato associados aos Telefones de Área Comum herdados e, em seguida, moverá esses objetos para o pool Skype for Business Server 2019.
ms.openlocfilehash: dabb91925b2d5271ba2760f62dd962ed7fa7a24c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58579525"
---
# <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

Os telefones de área comum são telefones IP que quase sempre se encontram em um espaço de trabalho compartilhado ou área comum, como um lobby, uma cozinha ou um andar de fábrica. Os Telefones de Área Comum não precisam estar conectados a um computador para fornecer Skype for Business Server UC (Comunicações Unificadas). Depois de migrar uma implantação para Skype for Business Server 2019, você também deve migrar os objetos de contato associados à área comum herdada Telefone. Usando Skype for Business Server Shell de Gerenciamento, você primeiro recuperará todos os objetos de contato associados aos Telefones de Área Comum herdados e, em seguida, moverá esses objetos para o pool Skype for Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

1. No servidor Skype for Business Server front-end 2019, abra Skype for Business Server Shell de Gerenciamento.
    
2. Na linha de comando, digite o seguinte:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para verificar se todos os objetos de contato foram movidos para o pool Skype for Business Server 2019, do Shell de Gerenciamento Skype for Business Server digite o seguinte:
    
   ```PowerShell
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verifique se todos os objetos de contato agora estão associados ao pool Skype for Business Server 2019.
    

