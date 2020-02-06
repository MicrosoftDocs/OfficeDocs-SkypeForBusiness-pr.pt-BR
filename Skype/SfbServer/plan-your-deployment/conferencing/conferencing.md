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
description: 'Resumo: Leia este tópico para saber mais sobre recursos de conferência e recursos no Skype for Business Server.'
ms.openlocfilehash: f91c815cf0b5d0b69ad5815157cba7a56bb28307
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815999"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planejar a conferência no Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre recursos de conferência e recursos no Skype for Business Server.
  
A conferência no Skype for Business Server permite que os usuários cumpram e participem de conferências online usando o cliente Skype for Business, em vez de todos se reunirem na mesma sala. Os participantes da reunião podem se conectar a uma reunião com o cliente Skype for Business para obter uma experiência completa de áudio e vídeo ou discar para uma conferência usando um telefone. As conferências também são compatíveis com mensagens instantâneas, compartilhamento da área de trabalho e de aplicativos, e quadros de comunicação interativos.
  
Este tópico inclui as seguintes seções:
  
- Recursos e funcionalidades da conferência
    
- Componentes de conferência
    
- Políticas de conferência
    
- Suporte a reuniões grandes
    
- Determinação das necessidades da sua organização
    
## <a name="conferencing-features-and-capabilities"></a>Recursos e funcionalidades da conferência

Há quatro tipos de conferência disponíveis no Skype for Business Server: conferência via Web, conferência de áudio e vídeo (A/V), conferência discada e conferência de mensagem instantânea. 
  
Você pode optar por habilitar todos os tipos de conferências ou usar apenas um deles, dependendo de suas necessidades. Por exemplo, você pode habilitar todos os tipos, incluindo a conferência discada, para permitir que os usuários que não conseguem ingressar em uma conferência com um cliente Skype for Business possam fazer chamadas e participar do áudio da reunião a partir de um telefone. Ao implantar o Skype for Business Server, os recursos de conferência de mensagem instantânea são automaticamente implantados; Você especifica se deseja implantar a Web, A/V e uma conferência discada usando o construtor de topologias. Para obter mais informações, consulte [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Nas subseções a seguir, estão descritos os recursos e as funcionalidades de cada tipo de conferência.
  
### <a name="web-conferencing"></a>Webconferência

A Webconferência permite que os participantes da reunião colaborem em documentos compartilhados durante a reunião e para o apresentador de reunião compartilhar aplicativos por meio do cliente Skype for Business. A webconferência oferece os seguintes recursos: 
  
- **Quadro de comunicações e anotações.** O quadro de comunicações é uma tela em branco que pode ser usada para colaboração com texto, tinta, desenhos e imagens. As anotações feitas nos quadros de comunicações podem ser vistas por todos os participantes da reunião. O recurso de quadro de comunicações aprimora a colaboração, pois habilita os participantes da reunião a discutirem ideias, fazerem brainstorming, anotações e muito mais.
    
- **Sondagem.** O recurso de sondagem aprimora a colaboração habilitando apresentadores para determinar rapidamente as preferências dos participantes. Durante reuniões online e conversas, os apresentadores podem utilizar a sondagem para obter respostas anônimas dos participantes. Todos os apresentadores podem ver os resultados e optar por escondê-los ou mostrá-los aos presentes.
    
- **Compartilhamento de aplicativos e de área de trabalho.** Durante uma conferência, o apresentador de reunião pode compartilhar toda a área de trabalho, um aplicativo individual ou monitores individuais em um ambiente com vários monitores. Além de simplesmente visualizar o conteúdo, outros participantes da conferência podem solicitar o controle da tela do apresentador e, mediante permissão, interagir com o conteúdo (inclusive com rolagem e edição). Os participantes da reunião também podem assumir como apresentadores e compartilhar conteúdo durante a reunião.
    
- **Compartilhamento do PowerPoint.** Permite que os usuários compartilhem apresentações do PowerPoint na reunião através de um servidor do Office Web Apps, que permite:
    
  - Exibições de alta resolução e suporte às funcionalidades do PowerPoint, como animações, transições de slide e vídeo incorporado.
    
  - Dispositivos móveis podem acessar essas apresentações.
    
  - Usuários com os privilégios adequados podem rolar uma apresentação do PowerPoint independente da apresentação propriamente dita. Por exemplo, enquanto Ken está fazendo a apresentação dele, Heidi pode olhar qualquer slide que desejar sem afetar a apresentação do Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferência de áudio e vídeo

A conferência de áudio e vídeo permite sons e imagem na reunião. O áudio permite que os participantes falem uns com os outros, como se estivessem na mesma sala. Vídeo permite a exibição de vídeo no cliente do Skype for Business de quaisquer participantes ou apresentadores que ingressam na reunião com um dispositivo de webcam ou de conferência da Web com suporte a vídeo.
  
 O Skype for Business Server fornece vários recursos que os usuários podem usar para configurar a experiência de audioconferência para o usuário, incluindo o seguinte:
  
- **Público mudo.** O apresentador pode usar essa configuração para retirar o áudio de todos os participantes na conferência e colocá-la em um estado no qual aqueles que não forem apresentadores não poderão ativar o áudio de si próprios.
    
- **Comunicados de entrada/saída de conferência.** Se você tiver habilitado a conferência discada, os apresentadores poderão usar esta configuração para ligar ou desligar os anúncios de entrada/saída e minimizar distrações enquanto a conferência estiver em andamento.
    
- **Adicionando um usuário através da discagem.** Os apresentadores e os participantes que receberam permissão podem adicionar números PSTN às conferências e fazer com que a conferência disque para esses números.
    
  O Skype for Business Server oferece vários recursos que os usuários podem usar para configurar a experiência de videoconferência para o usuário, incluindo o seguinte:
  
- **Modo de exibição de galeria.** Em conferências de vídeo que tenham mais de duas pessoas, os usuários automaticamente veem todos na conferência. Se a conferência tiver mais de cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida. O vídeo de vários participantes está ativado como padrão.
    
- **Vídeo panorâmico.** Se um dispositivo de conferência de vídeo RoundTable estiver instalado na sala de conferências, esse recurso fornecerá uma visão de 360 graus da sala. A faixa de vídeo panorâmico está disponível apenas com dispositivos RoundTable.
    
- **Modo de vídeo do apresentador somente.** Os apresentadores podem configurar a reunião de forma que apenas o vídeo deles seja exibido. Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e bloqueadas para diferentes fontes. Esse modo também se aplica ao vídeo capturado e fornecido por dispositivos RoundTable.
    
- **Vídeo em destaque.** Os apresentadores podem configurar a reunião para que apenas o vídeo de um participante selecionado que seja a fonte do vídeo seja visto pelos outros participantes na conferência. Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos RoundTable para vídeo panorâmico.
    
### <a name="dial-in-conferencing"></a>Conferência discada

A conferência discada permite que os participantes da reunião ingressem na parte de áudio de uma reunião ligando para a reunião a partir de um telefone. A conferência discada é um subconjunto da conferência de áudio e exige configuração adicional. Para obter mais informações sobre a conferência discada, consulte [planejar a conferência discada no Skype for Business Server](dial-in-conferencing.md) e [Configurar a conferência discada no Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferência por mensagens instantâneas

A conferência por mensagens instantâneas (IM) permite que mais de dois participantes se comuniquem em uma única sessão de mensagens instantâneas. Para obter detalhes sobre a conferência de mensagem instantânea, consulte [planejar mensagens instantâneas e presença no Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferência

Os componentes compatíveis com os recursos de conferência incluem o seguinte:
  
- **Serviço de aplicativo.** O serviço de aplicativo cria uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicações unificadas (UC). A conferência discada usa dois aplicativos de UC que requerem o serviço de aplicativo: Atendedor de Conferência e Comunicado de Conferência. O serviço de aplicativo é instalado e ativado por padrão em todos os servidores front-end em um pool de front-ends. Ele também é instalado em cada servidor Standard Edition para habilitar e configurar conferência discada.
    
- **Aplicativo Atendedor de Conferência.** O aplicativo Atendedor de Conferência é um aplicativo de comunicações unificadas que aceita chamadas de PSTN (Rede Telefônica Pública Comutada), reproduz prompts e ingressa em chamadas de conferências A/V. O aplicativo Atendedor de Conferência é instalado e ativado por padrão ao habilitar a conferência discada.
    
- **Aplicativo Comunicado de Conferência.** O Comunicado de Conferência é um aplicativo de comunicações unificadas que emite sons e prompts para participantes de PSTN em certas ações, como quando os participantes ingressam ou saem de uma conferência, são colocados e retirados do mudo, quando alguém entra no lobby da conferência ou quando a conferência é bloqueada ou desbloqueada. O aplicativo Comunicado de Conferência também é compatível com comandos de multifrequência de tom dual (DTMF) do teclado do telefone. O aplicativo Comunicado de Conferência é automaticamente instalado e habilitado por padrão quando você habilita a conferência discada.
    
- **Página Configurações da Conferência Discada.** A página de Configurações da Conferência Discada exibe os números de discagem da conferência, com os idiomas disponíveis, informações de atribuição da conferência (ou seja, para reuniões que não precisam ser agendadas) e controles DTMF durante a conferência, além de oferecer suporte ao gerenciamento do número de identificação pessoal (PIN) e informações atribuídas sobre a conferência. A página de Configurações da Conferência Discada é automaticamente instalada como parte dos serviços da Web.
    
- **Servidor de mediação e gateway PSTN.** A conferência discada exige que um servidor de mediação traduza sinalização (e mídia em algumas configurações) entre o Skype for Business Server e o gateway PSTN e um gateway PSTN para traduzir a sinalização e a mídia entre o servidor de mediação e o gateway PSTN . Para conferência discada, você deve implantar pelo menos um servidor de mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
  > [!NOTE]
  > Se você também estiver implantando o Enterprise Voice, o servidor de mediação e os gateways PSTN fazem parte da implantação do Enterprise Voice. Se não estiver implantando o Enterprise Voice, você precisará implantar pelo menos um servidor de mediação e pelo menos um gateway PSTN, PBX IP ou SBC para conferência discada. 
  
- **Repositório de arquivos.** O Repositório de arquivos é usado para arquivos de áudio de nomes gravados. O Repositório de Arquivos é um componente padrão de todas as implantações do Enterprise Edition ou Standard Edition.
    
- **Armazenamento de usuários.** O repositório de usuários é usado para armazenar PINs do usuário do Skype for Business Server. Os PINs são marcados por hash. O armazenamento de Usuários é um componente padrão em todas as implantações de Enterprise Edition ou Standard Edition.
    
- **Servidor do Office Web Apps.** Para poder usar os recursos de webconferência, os administradores devem instalar o Office Web Apps Server e devem configurar o Skype for Business Server para se comunicar com o servidor do Office Web Apps.
    
## <a name="conferencing-policies"></a>Políticas de conferência

Para impor as políticas da sua organização e controlar o uso da largura de banda, você pode definir políticas para os tipos de reuniões que os usuários podem organizar. É possível definir uma ampla variedade de políticas de conferência e atribuí-las a cada usuário e grupo de usuários. Você também pode definir políticas que regem as conversas ponto a ponto. Para obter detalhes sobre como definir políticas de conferência, consulte [gerenciar políticas de conferência no Skype for Business Server](../../manage/conferencing/conferencing-policies.md). Para obter detalhes sobre o gerenciamento de largura de banda, consulte [planejar o controle de admissão de chamadas no Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Suporte a reuniões grandes

O tamanho das reuniões que o Skype for Business Server pode suportar depende se a conferência está hospedada em um pool compartilhado ou dedicado:
  
- Em um pool compartilhado, o Skype for Business Server pode hospedar reuniões com até 250 usuários. Um pool compartilhado é um pool que hospeda todas as cargas de trabalho do Skype for Business Server, incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice. 
    
- Em um pool dedicado, o Skype for Business Server pode dar suporte a reuniões com até 1000 participantes usando a conferência da Web e de áudio/vídeo (A/V), incluindo o compartilhamento de apresentações do PowerPoint. Esse suporte exige um pool dedicado, configurado para suportar grandes reuniões e gerenciado de forma a garantir a hospedagem de apenas uma grande reunião por vez. 
    
Para obter mais informações sobre como gerenciar reuniões grandes, consulte [planejar reuniões grandes no Skype for Business Server](large-meetings.md).
  
Se a sua organização requer recursos de reunião maiores, você deve considerar a implementação de um ambiente híbrido que aproveita a transmissão de reunião do Skype, um serviço online que faz parte do Office 365. A Transmissão de Reunião do Skype habilita os usuários a hospedarem e divulgarem a grandes públicos online reuniões com até 10.000 participantes. O uso de Transmissão de Reunião do Skype exige que o Skype for Business Server esteja configurado como híbrido em um locatário do Office 365 de produção. O pré-requisito é que todos os usuários tenham um locatário online. Se você estiver interessado em implantar uma solução híbrida que possa tirar proveito da Transmissão de Reunião do Skype, consulte [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determine as necessidades da sua organização

Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista a seguir orienta você pelo processo de planejamento de conferência para determinar quais recursos de conferência você deve implantar com base nos requisitos da sua organização.
  
> [!NOTE]
> Ao habilitar a conferência na implantação, você automaticamente habilita webconferência e conferência A/V. No entanto, é possível desabilitar características específicas ao configurar políticas de conferência conforme descrito anteriormente neste tópico. 
  
- **Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**
    
    Em caso positivo, você precisará habilitar a conferência para seu pool de Front-Ends usando a Ferramenta de Planejamento ou o Construtor de Topologias. Para obter mais informações, consulte [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    O compartilhamento de aplicativos requer e usa mais largura de banda que a colaboração em documentos. O Skype for Business Server oferece um mecanismo de limitação para controlar cada sessão de compartilhamento de aplicativo. Por padrão, isso é definido como 1,5 KB por segundo para cada sessão. Se você não quiser habilitar o compartilhamento de aplicativos, mas quiser a colaboração de documentos, poderá habilitar a conferência e usar políticas de conferência para desabilitar o compartilhamento de aplicativos. Para obter detalhes sobre como configurar políticas de conferência, consulte [gerenciar políticas de conferência no Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Para habilitar os usuários a compartilharem apresentações do PowerPoint, é preciso configurar o Servidor do Office Web Apps. Para obter detalhes sobre como configurar o servidor do Office Web Apps, consulte [Configurar a integração com o servidor do Office Web Apps no Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Deseja habilitar a conferência de áudio e vídeo?**
    
    Em caso positivo, você precisará habilitar a conferência para seu pool de Front-Ends usando a Ferramenta de Planejamento ou o Construtor de Topologias. Para obter mais informações, consulte [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    A conferência A/V exige e usa mais largura de banda que a webconferência (que inclui a colaboração em documentos e o compartilhamento de aplicativos). Se você não quiser habilitar a conferência de áudio e vídeo, mas quiser habilitar a webconferência, poderá habilitar a conferência e usar as políticas para desabilitar conferências A/V.
    
    Se você quiser habilitar a conferência de áudio, mas não a conferência de vídeo, poderá habilitar a conferência A/V e usar políticas de conferência para impedir as conferências de vídeo. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V. 
    
    Para obter mais informações sobre como configurar políticas de conferência, consulte [gerenciar políticas de conferência no Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > O Enterprise Voice não é necessário para você usar a conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio às conferências, caso tenham dispositivos de áudio, mesmo que você use um sistema PBX como solução de telefonia. 
  
- **Deseja permitir que os usuários ingressem na parte de áudio de conferências ao usar um telefone PSTN?**
    
    Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.
    
    A conferência discada é um recurso opcional que você pode configurar ao implantar o Skype for Business Server conferências. Embora a conferência discada use alguns dos mesmos componentes do Enterprise Voice, você pode implantar a conferência discada mesmo se não implantar o Enterprise Voice. A conferência discada é compatível com usuários corporativos e anônimos. Para obter mais informações sobre como configurar a conferência discada para usuários corporativos e anônimos, consulte [implantar conferências no Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) e [Configurar a conferência discada no Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Deseja permitir que usuários externos com clientes Skype for Business ingressem nas conferências?**
    
    Ao permitir a participação externa em reuniões, você maximiza o investimento no Skype for Business Server. Entre os usuários externos podem estar:
    
  - **Usuários remotos.** Os próprios usuários da sua organização, quando estiverem trabalhando fora dos firewalls e estiverem usando seus laptops ou outros dispositivos do Skype for Business Server.
    
  - **Usuários federados.** Usuários de empresas com quem você trabalha com quem também executa o Skype for Business Server. Para habilitar que seus usuários entrem em contato facilmente com esses usuários, crie relacionamentos federados com essas empresas.
    
  - **Usuários anônimos.** Quaisquer outros usuários externos que são convidados especificamente por seus usuários para participar de conferências específicas. O organizador de uma reunião em sua empresa pode enviar um convite de uma conferência por email a um usuário externo. O email inclui um link no qual o usuário externo pode clicar para ingressar na conferência.
    
    Se quiser permitir usuários externos, você precisará implantar servidores de borda. Além disso, com os Servidores de Borda implantados, você pode criar relacionamentos federados com outras organizações, como clientes ou fornecedores, e os usuários dessas organizações poderão colaborar mais facilmente com seus usuários.
    
    Para obter detalhes sobre como implantar os Servidores de Borda, consulte Plano para Servidores de Borda e Implantar Servidores de Borda. Para obter detalhes sobre como habilitar o acesso externo para o Office Web Apps Server, consulte [Configurar a integração com o servidor do Office Web Apps no Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Você deseja controlar os clientes que podem ingressar em reuniões do Skype for Business Server?**
    
    Em caso afirmativo, você deve configurar a página de ingresso na reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis. Sempre que um usuário clica em um link para ingressar em uma reunião agendada, o Skype for Business Server detecta se um cliente já está instalado no computador. Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso na reunião, que contém links para clientes alternativos. A página Associação de reunião sempre contém a opção para usar o Skype for Business Web App. Além dessa opção, você pode decidir se deseja incluir links para o Atendedor e versões anteriores do Communicator. 
    

