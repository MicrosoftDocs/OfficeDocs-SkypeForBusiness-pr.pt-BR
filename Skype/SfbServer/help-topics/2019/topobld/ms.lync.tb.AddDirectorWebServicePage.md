---
title: Adicionar Serviço da Web de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
ms.openlocfilehash: df8f6d88e57be2abd3c4a5081188f6e22849da0f
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796550"
---
# <a name="add-director-web-service"></a>Adicionar Serviço da Web de Diretor
 
A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
  
Você não pode substituir o nome de domínio totalmente qualificado (FQDN) do pool de serviços Web interno se você estiver implantando apenas um único diretor. Se você estiver configurando um balanceamento de carga de DNS (sistema de nomes de domínio) para o pool de diretores, poderá especificar uma URL base interna diferente (que deve ser diferente do FQDN do pool e pode ser\<, por exemplo\>, interna – sua URL base).
  
Você pode especificar uma URL base externa que seja diferente da URL base interna para diferenciar o nome do domínio. Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com. Você definiria a URL base externa usando o nome de domínio contoso.com. Isso é importante para servidores proxy reverso para uma implantação de borda. O nome de domínio da URL base externa deve ser igual ao nome de domínio do FQDN do proxy reverso. 
  

