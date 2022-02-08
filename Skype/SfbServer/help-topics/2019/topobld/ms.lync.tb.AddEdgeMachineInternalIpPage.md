---
title: Adicionar IP Interno de Máquina de Borda
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeMachineInternalIpPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 34717d03-5ece-4be3-9d05-25497250dc16
ROBOTS: NOINDEX, NOFOLLOW
description: Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.
ms.openlocfilehash: a35e9557e66c7a66312ab461a2c87d05940de12f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384989"
---
# <a name="add-edge-machine-internal-ip"></a>Adicionar IP Interno de Máquina de Borda

Use esta página para especificar o endereço IP interno e o nome de domínio totalmente qualificado (FQDN) interno do Servidor de Borda.

O FQDN especificado precisa ser idêntico ao nome do computador configurado no servidor. Por padrão, o nome de computador de um computador que não faz parte de um domínio é um nome curto, não um FQDN. O Construtor de Topologia utiliza FQDNs, não nomes curtos. Portanto, é necessário configurar um sufixo DNS (Domain Name System) no nome do computador a ser implantado como um Servidor de Borda que não faz parte de um domínio. Para obter detalhes sobre como adicionar um sufixo DNS ao nome de um computador, consulte [Configure DNS for Edge Support](/previous-versions/office/lync-server-2013/lync-server-2013-configure-dns-for-edge-support).