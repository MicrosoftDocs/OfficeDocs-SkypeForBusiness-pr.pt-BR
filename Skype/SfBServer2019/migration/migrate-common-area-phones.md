---
title: Migrar telefones de área comum
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Telefones de área comum são IP telefones que mais frequentemente residirem em um espaço de trabalho compartilhado ou área comum, como um andar lobby, cozinha ou fábrica. Telefones de área comum não precisará ser conectado a um computador para fornecer que funcionalidade de comunicação unificada de Unificação de Skype para Business Server. Após migrar uma implantação para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado. Usando o Skype para Business Server Management Shell você irá primeiro recuperar todos os objetos de contato associados a telefones de área comum herdado e mova esses objetos para o Skype para Business Server 2019 pool.
ms.openlocfilehash: d17e15224a9124eaf3e9fd6696e6ecd9265044eb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887264"
---
# <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

Telefones de área comum são IP telefones que mais frequentemente residirem em um espaço de trabalho compartilhado ou área comum, como um andar lobby, cozinha ou fábrica. Telefones de área comum não precisará ser conectado a um computador para fornecer que funcionalidade de comunicação unificada de Unificação de Skype para Business Server. Após migrar uma implantação para o Skype para Business Server 2019, você também deve migrar os objetos de contato associados ao telefone de área comum herdado. Usando Skype do Shell de gerenciamento do servidor de negócios, você será primeiro recuperar todos os objetos de contato associados a telefones de área comum herdado e mova esses objetos para o Skype para Business Server 2019 pool.
  
### <a name="migrate-common-area-phones"></a>Migrar telefones de área comum

1. Em Skype para o servidor de negócios 2019 Front-End Server, abra Skype do Shell de gerenciamento do servidor de negócios.
    
2. Na linha de comando, digite o seguinte:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net
   ```

3. Para verificar se todos os objetos de contato foram movidos para o Skype para Business Server 2019 pool, no Skype do Shell de gerenciamento do servidor de negócios, digite o seguinte:
    
   ```
   Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

    Verifique se todos os objetos de contato estão agora associados com o Skype para Business Server 2019 pool.
    

