---
title: Planejar sua topologia de conferência para o Skype for Business Server
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
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Resumo: Leia este tópico para saber mais sobre como planejar sua topologia de conferência no Skype for Business Server.'
ms.openlocfilehash: 68ee859979deb7d977ee546e711474d0b6ba06e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030775"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planejar sua topologia de conferência para o Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre como planejar sua topologia de conferência no Skype for Business Server.
  
Este tópico descreve as noções básicas de topologia para conferências no Skype for Business Server:
  
- Topologias suportadas
    
- Considerações de conferência discada
    
- Considerações de Webconferência
    
- Requisitos para grandes reuniões
    
Para obter mais informações sobre requisitos de hardware e software, consulte [Hardware and Software Requirements for Conferencing in Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologias suportadas

No Skype for Business Server, o servidor que executa o serviços de conferência é sempre colocado com os servidores front-end ou servidores Standard Edition. Quando você implanta o Skype for Business Server, os recursos de conferência de mensagens instantâneas são implantados automaticamente. Você pode especificar se deseja implantar a Web, áudio e vídeo (A/V) e conferência discada usando o construtor de topologias. Você também pode usar o construtor de topologias para adicionar conferências a uma implantação existente. Para obter detalhes sobre as noções básicas de topologia e cenários de colocação, consulte [Topology Basics for Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
Você pode implantar a conferência nas seguintes topologias e configurações:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Com ou sem Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>Considerações de conferência discada

Se você estiver implantando a conferência discada, deverá considerar o seguinte:
  
- A conferência discada requer um servidor de mediação para converter a sinalização (e mídia em algumas configurações) entre o Skype for Business Server e o gateway PSTN e um gateway PSTN para converter a sinalização e mídia entre o servidor de mediação e o gateway PSTN .
    
   Antes de poder configurar a conferência discada, você precisa implantar o Enterprise Voice ou um servidor de mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
- Você pode implantar o serviço de aplicativo, o aplicativo de atendedor de conferência e o aplicativo de anúncio de conferência em um site central, mas não em um site de filial.
    
- Você deve implantar a conferência discada em todos os pools onde você implanta a conferência do Skype for Business Server. Não é necessário atribuir números de acesso em cada pool, mas é necessário implantar o recurso de conferência discada em cada pool. Esse requisito suporta o recurso de nome registrado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Skype for Business Server em um pool diferente. 
    
Para obter mais informações, consulte [Plan for dial-in Conferencing in Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considerações de Webconferência

A conferência da Web requer o seguinte: 
  
- O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.
    
- Integração com o servidor do Office Web Apps/servidor do Office Online, que é necessário para compartilhar arquivos do PowerPoint durante uma conferência.
    
> [!NOTE]
> A iteração mais recente do servidor do Office Web Apps é chamada de servidor do Office Online, que é compatível com o Skype for Business Server. Para obter mais detalhes, consulte a [documentação do servidor do Office Online](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx). 
  
O Skype for Business Server oferece as seguintes maneiras de configurar o servidor do Office Web Apps/servidor do Office Online. Dependendo das suas necessidades, você pode:
  
- **Instale o Skype for Business Server e o servidor do Office Web Apps/servidor do Office Online no local por meio do firewall da sua organização e na mesma zona de rede.** Com essa topologia, o acesso externo ao servidor do Office Web Apps/servidor do Office Online será fornecido através do servidor de proxy reverso. O ideal é que você instale o servidor do Office Web Apps/servidor do Office Online na mesma zona de rede que o Skype for Business Server.
    
    Clientes externos do Skype for Business podem se conectar ao Skype for Business Server e ao servidor do Office Web Apps/servidor do Office online usando um servidor proxy reverso, que é um servidor que toma solicitações da Internet e as encaminha para a rede interna. (Os clientes internos não precisam usar o servidor proxy reverso, pois podem se conectar ao servidor do Office Web Apps/servidor do Office Online diretamente.) Essa topologia funciona melhor se você quiser usar um farm dedicado do servidor do Office Web Apps/servidor do Office Online que é usado apenas pelo Skype for Business Server.
    
- **Use um servidor do Office Web Apps/servidor do Office Online implantado externamente.** Nesta topologia, o Skype for Business Server é implantado localmente e usa um servidor do Office Web Apps/servidor do Office Online implantado fora da zona de rede do Skype for Business Server. Isso pode acontecer quando o servidor do Office Web Apps/servidor do Office Online é compartilhado entre vários aplicativos na empresa e é implantado em uma rede que requer o Skype for Business Server para usar a interface externa do servidor do Office Web Apps/servidor do Office Online e vice-versa.
    
    Não é necessário instalar um servidor de proxy reverso; em vez disso, todas as solicitações do servidor do Office Web Apps/servidor do Office Online para o Skype for Business Server são roteadas através do servidor de borda. Os clientes internos e externos do Skype for Business se conectam ao servidor do Office Web Apps/servidor do Office online usando a URL externa.
    
    Se o servidor do Office Web Apps/servidor do Office Online for implantado fora do seu firewall interno, selecione a opção o **servidor do Office Web Apps é implantado em uma rede externa** (ou seja, perímetro/Internet) no construtor de topologias.
    
Para obter mais informações, consulte [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Independente da topologia selecionada, é fundamental que as portas de firewall certas estejam abertas. Você deve certificar-se de que os nomes DNS, endereços IP e portas não são bloqueados por firewalls no servidor do Office Web Apps/servidor do Office Online, no balanceador de carga ou no Skype for Business Server.
  
> [!NOTE]
> Outra opção para fornecer acesso externo ao servidor do Office Web Apps/servidor do Office Online é implantar o servidor na rede de perímetro. Se você optar por fazer isso, tenha em mente que a configuração do servidor do Office Web Apps/servidor do Office Online requer que o computador servidor seja membro do seu domínio do Active Directory. A menos que a política de rede permita que os computadores na rede de perímetro sejam membros do domínio do Active Directory, é recomendável que você não instale o servidor do Office Web Apps/servidor do Office Online na rede de perímetro. Em vez disso, você deve instalar o servidor do Office Web Apps/servidor do Office Online na rede interna e fornecer acesso de usuário externo através do servidor de proxy reverso. 
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de topologia para grandes reuniões

Uma única reunião grande requer pelo menos um servidor front-end e um servidor back-end. No entanto, para fornecer alta disponibilidade, recomendamos um pool de dois servidores front-end com servidores back-end espelhados, conforme mostrado no diagrama a seguir:
  
**Topologia de reunião grande**

![Topologia de reunião grande](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
O usuário que hospeda as grandes reuniões deve ter sua conta de usuário hospedada no pool de front-ends. No entanto, não recomendamos que você hospede outras contas de usuário nesse pool. Em vez disso, use-o apenas para grandes reuniões. A prática recomendada é criar uma conta de usuário especial nesse pool para ser usada apenas para hospedar grandes reuniões. Como a grande configuração de reunião é otimizada para desempenho, usá-la como um usuário normal pode ter problemas como a incapacidade de promover uma sessão P2P para uma reunião quando um ponto de extremidade PSTN está envolvido.
  
O gerenciamento de um pool com exatamente dois servidores front-end requer algumas considerações especiais. Para obter mais informações, consulte [Topology Basics para o Skype for Business server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) e [topologias de referência para o Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Além disso, se você quiser fornecer opcionalmente o backup de recuperação de desastres e o failover do pool usado para grandes reuniões, é possível emparelhar com uma configuração de pool dedicado de forma semelhante em um Data Center diferente. Para obter detalhes, consulte [Plan for High Availability and Disaster Recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
As observações adicionais sobre a topologia incluem:
  
- Um compartilhamento de arquivos é necessário para armazenar o conteúdo da reunião e, se o servidor de arquivamento estiver implantado e habilitado, para armazenar os arquivos de arquivamento. O compartilhamento de arquivos pode ser dedicado ao pool ou pode ser o mesmo compartilhamento de arquivo usado por outro pool no site no qual o pool é implantado. Para obter detalhes sobre como configurar o compartilhamento de arquivos, consulte [Create a File Share in Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- Um servidor do Office Web Apps/Office Online é necessário para habilitar a funcionalidade de apresentação do PowerPoint em grandes reuniões. O servidor do Office Web Apps/Office Online pode ser dedicado ao grande pool de reuniões ou pode ser o mesmo servidor do Office Web Apps/servidor do Office Online usado por outros pools no site no qual o pool dedicado é implantado. Para obter mais informações, consulte [Configure Integration with Office Web Apps Server in Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- O balanceamento de carga dos servidores front-end requer o balanceamento de carga de hardware para o tráfego HTTP (como download de conteúdo de reunião). O balanceamento de carga de DNS é recomendado para tráfego SIP. Para obter detalhes, consulte [Load Balancing Requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Se você quiser usar o Monitoring Server para o pool dedicado de grandes reuniões, recomendamos o uso do Monitoring Server e do banco de dados que são compartilhados por todos os pools de servidores front-end na sua implantação do Skype for Business Server. Para obter mais informações, consulte [Plan for monitoring in Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

