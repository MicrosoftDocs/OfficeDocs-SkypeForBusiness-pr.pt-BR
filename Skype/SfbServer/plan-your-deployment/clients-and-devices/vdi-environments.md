---
title: Planejar para o Skype for Business em ambientes VDI
author: lanachin
ms.author: v-lanac
ms.reviewer: krishra
manager: serdars
ms.date: 1/9/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ea68414b-bb7e-483a-b731-b6b5a44372b1
description: Este tópico aborda as considerações de planejamento para usar o Skype for Business enquanto se conecta a uma área de trabalho virtual remota.
ms.openlocfilehash: 958c13821eea46be91d51d7399722d2af433ccf0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277283"
---
# <a name="plan-for-skype-for-business-in-vdi-environments"></a>Plan for Skype for Business in VDI environments
 
Este tópico aborda as considerações de planejamento para usar o Skype for Business enquanto se conecta a uma área de trabalho virtual remota. 
  
Um ambiente VDI (Virtual Desktop Infrastructure) é usado em algumas organizações onde questões de segurança e conformidade são especialmente sensíveis. Seus usuários trabalham em uma área de trabalho virtual com todos os arquivos e aplicativos da área de trabalho usando Serviços de Área de Trabalho Remota ou uma conexão remota similar. Usar o Skype for Business com áudio e vídeo completos em uma conexão como essa requer grandes cargas de processamento de áudio e vídeo no cliente hospedado em uma área de trabalho virtual. O software de plug-in VDI adicional está disponível para transferir esse processamento para a máquina local do usuário final e reduz a carga na área de trabalho virtual.
  
Há três soluções disponíveis para o componente plug-in VDI, oferecido pela Microsoft, Citrix ou VMWare. Para novas implantações, a Microsoft recomenda o uso da solução do pacote de otimização do Citrix HDX em tempo real ou do pacote de virtualização do VMWare Horizon. O plug-in do VDI do Lync original ainda tem suporte para o restante do seu ciclo de vida.
  
- O **plug-in VDI do Lync** foi desenvolvido para o Lync 2013 e é compatível com o cliente do Lync 2013 ou do Skype for Business 2015 em execução em uma área de trabalho virtual. It's a stand-alone application that installs on the local computer and allows the use of local audio and video devices with a client on a virtual desktop. O plug-in não requer que um cliente Skype for Business seja instalado no computador local ou cliente leve, que deve executar os sistemas operacionais Windows 7, Windows 8 ou Windows Server 2008. (Os dispositivos cliente fino que usam esses sistemas operacionais e suportados pela Microsoft incluem: Dell Wyse Z90D7, Dell Wyse R90L7, Dell Wyse X90m7, HP T610 e HP t5740e.) Este plug-in ainda tem suporte, mas nenhuma atualização futura é planejada. For Citrix-based virtual environments, the Citrix RealTime Optimization Pack is recommended.
    
- O **pacote de otimização em tempo real do Citrix** é criado no plug-in VDI do Lync e funciona com clientes do Lync 2013 ou do Skype for Business 2016 em uma área de trabalho virtual. Ele foi desenvolvido em parceria entre a Citrix e a Microsoft para aperfeiçoar o plug-in VDI original. Esse pacote pode ser instalado em clientes com sistemas operacionais Windows e não Windows (inclusive Windows 10, Mac e Linux). Ele consiste em dois componentes: o conector em tempo real (que é instalado na área de trabalho virtual) e o mecanismo de mídia em tempo real (que é instalado no computador local do usuário final). Esses dois componentes permitem que o computador local do usuário use o cliente Skype for Business executado na área de trabalho virtual com o processamento a/V movido para o computador local. Para ambientes de área de trabalho virtual baseados em Citrix, recomenda-se a utilização do Citrix RealTime Optimization Pack, para o qual há mais suporte planejado.
    
- O **pacote** de virtualização de horizonte do VMware para o Skype for Business, desenvolvido em colaboração com o VMware, permite que você forneça o Skype for Business em uma área de trabalho virtual enquanto oferece uma excelente experiência do usuário. A solução funciona aproveitando um mecanismo de mídia no cliente para criar uma solução otimizada, com o ponto de extremidade do cliente fornecendo recursos de offload de mídia para chamadas de áudio e vídeo. Esta solução que pode oferecer áudio e vídeo diretamente entre pontos de extremidade para colaboração única ou o transfere para uma unidade de controle multiponto (MCU) central para chamadas em conferência ou reuniões de vários participantes.
    
> [!NOTE]
> Os clientes do Skype for Business Basic não são compatíveis com o pacote de otimização do Citrix HDX RealTime ou o pacote de virtualização do VMWare Horizon. 
  
## <a name="citrix-hdx-realtime-optimization-pack"></a>Citrix HDX RealTime Optimization Pack
<a name="Citrix_RT"> </a>

O plug-in do ambiente VDI do Citrix (um recurso do XenApp e do XenDesktop) é compatível com o Lync 2013 e com o Skype for Business 2015 e o 2016 (clientes completos que usam qualquer clique para executar o programa de instalação ou instaladores MSI lançados após os 2017 da PU) instalados em um virtual Desktop. Seu funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma ampla variedade de sistemas operacionais cliente, incluindo Windows 10, Macintosh e Linux.
  
Uma lista completa dos recursos e das tecnologias compatíveis podem ser encontradas no website da Citrix em [oferecer o Microsoft Skype for Business a usuários do XenApp e do XenDesktop](https://www.citrix.com/content/dam/citrix/en_us/documents/products-solutions/delivering-microsoft-lync-to-xenapp-and-xendesktop-users.pdf).
  
Confira os seguintes links para obter mais informações:
  
- Pacote de otimização do Citrix [HDX RealTime 2,1](https://docs.citrix.com/en-us/hdx-optimization/2-1.mdl)
    
- [Visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-1/about.mdl)
    
- [Suporte do recurso CTX200279 Skype for Business](https://support.citrix.com/article/CTX200279)
    
## <a name="vmware-horizon-virtualization-pack"></a>Pacote de virtualização de horizonte VMWare
<a name="Citrix_RT"> </a>

A solução de ambiente VDI do VMWare é compatível com os clientes completos do Skype for Business 2015 e do 2016 instalados em uma área de trabalho virtual. Seu funcionamento geral é baseado no plug-in VDI do Microsoft Lync, mas funciona em uma ampla variedade de sistemas operacionais cliente, incluindo Windows 10, Macintosh e Linux. 
  
Uma discussão completa dos recursos e das tecnologias compatíveis podem ser encontradas no website do VMWare nos seguintes links:
  
- [Novidades do cliente horizonte 7,4 &amp; horizonte do VMware 4,7](https://blogs.vmware.com/euc/2018/01/vmware-horizon-7-4-horizon-client-4-7-whats-new.mdl)
    
- [Pacote de virtualização de horizonte para o Skype for Business](https://www.vmware.com/products/horizon/skype-for-business.mdl)
    
- [Microsoft Skype for Business com VMWare horizonte](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/products/horizon/vmware-skype-for-business-solution-brief.pdf)
    
## <a name="microsofts-lync-vdi-plug-in"></a>Plug-in VDI do Microsoft Lync
<a name="Citrix_RT"> </a>

Com a solução de plug-in VDI do Microsoft Lync, o usuário precisa estar em um computador com Windows ou cliente leve e ter o plug-in VDI do Lync instalado para manipular fluxos de áudio/vídeo do cliente na área de trabalho virtual. O usuário deve:
  
1. Conectar um dispositivo de áudio/vídeo (como um fone de ouvido com microfone ou uma câmera) a um computador local.
    
2. Conecte-se a uma área de trabalho virtual remota com um cliente do Lync 2013 ou Skype for Business 2015.
    
3. Insira as credenciais do Skype for Business na área de trabalho virtual.
    
4. Insira novamente as credenciais do usuário para estabelecer uma conexão com o plug-in VDI do Lync no computador local do Windows ou cliente leve.
    
Depois que uma conexão é estabelecida, o usuário está pronto para fazer e receber chamadas de áudio e vídeo. O tráfego na rede e a carga na área de trabalho virtual são minimizados, pois o computador local faz o processamento de áudio e vídeo.
  
O plug-in VDI do Lync da Microsoft só tem suporte em determinados sistemas operacionais Windows e só oferece suporte ao Lync 2013 ou ao Skype for Business 2015 clientes. Consulte [Tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt) para ver mais detalhes sobre as tecnologias compatíveis e as limitações.
  
Confira os seguintes links para obter mais informações:
  
- [Tecnologias de virtualização suportadas e limitações conhecidas](vdi-environments.md#Supported_virt)
    
- [Pré-requisitos do plug-in VDI do Lync](vdi-environments.md#VDI_prereq)
    
- [Implantar o plug-in VDI do Lync com o Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)
    
- Artigo [CTX138408](https://support.citrix.com/article/CTX138408) da central de conhecimento da Citrix
    
O plug-in VDI da Microsoft está disponível no plugin [do Microsoft LYNC vdi 2013 (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou no [plugin do microsoft Lync vdi 2013 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454). Esse plugin é compatível com o cliente Skype for Business 2015, apesar do nome.
  
### <a name="supported-virtualization-technologies-and-known-limitations"></a>Tecnologias de virtualização suportadas e limitações conhecidas
<a name="Supported_virt"> </a>

O plug-in VDI do Lync permite chamadas de áudio e vídeo para tecnologias de virtualização compatíveis. Em conformidade com os regulamentos de telefonia padrão, o suporte para o E911 também está incluído. As seções a seguir descrevem as tecnologias de virtualização que são compatíveis com o plug-in VDI do Lync e as limitações de recursos conhecidos.
  
#### <a name="support-for-virtualization-technologies"></a>Suporte para Tecnologias de Virtualização

O plug-in VDI do Lync oferece suporte a sessões completas de área de trabalho remota no cenário de área de trabalho virtual pessoal, mas não no cenário da sessão da área de trabalho remota. Esses cenários podem ser descritos como segue:
  
- **Com suporte: Áreas de Trabalho Virtuais Personalizadas ou Virtual Desktop Infrastructure (VDI). ** Neste cenário, cada usuário faz logon em uma área de trabalho virtual personalizável e pode salvar arquivos na área de trabalho que persiste entre as sessões. Os serviços de área de trabalho remota da Microsoft e o modo de exibição do horizonte do VMware são implementações que foram testadas para uso com o Skype for Business 2015. Outras implementações em processo de validação incluem o Citrix XenDesktop. Para obter informações sobre ambientes VDI específicos do fornecedor e hardware cliente que foram testados pela Microsoft, consulte [infraestrutura qualificada para Microsoft Lync](https://go.microsoft.com/fwlink/?LinkID=313435).
    
- **Sem suporte: sessões da área de trabalho remota.** Neste cenário, cada usuário faz logon em uma sessão da área de trabalho virtual genérica que não pode ser personalizada. Os exemplos incluem o Microsoft Remote Desktop Sessions (RDSH) e o Citrix XenApp combinado com o receptor Citrix.
    
O plug-in VDI do Lync não oferece suporte a outras tecnologias de virtualização, como a virtualização de aplicativos, que permite o uso de um aplicativo sem a necessidade de instalação do aplicativo completo localmente. Exemplos de implementações incluem o Citrix XenApp e a Microsoft Application Virtualization (App-V). Aplicação de streaming, comunicação remota de aplicativos e modelos de virtualização mistos (por exemplo, comunicação remota de aplicativos em toda a área de trabalho remota) não são suportados.
  
O plug-in VDI do Lync foi projetado para usar APIs independentes de plataforma chamadas DVCs (canais virtuais dinâmicos). Para cenários que não têm suporte explicitamente, consulte as instruções de suporte do provedor sobre soluções de VDI.
  
#### <a name="lync-vdi-plug-in-prerequisites"></a>Pré-requisitos do plug-in Lync VDI
<a name="VDI_prereq"> </a>

Em um ambiente VDI, as máquinas virtuais e o computador local do usuário devem atender aos requisitos descritos nesta seção.
  
> [!NOTE]
>  Seu provedor de soluções de virtualização pode fornecer detalhes de como instalar e implantar o ambiente. Para obter informações gerais sobre a implantação de um ambiente virtualizado com base no Hyper-V e nos serviços de área de trabalho remota, consulte os seguintes artigos na Microsoft library: [Hyper-v](https://go.microsoft.com/fwlink/p/?linkid=247514), [serviços de área de trabalho remota no Windows Server 2008 R2](https://go.microsoft.com/fwlink/p/?linkid=247513) 
  
Máquinas virtuais devem ser configuradas com o Windows 8, Windows 7 ou Windows Server 2008 R2 com os service packs mais recentes.
  
O computador local do usuário deve atender aos seguintes requisitos:
  
- O usuário deve ser hospedado no Skype for Business Server ou no Lync Server 2013.
    
- O computador local deve estar executando o Windows Embedded Standard 7 com SP1, o Windows 7 com SP1 ou o Windows 8.
    
- Se você estiver usando os serviços de área de trabalho remota, escolha o plug-in do Lync VDI de 32 bits ou 64 bits para corresponder ao sistema operacional do computador local. Não é obrigatório que o computador local e a máquina virtual tenham sistemas operacionais de 32 bits ou de 64 bits. Se você estiver usando outra plataforma ou solução de virtualização, consulte os requisitos do provedor.
    
- O computador local deve estar executando a [versão mais recente do cliente da área de trabalho remota](https://go.microsoft.com/fwlink/p/?LinkId=268032). Instale as últimas atualizações do cliente de Serviços de Área de Trabalho Remota da Microsoft ou o software cliente de área de trabalho remota mais recente do seu provedor de soluções de virtualização. 
    
- No computador local, as configurações do cliente de área de trabalho remota devem ser definidas para que o áudio seja reproduzido no computador local e a gravação remota seja desabilitada. Para definir essas configurações para a conexão de área de trabalho remota no Windows, consulte a próxima seção, "para definir as configurações de conexão de área de trabalho remota". 
    
O plug-in VDI da Microsoft está disponível no plugin [do Microsoft LYNC vdi 2013 (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35457) ou no [plugin do microsoft Lync vdi 2013 (64 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=35454).
  
#### <a name="known-feature-limitations"></a>Limitações conhecidas dos recursos
<a name="VDI_prereq"> </a>

Veja a seguir as limitações conhecidas quando você usa o cliente Skype for Business 2015 em um ambiente VDI:
  
Há suporte limitado para recursos de delegação de chamada e de anonimato do agente do grupo de resposta.
  
Não há suporte aos seguintes recursos:
  
- Páginas de ajuste de dispositivo de áudio integrado e dispositivo de vídeo
    
- Vídeo com modo de exibição múltipla.
    
- Gravação de conversas.
    
- Ingressar em reuniões anonimamente (isto é, ingressando em reuniões do Skype for Business hospedadas por uma organização que não se federa à sua organização).
    
- Usar o plug-in VDI do Lync juntamente com um dispositivo Lync Phone Edition.
    
- Continuidade de chamadas em caso de indisponibilidade da rede.
    
- Toques personalizados e recursos de música em espera.
    
O plug-in VDI do Lync não é compatível com um ambiente do Office 365.
  
> [!NOTE]
> O Citrix RealTime Optimization Pack dá suporte ao Office 365. Para ambientes virtuais baseados em Citrix, examine a documentação de [visão geral técnica](https://docs.citrix.com/en-us/hdx-optimization/2-0/hdx-realtime-optimization-pack-about.mdl) da Citrix para obter a lista de recursos e versões com suporte.
  
## <a name="see-also"></a>Confira também
<a name="Citrix_RT"> </a>

[Implantar o plug-in VDI do Lync com o Skype for Business Server](../../deploy/deploy-clients/deploy-the-lync-vdi-plug-in.md)

