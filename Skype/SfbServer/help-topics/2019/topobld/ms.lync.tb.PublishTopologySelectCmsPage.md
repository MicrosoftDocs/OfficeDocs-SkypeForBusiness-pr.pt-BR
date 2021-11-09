---
title: Publicar Página CMS de Seleção de Topologia
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Você publica a topologia configurada usando o Construtor de Topologias. Você é solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o armazenamento de Gerenciamento Central. Somente um servidor front-end ou pool de front-end pode manter essa função a qualquer momento.
ms.openlocfilehash: 4f4658b13a634d5f1d231d4e8fe7683b3fc38b8f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860558"
---
# <a name="publish-topology-select-cms-page"></a>Publicar Página CMS de Seleção de Topologia
 
Você publica a topologia configurada usando o Construtor de Topologias. Você é solicitado a selecionar em uma lista qual servidor front-end ou pool de front-end assumirá a função de manter o armazenamento de Gerenciamento Central. Somente um servidor front-end ou pool de front-end pode manter essa função a qualquer momento. 
  
### <a name="about-the-central-management-server"></a>Sobre o Servidor de Gerenciamento Central
O Servidor de Gerenciamento Central é um único sistema mestre/réplica múltipla, onde a cópia de leitura/gravação do banco de dados é mantida pelo Servidor de Front-End que contém o Servidor de Gerenciamento Central. Cada computador na topologia, incluindo o Servidor front-end que contém o Servidor de Gerenciamento Central, tem uma cópia somente leitura dos dados do armazenamento do Gerenciamento Central no banco de dados do SQL Server (chamado RTCLOCAL por padrão) instalado no computador durante a instalação e implantação. O banco de dados local recebe atualizações de réplica por meio do Agente replicador de réplica do Lync Server que é executado como um serviço em todos os computadores. O nome do banco de dados real no Servidor de Gerenciamento Central e a réplica local é XDS, que é feito dos arquivos xds.mdf e xds.ldf. O local do banco de dados mestre é referenciado por um ponto de controle de serviço (SCP) nos Serviços de Domínio do Active Directory. Todas as ferramentas que usam o Servidor de Gerenciamento Central para gerenciar e configurar o Lync Server usam o SCP para localizar o armazenamento de Gerenciamento Central.
  
## <a name="see-also"></a>Confira também

[Move-CsManagementServer](/powershell/module/skype/move-csmanagementserver?view=skype-ps)