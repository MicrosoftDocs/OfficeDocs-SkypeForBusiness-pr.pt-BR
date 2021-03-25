---
title: Planejar sua topologia de conferência para o Skype for Business Server
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Resumo: leia este tópico para saber mais sobre como planejar sua topologia de conferência no Skype for Business Server.'
ms.openlocfilehash: acf1fecc4ab7c3ea19ca9b65b9ff2ffa2a1e93d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121579"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planejar sua topologia de conferência para o Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre como planejar sua topologia de conferência no Skype for Business Server.
  
Este tópico descreve noções básicas de topologia para conferência no Skype for Business Server:
  
- Topologias suportadas
    
- Considerações sobre conferência discagem
    
- Considerações sobre webconferência
    
- Requisitos para grandes reuniões
    
Para obter mais informações sobre requisitos de hardware e software, consulte [Requisitos](hardware-and-software-requirements.md)de hardware e software para conferência no Skype for Business Server .
  
## <a name="supported-topologies"></a>Topologias suportadas

No Skype for Business Server, o servidor que executa serviços de conferência é sempre alocado com os Servidores Front-End ou servidores Standard Edition. Quando você implanta o Skype for Business Server, os recursos de conferência de mensagens automáticas são implantados automaticamente. Você pode especificar se deve implantar web, áudio e vídeo (A/V) e conferência discada usando o Construtor de Topologias. Você também pode usar o Construtor de Topologias para adicionar conferência a uma implantação existente. Para obter detalhes sobre noções básicas de topologia e cenários de localização, consulte [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Você pode implantar a conferência nas seguintes topologias e configurações:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Com ou sem Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>Considerações sobre conferência discagem

Se você estiver implantando conferência discagem, considere o seguinte:
  
- A conferência discada exige que um Servidor de Mediação traduza sinalização (e mídia em algumas configurações) entre o Skype for Business Server e o gateway PSTN e um gateway PSTN para converter sinalização e mídia entre o Servidor de Mediação e o gateway PSTN.
    
   Antes de configurar a conferência discado, você precisa implantar um Enterprise Voice ou um Servidor de Mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
- Você pode implantar o aplicativo serviço de aplicativo, o aplicativo de Atendente de Conferência e o aplicativo Comunicado de Conferência em um site central, mas não em um site de filial.
    
- Você deve implantar a conferência discada em cada pool onde implantar a conferência do Skype for Business Server. Não é necessário atribuir números de acesso em cada pool, mas é necessário implantar o recurso de conferência discada em cada pool. Esse requisito dá suporte ao recurso de nome gravado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Skype for Business Server em um pool diferente. 
    
Para obter mais informações, [consulte Plan for dial-in conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considerações sobre webconferência

A webconferência requer o seguinte: 
  
- O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.
    
- Integração com o Servidor do Office Web Apps/Servidor do Office Online, que é necessário para compartilhar arquivos do PowerPoint durante uma conferência.
    
> [!NOTE]
> A última iteração do Servidor do Office Web Apps é denominada Servidor do Office Online, que é suportado pelo Skype for Business Server. Para obter mais detalhes, consulte a documentação do [Servidor do Office Online.](/officeonlineserver/office-online-server) 
  
O Skype for Business Server fornece as seguintes maneiras de configurar o Servidor do Office Web Apps/Servidor do Office Online. Dependendo das suas necessidades, você pode:
  
- **Instale o Skype for Business Server e o Servidor do Office Web Apps/Servidor do Office Online no local por trás do firewall da sua organização e na mesma zona de rede.** Com essa topologia, o acesso externo ao Servidor do Office Web Apps/Servidor do Office Online será fornecido por meio do servidor proxy reverso. O ideal é instalar o Servidor do Office Web Apps/Servidor do Office Online na mesma zona de rede do Skype for Business Server.
    
    Os clientes externos do Skype for Business podem se conectar ao Skype for Business Server e ao Servidor do Office Web Apps/Servidor do Office Online usando um servidor proxy reverso, que é um servidor que recebe solicitações da Internet e as encaminha para a rede interna. (Os clientes internos não precisam usar o servidor proxy reverso porque eles podem se conectar diretamente ao Servidor do Office Web Apps/Servidor do Office Online.) Essa topologia funciona melhor se você quiser usar um farm dedicado do Servidor do Office Web Apps/Servidor do Office Online que só é usado pelo Skype for Business Server.
    
- **Use um Servidor do Office Web Apps implantado externamente/Servidor do Office Online.** Nesta topologia, o Skype for Business Server é implantado no local e usa um Servidor do Office Web Apps/Servidor do Office Online implantado fora da zona de rede do Skype for Business Server. Isso pode acontecer quando o Servidor do Office Web Apps/Servidor do Office Online é compartilhado entre vários aplicativos na corporação e é implantado em uma rede que exige que o Skype for Business Server use a interface externa do Servidor do Office Web Apps/Servidor do Office Online e vice-versa.
    
    Você não precisa instalar um servidor proxy reverso; em vez disso, todas as solicitações do Servidor do Office Web Apps/Servidor do Office Online para o Skype for Business Server são roteados por meio do Servidor de Borda. Seus clientes internos e externos do Skype for Business conectam-se ao Servidor do Office Web Apps/Servidor do Office Online usando a URL externa.
    
    Se o Servidor do Office Web Apps/Servidor do Office Online for implantado fora do firewall interno, selecione a opção **Servidor do Office Web Apps** implantado em uma rede externa (ou seja, perímetro/Internet) no Construtor de Topologias.
    
Para obter mais informações, [consulte Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Independente da topologia selecionada, é fundamental que as portas de firewall certas estejam abertas. Você deve garantir que nomes DNS, endereços IP e portas não sejam bloqueados por firewalls no Servidor do Office Web Apps/Servidor do Office Online, no balanceador de carga ou no Skype for Business Server.
  
> [!NOTE]
> Outra opção para fornecer acesso externo ao Servidor do Office Web Apps/Servidor do Office Online é implantar o servidor na rede de perímetro. Se você optar por fazer isso, lembre-se de que a configuração do Servidor do Office Web Apps/Servidor do Office Online exige que o computador do servidor seja membro do seu domínio do Active Directory. A menos que sua política de rede permita que os computadores na rede de perímetro sejam membros de domínio do Active Directory, é recomendável que você não instale o Servidor do Office Web Apps/Servidor do Office Online na rede de perímetro. Em vez disso, você deve instalar o Servidor do Office Web Apps/Servidor do Office Online na rede interna e fornecer acesso de usuário externo por meio do servidor proxy reverso. 
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de topologia para grandes reuniões

Uma única reunião grande requer pelo menos um Servidor Front-End e um Servidor Back-End. No entanto, para fornecer alta disponibilidade, recomendamos um pool de dois Servidores Front-End com Servidores Back-End espelhados, conforme mostrado no diagrama a seguir:
  
**Topologia de reunião grande**

![Topologia de reunião grande](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
O usuário que hospeda as grandes reuniões deve ter sua conta de usuário hospedada no pool de Front-End. No entanto, não recomendamos que você hospede outras contas de usuário neste pool. Em vez disso, use-o apenas para reuniões grandes. A prática prática é criar uma conta de usuário especial neste pool para ser usada apenas para hospedar grandes reuniões. Como a configuração de reunião grande é otimizada para o desempenho, usá-la como um usuário normal pode ter problemas, como a incapacidade de promover uma sessão P2P para uma reunião quando um ponto de extremidade PSTN está envolvido.
  
Gerenciar um pool com exatamente dois Servidores Front-End requer algumas considerações especiais. Para obter mais informações, consulte [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) and [Reference toplogies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Além disso, se você quiser, opcionalmente, fornecer backup e failover de recuperação de desastres para o pool usado para grandes reuniões, você pode emparelhá-lo com um pool dedicado de configuração semelhante em um data center diferente. Para obter detalhes, [consulte Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Observações adicionais sobre a topologia incluem:
  
- Um compartilhamento de arquivos é necessário para armazenar conteúdo de reunião e, se o Servidor de Arquivamento for implantado e habilitado, para armazenar os arquivos de arquivamento. O compartilhamento de arquivos pode ser dedicado ao pool ou pode ser o mesmo compartilhamento de arquivos usado por outro pool no site no qual o pool é implantado. Para obter detalhes sobre como configurar o compartilhamento de arquivos, consulte [Create a file share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Um Servidor do Office Web Apps/Servidor do Office Online é necessário para habilenciar a funcionalidade de apresentação do PowerPoint em grandes reuniões. O Servidor do Office Web Apps/Servidor do Office Online pode ser dedicado ao pool de reuniões grande ou pode ser o mesmo Servidor do Office Web Apps/Servidor do Office Online usado por outros pools no site no qual o pool dedicado é implantado. Para obter mais informações, [consulte Configure integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- O balanceamento de carga dos Servidores Front-End requer balanceamento de carga de hardware para o tráfego HTTP (como download de conteúdo de reunião). O balanceamento de carga DNS é recomendado para tráfego SIP. Para obter [detalhes, consulte Requisitos de balanceamento de carga para Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Se você quiser usar o Monitoring Server para o pool dedicado de grandes reuniões, recomendamos usar o Servidor de Monitoramento e seu banco de dados compartilhados em todos os pools de Servidor Front-End em sua implantação do Skype for Business Server. Para obter mais informações, [consulte Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
