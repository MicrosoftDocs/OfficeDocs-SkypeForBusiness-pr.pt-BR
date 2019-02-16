---
title: Feature Overview (Planning Tool)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
ROBOTS: NOINDEX, NOFOLLOW
description: Skype para ferramenta de planejamento do Business Server
ms.openlocfilehash: f7a9f7fd0dfc7f4c65d85404bd827aee7b98332b
ms.sourcegitcommit: 6d4b99de7233e91dbab4f08331dac4d88c51d9e4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2019
ms.locfileid: "30059141"
---
# <a name="feature-overview-planning-tool"></a>Feature Overview (Planning Tool)
 
Skype para ferramenta de planejamento do Business Server
  
Você pode usar a página de **Sites centrais** da ferramenta de planejamento para projetar o Skype para implantação de servidor de negócios. Você pode criar tanto uma implantação centralizada quanto um distribuída. Uma implantação centralizada tem somente um site central, que hospedar Skype todos os usuários corporativos em sua organização. Uma implantação distribuída possui mais de um site central. Se você implantar o Skype para Business Server em vários sites centrais, você irá inserir o número de usuários em cada site central na ferramenta de planejamento.
  
Para completar a definição do site central, primeiro você precisa fornecer as seguintes informações:
  
- **Nome do site ** Insira o nome do Site central.
    
- **Número de Usuários** Insira o número de usuários, incluindo usuários em sites de filial que estão hospedados no site central.
    
- **Nuvem hospedados usuários** Insira o número de usuários que estão hospedados em um site central do Skype para Business Online.
    
## <a name="ui-elements"></a>Elementos da interface do usuário

Os elementos restantes foram populados com respostas que você forneceu às perguntas apresentadas no assistente da **Introdução** ou, se você tiver pulado o assistente, será populado automaticamente pela ferramenta de planejamento.
  
### <a name="online-collaboration"></a>Colaboração online

 A  **Colaboração online** contém as seguintes opções:
  
- **Mensagens instantâneas e presença**
    
    A mensagem instantânea permite que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens de texto. Tanto as sessões de mensagem instantânea entre duas partes como as entre várias partes são suportadas. A presença fornece informações a usuários sobre o status de outros na rede. Status de presença do usuário fornece informações que ajudam outros a determinar se o usuário está online e como melhor contatar o usuário. Por exemplo, a melhor forma de contatar um usuário que está em uma reunião é via email.
    
- **Conferência de áudio e vídeo**
    
    A conferência de áudio/vídeo (A/V) permite conferências de áudio e vídeo em tempo real.
    
- **Conferência discada**
    
    A conferência discada permite que os usuários participem de uma A/V a partir de um telefone na PSTN. A conferência discada requer a implantação dos aplicativos Atendedor de Conferência e Serviço de Comunicado de Conferência.
    
- **Webconferência**
    
    A Webconferência permite que os usuários empresariais internos e externos ao firewall criem e participem de conferências em tempo real hospedados nos servidores internos.
    
- **Chat Persistente**
    
    O Chat persistente permite que vários usuários participem de conversas nas quais eles postam e acessam conteúdo sobre tópicos específicos, incluindo texto, links e arquivos. Embora os usuários possam se comunicar em tempo real durante uma sessão, o conteúdo de cada sessão é persistente, o que significa que continua disponível após o fim de uma sessão.

    > [!NOTE] 
    > Bate-papo persistente está disponível no Skype para Business Server 2015, mas não é mais suportado no Skype para Business Server 2019. A mesma funcionalidade está disponível em equipes. Para obter mais informações, consulte [Atualizar Skype para negócios às equipes da Microsoft](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Se você precisar utilizar o chat persistente, suas opções são migrar usuários exigir que essa funcionalidade para equipes ou continuar usando Skype para Business Server 2015.
    
### <a name="users"></a>Usuários

 **Usuários** com as seguintes opções:
  
- **Organização interna**
    
- **Federação com outras organizações**
    
- **Federação com versões anteriores**
    
- **Federação com provedores de serviços de mensagem instantânea públicos** Permite que os usuários na organização estabeleçam comunicação com provedores públicos de serviço de mensagem instantânea, como MSN, Yahoo! e AOL. Uma licença separada é necessária para estabelecer federação com redes públicas de mensagem instantânea.
    
- **Federação com provedor de serviço com base XMPP**
    
    Skype para Business Server 2015 introduziu um proxy XMPP totalmente integrado (implantado nos servidores de borda) e um gateway XMPP implantado em seus servidores Front-End. É possível implantar adicionando e configurando o proxy XMPP e o gateway XMPP permitirá que seu Skype para usuários corporativos Server adicionar contatos de parceiros XMPP para mensagens instantâneas (IM) e presença.
    
- **Mobilidade**
    
    Quando você implanta o Skype para serviço de mobilidade do Business Server, os usuários podem usar suportados Apple iOS, Android, Windows Phone ou dispositivos móveis Nokia para realizar atividades como enviando e recebendo mensagens instantâneas, exibindo contatos e visualização de presença.
    
- **Caixa de correio W15 Exchange**
    
    Skype para Business Server permite que você tenha mensagens de caixa postal armazenadas no Exchange Unified Messaging (UM); Essas mensagens de caixa postal aparecerão como mensagens de email nas caixas de entrada dos usuários.

    > [!NOTE]
    > Unificação de mensagens do Exchange como conhecido anteriormente não está mais disponível no Exchange 2019, mas você pode ainda usar o sistema telefônico para mensagens de caixa postal de registro e, em seguida, deixar a gravação na caixa de correio do Exchange do usuário. Consulte o [serviço de caixa postal de nuvem planejar](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obter mais informações.
    
### <a name="voice"></a>Voz

 **Voz** contém as seguintes opções:
  
- **Enterprise Voice**
    
    Enterprise voice é a solução de VoIP ativado por software do Microsft. Voz empresarial permite aos usuários utilizar Skype for Business para fazer uma chamada telefônica de seu computador.
    
- **Unificação de Mensagens do Exchange**
    
    Caixa postal do Exchange Unified Messaging (UM) combina e email em uma única infra-estrutura de mensagens. Skype para Business Server 2015 usa UM do Exchange para fornecer atendimento de chamadas, acesso do assinante, notificação de chamada e serviços de atendedor automático. Se você usar esses serviços, será necessário integrar o UM do Exchange e Skype para Business Server em uma topologia compartilhada do Active Directory.

    > [!NOTE]
    > Unificação de mensagens do Exchange como conhecido anteriormente não está mais disponível no Exchange 2019, mas você pode ainda usar o sistema telefônico para mensagens de caixa postal de registro e, em seguida, deixar a gravação na caixa de correio do Exchange do usuário. Consulte o [serviço de caixa postal de nuvem planejar](../../../../sfbhybrid/hybrid/plan-cloud-voicemail.md) para obter mais informações.
    
### <a name="additional-deployment-options"></a>Opções de implantação adicionais

 **Opções de implantação adicionais** com as seguintes opções:
  
- **Alta disponibilidade**
    
    A alta disponibilidade permite servidores em espera para suporte contra failover.
    
- **Recuperação de desastres**
    
    Medidas de recuperação de desastres permitem aos pools de Front-End do par localizados em dois data centers.
    
- **Monitoramento**
    
    O monitoramento captura registros de detalhe de chamada relacionados a sessões de comunicação. Também coleta métricas de sessões de áudio e vídeo nas extremidades dos participantes. O Monitoring Server fornece as estatísticas de uso, tendências e estatísticas de qualidade de mídia.
    
- **Archiving**
    
    O arquivamento armazena conversas de mensagem instantânea e conferências.
    
- **Integração com arquivamento do Exchange**
    
    Se você tiver usuários hospedados no Exchange e suas caixas de correio que tenham sido colocadas em retenção In-loco, você pode selecionar a opção de integrar o Skype para armazenamento de Business Server com o armazenamento do Exchange.
    
- **IPv4**
    
    Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao número cada vez maior de dispositivos no mundo todo, os endereços IPv4 disponíveis podem se esgotar. Por isso, muitos dispositivos novos estão passando a usar endereços IPv6.
    
- **IPv6**
    
    Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32 bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.
    
- **Serviço Web de Atualização de Dispositivos**
    
    O serviço Web de atualização de dispositivo oferece uma forma automatizada de atualizar todos os dispositivos, como Skype para Business para Windows Phone, que são implantados fora da sua organização.
    
### <a name="server-applications"></a>Aplicativos de servidor

 **Aplicativos de servidor** contém as seguintes opções:
  
- **Grupo de Resposta**
    
    Aplicativo grupo de resposta atende e distribui chamadas para um operador de assistência técnica disponível automaticamente.
    
- **Comunicado**
    
    Se você planeja implantar o Enterprise Voice, você talvez queira ser capaz de configurar o modo como as chamadas telefônicas são tratadas se o número discado é válido, mas não atribuído a uma área comum do usuário. Os administradores podem configurar o Serviço de Comunicado para que essas chamadas sejam transferidas para um destino predeterminado (número telefônico ou URI SIP) ou reproduzir um comunicado em áudio ou ambos. O aplicativo de Anúncio ajuda a evitar situações em que o chamador disca para um número errado e ouve um tom de ocupado ou em que o cliente SIP recebe uma mensagem de erro. A funcionalidade de Serviço de Comunicado é um recurso típico de PBX. 
    
- **Estacionamento de Chamada**
    
    Habilita o aplicativo estacionamento de chamada de um usuário do Enterprise Voice para colocar uma chamada em espera em um telefone e, em seguida, recebe a chamada de outro telefone sem vincular recursos do telefone que recebeu a chamada. Aplicativo de estacionamento de chamada é útil quando um usuário precisa para transferir uma chamada, mas o destinatário específico é desconhecido. 
    
- **Atendedor de conferência**
    
    O aplicativo Conferencing Attendant fornece recursos de audioconferência aos usuários de telefone sem o serviço de um provedor de serviços de audioconferência de terceiros.
    
- **Comunicado de conferência**
    
    Anúncio de conferência aplicativo produz tons que sinalizam quando os usuários entram ou saem de uma conferência, bem como notificações aos usuários de telefone quando o mudo é ativado ou desativados.
    
- **Serviço de Controle de Admissão de Chamadas**
    
    O Controle de admissão de chamada (CAC), também conhecido como gerenciador de largura de banda WAN, ajuda a evitar a experiência de baixa qualidade para usuários em redes congestionadas ao determinar, com base na largura de banda disponível, se permite que sessões de comunicação novas e em tempo real sejam estabelecidas. 
    
    > [!NOTE]
    > O CAC controla apenas o tráfego em tempo real e não afeta o tráfego de dados. 
  
    Se uma nova voz ou sessão de vídeo exceder os limites de largura de banda alocados em um WAN, a sessão é bloqueada ou, somente para chamadas de telefone, redirecionada ao PSTN.
    

