---
title: Adicionar Serviços Web de Front-end 2010
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
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
ms.openlocfilehash: 96a258cd2d3c46d700dff32ea4adb6213b4de9b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824021"
---
# <a name="add-front-end-web-services-2010"></a>Adicionar Serviços Web de Front-end 2010
 
A URL base é a identidade dos Serviços Web para a URL, menos o https://. Por exemplo, se a URL completa dos Serviços Web do pool for , a https://pool01.contoso.net URL base será pool01.contoso.net.
  
Não é possível substituir o FQDN (nome de domínio totalmente qualificado) do pool de Serviços Web internos para um Servidor Standard Edition. Se você estiver configurando o balanceamento de carga DNS (Sistema de Nomes de Domínio) para um pool de Front-End Enterprise Edition, poderá especificar uma URL de base interna diferente (que deve ser diferente do FQDN do pool e pode ser, por exemplo, interna- \<your base URL\> ).
  
Você pode especificar uma URL de base externa que é diferente da sua URL de base interna para diferenciar a nomenclatura de domínio. Por exemplo, seu domínio interno é contoso.net, porém seu nome de domínio externo é contoso.com. Você definiria a URL de base externa utilizando o nome de domínio contoso.com. Isto é importante para servidores de proxy reverso para uma implantação de borda. O nome de domínio de URL de base externa deve ser o mesmo que o nome de domínio do FQDN do proxy reverso. O sistema de mensagens instantâneas e presença exigem acesso HTTP ao pool de Front-End.
  

