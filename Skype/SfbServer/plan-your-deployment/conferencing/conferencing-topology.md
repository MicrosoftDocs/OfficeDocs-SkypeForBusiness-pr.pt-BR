---
title: Planejar sua topologia de conferência para o Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: 'Resumo: Leia este tópico para saber mais sobre como planejar sua topologia de conferência no Skype Business Server 2015.'
ms.openlocfilehash: b81a8eeb1300fa6bad887ba923c28fc4d2676fe8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server-2015"></a>Planejar sua topologia de conferência para o Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber mais sobre como planejar sua topologia de conferência no Skype Business Server 2015.
  
Este tópico descreve os conhecimentos básicos de topologia de conferências no Skype for Business Server 2015:
  
- Topologias suportadas
    
- Considerações sobre a conferência discada
    
- Considerações sobre a webconferência
    
- Requisitos para grandes reuniões
    
Para obter mais informações sobre os requisitos de hardware e software, consulte [requisitos de Hardware e software para conferências no Skype para Business Server 2015](hardware-and-software-requirements.md).
  
## <a name="supported-topologies"></a>Topologias suportadas

Skype para Business Server, o servidor que executa serviços de conferência é sempre colocado com os servidores de servidores Front-End ou Standard Edition. Quando você implanta o Skype para Business Server, recursos de conferência de mensagem Instantânea serão implantados automaticamente. É possível especificar a implantação de web, áudio e vídeo (A/V) e conferência discada usando o Construtor de Topologias. Você também pode usar o Construtor de Topologias para adicionar conferências a uma implantação existente. Para obter detalhes sobre noções básicas de topologia e colocação cenários, consulte [Noções básicas de topologia para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).
  
É possível implantar a conferência discada nas seguintes topologias e configurações:
  
- Skype para Business Server Standard Edition
    
- Skype para Business Server Enterprise Edition
    
- Com ou sem Enterprise Voice
    
## <a name="dial-in-conferencing-considerations"></a>Considerações sobre a conferência discada

Se você estiver implantando a conferência discada, será necessário considerar o seguinte:
  
-  Conferência discada requer um servidor de mediação para convertem a sinalização (e mídia em algumas configurações) entre Skype para Business Server e o gateway PSTN e um gateway PSTN para converter a sinalização e mídia entre o servidor de mediação e o gateway PSTN .
    
    Antes de configurar a conferência discada, é necessário implantar o Enterprise Voice ou um Servidor de Mediação e pelo menos um dos seguintes:
    
  - Gateway PSTN
    
  - IP-PBX
    
  - Controlador de Borda de Sessão (SBC) (para um provedor de serviços de telefonia pela Internet ao qual você se conecta configurando um tronco SIP)
    
- Você pode implantar o serviço de Aplicativo, o aplicativo Atendedor de Conferência e aplicativo Comunicado de Conferência em um local central, mas não no local da filial.
    
- Você deve implantar a conferência discada em cada pool onde você implanta o Skype para conferências Business Server. Não é necessário atribuir números de acesso em cada pool, mas é necessário implantar o recurso de conferência discada em cada pool. Esse requisito oferece suporte ao recurso de nome registrado quando um usuário disca um número de acesso de um pool para ingressar em uma Skype para conferência Business Server em um pool diferente. 
    
Para obter mais informações, consulte [Planejar a conferência discada no Skype para Business Server 2015](dial-in-conferencing.md).
  
## <a name="web-conferencing-considerations"></a>Considerações sobre a webconferência

A webconferência requer o seguinte: 
  
- O acesso ao repositório de arquivos, usado para armazenar conteúdo de webconferências.
    
- Integração com o Servidor do Office Web Apps/Servidor do Office Online, necessárias para compartilhar arquivos do PowerPoint durante uma conferência.
    
> [!NOTE]
> A iteração mais recente do Office Web Apps Server é nomeada Office Online Server, que é suportado pelo Skype para Business Server 2015. Para obter mais detalhes, consulte a [documentação do servidor do Office Online](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx). 
  
Skype para Business Server oferece as seguintes maneiras de configurar o Office Web Apps Server/Office Online Server. Dependendo de seus requisitos, você pode:
  
- **Instale os dois Skype para Business Server e Office Web Apps Server/Office Online Server local atrás do firewall da organização e na mesma zona de rede.** Com essa topologia, o acesso externo ao Servidor do Office Web Apps/Servidor do Office Online será fornecido pelo servidor de proxy reverso. Idealmente, você deve instalar o Office Web Apps Server/Office Online Server na mesma zona do Skype para Business Server.
    
    Skype externo para clientes corporativos pode se conectar para Skype para Business Server e Office Web Apps Server/Office Online Server usando um servidor proxy reverso, que é um servidor que recebe as solicitações da Internet e encaminha para a rede interna. (Os clientes internos não precisará usar o servidor proxy reverso, porque eles podem se conectar ao servidor on-line do Office Web Apps Server/Office diretamente.) Esta topologia funciona melhor se você quiser usar um farm dedicado do Office Web Apps Server/Office Online Server que é usado somente pelo Skype para Business Server.
    
- **Use um implantado externamente Office Web Apps Server/Office Online Server.** Nessa topologia, Skype para Business Server é implantados no local e usa um Office Web Apps Server/Office Online Server implantado fora do Skype para zona de rede do servidor de negócios. Isso pode acontecer quando o Office Web Apps Server/Office Online Server é compartilhado entre vários aplicativos na empresa e é implantado em uma rede que exigem Skype para Business Server usar a interface externa do servidor on-line do Office Web Apps Server/escritório e vice-versa.
    
    Você não precisará instalar um servidor proxy reverso. em vez disso, todas as solicitações do servidor Office Web Apps Server/Office Online para Skype para Business Server são roteadas por meio do seu servidor de borda. Interna e sua Skype externo para clientes corporativos se conectar ao Office Web Apps Server/Office Online Server usando a URL externa.
    
    Se o Office Web Apps Server/Office Online Server for implantado fora do firewall interno, selecione a opção o **que Office Web Apps Server é implantado em uma rede externa** (ou seja, de perímetro/Internet) no construtor de topologia.
    
Para obter mais informações, consulte [Configure integração com o Office Web Apps Server no Skype para Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md). 
  
Independentemente da topologia selecionada, é fundamental que as portas do firewall certas estejam abertas. Você deve certificar-se de que nomes DNS, endereços IP e portas não estão bloqueadas por firewalls no Skype, o balanceador de carga ou o Office Web Apps Server/Office Online Server para Business Server.
  
> [!NOTE]
> Outra opção para fornecer acesso externo ao Servidor do Office Web Apps/Servidor do Office Online é implantar o servidor em uma rede de perímetro. Se você optar por fazer isso, tenha em mente que a instalação do Servidor do Office Web Apps/Servidor do Office Online requer que o computador servidor seja membro do seu domínio do Active Directory. A menos que sua política de rede permita computadores na rede de perímetro como membros do domínio do Active Directory, é recomendado não instalar o Servidor do Office Web Apps/Servidor do Office Online na rede de perímetro. Em vez disso, instale o Servidor do Office Web Apps/Servidor do Office Online na rede interna e dê acesso ao usuário externo através do servidor de proxy reverso.  
  
## <a name="topology-requirements-for-large-meetings"></a>Requisitos de topologia para grandes reuniões

Uma grande reunião exige pelo menos um Servidor Front-End e um Servidor Back-End. No entanto, para permitir alta disponibilidade, recomendamos um pool com dois Servidores Front-End com Servidores Back-End espelhados, como exibido no diagrama a seguir:
  
**Topologia de reunião grande**

![Topologia de grandes reuniões](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
O usuário que hospeda as grandes reuniões deve ter sua conta de usuário hospedada nesse pool de Front-Ends. No entanto, não recomendamos que você hospede outras contas de usuário nesse pool. Em vez disso, use-o apenas para reuniões grandes. A prática recomendada é criar uma conta de usuário especial nesse pool para ser usada apenas para hospedar reuniões grandes. Já que a definição de grandes reuniões é otimizada para um melhor desempenho, usá-la como usuário normal poderia gerar problemas como incapacidade de promover uma sessão de P2P em uma reunião quando um ponto de extremidade de PSTN estiver envolvido.
  
Gerenciar um pool com exatamente dois Servidores Front-End exige algumas considerações especiais. Para obter mais informações, consulte [Noções básicas de topologia para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md) e [topologias de referência para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md).
  
Além disso, se você quiser oferecer failover e backup de recuperação de desastres para o pool usado em grandes reuniões, poderá emparelhar com um pool dedicado de configuração semelhante em outro datacenter. Para obter detalhes, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
Observações adicionais sobre a topologia incluem:
  
- Um compartilhamento de arquivo é necessário para armazenar conteúdo da reunião e, se o Servidor de Arquivamento estiver implantado e habilitado, armazenar os arquivos de arquivo. O compartilhamento de arquivo pode ser dedicado ao pool ou pode ser o mesmo compartilhamento de arquivo usado por outro pool no site em que o pool é implantado. Para obter detalhes sobre como configurar o compartilhamento de arquivos, consulte [criar um compartilhamento de arquivo no Skype para Business Server 2015](../../deploy/install/create-a-file-share.md).
    
- É necessário haver um Servidor do Office Web Apps/Servidor do Office Online para habilitar a função de apresentação do PowerPoint em grandes reuniões. O Servidor do Office Web Apps/Servidor do Office Online pode ser dedicado ao pool de grandes reuniões ou pode ser o mesmo Servidor do Office Web Apps/Servidor do Office Online usado por outros pools no site em que o pool dedicado está implantado. Para obter mais informações, consulte [Configure integração com o Office Web Apps Server no Skype para Business Server 2015](../../deploy/deploy-conferencing/office-web-app-server.md). 
    
- Os Servidores Front-End exige balanceamento de carga para tráfego HTTP (como download de conteúdo de reunião). O balanceamento de carga DNS é recomendado para tráfego SIP. Para obter detalhes, consulte [requisitos do Skype para negócios de balanceamento de carga](../../plan-your-deployment/network-requirements/load-balancing.md). 
    
- Se desejar usar o Monitoring Server para o pool de reunião grande dedicado, recomendamos usando o Monitoring Server e seu banco de dados que são compartilhados em todos os pools de servidor Front-End da sua Skype para implantação de servidor de negócios. Para obter mais informações, consulte [Plan for monitoring no Skype para Business Server 2015](../../plan-your-deployment/monitoring.md).
    

