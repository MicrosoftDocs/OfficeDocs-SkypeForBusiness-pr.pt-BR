---
title: Adicionar serviços da Web de Front-End
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
ms.openlocfilehash: 6626bb14221aaa909219451d26b76b0cd15bc576
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="add-front-end-web-services"></a>Adicionar serviços da Web de Front-End
 
A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool é https://pool01.contoso.net, a URL base é pool01. contoso.NET.
  
Você não pode substituir o nome interno domínio totalmente qualificado de pool do Web Services (FQDN) para um servidor Standard Edition. Se você estiver configurando um sistema de nome de domínio (DNS) balanceamento de carga para um pool de Front End do Enterprise Edition, você pode especificar uma diferente URL de base interna, que deve ser diferente do FQDN do pool (por exemplo, interna -\<sua URL base\>).
  
Você pode especificar uma URL base externa diferente-lo do seu URL base interna para diferenciar a nomeação de domínio. Por exemplo, o seu domínio interno é contoso.net, mas o seu nome de domínio externo for contoso.com. Você deve definir a URL base externa usando o nome do domínio contoso.com. Isso é importante para os servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL base externo deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença requer acesso HTTP para o pool de Front-End.
  

