---
title: Skype para soluções híbridas de negócios
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/18/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Uma discussão das soluções híbridas disponíveis no Skype para Business Server 2019.
ms.openlocfilehash: 2909f524d1b9984fe01700a89d1bf6dc1b70f100
ms.sourcegitcommit: 112dc19075f9213207fde9e30bcde5681324b7c9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2018
ms.locfileid: "25696223"
---
OBSERVAÇÃO: A SEGUIR É COPIADA DO 2015 E ESTÁ EM ANDAMENTO. Conteúdo de espaço reservado de em andamento adicionais pode ser encontrado [abaixo](#placeholder-topic-for-hybrid-solutions).


# <a name="skype-for-business-hybrid-solutions"></a>Skype para soluções híbridas de negócios

Encontre informações sobre como planejar uma Skype para implantação híbrida do Business. 
  
Este tópico apresenta várias configurações híbridas que o ajudarão a determinar a melhor configuração para sua empresa. Depois, para saber mais sobre a configuração de seu interesse, siga os links a seguir. Este tópico inclui as seguintes seções:
  
- [Configurações híbridas do Skype for Business](hybrid-solutions.md#BKMK_HybridConfigurations)
    
- [Adicionar Skype para negócios Online em sua existente no local Skype para ambiente de negócios](hybrid-solutions.md#BKMK_HybridConnectivity)
    
- [Aproveite o Sistema de Telefonia do Office 365 (Cloud PBX)](hybrid-solutions.md#BKMK_CloudPBX)
    
- [Integração entre o Exchange e o SharePoint](hybrid-solutions.md#BKMK_IntegratewExchangeSharePoint)
    
- [Tarefas para planejar e configurar um ambiente híbrido](hybrid-solutions.md#BKMK_Tasks)
    
- [Para obter mais informações](hybrid-solutions.md#BKMK_MoreInfo)
    
## <a name="skype-for-business-hybrid-configurations"></a>Configurações híbridas do Skype for Business
<a name="BKMK_HybridConfigurations"> </a>

Skype para a empresa oferece suporte a várias configurações de híbridas. Você pode adicionar Skype para Business Online em sua atual local Skype para ambiente de negócios, integrar seu Skype para implantação de negócios com o Exchange Online e SharePoint Online e aproveitar o sistema telefônico no Office 365 (nuvem PBX) — da Microsoft tecnologia para habilitar o controle de chamada e os recursos de Private Branch Exchange (PBX) no Office 365 nuvem com Skype para Business Online. 
  
Com um Skype para implantação híbrida do Business, você deve combinar uma Skype para assinatura Business Online com Skype seu local para a oferta de negócios. Você pode começar a construir as habilidades de gerenciamento de software como serviço em sua organização e mover sua Skype para usuários comerciais para a nuvem em seu próprio ritmo. Os usuários hospedados na nuvem podem aproveitar sistema telefônico no Office 365 enquanto mantém a conectividade da rede de telefônica pública comutada (PSTN) local.
  
Com um Skype para configuração híbrida de negócios, lembre-se do seguinte:
  
- Pode haver usuários hospedados localmente e outros online, mas todos compartilham o mesmo domínio SIP; por exemplo, contoso.com.
    
- Você pode migrar usuários do Skype for Business no local para Skype para Business Online ao longo do tempo, no seu calendário.
    
- Você pode fazer a integração com outros aplicativos do Microsoft Office 365, como o Exchange Online e o SharePoint Online.
    
- Você pode fazer a integração com o Exchange e o SharePoint.
    
- Você pode utilizar a Transmissão de Reunião do Skype.
    
- Você pode utilizar a Conferência PSTN.
    
## <a name="add-skype-for-business-online-into-your-existing-on-premises-skype-for-business-environment"></a>Adicionar Skype para negócios Online em sua existente no local Skype para ambiente de negócios
<a name="BKMK_HybridConnectivity"> </a>

Conectividade híbrida entre Skype para Business Server e do Skype para Business Online significa que os usuários de um domínio, por exemplo, contoso.com, são divididos entre usando Skype para Business Server no local e Skype para Business Online. Alguns usuários do domínio são hospedados no local, e outros são hospedados online. Você pode configurar sua implantação no local para o híbrido com Skype para Business Online e usar a sincronização do Active Directory para manter seu local e online usuários sincronizados. 
  
O diagrama a seguir mostra como você pode adicionar Skype para Business Online em sua Skype local existente para o ambiente de negócios, permitindo que você mova os usuários para a nuvem em seu próprio ritmo:
  
![Configurações híbridas do Skype for Business](../../sfbserver/media/4580f2c8-7008-4c6e-826c-020d0f2d1636.png)
  
Para obter mais informações, consulte [Planejar a conectividade híbrida entre Skype para Business Server e do Skype para Business Online ou equipes](plan-hybrid-connectivity.md) e a [Configurar a conectividade de híbrido entre Skype para Business Server e do Skype para negócios Online](configure-hybrid-connectivity.md).
  
## <a name="take-advantage-of-phone-system-in-office-365-cloud-pbx"></a>Aproveite o Sistema de Telefonia do Office 365 (Cloud PBX)
<a name="BKMK_CloudPBX"> </a>

 Sistema telefônico no Office 365 (nuvem PBX) é uma tecnologia da Microsoft para habilitar o controle de chamada e os recursos de Private Branch Exchange (PBX) no Office 365 nuvem com Skype para Business Online. Esse sistema permite que você substitua seu sistema PBX existente por um conjunto de recursos fornecidos diretamente pelo Office 365, que está bem integrado com a experiência de produtividade da nuvem Microsoft.
  
Além de sistema telefônico duas no Office 365 ofertas de híbrido, a Microsoft oferece o sistema telefônico no Office 365 com chamar planejar — uma PSTN chamando serviço — para uma solução de all nuvem que não requer uma implantação de servidor local. Para decidir se o sistema telefônico no Office 365 com chamar planejar pode ser a solução certa para sua organização, consulte [Sistema telefônico nas soluções do Office 365](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings).
  
Há duas ofertas híbridas para o Sistema de Telefonia do Office 365:  
  
- [Sistema de Telefonia do Office 365 com conectividade local fornecida pela implantação do Skype for Business Server](hybrid-solutions.md#BKMK_Server)
    
- [Sistema de Telefonia do Office 365 com conectividade local fornecida pelo Skype for Business Server Cloud Connector Edition](hybrid-solutions.md#BKMK_CCE)
    
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-your-skype-for-business-server-deployment"></a>Sistema de Telefonia do Office 365 com conectividade local fornecida pela implantação do Skype for Business Server
<a name="BKMK_Server"> </a>

Essa configuração consiste em um Skype para implantação de local Business Server modificada para o híbrido PSTN. Usuários hospedados na nuvem em sua organização podem receber serviços PBX de nuvem da Microsoft, mas a conectividade PSTN é fornecida por meio do Enterprise Voice em sua Skype local para implantação de servidor de negócios. 
  
![Cloud PBX com implantação do Skype for Business Server](../../sfbserver/media/d4136bbc-b01e-469c-bf94-90ba59c61cda.png)
  
Essa é a melhor configuração quando: 
  
- Seu PBX não oferece recursos exclusivos que você precisa manter.
    
- O Plano de Chamadas, o serviço de chamadas PSTN do Office 365, não está disponível na sua região.
    
- Possui um Lync existente ou Skype para implantação de servidor de negócios.
    
Para obter mais informações, consulte [Planejar o sistema de telefone no Office 365 com conectividade PSTN em Skype para Business Server local](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md) e [habilitar usuários para o sistema telefônico no Office 365 com conectividade PSTN local no Skype para Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system.md).
  
### <a name="phone-system-in-office-365-with-on-premises-connectivity-provided-by-skype-for-business-server-cloud-connector-edition"></a>Sistema de Telefonia do Office 365 com conectividade local fornecida pelo Skype for Business Server Cloud Connector Edition
<a name="BKMK_CCE"> </a>

Essa configuração consiste em um conjunto de VMs (máquinas virtuais) empacotadas que implementam a conectividade PSTN local. Implantando um Skype mínimo para a topologia de servidor de negócios em um ambiente virtualizado, os usuários em sua organização hospedados na nuvem podem receber serviços PBX de nuvem da Microsoft, mas conectividade PSTN é fornecida por meio de voz no local existente infraestrutura. 
  
![CloudPBXCloudConnectorEdition](../../sfbserver/media/7a6ee221-bfe1-422b-ac44-6446db6b766c.png)
  
Essa é a melhor configuração quando:
  
- Seu PBX não oferece recursos exclusivos que você precisa manter.
    
- O Plano de Chamadas, o serviço de chamadas PSTN do Office 365, não está disponível na sua região.
    
- Você não tem um Lync existente ou Skype para implantação de servidor de negócios.
    
Para obter mais informações, consulte [Planejar Skype para o conector de nuvem Business Edition](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md).
  
## <a name="integrate-with-exchange-and-sharepoint"></a>Integração entre o Exchange e o SharePoint
<a name="BKMK_IntegratewExchangeSharePoint"> </a>

Um Skype para configuração híbrida de negócios permite a integração com outros aplicativos do Microsoft Office 365, incluindo o Exchange Online e SharePoint Online.
  
### <a name="skype-for-business-server-with-exchange-online-and-sharepoint-online"></a>Skype for Business Server com Exchange Online e SharePoint Online

Você pode integrar Skype para Business Server com o Exchange Online e SharePoint Online, conforme mostrado no diagrama a seguir:
  
![Skype for Business Server com Exchange Online e SharePoint Online](../../sfbserver/media/9f456ed2-8777-4a20-a519-c87dfc56b7f5.png)
  
Integrando Skype for Business Server com o Exchange Online e SharePoint Online tem várias vantagens. Você pode:
  
- Use o conjunto completo de recursos do Skype para Business Server.
    
- Aproveitar seu equipamento telefônico local existente, como os PBXs.
    
- Usar o email do Exchange Online, aliviando a carga de armazenamento e dos servidores locais de email.
    
- Usar a colaboração do SharePoint Online, aliviando a carga de manutenção dos servidores locais do SharePoint.
    
- Uso Skype para negócios, Exchange e SharePoint integrado de recursos, incluindo Unified Messaging (UM) no Office 365.
    
Para obter mais informações, consulte [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
### <a name="exchange-server-with-skype-for-business-online"></a>Exchange Server com Skype for Business Online

Você pode integrar o Exchange Server com Skype para Business Online conforme mostrado no diagrama a seguir:
  
![Integrar o Exchange com o Skype for Business Online](../../sfbserver/media/e8ca44ad-f47c-46a3-9cef-8fe7deafd615.png)
  
Integrando o Exchange Server com Skype for Business Online tem as seguintes vantagens:
  
- Aproveitamento da infraestrutura existente do Exchange.
    
- Use o Skype para Business Online para recursos de presença, mensagens Instantâneas e conferência. 
    
Para obter mais informações, consulte [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).
  
## <a name="tasks-for-planning-and-configuring-a-hybrid-environment"></a>Tarefas para planejar e configurar um ambiente híbrido
<a name="BKMK_Tasks"> </a>

Skype para negócios fornece um conjunto rico de recursos, independentemente de como você planejar a implantação. A arquitetura escolhida determina quais são as suas responsabilidades de TI e quais estão incluídas na assinatura de suporte da Microsoft. Independentemente de qual seja a melhor arquitetura para sua organização, você sempre será responsável por cinco itens principais:
  
- **Rede e conectividade** - garantir a capacidade de rede e a disponibilidade por meio de firewalls, servidores proxy, gateways e em links de WAN executando uma avaliação de rede ou por contratar com um parceiro a fim de fazer a avaliação.
    
- **Governança dados &amp; gerenciamento de direitos** - classificar seus dados confidenciais e certifique-se ele está protegido e monitorado onde ele está armazenado e enquanto ele está em trânsito.
    
- **Pontos de extremidade do cliente** - estabelecer, medir e impor padrões de segurança moderno em dispositivos que são usados para acessar seus dados e ativos.
    
- **Conta &amp; gerenciamento de acesso** - estabelecer um perfil para atividade de conta "normal" e a atividade incomum de alerta.
    
- **Identidades** - use credenciais protegidas por hardware ou pela MFA (Autenticação Multifator) para todas as identidades. 
    
Além das tarefas relacionadas à arquitetura que você realiza em seu ambiente local, também será necessário:
  
- Planejar e criar requisitos de gerenciamento de identidades, incluindo a integração de identidades locais com o Office 365.
    
- Garantir a capacidade e a disponibilidade da rede.
    
- Adquirir certificados SSL de terceiros para proporcionar segurança corporativa às ofertas de serviços do Office 365.
    
- Decidir se você deseja se conectar ao Office 365 usando o protocolo IPv6.
    
- Determine quanto integração de recurso com o local e a versões online do Skype para negócios, Exchange e SharePoint for desejada. 
    
- Determinar qual dispositivo de servidor proxy será usado para as solicitações do Office 365.
    
Você também precisará executar o acompanhamento tarefas profissional de TI para implementar sua Skype para ambiente híbrido de negócios:
  
- Certifique-se de que você tem um locatário do Microsoft Office 365 com Skype para Business Online habilitado.
    
- Implementar o plano de gerenciamento de identidades.  
    
- Planejar e implementar os registros e o roteamento DNS interno e externo.
    
- Configurar o proxy ou o firewall com os requisitos de endereço IP e URL do Office 365.
    
- Administrar contas de usuário e Skype para configurações de negócios Online. 
    
- Configurar o dispositivo de servidor proxy, se necessário.  
    
- Configurar a integração de recursos com as versões locais e online do Exchange Server e do SharePoint.
    
## <a name="for-more-information"></a>Para obter mais informações
<a name="BKMK_MoreInfo"> </a>

Para obter mais informações, confira:
  
- [Recursos da arquitetura de TI da nuvem da Microsoft](https://aka.ms/clouditarch)
    
- [Identidade da nuvem da Microsoft para arquitetos corporativos](https://docs.microsoft.com/en-us/office365/enterprise/microsoft-cloud-it-architecture-resources#identity)
    
- [Preparar a sua organização para o Office 365 Enterprise](https://aka.ms/O365EntPrep)
    
- [Planejar a conectividade híbrida entre Skype para Business Server e do Skype Business Online ou equipes](plan-hybrid-connectivity.md)
    
- [Configurar a conectividade híbrida entre Skype para Business Server e do Skype para negócios Online](configure-hybrid-connectivity.md)
    
- [Sistema telefônico nas soluções do Office 365](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-your-phone-system-cloud-pbx-solution.md#BKMK_PBXOfferings)
    
- [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
    
Para baixar a versão deste tópico em .pdf:
  
- [Modelos de arquitetura do Skype for Business (pdf)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.pdf)
    
- [Modelos de arquitetura do Skype for Business (Visio)](https://download.microsoft.com/download/7/7/4/7741262C-A60D-41F7-863B-99BF5964FBFE/Skype%20for%20Business%20Architectural%20Models.vsd)
    

### <a name="placeholder-topic-for-hybrid-solutions"></a>TÓPICO DE ESPAÇO RESERVADO PARA SOLUÇÕES HÍBRIDAS 

EM ANDAMENTO...


Talvez você também conheça o termo "hybrid voice", que se refere a troncos de voz no local que fornecem funcionalidades para usuários hospedados na nuvem. O Hybrid Voice permite a migração para a nuvem enquanto preserva a configuração de voz local. Se você já tem uma implantação do Skype for Business Server, o primeiro passo para habilitar o Hybrid Voice é configurar um ambiente de domínio dividido. 
  
Por exemplo, suponha que sua empresa tem um campo celular grande organização que requer o PBX mínima de suporte voz, mas use Smartphone extensiva. Você pode optar por migrar esses usuários para a nuvem para tirar proveito do Sistema de Telefonia da Microsoft no Office 365 (Cloud PBX). Se a sua empresa também tem uma central de atendimento de grande no local que requer o software avançado e complexos center contato como parte do seu PBX local, você pode optar por deixar esses usuários no local. Os usuários hospedados online e no local têm conectividade PSTN por meio da sua implantação local.
  
O diagrama a seguir mostra uma implantação do Hybrid Voice do Skype for Business:
  
![Domínio dividido do SfB com Cloud PBX](../../sfbserver/media/5e755772-269e-45ce-8b48-2e06ababfe6c.png)
  
Para obter mais informações sobre como configurar uma solução de voz híbrida com sua Skype para implantação de servidor de negócios, consulte [Planejar o sistema de telefone no Office 365 com conectividade PSTN local no Skype para Business Server](../../sfbserver/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity.md). 
  
Você também pode configurar implantações híbridas para integração com o Exchange e SharePoint, ou local com aplicativos do Microsoft Office 365, incluindo o Exchange Online e SharePoint Online. Você também pode configurar uma solução de voz híbrida que não requer uma implantação completa do Skype for Business Server, usando a Cloud Connector Edition. Para obter mais informações sobre todos os Skype para soluções híbridas de negócios e planejamento da mudança para a nuvem, consulte [Skype para soluções híbridas de negócios](hybrid-solutions.md).


## <a name="exchange-co-existence"></a>Coexistência do Exchange
<a name="BKMK_Exchange"> </a>

Para dar suporte à coexistência com o Exchange, considere o seguinte:
  
- A prática recomendada é mover a caixa de correio do usuário para o Exchange Online antes de mover Skype do usuário for Business residencial.
    
- Os usuários com caixas de correio locais do Exchange têm suporte com as seguintes limitações conhecidas:
    
  - Logon do cliente: talvez os usuários precisem fazer logon duas vezes durante o logon do cliente no SfB
    
  - Server side histórico da conversa, arquivamento, o repositório unificado de contatos, a foto HighRes exige o Exchange 2013 ou posterior e você deve ativar o servidor OAuth comunicação entre servidores. Para obter mais informações, consulte [gerenciar autenticação de servidor-para-servidor (OAuth) e aplicativos de parceiros no Skype para Business Server 2015](https://technet.microsoft.com/en-us/library/jj204817.aspx).
    
Para obter detalhes sobre a coexistência com o Exchange Server, incluindo os critérios e as limitações de suporte em várias combinações de local e online, consulte [Suporte aos recursos](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) em [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).



**TERMINOLOGIA**

unidade organizacional saberá mais sobre a configuração do Active Directory nas seções a seguir. Mas, primeiro, apresentamos uma visão geral da terminologia e dos acrônimos usados nos diagramas abaixo e em vários tópicos sobre conectividade híbrida:
  
- PSTN - Rede Telefônica Pública Comutada
    
- PBX - sistema de telefonia com central privada de comutação telefônica
    
- Sistema de Telefonia - opção de sistema de telefonia Cloud PBX da Microsoft
    
- Tronco - linha de telefonia que conecta PBXs à PSTN — um tronco pode usar o protocolo de iniciação de sessão (SIP) — uma Voice over Internet Protocol (VoIP) — ou a tecnologia de multiplexação de divisão de tempo (TDM) mais antiga 
    
- SBC - controlador de borda da sessão - dispositivo que serve como firewall e roteador nas redes telefônicas. Por exemplo, ele fornece segurança, conectividade, interoperabilidade e Qualidade de Serviço. 
    
- Gateway PSTN - um dispositivo que serve como roteador em redes telefônicas, capaz de fazer quase tudo o que um SBC faz, exceto segurança e NAT transversal.
    
O diagrama a seguir mostra um Skype para configuração do Business "domínio dividido" híbrida. Os usuários A e B estão hospedados online, mas podem ser detectados por usuários locais; os usuários C e D estão hospedados no local, mas podem ser detectados por usuários online.
  

