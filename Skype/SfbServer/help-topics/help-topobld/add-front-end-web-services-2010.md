---
title: Adicionar Serviços Web de Front End 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
ms.openlocfilehash: ec167b333948384a66f6ff66c64c4f53fcbe1076
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275322"
---
# <a name="add-front-end-web-services-2010"></a>Adicionar Serviços Web de Front End 2010
 
A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
  
Você não pode substituir o nome de domínio totalmente qualificado (FQDN) do pool de serviços Web interno para um servidor Standard Edition. Se você estiver configurando o balanceamento de carga do sistema de nomes de domínio (DNS) para um pool Front-end do Enterprise Edition, poderá especificar uma URL base interna diferente (que deve ser diferente do FQDN do pool e\<poderia ser,\>por exemplo, interna – sua URL base).
  
Você pode especificar uma URL base externa que seja diferente da URL base interna para diferenciar o nome do domínio. Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com. Você definiria a URL base externa usando o nome de domínio contoso.com. Isso é importante para servidores proxy reverso para uma implantação de borda. O nome de domínio da URL base externa deve ser igual ao nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de front-ends.
  

