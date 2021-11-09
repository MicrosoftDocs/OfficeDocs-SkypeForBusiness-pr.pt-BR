---
title: Skype for Business Server Ferramenta de planejamento de visão geral de recursos
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Informações sobre a ferramenta de planejamento Skype for Business Server Visão Geral de Recursos.
ms.openlocfilehash: ac759dab4000ebdbe969b2d7436cbb46c408dc38
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848874"
---
# <a name="skype-for-business-server-feature-overview-planning-tool"></a>Skype for Business Server Ferramenta de planejamento de visão geral de recursos
 
Skype for Business Server Ferramenta de Planejamento 2015
  
Você pode usar a **página Sites Centrais** da Ferramenta de Planejamento para projetar Skype for Business Server implantação. Você pode criar duas implantações centralizadas ou distribuídas. Uma implantação centralizada tem apenas um site central, que Skype for Business todos os usuários em sua organização. Uma implantação distribuída tem mais de um site central. Se você implantar Skype for Business Server em vários sites centrais, insira o número de usuários em cada site central na Ferramenta de Planejamento.
  
Para concluir a definição do site central, primeiro você precisa fornecer as seguintes informações:
  
- **Nome do site** Insira o nome do Site Central.
    
- **Número de usuários** Insira o número de usuários, incluindo usuários em sites de filial que estão em casa no site central.
    
- **Usuários da Nuvem Internas** Insira o número de usuários que estão no site central do Skype for Business Online.
    
## <a name="ui-elements"></a>Elementos da interface do usuário

Os elementos restantes foram preenchidos com as respostas fornecidas  às perguntas apresentadas no assistente de Introdução ou, se você ignorou o assistente, foi preenchido automaticamente pela ferramenta de planejamento.
  
### <a name="online-collaboration"></a>Colaboração Online

 **A Colaboração Online** contém as seguintes opções:
  
- **IM e Presença**
    
    A Mensagem Instantânea (IM) permite que os usuários se comuniquem uns com os outros em tempo real em seus computadores usando mensagens baseadas em texto. Tanto as sessões de IM de duas partes como as multipartes são suportadas. A presença fornece informações aos usuários sobre o status de outras pessoas na rede. O status de presença de um usuário fornece informações para ajudar outras pessoas a determinar se o usuário está online e como contatar melhor o usuário. Por exemplo, um usuário que está em uma reunião é melhor contatado por email.
    
- **Conferência de áudio e vídeo**
    
    A conferência de áudio/vídeo (A/V) permite conferências de áudio e vídeo em tempo real.
    
- **Conferência discada**
    
    A conferência discagem permite que os usuários instruam um A/V de um telefone na PSTN. A conferência discagem exige que você implante os aplicativos Atendedor de Conferência e Comunicado de Conferência Service.
    
- **Webconferência**
    
    A webconferência permite que os usuários corporativos dentro e fora do firewall criem e participem de conferências em tempo real hospedadas em seus servidores internos.
    
- **Chat Persistente**
    
    O Chat Persistente permite que vários usuários participem de conversas nas quais eles postam e acessam conteúdo sobre tópicos específicos, incluindo texto, links e arquivos. Embora os usuários possam se comunicar em tempo real durante uma sessão, o conteúdo de cada sessão é persistente, o que significa que continua disponível após o fim de uma sessão.
    
### <a name="users"></a>Usuários

 **Os** usuários contêm as seguintes opções:
  
- **Organização interna**
    
- **Federação com outras organizações**
    
- **Federação com versões anteriores**
    
- **Federação com provedores de serviços públicos de IM** Permite que os usuários em sua organização estabeleçam comunicação com provedores públicos de serviços de mensagens instantâneas, como MSN, Yahoo!, e AOL. Uma licença separada é necessária para estabelecer federação com redes públicas de mensagens instantâneas.
    
- **Federação com provedor de serviços baseado em XMPP**
    
    Skype for Business Server 2015 apresenta um proxy XMPP totalmente integrado (implantado nos Servidores de Borda) e um gateway XMPP implantado em seus Servidores Front-End. Você pode implantar Adicionar e configurar o proxy XMPP e o gateway XMPP permitirá que os usuários do Skype for Business Server 2015 adicionem contatos de parceiros baseados em XMPP para mensagens instantâneas (IM) e presença.
    
- **Mobilidade**
    
    Quando você implanta o Serviço de Mobilidade do Skype for Business Server 2015, os usuários podem usar dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia compatíveis para executar atividades como envio e recebimento de mensagens instantâneas, exibição de contatos e presença de visualização.
    
- **Caixa de correio W15 Exchange de correio**
    
    Skype for Business Server 2015 permite que você tenha mensagens de caixa postal armazenadas Exchange Unificação de Mensagens (UM); essas mensagens de caixa postal serão exibidas como mensagens de email nas Caixas de Entrada dos usuários.
    
### <a name="voice"></a>Voz

 **O Voice** contém as seguintes opções:
  
- **Enterprise Voice**
    
    Enterprise voz é a solução VoIP com software da Microsft. Enterprise voz permite que os usuários usem Skype for Business para fazer uma chamada telefônica de seu computador.
    
- **Unificação de Mensagens do Exchange**
    
    Exchange Unificação de Mensagens (UM) combina caixa postal e email em uma única infraestrutura de mensagens. Skype for Business Server 2015 usa Exchange UM para fornecer atendimento de chamada, acesso de assinante, notificação de chamada e serviços de atendedor automático. Se você usar esses serviços, precisará integrar Exchange UM e Skype for Business Server em uma topologia compartilhada do Active Directory.
    
### <a name="additional-deployment-options"></a>Opções adicionais de implantação

 **Opções adicionais de** implantação contém as seguintes opções:
  
- **Alta Disponibilidade**
    
    Alta disponibilidade habilita servidores em espera para suporte a failover.
    
- **Recuperação de desastres**
    
    As medidas de recuperação de desastres permitem emparelhar pools de Front-End localizados em dois datacenters.
    
- **Monitoramento**
    
    O monitoramento captura registros de detalhes de chamada relacionados a sessões de comunicação. Ele também coleta métricas de sessões de áudio e vídeo nos pontos de extremidade do participante. O Monitoring Server fornece estatísticas de uso, tendências e estatísticas de qualidade de mídia.
    
- **Arquivamento**
    
    O arquivamento armazena conversas e conferências de mensagens instantâneas.
    
- **Exchange Integração de Arquivamento**
    
    Se você tiver usuários que estão em casa no Exchange 2013 e suas caixas de correio foram colocadas em espera In-Place, você pode selecionar a opção para integrar o armazenamento Skype for Business Server 2015 com Exchange armazenamento.
    
- **IPv4**
    
    Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao número crescente de dispositivos em todo o mundo, os endereços IPv4 disponíveis foram executados. Devido a isso, muitos novos dispositivos estão mudando para o uso de endereços IPv6.
    
- **IPv6**
    
    Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32-bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.
    
- **Serviço Web de Atualização de Dispositivos**
    
    O serviço Web de Atualização de Dispositivo fornece uma maneira automatizada de atualizar todos os dispositivos, como Skype for Business para Windows Phone, que são implantados fora da sua organização.
    
### <a name="server-applications"></a>Aplicativos de Servidor

 **Aplicativos de Servidor** contém as seguintes opções:
  
- **Grupo de Resposta**
    
    O aplicativo grupo de resposta responde automaticamente e distribui chamadas para um agente auxiliar disponível.
    
- **Comunicado**
    
    Se você planeja implantar Enterprise Voice, talvez queira configurar como as chamadas telefônicas são tratadas se o número discado for válido, mas não atribuído a uma área comum do usuário. Os administradores podem configurar o Serviço de Comunicado para que essas chamadas transfiram para um destino predeterminado (número de telefone ou URI SIP) ou reproduzir um comunicado de áudio ou ambos. O uso do Serviço de Comunicado evita a situação em que um chamador faz uma misdial e ouve um tom de ocupado ou o cliente SIP recebe uma mensagem de erro. A funcionalidade do Serviço de Comunicado é um recurso PBX típico. 
    
- **Estacionamento de chamada**
    
    O aplicativo Estacionamento de Chamadas permite que um usuário Enterprise Voice uma chamada em espera de um telefone e, em seguida, receba a chamada de outro telefone sem amarrar os recursos no telefone que recebeu a chamada. O aplicativo Estacionamento de Chamada é útil quando um usuário precisa transferir uma chamada, mas o destinatário específico é desconhecido. 
    
- **Atendente de conferência**
    
    aplicativo Atendedor de Conferência oferece recursos de audioconferência para usuários de telefone sem o serviço de um provedor de audioconferência de terceiros.
    
- **Comunicado de Conferência**
    
    aplicativo Comunicado de Conferência produz tons que sinalizam quando os usuários entram ou saem de uma conferência, bem como notificações aos usuários de telefone quando eles são mudos ou não são intermediados.
    
- **Serviço de Controle de Admissão de Chamadas**
    
    O Controle de Admissão de Chamada (CAC), também conhecido como gerenciamento de largura de banda wan, ajuda a evitar uma má qualidade de experiência para usuários em redes congestionadas determinando, com base na largura de banda disponível, se as novas sessões de comunicação em tempo real serão estabelecidas. 
    
    > [!NOTE]
    > O CAC controla apenas o tráfego em tempo real e não afeta o tráfego de dados. 
  
    Se uma nova sessão de voz ou vídeo exceder os limites de largura de banda alocados em uma WAN, a sessão será bloqueada ou (somente para chamadas telefônicas) redirecionada para a PSTN.
    

