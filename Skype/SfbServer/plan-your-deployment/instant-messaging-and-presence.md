---
title: Planejar mensagens instantâneas e presença no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumo: saiba como planejar mensagens instantâneas e presença no Skype for Business Server.'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816271"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planejar mensagens instantâneas e presença no Skype for Business Server
 
**Resumo:** Saiba como planejar mensagens instantâneas e presença no Skype for Business Server.
  
Planejar mensagens instantâneas e presença no Skype for Business Server. Para saber mais sobre opções de implantação específicas, como habil ou desabilitar o IM (Sistema de Mensagens Instantâneas) Offline, consulte Implantar mensagens instantâneas e presença no [Skype for Business Server.](../deploy/im-and-presence/im-and-presence.md)
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planejar mensagens instantâneas e presença no Skype for Business Server

Os Servidores front-end fornecem a funcionalidade principal do Skype for Business Server, como mensagens instantâneas (IM) e presença, e estão incluídos em todas as implantações do Skype for Business Server. Há duas edições disponíveis: o Skype for Business Server Enterprise Edition, projetado principalmente para grandes organizações, e o Skype for Business Server Standard Edition, projetado principalmente para organizações menores que querem um investimento menor em hardware e não exigem opções de alta disponibilidade completas. Ambas as edições suportam todas as cargas de trabalho do Skype for Business Server, incluindo IM, presença, conferência e Enterprise Voice.
  
A mensagem instantânea (IM) permite que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens textuais. Tanto as sessões de IM de duas partes como as multipartes são suportadas. Um participante de uma conversa por IM de duas partes pode adicionar um terceiro participante à conversa a qualquer momento. Quando isso acontece, a janela de conversa muda para dar suporte aos recursos de conferência.
  
A presença fornece informações aos usuários sobre o status de outras pessoas na rede. O status de presença de um usuário fornece informações para ajudar outras pessoas a decidir se devem tentar entrar em contato com o usuário e se devem usar mensagens instantâneas, telefone ou email. A Presença encoraja a comunicação instantânea quando possível, mas também dá informações sobre se um usuário está em reunião ou fora do escritório, indicando que a comunicação instantânea não é possível. Esse status de presença é exibido como um ícone de presença no Skype for Business e em outros aplicativos com reconhecimento de presença, incluindo o cliente de mensagens e colaboração do Microsoft Outlook, as tecnologias do Microsoft SharePoint e o Microsoft Office. O ícone de presença representa a disponibilidade atual do usuário e a disposição de se comunicar. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

Mensagens instantâneas (IM) e presença sempre são executados em pools de front-end enterprise edition e servidores Standard Edition. Para obter informações sobre hardware, sistemas operacionais e software de banco de dados com suporte, consulte [Gateways Certificados, Requisitos](../../SfbPartnerCertification/certification/infra-gateways.md)para seu ambiente do [Skype for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)e requisitos de infraestrutura para [o Skype for Business Server 2019.](../../SfBServer2019/plan/system-requirements.md)
  
### <a name="enabling-communication-with-external-users"></a>Habilitando a comunicação com usuários externos

Você pode aumentar muito os benefícios do seu investimento no Skype for Business Server, permitindo que seus usuários se comuniquem com usuários externos. Os usuários externos podem incluir:
  
- Usuários remotos: os usuários da sua organização, quando eles estão trabalhando fora de seus firewalls e estão usando laptops ou outros dispositivos do Skype for Business Server.
    
- Usuários federados: usuários de empresas com quem você trabalha e que também executem o Skype for Business Server. Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas. 
    
- Usuários do Skype: os usuários do Skype for Business podem alcançar centenas de milhões de usuários no Skype com mensagens de IM, voz e vídeo.
    
> [!NOTE]
> AOL, Yahoo e Google Talk não são mais suportados. 
  
> [!NOTE]
> Para habilitar qualquer um ou todos esses cenários, você precisa implantar um Servidor de Borda para ajudar a habilitar comunicações seguras entre sua implantação do Skype for Business Server e usuários externos. Os usuários remotos e usuários da sua organização em organizações federadas poderão ver a presença uns dos outros e se comunicar usando IM. 
  
> [!NOTE]
> O XMPP (Extensible Messaging and Presence Protocol) só tem suporte para cenários de certificação UCCP (Unified Capabilities Collaboration Platform) Joint Interoperability Test Command (JITC). 
  
### <a name="archiving-im-content"></a>Arquivamento de conteúdo de IM

O Skype for Business Server fornece recursos que você pode usar se sua organização deve seguir os regulamentos de conformidade. Você pode usar o Arquivamento para arquivar o conteúdo de mensagens de IM para todos os usuários em sua organização ou apenas para determinados usuários que você especificar. Para obter detalhes, [consulte Plan for archiving in Skype for Business Server](archiving/archiving.md). 
  
Se você também tiver o Microsoft Exchange Server 2013 implantado, poderá integrar o arquivamento de dados do Exchange com o arquivamento de dados do Skype for Business Server e usar uma única ferramenta para pesquisar os dois tipos de dados arquivados. Para obter mais informações, [consulte Configurar o Skype for Business Server para usar o arquivamento do Exchange Server.](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)
  
### <a name="topologies-and-components"></a>Topologias e componentes

Os únicos componentes necessários para mensagem instantânea (IM) e presença são:
  
- Os servidores front-end da sua organização (conhecidos como pool) ou um servidor Standard Edition. As capacidades de IM e presença estão sempre habilitadas nestes servidores. Para obter mais informações sobre topologias e gerenciamento de pool de Front-End, consulte Alta disponibilidade e gerenciamento do Pool de [Front-End.](high-availability-and-disaster-recovery/high-availability.md)
    
- Um balanceador de carga, se você tiver um pool de Front-End Enterprise Edition.
    
### <a name="supported-collocation"></a>Locação com suporte

A realocação é definida como ter um único servidor, ou grupo de servidores, com várias funções instaladas. Para obter detalhes sobre a localização, consulte [Noções básicas de topologia para o Skype for Business Server.](topology-basics/topology-basics.md) 
  

