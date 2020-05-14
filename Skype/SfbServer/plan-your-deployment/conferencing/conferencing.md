---
title: Planejar a conferência no Skype for Business Server
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
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Resumo: Leia este tópico para saber mais sobre os recursos e recursos de conferência no Skype for Business Server.'
ms.openlocfilehash: 1c67eecda6c7691dfbb042f4743733b73864a426
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221161"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planejar a conferência no Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre recursos de conferência e recursos no Skype for Business Server.
  
A conferência no Skype for Business Server permite que os usuários encontrem e armazenem conferências online usando seu cliente Skype for Business, em vez de todos se juntarem na mesma sala. Os participantes da reunião podem se conectar a uma reunião com seu cliente Skype for Business para uma experiência de áudio e vídeo completa, ou discar para uma conferência usando um telefone. As conferências também oferecem suporte a mensagens instantâneas, compartilhamento de área de trabalho e aplicativos e quadros brancos interativos.
  
Este tópico inclui as seguintes seções:
  
- Recursos e recursos de conferência
    
- Componentes de conferência
    
- Políticas de conferência
    
- Suporte para grandes reuniões
    
- Determinar as necessidades da sua organização
    
## <a name="conferencing-features-and-capabilities"></a>Recursos e recursos de conferência

Há quatro tipos de conferência disponíveis no Skype for Business Server: webconferência, conferência de áudio e vídeo (A/V), conferência discada e conferência de mensagens instantâneas (IM). 
  
Você pode optar por habilitar todos os tipos de conferência ou usar apenas um tipo, dependendo de suas necessidades. Por exemplo, você pode habilitar todos os tipos, incluindo conferência discada, para permitir que usuários que não podem ingressar em uma conferência com um cliente Skype for Business chamem e participem do áudio da reunião de um telefone. Quando você implanta o Skype for Business Server, os recursos de conferência de mensagens instantâneas são implantados automaticamente; Você especifica se deseja implantar a Web, A/V e a conferência discada usando o construtor de topologias. Para obter mais informações, consulte [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
As subseções a seguir descrevem os recursos e as funcionalidades de cada tipo de conferência.
  
### <a name="web-conferencing"></a>Webconferência

A Webconferência permite que os participantes da reunião colaborem em documentos compartilhados durante a reunião e que o apresentador de reunião Compartilhe aplicativos por meio do cliente Skype for Business. A Webconferência fornece os seguintes recursos: 
  
- **Quadro de comunicações e anotações.** Um quadro de comunicações é uma tela em branco que pode ser usada para colaboração com texto, tinta, desenhos e imagens. As anotações feitas nos quadros de comunicações podem ser vistas por todos os participantes da reunião. O recurso de quadro de comunicações aprimora a colaboração ao permitir que os participantes da reunião discutam ideias, façam brainstorm, anotações e outros.
    
- **Sondagem.** O recurso de sondagem aprimora a colaboração, permitindo que os apresentadores determinem rapidamente as preferências dos participantes. Durante reuniões online e conversas, os apresentadores podem utilizar a sondagem para obter respostas anônimas dos participantes. Todos os apresentadores podem ver os resultados e podem escondê-los ou mostrá-los aos presentes.
    
- **Compartilhamento de aplicativos e compartilhamento de área de trabalho.** Durante uma conferência, o apresentador de reunião pode compartilhar a área de trabalho inteira, um aplicativo individual ou monitores individuais em um ambiente de vários monitores. Além de apenas exibir o conteúdo, outros participantes da conferência podem solicitar o controle da tela do apresentador e, com a permissão, interagir com o conteúdo (incluindo rolagem e edição). Os participantes da reunião também podem assumir o controle como apresentador e começar a compartilhar o conteúdo durante a reunião.
    
- **Compartilhamento do PowerPoint.** Permite que os usuários compartilhem apresentações do PowerPoint na reunião por meio de um servidor do Office Web Apps, que permite:
    
  - Exibições de alta resolução e suporte para recursos do PowerPoint, como animações, transições de slides e vídeo incorporado.
    
  - Os dispositivos móveis podem acessar essas apresentações.
    
  - Os usuários com as permissões apropriadas podem rolar por uma apresentação do PowerPoint independente da própria apresentação. Por exemplo, enquanto Ken está apresentando sua apresentação de slides, Patricia pode ver qualquer slide que desejar sem afetar a apresentação de Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferência de áudio e vídeo

A conferência de áudio e vídeo permite áudio e vídeo na reunião. O áudio permite que os participantes conversem uns com os outros como se estivessem na mesma sala. Vídeo permite a exibição de vídeo no cliente Skype for Business de qualquer participante ou apresentadores que ingressam na reunião com um dispositivo de conferência ou imagem da Web que oferece suporte a vídeo.
  
 O Skype for Business Server fornece vários recursos que os usuários podem usar para configurar a experiência de conferência de áudio para o usuário, incluindo o seguinte:
  
- **Audiência sem som.** O apresentador pode usar essa configuração para retirar o áudio de todos os participantes na conferência e colocar a conferência em um estado no qual aqueles que não forem apresentadores não poderão ativar o áudio.
    
- **Anúncios de entrada/saída de conferência.** Se você ativou a conferência discada, os apresentadores podem usar essa configuração para ligar ou desligar os anúncios de entrada/saída para minimizar distrações, enquanto a conferência estiver em andamento.
    
- **Adição de um usuário por discagem externa.** Apresentadores e participantes que receberam permissão, podem adicionar números PSTN às conferências e fazer com que a conferência disque para esses números.
    
  O Skype for Business Server fornece vários recursos que os usuários podem usar para configurar a experiência de conferência de vídeo para o usuário, incluindo o seguinte:
  
- **Modo de exibição de galeria.** Em conferências de vídeo que tenham mais que duas pessoas, os usuários podem automaticamente ver todos na conferência. Se a conferência tiver mais que cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida. O vídeo de vários participantes está ativado como padrão.
    
- **Vídeo panorâmico.** Se um dispositivo de conferência de vídeo de mesa redonda estiver instalado na sala de conferências, esse recurso fornecerá uma visão de 360 graus da sala de conferência. A faixa de vídeo panorâmico está disponível apenas em dispositivos de mesa redonda.
    
- **Modo de vídeo somente para apresentador.** Os apresentadores podem configurar a reunião de forma que apenas o vídeo deles seja exibido. Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e travadas para diferentes fontes. Esse modo também é aplicado ao vídeo capturado e fornecido por dispositivos de mesa redonda.
    
- **Spotlight em vídeo.** Os apresentadores podem configurar a reunião para que apenas o vídeo de um participante selecionado seja visto pelos outros participantes na conferência. Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos de mesa redonda de vídeo panorâmico.
    
### <a name="dial-in-conferencing"></a>Conferência discada

A conferência discada permite que os participantes da reunião ingressem na parte de áudio de uma reunião ligando para a reunião a partir de um telefone. A conferência discada é um subconjunto da conferência de áudio e exige configuração adicional. Para obter mais informações sobre conferência discada, consulte [Plan for dial-in Conferencing in Skype for Business Server](dial-in-conferencing.md) e [Configure dial-in Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferência de mensagens instantâneas

A conferência de mensagens instantâneas (IM) permite que mais de duas partes se comuniquem em uma única sessão de IM. Para obter detalhes sobre a conferência de mensagens instantâneas, consulte [Plan for Instant Messaging and Presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferência

Os componentes que oferecem suporte a recursos de conferência incluem o seguinte:
  
- **Serviço de aplicativo.** O serviço de aplicativo fornece uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicação unificada (UC). A conferência discada usa dois aplicativos de comunicação unificada que exigem o serviço de aplicativo: o atendedor de conferência e o comunicado de conferência. O serviço de aplicativo é instalado e ativado por padrão em todos os servidores front-end em um pool de front-ends. Ele também é instalado em cada servidor Standard Edition para habilitar e configurar a conferência discada.
    
- **Aplicativo de atendedor de conferência.** O aplicativo de atendedor de conferência é um aplicativo de comunicações unificado que aceita chamadas PSTN (rede telefônica pública comutada), reproduz prompts e une as chamadas a uma conferência A/V. O aplicativo atendedor de conferência é instalado e ativado por padrão quando você habilita a conferência discada.
    
- **Aplicativo comunicado de conferência.** O aplicativo de anúncio de conferência é um aplicativo de comunicações unificado que reproduz tons e avisa para os participantes de PSTN em determinadas ações, como quando os participantes ingressam ou saem de uma conferência, os participantes são habilitados ou desativados, alguém entra no lobby da conferência ou a conferência é bloqueada ou desbloqueada. O aplicativo de anúncio de conferência também suporta comandos DTMF (multifrequência de tom dual) do teclado numérico do telefone. O aplicativo comunicado de conferência é automaticamente instalado e ativado por padrão quando você habilita a conferência discada.
    
- **Página de configurações de conferência discada.** A página de configurações de conferência discada exibe os números de discagem de conferência com seus idiomas disponíveis, as informações de conferência atribuídas (ou seja, para reuniões que não precisam ser agendadas) e para o gerenciamento de DTMF de conferência e oferece suporte ao gerenciamento de PIN (número de identificação pessoal) e informações de conferência atribuídas. A página de configurações de conferência discada é instalada automaticamente como parte dos serviços Web.
    
- **Servidor de mediação e gateway PSTN.** A conferência discada requer um servidor de mediação para converter a sinalização (e mídia em algumas configurações) entre o Skype for Business Server e o gateway PSTN e um gateway PSTN para converter a sinalização e mídia entre o servidor de mediação e o gateway PSTN. Para a Conferência de Discagem, você deve implantar pelo menos um Servidor de Mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
  > [!NOTE]
  > Se você também estiver implantando o Enterprise Voice, o servidor de mediação e os gateways PSTN serão parte da implantação do Enterprise Voice. Se você não estiver implantando o Enterprise Voice, será necessário implantar pelo menos um Servidor de Mediação e um gateway PSTN, IP-PBX ou SBC para a conferência de discagem. 
  
- **Repositório de arquivos.** O repositório de arquivos é usado para arquivos de áudio de nome gravado. O repositório de arquivos é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.
    
- **Repositório do usuário.** O repositório do usuário é usado para armazenar PINs do usuário do Skype for Business. Os PINs estão em hash. O repositório de usuário é um componente padrão em cada implantação Enterprise Edition ou Standard Edition.
    
- **Servidor do Office Web Apps.** Para usar os recursos de conferência da Web, os administradores devem instalar o Office Web Apps Server e devem configurar o Skype for Business Server para se comunicar com o servidor do Office Web Apps.
    
## <a name="conferencing-policies"></a>Políticas de conferência

Para impor as políticas da sua organização e controlar o uso da largura de banda, você pode definir políticas para os tipos de reuniões que os usuários podem organizar. Você pode definir uma ampla variedade de políticas de conferência e atribuí-las a usuários individuais e grupos de usuários. Você também pode definir políticas que regem conversas ponto a ponto. Para obter detalhes sobre como definir políticas de conferência, consulte [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Para obter detalhes sobre o gerenciamento de largura de banda, consulte [Plan for Call Admission Control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Suporte para grandes reuniões

O tamanho das reuniões que o Skype for Business Server pode dar suporte depende se a conferência está hospedada em um pool compartilhado ou dedicado:
  
- Em um pool compartilhado, o Skype for Business Server pode hospedar reuniões com até 250 usuários. Um pool compartilhado é um pool que hospeda todas as cargas de trabalho do Skype for Business Server, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice. 
    
- Em um pool dedicado, o Skype for Business Server pode dar suporte a reuniões com até 1000 participantes usando a conferência da Web e áudio/vídeo (A/V), incluindo o compartilhamento de apresentações do PowerPoint. Esse suporte requer um pool dedicado configurado para dar suporte a grandes reuniões e gerenciados de forma a garantir a hospedagem de apenas uma única reunião de grande porte. 
    
Para obter mais informações sobre como gerenciar grandes reuniões, consulte [Plan for large encontros in Skype for Business Server](large-meetings.md).
  
Se sua organização requer recursos maiores de reunião, você deve considerar a implementação de um ambiente híbrido que aproveita a transmissão de reunião do Skype, um serviço online que faz parte do Microsoft 365 e do Office 365. A transmissão de reunião do Skype permite que os usuários hospedem e transmitam reuniões para grandes audiências online de até 10.000 participantes. O uso da transmissão de reunião do Skype exige que o Skype for Business Server já esteja configurado em uma instalação híbrida com uma organização de produção Microsoft 365 ou do Office 365. Todos os usuários devem ter um locatário online estabelecido como um pré-requisito. Se você estiver interessado em implantar uma solução híbrida que possa aproveitar a transmissão de reunião do Skype, confira [configurar sua implantação local para transmissão de reunião do Skype](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determinar suas necessidades de organizações

Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista a seguir orienta o processo de planejamento de conferência para determinar quais recursos de conferência você deve implantar, com base nos requisitos da sua organização.
  
> [!NOTE]
> Ao habilitar a conferência na implantação, você habilita automaticamente as conferências da Web e de A/V. No entanto, você pode desabilitar recursos específicos Configurando políticas de conferência, conforme descrito anteriormente neste tópico. 
  
- **Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**
    
    Em caso afirmativo, você deve habilitar a conferência para seu pool de front-ends usando a ferramenta de planejamento ou usando o construtor de topologias. Para obter mais informações, consulte [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    O compartilhamento de aplicativo requer e usa mais largura de banda do que a colaboração em documentos. O Skype for Business Server fornece um mecanismo de limitação para controlar cada sessão de compartilhamento de aplicativos. Por padrão, isso é definido como 1,5 KB por segundo para cada sessão. Se não quiser habilitar o compartilhamento de aplicativos, mas quiser a colaboração de documentos, você poderá habilitar a conferência e usar políticas de conferência para desabilitar o compartilhamento de aplicativos. Para obter detalhes sobre como configurar políticas de conferência, consulte [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Para permitir que os usuários compartilhem apresentações do PowerPoint, você precisa configurar o servidor do Office Web Apps. Para obter detalhes sobre como configurar o servidor do Office Web Apps, consulte [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Você deseja habilitar a conferência de áudio e vídeo?**
    
    Em caso afirmativo, você deve habilitar a conferência para seu pool de front-ends usando a ferramenta de planejamento ou usando o construtor de topologias. Para obter mais informações, consulte [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    A conferência de áudio e vídeo requer e usa mais largura de banda da rede que a Webconferência (que inclui colaboração de documentos e compartilhamento de aplicativos). Se você não deseja habilitar a conferência de áudio e vídeo, mas deseja habilitar a conferência da Web, é possível habilitar a conferência e usar políticas de conferência para desabilitar conferências A/V.
    
    Se você quiser habilitar conferências de áudio, mas não conferências de vídeo, poderá habilitar A conferência A/V e usar políticas de conferência para evitar videoconferências. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V. 
    
    Para obter mais informações sobre como configurar políticas de conferência, consulte [Manage Conferencing Policies in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > O Enterprise Voice não é necessário para usar A conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio a suas conferências se tiverem dispositivos de áudio, mesmo que você use um sistema PBX como sua solução de telefone. 
  
- **Deseja permitir que os usuários ingressem na parte de áudio de conferências quando usam um telefone PSTN?**
    
    Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.
    
    A conferência discada é um recurso opcional que você pode configurar ao implantar a conferência do Skype for Business Server. Embora a conferência discada use alguns dos mesmos componentes usados pelo Enterprise Voice, você pode implantar a conferência discada mesmo se não implantar o Enterprise Voice. A conferência de discagem suporta aos usuários corporativos e anônimos. Para obter mais informações sobre como configurar a conferência discada para usuários corporativos e anônimos, consulte [Deploy Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) e [Configure dial-in Conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Deseja permitir que usuários externos com clientes do Skype for Business ingressem em conferências?**
    
    Ao permitir a participação externa em reuniões, você maximiza seu investimento no Skype for Business Server. Os usuários externos podem incluir:
    
  - **Usuários remotos.** Os próprios usuários da sua organização, quando estão trabalhando fora de seus firewalls e estão usando seus laptops ou outros dispositivos do Skype for Business Server.
    
  - **Usuários federados.** Usuários de empresas com as quais você trabalha e que também executam o Skype for Business Server. Para permitir que os usuários contatem facilmente esses usuários, você pode criar relacionamentos federados com essas empresas.
    
  - **Usuários anônimos.** Outros usuários externos que são convidados especificamente por seus usuários para participar de conferências específicas. O organizador de uma reunião em sua empresa pode enviar um convite por email de uma conferência para um usuário externo. O email inclui um link no qual o usuário externo pode clicar para ingressar na conferência.
    
    Se você quiser permitir usuários externos, será necessário implantar servidores de borda. Além disso, com os servidores de Borda implantados, você pode criar relacionamentos federados com outras organizações, como seus clientes ou fornecedores, e os usuários dessas organizações podem colaborar mais facilmente com seus usuários.
    
    Para obter detalhes sobre como implantar servidores de borda, consulte Planejar servidores de borda e implantar servidores de borda. Para obter detalhes sobre como habilitar o acesso externo para o servidor do Office Web Apps, consulte [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Você deseja controlar os clientes que podem ingressar em reuniões do Skype for Business Server?**
    
    Em caso afirmativo, você deve configurar a página de ingresso em reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis. Cada vez que um usuário clica em um link para ingressar em uma reunião agendada, o Skype for Business Server detecta se um cliente já está instalado no computador. Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso em reunião, que contém links para clientes alternativos. A página de ingresso na reunião sempre contém a opção para usar o Skype for Business Web App. Além dessa opção, você pode decidir se deseja incluir links para o participante e versões anteriores do Communicator. 
    

