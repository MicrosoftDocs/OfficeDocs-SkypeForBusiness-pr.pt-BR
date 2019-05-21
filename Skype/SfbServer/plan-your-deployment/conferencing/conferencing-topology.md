---
title: Planejar a topologia de conferência para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Resumo: Leia este tópico para saber mais sobre como planejar a topologia de conferência no Skype for Business Server.'
ms.openlocfilehash: 39067403513173e3fe26c5767042c62f549e0a7c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277395"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Planejar a topologia de conferência para o Skype for Business Server
 
**Resumo:** Leia este tópico para saber mais sobre como planejar a topologia de conferência no Skype for Business Server.
  
Este tópico descreve noções básicas de topologia para conferências no Skype for Business Server:
  
- Topologias suportadas
    
- Considerações sobre a conferência discada
    
- Considerações sobre a webconferência
    
- Requisitos para grandes reuniões
    
Para obter mais informações sobre os requisitos de hardware e software, consulte [requisitos de hardware e software para conferência no Skype for Business Server](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologias suportadas

No Skype for Business Server, o servidor que executa serviços de conferência sempre é posicionado com os servidores de front-end ou servidores padrão da edição. Ao implantar o Skype for Business Server, os recursos de conferência por mensagem instantâneas são automaticamente implantados. É possível especificar a implantação de web, áudio e vídeo (A/V) e conferência discada usando o Construtor de Topologias. Você também pode usar o Construtor de Topologias para adicionar conferências a uma implantação existente. Para obter detalhes sobre as noções básicas de topologia e os cenários de colocação, consulte [noções básicas de topologia para o Skype for Business Server](../../plan-your-deployment/topology-basics/topology-basics.md).
  
É possível implantar a conferência discada nas seguintes topologias e configurações:
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- Com ou sem Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>Considerações sobre a conferência discada

Se você estiver implantando a conferência discada, será necessário considerar o seguinte:
  
- A conferência discada exige que um servidor de mediação traduza sinalização (e mídia em algumas configurações) entre o Skype for Business Server e o gateway PSTN e um gateway PSTN para traduzir a sinalização e a mídia entre o servidor de mediação e o gateway PSTN .
    
   Antes de configurar a conferência discada, é necessário implantar o Enterprise Voice ou um Servidor de Mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
- Você pode implantar o serviço de Aplicativo, o aplicativo Atendedor de Conferência e aplicativo Comunicado de Conferência em um local central, mas não no local da filial.
    
- Você deve implantar a conferência discada em todos os pools onde implantou a conferência do Skype for Business Server. Não é necessário atribuir números de acesso em cada pool, mas é necessário implantar o recurso de conferência discada em cada pool. Esse requisito dá suporte ao recurso de nome registrado quando um usuário chama um número de acesso de um pool para ingressar em uma conferência do Skype for Business Server em um pool diferente. 
    
Para obter mais informações, consulte [planejar conferência discada no Skype for Business Server](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considerações sobre a webconferência

A webconferência requer o seguinte: 
  
- O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.
    
- Integração com o Servidor do Office Web Apps/Servidor do Office Online, necessárias para compartilhar arquivos do PowerPoint durante uma conferência.
    
> [!NOTE]
> A iteração mais recente do Office Web Apps Server é chamada Office Online Server, que é compatível com o Skype for Business Server. Para obter mais detalhes, consulte a [documentação do Office Online Server](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
O Skype for Business Server fornece as seguintes maneiras de configurar o Office Web Apps Server/Office Online Server. Dependendo de seus requisitos, você pode:
  
- **Instale o Skype for Business Server e o Office Web Apps Server/Office Online Server no local por trás do firewall da sua organização e na mesma zona de rede.** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. O ideal é que você instale o Office Web Apps Server/Office Online Server na mesma zona de rede do Skype for Business Server.
    
    Os clientes externos do Skype for Business podem se conectar ao Skype for Business Server e ao Office Web Apps Server/Office Online Server usando um servidor proxy reverso, que é um servidor que recebe solicitações da Internet e as encaminha para a rede interna. (Os clientes internos não precisam usar o servidor proxy reverso porque podem se conectar ao servidor do Office Web Apps para o Office Online Server diretamente.) Essa topologia funciona melhor se você quiser usar um farm de servidor do Office Web Apps dedicado/Office Online usado somente pelo Skype for Business Server.
    
- **Use um servidor Office Web Apps implantado externamente/Office Online Server.** Nessa topologia, o Skype for Business Server é implantado no local e usa um servidor do Office Web Apps/Office Online que é implantado fora da zona de rede do Skype for Business Server. Isso pode acontecer quando o Office Web Apps Server/Office Online Server é compartilhado entre vários aplicativos na empresa e é implantado em uma rede que requer o Skype for Business Server para usar a interface externa do Office Web Apps Server/Office Online Server e vice-versa.
    
    Você não precisa instalar um servidor proxy reverso; em vez disso, todas as solicitações do servidor do Office Web Apps/do Office Online Server para o Skype for Business Server são roteadas pelo servidor de borda. Seus clientes internos e externos do Skype for Business se conectam ao servidor do Office Web Apps/do Office online usando a URL externa.
    
    If the Office Web Apps Server/Office Online Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network** (that is, perimeter/Internet) in Topology Builder.
    
Para obter mais informações, consulte [Configurar a integração com o servidor do Office Web Apps no Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Independentemente da topologia selecionada, é fundamental que as portas do firewall certas estejam abertas. Você deve certificar-se de que nomes DNS, endereços IP e portas não sejam bloqueados por firewalls no servidor Office Web Apps/Office Online Server, o balanceador de carga ou o Skype for Business Server.
  
> [!NOTE]
> Outra opção para fornecer acesso externo ao Servidor do Office Web Apps/Servidor do Office Online é implantar o servidor em uma rede de perímetro. Se você optar por fazer isso, tenha em mente que a instalação do Servidor do Office Web Apps/Servidor do Office Online requer que o computador servidor seja membro do seu domínio do Active Directory. A menos que sua política de rede permita computadores na rede de perímetro como membros do domínio do Active Directory, é recomendado não instalar o Servidor do Office Web Apps/Servidor do Office Online na rede de perímetro. Em vez disso, instale o Servidor do Office Web Apps/Servidor do Office Online na rede interna e dê acesso ao usuário externo através do servidor de proxy reverso.  
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de topologia para grandes reuniões

Uma grande reunião exige pelo menos um Servidor Front-End e um Servidor Back-End. No entanto, para permitir alta disponibilidade, recomendamos um pool com dois Servidores Front-End com Servidores Back-End espelhados, como exibido no diagrama a seguir:
  
**Topologia de grandes reuniões**

![Topologia de grandes reuniões](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
O usuário que hospeda as grandes reuniões deve ter sua conta de usuário hospedada nesse pool de Front-Ends. No entanto, não recomendamos que você hospede outras contas de usuário nesse pool. Em vez disso, use-o apenas para reuniões grandes. A prática recomendada é criar uma conta de usuário especial nesse pool para ser usada apenas para hospedar reuniões grandes. Já que a definição de grandes reuniões é otimizada para um melhor desempenho, usá-la como usuário normal poderia gerar problemas como incapacidade de promover uma sessão de P2P em uma reunião quando um ponto de extremidade de PSTN estiver envolvido.
  
Gerenciar um pool com exatamente dois Servidores Front-End exige algumas considerações especiais. Para obter mais informações, consulte [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) e [Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Além disso, se você quiser oferecer failover e backup de recuperação de desastres para o pool usado em grandes reuniões, poderá emparelhar com um pool dedicado de configuração semelhante em outro datacenter. Para obter detalhes, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
As notas adicionais sobre a topologia incluem:
  
- Um compartilhamento de arquivo é necessário para armazenar conteúdo da reunião e, se o Servidor de Arquivamento estiver implantado e habilitado, armazenar os arquivos de arquivo. O compartilhamento de arquivo pode ser dedicado ao pool ou pode ser o mesmo compartilhamento de arquivo usado por outro pool no site em que o pool é implantado. Para obter detalhes sobre como configurar o compartilhamento de arquivos, consulte [criar um compartilhamento de arquivos no Skype for Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- É necessário haver um Servidor do Office Web Apps/Servidor do Office Online para habilitar a função de apresentação do PowerPoint em grandes reuniões. O Servidor do Office Web Apps/Servidor do Office Online pode ser dedicado ao pool de grandes reuniões ou pode ser o mesmo Servidor do Office Web Apps/Servidor do Office Online usado por outros pools no site em que o pool dedicado está implantado. Para obter mais informações, consulte [Configurar a integração com o servidor do Office Web Apps no Skype for Business Server](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Os Servidores Front-End exige balanceamento de carga para tráfego HTTP (como download de conteúdo de reunião). O balanceamento de carga DNS é recomendado para tráfego SIP. Para obter detalhes, consulte [Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Se você quiser usar o Monitoring Server para o pool de reunião dedicada a grandes dimensões, recomendamos usar o Monitoring Server e seu banco de dados que são compartilhados entre todos os pools de servidores front-end na implantação do Skype for Business Server. Para obter mais informações, consulte [planejar o monitoramento no Skype for Business Server](../../plan-your-deployment/monitoring.md).
    

