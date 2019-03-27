---
title: Adicionar Serviço da Web de Diretor
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
ms.openlocfilehash: d87f4948fd2e619ce6aba99b556a9ed0af0fd098
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926529"
---
# <a name="add-director-web-service"></a>Adicionar Serviço da Web de Diretor
 
A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
  
Se você estiver implantando somente um único diretor, você não pode substituir o nome de domínio totalmente qualificado da pool do Web Services interno (FQDN). Se você estiver configurando uma sistema de nome de domínio (DNS) balanceamento de carga do pool de diretores, você poderá especificar outra URL base interna (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna -\<sua URL base\>).
  
Você pode especificar uma URL base externa diferente-lo do seu URL base interna para diferenciar a nomeação de domínio. Por exemplo, o seu domínio interno é contoso.net, mas o seu nome de domínio externo for contoso.com. Você deve definir a URL base externa usando o nome do domínio contoso.com. Isso é importante para os servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL base externo deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. 
  

