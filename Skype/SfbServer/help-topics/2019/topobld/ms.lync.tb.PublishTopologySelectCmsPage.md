---
title: Publicar Página CMS de Seleção de Topologia
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publique a topologia configurada usando o Construtor de Topologias. Você é solicitado a selecionar em uma lista qual Servidor de Front End ou pool de Front-End assumirá a função de manter o armazenamento de Gerenciamento Central. Somente um servidor front-end ou pool de front-end pode manter essa função a qualquer momento.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822181"
---
# <a name="publish-topology-select-cms-page"></a>Publicar Página CMS de Seleção de Topologia
 
Publique a topologia configurada usando o Construtor de Topologias. Você é solicitado a selecionar em uma lista qual Servidor de Front End ou pool de Front-End assumirá a função de manter o armazenamento de Gerenciamento Central. Somente um servidor front-end ou pool de front-end pode manter essa função a qualquer momento. 
  
### <a name="about-the-central-management-server"></a>Sobre o Servidor de Gerenciamento Central
O Servidor de Gerenciamento Central é um único sistema mestre/com várias réplicas, onde a cópia de leitura/gravação do banco de dados é mantida pelo Servidor front-end que contém o Servidor de Gerenciamento Central. Cada computador na topologia, incluindo o Servidor #A0 que contém o Servidor de Gerenciamento Central, tem uma cópia somente leitura dos dados do armazenamento de Gerenciamento Central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação. O banco de dados local recebe atualizações de réplica por meio do Agente Replicador de Réplica do Lync Server que é executado como um serviço em todos os computadores. O nome do banco de dados real no Servidor de Gerenciamento Central e a réplica local é XDS, que é feito dos arquivos xds.mdf e xds.ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos Serviços de Domínio Active Directory. Todas as ferramentas que usam o Servidor de Gerenciamento Central para gerenciar e configurar o Lync Server usam o SCP para localizar o armazenamento de Gerenciamento Central.
  
## <a name="see-also"></a>Confira também

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
