---
title: Planejamento de conferência no Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 10add1ea-d693-406c-9dc9-853df0ab05da
description: 'Resumo: Leia este tópico para saber mais sobre os recursos de conferência e capacidades no Skype para Business Server.'
ms.openlocfilehash: cefd631f1750d7eaa4404a2fe2ffa8aa91675824
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899432"
---
# <a name="plan-for-conferencing-in-skype-for-business-server"></a>Planejamento de conferência no Skype para Business Server
 
**Resumo:** Leia este tópico para saber mais sobre os recursos de conferência e capacidades no Skype para Business Server.
  
Conferência em Skype para Business Server permite que os usuários atender e participar de conferências on-line usando seu Skype para o cliente de negócios, em vez de todas as pessoas se unindo na mesma sala. Os participantes da reunião podem se conectar a uma reunião com seu Skype para o cliente de negócios para uma experiência de vídeo e o áudio completo ou discar para uma conferência usando um telefone. As conferências também são compatíveis com mensagens instantâneas, compartilhamento da área de trabalho e de aplicativos, e quadros de comunicação interativos.
  
Este tópico inclui as seguintes seções:
  
- Recursos e funcionalidades da conferência
    
- Componentes de conferência
    
- Políticas de conferência
    
- Suporte a reuniões grandes
    
- Determinação das necessidades da sua organização
    
## <a name="conferencing-features-and-capabilities"></a>Recursos e funcionalidades da conferência

Há quatro tipos de conferência disponíveis no Skype para Business Server: webconferências, áudio e vídeo (A / V) conferência, conferência discada e conferência de mensagem instantânea (IM). 
  
Você pode optar por habilitar todos os tipos de conferências ou usar apenas um deles, dependendo de suas necessidades. Por exemplo, você pode permitir que todos os tipos, incluindo conferência discada permitir que os usuários que não conseguem ingressar em uma conferência com um Skype para cliente corporativos chamada e participar de áudio da reunião de um telefone. Quando você implanta o Skype para Business Server, recursos de conferência de mensagem Instantânea serão implantados automaticamente; você especificar se deseja implantar a web, A / V e conferência discada usando o construtor de topologias. Para obter mais informações, consulte [Deploy conferência no Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md). 
  
Nas subseções a seguir, estão descritos os recursos e as funcionalidades de cada tipo de conferência.
  
### <a name="web-conferencing"></a>Webconferência

Webconferência permite que os participantes da reunião colaborar em documentos compartilhados durante a reunião e para o apresentador da reunião compartilhar aplicativos por meio do Skype para o cliente de negócios. A webconferência oferece os seguintes recursos: 
  
- **Quadro de comunicações e anotações.** O quadro de comunicações é uma tela em branco que pode ser usada para colaboração com texto, tinta, desenhos e imagens. As anotações feitas nos quadros de comunicações podem ser vistas por todos os participantes da reunião. O recurso de quadro de comunicações aprimora a colaboração, pois habilita os participantes da reunião a discutirem ideias, fazerem brainstorming, anotações e muito mais.
    
- **Sondagem.** O recurso sondagem aprimora a colaboração ao permitir que os apresentadores determinem rapidamente as preferências dos participantes. Durante reuniões online e conversas, os apresentadores podem utilizar a sondagem para obter respostas anônimas dos participantes. Todos os apresentadores podem ver os resultados e optar por escondê-los ou mostrá-los aos presentes.
    
- **Compartilhamento de aplicativos e de área de trabalho.** Durante uma conferência, o apresentador da reunião pode compartilhar sua área de trabalho inteira, um aplicativo individual ou monitores individuais em um ambiente de vários monitor. Além de simplesmente visualizar o conteúdo, outros participantes da conferência podem solicitar o controle da tela do apresentador e, mediante permissão, interagir com o conteúdo (inclusive com rolagem e edição). Os participantes da reunião também podem assumir como apresentadores e compartilhar conteúdo durante a reunião.
    
- **Compartilhamento do PowerPoint.** Permite que os usuários compartilhem apresentações do PowerPoint na reunião através de um servidor do Office Web Apps, que permite:
    
  - Exibições de alta resolução e suporte às funcionalidades do PowerPoint, como animações, transições de slide e vídeo incorporado.
    
  - Dispositivos móveis podem acessar essas apresentações.
    
  - Usuários com os privilégios adequados podem rolar uma apresentação do PowerPoint independente da apresentação propriamente dita. Por exemplo, enquanto Ken está fazendo a apresentação dele, Heidi pode olhar qualquer slide que desejar sem afetar a apresentação do Ken.
    
### <a name="audio-and-video-conferencing"></a>Conferência de áudio e vídeo

A conferência de áudio e vídeo permite sons e imagem na reunião. O áudio permite que os participantes falem uns com os outros, como se estivessem na mesma sala. Vídeo permite que o Monitor de vídeo no Skype para o cliente de negócios de qualquer participantes ou apresentadores que ingressem na reunião com um dispositivo de conferência ou responsável de web que ofereça suporte a vídeo.
  
 Skype para Business Server oferece vários recursos que os usuários podem usar para configurar os serviços de audioconferência experiência do usuário, incluindo o seguinte:
  
- **Mudo.** O apresentador pode usar essa configuração para retirar o áudio de todos os participantes na conferência e colocá-la em um estado no qual aqueles que não forem apresentadores não poderão ativar o áudio de si próprios.
    
- **Anúncios de entrada/saída da conferência.** Se você tiver habilitado a conferência discada, os apresentadores poderão usar esta configuração para ligar ou desligar os anúncios de entrada/saída e minimizar distrações enquanto a conferência estiver em andamento.
    
- **Adicionando um usuário discando a eles.** Os apresentadores e participantes que tiverem permissão, pode adicionar números PSTN às conferências e ter a conferência discar para esses números.
    
  Skype para Business Server oferece vários recursos que os usuários podem usar para configurar a conferência de vídeo experiência do usuário, incluindo o seguinte:
  
- **Modo de exibição de galeria.** Em conferências de vídeo que tenham mais de duas pessoas, os usuários automaticamente veem todos na conferência. Se a conferência tiver mais de cinco participantes, o vídeo dos participantes mais ativos serão exibidos na linha superior e apenas a foto dos outros participantes será exibida. O vídeo de vários participantes está ativado como padrão.
    
- **Vídeo panorâmico.** Se um dispositivo de conferência de vídeo RoundTable estiver instalado na sala de conferências, esse recurso fornecerá uma visão de 360 graus da sala. A faixa de vídeo panorâmico está disponível apenas com dispositivos RoundTable.
    
- **Modo de vídeo somente apresentador.** Os apresentadores podem configurar a reunião de forma que apenas o vídeo deles seja exibido. Isso evita distrações em reuniões grandes, quando várias transmissões de vídeo estão disponíveis e bloqueadas para diferentes fontes. Esse modo também se aplica ao vídeo capturado e fornecido por dispositivos RoundTable.
    
- **Destaque de vídeo.** Os apresentadores podem configurar a reunião para que apenas o vídeo de um participante selecionado que seja a fonte do vídeo seja visto pelos outros participantes na conferência. Esse modo também se aplica ao vídeo capturado e fornecido pelos dispositivos RoundTable para vídeo panorâmico.
    
### <a name="dial-in-conferencing"></a>Conferência discada

Conferência discada permite que os participantes da reunião ingressar na parte de áudio de uma reunião chamando reunião de um telefone. A conferência discada é um subconjunto da conferência de áudio e exige configuração adicional. Para obter mais informações sobre conferência discada, consulte [Planejar a conferência discada no Skype para Business Server](dial-in-conferencing.md) e [Configure a conferência discada no Skype para Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md). 
  
### <a name="instant-messaging-conferencing"></a>Conferência por mensagens instantâneas

A conferência por mensagens instantâneas (IM) permite que mais de dois participantes se comuniquem em uma única sessão de mensagens instantâneas. Para obter detalhes sobre a conferência de mensagens Instantâneas, consulte [Planejar a mensagens instantâneas e presença no Skype para Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
## <a name="conferencing-components"></a>Componentes de conferência

Os componentes compatíveis com os recursos de conferência incluem o seguinte:
  
- **Serviço de aplicativo.** O serviço de aplicativo cria uma plataforma para implantar, hospedar e gerenciar aplicativos de comunicações unificadas (UC). A conferência discada usa dois aplicativos de UC que requerem o serviço de aplicativo: Atendedor de Conferência e Comunicado de Conferência. O serviço de aplicativo é instalado e ativado por padrão em cada servidor Front-End em um pool de Front-End. Ele também é instalado em cada servidor Standard Edition para habilitar e configurar conferência discada.
    
- **Aplicativo Atendedor de Conferência.** O aplicativo Atendedor de Conferência é um aplicativo de comunicações unificadas que aceita chamadas de PSTN (Rede Telefônica Pública Comutada), reproduz prompts e ingressa em chamadas de conferências A/V. O aplicativo Atendedor de Conferência é instalado e ativado por padrão ao habilitar a conferência discada.
    
- **Aplicativo Comunicado de Conferência.** O Comunicado de Conferência é um aplicativo de comunicações unificadas que emite sons e prompts para participantes de PSTN em certas ações, como quando os participantes ingressam ou saem de uma conferência, são colocados e retirados do mudo, quando alguém entra no lobby da conferência ou quando a conferência é bloqueada ou desbloqueada. O aplicativo Comunicado de Conferência também é compatível com comandos de multifrequência de tom dual (DTMF) do teclado do telefone. O aplicativo Comunicado de Conferência é automaticamente instalado e habilitado por padrão quando você habilita a conferência discada.
    
- **Página Configurações da Conferência Discada.** A página de Configurações da Conferência Discada exibe os números de discagem da conferência, com os idiomas disponíveis, informações de atribuição da conferência (ou seja, para reuniões que não precisam ser agendadas) e controles DTMF durante a conferência, além de oferecer suporte ao gerenciamento do número de identificação pessoal (PIN) e informações atribuídas sobre a conferência. A página de Configurações da Conferência Discada é automaticamente instalada como parte dos serviços da Web.
    
- **Servidor de mediação e o gateway PSTN.** Conferência discada requer um servidor de mediação para convertem a sinalização (e mídia em algumas configurações) entre Skype para Business Server e o gateway PSTN e um gateway PSTN para converter a sinalização e mídia entre o servidor de mediação e o gateway PSTN . Para conferência discada, você deve implantar pelo menos um servidor de mediação e pelo menos um dos seguintes procedimentos:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
  > [!NOTE]
  > Se você estiver implantando o Enterprise Voice também, gateways PSTN e de servidor de mediação fazem parte da implantação do Enterprise Voice. Se você não estiver implantando o Enterprise Voice, você precisará implantar pelo menos um servidor de mediação e pelo menos um PSTN gateway, IP-PBX ou SBC para conferência discada. 
  
- **Repositório de arquivos.** O Repositório de arquivos é usado para arquivos de áudio de nomes gravados. O Repositório de Arquivos é um componente padrão de todas as implantações do Enterprise Edition ou Standard Edition.
    
- **Armazenamento de usuários.** Repositório do usuário é usado para armazenar o usuário Skype para Business Server PINs. Os PINs são marcados por hash. O armazenamento de Usuários é um componente padrão em todas as implantações de Enterprise Edition ou Standard Edition.
    
- **Servidor do Office Web Apps.** Para usar os recursos de webconferência, os administradores devem instalar o Office Web Apps Server e configurar o Skype para Business Server para se comunicar com o Office Web Apps Server.
    
## <a name="conferencing-policies"></a>Políticas de conferência

Para impor políticas e o uso de largura de banda do controle da sua organização, você pode definir políticas para os tipos de reuniões que os usuários podem organizar. É possível definir uma ampla variedade de políticas de conferência e atribuí-las a cada usuário e grupo de usuários. Você também pode definir políticas que regem as conversas ponto a ponto. Para obter detalhes sobre como definir políticas de conferência, consulte [Gerenciar políticas de conferência no Skype para Business Server](../../manage/conferencing/conferencing-policies.md). Para obter detalhes sobre o gerenciamento de largura de banda, consulte [Planejar o controle de admissão de chamada no Skype para Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
## <a name="support-for-large-meetings"></a>Suporte a reuniões grandes

O tamanho de reuniões que suporta o Skype para Business Server depende se a conferência está hospedada em um pool compartilhado ou dedicado:
  
- Em um pool compartilhado, Skype para Business Server poderá hospedar reuniões com até 250 usuários. Um pool compartilhado é um pool que hospeda Skype todas as cargas de trabalho do Business Server incluindo mensagens instantâneas (IM) e presença, conferência e Enterprise Voice. 
    
- Em um pool dedicado, Skype para Business Server pode suportar reuniões com até participantes de 1000 usando web e áudio/vídeo (A / V) conferências, incluindo compartilhamento de apresentações do PowerPoint. Esse suporte exige um pool dedicado, configurado para suportar grandes reuniões e gerenciado de forma a garantir a hospedagem de apenas uma grande reunião por vez. 
    
Para obter mais informações sobre o gerenciamento de grandes reuniões, consulte [Planejar para grandes reuniões em Skype para Business Server](large-meetings.md).
  
Se sua organização requer maiores capacidades de reunião, você deve considerar a implementação de um ambiente híbrido que tiram vantagens do Skype transmitir reunião, um serviço online que faz parte do Office 365. A Transmissão de Reunião do Skype habilita os usuários a hospedarem e divulgarem a grandes públicos online reuniões com até 10.000 participantes. O uso de Transmissão de Reunião do Skype exige que o Skype for Business Server esteja configurado como híbrido em um locatário do Office 365 de produção. O pré-requisito é que todos os usuários tenham um locatário online. Se você estiver interessado em implantar uma solução híbrida que possa tirar proveito da Transmissão de Reunião do Skype, consulte [Configure your on-premises deployment for Skype Meeting Broadcast](../../deploy/configure-skype-meeting-broadcast.md).
  
## <a name="determine-your-organizations-needs"></a>Determine as necessidades da sua organização

Ao determinar quais funcionalidades de conferência serão implantadas, você precisa considerar os recursos que deseja disponibilizar para seus usuários, bem como seus recursos de largura de banda de rede. A lista a seguir fornece orientações a conferência de planejamento de processo para determinar quais recursos de conferência que você deve implantar, com base nos requisitos da sua organização.
  
> [!NOTE]
> Ao habilitar a conferência na implantação, você automaticamente habilita webconferência e conferência A/V. No entanto, é possível desabilitar características específicas ao configurar políticas de conferência conforme descrito anteriormente neste tópico. 
  
- **Você deseja habilitar a webconferência, que inclui a colaboração em documentos e o compartilhamento de aplicativos?**
    
    Em caso positivo, você precisará habilitar a conferência para seu pool de Front-Ends usando a Ferramenta de Planejamento ou o Construtor de Topologias. Para obter mais informações, consulte [Deploy conferência no Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    O compartilhamento de aplicativos requer e usa mais largura de banda que a colaboração em documentos. Skype para Business Server oferece um mecanismo de limitação para controlar a cada sessão de compartilhamento de aplicativos. Por padrão, isso é definido como 1,5 KB por segundo para cada sessão. Se você não deseja habilitar o compartilhamento de aplicativo, mas desejar a colaboração de documentos, você pode habilitar a conferência e usar políticas de conferência para desabilitar o compartilhamento de aplicativos. Para obter detalhes sobre como configurar políticas de conferência, consulte [Gerenciar políticas de conferência no Skype para Business Server](../../manage/conferencing/conferencing-policies.md).
    
    Para habilitar os usuários a compartilharem apresentações do PowerPoint, é preciso configurar o Servidor do Office Web Apps. Para obter detalhes sobre como configurar o Office Web Apps Server, consulte [Configure integração com o Office Web Apps Server no Skype para Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Deseja habilitar a conferência de áudio e vídeo?**
    
    Em caso positivo, você precisará habilitar a conferência para seu pool de Front-Ends usando a Ferramenta de Planejamento ou o Construtor de Topologias. Para obter mais informações, consulte [Deploy conferência no Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).
    
    A conferência A/V exige e usa mais largura de banda que a webconferência (que inclui a colaboração em documentos e o compartilhamento de aplicativos). Se você não quiser habilitar a conferência de áudio e vídeo, mas quiser habilitar a webconferência, poderá habilitar a conferência e usar as políticas para desabilitar conferências A/V.
    
    Se você quiser habilitar a conferência de áudio, mas não a conferência de vídeo, poderá habilitar a conferência A/V e usar políticas de conferência para impedir as conferências de vídeo. Como alternativa, você pode habilitar a conferência A/V e permitir que somente determinados usuários iniciem ou participem de conferências A/V. 
    
    Para obter mais informações sobre como configurar políticas de conferência, consulte [Gerenciar políticas de conferência no Skype para Business Server](../../manage/conferencing/conferencing-policies.md).
    
    > [!NOTE]
    > O Enterprise Voice não é necessário para você usar a conferência A/V. Se você habilitar a conferência A/V, seus usuários poderão adicionar áudio às conferências, caso tenham dispositivos de áudio, mesmo que você use um sistema PBX como solução de telefonia. 
  
- **Deseja permitir que os usuários participem do áudio de conferências quando usam um telefone PSTN?**
    
    Em caso afirmativo, implante e habilite a conferência de discagem. Em seguida, os usuários convidados (dentro e fora da sua organização) poderão ingressar na parte de áudio de conferências usando um telefone PSTN.
    
    Conferência discada é um recurso opcional que você pode configurar quando você implanta o Skype para conferências Business Server. Embora a conferência discada use alguns dos mesmos componentes do Enterprise Voice, você pode implantar a conferência discada mesmo se não implantar o Enterprise Voice. A conferência discada é compatível com usuários corporativos e anônimos. Para obter mais informações sobre Configurando conferências discadas para enterprise e usuários anônimos, consulte [Deploy conferência no Skype para Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md) and [Configure a conferência discada no Skype para Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md).
    
- **Deseja permitir que usuários externos com clientes Skype for Business ingressem nas conferências?**
    
    Permitindo a participação externa em reuniões, você maximizar seu investimento em Skype para Business Server. Entre os usuários externos podem estar:
    
  - **Usuários remotos.** Os usuários da organização, quando eles estão trabalhando fora dos firewalls e estão usando seus laptops ou outro Skype para dispositivos do servidor de negócios.
    
  - **Usuários federados.** Os usuários de empresas que você trabalhe com quem também executar Skype para Business Server. Para habilitar que seus usuários entrem em contato facilmente com esses usuários, crie relacionamentos federados com essas empresas.
    
  - **Usuários anônimos.** Quaisquer outros usuários externos que são convidados especificamente por seus usuários para participar de conferências específicas. O organizador de uma reunião em sua empresa pode enviar um convite de uma conferência por email a um usuário externo. O email inclui um link no qual o usuário externo pode clicar para ingressar na conferência.
    
    Se você quiser permitir que usuários externos, você precisará implantar servidores de borda. Além disso, com os Servidores de Borda implantados, você pode criar relacionamentos federados com outras organizações, como clientes ou fornecedores, e os usuários dessas organizações poderão colaborar mais facilmente com seus usuários.
    
    Para obter detalhes sobre como implantar os Servidores de Borda, consulte Plano para Servidores de Borda e Implantar Servidores de Borda. Para obter detalhes sobre como habilitar o acesso externo para Office Web Apps Server, consulte [Configure integração com o Office Web Apps Server no Skype para Business Server](../../deploy/deploy-conferencing/office-web-app-server.md).
    
- **Você deseja controlar os clientes que podem ingressar Skype para reuniões Business Server?**
    
    Em caso afirmativo, você deve configurar a página de ingresso na reunião para que apenas as opções do cliente que você deseja oferecer fiquem disponíveis. Cada vez Skype para Business Server um usuário clica em um link para ingressar em uma reunião agendada, detecta se um cliente já estiver instalado no computador. Em seguida, ele iniciará o cliente padrão e abrirá a página de ingresso na reunião, que contém links para clientes alternativos. A reunião página de ingresso sempre contém a opção de usar Skype para negócios Web App. Além dessa opção, você pode decidir se deseja incluir links para o Atendedor e versões anteriores do Communicator. 
    

