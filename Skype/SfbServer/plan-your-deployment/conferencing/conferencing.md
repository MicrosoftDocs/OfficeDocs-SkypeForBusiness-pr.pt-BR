---
title: Planejar conferências em Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Resumo: leia este tópico para saber mais sobre recursos e recursos de conferência no Skype for Business Server.'
ms.openlocfilehash: 669c87bd2c5eae3944a586e289bbeac3fd4409df
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394983"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planejar conferências em Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre recursos e recursos de conferência Skype for Business Server.
  
A conferência no Skype for Business Server permite que os usuários se reunirem e realizarem conferências online usando seu cliente Skype for Business em vez de todos se reunirem na mesma sala. Os participantes da reunião podem se conectar a uma reunião com seu cliente Skype for Business para uma experiência completa de áudio e vídeo ou discar para uma conferência usando um telefone. As conferências também suportam mensagens instantâneas, compartilhamento de aplicativos e área de trabalho e painéis em branco interativos.
  
Este tópico inclui as seguintes seções:
  
- Recursos e recursos de conferência
    
- Componentes de conferência
    
- Políticas de conferência
    
- Suporte para grandes reuniões
    
- Determinar as necessidades da sua organização
    
## <a name="conferencing-features-and-capabilities"></a>Recursos e recursos de conferência

Há quatro tipos de conferências disponíveis em Skype for Business Server: webconferência, conferência de áudio e vídeo (A/V), conferência discda e conferência de mensagem instantânea (IM). 
  
Você pode optar por habilitar todos os tipos de conferência ou usar apenas um tipo, dependendo das suas necessidades. Por exemplo, você pode habilitar todos os tipos, incluindo conferência discda, para permitir que os usuários que não podem ingressar em uma conferência com um cliente Skype for Business liguem e participem do áudio da reunião de um telefone. Quando você implanta Skype for Business Server, os recursos de conferência de IM são implantados automaticamente; você especifica se deve implantar a Web, a A/V e a conferência discada usando o Construtor de Topologias. Para obter mais informações, [consulte Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
As subseções a seguir descrevem os recursos e os recursos de cada tipo de conferência.
  
### <a name="web-conferencing"></a>Webconferência

A webconferência permite que os participantes da reunião colaborem em documentos compartilhados durante a reunião e para que o apresentador da reunião compartilhe aplicativos por meio do Skype for Business cliente. A webconferência fornece os seguintes recursos: 
  
- **Quadro de anotações e anotações.** Um quadro de comunicações é uma tela em branco que pode ser usada para colaboração com texto, tinta, desenhos e imagens. As anotações feitas nos quadros de comunicações podem ser vistas por todos os participantes da reunião. O recurso de quadro de comunicações aprimora a colaboração ao permitir que os participantes da reunião discutam ideias, façam brainstorm, anotações e outros.
    
- **Sondagem.** O recurso de sondagem aprimora a colaboração permitindo que os apresentadores determinem rapidamente as preferências dos participantes. Durante reuniões online e conversas, os apresentadores podem utilizar a sondagem para obter respostas anônimas dos participantes. Todos os apresentadores podem ver os resultados e podem escondê-los ou mostrá-los aos presentes.
    
- **Compartilhamento de aplicativos e compartilhamento de área de trabalho.** Durante uma conferência, o apresentador de reunião pode compartilhar toda a área de trabalho, um aplicativo individual ou monitores individuais em um ambiente de vários monitores. Além de apenas exibir o conteúdo, outros participantes da conferência podem solicitar o controle da tela do apresentador e, com permissão, interagir com o conteúdo (incluindo rolagem e edição). Os participantes da reunião também podem assumir como apresentador e começar a compartilhar conteúdo durante a reunião.
    
- **PowerPoint Compartilhamento.** Permite que os usuários compartilhem PowerPoint apresentações na reunião por meio de um servidor Office Web Apps, que permite:
    
  - Exibe e suporta recursos de alta resolução para PowerPoint, como animações, transições de slides e vídeo incorporado.
    
  - Os dispositivos móveis podem acessar essas apresentações.
    
  - Os usuários com as permissões apropriadas podem percorrer uma apresentação PowerPoint independentemente da apresentação em si. Por exemplo, enquanto Ken apresenta sua apresentação de slides, Heidi pode olhar para qualquer slide que quiser sem afetar a apresentação de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferência de áudio e vídeo

A conferência de áudio e vídeo permite áudio e vídeo na reunião. O áudio permite que os participantes conversem uns com os outros como se eles estavam na mesma sala. O vídeo habilita a exibição de vídeo Skype for Business cliente de todos os participantes ou apresentadores que ingressarem na reunião com uma web cam ou dispositivo de conferência que oferece suporte a vídeo.
  
 Skype for Business Server vários recursos que os usuários podem usar para configurar a experiência de audioconferência para o usuário, incluindo o seguinte:
  
- **Audiência muda.** O apresentador pode usar essa configuração para retirar o áudio de todos os participantes na conferência e colocar a conferência em um estado no qual aqueles que não forem apresentadores não poderão ativar o áudio.
    
- **Comunicados de entrada/saída de conferência.** Se você ativou a conferência discada, os apresentadores podem usar essa configuração para ligar ou desligar os anúncios de entrada/saída para minimizar distrações, enquanto a conferência estiver em andamento.
    
- **Adicionando um usuário discando.** Apresentadores e participantes que receberam permissão, podem adicionar números PSTN às conferências e ter a discagem de conferência para esses números.
    
  Skype for Business Server vários recursos que os usuários podem usar para configurar a experiência de conferência de vídeo para o usuário, incluindo o seguinte:
  
- **Exibição da Galeria.** Em conferências de vídeo que tenham mais que duas pessoas, os usuários podem automaticamente ver todos na conferência. Se a conferência tiver mais que cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida. O vídeo de vários participantes está ativado como padrão.
    
- **Vídeo panorâmico.** Se um dispositivo de conferência de vídeo de mesa redonda estiver instalado na sala de conferências, esse recurso fornecerá uma visão de 360 graus da sala de conferência. A faixa de vídeo panorâmico está disponível apenas em dispositivos de mesa redonda.
    
- **Modo de vídeo somente apresentador.** Os apresentadores podem configurar a reunião de forma que apenas o vídeo deles seja exibido. Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e travadas para diferentes fontes. Esse modo também é aplicado ao vídeo capturado e fornecido por dispositivos de mesa redonda.
    
- **Destaque de vídeo.** Os apresentadores podem configurar a reunião para que apenas o vídeo de um participante selecionado seja visto pelos outros participantes na conferência. Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos de mesa redonda de vídeo panorâmico.
    
### <a name="dial-in-conferencing"></a>Conferência discada

A conferência discada permite que os participantes da reunião participem da parte de áudio de uma reunião ligando para a reunião de um telefone. A conferência discada é um subconjunto da conferência de áudio e exige configuração adicional. Para obter mais informações sobre conferência discda, consulte [Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md) and [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferência de mensagens instantâneas

A conferência de mensagens instantâneas (IM) permite que mais de duas partes se comuniquem em uma única sessão de mensagens instantâneas. Para obter detalhes sobre conferência de mensagens instantâneas, consulte [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferência

Os componentes que suportam recursos de conferência incluem o seguinte:
  
- **Serviço de aplicativo.** O serviço application fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicações unificadas (UC). A conferência discagem usa dois aplicativos UC que exigem o serviço application: Atendedor de Conferência e Comunicado de Conferência. O serviço application é instalado e ativado por padrão em todos os Servidores Front-End em um pool de Front-End. Ele também é instalado em todos os servidores Edição Standard para habilitar e configurar a conferência discada.
    
- **aplicativo Atendedor de Conferência.** O aplicativo Atendedor de Conferência é um aplicativo de comunicação unificado que aceita chamadas PSTN (rede telefônica pública comutado), reproduz prompts e inscreva as chamadas a uma conferência A/V. O aplicativo Atendedor de Conferência é instalado e ativado por padrão quando você habilita a conferência discada.
    
- **aplicativo Comunicado de Conferência.** O aplicativo Comunicado de Conferência é um aplicativo de comunicações unificado que reproduz tons e solicita aos participantes da PSTN determinadas ações, como quando os participantes ingressam ou saem de uma conferência, os participantes são mudos ou não são intermediados, alguém entra no lobby da conferência ou a conferência é bloqueada ou desbloqueada. aplicativo Comunicado de Conferência também oferece suporte a comandos DTMF (multifrequência de tom duplo) do teclado do telefone. O aplicativo Comunicado de Conferência é instalado automaticamente e ativado por padrão quando você habilita a conferência discada.
    
- **Página Configurações discagem.** A página conferência discada Configurações exibe números de discagem de conferência com seus idiomas disponíveis, informações de conferência atribuídas (ou seja, para reuniões que não precisam ser agendadas), controles DTMF em conferência e dá suporte ao gerenciamento de PIN (número de identificação pessoal) e informações de conferência atribuídas. A página de conferência discada Configurações é instalada automaticamente como parte dos Serviços Web.
    
- **Servidor de Mediação e gateway PSTN.** A conferência discagem exige que um Servidor de Mediação traduza sinalização (e mídia em algumas configurações) entre o Skype for Business Server e o gateway PSTN e um gateway PSTN para converter sinalização e mídia entre o Servidor de Mediação e o gateway PSTN. Para a Conferência de Discagem, você deve implantar pelo menos um Servidor de Mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
  > [!NOTE]
  > Se você também estiver implantando Enterprise Voice, os gateways PSTN e Servidor de Mediação fazem parte da implantação Enterprise Voice. Se você não estiver implantando o Enterprise Voice, será necessário implantar pelo menos um Servidor de Mediação e um gateway PSTN, IP-PBX ou SBC para a conferência de discagem. 
  
- **Armazenamento de arquivos.** O repositório de arquivos é usado para arquivos de áudio de nome gravado. O repositório de arquivos é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.
    
- **Armazenamento de usuários.** O armazenamento de usuários é usado para armazenar pins Skype for Business Server usuário. Os PINs estão em hash. O repositório de usuário é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.
    
- **Office Web Apps Server.** Para usar recursos de webconferência, os administradores devem instalar Office Web Apps Server e eles devem configurar o Skype for Business Server para se comunicar com o Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Políticas de conferência

Para impor as políticas da sua organização e controlar o uso da largura de banda, você pode definir políticas para os tipos de reuniões que os usuários podem organizar. Você pode definir uma ampla variedade de políticas de conferência e atribuí-las a usuários individuais e grupos de usuários. Você também pode definir políticas que governam conversas ponto a ponto. Para obter detalhes sobre como definir políticas de conferência, consulte [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Para obter detalhes sobre o gerenciamento de largura de banda, consulte [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Suporte para grandes reuniões

O tamanho das reuniões que Skype for Business Server pode suportar depende se a conferência está hospedada em um pool compartilhado ou dedicado:
  
- Em um pool compartilhado, Skype for Business Server pode hospedar reuniões com até 250 usuários. Um pool compartilhado é um pool que hospeda todas as Skype for Business Server de trabalho, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice. 
    
- Em um pool dedicado, Skype for Business Server pode dar suporte a reuniões com até 1.000 participantes usando conferência web e áudio/vídeo (A/V), incluindo o compartilhamento de PowerPoint apresentações. Esse suporte requer um pool dedicado configurado para dar suporte a grandes reuniões e gerenciados de forma a garantir a hospedagem de apenas uma única grande reunião por vez. 
    
Para obter mais informações sobre como gerenciar grandes reuniões, consulte [Plan for large meetings in Skype for Business Server](large-meetings.md).
  
Se sua organização exigir recursos de reunião maiores, considere a implementação de um ambiente híbrido que aproveite o Reunião do Skype Broadcast, um serviço online que faz parte do Microsoft 365 e Office 365. Reunião do Skype Transmissão permite que os usuários hospedem e transdiem reuniões para grandes audiências online de até 10.000 participantes. O uso do Reunião do Skype Broadcast exige que Skype for Business Server já sejam configurados em uma instalação híbrida com uma organização de Microsoft 365 ou Office 365 de produção. Todos os usuários devem ter um locatário online estabelecido como um pré-requisito. Se você estiver interessado em implantar uma solução híbrida que possa tirar proveito Reunião do Skype Transmissão, consulte [Configure your on-premises deployment for Reunião do Skype Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinar as necessidades de suas organizações

Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista a seguir orienta você pelo processo de planejamento de conferência para determinar quais recursos de conferência você deve implantar, com base nos requisitos da sua organização.
  
> [!NOTE]
> Ao habilitar a conferência na implantação, você habilita automaticamente a conferência web e A/V. No entanto, você pode desabilitar recursos específicos configurando políticas de conferência conforme descrito anteriormente neste tópico. 
  
- **Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**
    
    Em caso afirmado, você deve habilitar a conferência para seu pool de Front-End usando a Ferramenta de Planejamento ou usando o Construtor de Topologias. Para obter mais informações, [consulte Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    O compartilhamento de aplicativo requer e usa mais largura de banda do que a colaboração em documentos. Skype for Business Server fornece um mecanismo de throttling para controlar cada sessão de compartilhamento de aplicativos. Por padrão, isso é definido como 1,5 KB por segundo para cada sessão. Se você não quiser habilitar o compartilhamento de aplicativos, mas quiser a colaboração de documentos, poderá habilitar a conferência e usar políticas de conferência para desabilitar o compartilhamento de aplicativos. Para obter detalhes sobre como configurar políticas de conferência, consulte [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Para permitir que os usuários compartilhem PowerPoint apresentações, você precisa configurar Office Web Apps Server. Para obter detalhes sobre como configurar Office Web Apps Server, consulte [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Deseja habilitar a conferência de áudio e vídeo?**
    
    Em caso afirmado, você deve habilitar a conferência para seu pool de Front-End usando a Ferramenta de Planejamento ou usando o Construtor de Topologias. Para obter mais informações, [consulte Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    A conferência de áudio e vídeo exige e usa mais largura de banda de rede do que a webconferência (que inclui colaboração de documentos e compartilhamento de aplicativos). Se você não quiser habilitar a conferência de áudio e vídeo, mas deseja habilitar a webconferência, você pode habilitar a conferência e usar políticas de conferência para desabilitar conferências A/V.
    
    Se você quiser habilitar conferências de áudio, mas não conferências de vídeo, poderá habilitar conferências A/V e usar políticas de conferência para evitar conferências de vídeo. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V. 
    
    Para obter mais informações sobre como configurar políticas de conferência, consulte [Manage conferencing policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > Enterprise Voice não é necessário para você usar a conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio a suas conferências se tiverem dispositivos de áudio, mesmo que você use um sistema PBX como sua solução de telefone. 
  
- **Deseja permitir que os usuários ingressem na parte de áudio de conferências quando usam um telefone PSTN?**
    
    Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.
    
    A conferência discagem é um recurso opcional que você pode configurar ao implantar Skype for Business Server conferência. Embora a conferência discado use alguns dos mesmos componentes que Enterprise Voice usa, você pode implantar a conferência discagem mesmo que você não implante Enterprise Voice. A conferência de discagem suporta aos usuários corporativos e anônimos. Para obter mais informações sobre como configurar a conferência discagem para usuários corporativos e anônimos, consulte [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) and [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Deseja habilitar usuários externos com clientes Skype for Business ingressar em conferências?**
    
    Ao permitir a participação externa em reuniões, você maximiza seu investimento em Skype for Business Server. Os usuários externos podem incluir:
    
  - **Usuários remotos.** Os próprios usuários da sua organização, quando eles estão trabalhando fora de seus firewalls e estão usando seus laptops ou outros Skype for Business Server dispositivos.
    
  - **Usuários Federados.** Usuários de empresas com quem você trabalha que também Skype for Business Server. Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas.
    
  - **Usuários anônimos.** Outros usuários externos que são convidados especificamente por seus usuários para participar de conferências específicas. O organizador de uma reunião em sua empresa pode enviar um convite por email de uma conferência para um usuário externo. O email inclui um link no qual o usuário externo pode clicar para ingressar na conferência.
    
    Se você quiser permitir usuários externos, precisará implantar Servidores de Borda. Além disso, com os Servidores de Borda implantados, você pode criar relações federadas com outras organizações, como seus clientes ou fornecedores, e os usuários dessas organizações podem colaborar mais facilmente com seus usuários.
    
    Para obter detalhes sobre como implantar Servidores de Borda, consulte Plan for Edge Servers and Deploy Edge Servers. Para obter detalhes sobre a habilitação do acesso externo para Office Web Apps Server, consulte [Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Você deseja controlar os clientes que podem participar de Skype for Business Server reuniões?**
    
    Em caso afirmativo, você deve configurar a página de ingresso em reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis. Sempre que um usuário clica em um link para ingressar em uma reunião agendada, Skype for Business Server detecta se um cliente já está instalado no computador. Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso em reunião, que contém links para clientes alternativos. A página de junção de reunião sempre contém a opção de uso Skype for Business Web App. Além dessa opção, você pode decidir se deve incluir links para o Participante e versões anteriores do Communicator. 
    

