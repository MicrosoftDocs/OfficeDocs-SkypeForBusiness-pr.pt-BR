---
title: Adicionar Serviços Web de Front End 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net , a URL base será pool01.contoso.net.
ms.openlocfilehash: d87bb3716a19f59f2614194d79dfedaf544964e1
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217952"
---
# <a name="add-front-end-web-services-2010"></a>Adicionar Serviços Web de Front End 2010
 
A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa para os serviços Web do pool for https://pool01.contoso.net , a URL base será pool01.contoso.net.
  
Não é possível substituir o nome de domínio totalmente qualificado (FQDN) do pool de serviços Web interno para um servidor Standard Edition. Se você estiver configurando o balanceamento de carga do DNS (sistema de nomes de domínio) para um pool de front-ends Enterprise Edition, poderá especificar uma URL de base interna diferente (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna \<your base URL\> ).
  
Você pode especificar uma URL de base externa que é diferente da sua URL de base interna para diferenciar a nomenclatura de domínio. Por exemplo, seu domínio interno é contoso.net, porém seu nome de domínio externo é contoso.com. Você definiria a URL de base externa utilizando o nome de domínio contoso.com. Isto é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de front-ends.
  

