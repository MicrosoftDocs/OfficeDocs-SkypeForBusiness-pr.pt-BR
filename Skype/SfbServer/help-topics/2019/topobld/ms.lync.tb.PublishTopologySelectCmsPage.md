---
title: Publicar Página CMS de Seleção de Topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Publicar a topologia que você configurou usando o construtor de topologia. Será solicitado que você selecione em uma lista na qual pool de Front-End ou de servidor Front-End assumirá a função de reter o repositório de gerenciamento Central. Somente um pool de Front-End ou de servidor Front-End pode conter esta função em um determinado momento.
ms.openlocfilehash: e649629650bfa1fe168698984e3e8b0aaa5d2df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888755"
---
# <a name="publish-topology-select-cms-page"></a>Publicar Página CMS de Seleção de Topologia
 
Publicar a topologia que você configurou usando o construtor de topologia. Será solicitado que você selecione em uma lista na qual pool de Front-End ou de servidor Front-End assumirá a função de reter o repositório de gerenciamento Central. Somente um pool de Front-End ou de servidor Front-End pode conter esta função em um determinado momento. 
  
### <a name="about-the-central-management-server"></a>Sobre o servidor de gerenciamento Central
O servidor de gerenciamento Central é um sistema de única réplica mestre/múltiplo, onde a cópia de leitura/gravação do banco de dados é mantida por servidor Front-End que contém o servidor de gerenciamento Central. Cada computador na topologia, incluindo o servidor Front-End que contém o servidor de gerenciamento Central, tem uma cópia somente leitura dos dados do repositório de gerenciamento Central em dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação. O banco de dados local recebe atualizações de réplica por meio de agente replicador de réplica de servidor do Lync que é executado como um serviço em todos os computadores. O nome do banco de dados real no servidor de gerenciamento Central e da réplica local é XDS, que é composta dos arquivos XDS. mdf e xds.ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory. Todas as ferramentas que usam o servidor de gerenciamento Central para gerenciar e configurar o Lync Server usam o SCP para localizar o repositório de gerenciamento Central.
  
## <a name="see-also"></a>Confira também

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
