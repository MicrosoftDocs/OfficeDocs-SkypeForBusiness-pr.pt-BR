---
title: Adicionar Serviços Web de Front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
ms.openlocfilehash: c2fd91d9f16d585e4ade2ac6a071d699e6917af7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615797"
---
# <a name="add-front-end-web-services"></a>Adicionar Serviços Web de Front-end
 
A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
  
Você não pode substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web internos por um servidor Standard Edition. Se você estiver configurando o balanceamento de carga dns (sistema de nomes de domínio) para um pool de front-end do Edição Enterprise, você pode especificar uma URL base interna diferente, que deve ser diferente do FQDN do pool (por exemplo, interno- \<your base URL\> ).
  
É possível especificar uma URL de base externa diferente de sua URL de base interna para diferenciar a designação de domínios. Por exemplo, seu domínio interno é contoso.net, mas seu nome de domínio externo é contoso.com; você definiria a URL de base externa usando o nome de domínio contoso.com. Isso é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. Mensagens instantâneas e presença exigem acesso HTTP ao pool de Front-Ends.
  

