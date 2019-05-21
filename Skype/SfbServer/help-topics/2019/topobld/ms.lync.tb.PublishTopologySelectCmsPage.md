---
title: Publicar Página CMS de Seleção de Topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Você publica a topologia que você configurou usando o construtor de topologias. Você será solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o repositório de gerenciamento central. Somente um servidor front-end ou um pool de front-end pode reter essa função a qualquer momento.
ms.openlocfilehash: e56597a1380f908c7abdb49b9b88edd7ad249870
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277878"
---
# <a name="publish-topology-select-cms-page"></a>Publicar Página CMS de Seleção de Topologia
 
Você publica a topologia que você configurou usando o construtor de topologias. Você será solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o repositório de gerenciamento central. Somente um servidor front-end ou um pool de front-end pode reter essa função a qualquer momento. 
  
### <a name="about-the-central-management-server"></a>Sobre o servidor de gerenciamento central
O servidor de gerenciamento central é um único sistema de réplica mestra/múltipla, em que a cópia de leitura/gravação do banco de dados é mantida pelo servidor front-end que contém o servidor de gerenciamento central. Cada computador na topologia, incluindo o servidor front-end que contém o servidor de gerenciamento central, tem uma cópia somente leitura dos dados do repositório de gerenciamento central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalados no computador durante a instalação e implementação. O banco de dados local recebe atualizações de réplica por meio do agente duplicador de réplica do Lync Server que é executado como um serviço em todos os computadores. O nome do banco de dados real no servidor de gerenciamento central e na réplica local é XDS, que é composto pelos arquivos XDS. MDF e XDS. ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos serviços de domínio Active Directory. Todas as ferramentas que usam o servidor de gerenciamento central para gerenciar e configurar o Lync Server usam o SCP para localizar o repositório de gerenciamento central.
  
## <a name="see-also"></a>Confira também

[Move-CsManagementServer](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
