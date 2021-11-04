---
title: Adicionar Serviços Web de Front-end 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for `https://pool01.contoso.net` , a URL base será `pool01.contoso.net` .
ms.openlocfilehash: 372748531d4f6caaaaaddb97d5733d4e107fdf6b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739367"
---
# <a name="add-front-end-web-services-2010"></a>Adicionar Serviços Web de Front-end 2010
 
A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for `https://pool01.contoso.net` , a URL base será `pool01.contoso.net` .
  
Não é possível substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web interno para um Edição Standard Server. Se você estiver configurando o balanceamento de carga dns (Sistema de Nomes de Domínio) para um pool de front-end do Edição Enterprise, poderá especificar uma URL base interna diferente (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna- \<your base URL\> ).
  
Você pode especificar uma URL de base externa que é diferente da sua URL de base interna para diferenciar a nomenclatura de domínio. Por exemplo, seu domínio interno `contoso.net` é , mas seu nome de domínio externo é `contoso.com` . Você definiria a URL de base externa utilizando o nome de domínio contoso.com. Isto é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de Front-End.
  

