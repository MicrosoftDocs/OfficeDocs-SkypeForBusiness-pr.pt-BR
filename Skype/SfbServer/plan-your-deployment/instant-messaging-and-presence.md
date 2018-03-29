---
title: Planejar mensagens instantâneas e presença no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: 'Resumo: Saiba como planejar para mensagens instantâneas e presença no Skype Business Server 2015.'
ms.openlocfilehash: 1934f0308cda59b52073c47d1652ad2286bd6977
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planejar mensagens instantâneas e presença no Skype for Business Server 2015
 
**Resumo:** Saiba como planejar as mensagens instantâneas e a presença no Skype for Business Server 2015.
  
Planejar mensagens instantâneas e presença no Skype for Business Server 2015. Para saber mais sobre as opções de implantação específicas, habilitando ou desabilitando Offline as mensagens Instantâneas, consulte [Deploy de mensagens instantâneas e presença em Skype para Business Server 2015](../deploy/im-and-presence/im-and-presence.md).
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server-2015"></a>Planejar mensagens instantâneas e presença no Skype for Business Server 2015

Front End servidores fornecem core Skype para a funcionalidade do servidor de negócios, como mensagens instantâneas (IM) e presença e são incluídos em cada Skype para implantação de servidor de negócios. Há duas edições: Skype para Business Server Enterprise Edition, que foi projetada principalmente para organizações maiores, e Skype para Business Server Standard Edition, que foi projetada principalmente para organizações menores que deseja um menor investimento de hardware e não exigem opções de alta disponibilidade. Ambas as edições suportam Skype todas as cargas de trabalho do Business Server incluindo mensagens Instantâneas, presença, conferência e Enterprise Voice.
  
Mensagens instantâneas (IM) permitem que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens textuais. Tanto sessões de IM de duas partes como as multipartes são suportadas. Um participante de uma conversa via IM de duas partes pode adicionar um terceiro participante à conversa a qualquer momento. Quando isso acontece, a janela de conversa muda para dar suporte aos recursos de conferência.
  
A Presença fornece informações a usuários sobre o status de outros na rede. Status de presença do usuário fornece informações que ajudam outros a decidir se devem contatar o usuário e se deseja usar mensagens instantâneas, telefone ou email. A Presença encoraja a comunicação instantânea quando possível, mas também dá informações sobre se um usuário está em reunião ou fora do escritório, indicando que a comunicação instantânea não é possível. O status de presença é exibido como um ícone de presença no Skype for Business e em outros aplicativos com alerta de presença, incluindo o cliente de mensagens e de colaboração do Microsoft Outlook, as tecnologias do Microsoft SharePoint, o Microsoft Word e o software de planilhas do Microsoft Excel. O ícone de presença representa a disponibilidade atual e a disposição de comunicação do usuário. 
  
### <a name="technical-requirements"></a>Requisitos técnicos

O sistema de mensagens instantâneas e a presença são sempre executados nos pools de Front-Ends Enterprise Edition e servidores Standard Edition. Para obter informações sobre com suporte de hardware, sistemas operacionais e o software de banco de dados, consulte [infraestrutura para Skype para negócios](https://technet.microsoft.com/en-us/office/dn947483) e [requisitos para sua Skype para ambiente de negócios](requirements-for-your-environment/requirements-for-your-environment.md).
  
### <a name="enabling-communication-with-external-users"></a>Habilitando a comunicação com usuários externos

É possível aumentar muito os benefícios do seu investimento no Skype for Business Server habilitando seus usuários a se comunicarem com usuários externos. Os usuários externos podem incluir:
  
- Usuários remotos: os usuários da organização, quando eles estão trabalhando fora dos firewalls e estão usando seus laptops ou outro Skype para dispositivos do servidor de negócios.
    
- Usuários federados: os usuários de empresas que você trabalha com quem também executar Skype para Business Server. Para habilitar seus usuários a contatar facilmente esses usuários, crie relacionamentos federados com essas empresas. 
    
- Usuários Skype: usuários do Skype for Business podem entrar em contato com centenas de milhões de usuários no Skype através de IM, voz e vídeo.
    
> [!NOTE]
> AOL, Yahoo e Google Talk não são mais suportados. 
  
> [!NOTE]
> Para habilitar qualquer um ou todos esses cenários, é necessário implantar um Servidor de Borda para ajudar a permitir comunicações seguras entre sua implantação do Skype for Business Server e os usuários externos. Os usuários remotos e usuários em organizações federadas da sua organização poderão vejam a presença uns dos outros e se comunicar usando mensagens Instantâneas. 
  
> [!NOTE]
> O protocolo XMPP é suportado apenas para cenários de certificação UCCP e JITC. 
  
### <a name="archiving-im-content"></a>Conteúdo de arquivamento de IM

O Skype for Business oferece recursos que você pode usar se sua organização devem seguir os regulamentos de conformidade. É possível usar o Arquivamento para arquivar o conteúdo de mensagens de IM de todos os usuários em sua organização ou apenas usuários específicos. Para obter detalhes, consulte Planejamento para Arquivamento no Skype for Business Server 2015, na documentação de Planejamento. 
  
Se você também tem o Microsoft Exchange Server 2013 implantado, é possível integrar o arquivamento dos dados do Exchange com o arquivamento dos dados do Skype for Business Server e usar uma única ferramenta para pesquisar ambos os tipos de dados arquivados. Para obter mais informações, consulte Configurando Skype para negócios 2015 de servidor usar o arquivamento do Microsoft Exchange Server 2013.
  
### <a name="topologies-and-components"></a>Topologias e componentes

Os únicos componentes necessários para mensagens instantâneas (IM) e presença são:
  
- Servidores de Front-End da sua organização (conhecidos como um pool) ou um servidor Standard Edition. As capacidades de IM e presença estão sempre habilitadas nesses servidores. Para obter mais informações sobre topologias de pool de Front-End e gerenciamento, consulte [gerenciamento e alta disponibilidade do Pool Front-End](high-availability-and-disaster-recovery/high-availability.md).
    
- Um balanceador de carga, se você tiver um pool de Front-Ends do Enterprise Edition.
    
### <a name="supported-collocation"></a>Colocação com suporte

A colocação é definida como ter um único servidor, ou grupo de servidores, com múltiplas funções instaladas. Para obter detalhes sobre a colocação, consulte [Noções básicas de topologia para Skype para Business Server 2015](topology-basics/topology-basics.md). 
  

