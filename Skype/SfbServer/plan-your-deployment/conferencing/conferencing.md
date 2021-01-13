---
title: Planejar a conferência no Skype for Business Server
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
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Resumo: Leia este tópico para saber mais sobre recursos de conferência no Skype for Business Server.'
ms.openlocfilehash: 187da0c45724140295ba28285a33d8d57d422e4b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814051"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planejar a conferência no Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre recursos de conferência no Skype for Business Server.
  
A conferência no Skype for Business Server permite que os usuários se reunirem e realizarem conferências online usando seu cliente Skype for Business em vez de todos se reunirem na mesma sala. Os participantes da reunião podem se conectar a uma reunião com seu cliente Skype for Business para uma experiência completa de áudio e vídeo ou discar para uma conferência usando um telefone. As conferências também suportam mensagens instantâneas, compartilhamento de área de trabalho e aplicativos e painéis em branco interativos.
  
Este tópico inclui as seguintes seções:
  
- Recursos e funcionalidades de conferência
    
- Componentes de conferência
    
- Políticas de conferência
    
- Suporte para reuniões grandes
    
- Determinar as necessidades da sua organização
    
## <a name="conferencing-features-and-capabilities"></a>Recursos e funcionalidades de conferência

Há quatro tipos de conferências disponíveis no Skype for Business Server: webconferência, conferência de áudio e vídeo (A/V), conferência discada e conferência por mensagem instantânea (IM). 
  
Você pode optar por habilitar todos os tipos de conferência ou usar apenas um tipo, dependendo de suas necessidades. Por exemplo, você pode habilitar todos os tipos, incluindo conferência discada, para permitir que os usuários que não conseguem ingressar em uma conferência com um cliente Skype for Business liguem e participem do áudio da reunião de um telefone. Quando você implanta o Skype for Business Server, os recursos de conferência por IM são implantados automaticamente; você especifica se a web, A/V e conferência discada devem ser implantadas usando o Construtor de Topologias. Para obter mais informações, [consulte Implantar conferências no Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md) 
  
As subseções a seguir descrevem os recursos e capacidades de cada tipo de conferência.
  
### <a name="web-conferencing"></a>Webconferência

A webconferência permite que os participantes da reunião colaborem em documentos compartilhados durante a reunião e que o apresentador compartilhe aplicativos por meio do cliente Skype for Business. A webconferência fornece os seguintes recursos: 
  
- **Quadro de anotações e quadro de anotações.** Um quadro de comunicações é uma tela em branco que pode ser usada para colaboração com texto, tinta, desenhos e imagens. As anotações feitas nos quadros de comunicações podem ser vistas por todos os participantes da reunião. O recurso de quadro de comunicações aprimora a colaboração ao permitir que os participantes da reunião discutam ideias, façam brainstorm, anotações e outros.
    
- **Sondagem.** O recurso de sondagem aprimora a colaboração, permitindo que os apresentadores determinem rapidamente as preferências dos participantes. Durante reuniões online e conversas, os apresentadores podem utilizar a sondagem para obter respostas anônimas dos participantes. Todos os apresentadores podem ver os resultados e podem escondê-los ou mostrá-los aos presentes.
    
- **Compartilhamento de aplicativos e área de trabalho.** Durante uma conferência, o apresentador da reunião pode compartilhar toda a área de trabalho, um aplicativo individual ou monitores individuais em um ambiente com vários monitores. Além de apenas visualizar o conteúdo, outros participantes da conferência podem solicitar o controle da tela do apresentador e, com permissão, interagir com o conteúdo (incluindo rolagem e edição). Os participantes da reunião também podem assumir como apresentadores e começar a compartilhar conteúdo durante a reunião.
    
- **Compartilhamento do PowerPoint.** Permite que os usuários compartilhem apresentações do PowerPoint na reunião por meio de um servidor do Office Web Apps, que permite:
    
  - Exibições de alta resolução e suporte para recursos do PowerPoint, como animações, transições de slides e vídeo incorporado.
    
  - Os dispositivos móveis podem acessar essas apresentações.
    
  - Os usuários com as permissões apropriadas podem rolar uma apresentação do PowerPoint independente da apresentação propriamente dita. Por exemplo, enquanto Ken está apresentando sua apresentação de slides, Paulo pode olhar para qualquer slide que quiser sem afetar a apresentação de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferência de áudio e vídeo

A conferência de áudio e vídeo permite áudio e vídeo na reunião. O áudio permite que os participantes conversem uns com os outros como se estivesse na mesma sala. O vídeo habilita a exibição de vídeo no cliente Skype for Business de quaisquer participantes ou apresentadores que participem da reunião com uma webcam ou um dispositivo de conferência que suporte vídeo.
  
 O Skype for Business Server fornece vários recursos que os usuários podem usar para configurar a experiência de audioconferência para o usuário, incluindo o seguinte:
  
- **Mudo do público.** O apresentador pode usar essa configuração para retirar o áudio de todos os participantes na conferência e colocar a conferência em um estado no qual aqueles que não forem apresentadores não poderão ativar o áudio.
    
- **Anúncios de entrada/saída de conferência.** Se você ativou a conferência discada, os apresentadores podem usar essa configuração para ligar ou desligar os anúncios de entrada/saída para minimizar distrações, enquanto a conferência estiver em andamento.
    
- **Adicionar um usuário discando.** Os apresentadores e participantes que receberam permissão podem adicionar números PSTN às conferências e fazer com que a conferência disque para esses números.
    
  O Skype for Business Server fornece vários recursos que os usuários podem usar para configurar a experiência de videoconferência para o usuário, incluindo o seguinte:
  
- **Exibição de Galeria.** Em conferências de vídeo que tenham mais que duas pessoas, os usuários podem automaticamente ver todos na conferência. Se a conferência tiver mais que cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida. O vídeo de vários participantes está ativado como padrão.
    
- **Vídeo panorâmico.** Se um dispositivo de conferência de vídeo de mesa redonda estiver instalado na sala de conferências, esse recurso fornecerá uma visão de 360 graus da sala de conferência. A faixa de vídeo panorâmico está disponível apenas em dispositivos de mesa redonda.
    
- **Modo de vídeo somente do apresentador.** Os apresentadores podem configurar a reunião de forma que apenas o vídeo deles seja exibido. Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e travadas para diferentes fontes. Esse modo também é aplicado ao vídeo capturado e fornecido por dispositivos de mesa redonda.
    
- **Destaque de Vídeo.** Os apresentadores podem configurar a reunião para que apenas o vídeo de um participante selecionado seja visto pelos outros participantes na conferência. Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos de mesa redonda de vídeo panorâmico.
    
### <a name="dial-in-conferencing"></a>Conferência discada

A conferência discada permite que os participantes da reunião participem da parte de áudio de uma reunião ligando para a reunião de um telefone. A conferência discada é um subconjunto da conferência de áudio e exige configuração adicional. Para obter mais informações sobre conferência discada, consulte [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md) and Configure [dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferência de mensagens instantâneas

A conferência de mensagens instantâneas (IM) permite que mais de duas partes se comuniquem em uma única sessão de IM. Para obter detalhes sobre conferência de mensagens instantâneas, consulte Plano para mensagens instantâneas [e presença no Skype for Business Server.](../../plan-your-deployment/instant-messaging-and-presence.md)
  
## <a name="conferencing-components"></a>Componentes de conferência

Os componentes que suportam recursos de conferência incluem o seguinte:
  
- **Serviço de aplicativo.** O serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicações unificadas (UC). A conferência discda usa dois aplicativos de UC que exigem o serviço de Aplicativo: Atendente de Conferência e Comunicado de Conferência. O serviço de Aplicativo é instalado e ativado por padrão em cada Servidor front-end em um pool de Front-End. Ele também é instalado em cada servidor Standard Edition para habilitar e configurar a conferência discada.
    
- **Aplicativo Attendant de Conferência.** O aplicativo Atendente de Conferência é um aplicativo de comunicações unificadas que aceita chamadas PSTN (rede telefônica pública comutado), reproduz prompts e inscreva as chamadas em uma conferência A/V. O aplicativo Atendente de Conferência é instalado e ativado por padrão quando você habilita a conferência discada.
    
- **Aplicativo Comunicado de Conferência.** O aplicativo Comunicado de Conferência é um aplicativo de comunicações unificadas que reproduz tons e solicita aos participantes PSTN determinadas ações, como quando os participantes ingressam ou saem de uma conferência, os participantes são silenciados ou sem som, alguém entra no lobby da conferência ou a conferência está bloqueada ou desbloqueada. O aplicativo Comunicado de Conferência também oferece suporte a comandos DTMF (multifrequência de tom dual) no teclado do telefone. O aplicativo Comunicado de Conferência é instalado e ativado automaticamente por padrão quando você habilita a conferência discada.
    
- **Página Configurações de Conferência Discado.** A página Configurações de Conferência Discada exibe os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (ou seja, para reuniões que não precisam ser agendadas) e os controles DTMF em conferência e oferece suporte ao gerenciamento de PIN (número de identificação pessoal) e informações de conferência atribuídas. A página Configurações de Conferência Discada é instalada automaticamente como parte dos Serviços Web.
    
- **Servidor de Mediação e gateway PSTN.** A conferência discada requer um Servidor de Mediação para traduzir a sinalização (e mídia em algumas configurações) entre o Skype for Business Server e o gateway PSTN e um gateway PSTN para traduzir a sinalização e a mídia entre o Servidor de Mediação e o gateway PSTN. Para a Conferência de Discagem, você deve implantar pelo menos um Servidor de Mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
  > [!NOTE]
  > Se você também estiver implantando o Enterprise Voice, o Servidor de Mediação e os gateways PSTN fazem parte da implantação do Enterprise Voice. Se você não estiver implantando o Enterprise Voice, será necessário implantar pelo menos um Servidor de Mediação e um gateway PSTN, IP-PBX ou SBC para a conferência de discagem. 
  
- **Armazenamento de arquivos.** O repositório de arquivos é usado para arquivos de áudio de nome gravado. O repositório de arquivos é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.
    
- **Armazenamento do usuário.** O armazenamento do usuário é usado para armazenar os PINs do Skype for Business Server do usuário. Os PINs estão em hash. O repositório de usuário é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.
    
- **Servidor do Office Web Apps.** Para usar os recursos de webconferência, os administradores devem instalar o Servidor do Office Web Apps e configurar o Skype for Business Server para se comunicar com o Servidor do Office Web Apps.
    
## <a name="conferencing-policies"></a>Políticas de conferência

Para impor as políticas da sua organização e controlar o uso da largura de banda, você pode definir políticas para os tipos de reuniões que os usuários podem organizar. Você pode definir uma ampla variedade de políticas de conferência e atribuí-las a usuários individuais e grupos de usuários. Você também pode definir políticas que governam conversas ponto a ponto. Para obter detalhes sobre como definir políticas de conferência, consulte Gerenciar políticas [de conferência no Skype for Business Server.](../../manage/conferencing/conferencing-policies.md) Para obter detalhes sobre gerenciamento de largura de banda, [consulte Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Suporte para reuniões grandes

O tamanho das reuniões que o Skype for Business Server pode suportar depende de a conferência ser hospedada em um pool compartilhado ou dedicado:
  
- Em um pool compartilhado, o Skype for Business Server pode hospedar reuniões com até 250 usuários. Um pool compartilhado é um pool que hospeda todas as cargas de trabalho do Skype for Business Server, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice. 
    
- Em um pool dedicado, o Skype for Business Server pode dar suporte a reuniões com até 1.000 participantes usando conferências web e de áudio/vídeo (A/V), incluindo o compartilhamento de apresentações do PowerPoint. Esse suporte requer um pool dedicado configurado para suportar grandes reuniões e gerenciado de forma a garantir a hospedagem de apenas uma grande reunião por vez. 
    
Para obter mais informações sobre como gerenciar grandes reuniões, [consulte Planejar grandes reuniões no Skype for Business Server.](large-meetings.md)
  
Se sua organização exigir recursos maiores de reunião, considere a implementação de um ambiente híbrido que aproveite a Transmissão de Reunião do Skype, um serviço online que faz parte do Microsoft 365 e do Office 365. A Transmissão de Reunião do Skype permite que os usuários hospedem e transdiem reuniões para grandes audiências online de até 10.000 participantes. O uso da Transmissão de Reunião do Skype exige que o Skype for Business Server já tenha sido configurado em uma configuração híbrida com uma organização de produção do Microsoft 365 ou Office 365. Todos os usuários devem ter um locatário online estabelecido como pré-requisito. Se você estiver interessado em implantar uma solução híbrida que possa aproveitar a Transmissão de Reunião do Skype, consulte Configurar sua implantação local para a Transmissão de Reunião [do Skype.](../../deploy/configure-skype-meeting-broadcast.md)
  
## <a name="determine-your-organizations-needs"></a>Determinar as necessidades de suas organizações

Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista a seguir orienta você durante o processo de planejamento de conferências para determinar quais recursos de conferência você deve implantar, com base nos requisitos da sua organização.
  
> [!NOTE]
> Ao habilitar a conferência na implantação, você habilita automaticamente a webconferência e a conferência A/V. No entanto, você pode desabilitar recursos específicos configurando políticas de conferência conforme descrito anteriormente neste tópico. 
  
- **Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**
    
    Se sim, você deve habilitar a conferência para seu pool de Front-End usando a Ferramenta de Planejamento ou o Construtor de Topologias. Para obter mais informações, [consulte Implantar conferências no Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    O compartilhamento de aplicativo requer e usa mais largura de banda do que a colaboração em documentos. O Skype for Business Server fornece um mecanismo de controle para controlar cada sessão de compartilhamento de aplicativos. Por padrão, isso é definido como 1,5 KB por segundo para cada sessão. Se você não quiser habilitar o compartilhamento de aplicativos, mas quiser a colaboração em documentos, poderá habilitar a conferência e usar as políticas de conferência para desabilitar o compartilhamento de aplicativos. Para obter detalhes sobre como configurar políticas de conferência, consulte Gerenciar políticas [de conferência no Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
    
    Para permitir que os usuários compartilhem apresentações do PowerPoint, você precisa configurar o Servidor do Office Web Apps. Para obter detalhes sobre como configurar o Servidor do Office Web Apps, consulte Configurar a integração com o Servidor do [Office Web Apps no Skype for Business Server.](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **Deseja habilitar a conferência de áudio e vídeo?**
    
    Se sim, você deve habilitar a conferência para seu pool de Front-End usando a Ferramenta de Planejamento ou o Construtor de Topologias. Para obter mais informações, [consulte Implantar conferências no Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)
    
    A conferência de áudio e vídeo exige e usa mais largura de banda do que a webconferência (que inclui a colaboração em documentos e o compartilhamento de aplicativos). Se você não quiser habilitar a conferência de áudio e vídeo, mas quiser habilitar a webconferência, poderá habilitar a conferência e usar políticas de conferência para desabilitar conferências A/V.
    
    Se você quiser habilitar conferências de áudio, mas não conferências de vídeo, poderá habilitar a conferência A/V e usar políticas de conferência para impedir conferências de vídeo. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V. 
    
    Para obter mais informações sobre como configurar políticas de conferência, consulte Gerenciar políticas [de conferência no Skype for Business Server.](../../manage/conferencing/conferencing-policies.md)
    
    > [!NOTE]
    > O Enterprise Voice não é necessário para você usar a conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio a suas conferências se tiverem dispositivos de áudio, mesmo que você use um sistema PBX como sua solução de telefone. 
  
- **Deseja permitir que os usuários ingressem na parte de áudio de conferências quando usam um telefone PSTN?**
    
    Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.
    
    A conferência discada é um recurso opcional que você pode configurar ao implantar a conferência do Skype for Business Server. Embora a conferência discda use alguns dos mesmos componentes que o Enterprise Voice usa, você pode implantar a conferência discado mesmo se não implantar o Enterprise Voice. A conferência de discagem suporta aos usuários corporativos e anônimos. Para obter mais informações sobre como configurar a conferência discada para usuários corporativos e anônimos, consulte [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) and Configure [dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Você deseja permitir que usuários externos com clientes do Skype for Business participem de conferências?**
    
    Ao permitir a participação externa em reuniões, você maximiza seu investimento no Skype for Business Server. Os usuários externos podem incluir:
    
  - **Usuários remotos.** Os usuários da sua organização, quando eles estão trabalhando fora de seus firewalls e estão usando laptops ou outros dispositivos do Skype for Business Server.
    
  - **Usuários federados.** Usuários de empresas com quem você trabalha e que também executem o Skype for Business Server. Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas.
    
  - **Usuários anônimos.** Outros usuários externos que são convidados especificamente por seus usuários para participar de conferências específicas. O organizador de uma reunião em sua empresa pode enviar um convite por email de uma conferência para um usuário externo. O email inclui um link no qual o usuário externo pode clicar para ingressar na conferência.
    
    Se você quiser permitir usuários externos, será necessário implantar Servidores de Borda. Além disso, com os Servidores de Borda implantados, você pode criar relacionamentos federados com outras organizações , como seus clientes ou fornecedores, e os usuários dessas organizações podem colaborar mais facilmente com seus usuários.
    
    Para obter detalhes sobre como implantar Servidores de Borda, consulte Plan for Edge Servers and Deploy Edge Servers. Para obter detalhes sobre a habilitação do acesso externo para o Servidor do Office Web Apps, consulte Configurar a integração com o Servidor do [Office Web Apps no Skype for Business Server.](../../deploy/deploy-conferencing/office-web-app-server.md)
    
- **Você deseja controlar os clientes que podem ingressar em reuniões do Skype for Business Server?**
    
    Em caso afirmativo, você deve configurar a página de ingresso em reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis. Sempre que um usuário clica em um link para ingressar em uma reunião agendada, o Skype for Business Server detecta se um cliente já está instalado no computador. Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso em reunião, que contém links para clientes alternativos. A página de junção de reunião sempre contém a opção de usar o Skype for Business Web App. Além dessa opção, você pode decidir se incluirá links para Participantes e versões anteriores do Communicator. 
    

