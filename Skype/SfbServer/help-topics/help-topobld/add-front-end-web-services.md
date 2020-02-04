---
title: Adicionar Serviços Web de Front End
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
ms.openlocfilehash: 10749cc746cf1f3d039a89fd351be6de77eafaee
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698196"
---
# <a name="add-front-end-web-services"></a>Adicionar Serviços Web de Front End
 
A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
  
Você não pode substituir o nome de domínio totalmente qualificado (FQDN) do pool de serviços Web interno para um servidor Standard Edition. Se você estiver configurando o balanceamento de carga do sistema de nomes de domínio (DNS) para um pool de front-end do Enterprise Edition, você pode especificar uma URL base interna diferente, que deve ser diferente\<da FQDN do\>pool (por exemplo, interna-sua URL base).
  
Você pode especificar uma URL base externa que seja diferente da URL base interna para diferenciar o nome do domínio. Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com. Você deve definir a URL base externa usando o nome de domínio contoso.com. Isso é importante para servidores proxy reverso para uma implantação de borda. O nome de domínio da URL base externa deve ser igual ao nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de front-ends.
  

