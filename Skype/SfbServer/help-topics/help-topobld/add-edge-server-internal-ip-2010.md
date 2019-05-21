---
title: Adicionar IP Interno de Servidor de Borda 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerInternalIpPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 661dd74e-c42a-4905-a9c6-6efe02acc5f8
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) do servidor de borda.
ms.openlocfilehash: dfe5d082b14d5480061f7262c481e455b7eb8a1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302441"
---
# <a name="add-edge-server-internal-ip-2010"></a>Adicionar IP Interno de Servidor de Borda 2010

Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) do servidor de borda.

Esse FQDN que você especificar deve ser idêntico ao nome do computador que está configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologias usa FQDNs, não nomes curtos. Portanto, você deve configurar um sufixo DNS (sistema de nomes de domínio) no nome do computador a ser implantado como um servidor de borda que não está associado a um domínio. Para obter detalhes sobre como adicionar um sufixo DNS a um nome de computador, consulte [Configurar o DNS para suporte de borda](https://technet.microsoft.com/library/955493e6-aa29-424d-bb81-1ef87b3b15e3.aspx).


