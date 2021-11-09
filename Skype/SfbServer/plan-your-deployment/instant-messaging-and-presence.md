---
title: Planejar mensagens instantâneas e presença no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumo: saiba como planejar mensagens instantâneas e presença no Skype for Business Server.'
ms.openlocfilehash: b81da143bf7b8d917d88939d8b28261910bb8f5a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835079"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planejar mensagens instantâneas e presença no Skype for Business Server
 
**Resumo:** Saiba como planejar mensagens instantâneas e presença no Skype for Business Server.
  
Planeje mensagens instantâneas e presença no Skype for Business Server. Para saber mais sobre opções específicas de implantação, como habilbilização ou desabilitação de Mensagens Instantâneas Offline (IM), consulte [Deploy instant messaging](../deploy/im-and-presence/im-and-presence.md)and presence in Skype for Business Server .
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>Planejar mensagens instantâneas e presença no Skype for Business Server

Os Servidores Front-End fornecem funcionalidades Skype for Business Server principais, como mensagens instantâneas (IM) e presença, e são incluídos em todas as implantações Skype for Business Server de mensagens instantâneas. Há duas edições disponíveis: Skype for Business Server Edição Enterprise, que é projetado principalmente para organizações maiores, e Skype for Business Server Edição Standard, que é projetado principalmente para organizações menores que querem um menor investimento em hardware e não exige opções completas de alta disponibilidade. Ambas as edições suportam todas as Skype for Business Server de trabalho, incluindo IM, presença, conferência e Enterprise Voice.
  
A mensagem instantânea (IM) permite que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens textuais. Tanto as sessões de IM de duas partes como as multipartes são suportadas. Um participante de uma conversa por IM de duas partes pode adicionar um terceiro participante à conversa a qualquer momento. Quando isso acontece, a janela de conversa muda para dar suporte aos recursos de conferência.
  
A presença fornece informações aos usuários sobre o status de outras pessoas na rede. O status de presença de um usuário fornece informações para ajudar outras pessoas a decidir se devem tentar entrar em contato com o usuário e se devem usar mensagens instantâneas, telefone ou email. A Presença encoraja a comunicação instantânea quando possível, mas também dá informações sobre se um usuário está em reunião ou fora do escritório, indicando que a comunicação instantânea não é possível. Esse status de presença é exibido como um ícone de presença no Skype for Business e em outros aplicativos com reconhecimento de presença, incluindo o cliente de mensagens e colaboração do Microsoft Outlook, tecnologias do Microsoft SharePoint e Microsoft Office. O ícone de presença representa a disponibilidade atual e a disposição do usuário para se comunicar. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

Mensagens instantâneas (IM) e presença sempre são executados em Edição Enterprise de front-end e Edição Standard servidores. Para obter informações sobre hardware, sistemas operacionais e software de banco de dados com suporte, consulte [Gateways Certificados, Requisitos](../../SfbPartnerCertification/certification/infra-gateways.md)para seu ambiente [Skype for Business 2015](requirements-for-your-environment/requirements-for-your-environment.md)e Requisitos de infraestrutura [para Skype for Business Server 2019](../../SfBServer2019/plan/system-requirements.md).
  
### <a name="enabling-communication-with-external-users"></a>Habilitando a comunicação com usuários externos

Você pode aumentar muito os benefícios do seu investimento em Skype for Business Server permitindo que seus usuários se comuniquem com usuários externos. Os usuários externos podem incluir:
  
- Usuários remotos: os próprios usuários da sua organização, quando eles estão trabalhando fora de seus firewalls e estão usando seus laptops ou outros Skype for Business Server dispositivos.
    
- Usuários federados: usuários de empresas com quem você trabalha que também Skype for Business Server. Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas. 
    
- Skype usuários: Skype for Business os usuários podem alcançar as centenas de milhões de usuários no Skype com mensagens de IM, voz e vídeo.
    
> [!NOTE]
> O AOL, o Yahoo e o Google Talk não são mais suportados. 
  
> [!NOTE]
> Para habilitar qualquer ou todos esses cenários, você precisa implantar um Servidor de Borda para ajudar a habilitar comunicações seguras entre sua implantação Skype for Business Server e usuários externos. Os usuários remotos e usuários de sua organização em organizações federadas poderão ver a presença uns dos outros e se comunicar usando OM. 
  
> [!NOTE]
> O Protocolo XMPP (Extensible Messaging and Presence Protocol) só tem suporte para cenários de certificação de JITC (Unified Capabilities Collaboration Platform) (UCCP). 
  
### <a name="archiving-im-content"></a>Conteúdo de IM de arquivamento

Skype for Business Server fornece recursos que você pode usar se sua organização precisa seguir os regulamentos de conformidade. Você pode usar o Arquivamento para arquivar o conteúdo de mensagens de mensagens IM para todos os usuários em sua organização ou apenas para determinados usuários que você especificar. Para obter detalhes, [consulte Plan for archiving in Skype for Business Server](archiving/archiving.md). 
  
Se você também tiver Microsoft Exchange Server 2013 implantado, poderá integrar o arquivamento de dados Exchange com o arquivamento de dados Skype for Business Server e usar uma única ferramenta para pesquisar os dois tipos de dados arquivados. Para obter mais informações, [consulte Configure Skype for Business Server to use Exchange Server archiving](../deploy/integrate-with-exchange-server/use-exchange-archiving.md).
  
### <a name="topologies-and-components"></a>Topologias e componentes

Os únicos componentes necessários para mensagem instantânea (IM) e presença são:
  
- Os servidores Front-End da sua organização (conhecidos como pool) ou um Edição Standard servidor. As capacidades de IM e presença estão sempre habilitadas nestes servidores. Para obter mais informações sobre topologias e gerenciamento de pool de [front-end,](high-availability-and-disaster-recovery/high-availability.md)consulte Front End Pool high availability and management .
    
- Um balanceador de carga, se você tiver um pool Edição Enterprise front-end.
    
### <a name="supported-collocation"></a>Localização com suporte

A localização é definida como ter um único servidor ou grupo de servidores, com várias funções instaladas. Para obter detalhes sobre a localização, consulte [Topology Basics for Skype for Business Server](topology-basics/topology-basics.md). 
  

