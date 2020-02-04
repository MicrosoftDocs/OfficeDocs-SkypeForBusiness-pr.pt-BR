---
title: Adicionar Serviço da Web de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
ms.openlocfilehash: e62adfb080886397de51ff4c51c5fac19878eeff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685314"
---
# <a name="add-director-web-service"></a>Adicionar Serviço da Web de Diretor
 
A URL base é a identidade dos serviços Web para a URL, menos "https://". Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net, a URL base será pool01.contoso.net.
  
Você não pode substituir o nome de domínio totalmente qualificado (FQDN) do pool de serviços Web interno se você estiver implantando apenas um único diretor. Se você estiver configurando um balanceamento de carga de DNS (sistema de nomes de domínio) para o pool de diretores, poderá especificar uma URL base interna diferente (que deve ser diferente do FQDN do pool e pode ser\<, por exemplo\>, interna – sua URL base).
  
Você pode especificar uma URL base externa que seja diferente da URL base interna para diferenciar o nome do domínio. Por exemplo, seu domínio interno é contoso.net, mas o seu nome de domínio externo é contoso.com. Você definiria a URL base externa usando o nome de domínio contoso.com. Isso é importante para servidores proxy reverso para uma implantação de borda. O nome de domínio da URL base externa deve ser igual ao nome de domínio do FQDN do proxy reverso. 
  

