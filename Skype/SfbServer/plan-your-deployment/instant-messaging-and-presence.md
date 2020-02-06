---
title: Planejar mensagens instantâneas e presença no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumo: saiba como planejar mensagens instantâneas e presença no Skype for Business Server.'
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815899"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planejar mensagens instantâneas e presença no Skype for Business Server
 
**Resumo:** Saiba como planejar mensagens instantâneas e presença no Skype for Business Server.
  
Planejar mensagens instantâneas e presença no Skype for Business Server. Para saber mais sobre opções de implantação específicas, como habilitar ou desabilitar mensagens instantâneas (IM) offline, consulte [implantar mensagens instantâneas e presença no Skype for Business Server](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planejar mensagens instantâneas e presença no Skype for Business Server

Os servidores front-end fornecem a funcionalidade básica do Skype for Business Server, como mensagens instantâneas (IM) e presença, e estão incluídos em cada implantação do Skype for Business Server. Há duas edições disponíveis: Skype for Business Server Enterprise Edition, projetada principalmente para organizações maiores e Skype for Business Server Standard Edition, projetada principalmente para organizações menores que desejam uma pequena investimento em hardware e não exigem opções completas de alta disponibilidade. Ambas as edições dão suporte a todas as cargas de trabalho do Skype for Business Server, incluindo mensagens instantâneas, presença, conferência e Enterprise Voice.
  
Mensagens instantâneas (IM) permitem que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens textuais. Tanto sessões de IM de duas partes como as multipartes são suportadas. Um participante de uma conversa via IM de duas partes pode adicionar um terceiro participante à conversa a qualquer momento. Quando isso acontece, a janela de conversa muda para dar suporte aos recursos de conferência.
  
A Presença fornece informações a usuários sobre o status de outros na rede. O status de presença de um usuário fornece informações para ajudar outras pessoas a decidirem se devem tentar contatar o usuário e se devem ou não usar mensagens instantâneas, telefones ou emails. A Presença encoraja a comunicação instantânea quando possível, mas também dá informações sobre se um usuário está em reunião ou fora do escritório, indicando que a comunicação instantânea não é possível. O status de presença é exibido como um ícone de presença no Skype for Business e em outros aplicativos com alerta de presença, incluindo o cliente de mensagens e de colaboração do Microsoft Outlook, as tecnologias do Microsoft SharePoint, o Microsoft Word e o software de planilhas do Microsoft Excel. O ícone de presença representa a disponibilidade atual do usuário e a disposição para se comunicar. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

O sistema de mensagens instantâneas e a presença são sempre executados nos pools de Front-Ends Enterprise Edition e servidores Standard Edition. Para obter informações sobre hardware, sistemas operacionais e software de banco de dados com suporte, consulte [gateways certificados](../../SfbPartnerCertification/certification/infra-gateways.md), [requisitos para o ambiente do skype for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)e [requisitos de infraestrutura para o Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Habilitando a comunicação com usuários externos

Você pode aumentar bastante as vantagens do seu investimento no Skype for Business Server permitindo que seus usuários se comuniquem com usuários externos. Entre os usuários externos podem estar:
  
- Usuários remotos: os próprios usuários da sua organização, quando estiverem trabalhando fora dos firewalls e estiverem usando seus laptops ou outros dispositivos do Skype for Business Server.
    
- Usuários federados: usuários de empresas com quem você trabalha com quem também executam o Skype for Business Server. Para habilitar seus usuários a contatar facilmente esses usuários, crie relacionamentos federados com essas empresas. 
    
- Usuários Skype: usuários do Skype for Business podem entrar em contato com centenas de milhões de usuários no Skype através de IM, voz e vídeo.
    
> [!NOTE]
> AOL, Yahoo e Google Talk não são mais suportados. 
  
> [!NOTE]
> Para habilitar um ou todos esses cenários, você precisa implantar um servidor de borda para ajudar a permitir comunicações seguras entre a implantação do Skype for Business Server e os usuários externos. Os usuários remotos da sua organização e os usuários de organizações federadas poderão ver a presença dos outros e se comunicarem usando mensagens instantâneas. 
  
> [!NOTE]
> O protocolo XMPP é suportado apenas para cenários de certificação UCCP e JITC. 
  
### <a name="archiving-im-content"></a>Conteúdo de arquivamento de IM

O Skype for Business Server fornece recursos que você pode usar se a sua organização deve seguir as normas de conformidade. É possível usar a função Arquivamento para arquivar o conteúdo de mensagens instantâneas de todos os usuários de sua organização ou apenas de usuários específicos. Para obter detalhes, consulte [planejar o arquivamento no Skype for Business Server](archiving/archiving.md). 
  
Se você também tiver o Microsoft Exchange Server 2013 implantado, poderá integrar o arquivamento dos dados do Exchange com o arquivamento dos dados do Skype for Business Server e usar uma única ferramenta para pesquisar os dois tipos de dados arquivados. Para obter mais informações, consulte [Configurar o Skype for Business Server para usar o arquivamento do Exchange Server](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologias e componentes

Os únicos componentes necessários para mensagem instantânea (IM) e presença são:
  
- Os servidores front-end da sua organização (conhecidos como um pool) ou um servidor Standard Edition. As capacidades de IM e presença estão sempre habilitadas nesses servidores. Para obter mais informações sobre topologias e gerenciamento de pools de front-end, consulte [alta disponibilidade e gerenciamento do pool de front-end](high-availability-and-disaster-recovery/high-availability.md).
    
- Um balanceador de carga, se você tiver um pool de Front-Ends do Enterprise Edition.
    
### <a name="supported-collocation"></a>Colocação com suporte

A colocação é definida como ter um único servidor, ou grupo de servidores, com múltiplas funções instaladas. Para obter detalhes sobre a colocação, consulte [noções básicas de topologia para o Skype for Business Server](topology-basics/topology-basics.md). 
  

