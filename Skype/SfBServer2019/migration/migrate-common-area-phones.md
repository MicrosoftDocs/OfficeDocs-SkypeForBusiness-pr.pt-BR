---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Os telefones de área comuns são telefones IP que costumam residir em um espaço de trabalho compartilhado ou em uma área comum, como um lobby, uma cozinha ou um chão de fábrica. Os telefones de área comuns não precisam estar conectados a um computador para fornecer a funcionalidade de comunicação unificada do Skype for Business Server. Depois de migrar uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum comum. Usando o Shell de gerenciamento do Skype for Business Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comuns do herdado e, em seguida, moverá esses objetos para o pool do Skype for Business Server 2019.
ms.openlocfilehash: 915b0b86c4f0b1ac74e2575cdfcd65d0cbf23d31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280816"
---
# <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

Os telefones de área comuns são telefones IP que costumam residir em um espaço de trabalho compartilhado ou em uma área comum, como um lobby, uma cozinha ou um chão de fábrica. Os telefones de área comuns não precisam estar conectados a um computador para fornecer a funcionalidade de comunicação unificada do Skype for Business Server. Depois de migrar uma implantação para o Skype for Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum comum. Usando o Shell de gerenciamento do Skype for Business Server, primeiro você recuperará todos os objetos de contato associados aos telefones de área comuns herdados e, em seguida, moverá esses objetos para o pool do Skype for Business Server 2019.
  
### <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

1. No servidor front-end do Skype for Business Server 2019, abra o Shell de gerenciamento do Skype for Business Server.
    
2. Na linha de comando, digite o seguinte:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para verificar se todos os objetos de contato foram movidos para o pool do Skype for Business Server 2019, no Shell de gerenciamento do Skype for Business Server, digite o seguinte:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verifique se todos os objetos de contato agora estão associados ao pool do Skype for Business Server 2019.
    

