---
title: Adicionar Serviço da Web de Diretor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
ms.openlocfilehash: fa664f19efaf4fe120ca96fdf04f69a58e59d3f1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590317"
---
# <a name="add-director-web-service"></a>Adicionar Serviço Web de Diretor
 
A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
  
Você não pode substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web internos caso esteja implantando apenas um único Diretor. Se você estiver configurando um balanceamento de carga DNS (Sistema de Nomes de Domínio) para pool de Diretores, poderá especificar uma URL base interna diferente (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna- \<your base URL\> ).
  
Você pode especificar uma URL de base externa que é diferente da sua URL de base interna para diferenciar a nomenclatura de domínio. Por exemplo, seu domínio interno é contoso.net, porém seu nome de domínio externo é contoso.com. Você definiria a URL de base externa utilizando o nome de domínio contoso.com. Isto é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. 
  

