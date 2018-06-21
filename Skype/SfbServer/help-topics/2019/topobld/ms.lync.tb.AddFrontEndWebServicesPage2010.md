---
title: Adicionar serviços Web de Front End 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
ms.openlocfilehash: 5d5c935d1357c2baf66ed17ab762db8fd442ac67
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976890"
---
# <a name="add-front-end-web-services-2010"></a>Adicionar serviços Web de Front End 2010
 
A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
  
Você não pode substituir o nome interno domínio totalmente qualificado de pool do Web Services (FQDN) para um servidor Standard Edition. Se você estiver configurando um sistema de nome de domínio (DNS) balanceamento de carga para um pool de Front End do Enterprise Edition, você pode especificar outra URL base interna (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna -\<sua URL base\>).
  
Você pode especificar uma URL base externa diferente-lo do seu URL base interna para diferenciar a nomeação de domínio. Por exemplo, o seu domínio interno é contoso.net, mas o seu nome de domínio externo for contoso.com. Você deve definir a URL base externa usando o nome do domínio contoso.com. Isso é importante para os servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL base externo deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença requer acesso HTTP para o pool de Front-End.
  

