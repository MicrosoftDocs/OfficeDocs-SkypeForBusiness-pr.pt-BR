---
title: Visão geral do recurso (Ferramenta de Planejamento)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/6/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.FeatureOverview
- ms.lync.plan.FeatureOverview
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44783b37-c87f-41f2-9de1-39176f1856ab
description: Ferramenta de Planejamento do Skype for Business Server 2015
ms.openlocfilehash: 3aa259314d8a92142cf37dcd3611773490248e02
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834781"
---
# <a name="feature-overview-planning-tool"></a>Visão geral do recurso (Ferramenta de Planejamento)
 
Ferramenta de Planejamento do Skype for Business Server 2015
  
Você pode usar a **página Sites Centrais** da Ferramenta de Planejamento para projetar a implantação do Skype for Business Server. Você pode criar duas implantações centralizadas ou distribuídas. Uma implantação centralizada tem apenas um site central, que fica com todos os usuários do Skype for Business em sua organização. Uma implantação distribuída tem mais de um site central. Se você implantar o Skype for Business Server em vários sites centrais, inserirá o número de usuários em cada site central na Ferramenta de Planejamento.
  
Para concluir a definição do site central, primeiro você precisa fornecer as seguintes informações:
  
- **Nome do Site** Insira o nome do Site Central.
    
- **Número de usuários** Insira o número de usuários, incluindo usuários em sites de filial que estão no site central.
    
- **Usuários na nuvem** Insira o número de usuários que estão instalados no site central do Skype for Business Online.
    
> [!NOTE]
> Essa ferramenta não será atualizada para o Skype for Business Server 2019.

## <a name="ui-elements"></a>Elementos de interface do usuário

Os elementos restantes foram preenchidos com as respostas que  você forneceu às perguntas apresentadas no assistente de Iniciação ou, se você ignorou o assistente, foi preenchido automaticamente pela ferramenta de planejamento.
  
### <a name="online-collaboration"></a>Colaboração Online

 **A Colaboração Online** contém as seguintes opções:
  
- **IM e presença**
    
    As mensagens instantâneas (IM) permitem que os usuários se comuniquem entre si em tempo real em seus computadores usando mensagens baseadas em texto. Tanto as sessões de IM de duas partes como as multipartes são suportadas. A presença fornece informações aos usuários sobre o status de outras pessoas na rede. O status de presença de um usuário fornece informações para ajudar outras pessoas a determinar se o usuário está online e como entrar em contato melhor com o usuário. Por exemplo, um usuário que está em uma reunião é melhor contatado por email.
    
- **Conferência de áudio e vídeo**
    
    A conferência de áudio/vídeo (A/V) permite conferências de áudio e vídeo em tempo real.
    
- **Conferência discada**
    
    A conferência discda permite que os usuários participem de uma A/V a partir de um telefone na PSTN. A conferência discda exige que você implante os aplicativos De Serviço de Anúncio de Conferência e Atendente de Conferência.
    
- **Webconferência**
    
    A webconferência permite que os usuários corporativos dentro e fora do firewall criem e participem de conferências em tempo real hospedadas em seus servidores internos.
    
- **Chat Persistente**
    
    O Chat Persistente permite que vários usuários participem de conversas nas quais eles publicam e acessam conteúdo sobre tópicos específicos, incluindo texto, links e arquivos. Embora os usuários possam se comunicar em tempo real durante uma sessão, o conteúdo de cada sessão é persistente, o que significa que continua disponível após o fim de uma sessão.
    
### <a name="users"></a>Usuários

 **Os** usuários contêm as seguintes opções:
  
- **Organização interna**
    
- **Federação com outras organizações**
    
- **Federação com versões anteriores**
    
- **Federação com provedores de serviços públicos de IM** Permite que os usuários em sua organização estabeleçam comunicação com provedores públicos de serviços de mensagens instantâneas, como MSN, Yahoo!, e AOL. Uma licença separada é necessária para estabelecer a federação com redes públicas de mensagens instantâneas.
    
- **Federação com provedor de serviços baseado em XMPP**
    
    O Skype for Business Server 2015 apresenta um proxy XMPP totalmente integrado (implantado nos Servidores de Borda) e um gateway XMPP implantado em seus Servidores Front-End. Você pode implantar Adicionando e configurando o proxy XMPP e o gateway XMPP permitirá que seus usuários do Skype for Business Server 2015 adicionem contatos de parceiros baseados em XMPP para mensagens instantâneas (IM) e presença.

> [!NOTE]
> Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019. Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.
    
- **Mobilidade**
    
    Quando você implanta o Serviço de Mobilidade do Skype for Business Server 2015, os usuários podem usar os dispositivos móveis Apple iOS, Android, Windows Phone ou Nokia com suporte para realizar atividades como enviar e receber mensagens instantâneas, exibir contatos e exibir presença.
    
- **Caixa de correio do Exchange W15**
    
    O Skype for Business Server 2015 permite que você tenha mensagens de caixa postal armazenadas na Unificação de Mensagens (UM) do Exchange; essas mensagens de caixa postal aparecerão como mensagens de email nas Caixas de Entrada dos usuários.
    
### <a name="voice"></a>Voz

 **A** voz contém as seguintes opções:
  
- **Enterprise Voice**
    
    O Enterprise Voice é a solução VoIP da Microsft com software. O Enterprise Voice permite que os usuários usem o Skype for Business para fazer uma chamada telefônica de seus computadores.
    
- **Unificação de Mensagens do Exchange**
    
    A Unificação de Mensagens (UM) do Exchange combina caixa postal e email em uma única infraestrutura de mensagens. O Skype for Business Server 2015 usa a UM do Exchange para fornecer atendimento de chamadas, acesso de assinante, notificação de chamada e serviços de atendedor automático. Se você usar esses serviços, precisará integrar o UM do Exchange e o Skype for Business Server em uma topologia compartilhada do Active Directory.
    
### <a name="additional-deployment-options"></a>Opções de implantação adicionais

 **Opções de implantação adicionais** contêm as seguintes opções:
  
- **Alta Disponibilidade**
    
    A alta disponibilidade habilita servidores em espera para suporte a failover.
    
- **Recuperação de desastres**
    
    As medidas de recuperação de desastres permitem que você emparelhe pools de Front-End localizados em dois datacenters.
    
- **Monitoramento**
    
    O monitoramento captura registros de detalhes de chamada relacionados a sessões de comunicação. Ele também coleta métricas de sessões de áudio e vídeo nos pontos de extremidade do participante. O Monitoring Server fornece estatísticas de uso, tendências e estatísticas de qualidade de mídia.
    
- **Arquivamento**
    
    O arquivamento armazena conversas e conferências de mensagens instantâneas.
    
- **Integração com Arquivamento do Exchange**
    
    Se você tiver usuários que estão no Exchange 2013 e suas caixas de correio foram colocadas em In-Place, você pode selecionar a opção para integrar o armazenamento do Skype for Business Server 2015 com o armazenamento do Exchange.
    
- **IPv4**
    
    Os endereços IPv4 são endereços 32 bits que permitem a um computador se comunicar pela Internet. Devido ao crescente número de dispositivos em todo o mundo, os endereços IPv4 disponíveis estão sem saída. Por isso, muitos dispositivos novos estão passando a usar endereços IPv6.
    
- **IPv6**
    
    Os endereços IPv6 executam a mesma função que os endereços IPv4 (com alguns recursos adicionais), mas em vez de usar somente 32-bits, os endereços IPv6 usam 128 bits. Isso fornece não apenas um novo conjunto de endereços, mas também um número muito maior deles.
    
- **Serviço Web de Atualização de Dispositivos**
    
    O serviço Web de Atualização de Dispositivo fornece uma maneira automatizada de atualizar todos os dispositivos, como o Skype for Business para Windows Phone, que são implantados fora da sua organização.
    
### <a name="server-applications"></a>Aplicativos para servidores

 **Os Aplicativos para** Servidores contêm as seguintes opções:
  
- **Grupo de Resposta**
    
    O aplicativo Grupo de Resposta responde automaticamente e distribui chamadas para um agente de helpdesk disponível.
    
- **Comunicado**
    
    Se você planeja implantar o Enterprise Voice, talvez queira configurar como as chamadas telefônicas serão tratadas se o número discado for válido, mas não atribuído a uma área comum do usuário. Os administradores podem configurar o Serviço de Comunicado para que essas chamadas transfiram para um destino predeterminado (número de telefone ou URI do SIP) ou reproduzam um comunicado de áudio ou ambos. O uso do Serviço de Comunicado evita a situação em que um chamador se desinforma e ouve um tom de ocupado ou o cliente SIP recebe uma mensagem de erro. A funcionalidade do Serviço de Comunicado é um recurso típico de PBX. 
    
- **Estacionamento de chamada**
    
    O aplicativo Estacionamento de Chamada permite que um usuário do Enterprise Voice coloque uma chamada em espera em um telefone e receba a chamada de outro telefone sem ligar para o telefone que recebeu a chamada. O aplicativo Estacionamento de Chamada é útil quando um usuário precisa transferir uma chamada, mas o destinatário específico é desconhecido. 
    
- **Atendente de conferência**
    
    O aplicativo Atendente de Conferência fornece recursos de audioconferência para usuários de telefone sem o serviço de um provedor de serviços de audioconferência de terceiros.
    
- **Comunicado de Conferência**
    
    O aplicativo Comunicado de Conferência produz tons que sinalizam quando os usuários entram ou saem de uma conferência, bem como notificações aos usuários de telefone quando eles estão sem som ou sem som.
    
- **Serviço de Controle de Admissão de Chamadas**
    
    O CAC (Controle de Admissão de Chamada), também conhecido como gerenciamento de largura de banda WAN, ajuda a evitar uma baixa qualidade da experiência para usuários em redes congestionadas determinando, com base na largura de banda disponível, se é para permitir e estabelecer novas sessões de comunicação em tempo real. 
    
    > [!NOTE]
    > O CAC controla apenas o tráfego em tempo real e não afeta o tráfego de dados. 
  
    Se uma nova sessão de voz ou vídeo exceder os limites de largura de banda alocados em uma WAN, a sessão será bloqueada ou (somente para chamadas telefônicas) redirecionada para a PSTN.
    

