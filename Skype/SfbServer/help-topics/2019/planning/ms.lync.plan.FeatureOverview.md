---
title: Feature Overview (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Ferramenta de planejamento do Skype for Business Server
ms.openlocfilehash: 35fd0d44bbfde381b18eaf7c4e009b623dea8888
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797192"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Ferramenta de planejamento do Skype for Business Server
  
Você pode usar a página **sites centrais** da ferramenta de planejamento para criar a implantação do Skype for Business Server. Você pode criar tanto uma implantação centralizada quanto um distribuída. Uma implantação centralizada tem apenas um site central, que se refere a todos os usuários do Skype for Business em sua organização. Uma implantação distribuída possui mais de um site central. Se você implantar o Skype for Business Server em vários sites centrais, será inserido o número de usuários em cada site central na ferramenta de planejamento.
  
Para completar a definição do site central, primeiro você precisa fornecer as seguintes informações:
  
- **Nome do site ** Insira o nome do Site central.
    
- **Número de Usuários** Insira o número de usuários, incluindo usuários em sites de filial que estão hospedados no site central.
    
- **Usuários hospedados na nuvem** Digite o número de usuários que são hospedados no site central pelo Skype for Business online.
    
## <a name="ui-elements"></a>Elementos da interface do usuário

Os elementos restantes foram populados com respostas que você forneceu às perguntas apresentadas no assistente da **Introdução** ou, se você tiver pulado o assistente, será populado automaticamente pela ferramenta de planejamento.
  
### <a name="online-collaboration"></a>Colaboração online

 A  **Colaboração online** contém as seguintes opções:
  
- **Mensagens instantâneas e presença**
    
    A mensagem instantânea permite que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens de texto. Tanto as sessões de mensagem instantânea entre duas partes como as entre várias partes são suportadas. A presença fornece informações a usuários sobre o status de outros na rede. O status de presença de um usuário fornece informações para ajudar outras pessoas a determinarem se o usuário está online e como entrar em contato com ele melhor. Por exemplo, a melhor forma de contatar um usuário que está em uma reunião é via email.
    
- **Conferência de áudio e vídeo**
    
    A conferência de áudio/vídeo (A/V) permite conferências de áudio e vídeo em tempo real.
    
- **Conferência discada**
    
    A conferência discada permite que os usuários participem de uma A/V a partir de um telefone na PSTN. A conferência discada requer a implantação dos aplicativos Atendedor de Conferência e Serviço de Comunicado de Conferência.
    
- **Webconferência**
    
    A Webconferência permite que os usuários empresariais internos e externos ao firewall criem e participem de conferências em tempo real hospedados nos servidores internos.
    
- **Chat Persistente**
    
    O Chat persistente permite que vários usuários participem de conversas nas quais eles postam e acessam conteúdo sobre tópicos específicos, incluindo texto, links e arquivos. Embora os usuários possam se comunicar em tempo real durante uma sessão, o conteúdo de cada sessão é persistente, o que significa que continua disponível após o fim de uma sessão.

    > [!NOTE] 
    > O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [atualização do Skype for Business para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar usuários que exigem essa funcionalidade para o Microsoft Teams ou continuar usando o Skype for Business Server 2015.
    
### <a name="users"></a>Usuários

 **Usuários** com as seguintes opções:
  
- **Organização interna**
    
- **Federação com outras organizações**
    
- **Federação com versões anteriores**
    
- **Federação com provedores de serviços de mensagem instantânea públicos** Permite que os usuários na organização estabeleçam comunicação com provedores públicos de serviço de mensagem instantânea, como MSN, Yahoo! e AOL. Uma licença separada é necessária para estabelecer federação com redes públicas de mensagem instantânea.
    
- **Federação com provedor de serviço com base XMPP**
    
    O Skype for Business Server 2015 introduziu um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um Gateway XMPP implantado em seus servidores front-end. Você pode implantar a adição e a configuração do XMPP proxy e do XMPP gateway permitirá que seus usuários do Skype for Business Server adicionem contatos de parceiros baseados no XMPP para mensagens instantâneas (IM) e presença.
    
- **Mobilidade**
    
    Ao implantar o serviço Skype for Business Server Mobility, os usuários podem usar dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia para executar tais atividades como enviar e receber mensagens instantâneas, ver contatos e ver a presença.
    
- **Caixa de correio W15 Exchange**
    
    O Skype for Business Server permite que você tenha mensagens de correio de voz armazenadas na Unificação de mensagens do Exchange (UM); essas mensagens de correio de voz serão exibidas como mensagens de email nas caixas de entrada dos usuários.

    > [!NOTE]
    > A Unificação de mensagens do Exchange como anteriormente conhecida não está mais disponível no Exchange 2019, mas você ainda pode usar o sistema telefônico para gravar mensagens de correio de voz e deixar a gravação na caixa de correio do Exchange de um usuário. Para obter mais informações, consulte [planejar o serviço de correio de voz na nuvem](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
    
### <a name="voice"></a>Voz

 **Voz** contém as seguintes opções:
  
- **Enterprise Voice**
    
    O Enterprise Voice é uma solução VoIP com o software da Microsft. O Enterprise Voice permite que os usuários usem o Skype for Business para fazer uma chamada telefônica do computador.
    
- **Unificação de Mensagens do Exchange**
    
    A Unificação de mensagens do Exchange combina correio de voz e e-mail em uma única infra-estrutura de mensagens. O Skype for Business Server 2015 usa o Exchange UM para fornecer atendimento de chamadas, acesso ao Assinante, notificação de chamada e serviços de atendedor automático. Se você usar esses serviços, será necessário integrar o Exchange UM e o Skype for Business Server em uma topologia compartilhada do Active Directory.

    > [!NOTE]
    > A Unificação de mensagens do Exchange como anteriormente conhecida não está mais disponível no Exchange 2019, mas você ainda pode usar o sistema telefônico para gravar mensagens de correio de voz e deixar a gravação na caixa de correio do Exchange de um usuário. Para obter mais informações, consulte [planejar o serviço de correio de voz na nuvem](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) .
    
### <a name="additional-deployment-options"></a>Opções de implantação adicionais

 **Opções de implantação adicionais** com as seguintes opções:
  
- **Alta disponibilidade**
    
    A alta disponibilidade permite servidores em espera para suporte contra failover.
    
- **Recuperação de desastres**
    
    As medidas de recuperação de desastres permitem emparelhar pools de front-end localizados em dois datacenters.
    
- **Monitoramento**
    
    O monitoramento captura registros de detalhe de chamada relacionados a sessões de comunicação. Também coleta métricas de sessões de áudio e vídeo nas extremidades dos participantes. O Monitoring Server fornece estatísticas de uso, tendências e estatísticas de qualidade de mídia.
    
- **Archiving**
    
    O arquivamento armazena conversas de mensagem instantânea e conferências.
    
- **Integração com arquivamento do Exchange**
    
    Se você tiver usuários hospedados no Exchange e suas caixas de correio tiverem sido colocadas no bloqueio in-loco, você poderá selecionar a opção para integrar o armazenamento do Skype for Business Server ao armazenamento do Exchange.
    
- **IPv4**
    
    Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao número cada vez maior de dispositivos no mundo todo, os endereços IPv4 disponíveis podem se esgotar. Por isso, muitos dispositivos novos estão passando a usar endereços IPv6.
    
- **IPv6**
    
    Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32 bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.
    
- **Serviço Web de Atualização de Dispositivos**
    
    O serviço Web de atualização de dispositivo oferece uma maneira automatizada de atualizar todos os dispositivos, como o Skype for Business para Windows Phone, que são implantados fora de sua organização.
    
### <a name="server-applications"></a>Aplicativos de servidor

 **Aplicativos de servidor** contém as seguintes opções:
  
- **Grupo de Resposta**
    
    O aplicativo de grupo de resposta automaticamente atende e distribui chamadas para um agente disponível do helpdesk.
    
- **Comunicado**
    
    Se você planeja implantar o Enterprise Voice, talvez queira configurar o modo como as chamadas telefônicas são manipuladas se o número discado for válido, mas não atribuído a uma área comum do usuário. Os administradores podem configurar o Serviço de Comunicado para que essas chamadas sejam transferidas para um destino predeterminado (número telefônico ou URI SIP) ou reproduzir um comunicado em áudio ou ambos. O aplicativo de Anúncio ajuda a evitar situações em que o chamador disca para um número errado e ouve um tom de ocupado ou em que o cliente SIP recebe uma mensagem de erro. A funcionalidade de Serviço de Comunicado é um recurso típico de PBX. 
    
- **Estacionamento de Chamada**
    
    O aplicativo de estacionamento de chamadas permite que um usuário de voz empresarial Coloque uma chamada em espera de um telefone e, em seguida, receba a chamada de outro telefone sem precisar ligar os recursos do telefone que recebeu a chamada. O aplicativo de estacionamento de chamadas é útil quando um usuário precisa transferir uma chamada, mas o destinatário específico é desconhecido. 
    
- **Atendedor de conferência**
    
    O aplicativo atendedor de conferências fornece recursos de audioconferência para usuários telefônicos sem o serviço de um provedor de serviços de audioconferência de terceiros.
    
- **Comunicado de conferência**
    
    O aplicativo de anúncio de conferência produz toques que se sinalizam quando os usuários inserem ou saem de uma conferência, bem como as notificações para os usuários de telefones quando eles têm mudo ou mudo.
    
- **Serviço de Controle de Admissão de Chamadas**
    
    O Controle de admissão de chamada (CAC), também conhecido como gerenciador de largura de banda WAN, ajuda a evitar a experiência de baixa qualidade para usuários em redes congestionadas ao determinar, com base na largura de banda disponível, se permite que sessões de comunicação novas e em tempo real sejam estabelecidas. 
    
    > [!NOTE]
    > O CAC controla apenas o tráfego em tempo real e não afeta o tráfego de dados. 
  
    Se uma nova voz ou sessão de vídeo exceder os limites de largura de banda alocados em um WAN, a sessão é bloqueada ou, somente para chamadas de telefone, redirecionada ao PSTN.
    

